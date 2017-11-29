---
title: "Odebrání atributů z uzlu elementu v modelu DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ede6f9e-a3ac-49a4-8488-ab8360a44aa4
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b4ca08d8080c2116ce05634a544c91780869b165
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="removing-attributes-from-an-element-node-in-the-dom"></a><span data-ttu-id="830c2-102">Odebrání atributů z uzlu elementu v modelu DOM</span><span class="sxs-lookup"><span data-stu-id="830c2-102">Removing Attributes from an Element Node in the DOM</span></span>
<span data-ttu-id="830c2-103">Existuje mnoho způsobů, jak odebrat atributy.</span><span class="sxs-lookup"><span data-stu-id="830c2-103">There are many ways to remove attributes.</span></span> <span data-ttu-id="830c2-104">Jednoho technika je odebrat z kolekce atributů.</span><span class="sxs-lookup"><span data-stu-id="830c2-104">One technique is to remove them from the attribute collection.</span></span> <span data-ttu-id="830c2-105">K tomu jsou prováděny následovně:</span><span class="sxs-lookup"><span data-stu-id="830c2-105">To do this, the following steps are performed:</span></span>  
  
1.  <span data-ttu-id="830c2-106">Získání kolekce atributů z elementu pomocí `XmlAttributeCollection attrs = elem.Attributes;`.</span><span class="sxs-lookup"><span data-stu-id="830c2-106">Get the attribute collection from the element using `XmlAttributeCollection attrs = elem.Attributes;`.</span></span>  
  
2.  <span data-ttu-id="830c2-107">Odeberte atribut z kolekce atributů pomocí jedné ze tří metod:</span><span class="sxs-lookup"><span data-stu-id="830c2-107">Remove the attribute from the attribute collection using one of three methods:</span></span>  
  
    -   <span data-ttu-id="830c2-108">Použití <xref:System.Xml.XmlAttributeCollection.Remove%2A> odebrat určitým atributem.</span><span class="sxs-lookup"><span data-stu-id="830c2-108">Use <xref:System.Xml.XmlAttributeCollection.Remove%2A> to remove a specific attribute.</span></span>  
  
    -   <span data-ttu-id="830c2-109">Použití <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> odebrat všechny atributy z kolekce a nechte žádné atributy elementu.</span><span class="sxs-lookup"><span data-stu-id="830c2-109">Use <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> to remove all attributes from the collection and leave the element with no attributes.</span></span>  
  
    -   <span data-ttu-id="830c2-110">Použití <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> pomocí jeho indexové číslo odstranit atribut z kolekce atributů.</span><span class="sxs-lookup"><span data-stu-id="830c2-110">Use <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> to remove an attribute from the attribute collection by using its index number.</span></span>  
  
 <span data-ttu-id="830c2-111">Následující metody odebrat z uzlu element atributy.</span><span class="sxs-lookup"><span data-stu-id="830c2-111">The following methods remove attributes from the element node.</span></span>  
  
-   <span data-ttu-id="830c2-112">Použití <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> odebrat kolekce atributů.</span><span class="sxs-lookup"><span data-stu-id="830c2-112">Use <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> to remove the attribute collection.</span></span>  
  
-   <span data-ttu-id="830c2-113">Použití <xref:System.Xml.XmlElement.RemoveAttribute%2A> odebrat jeden atribut podle názvu z kolekce.</span><span class="sxs-lookup"><span data-stu-id="830c2-113">Use <xref:System.Xml.XmlElement.RemoveAttribute%2A> to remove a single attribute by name from the collection.</span></span>  
  
