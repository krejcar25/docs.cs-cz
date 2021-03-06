---
title: "Postupy: dotazování sestavení & č. 39; s Metadata s reflexí (LINQ) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b15fbed050c35dbe7c31eaa61accefe96d4b15da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-an-assembly39s-metadata-with-reflection-linq-c"></a>Postupy: dotazování sestavení & č. 39; s Metadata s reflexí (LINQ) (C#)
Následující příklad ukazuje, jak lze použít LINQ s reflexí načíst konkrétní metadata o metodách, které splňují zadané kritérium. V takovém případě bude dotaz vrátí názvy ze všech metod sestavení, které vrací výčtové typy jako je například pole.  
  
## <a name="example"></a>Příklad  
  
```csharp  
using System.Reflection;  
using System.IO;  
namespace LINQReflection  
{  
    class ReflectionHowTO  
    {  
        static void Main(string[] args)  
        {  
            Assembly assembly = Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089");  
            var pubTypesQuery = from type in assembly.GetTypes()  
                        where type.IsPublic  
                            from method in type.GetMethods()  
                            where method.ReturnType.IsArray == true   
                                || ( method.ReturnType.GetInterface(  
                                    typeof(System.Collections.Generic.IEnumerable<>).FullName ) != null  
                                && method.ReturnType.FullName != "System.String" )  
                            group method.ToString() by type.ToString();  
  
            foreach (var groupOfMethods in pubTypesQuery)  
            {  
                Console.WriteLine("Type: {0}", groupOfMethods.Key);  
                foreach (var method in groupOfMethods)  
                {  
                    Console.WriteLine("  {0}", method);  
                }  
            }  
  
            Console.WriteLine("Press any key to exit");  
            Console.ReadKey();  
        }  
    }    
}  
```  
  
 V příkladu se používá <xref:System.Reflection.Assembly.GetTypes%2A> metoda vrátí pole typů v zadaném sestavení. [Kde](../../../../csharp/language-reference/keywords/where-clause.md) filtr tak, aby se vrátí jenom veřejné typy. Pro každý typ veřejné poddotazu je generována pomocí <xref:System.Reflection.MethodInfo> pole, která je vrácena z <xref:System.Type.GetMethods%2A> volání. Tyto výsledky se filtrují vrátit pouze těch metod, jejichž návratový typ je nebo pole s jiným typem, který implementuje <xref:System.Collections.Generic.IEnumerable%601>. Nakonec jsou tyto výsledky seskupené podle pomocí názvu typu jako klíč.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Vytvoření projektu, jehož cílem rozhraní .NET Framework verze 3.5 nebo vyšší s odkazem na System.Core.dll a `using` direktivy pro obory názvů System.Linq a System.IO.  
  
## <a name="see-also"></a>Viz také  
 [LINQ na objekty (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
