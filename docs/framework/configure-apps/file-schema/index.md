---
title: "Schéma konfiguračního souboru pro rozhraní .NET Framework"
ms.custom: 
ms.date: 05/01/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7f2dec0d71c1a0822bf39ae420d4e56bdaf99e0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="a3053-102">Schéma konfiguračního souboru pro rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a3053-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="a3053-103">Konfigurační soubory jsou standardní soubory XML, které můžete použít ke změně nastavení a nastavení zásad pro vaše aplikace.</span><span class="sxs-lookup"><span data-stu-id="a3053-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="a3053-104">Konfigurační schéma rozhraní .NET Framework se skládá z prvky používané v konfiguračních souborech můžete řídit chování aplikací.</span><span class="sxs-lookup"><span data-stu-id="a3053-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="a3053-105">Obsah pro tento oddíl odráží schéma hierarchie pro spouštění, modul runtime, sítě a další typy nastavení konfigurace.</span><span class="sxs-lookup"><span data-stu-id="a3053-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="a3053-106">Informace o typech, formát a umístění konfigurační soubory, najdete v článku [konfigurace aplikace](~/docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="a3053-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](~/docs/framework/configure-apps/index.md).</span></span> <span data-ttu-id="a3053-107">Pokud chcete upravit konfigurační soubory, které přímo, seznamte se se souborem XML.</span><span class="sxs-lookup"><span data-stu-id="a3053-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3053-108">Značky XML a atributů v konfiguračních souborech jsou malá a velká písmena.</span><span class="sxs-lookup"><span data-stu-id="a3053-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a3053-109">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="a3053-109">In this section</span></span>

