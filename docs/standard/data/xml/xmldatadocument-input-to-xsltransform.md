---
title: XmlDataDocument vstup XslTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 813c240ca0115015158988e1226d25890cde6939
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="xmldatadocument-input-to-xsltransform"></a><span data-ttu-id="9fad4-102">XmlDataDocument vstup XslTransform</span><span class="sxs-lookup"><span data-stu-id="9fad4-102">XmlDataDocument Input to XslTransform</span></span>
> [!NOTE]
>  <span data-ttu-id="9fad4-103"><xref:System.Xml.Xsl.XslTransform> Třída je zastaralá ve [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fad4-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="9fad4-104">Můžete provést jazyk XSL pro transformace transformace XSLT () pomocí <xref:System.Xml.Xsl.XslCompiledTransform> třídy.</span><span class="sxs-lookup"><span data-stu-id="9fad4-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="9fad4-105">V tématu [pomocí třídy XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) a [migrace z třídy XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) Další informace.</span><span class="sxs-lookup"><span data-stu-id="9fad4-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="9fad4-106">Microsoft [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] implementuje XML modelu DOM (Document Object) k poskytování přístupu k datům v XML – dokumenty a další třídy pro čtení, zápisu a přejděte do dokumentů XML.</span><span class="sxs-lookup"><span data-stu-id="9fad4-106">The Microsoft [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] implements the XML Document Object Model (DOM) to provide access to data in XML documents and additional classes to read, write, and navigate in XML documents.</span></span> <span data-ttu-id="9fad4-107"><xref:System.Xml.XmlDataDocument>, Který se nachází v <xref:System.Xml> obor názvů, poskytuje schopnost synchronizovat s relační data v relační přístup k datům <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9fad4-107">The <xref:System.Xml.XmlDataDocument>, found in the <xref:System.Xml> namespace, provides relational access to data with its ability to synchronize with the relational data in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9fad4-108">Najednou můžete zobrazit a pracovat s strukturovaných XML prostřednictvím relační reprezentace <xref:System.Data.DataSet> částečně strukturovaných XML pomocí modelu DOM reprezentace pro práci s nimi <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="9fad4-108">You can simultaneously view and manipulate structured XML through the relational representation of the <xref:System.Data.DataSet> or manipulate the semi-structured XML through the DOM representation of the <xref:System.Xml.XmlDataDocument>.</span></span> <span data-ttu-id="9fad4-109"><xref:System.Xml.XmlDataDocument> Proto hranice soubor XML a relační světů protíná.</span><span class="sxs-lookup"><span data-stu-id="9fad4-109">The <xref:System.Xml.XmlDataDocument> therefore crosses the boundaries of the XML and the relational worlds.</span></span>  
  
 <span data-ttu-id="9fad4-110">Pokud jsou data uložena v relační struktura a má být vstup k transformaci XSLT, můžete načíst relačních dat do <xref:System.Data.DataSet> a přidružte ji s <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="9fad4-110">If data is stored in a relational structure and you want it to be input to an XSLT transformation, you can load the relational data into a <xref:System.Data.DataSet> and associate it with the <xref:System.Xml.XmlDataDocument>.</span></span> <span data-ttu-id="9fad4-111"><xref:System.Xml.XPath.XPathNavigator>, Vstup <xref:System.Xml.Xsl.XslTransform>, se implementuje na <xref:System.Xml.XmlDataDocument> prostřednictvím <xref:System.Xml.XPath.IXPathNavigable> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="9fad4-111">The <xref:System.Xml.XPath.XPathNavigator>, the input to the <xref:System.Xml.Xsl.XslTransform>, is implemented on the <xref:System.Xml.XmlDataDocument> through the <xref:System.Xml.XPath.IXPathNavigable> interface.</span></span> <span data-ttu-id="9fad4-112">Provedením relačních dat načítání do aplikace <xref:System.Data.DataSet>a pomocí synchronizace v rámci <xref:System.Xml.XmlDataDocument>, relačních dat může mít nyní provádí transformace XSLT.</span><span class="sxs-lookup"><span data-stu-id="9fad4-112">By taking relational data, loading it into a <xref:System.Data.DataSet>, and using the synchronizing within the <xref:System.Xml.XmlDataDocument>, the relational data can now have XSLT transformations performed on it.</span></span>  
  
 <span data-ttu-id="9fad4-113">Další informace o použití transformace na relační data, najdete v části [použití transformaci XSLT na datovou sadu](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="9fad4-113">For more information on applying a transform to relational data, see [Applying an XSLT Transform to a DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fad4-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="9fad4-114">See Also</span></span>  
 <xref:System.Xml.XmlDataDocument>  
 [<span data-ttu-id="9fad4-115">Datové sady a XmlDataDocument synchronizace</span><span class="sxs-lookup"><span data-stu-id="9fad4-115">DataSet and XmlDataDocument Synchronization</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [<span data-ttu-id="9fad4-116">Transformace XSLT pomocí XslTransform – třída</span><span class="sxs-lookup"><span data-stu-id="9fad4-116">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="9fad4-117">Třída XslTransform implementuje procesoru XSLT</span><span class="sxs-lookup"><span data-stu-id="9fad4-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [<span data-ttu-id="9fad4-118">Objektem XPathNavigator nastaveným v transformace</span><span class="sxs-lookup"><span data-stu-id="9fad4-118">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [<span data-ttu-id="9fad4-119">XPathNodeIterator v transformace</span><span class="sxs-lookup"><span data-stu-id="9fad4-119">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [<span data-ttu-id="9fad4-120">Vstup XPathDocument XslTransform</span><span class="sxs-lookup"><span data-stu-id="9fad4-120">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [<span data-ttu-id="9fad4-121">Třídou XMLDocument nastavenou na vstup XslTransform</span><span class="sxs-lookup"><span data-stu-id="9fad4-121">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)