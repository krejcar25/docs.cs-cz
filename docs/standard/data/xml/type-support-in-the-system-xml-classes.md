---
title: "Podpora typu v System.Xml třídy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 14821ef78f20d1ff303afacb42415e4017a92742
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="bb7d7-102">Podpora typu v System.Xml třídy</span><span class="sxs-lookup"><span data-stu-id="bb7d7-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="bb7d7-103">V rozhraní .NET Framework verze 2.0 mají základní třídy XML vylepšené a zahrnují typ podpory funkce.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="bb7d7-104"><xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, A <xref:System.Xml.XPath.XPathNavigator> třídy zahrnují typ podpory funkce, včetně možnosti pro převod mezi typy schémat XML a běžné typy language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bb7d7-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="bb7d7-105">V rozhraní .NET Framework verze 2.0 <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, a <xref:System.Xml.XPath.XPathNavigator> třídy vylepšené a zahrnují typ podpory funkce.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
-   <span data-ttu-id="bb7d7-106"><xref:System.Xml.XmlReader> a <xref:System.Xml.XPath.XPathNavigator> třídy každý zahrnují **SchemaInfo** vlastnost, která vrací informace o schématu na uzlu.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
-   <span data-ttu-id="bb7d7-107">**ReadContentAs** a **ReadElementContentAs** a metody na <xref:System.Xml.XmlReader> třídy číst textové hodnoty a převést na hodnotu CLR v rámci jednoho volání metody.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
-   <span data-ttu-id="bb7d7-108"><xref:System.Xml.XmlWriter.WriteValue%2A> Metodu <xref:System.Xml.XmlWriter> třída převede na typ CLR na typ schématu XML při zápisu se XML.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
-   <span data-ttu-id="bb7d7-109">**ValueAs** a <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> vlastnosti <xref:System.Xml.XPath.XPathNavigator> třídy vrátit hodnotu uzlu a převeďte ho na hodnotu CLR v rámci jednoho volání metody.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb7d7-110">V rozhraní .NET Framework verze 1.0 <xref:System.Xml.XmlConvert> třídy byly potřebné pro převod mezi typy schématu XML a CLR.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb7d7-111">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="bb7d7-111">In This Section</span></span>  
 [<span data-ttu-id="bb7d7-112">Mapování datové typy XML pro typy CLR</span><span class="sxs-lookup"><span data-stu-id="bb7d7-112">Mapping XML Data Types to CLR Types</span></span>](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="bb7d7-113">Popisuje výchozí mapování datových typů XML pro typy CLR.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="bb7d7-114">Poznámky k implementaci XML typu podpory</span><span class="sxs-lookup"><span data-stu-id="bb7d7-114">XML Type Support Implementation Notes</span></span>](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 <span data-ttu-id="bb7d7-115">Popisuje některé podrobnosti implementace podporu typu.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="bb7d7-116">Převod XML datových typů</span><span class="sxs-lookup"><span data-stu-id="bb7d7-116">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 <span data-ttu-id="bb7d7-117">Popisuje postup použití <xref:System.Xml.XmlConvert> třídy pro převod mezi typy schématu XML a CLR.</span><span class="sxs-lookup"><span data-stu-id="bb7d7-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bb7d7-118">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="bb7d7-118">Related Sections</span></span>  
 [<span data-ttu-id="bb7d7-119">Přístup k důrazně zadali pomocí objektem XPathNavigator nastaveným na Data XML</span><span class="sxs-lookup"><span data-stu-id="bb7d7-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)