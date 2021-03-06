---
title: "Postupy: přizpůsobení datové vazby chování (služby WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e94ccb04028db3530705432309a808f17054d970
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Postupy: přizpůsobení datové vazby chování (služby WCF Data Services)
S [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], můžete zadat vlastní logiky, která je volána <xref:System.Data.Services.Client.DataServiceCollection%601> když je objekt přidat nebo odebrat z kolekce vazby, nebo když je zjištěna změna vlastností. Tato vlastní logiky je k dispozici jako metody, který je odkazováno jako <xref:System.Func%602> delegáti, které vrací hodnotu `false` při výchozí chování stále měla při dokončení vlastní metoda a `true` při následné zpracování události by se měla zastavit.  
  
 V příkladech v tomto tématu zadat vlastní metody i `entityChanged` a `entityCollectionChanged` parametry <xref:System.Data.Services.Client.DataServiceCollection%601>. Příklady v tomto tématu službu Northwind ukázková data a data klienta automaticky vygenerovanou služby třídy. Tato služba a datové třídy klienta se vytvoří při dokončení [rychlého startu služby WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Příklad  
 Vytvoří následující kódu stránky XAML souboru <xref:System.Data.Services.Client.DataServiceCollection%601> s vlastních metod, jež jsou volány při změně dat, která je vázána na kolekci vazby. Když <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged> události dojde, je zadaná metoda zabraňuje položku, která byla odebrána z kolekce vazby odstranit ze služby data. Když <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged> události dojde, `ShipDate` ověření hodnoty zajistit, že se neprovedou změny objednávky, které již byly součástí.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Příklad  
 Následující XAML definuje okna pro předchozí příklad.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>Viz také  
 [Klientská knihovna pro WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
