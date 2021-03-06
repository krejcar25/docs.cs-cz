---
title: "Postupy: čtení dat objektů ze souboru XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6a3389de2f3272a546a7380ef386f5d88666e6d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a>Postupy: čtení dat objektů ze souboru XML (C#)
Tento příklad čte data objektu, která byla dříve zapsána do souboru XML pomocí <xref:System.Xml.Serialization.XmlSerializer> třídy.  
  
## <a name="example"></a>Příklad  
  
```csharp  
public class Book  
{  
    public String title;  
}         
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =   
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Nahraďte názvem souboru "c:\temp\SerializationOverview.xml" název souboru, který obsahuje serializovaná data. Další informace o serializaci dat najdete v tématu [postupy: zápis dat objektů do souboru XML (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
 Třída musí mít veřejný konstruktor bez parametrů.  
  
 Pouze veřejné vlastnosti a pole jsou deserializovat.  
  
## <a name="robust-programming"></a>Robustní programování  
 Následující podmínky mohou způsobit výjimku:  
  
-   Třída serializována nemá veřejný konstruktor bez parametrů.  
  
-   Data v souboru nepředstavuje data ze třídy k deserializaci.  
  
-   Soubor neexistuje (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework  
 Vždy zkontrolujte vstupy a nikdy deserializaci dat z nedůvěryhodného zdroje. Objekt znovu vytvořit běží na místním počítači s oprávněními kód, který ji deserializovat. Před použitím dat ve své aplikaci ověřte všechny vstupy.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.IO.StreamWriter>  
 [Postupy: zápis dat objektů do souboru XML (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)  
 [Serializace (C#)](../../../../csharp/programming-guide/concepts/serialization/index.md)  
 [Průvodce programováním v C#](../../../../csharp/programming-guide/index.md)
