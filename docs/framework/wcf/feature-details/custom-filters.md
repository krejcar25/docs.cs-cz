---
title: "Vlastní filtry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97cf247d-be0a-4057-bba9-3be5c45029d5
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: c9d0c81d715b2e876fe8144d4cff198f3321a22e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="custom-filters"></a><span data-ttu-id="50e22-102">Vlastní filtry</span><span class="sxs-lookup"><span data-stu-id="50e22-102">Custom Filters</span></span>
<span data-ttu-id="50e22-103">Vlastní filtry umožňují definovat odpovídající logiky, která nelze provést pomocí filtrů zpráv systému.</span><span class="sxs-lookup"><span data-stu-id="50e22-103">Custom filters allow you to define matching logic that cannot be accomplished using the system-provided message filters.</span></span> <span data-ttu-id="50e22-104">Například může vytvořit vlastní filtr, který vytvoří hodnotu hash elementu konkrétní zprávy a poté zkoumá hodnotu, která určí, zda filtr by měla vrátit hodnotu true nebo false.</span><span class="sxs-lookup"><span data-stu-id="50e22-104">For example, you might create a custom filter that hashes a particular message element and then examines the value to determine whether the filter should return true or false.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="50e22-105">Implementace</span><span class="sxs-lookup"><span data-stu-id="50e22-105">Implementation</span></span>  
 <span data-ttu-id="50e22-106">Vlastní filtr je implementací <xref:System.ServiceModel.Dispatcher.MessageFilter> abstraktní základní třída.</span><span class="sxs-lookup"><span data-stu-id="50e22-106">A custom filter is an implementation of the <xref:System.ServiceModel.Dispatcher.MessageFilter> abstract base class.</span></span> <span data-ttu-id="50e22-107">Při implementaci vlastního filtru, konstruktor může volitelně přijmout parametr jeden řetězec.</span><span class="sxs-lookup"><span data-stu-id="50e22-107">When implementing your custom filter, the constructor can optionally accept a single string parameter.</span></span> <span data-ttu-id="50e22-108">Tento parametr obsahuje informace o konfiguraci, která předaný konstruktoru MessageFilter Chcete-li poskytovat, že všechny hodnoty nebo konfigurace, která filtr musí za běhu, aby bylo možné provést odpovídá.</span><span class="sxs-lookup"><span data-stu-id="50e22-108">This parameter contains the configuration information that is passed to the MessageFilter constructor in order to provide any values or configuration that the filter needs at runtime in order to perform matches.</span></span> <span data-ttu-id="50e22-109">Například to lze použít pro zadejte hodnotu, která filtr vyhledává ve zprávě vyhodnocovaný.</span><span class="sxs-lookup"><span data-stu-id="50e22-109">For example, this might be used to provide a value that the filter looks for within the message being evaluated.</span></span> <span data-ttu-id="50e22-110">Následující příklad ukazuje základní implementace filtru vlastní zprávu, která přijímá řetězcový parametr:</span><span class="sxs-lookup"><span data-stu-id="50e22-110">The following example demonstrates a basic implementation of a custom message filter that accepts a string parameter:</span></span>  
  
