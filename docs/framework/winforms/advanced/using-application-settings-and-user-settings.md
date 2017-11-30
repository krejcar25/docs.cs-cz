---
title: "Použití nastavení aplikace a uživatelských nastavení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f9544b6af74608bd1b29db3250e887999ae3187f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="b585b-102">Použití nastavení aplikace a uživatelských nastavení</span><span class="sxs-lookup"><span data-stu-id="b585b-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="b585b-103">Od verze rozhraní .NET Framework 2.0, můžete vytvořit a přístup k hodnoty, které jsou nastavené jako trvalé mezi relacemi spuštění aplikace.</span><span class="sxs-lookup"><span data-stu-id="b585b-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="b585b-104">Tyto hodnoty se nazývají *nastavení*.</span><span class="sxs-lookup"><span data-stu-id="b585b-104">These values are called *settings*.</span></span> <span data-ttu-id="b585b-105">Nastavení může představovat uživatelské předvolby nebo cenné informace aplikaci potřebuje používat.</span><span class="sxs-lookup"><span data-stu-id="b585b-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="b585b-106">Například může vytvořit řadu nastavení, které ukládají uživatelské předvolby pro barevné schéma aplikace.</span><span class="sxs-lookup"><span data-stu-id="b585b-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="b585b-107">Nebo může být uložena připojovací řetězec, který určuje databázi, která vaše aplikace používá.</span><span class="sxs-lookup"><span data-stu-id="b585b-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="b585b-108">Nastavení povolit, že jste do obou uchovávat informace, které je velmi důležité do aplikace mimo kódu a vytváření profilů, které ukládají požadavků jednotlivých uživatelů.</span><span class="sxs-lookup"><span data-stu-id="b585b-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="b585b-109">Témata v této části popisují, jak můžete použít nastavení v době návrhu a čas spuštění.</span><span class="sxs-lookup"><span data-stu-id="b585b-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b585b-110">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="b585b-110">In This Section</span></span>  
 [<span data-ttu-id="b585b-111">Postupy: Vytvoření nového nastavení v době návrhu</span><span class="sxs-lookup"><span data-stu-id="b585b-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="b585b-112">Vysvětluje, jak používat Visual Studio k vytvoření nového nastavení pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="b585b-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="b585b-113">Postupy: Změna hodnoty existujícího nastavení v době návrhu</span><span class="sxs-lookup"><span data-stu-id="b585b-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="b585b-114">Popisuje, jak pomocí sady Visual Studio změna hodnoty existujícího nastavení.</span><span class="sxs-lookup"><span data-stu-id="b585b-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="b585b-115">Postupy: Změna hodnoty nastavení mezi relacemi aplikace</span><span class="sxs-lookup"><span data-stu-id="b585b-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="b585b-116">Podrobné informace o tom, jak změnit hodnoty nastavení v kompilované aplikace mezi relacemi aplikace.</span><span class="sxs-lookup"><span data-stu-id="b585b-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="b585b-117">Postupy: Čtení uživatelských nastavení při běhu pomocí C#</span><span class="sxs-lookup"><span data-stu-id="b585b-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="b585b-118">Popisuje, jak použít kód číst nastavení pomocí C#.</span><span class="sxs-lookup"><span data-stu-id="b585b-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="b585b-119">Postupy: Zápis uživatelských nastavení při běhu pomocí C#</span><span class="sxs-lookup"><span data-stu-id="b585b-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="b585b-120">Vysvětluje, jak pomocí kódu napíšete a uložíte hodnoty nastavení uživatele pomocí C#.</span><span class="sxs-lookup"><span data-stu-id="b585b-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="b585b-121">Postupy: Přidání více množin nastavení do vaší aplikace v jazyce C#</span><span class="sxs-lookup"><span data-stu-id="b585b-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="b585b-122">Podrobné informace o tom, jak přidat více sad nastavení aplikace pomocí C#.</span><span class="sxs-lookup"><span data-stu-id="b585b-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b585b-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="b585b-123">See Also</span></span>  
 [<span data-ttu-id="b585b-124">Nastavení aplikace pro Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b585b-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)