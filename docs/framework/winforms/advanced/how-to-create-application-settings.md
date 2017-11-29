---
title: "Postupy: Vytváření nastavení aplikace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 481239b472ced5ef6251b665dad16e83a170607d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-application-settings"></a><span data-ttu-id="67645-102">Postupy: Vytváření nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="67645-102">How to: Create Application Settings</span></span>
<span data-ttu-id="67645-103">Pomocí spravovaného kódu, můžete vytvořit nové nastavení aplikace a navázat je na vlastnosti svého formuláře nebo svého formuláře ovládací prvky, tak, aby tato nastavení jsou načteny a automaticky uloženy v době běhu.</span><span class="sxs-lookup"><span data-stu-id="67645-103">Using managed code, you can create new application settings and bind them to properties on your form or your form's controls, so that these settings are loaded and saved automatically at run time.</span></span>  
  
 <span data-ttu-id="67645-104">V následujícím postupu vytvoříte ručně obálkovou třídu odvozenou od <xref:System.Configuration.ApplicationSettingsBase>.</span><span class="sxs-lookup"><span data-stu-id="67645-104">In the following procedure, you manually create a wrapper class that derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="67645-105">Pro tuto třídu přidáte veřejně přístupná vlastnost pro každé nastavení aplikace, kterou chcete vystavit.</span><span class="sxs-lookup"><span data-stu-id="67645-105">To this class you add a publicly accessible property for each application setting that you want to expose.</span></span>  
  
 <span data-ttu-id="67645-106">Tento postup pomocí minimální kódu v návrháři Visual Studio můžete také provést.</span><span class="sxs-lookup"><span data-stu-id="67645-106">You can also perform this procedure using minimal code in the Visual Studio designer.</span></span>  <span data-ttu-id="67645-107">Viz také [postupy: vytvoření aplikace nastavení pomocí návrháře](http://msdn.microsoft.com/library/wabtadw6\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="67645-107">Also see [How to: Create Application Settings Using the Designer](http://msdn.microsoft.com/library/wabtadw6\(v=vs.110\)).</span></span>  
  
### <a name="to-create-new-application-settings-programmatically"></a><span data-ttu-id="67645-108">Chcete-li vytvořit nové nastavení aplikace prostřednictvím kódu programu</span><span class="sxs-lookup"><span data-stu-id="67645-108">To create new Application Settings programmatically</span></span>  
  
1.  <span data-ttu-id="67645-109">Přidejte novou třídu do projektu a přejmenujte ji.</span><span class="sxs-lookup"><span data-stu-id="67645-109">Add a new class to your project, and rename it.</span></span> <span data-ttu-id="67645-110">Pro tento postup jsme zavolá Tato třída `MyUserSettings`.</span><span class="sxs-lookup"><span data-stu-id="67645-110">For this procedure, we will call this class `MyUserSettings`.</span></span> <span data-ttu-id="67645-111">Změňte definici třídy tak, aby třída odvozená z <xref:System.Configuration.ApplicationSettingsBase>.</span><span class="sxs-lookup"><span data-stu-id="67645-111">Change the class definition so that the class derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span>  
  
2.  <span data-ttu-id="67645-112">Definujte vlastnost této obálkové třídy pro každé nastavení aplikace, budete potřebovat a použít tuto vlastnost se buď <xref:System.Configuration.ApplicationScopedSettingAttribute> nebo <xref:System.Configuration.UserScopedSettingAttribute>, v závislosti na rozsahu nastavení.</span><span class="sxs-lookup"><span data-stu-id="67645-112">Define a property on this wrapper class for each application setting you require, and apply that property with either the <xref:System.Configuration.ApplicationScopedSettingAttribute> or <xref:System.Configuration.UserScopedSettingAttribute>, depending on the scope of the setting.</span></span> <span data-ttu-id="67645-113">Další informace o nastavení oboru, najdete v části [přehled nastavení aplikace](../../../../docs/framework/winforms/advanced/application-settings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67645-113">For more information about settings scope, see [Application Settings Overview](../../../../docs/framework/winforms/advanced/application-settings-overview.md).</span></span> <span data-ttu-id="67645-114">Nyní by váš kód by měl vypadat takto:</span><span class="sxs-lookup"><span data-stu-id="67645-114">By now, your code should look like this:</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3.  <span data-ttu-id="67645-115">Vytvoření instance této třídy obálku ve vaší aplikaci.</span><span class="sxs-lookup"><span data-stu-id="67645-115">Create an instance of this wrapper class in your application.</span></span> <span data-ttu-id="67645-116">Obvykle bude členem privátní hlavní formulář.</span><span class="sxs-lookup"><span data-stu-id="67645-116">It will commonly be a private member of the main form.</span></span> <span data-ttu-id="67645-117">Teď, když jste definovali třídě, musíte pro vytvoření vazby na vlastnost; v takovém případě <xref:System.Windows.Forms.Form.BackColor%2A> vlastnosti svého formuláře.</span><span class="sxs-lookup"><span data-stu-id="67645-117">Now that you have defined your class, you need to bind it to a property; in this case, the <xref:System.Windows.Forms.Form.BackColor%2A> property of your form.</span></span> <span data-ttu-id="67645-118">Můžete to provést v svého formuláře `Load` obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="67645-118">You can accomplish this in your form's `Load` event handler.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="67645-119">Pokud zadáte způsob, jak změnit nastavení v době běhu, musíte uložit aktuální nastavení uživatele na disk, když svého formuláře zavře, jinak tyto změny budou ztraceny.</span><span class="sxs-lookup"><span data-stu-id="67645-119">If you provide a way to change settings at run time, you will need to save the user's current settings to disk when your form closes, or else these changes will be lost.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     <span data-ttu-id="67645-120">Teď úspěšně vytvořit nové nastavení aplikace a vázána na zadanou vlastnost.</span><span class="sxs-lookup"><span data-stu-id="67645-120">You have now successfully created a new application setting and bound it to the specified property.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="67645-121">Zabezpečení rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="67645-121">.NET Framework Security</span></span>  
 <span data-ttu-id="67645-122">Ve výchozím nastavení <xref:System.Configuration.LocalFileSettingsProvider>, udržuje informace o konfiguračních souborů jako prostý text.</span><span class="sxs-lookup"><span data-stu-id="67645-122">The default settings provider, <xref:System.Configuration.LocalFileSettingsProvider>, persists information to configuration files as plain text.</span></span> <span data-ttu-id="67645-123">Toto omezení zabezpečení zabezpečení přístupu k souboru poskytované operačním systémem pro aktuálního uživatele.</span><span class="sxs-lookup"><span data-stu-id="67645-123">This limits security to the file access security provided by the operating system for the current user.</span></span> <span data-ttu-id="67645-124">Z toho důvodu se musí dát pozor s informacemi uloženými v konfiguračních souborech.</span><span class="sxs-lookup"><span data-stu-id="67645-124">Because of this, care must be taken with the information stored in configuration files.</span></span> <span data-ttu-id="67645-125">Například jeden běžně používá pro nastavení aplikace je k ukládání připojovacích řetězců, které odkazují na úložiště dat aplikace.</span><span class="sxs-lookup"><span data-stu-id="67645-125">For example, one common use for application settings is to store connection strings that point to the application's data store.</span></span> <span data-ttu-id="67645-126">Z důvodu zabezpečení se ale tyto řetězce by neměla zahrnovat hesla.</span><span class="sxs-lookup"><span data-stu-id="67645-126">However, because of security concerns, such strings should not include passwords.</span></span> <span data-ttu-id="67645-127">Další informace o připojovacích řetězcích najdete v tématu <xref:System.Configuration.SpecialSetting>.</span><span class="sxs-lookup"><span data-stu-id="67645-127">For more information about connection strings, see <xref:System.Configuration.SpecialSetting>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67645-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="67645-128">See Also</span></span>  
 <xref:System.Configuration.SpecialSettingAttribute>  
 <xref:System.Configuration.LocalFileSettingsProvider>  
 [<span data-ttu-id="67645-129">Přehled nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="67645-129">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="67645-130">Postupy: ověření nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="67645-130">How to: Validate Application Settings</span></span>](../../../../docs/framework/winforms/advanced/how-to-validate-application-settings.md)