---
title: "Načítání datové sady z XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db507bf4f90d875960408857c7e6b1e3aa145730
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="72b76-102">Načítání datové sady z XML</span><span class="sxs-lookup"><span data-stu-id="72b76-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="72b76-103">Obsah technologie ADO.NET <xref:System.Data.DataSet> lze vytvořit z datového proudu XML nebo dokumentu.</span><span class="sxs-lookup"><span data-stu-id="72b76-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="72b76-104">Kromě toho s rozhraním .NET Framework máte flexibilitu přes načtení informací ze souboru XML a jak schéma nebo relační struktura <xref:System.Data.DataSet> je vytvořena.</span><span class="sxs-lookup"><span data-stu-id="72b76-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="72b76-105">K vyplnění <xref:System.Data.DataSet> s daty ze souboru XML, použijte **ReadXml** metodu <xref:System.Data.DataSet> objektu.</span><span class="sxs-lookup"><span data-stu-id="72b76-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="72b76-106">**ReadXml** metoda čte z soubor datového proudu, nebo **XmlReader**a jako argumenty trvá zdroj XML plus volitelný **XmlReadMode** argument.</span><span class="sxs-lookup"><span data-stu-id="72b76-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="72b76-107">(Další informace o **XmlReader**, najdete v části [NIB: čtení dat XML s XmlTextReader](http://msdn.microsoft.com/en-us/762c069b-b50c-41b8-936e-39eacfb0d540).) **ReadXml** metoda načte obsah datový proud XML nebo dokumentu a zatížení <xref:System.Data.DataSet> s daty.</span><span class="sxs-lookup"><span data-stu-id="72b76-107">(For more information about the **XmlReader**, see [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/en-us/762c069b-b50c-41b8-936e-39eacfb0d540).) The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="72b76-108">Vytvoří také relační schéma <xref:System.Data.DataSet> v závislosti na tom **XmlReadMode** zadaný a jestli relační schéma už existuje.</span><span class="sxs-lookup"><span data-stu-id="72b76-108">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="72b76-109">Následující tabulka popisuje možnosti **XmlReadMode** argument.</span><span class="sxs-lookup"><span data-stu-id="72b76-109">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="72b76-110">Možnost</span><span class="sxs-lookup"><span data-stu-id="72b76-110">Option</span></span>|<span data-ttu-id="72b76-111">Popis</span><span class="sxs-lookup"><span data-stu-id="72b76-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="72b76-112">**Automaticky**</span><span class="sxs-lookup"><span data-stu-id="72b76-112">**Auto**</span></span>|<span data-ttu-id="72b76-113">Toto nastavení je výchozí.</span><span class="sxs-lookup"><span data-stu-id="72b76-113">This is the default.</span></span> <span data-ttu-id="72b76-114">Prozkoumá XML a vybere nejvíc příslušnou možnost v následujícím pořadí:</span><span class="sxs-lookup"><span data-stu-id="72b76-114">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="72b76-115">– Pokud XML je prvek formátu DiffGram **formát DiffGram** se používá.</span><span class="sxs-lookup"><span data-stu-id="72b76-115">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="72b76-116">-Pokud <xref:System.Data.DataSet> obsahuje schéma nebo XML obsahuje vložené schéma, **ReadSchema** se používá.</span><span class="sxs-lookup"><span data-stu-id="72b76-116">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="72b76-117">-Pokud <xref:System.Data.DataSet> neobsahuje schéma a soubor XML neobsahuje vložené schéma, **InferSchema** se používá.</span><span class="sxs-lookup"><span data-stu-id="72b76-117">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="72b76-118">Pokud znáte formát XML, který je čten, pro nejlepší výkon doporučujeme, abyste nastavili explicitního **XmlReadMode**, spíš než přijmout **automaticky** výchozí.</span><span class="sxs-lookup"><span data-stu-id="72b76-118">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="72b76-119">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="72b76-119">**ReadSchema**</span></span>|<span data-ttu-id="72b76-120">Načte všechny vložené schéma a načte dat a schématu.</span><span class="sxs-lookup"><span data-stu-id="72b76-120">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="72b76-121">Pokud <xref:System.Data.DataSet> již obsahuje schéma, přidat nové tabulky z vloženého schématu existující schéma v <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="72b76-121">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="72b76-122">Pokud žádné tabulky v vloženého schématu již existuje v <xref:System.Data.DataSet>, je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="72b76-122">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="72b76-123">Nebudete moct změnit schéma existující tabulky pomocí **XmlReadMode.ReadSchema**.</span><span class="sxs-lookup"><span data-stu-id="72b76-123">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="72b76-124">Pokud <xref:System.Data.DataSet> neobsahuje schématu a neexistuje žádný vložené schéma, nenačtou žádná data.</span><span class="sxs-lookup"><span data-stu-id="72b76-124">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="72b76-125">Vložené schéma lze definovat pomocí schématu XML definition language (XSD) schématu.</span><span class="sxs-lookup"><span data-stu-id="72b76-125">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="72b76-126">Podrobnosti o zápis vloženého schématu jako schématu XML najdete v tématu [odvozování relační strukturu datové sady z schématu XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="72b76-126">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="72b76-127">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="72b76-127">**IgnoreSchema**</span></span>|<span data-ttu-id="72b76-128">Ignoruje všechny vložené schéma a načte data do existující <xref:System.Data.DataSet> schématu.</span><span class="sxs-lookup"><span data-stu-id="72b76-128">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="72b76-129">Všechna data, která neodpovídá existující schéma se zahodí.</span><span class="sxs-lookup"><span data-stu-id="72b76-129">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="72b76-130">Pokud neexistuje žádné schéma v <xref:System.Data.DataSet>, je načtena žádná data.</span><span class="sxs-lookup"><span data-stu-id="72b76-130">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="72b76-131">Pokud jsou data formát DiffGram **IgnoreSchema** má stejné funkce jako **formát DiffGram** *.*</span><span class="sxs-lookup"><span data-stu-id="72b76-131">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="72b76-132">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="72b76-132">**InferSchema**</span></span>|<span data-ttu-id="72b76-133">Ignoruje všechny vložené schéma a odvodí, že schéma za strukturu dat XML a pak načte data.</span><span class="sxs-lookup"><span data-stu-id="72b76-133">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="72b76-134">Pokud <xref:System.Data.DataSet> již obsahuje schéma, je aktuální schéma rozšířeno přidáním sloupce do existující tabulky.</span><span class="sxs-lookup"><span data-stu-id="72b76-134">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="72b76-135">Navíc tabulky se nepřidají, pokud nejsou existující tabulky.</span><span class="sxs-lookup"><span data-stu-id="72b76-135">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="72b76-136">Pokud odvozené tabulky s jiný obor názvů již existuje, nebo pokud žádné odvozené sloupce v konfliktu s existující sloupce, je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="72b76-136">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="72b76-137">Podrobnosti o **ReadXmlSchema** odvodí schématu z dokumentu XML, najdete na stránce [odvození datovou sadu relační struktura z XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="72b76-137">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="72b76-138">**Formát DiffGram**</span><span class="sxs-lookup"><span data-stu-id="72b76-138">**DiffGram**</span></span>|<span data-ttu-id="72b76-139">Načte prvek formátu DiffGram a přidá data na aktuální schéma.</span><span class="sxs-lookup"><span data-stu-id="72b76-139">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="72b76-140">**Formát DiffGram** nové řádky s existující kde jedinečný identifikátor hodnoty shodují, řádky sloučí.</span><span class="sxs-lookup"><span data-stu-id="72b76-140">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="72b76-141">Najdete v části "Slučování dat z XML" na konci tohoto tématu.</span><span class="sxs-lookup"><span data-stu-id="72b76-141">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="72b76-142">Další informace o DiffGrams najdete v tématu [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="72b76-142">For more information about DiffGrams, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
|<span data-ttu-id="72b76-143">**Fragment**</span><span class="sxs-lookup"><span data-stu-id="72b76-143">**Fragment**</span></span>|<span data-ttu-id="72b76-144">Pokračuje, dokud nebude dosaženo konce datový proud čtení více fragmentů kódu XML.</span><span class="sxs-lookup"><span data-stu-id="72b76-144">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="72b76-145">Fragmenty, které odpovídají <xref:System.Data.DataSet> schématu se připojí k příslušné tabulky.</span><span class="sxs-lookup"><span data-stu-id="72b76-145">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="72b76-146">Fragmenty, které neodpovídají <xref:System.Data.DataSet> schématu se zahodí.</span><span class="sxs-lookup"><span data-stu-id="72b76-146">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="72b76-147">Pokud předáte **XmlReader** k **ReadXml** tedy umístěného součástí způsob dokument XML **ReadXml** na další uzel elementu, bude číst a který považovat kořenu Element čtení až do konce uzlu elementu.</span><span class="sxs-lookup"><span data-stu-id="72b76-147">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="72b76-148">To neplatí zadáte-li **XmlReadMode.Fragment**.</span><span class="sxs-lookup"><span data-stu-id="72b76-148">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="72b76-149">DTD entity</span><span class="sxs-lookup"><span data-stu-id="72b76-149">DTD Entities</span></span>  
 <span data-ttu-id="72b76-150">Pokud soubor XML obsahuje entity definovaná ve schématu definice (DTD) typu dokumentu, bude vyvolána výjimka, pokud se pokus o načtení <xref:System.Data.DataSet> předáním soubor název, datový proud nebo bez ověřování **XmlReader** k  **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="72b76-150">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="72b76-151">Místo toho je nutné vytvořit **třídy XmlValidatingReader**, s **EntityHandling příslušným** nastavena na **EntityHandling.ExpandEntities**a předejte vaší  **Třídy XmlValidatingReader** k **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="72b76-151">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="72b76-152">**Třídy XmlValidatingReader** bude rozšiřovat entity před čtením <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="72b76-152">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="72b76-153">Následující příklady kódu ukazují, jak načíst <xref:System.Data.DataSet> z datový proud XML.</span><span class="sxs-lookup"><span data-stu-id="72b76-153">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="72b76-154">V prvním příkladu zobrazuje název souboru je předán **ReadXml** metoda.</span><span class="sxs-lookup"><span data-stu-id="72b76-154">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="72b76-155">Druhý příklad ukazuje řetězec, který obsahuje XML vrácení načíst pomocí <xref:System.IO.StringReader>.</span><span class="sxs-lookup"><span data-stu-id="72b76-155">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
>  <span data-ttu-id="72b76-156">Když zavoláte **ReadXml** načíst velmi velký soubor, se můžete setkat nízký výkon.</span><span class="sxs-lookup"><span data-stu-id="72b76-156">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="72b76-157">K zajištění nejlepšího výkonu pro **ReadXml**, na velký soubor, volání <xref:System.Data.DataTable.BeginLoadData%2A> metoda pro každou tabulku v <xref:System.Data.DataSet>a pak zavolají **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="72b76-157">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="72b76-158">Nakonec volání <xref:System.Data.DataTable.EndLoadData%2A> pro každou tabulku v <xref:System.Data.DataSet>, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="72b76-158">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");   
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
>  <span data-ttu-id="72b76-159">Pokud schéma XSD pro vaše <xref:System.Data.DataSet> zahrnuje **cílový obor názvů**, nemusí být načtena data a výjimkami, může dojít, pokud volání **ReadXml** načíst <xref:System.Data.DataSet> se souborem XML, který obsahuje prvky s žádné opravňující oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="72b76-159">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="72b76-160">V takovém případě číst nekvalifikované prvky, nastavení **elementFormDefault** rovno "kvalifikovaný" v schéma XSD.</span><span class="sxs-lookup"><span data-stu-id="72b76-160">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="72b76-161">Příklad:</span><span class="sxs-lookup"><span data-stu-id="72b76-161">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="72b76-162">Slučování dat z XML</span><span class="sxs-lookup"><span data-stu-id="72b76-162">Merging Data from XML</span></span>  
 <span data-ttu-id="72b76-163">Pokud <xref:System.Data.DataSet> už obsahuje data, přidávání nových dat z XML s daty, která je již v <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="72b76-163">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="72b76-164">**ReadXml** nesloučí z XML do <xref:System.Data.DataSet> žádný řádek informace s odpovídajícími primárními klíči.</span><span class="sxs-lookup"><span data-stu-id="72b76-164">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="72b76-165">Pokud chcete přepsat existující řádek informace se novými informacemi ze souboru XML, použijte **ReadXml** pro vytvoření nového <xref:System.Data.DataSet>a potom <xref:System.Data.DataSet.Merge%2A> nové <xref:System.Data.DataSet> do existujících <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="72b76-165">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="72b76-166">Všimněte si, že načtení formát DiffGram pomocí **ReadXML** s **XmlReadMode** z **formát DiffGram** bude Sloučit řádky, které mají stejný jedinečný identifikátor.</span><span class="sxs-lookup"><span data-stu-id="72b76-166">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b76-167">Viz také</span><span class="sxs-lookup"><span data-stu-id="72b76-167">See Also</span></span>  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="72b76-168">Pomocí XML v datové sadě</span><span class="sxs-lookup"><span data-stu-id="72b76-168">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="72b76-169">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="72b76-169">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [<span data-ttu-id="72b76-170">Odvozování relační strukturu datové sady z schématu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="72b76-170">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="72b76-171">Odvození relační strukturu datové sady z XML</span><span class="sxs-lookup"><span data-stu-id="72b76-171">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="72b76-172">Načítání informací o schématu sady dat z XML</span><span class="sxs-lookup"><span data-stu-id="72b76-172">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="72b76-173">Datové sady, DataTables a DataView</span><span class="sxs-lookup"><span data-stu-id="72b76-173">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="72b76-174">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="72b76-174">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)