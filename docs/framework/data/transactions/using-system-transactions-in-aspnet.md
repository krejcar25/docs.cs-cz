---
title: "System.Transactions – pomocí technologie ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a27428211fad8c5c53f2799ee832baa6c644f36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="21fd9-102">System.Transactions – pomocí technologie ASP.NET</span><span class="sxs-lookup"><span data-stu-id="21fd9-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="21fd9-103">Toto téma popisuje, jak lze úspěšně pomocí <xref:System.Transactions> v rámci [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="21fd9-103">This topic describes how you can successfully use <xref:System.Transactions> inside an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="21fd9-104">Povolit DistributedTransactionPermission v technologii ASP.NET</span><span class="sxs-lookup"><span data-stu-id="21fd9-104">Enable DistributedTransactionPermission in ASP.NET</span></span>  
 <span data-ttu-id="21fd9-105"><xref:System.Transactions>podporuje částečně důvěryhodné volající a je označené **AllowPartiallyTrustedCallers** atribut (APTCA).</span><span class="sxs-lookup"><span data-stu-id="21fd9-105"><xref:System.Transactions> supports partially trusted callers and is marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="21fd9-106">Vztah důvěryhodnosti úrovní pro <xref:System.Transactions> jsou definovány v závislosti na typy prostředků (pro příklad, systémová paměť, sdílené prostředky celého procesu, systémové prostředky a další materiály), který <xref:System.Transactions> zpřístupňuje a úroveň vztahu důvěryhodnosti, který je třeba získat přístup k těmto prostředkům.</span><span class="sxs-lookup"><span data-stu-id="21fd9-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources, (for example, system memory, shared process-wide resources, system-wide resources, and other resources), that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="21fd9-107">V prostředí částečné důvěryhodnosti, můžete použít jiný plně důvěryhodné sestavení pouze transakce v rámci domény aplikace (v takovém případě jediný zdroj chráněn je systémová paměť), pokud má oprávnění <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="21fd9-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>  
  
 <span data-ttu-id="21fd9-108"><xref:System.Transactions.DistributedTransactionPermission>je požadováno vždy, když je Správa transakcí eskalován jej lze spravovat pomocí Microsoft distribuované transakce koordinátor MSDTC ().</span><span class="sxs-lookup"><span data-stu-id="21fd9-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="21fd9-109">Tento druh scénář využívá prostředky celého procesu a zejména globální zdroj, který je vyhrazené místo v protokolu MSDTC.</span><span class="sxs-lookup"><span data-stu-id="21fd9-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="21fd9-110">Příklad toto využití je do databáze nebo aplikace, která používá databázi v rámci služeb, které poskytuje klientské části webu.</span><span class="sxs-lookup"><span data-stu-id="21fd9-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="21fd9-111">obsahuje vlastní sadu úrovně důvěryhodnosti a přidruží konkrétní sadu oprávnění tyto úrovně důvěryhodnosti prostřednictvím soubory zásad.</span><span class="sxs-lookup"><span data-stu-id="21fd9-111"> has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="21fd9-112">[Úrovně důvěryhodnosti ASP.NET a soubory zásad](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span><span class="sxs-lookup"><span data-stu-id="21fd9-112"> [ASP.NET Trust Levels and Policy Files](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span></span> <span data-ttu-id="21fd9-113">Při počáteční instalaci sadu Windows SDK, žádná výchozí [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] soubory zásad jsou přidruženy <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="21fd9-113">When you initially install the Windows SDK, none of the default [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="21fd9-114">Jako takové, když vaši transakci v [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikace je eskalován jej lze spravovat pomocí příkaz MSDTC, eskalace nezdaří a zobrazí se <xref:System.Security.SecurityException> při náročných <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="21fd9-114">As such, when your transaction in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="21fd9-115">Chcete-li povolit eskalace transakce v [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] prostředí částečným vztahem důvěryhodnosti, byste měli udělit <xref:System.Transactions.DistributedTransactionPermission> ve stejné úrovně důvěryhodnosti výchozí jako <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="21fd9-115">To enable transaction escalation in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="21fd9-116">Buď můžete nakonfigurovat svůj vlastní soubor vlastní důvěryhodnosti úroveň a zásady pro podporu tohoto, nebo můžete upravit výchozí zásady soubory, které jsou **Web_hightrust.config** a **Web_mediumtrust.config**.</span><span class="sxs-lookup"><span data-stu-id="21fd9-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>  
  
 <span data-ttu-id="21fd9-117">Chcete-li upravit soubory zásad, přidejte **SecurityClass** element pro **DistributedTransactionPermission** k **SecurityClasses** prvek v rámci  **PolicyLevel, který** prvek a přidat odpovídající **IPermission** prvek v rámci [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** pro System.Transactions.</span><span class="sxs-lookup"><span data-stu-id="21fd9-117">To modify the policy files, add a **SecurityClass** element for **DistributedTransactionPermission** to the **SecurityClasses** element under the **PolicyLevel** element and add a corresponding **IPermission** element under the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** for System.Transactions.</span></span> <span data-ttu-id="21fd9-118">Následující konfigurační soubor ukazuje to.</span><span class="sxs-lookup"><span data-stu-id="21fd9-118">The following configuration file demonstrates this.</span></span>  
  
```xml  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="21fd9-119">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] zásady zabezpečení, najdete v části [securityPolicy – Element (schéma nastavení ASP.NET)](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba).</span><span class="sxs-lookup"><span data-stu-id="21fd9-119"> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] security policy, see [securityPolicy Element (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba).</span></span>  
  
## <a name="dynamic-compilation"></a><span data-ttu-id="21fd9-120">Dynamická kompilace</span><span class="sxs-lookup"><span data-stu-id="21fd9-120">Dynamic Compilation</span></span>  
 <span data-ttu-id="21fd9-121">Pokud chcete importovat a používat <xref:System.Transactions> v [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplikaci, která je dynamicky zkompilován přístupu, měli byste umístit odkaz <xref:System.Transactions> sestavení v konfiguračním souboru.</span><span class="sxs-lookup"><span data-stu-id="21fd9-121">If you want to import and use <xref:System.Transactions> in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="21fd9-122">Konkrétně by měl být odkaz na přidají pod **kompilace**/**sestavení** část kořenové výchozí **Web.config** konfigurační soubor, nebo konfigurační soubor konkrétní webové aplikace.</span><span class="sxs-lookup"><span data-stu-id="21fd9-122">Specifically, the reference should be added under the **compilation**/**assemblies** section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="21fd9-123">Následující příklad ukazuje to.</span><span class="sxs-lookup"><span data-stu-id="21fd9-123">The following example demonstrates this.</span></span>  
  
```xml  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="21fd9-124">[add – Element pro sestavení pro kompilaci (schéma nastavení ASP.NET)](http://msdn.microsoft.com/en-us/602197e8-108d-4249-b752-ba2a318f75e4).</span><span class="sxs-lookup"><span data-stu-id="21fd9-124"> [add Element for assemblies for compilation (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/602197e8-108d-4249-b752-ba2a318f75e4).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21fd9-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="21fd9-125">See Also</span></span>  
 [<span data-ttu-id="21fd9-126">Úrovně důvěryhodnosti ASP.NET a soubory zásad</span><span class="sxs-lookup"><span data-stu-id="21fd9-126">ASP.NET Trust Levels and Policy Files</span></span>](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [<span data-ttu-id="21fd9-127">securityPolicy – Element (schéma nastavení ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="21fd9-127">securityPolicy Element (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba)  
 [<span data-ttu-id="21fd9-128">Transakce správy eskalaci</span><span class="sxs-lookup"><span data-stu-id="21fd9-128">Transaction Management Escalation</span></span>](../../../../docs/framework/data/transactions/transaction-management-escalation.md)