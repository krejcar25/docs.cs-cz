---
title: "Načítání binární Data"
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
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd524ed605f1fe125480bae0949745f4f045f03a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-binary-data"></a><span data-ttu-id="f15a8-102">Načítání binární Data</span><span class="sxs-lookup"><span data-stu-id="f15a8-102">Retrieving Binary Data</span></span>
<span data-ttu-id="f15a8-103">Ve výchozím nastavení **DataReader** načte příchozích dat jako řádek, jakmile celý řádek dat je k dispozici.</span><span class="sxs-lookup"><span data-stu-id="f15a8-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="f15a8-104">Binární rozsáhlé objekty (objekty BLOB) vyžadují odlišné zacházení, ale, protože obsahují GB dat, které nemůžou být obsažené ve jeden řádek.</span><span class="sxs-lookup"><span data-stu-id="f15a8-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="f15a8-105">**Command.ExecuteReader** metoda má přetížení, které bude trvat <xref:System.Data.CommandBehavior> argument změnit výchozí chování **DataReader –**.</span><span class="sxs-lookup"><span data-stu-id="f15a8-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="f15a8-106">Můžete předat <xref:System.Data.CommandBehavior.SequentialAccess> k **ExecuteReader** metoda změnit výchozí chování **DataReader** tak, aby místo načítání řádky dat, načte data sekvenčně. to znamená přijetí.</span><span class="sxs-lookup"><span data-stu-id="f15a8-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="f15a8-107">To je ideální pro načítání objektů BLOB nebo další velké datové struktury.</span><span class="sxs-lookup"><span data-stu-id="f15a8-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="f15a8-108">Všimněte si, že toto chování může záviset na zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="f15a8-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="f15a8-109">Například vrací objekt BLOB z aplikace Microsoft Access načte celý objekt BLOB se načtena do paměti, spíše než postupně přijetí.</span><span class="sxs-lookup"><span data-stu-id="f15a8-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="f15a8-110">Při nastavení **DataReader –** používat **SequentialAccess**, je důležité si uvědomit pořadí, ve kterém přístup vrátil pole.</span><span class="sxs-lookup"><span data-stu-id="f15a8-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="f15a8-111">Výchozí chování **DataReader –**, což způsobí načtení celý řádek, jakmile je k dispozici, vám umožní přistupovat k pole vrátila v libovolném pořadí, až na další řádek je pro čtení.</span><span class="sxs-lookup"><span data-stu-id="f15a8-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="f15a8-112">Při použití **SequentialAccess** však musí přístup pole vrácené **DataReader** v pořadí.</span><span class="sxs-lookup"><span data-stu-id="f15a8-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="f15a8-113">Například pokud dotaz vrátí tři sloupce, třetí by se objekt BLOB, musí vracet hodnoty polí první a druhý před přístup k datům objektu BLOB ve třetím poli.</span><span class="sxs-lookup"><span data-stu-id="f15a8-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="f15a8-114">Pokud máte přístup k poli třetí před první nebo druhé pole, hodnoty polí první a druhý již nejsou k dispozici.</span><span class="sxs-lookup"><span data-stu-id="f15a8-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="f15a8-115">Důvodem je, že **SequentialAccess** změnil **DataReader –** vrátit data v pořadí a dat není k dispozici po **DataReader** má čtení za ho.</span><span class="sxs-lookup"><span data-stu-id="f15a8-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="f15a8-116">Při přístupu k datům v poli objektů BLOB, použijte **GetBytes** nebo **GetChars** zadali přístupových objektů **DataReader –**, který vyplnit pole s daty.</span><span class="sxs-lookup"><span data-stu-id="f15a8-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="f15a8-117">Můžete také použít **GetString** znaková data; ale.</span><span class="sxs-lookup"><span data-stu-id="f15a8-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="f15a8-118">Pokud chcete ušetřit prostředky systému možná nebudete chtít načíst hodnotu celý objekt BLOB do jednoho řetězce proměnné.</span><span class="sxs-lookup"><span data-stu-id="f15a8-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="f15a8-119">Místo toho můžete zadat konkrétní vyrovnávací paměť o velikosti dat, který se má vrátit a výchozí umístění pro první bajt nebo znak, který má být čtení z vrácená data.</span><span class="sxs-lookup"><span data-stu-id="f15a8-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="f15a8-120">**GetBytes** a **GetChars** vrátí `long` hodnotu, která představuje počet bajtů nebo znaků vrátila.</span><span class="sxs-lookup"><span data-stu-id="f15a8-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="f15a8-121">Pokud předáte hodnotu null pole pro **GetBytes** nebo **GetChars**, dlouhou hodnotu vrátí, bude celkový počet bajtů nebo znaků v objektu BLOB.</span><span class="sxs-lookup"><span data-stu-id="f15a8-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="f15a8-122">Volitelně můžete zadat index v poli jako počáteční pozice pro data, který je čten.</span><span class="sxs-lookup"><span data-stu-id="f15a8-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f15a8-123">Příklad</span><span class="sxs-lookup"><span data-stu-id="f15a8-123">Example</span></span>  
 <span data-ttu-id="f15a8-124">Následující příklad vrací ID vydavatele a logo z **pubs** ukázkové databáze v systému Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f15a8-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="f15a8-125">ID vydavatele (`pub_id`) je znak, a je logo je obrázek, který je objekt BLOB.</span><span class="sxs-lookup"><span data-stu-id="f15a8-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="f15a8-126">Protože **logo** pole rastr, v příkladu vrací binární data pomocí **GetBytes**.</span><span class="sxs-lookup"><span data-stu-id="f15a8-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="f15a8-127">Všimněte si, že ID vydavatele je přístupné pro aktuální řádek dat před loga, protože pole musí mít přístup postupně.</span><span class="sxs-lookup"><span data-stu-id="f15a8-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream                   
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter                 
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100        
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte    
' The bytes returned from GetBytes.  
Dim retval As Long                     
' The starting position in the BLOB output.  
Dim startIndex As Long = 0             
  
' The publisher id to use in the file name.  
Dim pubID As String = ""              
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;                            
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;                          
  
// Size of the BLOB buffer.  
int bufferSize = 100;                     
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];    
// The bytes returned from GetBytes.  
long retval;                              
// The starting position in the BLOB output.  
long startIndex = 0;                      
  
// The publisher id to use in the file name.  
string pubID = "";                       
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);    
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="f15a8-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="f15a8-128">See Also</span></span>  
 [<span data-ttu-id="f15a8-129">Práce s DataReaders</span><span class="sxs-lookup"><span data-stu-id="f15a8-129">Working with DataReaders</span></span>](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="f15a8-130">Binární a velké hodnoty dat systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="f15a8-130">SQL Server Binary and Large-Value Data</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="f15a8-131">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="f15a8-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)