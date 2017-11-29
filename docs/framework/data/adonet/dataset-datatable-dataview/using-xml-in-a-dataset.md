---
title: "Pomocí XML v datové sadě"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 28c1668dcb9678b65db62c0040adcd116221b92e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="using-xml-in-a-dataset"></a><span data-ttu-id="8eac7-102">Pomocí XML v datové sadě</span><span class="sxs-lookup"><span data-stu-id="8eac7-102">Using XML in a DataSet</span></span>
<span data-ttu-id="8eac7-103">S ADO.NET, můžete vyplnit <xref:System.Data.DataSet> z datového proudu XML nebo dokumentu.</span><span class="sxs-lookup"><span data-stu-id="8eac7-103">With ADO.NET you can fill a <xref:System.Data.DataSet> from an XML stream or document.</span></span> <span data-ttu-id="8eac7-104">Datový proud XML nebo dokument můžete použít k poskytování k <xref:System.Data.DataSet> data, informace o schématu nebo obojí.</span><span class="sxs-lookup"><span data-stu-id="8eac7-104">You can use the XML stream or document to supply to the <xref:System.Data.DataSet> either data, schema information, or both.</span></span> <span data-ttu-id="8eac7-105">Informací získaných z datového proudu XML nebo dokumentů mohou být kombinovány s existující data nebo informace o schématu již existuje v <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="8eac7-105">The information supplied from the XML stream or document can be combined with existing data or schema information already present in the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="8eac7-106">ADO.NET umožňuje taky vytvořit reprezentaci XML <xref:System.Data.DataSet>, s nebo bez jeho schématu, aby bylo možné přenosu <xref:System.Data.DataSet> přes HTTP pro použití jiná aplikace nebo platformu XML povolen.</span><span class="sxs-lookup"><span data-stu-id="8eac7-106">ADO.NET also allows you to create an XML representation of a <xref:System.Data.DataSet>, with or without its schema, in order to transport the <xref:System.Data.DataSet> across HTTP for use by another application or XML-enabled platform.</span></span> <span data-ttu-id="8eac7-107">V XML reprezentaci <xref:System.Data.DataSet>, budou data zapsána v kódu XML a schématu, pokud je součástí vložený v rámci reprezentace je zapsán pomocí jazyka definice schématu XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="8eac7-107">In an XML representation of a <xref:System.Data.DataSet>, the data is written in XML and the schema, if it is included inline in the representation, is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="8eac7-108">XML a schématu XML poskytují pohodlný formát pro přenos obsahu <xref:System.Data.DataSet> do a ze vzdálených klientů.</span><span class="sxs-lookup"><span data-stu-id="8eac7-108">XML and XML Schema provide a convenient format for transferring the contents of a <xref:System.Data.DataSet> to and from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8eac7-109">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="8eac7-109">In This Section</span></span>  
 [<span data-ttu-id="8eac7-110">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="8eac7-110">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 <span data-ttu-id="8eac7-111">Poskytuje podrobné informace o formátu DiffGram formátu XML, který používá ke čtení a zápis obsahu <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="8eac7-111">Provides details on the DiffGram, an XML format used to read and write the contents of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="8eac7-112">Načítání datové sady z XML</span><span class="sxs-lookup"><span data-stu-id="8eac7-112">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 <span data-ttu-id="8eac7-113">Popisuje různé možnosti, které je třeba zvážit při načítání obsahu <xref:System.Data.DataSet> z dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="8eac7-113">Discusses different options to consider when loading the contents of a <xref:System.Data.DataSet> from an XML document.</span></span>  
  
 [<span data-ttu-id="8eac7-114">Zápis obsah datovou sadu jako XML Data</span><span class="sxs-lookup"><span data-stu-id="8eac7-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 <span data-ttu-id="8eac7-115">Popisuje, jak vygenerovat obsah <xref:System.Data.DataSet> jako XML data a můžete použít různé možnosti formátu XML.</span><span class="sxs-lookup"><span data-stu-id="8eac7-115">Discusses how to generate the contents of a <xref:System.Data.DataSet> as XML data, and the different XML format options you can use.</span></span>  
  
 [<span data-ttu-id="8eac7-116">Načítání informací o schématu sady dat z XML</span><span class="sxs-lookup"><span data-stu-id="8eac7-116">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="8eac7-117">Popisuje <xref:System.Data.DataSet> metod používaných k načtení schématu <xref:System.Data.DataSet> ze souboru XML.</span><span class="sxs-lookup"><span data-stu-id="8eac7-117">Discusses the <xref:System.Data.DataSet> methods used to load the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="8eac7-118">Zápis informací o schématu datovou sadu jako XSD</span><span class="sxs-lookup"><span data-stu-id="8eac7-118">Writing DataSet Schema Information as XSD</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="8eac7-119">Popisuje využití pro schéma XML a jak vygenerovat z <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="8eac7-119">Discusses the uses for an XML Schema and how to generate one from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="8eac7-120">Datové sady a XmlDataDocument synchronizace</span><span class="sxs-lookup"><span data-stu-id="8eac7-120">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 <span data-ttu-id="8eac7-121">Popisuje funkce dostupné v rozhraní .NET Framework synchronní přístupu k relačních i hierarchické zobrazení jednu sadu dat a ukazuje, jak vytvořit synchronní relaci mezi tabulkou <xref:System.Data.DataSet> a <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="8eac7-121">Discusses the capability available in the .NET Framework of synchronous access to both relational and hierarchical views of a single set of data, and shows how to create a synchronous relationship between a <xref:System.Data.DataSet> and an <xref:System.Xml.XmlDataDocument>.</span></span>  
  
 [<span data-ttu-id="8eac7-122">DataRelations vnoření</span><span class="sxs-lookup"><span data-stu-id="8eac7-122">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="8eac7-123">Popisuje význam vnořené <xref:System.Data.DataRelation> objekty při představující obsah <xref:System.Data.DataSet> jako data XML a popisuje, jak k jejich vytvoření.</span><span class="sxs-lookup"><span data-stu-id="8eac7-123">Discusses the importance of nested <xref:System.Data.DataRelation> objects when representing the contents of a <xref:System.Data.DataSet> as XML data, and describes how to create them.</span></span>  
  
 [<span data-ttu-id="8eac7-124">Odvozování relační strukturu datové sady z schématu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="8eac7-124">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="8eac7-125">Popisuje relační struktura nebo schéma z <xref:System.Data.DataSet> vytvořený z schématu XML.</span><span class="sxs-lookup"><span data-stu-id="8eac7-125">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema.</span></span>  
  
 [<span data-ttu-id="8eac7-126">Odvození relační strukturu datové sady z XML</span><span class="sxs-lookup"><span data-stu-id="8eac7-126">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 <span data-ttu-id="8eac7-127">Popisuje výsledné relační struktura nebo schéma z <xref:System.Data.DataSet> vytvořený při odvodit z elementů XML.</span><span class="sxs-lookup"><span data-stu-id="8eac7-127">Describes the resulting relational structure, or schema, of a <xref:System.Data.DataSet> that is created when inferred from XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8eac7-128">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="8eac7-128">Related Sections</span></span>  
 [<span data-ttu-id="8eac7-129">ADO.NET – přehled</span><span class="sxs-lookup"><span data-stu-id="8eac7-129">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="8eac7-130">Popisuje technologie ADO.NET architektura a komponenty a jak je používat pro přístup k existující zdroje dat. také jako ke správě dat aplikací.</span><span class="sxs-lookup"><span data-stu-id="8eac7-130">Describes the ADO.NET architecture and components, and how to use them to access existing data sources as well as to manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eac7-131">Viz také</span><span class="sxs-lookup"><span data-stu-id="8eac7-131">See Also</span></span>  
 [<span data-ttu-id="8eac7-132">Datové sady, DataTables a DataView</span><span class="sxs-lookup"><span data-stu-id="8eac7-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="8eac7-133">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="8eac7-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)