```csharp  
public class MyMessageFilter: MessageFilter  
{  
    string filterData;  
    public MyMessageFilter(string filterData)  
    {  
        if(string.IsNullOrEmpty(filterData)  
            throw new ArgumentNullException("filterData");  
        this.filterData=filterData;  
    }  
    public override bool Match(System.ServiceModel.Channels.Message message)  
    {  
        ...  
        return retValue;  
    }  
    public override bool Match(System.ServiceModel.Channels.MessageBuffer buffer)  
    {  
        ...  
        return retValue;  
    }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="50e22-111">V implementaci skutečné metodu nebo metody shodu obsahuje logiku, která bude zkontrolujte zprávy k určení, pokud by měla vrátit tento filtr zpráv **true** nebo **false**.</span><span class="sxs-lookup"><span data-stu-id="50e22-111">In an actual implementation, the Match method(s) contains logic that will examine the message to determine if this message filter should return **true** or **false**.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="50e22-112">Výkon</span><span class="sxs-lookup"><span data-stu-id="50e22-112">Performance</span></span>  
 <span data-ttu-id="50e22-113">Při implementaci vlastního filtru, je potřeba vzít v úvahu maximální délku čas potřebný pro filtr k dokončení testování zprávu.</span><span class="sxs-lookup"><span data-stu-id="50e22-113">When implementing a custom filter, it is important to take into consideration the maximum length of time required for the filter to complete the evaluation of a message.</span></span> <span data-ttu-id="50e22-114">Vzhledem k tomu, že zpráva může být porovnán s více filtrů, než je nalezena shoda, je důležité zajistit, že nemá požadavku klienta není vypršení časového limitu před vyhodnocením všechny filtry.</span><span class="sxs-lookup"><span data-stu-id="50e22-114">Since a message may be evaluated against multiple filters before a match is found, it is important to ensure that the client request does not time out before all filters can be evaluated.</span></span> <span data-ttu-id="50e22-115">Vlastní filtr proto musí obsahovat pouze kód, nutné vyhodnotit obsah nebo atributy zprávy, aby bylo možné zjistit, jestli odpovídá kritéria filtru.</span><span class="sxs-lookup"><span data-stu-id="50e22-115">Therefore a custom filter should contain only the code necessary to evaluate the contents or attributes of a message in order to determine if it matches the filter criteria.</span></span>  
  
 <span data-ttu-id="50e22-116">Obecně platí neměli byste následující při implementaci vlastního filtru:</span><span class="sxs-lookup"><span data-stu-id="50e22-116">In general, you should avoid the following when implementing a custom filter:</span></span>  
  
-   <span data-ttu-id="50e22-117">Vstupně-výstupní operace, jako je například ukládání dat na disk nebo do databáze.</span><span class="sxs-lookup"><span data-stu-id="50e22-117">IO, such as saving data to disk or to a database.</span></span>  
  
-   <span data-ttu-id="50e22-118">Nepotřebné zpracování, např. opakování ve smyčce přes více záznamů v dokumentu.</span><span class="sxs-lookup"><span data-stu-id="50e22-118">Unnecessary processing, such as looping over multiple records in a document.</span></span>  
  
-   <span data-ttu-id="50e22-119">Blokování operace, například volání, které se týkají získání zámku na sdílených prostředků nebo provádění hledání proti databázi.</span><span class="sxs-lookup"><span data-stu-id="50e22-119">Blocking operations, such as calls that involve obtaining a lock on shared resources or performing lookups against a database.</span></span>  
  
 <span data-ttu-id="50e22-120">Před použitím vlastního filtru v provozním prostředí, byste měli spustit testy výkonu k určení průměrnou délku dobu, která filtr potřebná k vyhodnocení zprávu.</span><span class="sxs-lookup"><span data-stu-id="50e22-120">Before using a custom filter in a production environment, you should run performance tests to determine the average length of time that the filter takes to evaluate a message.</span></span> <span data-ttu-id="50e22-121">V kombinaci s průměrný čas zpracovávání ostatní filtry použité v tabulce filtru, to vám umožní přesně určit maximální časový limit hodnotu, která musí být zadán klientskou aplikací.</span><span class="sxs-lookup"><span data-stu-id="50e22-121">When combined with the average processing time of the other filters used in the filter table, this will allow you to accurately determine the maximum timeout value that should be specified by the client application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="50e22-122">Použití</span><span class="sxs-lookup"><span data-stu-id="50e22-122">Usage</span></span>  
 <span data-ttu-id="50e22-123">Pokud chcete používat vlastní filtr se službou směrování, je třeba přidat ji do tabulky filtru tak, že zadáte nový záznam filtru typu "Vlastní," název plně kvalifikovaný typ filtru zpráv a název vaší sestavení.</span><span class="sxs-lookup"><span data-stu-id="50e22-123">In order to use your custom filter with the Routing Service, you must add it to the filter table by specifying a new filter entry of type "Custom," the fully qualified type name of the message filter, and the name of your assembly.</span></span>  <span data-ttu-id="50e22-124">Stejně jako u jiných MessageFilters zadaný řetězec fulltextových dat filtru, která bude předána do konstruktoru vlastního filtru.</span><span class="sxs-lookup"><span data-stu-id="50e22-124">As with other MessageFilters, you can specify the string filterData that will be passed to your custom filter’s constructor.</span></span>  
  
 <span data-ttu-id="50e22-125">Následující příklady ukazují použití vlastního filtru se službou směrování:</span><span class="sxs-lookup"><span data-stu-id="50e22-125">The following examples demonstrate using a custom filter with the Routing Service:</span></span>  
  
```xml  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="CustomFilter1" filterType="Custom"   
            customType="CustomAssembly.MyMessageFilter,   
            CustomAssembly" filterData="custom data" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="CustomFilter1" endpointName="CalculatorService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
RoutingConfiguration rc = new RoutingConfiguration();  
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();  
endpointList.Add(client);  
rc.FilterTable.Add(new MyMessageFilter("CustomData"), endpointList);  
```