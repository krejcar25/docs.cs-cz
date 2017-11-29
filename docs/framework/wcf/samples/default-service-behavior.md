---
title: "Výchozí chování služby"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, defaults
- Default Service Behavior Sample [Windows Communication Foundation]
ms.assetid: 442d4f71-c64e-4c62-816a-a66c38e7d3ec
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d584bbe3092524397639e5db8da6632deea8a752
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="default-service-behavior"></a><span data-ttu-id="66e66-102">Výchozí chování služby</span><span class="sxs-lookup"><span data-stu-id="66e66-102">Default Service Behavior</span></span>
<span data-ttu-id="66e66-103">Tento příklad znázorňuje, jak lze nakonfigurovat nastavení chování služby.</span><span class="sxs-lookup"><span data-stu-id="66e66-103">This sample demonstrates how service behavior settings can be configured.</span></span> <span data-ttu-id="66e66-104">Ukázka je založena na [Začínáme](../../../../docs/framework/wcf/samples/getting-started-sample.md), který implementuje `ICalculator` kontrakt služby.</span><span class="sxs-lookup"><span data-stu-id="66e66-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="66e66-105">Tato ukázka explicitně definuje chování služby a chování operace pomocí <xref:System.ServiceModel.ServiceBehaviorAttribute> a <xref:System.ServiceModel.OperationBehaviorAttribute> atributy.</span><span class="sxs-lookup"><span data-stu-id="66e66-105">This sample explicitly defines service behaviors and operation behaviors using the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes.</span></span> <span data-ttu-id="66e66-106">Chování můžete nakonfigurovat v konfiguračních souborech nebo imperativní v kódu (jako je tento příklad znázorňuje).</span><span class="sxs-lookup"><span data-stu-id="66e66-106">You can configure behaviors in configuration files or imperatively in code (as this sample demonstrates).</span></span>  
  
 <span data-ttu-id="66e66-107">V této ukázce klienta je konzolová aplikace (.exe) a služba je hostovaná Internetové informační služby (IIS).</span><span class="sxs-lookup"><span data-stu-id="66e66-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66e66-108">V postupu a sestavení pokynech k instalaci této ukázce jsou umístěné na konci tohoto tématu.</span><span class="sxs-lookup"><span data-stu-id="66e66-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="66e66-109">Třída služby určuje chování s <xref:System.ServiceModel.ServiceBehaviorAttribute> a <xref:System.ServiceModel.OperationBehaviorAttribute> jak znázorňuje následující ukázka kódu.</span><span class="sxs-lookup"><span data-stu-id="66e66-109">The service class specifies behaviors with the <xref:System.ServiceModel.ServiceBehaviorAttribute> and the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following code sample.</span></span> <span data-ttu-id="66e66-110">Všechny hodnoty zadané jsou výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="66e66-110">All values specified are the defaults.</span></span>  
  
