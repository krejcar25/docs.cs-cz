---
title: "Typy uzlů XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3914a2c5c06a2cc73f14bc473984094b474d537e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-xml-nodes"></a><span data-ttu-id="0641b-102">Typy uzlů XML</span><span class="sxs-lookup"><span data-stu-id="0641b-102">Types of XML Nodes</span></span>
<span data-ttu-id="0641b-103">Pokud dokument XML je pro čtení do paměti jako strom uzlů, typy uzlů pro uzly se rozhodla při vytvoření uzly.</span><span class="sxs-lookup"><span data-stu-id="0641b-103">When an XML document is read into memory as a tree of nodes, the node types for the nodes are decided when the nodes are created.</span></span> <span data-ttu-id="0641b-104">XML modelu DOM (Document Object) má několik druhů typy uzlů, dáno World Wide Web Consortium (W3C) a uvedené v části 1.1.1 modelu DOM struktura.</span><span class="sxs-lookup"><span data-stu-id="0641b-104">The XML Document Object Model (DOM) has several kinds of node types, determined by the World Wide Web Consortium (W3C) and listed in section 1.1.1 The DOM Structure Model.</span></span> <span data-ttu-id="0641b-105">Následující tabulka uvádí typy uzlů přiřazené pro daný typ uzlu a krátký popis každého objektu.</span><span class="sxs-lookup"><span data-stu-id="0641b-105">The following table lists the node types, the object assigned to that node type, and a short description of each.</span></span>  
  
