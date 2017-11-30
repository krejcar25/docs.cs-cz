---
title: "Připojení událostí"
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
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e551a09ef6dc778f5dfab9ba8cf263f803556f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="connection-events"></a><span data-ttu-id="ae9e5-102">Připojení událostí</span><span class="sxs-lookup"><span data-stu-id="ae9e5-102">Connection Events</span></span>
<span data-ttu-id="ae9e5-103">Všechny zprostředkovatele dat .NET Framework mají **připojení** objekty s dvě události, které můžete použít k načtení informační zprávy ze zdroje dat nebo k určení, zda stav **připojení** má změnit.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="ae9e5-104">Následující tabulka popisuje události z **připojení** objektu.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="ae9e5-105">Událost</span><span class="sxs-lookup"><span data-stu-id="ae9e5-105">Event</span></span>|<span data-ttu-id="ae9e5-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ae9e5-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae9e5-107">**InfoMessage**</span><span class="sxs-lookup"><span data-stu-id="ae9e5-107">**InfoMessage**</span></span>|<span data-ttu-id="ae9e5-108">Nastane, když je pouze informativní zpráva vrácená ze zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="ae9e5-109">Informační zprávy jsou zprávy ze zdroje dat, které za následek výjimku hlášeny.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="ae9e5-110">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="ae9e5-110">**StateChange**</span></span>|<span data-ttu-id="ae9e5-111">Nastane při stav **připojení** změny.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="ae9e5-112">Práce s InfoMessage událostí</span><span class="sxs-lookup"><span data-stu-id="ae9e5-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="ae9e5-113">Upozornění a informativní zprávy můžete načíst z zdroje dat systému SQL Server pomocí <xref:System.Data.SqlClient.SqlConnection.InfoMessage> události <xref:System.Data.SqlClient.SqlConnection> objektu.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="ae9e5-114">Chyby vrácené ze zdroje dat s úroveň závažnosti: 11 až 16 způsobit vyvolání výjimky.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="ae9e5-115">Ale <xref:System.Data.SqlClient.SqlConnection.InfoMessage> události lze použít k získání zprávy ze zdroje dat, které nejsou přidružené k chybě.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="ae9e5-116">V případě Microsoft SQL Server, se považuje za informační zpráva chyby se závažností 10 nebo méně a mohou být zachyceny pomocí <xref:System.Data.SqlClient.SqlConnection.InfoMessage> událostí.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="ae9e5-117">Další informace najdete v tématu "Úrovně závažnosti chyby zpráva" v SQL Server Books Online.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-117">For more information, see the "Error Message Severity Levels" topic in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="ae9e5-118"><xref:System.Data.SqlClient.SqlConnection.InfoMessage> Přijímá události <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> objekt obsahující v jeho **chyby** vlastnost, zprávy ze zdroje dat kolekce.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="ae9e5-119">Můžete zadat dotaz **chyba** objekty v této kolekci pro text chyby číslo a zprávy, jakož i zdroji této chyby.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="ae9e5-120">Zprostředkovatel dat .NET Framework pro SQL Server obsahuje také podrobnosti o databáze, uložené procedury a číslo řádku, který pochází zprávy.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ae9e5-121">Příklad</span><span class="sxs-lookup"><span data-stu-id="ae9e5-121">Example</span></span>  
 <span data-ttu-id="ae9e5-122">Následující příklad kódu ukazuje, jak přidat obslužné rutiny události pro <xref:System.Data.SqlClient.SqlConnection.InfoMessage> událostí.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=   
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,   
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="ae9e5-123">Zpracování chyb jako InfoMessages</span><span class="sxs-lookup"><span data-stu-id="ae9e5-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="ae9e5-124"><xref:System.Data.SqlClient.SqlConnection.InfoMessage> Událostí bude obvykle platit pouze pro informační a výstražných zpráv odesílaných ze serveru.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="ae9e5-125">Ale když skutečné dojde k chybě, provádění **ExecuteNonQuery** nebo **ExecuteReader** je metoda, která iniciovala operaci serveru zastavilo a je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="ae9e5-126">Pokud chcete pokračovat zpracování zbytek příkazy v příkazu bez ohledu na případné chyby vyprodukované serveru, nastavte <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> vlastnost <xref:System.Data.SqlClient.SqlConnection> k `true`.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="ae9e5-127">To způsobí, že připojení k fire <xref:System.Data.SqlClient.SqlConnection.InfoMessage> událost chyby místo vyvolání výjimky a přerušení zpracování.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="ae9e5-128">Klientská aplikace můžete zpracování této události a reagovat na chybové stavy.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae9e5-129">K chybě s úrovní závažnosti 17 nebo vyšší, která způsobí, že server zastavit zpracování příkazu musí být zpracován jako výjimku.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="ae9e5-130">V takovém případě je vyvolána výjimka, bez ohledu na to, jak se chyba zpracovává v <xref:System.Data.SqlClient.SqlConnection.InfoMessage> událostí.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="ae9e5-131">Práce s událost StateChange</span><span class="sxs-lookup"><span data-stu-id="ae9e5-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="ae9e5-132">**StateChange** dojde k události při stav **připojení** změny.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="ae9e5-133">**StateChange** přijímá události <xref:System.Data.StateChangeEventArgs> které umožňují zjistit změny ve stavu systému **připojení** pomocí **OriginalState** a **CurrentState** vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="ae9e5-134">**OriginalState** vlastnost je <xref:System.Data.ConnectionState> výčet, který označuje stav **připojení** před ho změnit.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="ae9e5-135">**CurrentState** je <xref:System.Data.ConnectionState> výčet, který označuje stav **připojení** po ho změnit.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="ae9e5-136">Následující příklad kódu používá **StateChange** událostí zapsat zprávu do konzole při stav **připojení** změny.</span><span class="sxs-lookup"><span data-stu-id="ae9e5-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,   
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae9e5-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="ae9e5-137">See Also</span></span>  
 [<span data-ttu-id="ae9e5-138">Připojení ke zdroji dat</span><span class="sxs-lookup"><span data-stu-id="ae9e5-138">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="ae9e5-139">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="ae9e5-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)