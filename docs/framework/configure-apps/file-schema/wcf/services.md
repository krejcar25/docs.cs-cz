---
title: "&lt;služby&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eb292a62c2b042c387799164ff4cec88bd2ca482
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="0c4ed-102">&lt;služby&gt;</span><span class="sxs-lookup"><span data-stu-id="0c4ed-102">&lt;services&gt;</span></span>
<span data-ttu-id="0c4ed-103">Služby jsou definovány v `services` oddílu konfiguračního souboru.</span><span class="sxs-lookup"><span data-stu-id="0c4ed-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="0c4ed-104">Každá služba má svůj vlastní `service` konfigurační oddíl.</span><span class="sxs-lookup"><span data-stu-id="0c4ed-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="0c4ed-105">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0c4ed-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c4ed-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0c4ed-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c4ed-107">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="0c4ed-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0c4ed-108">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="0c4ed-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c4ed-109">Atributy</span><span class="sxs-lookup"><span data-stu-id="0c4ed-109">Attributes</span></span>  
 <span data-ttu-id="0c4ed-110">Žádné</span><span class="sxs-lookup"><span data-stu-id="0c4ed-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c4ed-111">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="0c4ed-111">Child Elements</span></span>  
  
|<span data-ttu-id="0c4ed-112">Prvek</span><span class="sxs-lookup"><span data-stu-id="0c4ed-112">Element</span></span>|<span data-ttu-id="0c4ed-113">Popis</span><span class="sxs-lookup"><span data-stu-id="0c4ed-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c4ed-114">\<služby ></span><span class="sxs-lookup"><span data-stu-id="0c4ed-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="0c4ed-115">Definujte kontrakt služby, chování a koncové body konkrétní služby.</span><span class="sxs-lookup"><span data-stu-id="0c4ed-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c4ed-116">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="0c4ed-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0c4ed-117">Prvek</span><span class="sxs-lookup"><span data-stu-id="0c4ed-117">Element</span></span>|<span data-ttu-id="0c4ed-118">Popis</span><span class="sxs-lookup"><span data-stu-id="0c4ed-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c4ed-119">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0c4ed-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="0c4ed-120">Kořenový element všechny konfigurační prvky Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0c4ed-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c4ed-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="0c4ed-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>