|<span data-ttu-id="0641b-106">Typ uzlu DOM</span><span class="sxs-lookup"><span data-stu-id="0641b-106">DOM node type</span></span>|<span data-ttu-id="0641b-107">Objekt</span><span class="sxs-lookup"><span data-stu-id="0641b-107">Object</span></span>|<span data-ttu-id="0641b-108">Popis</span><span class="sxs-lookup"><span data-stu-id="0641b-108">Description</span></span>|  
|-------------------|------------|-----------------|  
|<span data-ttu-id="0641b-109">Dokument</span><span class="sxs-lookup"><span data-stu-id="0641b-109">Document</span></span>|<xref:System.Xml.XmlDocument>|<span data-ttu-id="0641b-110">Kontejner všechny uzly ve stromu.</span><span class="sxs-lookup"><span data-stu-id="0641b-110">The container of all the nodes in the tree.</span></span> <span data-ttu-id="0641b-111">Je také označované jako kořen dokumentu, který není vždy stejná jako kořenový element.</span><span class="sxs-lookup"><span data-stu-id="0641b-111">It is also known as the document root, which is not always the same as the root element.</span></span>|  
|<span data-ttu-id="0641b-112">DocumentFragment</span><span class="sxs-lookup"><span data-stu-id="0641b-112">DocumentFragment</span></span>|<xref:System.Xml.XmlDocumentFragment>|<span data-ttu-id="0641b-113">Dočasné kontejner obsahující jeden nebo více uzlů bez jakékoli stromové struktury.</span><span class="sxs-lookup"><span data-stu-id="0641b-113">A temporary bag containing one or more nodes without any tree structure.</span></span>|  
|<span data-ttu-id="0641b-114">DocumentType</span><span class="sxs-lookup"><span data-stu-id="0641b-114">DocumentType</span></span>|<xref:System.Xml.XmlDocumentType>|<span data-ttu-id="0641b-115">Představuje `<!DOCTYPE…>` uzlu.</span><span class="sxs-lookup"><span data-stu-id="0641b-115">Represents the `<!DOCTYPE…>` node.</span></span>|  
|<span data-ttu-id="0641b-116">Třída EntityReference</span><span class="sxs-lookup"><span data-stu-id="0641b-116">EntityReference</span></span>|<xref:System.Xml.XmlEntityReference>|<span data-ttu-id="0641b-117">Představuje text odkazu-rozšířit entity.</span><span class="sxs-lookup"><span data-stu-id="0641b-117">Represents the non-expanded entity reference text.</span></span>|  
|<span data-ttu-id="0641b-118">Prvek</span><span class="sxs-lookup"><span data-stu-id="0641b-118">Element</span></span>|<xref:System.Xml.XmlElement>|<span data-ttu-id="0641b-119">Představuje uzel elementu.</span><span class="sxs-lookup"><span data-stu-id="0641b-119">Represents an element node.</span></span>|  
|<span data-ttu-id="0641b-120">Line</span><span class="sxs-lookup"><span data-stu-id="0641b-120">Attr</span></span>|<xref:System.Xml.XmlAttribute>|<span data-ttu-id="0641b-121">Je atribut elementu.</span><span class="sxs-lookup"><span data-stu-id="0641b-121">Is an attribute of an element.</span></span>|  
|<span data-ttu-id="0641b-122">ProcessingInstruction</span><span class="sxs-lookup"><span data-stu-id="0641b-122">ProcessingInstruction</span></span>|<xref:System.Xml.XmlProcessingInstruction>|<span data-ttu-id="0641b-123">Je uzel zpracování instrukcí.</span><span class="sxs-lookup"><span data-stu-id="0641b-123">Is a processing instruction node.</span></span>|  
|<span data-ttu-id="0641b-124">Komentář</span><span class="sxs-lookup"><span data-stu-id="0641b-124">Comment</span></span>|<xref:System.Xml.XmlComment>|<span data-ttu-id="0641b-125">Uzel komentáře.</span><span class="sxs-lookup"><span data-stu-id="0641b-125">A comment node.</span></span>|  
|<span data-ttu-id="0641b-126">Text</span><span class="sxs-lookup"><span data-stu-id="0641b-126">Text</span></span>|<xref:System.Xml.XmlText>|<span data-ttu-id="0641b-127">Text, které patří do elementu nebo atributu.</span><span class="sxs-lookup"><span data-stu-id="0641b-127">Text belonging to an element or attribute.</span></span>|  
|<span data-ttu-id="0641b-128">CDATASection</span><span class="sxs-lookup"><span data-stu-id="0641b-128">CDATASection</span></span>|<xref:System.Xml.XmlCDataSection>|<span data-ttu-id="0641b-129">Představuje CDATA.</span><span class="sxs-lookup"><span data-stu-id="0641b-129">Represents CDATA.</span></span>|  
|<span data-ttu-id="0641b-130">Entity</span><span class="sxs-lookup"><span data-stu-id="0641b-130">Entity</span></span>|<xref:System.Xml.XmlEntity>|<span data-ttu-id="0641b-131">Představuje `<!ENTITY…>` deklarace ve formátu XML dokumentu z dokumentu interní typ definice (DTD) podmnožinu nebo z externí specifikace DTD a parametr entity.</span><span class="sxs-lookup"><span data-stu-id="0641b-131">Represents the `<!ENTITY…>` declarations in an XML document, either from an internal document type definition (DTD) subset or from external DTDs and parameter entities.</span></span>|  
|<span data-ttu-id="0641b-132">Zápis</span><span class="sxs-lookup"><span data-stu-id="0641b-132">Notation</span></span>|<xref:System.Xml.XmlNotation>|<span data-ttu-id="0641b-133">Představuje notace deklarované v DTD.</span><span class="sxs-lookup"><span data-stu-id="0641b-133">Represents a notation declared in the DTD.</span></span>|  
  
 <span data-ttu-id="0641b-134">I když atribut (*line*), je uvedena v W3C DOM úrovně 1 části 1.2 základní rozhraní jako uzel, není to považováno za podřízený element uzlů.</span><span class="sxs-lookup"><span data-stu-id="0641b-134">Even though an attribute (*attr*) is listed in the W3C DOM Level 1 section 1.2 Fundamental Interfaces as a node, it is not considered a child of any element node.</span></span>  
  
 <span data-ttu-id="0641b-135">Následující tabulka uvádí typy dalšího uzlu není definovaných pomocí W3C, ale jsou k dispozici pro použití v objektový model rozhraní Microsoft .NET Framework jako **XmlNodeType** výčty.</span><span class="sxs-lookup"><span data-stu-id="0641b-135">The following table shows additional node types not defined by the W3C, however they are available for use in the Microsoft .NET Framework object model as **XmlNodeType** enumerations.</span></span> <span data-ttu-id="0641b-136">Proto neexistuje odpovídající sloupec typu uzlu DOM pro tyto typy uzlů.</span><span class="sxs-lookup"><span data-stu-id="0641b-136">Therefore, there is no matching DOM node type column for these node types.</span></span>  
  