<span data-ttu-id="a3053-110">[**\<Konfigurace >** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) popisuje `<configuration>` element, který je element nejvyšší úrovně pro všechny konfigurační soubory.</span><span class="sxs-lookup"><span data-stu-id="a3053-110">[**\<configuration>** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="a3053-111">[**\<assemblybinding – >** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) určuje sestavení vazby zásady na úrovni konfigurace.</span><span class="sxs-lookup"><span data-stu-id="a3053-111">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="a3053-112">[**\<linkedconfiguration – >** Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Určuje konfigurační soubor pro zahrnout.</span><span class="sxs-lookup"><span data-stu-id="a3053-112">[**\<linkedConfiguration>** Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="a3053-113">[Schéma nastavení spouštění](~/docs/framework/configure-apps/file-schema/startup/index.md) popisuje elementy, které určují, kterou verzi modulu CLR používat.</span><span class="sxs-lookup"><span data-stu-id="a3053-113">[Startup Settings Schema](~/docs/framework/configure-apps/file-schema/startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="a3053-114">[Schéma nastavení běhového prostředí](~/docs/framework/configure-apps/file-schema/runtime/index.md) popisuje elementy, které konfiguruje chování vazby a runtime sestavení.</span><span class="sxs-lookup"><span data-stu-id="a3053-114">[Runtime Settings Schema](~/docs/framework/configure-apps/file-schema/runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="a3053-115">[Schéma nastavení sítě](~/docs/framework/configure-apps/file-schema/network/index.md) popisuje elementy, které určují, jak rozhraní .NET Framework se připojuje k Internetu.</span><span class="sxs-lookup"><span data-stu-id="a3053-115">[Network Settings Schema](~/docs/framework/configure-apps/file-schema/network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="a3053-116">[Schéma nastavení šifrování](~/docs/framework/configure-apps/file-schema/cryptography/index.md) popisuje elementy, které mapování názvů popisný algoritmů na třídy, které implementují kryptografické algoritmy.</span><span class="sxs-lookup"><span data-stu-id="a3053-116">[Cryptography Settings Schema](~/docs/framework/configure-apps/file-schema/cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="a3053-117">[Schéma konfigurace oddílů](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) popisuje elementy slouží k vytvoření a použití konfiguračních oddílů pro vlastní nastavení.</span><span class="sxs-lookup"><span data-stu-id="a3053-117">[Configuration Sections Schema](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="a3053-118">[Trasování a ladění schématu nastavení](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) popisuje elementy, které určují trasování – přepínače a naslouchací procesy.</span><span class="sxs-lookup"><span data-stu-id="a3053-118">[Trace and Debug Settings Schema](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="a3053-119">[Schéma nastavení poskytovatele jazyka a kompilátor](~/docs/framework/configure-apps/file-schema/compiler/index.md) popisuje elementy, které určují kompilátoru konfigurace pro zprostředkovatele dostupný jazyk.</span><span class="sxs-lookup"><span data-stu-id="a3053-119">[Compiler and Language Provider Settings Schema](~/docs/framework/configure-apps/file-schema/compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="a3053-120">[Schéma nastavení aplikace](~/docs/framework/configure-apps/file-schema/application-settings-schema.md) popisuje elementy, které umožňují aplikacím Windows Forms nebo v technologii ASP.NET pro ukládání a načítání nastavení obor aplikace a nastavení uživatele.</span><span class="sxs-lookup"><span data-stu-id="a3053-120">[Application Settings Schema](~/docs/framework/configure-apps/file-schema/application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="a3053-121">[Schéma nastavení aplikace](~/docs/framework/configure-apps/file-schema/appsettings/index.md) obsahuje vlastní nastavení aplikace, například cesty k souborům, adresy URL XML webových služeb nebo všechny ostatní informace vlastní konfigurace pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="a3053-121">[App Settings Schema](~/docs/framework/configure-apps/file-schema/appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="a3053-122">[Webové nastavení schématu](~/docs/framework/configure-apps/file-schema/web/index.md) všechny elementy ve schéma nastavení webu, který obsahuje prvky pro konfiguraci, jak funguje technologie ASP.NET s hostitelskou aplikaci, například služby IIS.</span><span class="sxs-lookup"><span data-stu-id="a3053-122">[Web Settings Schema](~/docs/framework/configure-apps/file-schema/web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="a3053-123">Použít v *soubor Aspnet.config* soubory.</span><span class="sxs-lookup"><span data-stu-id="a3053-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="a3053-124">[Windows Forms konfigurační schéma](winforms/index.md) všechny elementy v konfiguračním oddílu aplikace Windows Forms, včetně přizpůsobení například více monitorování a vysokou podporu DPI.</span><span class="sxs-lookup"><span data-stu-id="a3053-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="a3053-125">[Konfigurační schéma služby WCF](~/docs/framework/configure-apps/file-schema/wcf/index.md) všechny elementy, které vám umožní nakonfigurovat aplikace klienta a služby WCF.</span><span class="sxs-lookup"><span data-stu-id="a3053-125">[WCF Configuration Schema](~/docs/framework/configure-apps/file-schema/wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="a3053-126">[Syntaxe – direktiva WCF](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md) popisuje `@ServiceHost` – direktiva, který definuje používané kompilátoru .svc atributy specifické pro stránku.</span><span class="sxs-lookup"><span data-stu-id="a3053-126">[WCF Directive Syntax](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="a3053-127">[Schéma konfigurace WIF](windows-identity-foundation/index.md) všechny elementy schématu konfigurace Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="a3053-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a3053-128">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="a3053-128">Related sections</span></span>

<span data-ttu-id="a3053-129">[Schéma nastavení vzdálené komunikace](http://msdn.microsoft.com/en-us/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) popisuje elementy, které nakonfigurovat klientské a serverové aplikace, které implementují vzdálenou komunikaci.</span><span class="sxs-lookup"><span data-stu-id="a3053-129">[Remoting Settings Schema](http://msdn.microsoft.com/en-us/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="a3053-130">[Schéma nastavení ASP.NET](http://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx) popisuje prvky, které řídí chování webových aplikací ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a3053-130">[ASP.NET Settings Schema](http://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="a3053-131">[Webové služby schéma nastavení](http://msdn.microsoft.com/en-us/f84d6d55-1add-4eb7-ae46-33df5833ea2e) popisuje elementy, které řídí chování webových služeb ASP.NET a svým klientům.</span><span class="sxs-lookup"><span data-stu-id="a3053-131">[Web Services Settings Schema](http://msdn.microsoft.com/en-us/f84d6d55-1add-4eb7-ae46-33df5833ea2e) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="a3053-132">[Konfigurace aplikací rozhraní .NET Framework](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42) popisuje postup konfigurace zabezpečení, sestavení – vazby a vzdálenou komunikaci v rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3053-132">[Configuring .NET Framework Apps](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>