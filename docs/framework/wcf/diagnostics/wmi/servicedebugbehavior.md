---
title: ServiceDebugBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d6b866c90e3e6c6e72dc75f230bcf7b4e03a6bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="fcfe9-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="fcfe9-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="fcfe9-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="fcfe9-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcfe9-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fcfe9-104">Syntax</span></span>  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fcfe9-105">Metody</span><span class="sxs-lookup"><span data-stu-id="fcfe9-105">Methods</span></span>  
 <span data-ttu-id="fcfe9-106">Třída ServiceDebugBehavior nedefinuje žádné metody.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fcfe9-107">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="fcfe9-107">Properties</span></span>  
 <span data-ttu-id="fcfe9-108">Třída ServiceDebugBehavior má následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="fcfe9-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="fcfe9-109">httpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="fcfe9-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="fcfe9-110">Datový typ: logická hodnota</span><span class="sxs-lookup"><span data-stu-id="fcfe9-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="fcfe9-111">Přístup k typu: jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="fcfe9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcfe9-112">Určuje, zda služba zveřejňuje jeho WSDL na adrese řízené `HttpGetUrl` atribut.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="fcfe9-113">httpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="fcfe9-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="fcfe9-114">Datový typ: řetězec</span><span class="sxs-lookup"><span data-stu-id="fcfe9-114">Data type: string</span></span>  
  
 <span data-ttu-id="fcfe9-115">Přístup k typu: jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="fcfe9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcfe9-116">Nastaví umístění, kde je služba WSDL zveřejněna k získání pomocí protokolu HTTP.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="fcfe9-117">httpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="fcfe9-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="fcfe9-118">Datový typ: logická hodnota</span><span class="sxs-lookup"><span data-stu-id="fcfe9-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="fcfe9-119">Přístup k typu: jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="fcfe9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcfe9-120">Určuje, zda služba zveřejňuje jeho WSDL přes protokol HTTPS na adrese řízené `HttpsGetUrl` atribut.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="fcfe9-121">httpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="fcfe9-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="fcfe9-122">Datový typ: řetězec</span><span class="sxs-lookup"><span data-stu-id="fcfe9-122">Data type: string</span></span>  
  
 <span data-ttu-id="fcfe9-123">Přístup k typu: jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="fcfe9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcfe9-124">Nastaví umístění, kde je služba WSDL zveřejněna k získání pomocí protokolu HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="fcfe9-125">Třídu IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="fcfe9-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="fcfe9-126">Datový typ: logická hodnota</span><span class="sxs-lookup"><span data-stu-id="fcfe9-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="fcfe9-127">Přístup k typu: jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="fcfe9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcfe9-128">Určuje, zda mají být zahrnuty informace o spravovaných výjimce podrobností chyb SOAP vrácených klientům pro účely ladění.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcfe9-129">Požadavky</span><span class="sxs-lookup"><span data-stu-id="fcfe9-129">Requirements</span></span>  
  
|<span data-ttu-id="fcfe9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="fcfe9-130">MOF</span></span>|<span data-ttu-id="fcfe9-131">Deklarované v Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fcfe9-132">Obor názvů</span><span class="sxs-lookup"><span data-stu-id="fcfe9-132">Namespace</span></span>|<span data-ttu-id="fcfe9-133">Definované v root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fcfe9-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fcfe9-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="fcfe9-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>