-   <span data-ttu-id="830c2-114">Použití <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> možnost odebrání jeden atribut číslo indexu z kolekce.</span><span class="sxs-lookup"><span data-stu-id="830c2-114">Use <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> to remove a single attribute by index number from the collection.</span></span>  
  
 <span data-ttu-id="830c2-115">Jeden další možností je získat element, získat atribut z kolekce atributů a odebrat uzel atribut přímo.</span><span class="sxs-lookup"><span data-stu-id="830c2-115">One more alternative is to get the element, get the attribute from the attribute collection, and remove the attribute node directly.</span></span> <span data-ttu-id="830c2-116">Pokud chcete atribut z kolekce atributů, můžete použít název, `XmlAttribute attr = attrs["attr_name"];`, index `XmlAttribute attr = attrs[0];`, nebo plně kvalifikovaný název s oborem názvů `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`.</span><span class="sxs-lookup"><span data-stu-id="830c2-116">To get the attribute from the attribute collection, you can use a name, `XmlAttribute attr = attrs["attr_name"];`, an index `XmlAttribute attr = attrs[0];`, or by fully qualifying the name with the namespace `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`.</span></span>  
  
 <span data-ttu-id="830c2-117">Bez ohledu na to, v případě metody slouží k odebírání atributy jsou speciální omezení odebrání atributů, které jsou definovány jako výchozí atributy v definici typu dokumentu (DTD).</span><span class="sxs-lookup"><span data-stu-id="830c2-117">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the document type definition (DTD).</span></span> <span data-ttu-id="830c2-118">Výchozí atributy nelze odebrat, pokud je odebrán element, ke které patří.</span><span class="sxs-lookup"><span data-stu-id="830c2-118">Default attributes cannot be removed unless the element they belong to is removed.</span></span> <span data-ttu-id="830c2-119">Výchozí atributy jsou vždy k dispozici pro prvky, které mají výchozí atributy deklarován.</span><span class="sxs-lookup"><span data-stu-id="830c2-119">Default attributes are always present for elements that have default attributes declared.</span></span> <span data-ttu-id="830c2-120">Odebrání výchozí atribut z <xref:System.Xml.XmlAttributeCollection> nebo z <xref:System.Xml.XmlElement> výsledky v atributu nahrazení vloženy do <xref:System.Xml.XmlAttributeCollection> elementu, inicializovat na výchozí hodnotu, která byla definována.</span><span class="sxs-lookup"><span data-stu-id="830c2-120">Removing a default attribute from an <xref:System.Xml.XmlAttributeCollection> or from the <xref:System.Xml.XmlElement> results in a replacement attribute inserted into the <xref:System.Xml.XmlAttributeCollection> of the element, initialized to the default value that was declared.</span></span> <span data-ttu-id="830c2-121">Pokud máte element definovaný jako `<book att1="1" att2="2" att3="3"></book>`, pak máte `book` deklarovaný element s tři výchozí atributy.</span><span class="sxs-lookup"><span data-stu-id="830c2-121">If you have an element defined as `<book att1="1" att2="2" att3="3"></book>`, then you have a `book` element with three default attributes declared.</span></span> <span data-ttu-id="830c2-122">Implementace XML modelu DOM (Document Object) zaručuje, že stejně dlouho jako to `book` element existuje, obsahuje tyto tři výchozí atributy `att1`, `att2`, a `att3`.</span><span class="sxs-lookup"><span data-stu-id="830c2-122">The XML Document Object Model (DOM) implementation guarantees that as long as this `book` element exists, it has these three default attributes of `att1`, `att2`, and `att3`.</span></span>  
  
 <span data-ttu-id="830c2-123">Při volání s <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> metoda nastaví na hodnotu atributu String.Empty, protože atribut nemůže existovat bez hodnoty.</span><span class="sxs-lookup"><span data-stu-id="830c2-123">When called with an <xref:System.Xml.XmlAttribute>, the <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> method sets the value of the attribute to String.Empty, as an attribute cannot exist without a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="830c2-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="830c2-124">See Also</span></span>  
 [<span data-ttu-id="830c2-125">XML Document Object Model (DOM).</span><span class="sxs-lookup"><span data-stu-id="830c2-125">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)