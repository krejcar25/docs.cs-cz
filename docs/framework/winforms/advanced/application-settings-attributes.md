---
title: "Atributy nastavení aplikace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1879ac6704619092c4c0d9cd6fab0356ea07a13d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="application-settings-attributes"></a><span data-ttu-id="b6249-102">Atributy nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="b6249-102">Application Settings Attributes</span></span>
<span data-ttu-id="b6249-103">Architektura nastavení aplikace obsahuje mnoho atributů, které mohou být použity buď obálkovou třídu nastavení aplikace nebo jeho jednotlivé vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="b6249-103">The Application Settings architecture provides many attributes that can be applied either to the applications settings wrapper class or its individual properties.</span></span> <span data-ttu-id="b6249-104">Tyto atributy se zkontrolují v době běhu aplikace nastavení infrastruktury, často konkrétně poskytovatel nastavení, aby bylo možné přizpůsobit funguje stanovené potřebám vlastní obálky.</span><span class="sxs-lookup"><span data-stu-id="b6249-104">These attributes are examined at run time by the application settings infrastructure, often specifically the settings provider, in order to tailor its functioning to the stated needs of the custom wrapper.</span></span>  
  
 <span data-ttu-id="b6249-105">Následující tabulka obsahuje seznam atributy, které mohou být použity pro obálkovou třídu nastavení aplikace a tato třída jednotlivé vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="b6249-105">The following table lists the attributes that can be applied to the application settings wrapper class, this class's individual properties, or both.</span></span> <span data-ttu-id="b6249-106">Podle definice pouze atribut jeden obor –**UserScopedSettingAttribute** nebo **atribut ApplicationScopedSettingAttribute**– musí použít u každého nastavení vlastností.</span><span class="sxs-lookup"><span data-stu-id="b6249-106">By definition, only a single scope attribute—**UserScopedSettingAttribute** or **ApplicationScopedSettingAttribute**—must be applied to each and every settings property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6249-107">Vlastní nastavení poskytovatele, odvozené od <xref:System.Configuration.SettingsProvider> třídy, je potřeba jenom rozpoznat následující tři atributy: **atribut ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, a **DefaultSettingValueAttribute**.</span><span class="sxs-lookup"><span data-stu-id="b6249-107">A custom settings provider, derived from the <xref:System.Configuration.SettingsProvider> class, is only required to recognize the following three attributes: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, and **DefaultSettingValueAttribute**.</span></span>  
  
