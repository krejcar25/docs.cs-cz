---
title: "Zabezpečení služeb a klientů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ed37992b5488d33b9292bdd54eef47f9eb12f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="9cd2a-102">Zabezpečení služeb a klientů</span><span class="sxs-lookup"><span data-stu-id="9cd2a-102">Securing Services and Clients</span></span>
<span data-ttu-id="9cd2a-103">Informace v této části se zaměřuje na programování zabezpečení v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cd2a-103">The information in this section focuses on programming security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="9cd2a-104">Obecně platí jedná se o výběr odpovídající vazby poskytované systémem, nastavení vlastností prvku zabezpečení a pak nastavení vlastnosti chování služby, které řídí, jak načíst přihlašovací údaje pro použití služby nebo klient.</span><span class="sxs-lookup"><span data-stu-id="9cd2a-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="9cd2a-105">Tyto postupy zahrnují požadavky na zabezpečení většiny uživatelů pro většinu scénářů, jak je znázorněno v [běžné scénáře zabezpečení](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="9cd2a-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="9cd2a-106">Pokud váš scénář vyžaduje další možnosti, nejprve v tématu [možnosti zabezpečení u vlastních vazeb](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); Pokud řešení není zřejmá, najdete v části [rozšíření zabezpečení](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="9cd2a-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="9cd2a-107">Pokud vytváříte (nebo spolupráce s) systému, který používá bohaté deklarace identity, najdete v tématech v [autorizace](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="9cd2a-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9cd2a-108">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="9cd2a-108">In This Section</span></span>  
 [<span data-ttu-id="9cd2a-109">Programování zabezpečení WCF</span><span class="sxs-lookup"><span data-stu-id="9cd2a-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="9cd2a-110">Přehled modelu programování sloužící k zabezpečení zprávy.</span><span class="sxs-lookup"><span data-stu-id="9cd2a-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="9cd2a-111">Přehled zabezpečení přenosu</span><span class="sxs-lookup"><span data-stu-id="9cd2a-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="9cd2a-112">Přehled o tom, jak zabezpečit zprávy prostřednictvím přenosové vrstvy.</span><span class="sxs-lookup"><span data-stu-id="9cd2a-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="9cd2a-113">Zabezpečení zpráv</span><span class="sxs-lookup"><span data-stu-id="9cd2a-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="9cd2a-114">Shrnuje důvody pomocí zabezpečení na úrovni zpráv v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cd2a-114">Summarizes reasons for using message-level security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
 [<span data-ttu-id="9cd2a-115">Zabezpečené relace</span><span class="sxs-lookup"><span data-stu-id="9cd2a-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="9cd2a-116">Se zabývat aspekty při zabezpečení vyžaduje [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relace.</span><span class="sxs-lookup"><span data-stu-id="9cd2a-116">A discussion of the considerations required when securing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] session.</span></span>  
  
 [<span data-ttu-id="9cd2a-117">Práce s certifikáty</span><span class="sxs-lookup"><span data-stu-id="9cd2a-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="9cd2a-118">Vysvětlení některé běžné úlohy, které vyžadují při použití certifikátů X.509.</span><span class="sxs-lookup"><span data-stu-id="9cd2a-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9cd2a-119">Odkaz</span><span class="sxs-lookup"><span data-stu-id="9cd2a-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="9cd2a-120">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="9cd2a-120">Related Sections</span></span>  
 [<span data-ttu-id="9cd2a-121">Koncepty zabezpečení</span><span class="sxs-lookup"><span data-stu-id="9cd2a-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="9cd2a-122">Rozšíření zabezpečení</span><span class="sxs-lookup"><span data-stu-id="9cd2a-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="9cd2a-123">Běžné scénáře zabezpečení</span><span class="sxs-lookup"><span data-stu-id="9cd2a-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="9cd2a-124">Vazby a zabezpečení</span><span class="sxs-lookup"><span data-stu-id="9cd2a-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="9cd2a-125">Možnosti zabezpečení u vlastních vazeb</span><span class="sxs-lookup"><span data-stu-id="9cd2a-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="9cd2a-126">Rozšíření zabezpečení</span><span class="sxs-lookup"><span data-stu-id="9cd2a-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="9cd2a-127">Autorizace</span><span class="sxs-lookup"><span data-stu-id="9cd2a-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="9cd2a-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="9cd2a-128">See Also</span></span>  
 [<span data-ttu-id="9cd2a-129">Základní programování WCF</span><span class="sxs-lookup"><span data-stu-id="9cd2a-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="9cd2a-130">Model zabezpečení pro Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="9cd2a-130">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)