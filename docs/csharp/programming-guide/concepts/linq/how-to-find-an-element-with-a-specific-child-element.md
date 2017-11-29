---
title: "Postupy: vyhledávání prvku s konkrétní podřízeným elementem (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d4d865b6e412f6f039df3578340db046ca59fa6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="3c634-102">Postupy: vyhledávání prvku s konkrétní podřízeným elementem (C#)</span><span class="sxs-lookup"><span data-stu-id="3c634-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="3c634-103">Toto téma ukazuje, jak najít konkrétní element, který má podřízený element s konkrétní hodnotou.</span><span class="sxs-lookup"><span data-stu-id="3c634-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c634-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="3c634-104">Example</span></span>  
 <span data-ttu-id="3c634-105">Vyhledá v příkladu `Test` element, který má `CommandLine` podřízený element s hodnotou "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="3c634-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="3c634-106">Tento příklad používá následující dokumentu XML: [ukázkový soubor XML: Konfigurace testu (technologie LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3c634-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="3c634-107">Tento kód vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="3c634-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="3c634-108">Příklad</span><span class="sxs-lookup"><span data-stu-id="3c634-108">Example</span></span>  
 <span data-ttu-id="3c634-109">Následující příklad ukazuje stejný dotaz pro formát XML, který je v oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="3c634-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="3c634-110">Další informace najdete v tématu [práci s obory názvů XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="3c634-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="3c634-111">Tento příklad používá následující dokumentu XML: [ukázkový soubor XML: Konfigurace testu v Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="3c634-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="3c634-112">Tento kód vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="3c634-112">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c634-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="3c634-113">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="3c634-114">Základní dotazy (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3c634-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="3c634-115">Přehled standardních operátorů dotazu (C#)</span><span class="sxs-lookup"><span data-stu-id="3c634-115">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="3c634-116">Operace projekce (C#)</span><span class="sxs-lookup"><span data-stu-id="3c634-116">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)