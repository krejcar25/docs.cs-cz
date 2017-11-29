---
title: "Postupy: získání certifikátu (WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 468298c7a0ea673a90e0cde9d481333fad60e4a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="8247d-102">Postupy: získání certifikátu (WCF)</span><span class="sxs-lookup"><span data-stu-id="8247d-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="8247d-103">K používání některé z [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] funkce, které používají certifikáty X.509, je právě nejprve získat certifikáty.</span><span class="sxs-lookup"><span data-stu-id="8247d-103">To use any of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="8247d-104">K získání certifikátu X.509</span><span class="sxs-lookup"><span data-stu-id="8247d-104">To obtain an X.509 certificate</span></span>  
  
1.  <span data-ttu-id="8247d-105">Vyberte jednu z následujících možností:</span><span class="sxs-lookup"><span data-stu-id="8247d-105">Choose one of the following:</span></span>  
  
    -   <span data-ttu-id="8247d-106">Koupit certifikát od certifikační autority, jako je například VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="8247d-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    -   <span data-ttu-id="8247d-107">Nastavení certifikátu služby a mít podepsání certifikátů certifikační autority.</span><span class="sxs-lookup"><span data-stu-id="8247d-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]<span data-ttu-id="8247d-108">, Windows 2000 Server, Windows 2000 Server Datacenter a systém Windows 2000 Datacenter zahrnují certifikační služby, které podporují infrastruktury veřejných klíčů (PKI).</span><span class="sxs-lookup"><span data-stu-id="8247d-108">, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="8247d-109">V systému Windows Server 2008, použijte [Active Directory Certificate Services](http://go.microsoft.com/fwlink/?LinkID=153483) rolí ke správě certifikační autority.</span><span class="sxs-lookup"><span data-stu-id="8247d-109">In Windows Server 2008, use the [Active Directory Certificate Services](http://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    -   <span data-ttu-id="8247d-110">Nastavení certifikátu služby a provést není mít certifikáty podepsané.</span><span class="sxs-lookup"><span data-stu-id="8247d-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8247d-111">V obou případech můžete využít, příjemce žádosti SOAP, který obsahuje certifikát X.509 musí důvěřovat certifikátu X.509.</span><span class="sxs-lookup"><span data-stu-id="8247d-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="8247d-112">To znamená, že certifikát X.509 nebo vystavitele v řetězu certifikátů je v úložišti certifikátů důvěryhodných osob a zda není v úložišti nedůvěryhodné certifikáty certifikátu X.509.</span><span class="sxs-lookup"><span data-stu-id="8247d-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8247d-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="8247d-113">See Also</span></span>  
 [<span data-ttu-id="8247d-114">Práce s certifikáty</span><span class="sxs-lookup"><span data-stu-id="8247d-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="8247d-115">Postupy: vytváření dočasných certifikátů pro použití při vývoji</span><span class="sxs-lookup"><span data-stu-id="8247d-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)