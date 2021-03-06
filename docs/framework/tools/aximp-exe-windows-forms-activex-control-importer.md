---
title: "Aximp.exe (importér ovládacích prvků ActiveX Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ActiveX controls, hosting in Windows Forms
- ActiveX Control Importer
- type definitions, converting
- Aximp.exe
- Windows Forms ActiveX Control Importer
ms.assetid: 482c0d83-7144-4497-b626-87d2351b78d0
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ebde5bd48b02c20f7d607ebcda2b18ed0830c569
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="aximpexe-windows-forms-activex-control-importer"></a>Aximp.exe (importér ovládacích prvků ActiveX Windows Forms)
Importér ovládacích prvků ActiveX převede definice typů v knihovně typů modelu COM pro ovládací prvek ActiveX na ovládací prvek Windows Forms.  
  
 Windows Forms můžou hostovat pouze ovládací prvky Windows Forms – to znamená, třídy, které jsou odvozeny od <xref:System.Windows.Forms.Control>. Aximp.exe generuje obálkovou třídu pro ovládací prvek ActiveX, který může být hostován na Windows Forms. To umožňuje použít stejnou podporu návrhu a programovací metody jako pro ostatní ovládací prvky Windows Forms.  
  
 K hostování ovládacího prvku ActiveX, musíte vygenerovat obálku ovládací prvek, který je odvozen od <xref:System.Windows.Forms.AxHost>. Tento ovládací prvek obálky obsahuje instanci původního ovládacího prvku ActiveX. Dokáže komunikovat s ovládacím prvkem ActiveX, ale je zobrazen jako ovládací prvek Windows Forms. Tento vygenerovaný ovládací prvek hostuje ovládací prvek ActiveX a zpřístupňuje jeho vlastnosti, metody a události, jako by náležely vygenerovanému ovládacímu prvku.  
  
 Tento nástroj je automaticky nainstalován se sadou Visual Studio. Chcete-li spustit tento nástroj, použijte příkazový řádek vývojáře (nebo příkazový řádek Visual Studio v systému Windows 7). Další informace najdete v tématu [příkazového řádku](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 V příkazovém řádku zadejte následující:  
  
## <a name="syntax"></a>Syntaxe  
  
```  
aximp [options]{file.dll | file.ocx}  
```  
  
## <a name="remarks"></a>Poznámky  
  
|Argument|Popis|  
|--------------|-----------------|  
|*soubor*|Název zdrojového souboru obsahujícího ovládací prvek ActiveX, který má být převeden. Argument souboru musí mít příponu .dll nebo .ocx.|  
  
|Možnost|Popis|  
|------------|-----------------|  
|`/delaysign`|Určuje, že Aximp.exe podepíše výsledný ovládací prvek pomocí zpožděného podepisování. Tato možnost je nutné zadat s buď `/keycontainer:`, `/keyfile:`, nebo `/publickey:` možnost. Další informace o procesu zpožděné podepisování najdete v tématu [zpoždění podepsání sestavení](../../../docs/framework/app-domains/delay-sign-assembly.md).|  
|`/help`|Zobrazí syntaxi příkazu a možnosti nástroje.|  
|`/keycontainer:`*containerName*|Podepíše výsledné ovládacího prvku se silným názvem pomocí pár veřejného a privátního klíče najít v kontejneru klíčů určeného *containerName*.|  
|`/keyfile:`*filename*|Podepíše výsledné ovládacího prvku se silným názvem pomocí vydavatele oficiální pár veřejného a privátního klíče v nalezen *filename*.|  
|`/nologo`|Potlačí zobrazení úvodního nápisu společnosti Microsoft.|  
|`/out:`*filename*|Určuje název sestavení, které se má vytvořit.|  
|`/publickey:`*filename*|Podepíše výsledné ovládacího prvku se silným názvem pomocí veřejného klíče v souboru určeného nalezen *filename*.|  
|`/rcw:`*filename*|Používá určenou obálku volatelnou modulem runtime namísto generování nové. Můžete zadat více instancí. Aktuální adresář se používá pro relativní cesty. Další informace najdete v tématu [obálka volatelná za běhu](../../../docs/framework/interop/runtime-callable-wrapper.md).|  
|`/silent`|Potlačí zobrazování zpráv o úspěšném dokončení.|  
|`/source`|Generuje zdrojový kód jazyka C# pro obálku Windows Forms.|  
|`/verbose`|Určuje režim podrobného vypisování; zobrazuje dodatečné informace o průběhu.|  
|`/?`|Zobrazí syntaxi příkazu a možnosti nástroje.|  
  
 Aximp.exe najednou převede celé knihovny typů ovládacího prvku ActiveX a vytvoří sadu sestavení, která obsahují metadata Common Language Runtime (CML) a implementaci ovládacích prvků pro typy definované v původní knihovně typů. Generované soubory jsou pojmenovány podle následujícího vzoru:  
  
 běžné proxy runtime jazyka pro typy modelu COM: *progid*.dll  
  
 Windows Forms proxy pro ovládací prvky ActiveX (kde Ax označuje ActiveX): Ax*progid*.dll  
  
> [!NOTE]
>  Pokud název členu ovládacího prvku ActiveX odpovídá názvu definovanému v rozhraní .NET Framework, Aximp.exe při vytváření odvozené třídy AxHost před název člena přidá „Ctl“. Například, pokud ovládací prvek ActiveX má člen nazvaný „Layout“, přejmenuje se v odvozené třídě AxHost na „CtlLayout“, protože událost Layout je definována v rámci .NET Framework.  
  
 Můžete zkontrolovat tyto soubory generované s nástroji, jako [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md).  
  
 Použití Aximp.exe za účelem generování sestavení .NET pro ovládací prvek ActiveX pro webový prohlížeč (shdocvw.dll) není podporováno.  
  
 Při spuštění Aximp.exe přes shdocvw.dll se vždy vytvoří další soubor s názvem shdocvw.dll v adresáři, ze kterého je nástroj spuštěn. Pokud je tento vygenerovaný soubor umístěn v adresáři Documents and Settings, způsobuje problémy v aplikacích Microsoft Internet Explorer a Průzkumník Windows. Po restartování počítače systém Windows hledá v adresáři Documents and Settings před adresářem system32, aby našel kopii souboru shdocvw.dll. Použije kopii, kterou najde v adresáři Documents and Settings a pokusí se načíst spravované obálky. Aplikace Internet Explorer a Průzkumník Windows nebudou správně fungovat, protože spoléhají na vykreslovací modul ve verzi shdocvw.dll v adresáři system32. Pokud nastane tento problém, odstraňte kopii souboru shdocvw.dll v adresáři Documents and Settings a restartujte počítač.  
  
 Použití Aximp.exe se souborem shdocvw.dll k vytvoření sestavení .NET pro použití při vývoji aplikace může také způsobit problémy. V tomto případě aplikace načte systémovou verzi souboru shdocvw.dll i vygenerovanou verzi a může dát přednost verzi systému. V takovém případě se při pokusu o načtení webové stránky uvnitř ovládacího prvku ActiveX webového prohlížeče uživatelům může zobrazit dialogové okno Otevřít/Uložit. Když uživatel klikne na **otevřete**, otevřou se webové stránky v aplikaci Internet Explorer. K této situaci dochází pouze u počítačů používajících aplikaci Internet Explorer verze 6 nebo starší. K tomuto problému zabránit, použijte spravovaný <xref:System.Windows.Forms.WebBrowser> řízení nebo použijte [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ke generování spravované shdocvw.dll, jak je popsáno v [postup: Přidejte odkazy na knihovny typů](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md).  
  
## <a name="example"></a>Příklad  
 Následující příkaz vytvoří MediaPlayer.dll a AxMediaPlayer.dll pro ovládací prvek Media Player `msdxm.ocx`.  
  
```  
aximp c:\systemroot\system32\msdxm.ocx  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroje](../../../docs/framework/tools/index.md)  
 [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)
