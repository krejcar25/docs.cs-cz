---
title: "Postupy: Určení typu pověření klienta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 35c3b5ee429f7c9337fa3c3e3eb0d0476e3f56d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="681a9-102">Postupy: Určení typu pověření klienta</span><span class="sxs-lookup"><span data-stu-id="681a9-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="681a9-103">Po nastavení režimu zabezpečení (přenos nebo zpráv), máte možnost nastavení klienta typ přihlašovacích údajů.</span><span class="sxs-lookup"><span data-stu-id="681a9-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="681a9-104">Tato vlastnost určuje, jaký typ přihlašovacích údajů klient musí poskytnout službě pro ověření.</span><span class="sxs-lookup"><span data-stu-id="681a9-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="681a9-105">nastavení režimu zabezpečení rozhraní (nezbytným krokem před nastavením klienta typ přihlašovacích údajů), najdete v části [postupy: nastavení režimu zabezpečení](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="681a9-105"> setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="681a9-106">Chcete-li nastavit typ přihlašovacích údajů klienta v kódu</span><span class="sxs-lookup"><span data-stu-id="681a9-106">To set the client credential type in code</span></span>  
  
1.  <span data-ttu-id="681a9-107">Vytvoření instance vazby, který bude používán službou.</span><span class="sxs-lookup"><span data-stu-id="681a9-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="681a9-108">Tento příklad používá <xref:System.ServiceModel.WSHttpBinding> vazby.</span><span class="sxs-lookup"><span data-stu-id="681a9-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2.  <span data-ttu-id="681a9-109">Nastavte <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> vlastnost na odpovídající hodnotu.</span><span class="sxs-lookup"><span data-stu-id="681a9-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="681a9-110">Tento příklad používá režim zprávy.</span><span class="sxs-lookup"><span data-stu-id="681a9-110">This example uses the Message mode.</span></span>  
  
3.  <span data-ttu-id="681a9-111">Nastavte <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> vlastnost na odpovídající hodnotu.</span><span class="sxs-lookup"><span data-stu-id="681a9-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="681a9-112">Tento příklad nastaví ho na použití ověřování systému Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="681a9-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="681a9-113">Chcete-li nastavit typ přihlašovacích údajů klienta v konfiguraci</span><span class="sxs-lookup"><span data-stu-id="681a9-113">To set the client credential type in configuration</span></span>  
  
1.  <span data-ttu-id="681a9-114">Přidat [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element konfiguračního souboru.</span><span class="sxs-lookup"><span data-stu-id="681a9-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2.  <span data-ttu-id="681a9-115">Jako podřízený element přidat [ \<vazby >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span><span class="sxs-lookup"><span data-stu-id="681a9-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3.  <span data-ttu-id="681a9-116">Přidejte příslušné vazby.</span><span class="sxs-lookup"><span data-stu-id="681a9-116">Add an appropriate binding.</span></span> <span data-ttu-id="681a9-117">Tento příklad používá [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span><span class="sxs-lookup"><span data-stu-id="681a9-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4.  <span data-ttu-id="681a9-118">Přidat [ \<vazby >](../../../docs/framework/misc/binding.md) elementu a sadu `name` atribut na odpovídající hodnotu.</span><span class="sxs-lookup"><span data-stu-id="681a9-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="681a9-119">Tento příklad používá název "SecureBinding".</span><span class="sxs-lookup"><span data-stu-id="681a9-119">This example uses the name "SecureBinding".</span></span>  
  
5.  <span data-ttu-id="681a9-120">Přidat `<security>` vazby.</span><span class="sxs-lookup"><span data-stu-id="681a9-120">Add a `<security>` binding.</span></span> <span data-ttu-id="681a9-121">Nastavte `mode` atribut na odpovídající hodnotu.</span><span class="sxs-lookup"><span data-stu-id="681a9-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="681a9-122">Tento příklad ji nastaví na `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="681a9-122">This example sets it to `"Message"`.</span></span>  
  
6.  <span data-ttu-id="681a9-123">Přidat buď `<message>` nebo `<transport>` elementu, počítáno od režim zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="681a9-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="681a9-124">Nastavte `clientCredentialType` atribut na odpovídající hodnotu.</span><span class="sxs-lookup"><span data-stu-id="681a9-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="681a9-125">Tento příklad používá `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="681a9-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="681a9-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="681a9-126">See Also</span></span>  
 [<span data-ttu-id="681a9-127">Zabezpečení služeb</span><span class="sxs-lookup"><span data-stu-id="681a9-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="681a9-128">Postupy: nastavení režimu zabezpečení</span><span class="sxs-lookup"><span data-stu-id="681a9-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)