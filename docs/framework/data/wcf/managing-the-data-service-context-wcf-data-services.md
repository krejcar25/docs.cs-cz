---
title: "Správa služby kontextu dat (služby WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 15b19d09-7de7-4638-9556-6ef396cc45ec
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 12a0a0b93bfb944a3032cc171f97f411de5d2aab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="managing-the-data-service-context-wcf-data-services"></a><span data-ttu-id="53054-102">Správa služby kontextu dat (služby WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="53054-102">Managing the Data Service Context (WCF Data Services)</span></span>
<span data-ttu-id="53054-103"><xref:System.Data.Services.Client.DataServiceContext> Třída zapouzdří operace, které jsou podporovány službě zadaná data.</span><span class="sxs-lookup"><span data-stu-id="53054-103">The <xref:System.Data.Services.Client.DataServiceContext> class encapsulates operations that are supported against a specified data service.</span></span> <span data-ttu-id="53054-104">I když [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] jsou bezstavové služby, není kontextu.</span><span class="sxs-lookup"><span data-stu-id="53054-104">Although [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] services are stateless, the context is not.</span></span> <span data-ttu-id="53054-105">Proto můžete použít <xref:System.Data.Services.Client.DataServiceContext> třídy pro uchování stavu na straně klienta mezi interakce s službu data za účelem podpory funkcí, jako například Správa změn.</span><span class="sxs-lookup"><span data-stu-id="53054-105">Therefore, you can use the <xref:System.Data.Services.Client.DataServiceContext> class to maintain state on the client between interactions with the data service in order to support features such as change management.</span></span> <span data-ttu-id="53054-106">Tato třída také spravuje identit a sleduje změny.</span><span class="sxs-lookup"><span data-stu-id="53054-106">This class also manages identities and tracks changes.</span></span>  
  
## <a name="merge-options-and-identity-resolution"></a><span data-ttu-id="53054-107">Možnosti sloučení a řešení Identity</span><span class="sxs-lookup"><span data-stu-id="53054-107">Merge Options and Identity Resolution</span></span>  
 <span data-ttu-id="53054-108">Když <xref:System.Data.Services.Client.DataServiceQuery%601> je proveden, entity v odpovědi kanálu materializována do objektů.</span><span class="sxs-lookup"><span data-stu-id="53054-108">When a <xref:System.Data.Services.Client.DataServiceQuery%601> is executed, the entities in the response feed are materialized into objects.</span></span> <span data-ttu-id="53054-109">Další informace najdete v tématu [Materialization objekt](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53054-109">For more information, see [Object Materialization](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md).</span></span> <span data-ttu-id="53054-110">Způsob, ve kterém jsou položky ve zprávě odpovědi materializována do objektů se provádí v závislosti na řešení identity a závisí na možnosti sloučení, pod kterým byl proveden dotaz.</span><span class="sxs-lookup"><span data-stu-id="53054-110">The way in which entries in a response message are materialized into objects is performed based on identity resolution and depends on the merge option under which the query was executed.</span></span> <span data-ttu-id="53054-111">Když více dotazy nebo zatížení požadavky jsou spouštěny v oboru jedné <xref:System.Data.Services.Client.DataServiceContext>, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] klienta sleduje pouze jednu instanci objektu s konkrétní hodnotou klíče.</span><span class="sxs-lookup"><span data-stu-id="53054-111">When multiple queries or load requests are executed in the scope of a single <xref:System.Data.Services.Client.DataServiceContext>, the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client only tracks a single instance of an object that has a specific key value.</span></span> <span data-ttu-id="53054-112">Tento klíč, který se používá k provádění řešení identity, jednoznačně identifikuje entity.</span><span class="sxs-lookup"><span data-stu-id="53054-112">This key, which is used to perform identity resolution, uniquely identifies an entity.</span></span>  
  
 <span data-ttu-id="53054-113">Ve výchozím nastavení, klient pouze bude realizována položku v odpovědi informačního kanálu do objektu entity, které nejsou již sledován pomocí <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="53054-113">By default, the client only materializes an entry in the response feed into an object for entities that are not already being tracked by the <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="53054-114">To znamená, že se nepřepíšou změny objekty již v mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="53054-114">This means that changes to objects already in the cache are not overwritten.</span></span> <span data-ttu-id="53054-115">Toto chování je řízen zadáním <xref:System.Data.Services.Client.MergeOption> hodnotu pro dotazy a operace načtení.</span><span class="sxs-lookup"><span data-stu-id="53054-115">This behavior is controlled by specifying a <xref:System.Data.Services.Client.MergeOption> value for queries and load operations.</span></span> <span data-ttu-id="53054-116">Tato možnost je určený nastavením <xref:System.Data.Services.Client.DataServiceContext.MergeOption%2A> vlastnost <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="53054-116">This option is specified by setting the <xref:System.Data.Services.Client.DataServiceContext.MergeOption%2A> property on the <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="53054-117">Možnost sloučení výchozí hodnota je <xref:System.Data.Services.Client.MergeOption.AppendOnly>.</span><span class="sxs-lookup"><span data-stu-id="53054-117">The default merge option value is <xref:System.Data.Services.Client.MergeOption.AppendOnly>.</span></span> <span data-ttu-id="53054-118">To jenom bude realizována objekty pro entity, které nejsou již sledován, což znamená, že nejsou přepsat stávající objekty.</span><span class="sxs-lookup"><span data-stu-id="53054-118">This only materializes objects for entities that are not already being tracked, which means that existing objects are not overwritten.</span></span> <span data-ttu-id="53054-119">Jiný způsob, jak zabránit změny k objektům v klientovi nepřepsal aktualizace ze služby dat slouží k zadání <xref:System.Data.Services.Client.MergeOption.PreserveChanges>.</span><span class="sxs-lookup"><span data-stu-id="53054-119">Another way to prevent changes to objects on the client from being overwritten by updates from the data service is to specify <xref:System.Data.Services.Client.MergeOption.PreserveChanges>.</span></span> <span data-ttu-id="53054-120">Pokud zadáte <xref:System.Data.Services.Client.MergeOption.OverwriteChanges>, hodnoty objektů na straně klienta jsou nahrazovány nejnovější hodnoty z položek v informačním kanálu odpovědi i v případě, že už byly provedeny změny těchto objektů.</span><span class="sxs-lookup"><span data-stu-id="53054-120">When you specify <xref:System.Data.Services.Client.MergeOption.OverwriteChanges>, values of objects on the client are replaced by the latest values from the entries in the response feed, even if changes have already been made to these objects.</span></span> <span data-ttu-id="53054-121">Když <xref:System.Data.Services.Client.MergeOption.NoTracking> možnost sloučení se používá, <xref:System.Data.Services.Client.DataServiceContext> nelze odeslat změny provedené u objektů klienta ke službě data.</span><span class="sxs-lookup"><span data-stu-id="53054-121">When a <xref:System.Data.Services.Client.MergeOption.NoTracking> merge option is used, the <xref:System.Data.Services.Client.DataServiceContext> cannot send changes made on client objects to the data service.</span></span> <span data-ttu-id="53054-122">Pomocí této možnosti se změny vždy přepíší hodnotami z službu data.</span><span class="sxs-lookup"><span data-stu-id="53054-122">With this option, changes are always overwritten with values from the data service.</span></span>  
  
## <a name="managing-concurrency"></a><span data-ttu-id="53054-123">Správa souběžnosti</span><span class="sxs-lookup"><span data-stu-id="53054-123">Managing Concurrency</span></span>  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="53054-124">podporuje optimistickou metodu souběžného, který povoluje službu data ke zjištění konfliktu aktualizace.</span><span class="sxs-lookup"><span data-stu-id="53054-124"> supports optimistic concurrency that enables the data service to detect update conflicts.</span></span> <span data-ttu-id="53054-125">Zprostředkovatel dat služby lze nakonfigurovat tak, že služba data vyhledává změny entity pomocí token souběžnosti.</span><span class="sxs-lookup"><span data-stu-id="53054-125">The data service provider can be configured in such a way that the data service checks for changes to entities by using a concurrency token.</span></span> <span data-ttu-id="53054-126">Tento token obsahuje jednu nebo více vlastností typu entity, které se ověřují pomocí služby data k určení, zda došlo ke změně prostředku.</span><span class="sxs-lookup"><span data-stu-id="53054-126">This token includes one or more properties of an entity type that are validated by the data service to determine whether a resource has changed.</span></span> <span data-ttu-id="53054-127">Tokeny souběžnosti, které jsou součástí hlavičku eTag žádostí a odpovědí z službu data, jsou spravovaná pomocí [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] klienta.</span><span class="sxs-lookup"><span data-stu-id="53054-127">Concurrency tokens, which are included in the eTag header of requests to and responses from the data service, are managed for you by the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client.</span></span> <span data-ttu-id="53054-128">Další informace najdete v tématu [aktualizaci dat služby](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53054-128">For more information, see [Updating the Data Service](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="53054-129"><xref:System.Data.Services.Client.DataServiceContext> Sleduje změny provedené u objektů, které byly ručně nahlášeny pomocí <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>, <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>, a <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A>, nebo <xref:System.Data.Services.Client.DataServiceCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="53054-129">The <xref:System.Data.Services.Client.DataServiceContext> tracks changes made to objects that have been reported manually by using <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>, <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>, and <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A>, or by a <xref:System.Data.Services.Client.DataServiceCollection%601>.</span></span> <span data-ttu-id="53054-130">Když <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> metoda je volána, klient odešle změny zpět na službu data.</span><span class="sxs-lookup"><span data-stu-id="53054-130">When the <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> method is called, the client sends changes back to the data service.</span></span> <span data-ttu-id="53054-131"><xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>může selhat, pokud změny dat v klientovi v konfliktu s změny ve službě data.</span><span class="sxs-lookup"><span data-stu-id="53054-131"><xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> can fail when data changes in the client conflict with changes in the data service.</span></span> <span data-ttu-id="53054-132">V takovém případě musí dotaz pro daný prostředek entity znovu a přijímat data aktualizace.</span><span class="sxs-lookup"><span data-stu-id="53054-132">When this occurs, you must query for the entity resource again to receive the update data.</span></span> <span data-ttu-id="53054-133">Chcete-li přepsat změny ve službě data, spustit dotaz pomocí <xref:System.Data.Services.Client.MergeOption.PreserveChanges> merge – možnost.</span><span class="sxs-lookup"><span data-stu-id="53054-133">To overwrite changes in the data service, execute the query using the <xref:System.Data.Services.Client.MergeOption.PreserveChanges> merge option.</span></span> <span data-ttu-id="53054-134">Při volání <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> znovu, jsou změny zachovaná v klientovi trvalé ke službě data tak dlouho, dokud k prostředku ve službě dat nebyly již provedeny další změny.</span><span class="sxs-lookup"><span data-stu-id="53054-134">When you call <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> again, the changes preserved on the client are persisted to the data service, as long as other changes have not already been made to the resource in the data service.</span></span>  
  
## <a name="saving-changes"></a><span data-ttu-id="53054-135">Ukládají se změny</span><span class="sxs-lookup"><span data-stu-id="53054-135">Saving Changes</span></span>  
 <span data-ttu-id="53054-136">Změny jsou sledovány v <xref:System.Data.Services.Client.DataServiceContext> instance však nebyla odeslána na server okamžitě.</span><span class="sxs-lookup"><span data-stu-id="53054-136">Changes are tracked in the <xref:System.Data.Services.Client.DataServiceContext> instance but not sent to the server immediately.</span></span> <span data-ttu-id="53054-137">Po skončení požadované změny pro zadanou aktivitu, volat <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> odeslat všechny změny ve službě data.</span><span class="sxs-lookup"><span data-stu-id="53054-137">After you are finished with the required changes for a specified activity, call <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> to submit all the changes to the data service.</span></span> <span data-ttu-id="53054-138">A <xref:System.Data.Services.Client.DataServiceResponse> objektu se vrátí po <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> bylo dokončeno.</span><span class="sxs-lookup"><span data-stu-id="53054-138">A <xref:System.Data.Services.Client.DataServiceResponse> object is returned after the <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> operation is complete.</span></span> <span data-ttu-id="53054-139"><xref:System.Data.Services.Client.DataServiceResponse> Objekt zahrnuje posloupnost <xref:System.Data.Services.Client.OperationResponse> objektů, které se pak obsahují posloupnost <xref:System.Data.Services.Client.EntityDescriptor> nebo <xref:System.Data.Services.Client.LinkDescriptor> instancí, které představují změny trvalé, nebo k pokusu o.</span><span class="sxs-lookup"><span data-stu-id="53054-139">The <xref:System.Data.Services.Client.DataServiceResponse> object includes a sequence of <xref:System.Data.Services.Client.OperationResponse> objects that, in turn, contain a sequence of <xref:System.Data.Services.Client.EntityDescriptor> or <xref:System.Data.Services.Client.LinkDescriptor> instances that represent the changes persisted or attempted.</span></span> <span data-ttu-id="53054-140">Při vytvoření nebo úpravě ve službě data entity <xref:System.Data.Services.Client.EntityDescriptor> obsahuje odkaz na aktualizovanou entitu, včetně všechny hodnoty generované serverem vlastností, jako je například vygenerovaného `ProductID` hodnota v předchozím příkladu.</span><span class="sxs-lookup"><span data-stu-id="53054-140">When an entity is created or modified in the data service, the <xref:System.Data.Services.Client.EntityDescriptor> includes a reference to the updated entity, including any server-generated property values, such as the generated `ProductID` value in the previous example.</span></span> <span data-ttu-id="53054-141">Klientská knihovna automaticky aktualizuje [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] objekt, který chcete mít tyto nové hodnoty.</span><span class="sxs-lookup"><span data-stu-id="53054-141">The client library automatically updates the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] object to have these new values.</span></span>  
  
 <span data-ttu-id="53054-142">Pro úspěšné insert a operace aktualizace, vlastnost state <xref:System.Data.Services.Client.EntityDescriptor> nebo <xref:System.Data.Services.Client.LinkDescriptor> objekt přidružený k operaci je nastavena na <xref:System.Data.Services.Client.EntityStates.Unchanged> a nové hodnoty jsou sloučeny s použitím <xref:System.Data.Services.Client.MergeOption.OverwriteChanges>.</span><span class="sxs-lookup"><span data-stu-id="53054-142">For successful insert and update operations, the state property of the <xref:System.Data.Services.Client.EntityDescriptor> or <xref:System.Data.Services.Client.LinkDescriptor> object associated with the operation is set to <xref:System.Data.Services.Client.EntityStates.Unchanged> and the new values are merged by using <xref:System.Data.Services.Client.MergeOption.OverwriteChanges>.</span></span> <span data-ttu-id="53054-143">Když typu vložení, aktualizace nebo odstranění operace selže ve službě data, stav entity zůstává stejná jako byl před <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> byla volána a <xref:System.Data.Services.Client.OperationResponse.Error%2A> vlastnost <xref:System.Data.Services.Client.OperationResponse> je nastaven na <xref:System.Data.Services.Client.DataServiceRequestException> obsahující informace o došlo k chybě.</span><span class="sxs-lookup"><span data-stu-id="53054-143">When an insert, update, or delete operation fails in the data service, the entity state remains the same as it was before <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> was called, and the <xref:System.Data.Services.Client.OperationResponse.Error%2A> property of the <xref:System.Data.Services.Client.OperationResponse> is set to an <xref:System.Data.Services.Client.DataServiceRequestException> that contains information about the error.</span></span> <span data-ttu-id="53054-144">Další informace najdete v tématu [aktualizaci dat služby](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53054-144">For more information, see [Updating the Data Service](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).</span></span>  
  
### <a name="setting-the-http-method-for-updates"></a><span data-ttu-id="53054-145">Nastavení metoda HTTP pro aktualizace</span><span class="sxs-lookup"><span data-stu-id="53054-145">Setting the HTTP Method for Updates</span></span>  
 <span data-ttu-id="53054-146">Ve výchozím nastavení odešle klientské knihovny rozhraní .NET Framework aktualizace stávající entity jako požadavky SLOUČENÍ.</span><span class="sxs-lookup"><span data-stu-id="53054-146">By default, the .NET Framework client library sends updates to existing entities as MERGE requests.</span></span> <span data-ttu-id="53054-147">Požadavek SLOUČENÍ aktualizací vybraných vlastností entity; Klient ale vždycky obsahuje všechny vlastnosti v žádosti o SLOUČENÍ, i vlastnosti, které nebyly změněny.</span><span class="sxs-lookup"><span data-stu-id="53054-147">A MERGE request updates selected properties of the entity; however the client always includes all properties in the MERGE request, even properties that have not changed.</span></span> <span data-ttu-id="53054-148">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Protokol také podporuje odesílání žádosti PUT k aktualizaci entity.</span><span class="sxs-lookup"><span data-stu-id="53054-148">The [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol also supports sending PUT requests to update entities.</span></span> <span data-ttu-id="53054-149">V požadavku PUT se stávající entitu v podstatě nahradí novou instanci třídy entita se hodnoty vlastností z klienta.</span><span class="sxs-lookup"><span data-stu-id="53054-149">In a PUT request, an existing entity is essentially replaced with a new instance of the entity with property values from the client.</span></span> <span data-ttu-id="53054-150">Chcete-li použít požadavky PUT, nastavte <xref:System.Data.Services.Client.SaveChangesOptions.ReplaceOnUpdate> příznak na <xref:System.Data.Services.Client.SaveChangesOptions> výčtu při volání metody <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="53054-150">To use PUT requests, set the <xref:System.Data.Services.Client.SaveChangesOptions.ReplaceOnUpdate> flag on the <xref:System.Data.Services.Client.SaveChangesOptions> enumeration when calling <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53054-151">Požadavek PUT budou chovat jinak než požadavek SLOUČENÍ, pokud klient nebude vědět o všech vlastností entity.</span><span class="sxs-lookup"><span data-stu-id="53054-151">A PUT request will behave differently than a MERGE request when the client does not know about all properties of the entity.</span></span> <span data-ttu-id="53054-152">Tomu může dojít při projekci typ entity do nového typu na straně klienta.</span><span class="sxs-lookup"><span data-stu-id="53054-152">This might occur when projecting an entity type into a new type on the client.</span></span> <span data-ttu-id="53054-153">Může také nastat, pokud byly přidány nové vlastnosti do entity v datovém modelu služby a <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> vlastnost <xref:System.Data.Services.Client.DataServiceContext> je nastaven na `true` ignorovat takové chyby mapování klienta.</span><span class="sxs-lookup"><span data-stu-id="53054-153">It might also occur when new properties have been added to the entity in the service data model and the <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> property on the <xref:System.Data.Services.Client.DataServiceContext> is set to `true` to ignore such client mapping errors.</span></span> <span data-ttu-id="53054-154">V těchto případech požadavek PUT resetuje všechny vlastnosti, které jsou pro nástroj neznámé klienta na výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="53054-154">In these cases, a PUT request will reset any properties that are unknown to the client to their default values.</span></span>  
  
### <a name="post-tunneling"></a><span data-ttu-id="53054-155">Tunelové propojení POST</span><span class="sxs-lookup"><span data-stu-id="53054-155">POST Tunneling</span></span>  
 <span data-ttu-id="53054-156">Ve výchozím nastavení, odešle knihovny klienta vytvářet, číst, aktualizovat a odstranit žádosti o [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] pomocí odpovídající metody HTTP POST, GET, PUT/MERGE nebo opravy služeb a odstranění.</span><span class="sxs-lookup"><span data-stu-id="53054-156">By default, the client library sends create, read, update, and delete requests to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] service by using the corresponding HTTP methods of POST, GET, PUT/MERGE/PATCH, and DELETE.</span></span> <span data-ttu-id="53054-157">To podporuje základní principy z přenosu REST (Representational State).</span><span class="sxs-lookup"><span data-stu-id="53054-157">This upholds the basic principles of Representational State Transfer (REST).</span></span> <span data-ttu-id="53054-158">Ne každý implementaci serveru pro webové však podporuje úplnou sadu metod HTTP.</span><span class="sxs-lookup"><span data-stu-id="53054-158">However, not every Web server implementation supports the full set of HTTP methods.</span></span> <span data-ttu-id="53054-159">V některých případech může být omezené na právě GET a POST podporovaných metod.</span><span class="sxs-lookup"><span data-stu-id="53054-159">In some cases, the supported methods might be restricted to just GET and POST.</span></span> <span data-ttu-id="53054-160">To může dojít v případě zprostředkovatele, jako je brána firewall blokuje požadavky u některých metod.</span><span class="sxs-lookup"><span data-stu-id="53054-160">This can happen when an intermediary, like a firewall, blocks requests with certain methods.</span></span> <span data-ttu-id="53054-161">Protože jsou nejčastěji podporované metody GET a POST, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] předepisuje způsob, jak spouštět žádné nepodporované metody HTTP pomocí požadavek POST.</span><span class="sxs-lookup"><span data-stu-id="53054-161">Because the GET and POST methods are most often supported, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] prescribes a way to execute any unsupported HTTP methods by using a POST request.</span></span> <span data-ttu-id="53054-162">Označuje jako *tunelování metod* nebo *POST tunelování*, to umožňuje klientovi umožní odeslat požadavek POST s skutečné metody popsané v vlastní `X-HTTP-Method` záhlaví.</span><span class="sxs-lookup"><span data-stu-id="53054-162">Known as *method tunneling* or *POST tunneling*, this enables a client to send a POST request with the actual method specified in the custom `X-HTTP-Method` header.</span></span> <span data-ttu-id="53054-163">Chcete-li povolit pro požadavky POST vynucoval tunelové připojení, nastavte <xref:System.Data.Services.Client.DataServiceContext.UsePostTunneling%2A> vlastnost na <xref:System.Data.Services.Client.DataServiceContext> instance k `true`.</span><span class="sxs-lookup"><span data-stu-id="53054-163">To enable POST tunneling for requests, set the <xref:System.Data.Services.Client.DataServiceContext.UsePostTunneling%2A> property on the <xref:System.Data.Services.Client.DataServiceContext> instance to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53054-164">Viz také</span><span class="sxs-lookup"><span data-stu-id="53054-164">See Also</span></span>  
 [<span data-ttu-id="53054-165">Klientská knihovna pro WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="53054-165">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="53054-166">Aktualizaci datové služby</span><span class="sxs-lookup"><span data-stu-id="53054-166">Updating the Data Service</span></span>](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 [<span data-ttu-id="53054-167">Asynchronní operace</span><span class="sxs-lookup"><span data-stu-id="53054-167">Asynchronous Operations</span></span>](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 [<span data-ttu-id="53054-168">Dávkování operací</span><span class="sxs-lookup"><span data-stu-id="53054-168">Batching Operations</span></span>](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)