|<span data-ttu-id="b6249-108">Atribut</span><span class="sxs-lookup"><span data-stu-id="b6249-108">Attribute</span></span>|<span data-ttu-id="b6249-109">cíl</span><span class="sxs-lookup"><span data-stu-id="b6249-109">Target</span></span>|<span data-ttu-id="b6249-110">Popis</span><span class="sxs-lookup"><span data-stu-id="b6249-110">Description</span></span>|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|<span data-ttu-id="b6249-111">Obě</span><span class="sxs-lookup"><span data-stu-id="b6249-111">Both</span></span>|<span data-ttu-id="b6249-112">Určuje krátký název poskytovatele nastavení chcete použít pro trvalost.</span><span class="sxs-lookup"><span data-stu-id="b6249-112">Specifies the short name of the settings provider to use for persistence.</span></span><br /><br /> <span data-ttu-id="b6249-113">Pokud je tento atribut není zadaný, výchozí zprostředkovatel <xref:System.Configuration.LocalFileSettingsProvider>, předpokládá se.</span><span class="sxs-lookup"><span data-stu-id="b6249-113">If this attribute is not supplied, the default provider, <xref:System.Configuration.LocalFileSettingsProvider>, is assumed.</span></span>|  
|<xref:System.Configuration.UserScopedSettingAttribute>|<span data-ttu-id="b6249-114">Obě</span><span class="sxs-lookup"><span data-stu-id="b6249-114">Both</span></span>|<span data-ttu-id="b6249-115">Definuje vlastnost jako nastavení uživatelských aplikací.</span><span class="sxs-lookup"><span data-stu-id="b6249-115">Defines a property as a user-scoped application setting.</span></span>|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|<span data-ttu-id="b6249-116">Obě</span><span class="sxs-lookup"><span data-stu-id="b6249-116">Both</span></span>|<span data-ttu-id="b6249-117">Definuje vlastnost jako nastavení aplikace s rozsahem aplikace.</span><span class="sxs-lookup"><span data-stu-id="b6249-117">Defines a property as an application-scoped application setting.</span></span>|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|<span data-ttu-id="b6249-118">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="b6249-118">Property</span></span>|<span data-ttu-id="b6249-119">Určuje řetězec, který lze deserializovat zprostředkovatelem do pevně výchozí hodnoty pro tuto vlastnost.</span><span class="sxs-lookup"><span data-stu-id="b6249-119">Specifies a string that can be deserialized by the provider into the hard-coded default value for this property.</span></span><br /><br /> <span data-ttu-id="b6249-120"><xref:System.Configuration.LocalFileSettingsProvider> Nevyžaduje, aby tento atribut a přepíše libovolná hodnota zadaná tímto atributem Pokud je hodnota nenastavili jako trvalé.</span><span class="sxs-lookup"><span data-stu-id="b6249-120">The <xref:System.Configuration.LocalFileSettingsProvider> does not require this attribute, and will override any value provided by this attribute if there is a value already persisted.</span></span>|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|<span data-ttu-id="b6249-121">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="b6249-121">Property</span></span>|<span data-ttu-id="b6249-122">Poskytuje popisný test pro individuální nastavení, používá primárně nástroje pro spuštění a návrhu.</span><span class="sxs-lookup"><span data-stu-id="b6249-122">Provides the descriptive test for an individual setting, used primarily by run-time and design-time tools.</span></span>|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|<span data-ttu-id="b6249-123">Třída</span><span class="sxs-lookup"><span data-stu-id="b6249-123">Class</span></span>|<span data-ttu-id="b6249-124">Poskytuje explicitní název pro skupinu nastavení.</span><span class="sxs-lookup"><span data-stu-id="b6249-124">Provides an explicit name for a settings group.</span></span> <span data-ttu-id="b6249-125">Pokud tento atribut nebyl nalezen, <xref:System.Configuration.ApplicationSettingsBase> používá název třídy obálku.</span><span class="sxs-lookup"><span data-stu-id="b6249-125">If this attribute is missing, <xref:System.Configuration.ApplicationSettingsBase> uses the wrapper class name.</span></span>|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|<span data-ttu-id="b6249-126">Třída</span><span class="sxs-lookup"><span data-stu-id="b6249-126">Class</span></span>|<span data-ttu-id="b6249-127">Poskytuje popisný testu pro skupinu nastavení, používá primárně nástroje pro spuštění a návrhu.</span><span class="sxs-lookup"><span data-stu-id="b6249-127">Provides the descriptive test for a settings group, used primarily by run-time and design-time tools.</span></span>|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|<span data-ttu-id="b6249-128">Obě</span><span class="sxs-lookup"><span data-stu-id="b6249-128">Both</span></span>|<span data-ttu-id="b6249-129">Určuje nula nebo více možností správy služeb, které by měly být zadané nastavení skupina nebo vlastnost.</span><span class="sxs-lookup"><span data-stu-id="b6249-129">Specifies zero or more manageability services that should be provided to the settings group or property.</span></span> <span data-ttu-id="b6249-130">Jsou k dispozici služby popsaného <xref:System.Configuration.SettingsManageability> výčtu.</span><span class="sxs-lookup"><span data-stu-id="b6249-130">The available services are described by the <xref:System.Configuration.SettingsManageability> enumeration.</span></span>|  
|<xref:System.Configuration.SpecialSettingAttribute>|<span data-ttu-id="b6249-131">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="b6249-131">Property</span></span>|<span data-ttu-id="b6249-132">Označuje, že nastavení patří do speciální předdefinované kategorie, jako je například připojovací řetězec, která navrhuje speciální zpracování zprostředkovatelem nastavení.</span><span class="sxs-lookup"><span data-stu-id="b6249-132">Indicates that a setting belongs to a special, predefined category, such as a connection string, that suggests special processing by the settings provider.</span></span> <span data-ttu-id="b6249-133">Jsou definovány předdefinovaných kategorií pro tento atribut <xref:System.Configuration.SpecialSetting> výčtu.</span><span class="sxs-lookup"><span data-stu-id="b6249-133">The predefined categories for this attribute are defined by the <xref:System.Configuration.SpecialSetting> enumeration.</span></span>|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|<span data-ttu-id="b6249-134">Obě</span><span class="sxs-lookup"><span data-stu-id="b6249-134">Both</span></span>|<span data-ttu-id="b6249-135">Určuje upřednostňovaný serializace mechanismus pro nastavení skupina nebo vlastnost.</span><span class="sxs-lookup"><span data-stu-id="b6249-135">Specifies a preferred serialization mechanism for a settings group or property.</span></span> <span data-ttu-id="b6249-136">Mechanismy dostupné serializace jsou definovány <xref:System.Configuration.SettingsSerializeAs> výčtu.</span><span class="sxs-lookup"><span data-stu-id="b6249-136">The available serialization mechanisms are defined by the <xref:System.Configuration.SettingsSerializeAs> enumeration.</span></span>|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|<span data-ttu-id="b6249-137">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="b6249-137">Property</span></span>|<span data-ttu-id="b6249-138">Určuje, že nastavení poskytovatele měli vypnout všechny funkce upgradu aplikace pro vlastnost označena.</span><span class="sxs-lookup"><span data-stu-id="b6249-138">Specifies that a settings provider should disable all application upgrade functionality for the marked property.</span></span>|  
  
 <span data-ttu-id="b6249-139">*Třída* udává, že atribut lze použít pouze pro třídu obálky nastavení aplikace.</span><span class="sxs-lookup"><span data-stu-id="b6249-139">*Class* indicates that the attribute can be applied only to an application settings wrapper class.</span></span> <span data-ttu-id="b6249-140">*Vlastnost* označuje, že atribut může být použité jenom nastavení vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="b6249-140">*Property* indicates that the attribute can be applied only settings properties.</span></span> <span data-ttu-id="b6249-141">*Obě* udává, že atribut lze použít buď úrovni.</span><span class="sxs-lookup"><span data-stu-id="b6249-141">*Both* indicates that the attribute can be applied at either level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6249-142">Viz také</span><span class="sxs-lookup"><span data-stu-id="b6249-142">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [<span data-ttu-id="b6249-143">Architektura nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="b6249-143">Application Settings Architecture</span></span>](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [<span data-ttu-id="b6249-144">Postupy: vytvoření nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="b6249-144">How to: Create Application Settings</span></span>](http://msdn.microsoft.com/en-us/53b3af80-1c02-4e35-99c6-787663148945)