```  
[ServiceBehavior(  
    AutomaticSessionShutdown=true,  
    ConcurrencyMode=ConcurrencyMode.Single,  
    InstanceContextMode=InstanceContextMode.PerSession,  
    IncludeExceptionDetailInFaults=false,  
    UseSynchronizationContext=true,  
    ValidateMustUnderstand=true)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(  
        TransactionAutoComplete=true,  
        TransactionScopeRequired=false,  
        Impersonation=ImpersonationOption.NotAllowed)]  
    public double Add(double n1, double n2)  
    {  
        System.Threading.Thread.Sleep(1600);  
        return n1 + n2;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="66e66-111">Chování služby se zadaným <xref:System.ServiceModel.ServiceBehaviorAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="66e66-111">Service behaviors are specified with the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span> <span data-ttu-id="66e66-112">Následující tabulka popisuje některé z těchto projevů.</span><span class="sxs-lookup"><span data-stu-id="66e66-112">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="66e66-113">Chování služby</span><span class="sxs-lookup"><span data-stu-id="66e66-113">Service behavior</span></span>|<span data-ttu-id="66e66-114">Popis</span><span class="sxs-lookup"><span data-stu-id="66e66-114">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.AutomaticSessionShutdown%2A>|<span data-ttu-id="66e66-115">Automaticky ukončí relace v požadavku klienta.</span><span class="sxs-lookup"><span data-stu-id="66e66-115">Automatically shuts down a session at the client's request.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>|<span data-ttu-id="66e66-116">Určuje režim souběžnosti pro každou instanci služby.</span><span class="sxs-lookup"><span data-stu-id="66e66-116">Specifies the concurrency mode for each service instance.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>|<span data-ttu-id="66e66-117">Určuje režim kontextu instance.</span><span class="sxs-lookup"><span data-stu-id="66e66-117">Specifies the instance context mode.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.UseSynchronizationContext%2A>|<span data-ttu-id="66e66-118">Určuje, zda se použít kontext zadaný synchronizace, je-li nastavena.</span><span class="sxs-lookup"><span data-stu-id="66e66-118">Determines whether to use the provided synchronization context, if one is set.</span></span> <span data-ttu-id="66e66-119">To použijte, pokud chcete řídit, jestli se má použít `WindowsFormsSynchronizationContext` v aplikacích Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="66e66-119">Use this when you want to control whether to use a `WindowsFormsSynchronizationContext` in Windows Forms applications.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A>|<span data-ttu-id="66e66-120">Určuje, zda mají být převedeny do jsou obecné provádění neošetřené výjimky `Fault<string>` a odeslán jako zprávu o chybě.</span><span class="sxs-lookup"><span data-stu-id="66e66-120">Determines whether general unhandled execution exceptions are to be converted into a `Fault<string>` and sent as a fault message.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>|<span data-ttu-id="66e66-121">Určuje úroveň izolace transakce.</span><span class="sxs-lookup"><span data-stu-id="66e66-121">Specifies the isolation level for transactions.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ValidateMustUnderstand%2A>|<span data-ttu-id="66e66-122">Určuje, zda záhlaví neočekávaná zpráva způsobit chybový stav.</span><span class="sxs-lookup"><span data-stu-id="66e66-122">Determines whether unexpected message headers cause an error condition.</span></span>|  
  
 <span data-ttu-id="66e66-123">Chování operace jsou určeny pomocí <xref:System.ServiceModel.OperationBehaviorAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="66e66-123">Operation behaviors are specified by using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="66e66-124">Následující tabulka popisuje některé z těchto projevů.</span><span class="sxs-lookup"><span data-stu-id="66e66-124">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="66e66-125">Operace chování</span><span class="sxs-lookup"><span data-stu-id="66e66-125">Operation Behavior</span></span>|<span data-ttu-id="66e66-126">Popis</span><span class="sxs-lookup"><span data-stu-id="66e66-126">Description</span></span>|  
|------------------------|-----------------|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>|<span data-ttu-id="66e66-127">Určuje, jestli dokončení operace služby potvrdí aktuální transakci.</span><span class="sxs-lookup"><span data-stu-id="66e66-127">Determines whether service operation completion commits the current transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>|<span data-ttu-id="66e66-128">Určuje, zda operace služby využívá v transakci plynoucích klienta.</span><span class="sxs-lookup"><span data-stu-id="66e66-128">Determines whether the service operation enlists in a client-flowed transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>|<span data-ttu-id="66e66-129">Určuje, zda operace služby zosobňuje identitu volajícího.</span><span class="sxs-lookup"><span data-stu-id="66e66-129">Determines whether the service operation impersonates the caller's identity.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A>|<span data-ttu-id="66e66-130">Určuje, zda instance služby recykluje na začátku nebo na konci volání operace služby.</span><span class="sxs-lookup"><span data-stu-id="66e66-130">Determines whether service instances are recycled at the start or end of the service operation call.</span></span>|  
  
 <span data-ttu-id="66e66-131">Když spustíte ukázku, operace požadavky a odpovědi se zobrazí v okně konzoly klienta.</span><span class="sxs-lookup"><span data-stu-id="66e66-131">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="66e66-132">Zpoždění mezi volání je výsledkem volání `System.Threading.Thread.Sleep()` provedené v operací služby.</span><span class="sxs-lookup"><span data-stu-id="66e66-132">The delay between the calls is the result of the calls to `System.Threading.Thread.Sleep()` made in the service operations.</span></span> <span data-ttu-id="66e66-133">Zbývající chování vzorků, které popisují tyto chování podrobněji.</span><span class="sxs-lookup"><span data-stu-id="66e66-133">The rest of the behavior samples explain these behaviors in more detail.</span></span> <span data-ttu-id="66e66-134">Stisknutím klávesy ENTER v okně klienta vypnout klienta.</span><span class="sxs-lookup"><span data-stu-id="66e66-134">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="66e66-135">Pokud chcete nastavit, sestavit a spustit ukázku</span><span class="sxs-lookup"><span data-stu-id="66e66-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="66e66-136">Ujistěte se, že jste provedli [jednorázové postup nastavení pro ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="66e66-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="66e66-137">Sestavení C# nebo Visual Basic .NET edice řešení, postupujte podle pokynů v [vytváření ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="66e66-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="66e66-138">Spustit ukázku v konfiguraci s jednou nebo mezi počítači, postupujte podle pokynů v [spuštění ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="66e66-138">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="66e66-139">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="66e66-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="66e66-140">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="66e66-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="66e66-141">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="66e66-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="66e66-142">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="66e66-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Default`  
  
## <a name="see-also"></a><span data-ttu-id="66e66-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="66e66-143">See Also</span></span>