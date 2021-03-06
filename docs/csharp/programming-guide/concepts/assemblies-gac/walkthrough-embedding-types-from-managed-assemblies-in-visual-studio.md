---
title: "Návod: Vložení typů z řízených sestavení v sadě Visual Studio (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5b07b940d6287de0caf41c7d15f3036ad4041ad0
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a>Návod: Vložení typů z řízených sestavení v sadě Visual Studio (C#)
Pokud jste pro vložení informací o typu ze spravovaných sestavení se silným názvem, můžete volně spojte typy v aplikaci k dosažení nezávislost verze. To znamená váš program může být napsán používat typy z více verzí aplikace spravované knihovny aniž byste museli zopakovat pro každou verzi.  
  
 Typ vložení se často používá se spoluprací COM, jako je například aplikace, která používá objekty automatizace z aplikace Microsoft Office. Vložení informací o typu umožňuje ve stejném sestavení programu pro práci s různými verzemi nástroje Microsoft Office na různých počítačích. Však můžete použít také typu vložení v rámci řešení pro plně spravovaná.  
  
 Lze jej vkládat informace o typu ze sestavení, který má následující vlastnosti:  
  
-   Sestavení zpřístupní alespoň jeden veřejné rozhraní.  
  
-   Vložené rozhraní jsou opatřen poznámkou `ComImport` atribut a `Guid` atribut (a jedinečný identifikátor GUID).  
  
-   Sestavení je opatřen poznámkou `ImportedFromTypeLib` atribut nebo `PrimaryInteropAssembly` atribut a úroveň sestavení `Guid` atribut. (Ve výchozím nastavení, zahrnují šablony projektů Visual C# úrovni sestavení `Guid` atributů.)  
  
 Po zadání veřejného rozhraní, která může být vložen, můžete vytvořit runtime třídy, které implementují těchto rozhraní. Program klienta můžete pak vložení informací o typu pro tyto rozhraní v době návrhu pomocí odkazování na sestavení, které obsahuje veřejné rozhraní a nastavení `Embed Interop Types` vlastnost odkazu na `True`. Jde o ekvivalent pomocí příkazového řádku kompilátoru a odkazování na sestavení s použitím `/link` – možnost kompilátoru. Program klienta pak můžete načíst instancí objektů vaší runtime, která je zadán jako těchto rozhraní. Pokud vytvoříte novou verzi vašeho sestavení silným názvem modulu runtime, není nutné zopakovat s sestavení aktualizované runtime program klienta. Místo toho program klienta budou nadále používat kteroukoli verzi modulu runtime sestavení je k dispozici, pomocí informací o vloženého typu pro veřejné rozhraní.  
  
 Vzhledem k tomu, že primární funkce typ vnoření je podpora vložení informací o typu ze sestavení vzájemné spolupráce COM, při vložení informací o typu ve plně spravovaná řešení platí následující omezení:  
  
-   Pouze atributy, které jsou specifické pro zprostředkovatele komunikace s objekty COM jsou vloženy; ostatní atributy se ignorují.  
  
-   Pokud typu používá obecné parametry a typ obecný parametr je vloženého typu, typu nelze použít v hranici sestavení. Při překročení hranici sestavení příklady volání metody z jiného sestavení nebo typ odvozování z typu definovaný v jiném sestavení.  
  
-   Konstanty nejsou vložena.  
  
-   <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> Třída nepodporuje vloženého typu jako klíč. Můžete implementovat vlastní typ slovníku pro podporu vloženého typu jako klíč.  
  
 V tomto návodu se postupujte takto:  
  
-   Vytvořte sestavení se silným názvem, který má veřejné rozhraní, který obsahuje informace o typu, kterou můžete vložit.  
  
-   Vytvořte sestavení silným názvem modulu runtime, který implementuje této veřejné rozhraní.  
  
-   Vytvořte program klienta, který se vloží informací o typu ze veřejné rozhraní a vytvoří instanci třídy ze sestavení modulu runtime.  
  
-   Upravit a znovu sestavte sestavení za běhu.  
  
-   Spusťte klientskou aplikaci, která v tématu, aby se používal novou verzi modulu runtime sestavení bez nutnosti její kompilace programu klienta.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a>Vytváření rozhraní  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a>Vytvoření projektu typu ekvivalenční rozhraní  
  
1.  V sadě Visual Studio na **soubor** nabídce zvolte **nový** a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogovém **typy projektů** podokně, ujistěte se, že **Windows** je vybrána. Vyberte **knihovny tříd** v **šablony** podokně. V **název** zadejte `TypeEquivalenceInterface`a potom klikněte na **OK**. Vytvoření nového projektu.  
  
3.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na soubor Class1.cs a klikněte na **přejmenovat**. Přejmenujte soubor `ISampleInterface.cs` a stiskněte klávesu ENTER. Přejmenování souboru také přejmenuje třídy pro `ISampleInterface`. Tato třída bude reprezentovat veřejné rozhraní pro třídu.  
  
4.  Klikněte pravým tlačítkem na projekt TypeEquivalenceInterface a klikněte na tlačítko **vlastnosti**. Klikněte **sestavení** kartě. Nastavte výstupní cesta na některé platné místo ve svém vývojovém počítači, jako je třeba `C:\TypeEquivalenceSample`. Toto umístění se taky použije později v tomto návodu.  
  
5.  Při úpravách stále vlastností projektu, klikněte **podpisování** karta. Vyberte **podepsání sestavení** možnost. V **vyberte soubor klíče se silným názvem** seznamu, klikněte na tlačítko **< nová... >**. V **název souboru klíče** zadejte `key.snk`. Vymazat **chránit Moje soubor klíče s heslem** zaškrtávací políčko. Click **OK**.  
  
6.  Otevřete soubor ISampleInterface.cs. Přidejte následující kód do souboru třídy ISampleInterface k vytvoření rozhraní ISampleInterface.  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
  
    namespace TypeEquivalenceInterface  
    {  
        [ComImport]  
        [Guid("8DA56996-A151-4136-B474-32784559F6DF")]  
        public interface ISampleInterface  
        {  
            void GetUserInput();  
            string UserInput { get; }  
        }  
    }  
    ```  
  
7.  Na **nástroje** nabídky, klikněte na tlačítko **vytvořit Guid**. V **vytvořit GUID** dialogové okno, klikněte na tlačítko **registru formátu** a pak klikněte na **kopie**. Klikněte na tlačítko **ukončení**.  
  
8.  V `Guid` atribut, odstraňte ukázka GUID a vložte identifikátor GUID, který jste zkopírovali ze **vytvořit GUID** dialogové okno. Odebrání zkopírovaný GUID složené závorky ({}).  
  
9. V **Průzkumníku řešení**, rozbalte **vlastnosti** složky. Poklikejte na soubor AssemblyInfo.cs. Do souboru přidejte následující atribut.  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     Uložte soubor.  
  
10. Uložte projekt.  
  
11. Klikněte pravým tlačítkem na projekt TypeEquivalenceInterface a klikněte na tlačítko **sestavení**. Soubor DLL knihovny tříd jsou kompilované a uložit na zadaná sestavení výstupní cestu (například C:\TypeEquivalenceSample).  
  
## <a name="creating-a-runtime-class"></a>Vytvoření třídy modulu Runtime  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a>Vytvoření projektu typu ekvivalenční modulu runtime  
  
1.  V sadě Visual Studio na **soubor** nabídky, přejděte na příkaz **nový** a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogovém **typy projektů** podokně, ujistěte se, že **Windows** je vybrána. Vyberte **knihovny tříd** v **šablony** podokně. V **název** zadejte `TypeEquivalenceRuntime`a potom klikněte na **OK**. Vytvoření nového projektu.  
  
3.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na soubor Class1.cs a klikněte na **přejmenovat**. Přejmenujte soubor `SampleClass.cs` a stiskněte klávesu ENTER. Přejmenování souboru také přejmenuje třídy pro `SampleClass`. Tato třída se implementovat `ISampleInterface` rozhraní.  
  
4.  Klikněte pravým tlačítkem na projekt TypeEquivalenceRuntime a klikněte na tlačítko **vlastnosti**. Klikněte **sestavení** kartě. Nastavit výstupní cesta do stejného umístění, které jste použili v TypeEquivalenceInterface projektu, například `C:\TypeEquivalenceSample`.  
  
5.  Při úpravách stále vlastností projektu, klikněte **podpisování** karta. Vyberte **podepsání sestavení** možnost. V **vyberte soubor klíče se silným názvem** seznamu, klikněte na tlačítko **< nová... >**. V **název souboru klíče** zadejte `key.snk`. Vymazat **chránit Moje soubor klíče s heslem** zaškrtávací políčko. Click **OK**.  
  
6.  Klikněte pravým tlačítkem na projekt TypeEquivalenceRuntime a klikněte na tlačítko **přidat odkaz na**. Klikněte **Procházet** kartě a přejděte do složky výstupní cesta. Vyberte soubor TypeEquivalenceInterface.dll a klikněte na tlačítko **OK**.  
  
7.  V **Průzkumníku řešení**, rozbalte **odkazy** složky. Vyberte odkaz na TypeEquivalenceInterface. V okně Vlastnosti pro odkaz na TypeEquivalenceInterface nastavit **konkrétní verzi** vlastnost **False**.  
  
8.  Přidejte následující kód do souboru SampleClass třídy pro vytvoření třídy SampleClass.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
  
    namespace TypeEquivalenceRuntime  
    {  
        public class SampleClass : ISampleInterface  
        {  
            private string p_UserInput;  
            public string UserInput { get { return p_UserInput; } }  
  
            public void GetUserInput()  
            {  
                Console.WriteLine("Please enter a value:");  
                p_UserInput = Console.ReadLine();  
            }  
        }  
    )  
    ```  
  
9. Uložte projekt.  
  
10. Klikněte pravým tlačítkem na projekt TypeEquivalenceRuntime a klikněte na tlačítko **sestavení**. Soubor DLL knihovny tříd jsou kompilované a uložit na zadaná sestavení výstupní cestu (například C:\TypeEquivalenceSample).  
  
## <a name="creating-a-client-project"></a>Vytvoření projektu klienta  
  
#### <a name="to-create-the-type-equivalence-client-project"></a>Vytvoření projektu klienta ekvivalenční typu  
  
1.  V sadě Visual Studio na **soubor** nabídky, přejděte na příkaz **nový** a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogovém **typy projektů** podokně, ujistěte se, že **Windows** je vybrána. Vyberte **konzolové aplikace** v **šablony** podokně. V **název** zadejte `TypeEquivalenceClient`a potom klikněte na **OK**. Vytvoření nového projektu.  
  
3.  Klikněte pravým tlačítkem na projekt TypeEquivalenceClient a klikněte na tlačítko **vlastnosti**. Klikněte **sestavení** kartě. Nastavit výstupní cesta do stejného umístění, které jste použili v TypeEquivalenceInterface projektu, například `C:\TypeEquivalenceSample`.  
  
4.  Klikněte pravým tlačítkem na projekt TypeEquivalenceClient a klikněte na tlačítko **přidat odkaz na**. Klikněte **Procházet** kartě a přejděte do složky výstupní cesta. Vyberte soubor TypeEquivalenceInterface.dll (ne TypeEquivalenceRuntime.dll) a klikněte na tlačítko **OK**.  
  
5.  V **Průzkumníku řešení**, rozbalte **odkazy** složky. Vyberte odkaz na TypeEquivalenceInterface. V okně Vlastnosti pro odkaz na TypeEquivalenceInterface nastavit **vložit zprostředkovatel komunikace s objekty typy** vlastnost **True**.  
  
6.  Přidejte následující kód do souboru Program.cs vytvoření programu klienta.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
    namespace TypeEquivalenceClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");  
                ISampleInterface sampleClass =   
                    (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");  
                sampleClass.GetUserInput();  
                Console.WriteLine(sampleClass.UserInput);  
                Console.WriteLine(sampleAssembly.GetName().Version.ToString());  
                Console.ReadLine();  
            }  
        }  
    }  
    ```  
  
7.  Stisknutím klávesy CTRL + F5 sestavit a spustit program.  
  
## <a name="modifying-the-interface"></a>Úprava rozhraní  
  
#### <a name="to-modify-the-interface"></a>Chcete-li upravit rozhraní  
  
1.  V sadě Visual Studio na **soubor** nabídky, přejděte na příkaz **otevřete**a potom klikněte na **projekt nebo řešení**.  
  
2.  V **otevřeného projektu** dialogové okno, klikněte pravým tlačítkem na projekt TypeEquivalenceInterface a pak klikněte na tlačítko **vlastnosti**. Klikněte **aplikace** kartě. Klikněte **informací o sestavení** tlačítko. Změna **verze sestavení** a **verze souboru** hodnoty k `2.0.0.0`.  
  
3.  Otevřete soubor SampleInterface.cs. Přidejte následující řádek kódu rozhraní ISampleInterface.  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     Uložte soubor.  
  
4.  Uložte projekt.  
  
5.  Klikněte pravým tlačítkem na projekt TypeEquivalenceInterface a klikněte na tlačítko **sestavení**. Nová verze souboru třídy knihovny DLL je zkompilovat a uloží do výstupní cesta zadaná sestavení (například C:\TypeEquivalenceSample).  
  
## <a name="modifying-the-runtime-class"></a>Úprava Runtime – třída  
  
#### <a name="to-modify-the-runtime-class"></a>Chcete-li upravit runtime – třída  
  
1.  V sadě Visual Studio na **soubor** nabídky, přejděte na příkaz **otevřete**a potom klikněte na **projekt nebo řešení**.  
  
2.  V **otevřeného projektu** dialogové okno pole, klikněte pravým tlačítkem na projekt TypeEquivalenceRuntime a klikněte na tlačítko **vlastnosti**. Klikněte **aplikace** kartě. Klikněte **informací o sestavení** tlačítko. Změna **verze sestavení** a **verze souboru** hodnoty k `2.0.0.0`.  
  
3.  Otevřete soubor SampleClass.cs. Přidejte následující řádky kódu do třídy SampleClass.  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     Uložte soubor.  
  
4.  Uložte projekt.  
  
5.  Klikněte pravým tlačítkem na projekt TypeEquivalenceRuntime a klikněte na tlačítko **sestavení**. Aktualizovaná verze souboru třídy knihovny DLL je zkompilovat a uloží do výstupní cesta dříve zadané sestavení (například C:\TypeEquivalenceSample).  
  
6.  V Průzkumníku souborů otevřete složku výstupu cestu (například C:\TypeEquivalenceSample). Dvakrát klikněte na TypeEquivalenceClient.exe ke spuštění programu. Program se projeví novou verzi sestavení TypeEquivalenceRuntime bez nutnosti znovu kompilovány.  
  
## <a name="see-also"></a>Viz také  
 [/ Link (možnosti kompilátoru C#)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)  
 [Průvodce programováním v jazyce C#](../../../../csharp/programming-guide/index.md)  
 [Programování se sestaveními](../../../../framework/app-domains/programming-with-assemblies.md)  
 [Sestavení a globální mezipaměti sestavení (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
