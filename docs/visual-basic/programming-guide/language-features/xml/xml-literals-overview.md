---
title: "Přehled literálů XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59ce79995025692428263120f9c21c7baf5cf231
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="xml-literals-overview-visual-basic"></a>Přehled literálů XML (Visual Basic)
*Literál XML* umožňuje začlenit XML přímo do vaší [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kódu. Představuje literálu syntaxe XML [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objekty a je podobná syntaxe XML 1.0. Díky tomu je snazší vytvářet XML elementů a dokumentů prostřednictvím kódu programu, protože kódu má stejné struktuře jako poslední XML.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]zkompiluje literálů XML do [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objekty. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]poskytuje jednoduché objektový model pro vytváření a manipulace s nimi XML a tento model se integruje s [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Další informace naleznete v tématu <xref:System.Xml.Linq.XElement>.  
  
 Můžete vložit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] výrazu v literál XML. V době běhu, vytváří vaše aplikace [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objekt pro každý literál zařadit hodnoty vložené výrazy. To vám umožní určit dynamický obsah uvnitř literál XML. Další informace najdete v tématu [vložené výrazy v XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Další informace o rozdílech mezi literálu syntaxe jazyka XML a syntaxe XML 1.0 najdete v tématu [literály XML a specifikace XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Jednoduché literály  
 Můžete vytvořit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objekt v vaší [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kód zadáním nebo vložením v platném formátu XML. Literál XML elementu vrátí <xref:System.Xml.Linq.XElement> objektu. Další informace najdete v tématu [literál XML elementu](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) a [literály XML a specifikace XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). Následující příklad vytvoří elementu XML, který má několik podřízených elementů.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Můžete vytvořit dokument XML spuštěním literál s XML `<?xml version="1.0"?>`, jak je znázorněno v následujícím příkladu. Literál dokumentu XML vrátí <xref:System.Xml.Linq.XDocument> objektu. Další informace najdete v tématu [literál dokumentu XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  Literál syntaxe XML [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] není totožný syntaxe specifikace XML 1.0. Další informace najdete v tématu [literály XML a specifikace XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Pokračování řádku  
 Literál XML může zahrnovat více řádků bez použití znaky pokračování řádku (místo podtržítka zadejte pořadí). To usnadňuje porovnat literálů XML v kódu s XML dokumenty.  
  
 Kompilátor zpracovává znaky pokračování řádku jako součást literál XML. Proto měli používat pořadí místo podtržítka zadejte pouze v případě, že patří v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objektu.  
  
 Pokud máte víceřádkových výrazů ve výrazu embedded, ale potřebovat znaky pokračování řádku. Další informace najdete v tématu [vložené výrazy v XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Vložení dotazy v literálech XML  
 Dotaz můžete použít ve výrazu embedded. Když to uděláte, prvky vrácených dotazem jsou přidány do elementu XML. Díky tomu můžete přidat dynamický obsah, jako je například výsledek dotazu uživatele do literál XML.  
  
 Například následující kód používá vložený dotaz k vytvoření elementů XML z členů `phoneNumbers2` pole a poté přidejte tyto elementy jako podřízené objekty `contact2`.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Jak kompilátor vytvoří objekty z XML – literály  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Kompilátoru překládá literálů XML do volání ekvivalent [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] konstruktory vybudovat [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objektu. Například [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kompilátoru přeloží následující příklad kódu do volání <xref:System.Xml.Linq.XProcessingInstruction> konstruktor pro verzi pokyn XML, volá, aby se <xref:System.Xml.Linq.XElement> konstruktor `<contact>`, `<name>`a `<phone>`elementy a volání <xref:System.Xml.Linq.XAttribute> konstruktor `type` atribut. Konkrétně zadané atributy v následující ukázce [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kompilátoru zavolá <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> konstruktor dvakrát. První předá hodnotu `type` pro `name` parametru a hodnota `home` pro `value` parametr. Druhý také předá hodnotu `type` pro `name` parametr, ale hodnota `work` pro `value` parametr.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Xml.Linq.XElement>  
 [Vytvoření XML v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Vložené výrazy v XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Literál dokumentu XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [Literál XML elementu](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML – literály](../../../../visual-basic/language-reference/xml-literals/index.md)