|<span data-ttu-id="0641b-137">Typ uzlu</span><span class="sxs-lookup"><span data-stu-id="0641b-137">Node type</span></span>|<span data-ttu-id="0641b-138">Popis</span><span class="sxs-lookup"><span data-stu-id="0641b-138">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|<span data-ttu-id="0641b-139">Představuje uzel deklarace `<?xml version="1.0"…>`.</span><span class="sxs-lookup"><span data-stu-id="0641b-139">Represents the declaration node `<?xml version="1.0"…>`.</span></span>|  
|<xref:System.Xml.XmlSignificantWhitespace>|<span data-ttu-id="0641b-140">Představuje významné prázdné znaky, které je prázdné místo v smíšený obsah.</span><span class="sxs-lookup"><span data-stu-id="0641b-140">Represents significant white space, which is white space in mixed content.</span></span>|  
|<xref:System.Xml.XmlWhitespace>|<span data-ttu-id="0641b-141">Představuje prázdné znaky v obsahu elementu.</span><span class="sxs-lookup"><span data-stu-id="0641b-141">Represents the white space in the content of an element.</span></span>|  
|<span data-ttu-id="0641b-142">EndElement</span><span class="sxs-lookup"><span data-stu-id="0641b-142">EndElement</span></span>|<span data-ttu-id="0641b-143">Vrácená při **XmlReader** získá na konec elementu.</span><span class="sxs-lookup"><span data-stu-id="0641b-143">Returned when **XmlReader** gets to the end of an element.</span></span><br /><br /> <span data-ttu-id="0641b-144">Příklad kódu XML:  **\< /bodu >**</span><span class="sxs-lookup"><span data-stu-id="0641b-144">Example XML: **\</item>**</span></span><br /><br /> <span data-ttu-id="0641b-145">Další informace naleznete v tématu <xref:System.Xml.XmlNodeType>.</span><span class="sxs-lookup"><span data-stu-id="0641b-145">For more information, see <xref:System.Xml.XmlNodeType>.</span></span>|  
|<span data-ttu-id="0641b-146">EndEntity</span><span class="sxs-lookup"><span data-stu-id="0641b-146">EndEntity</span></span>|<span data-ttu-id="0641b-147">Vrácená při **XmlReader** získá na konec nahrazení entity v důsledku volání <xref:System.Xml.XmlReader.ResolveEntity%2A>.</span><span class="sxs-lookup"><span data-stu-id="0641b-147">Returned when **XmlReader** gets to the end of the entity replacement as a result of a call to <xref:System.Xml.XmlReader.ResolveEntity%2A>.</span></span> <span data-ttu-id="0641b-148">Další informace naleznete v tématu <xref:System.Xml.XmlNodeType>.</span><span class="sxs-lookup"><span data-stu-id="0641b-148">For more information, see <xref:System.Xml.XmlNodeType>.</span></span>|  
  
 <span data-ttu-id="0641b-149">Pokud chcete zobrazit příklad kódu, který čte v kódu XML a používá případu konstrukce na typy uzlů na tiskové informace o uzlu a její obsah, najdete v části <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>.</span><span class="sxs-lookup"><span data-stu-id="0641b-149">To view a code example that reads in XML and uses a case construct on the node types to print information about the node and its contents, see <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>.</span></span>  
  
 <span data-ttu-id="0641b-150">Další informace o hierarchie objektů typy uzlů a jejich název ekvivalentnímu objektu v tématu [hierarchii XML modelu DOM (Document Object)](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="0641b-150">For more information on the object hierarchy of the node types and their equivalent object name, see [XML Document Object Model (DOM) Hierarchy](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md).</span></span> <span data-ttu-id="0641b-151">Další informace o objekty vytvořené v uzlu stromu najdete v tématu [mapování hierarchie objektů na XML Data](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="0641b-151">For more information on the objects created in the node tree, see [Mapping the Object Hierarchy to XML Data](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0641b-152">Viz také</span><span class="sxs-lookup"><span data-stu-id="0641b-152">See Also</span></span>  
 [<span data-ttu-id="0641b-153">XML Document Object Model (DOM).</span><span class="sxs-lookup"><span data-stu-id="0641b-153">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)