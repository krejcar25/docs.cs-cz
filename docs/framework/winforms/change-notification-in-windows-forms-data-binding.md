---
title: "Oznámení změn v datové vazbě rozhraní Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ffafaff2355e89e2127742f2fba5c005492b4580
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="change-notification-in-windows-forms-data-binding"></a><span data-ttu-id="302ac-102">Oznámení změn v datové vazbě rozhraní Windows Forms</span><span class="sxs-lookup"><span data-stu-id="302ac-102">Change Notification in Windows Forms Data Binding</span></span>
<span data-ttu-id="302ac-103">Jedním z nejdůležitějších konceptů Windows Forms – datová vazba je *upozornění na změnu*.</span><span class="sxs-lookup"><span data-stu-id="302ac-103">One of the most important concepts of Windows Forms data binding is *change notification*.</span></span> <span data-ttu-id="302ac-104">Aby se zajistilo, že zdroj dat a vázané ovládací prvky vždy mít nejnovější data, je nutné přidat oznámení o změně pro datovou vazbu.</span><span class="sxs-lookup"><span data-stu-id="302ac-104">To ensure that your data source and bound controls always have the most recent data, you must add change notification for data binding.</span></span> <span data-ttu-id="302ac-105">Konkrétně chcete zajistit, že jsou vázané ovládací prvky upozorněni na změny, které byly provedeny k jejich zdroji dat a zdroj dat je upozornění na změny, které byly provedeny na vázané vlastnosti ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="302ac-105">Specifically, you want to ensure that bound controls are notified of changes that were made to their data source, and the data source is notified of changes that were made to the bound properties of a control.</span></span>  
  
 <span data-ttu-id="302ac-106">Existují různé druhy oznámení o změně, v závislosti na druhu datové vazby:</span><span class="sxs-lookup"><span data-stu-id="302ac-106">There are different kinds of change notification, depending on the kind of data binding:</span></span>  
  
-   <span data-ttu-id="302ac-107">Jednoduchá vazba, ve kterém jeden řídicí vlastnost je vázána na jednu instanci objektu.</span><span class="sxs-lookup"><span data-stu-id="302ac-107">Simple binding, in which a single control property is bound to a single instance of an object.</span></span>  
  
-   <span data-ttu-id="302ac-108">Vazba na základě seznamu, která může zahrnovat vlastnost jeden ovládací prvek vázán vlastnost položky v seznamu nebo vlastnost ovládací prvek vázán na seznam objektů.</span><span class="sxs-lookup"><span data-stu-id="302ac-108">List-based binding, which can include a single control property bound to the property of an item in a list or a control property bound to a list of objects.</span></span>  
  
 <span data-ttu-id="302ac-109">Kromě toho při vytváření ovládacích prvků Windows Forms, které chcete použít pro datovou vazbu, musíte použít *PropertyName*změnilo vzor ovládacích prvků, tak, že změny vázané vlastnosti ovládacího prvku rozšířeny zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="302ac-109">Additionally, if you are creating Windows Forms controls that you want to use for data binding, you must apply the *PropertyName*Changed pattern to the controls, so that changes to the bound property of a control are propagated to the data source.</span></span>  
  
## <a name="change-notification-for-simple-binding"></a><span data-ttu-id="302ac-110">Oznámení o změně pro jednoduchá vazba</span><span class="sxs-lookup"><span data-stu-id="302ac-110">Change Notification for Simple Binding</span></span>  
 <span data-ttu-id="302ac-111">Jednoduchá vazba obchodní objekty musí zadejte oznámení o změně při změně hodnoty vázané vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="302ac-111">For simple binding, business objects must provide change notification when the value of a bound property changes.</span></span> <span data-ttu-id="302ac-112">Můžete to provést pomocí vystavení *PropertyName*změněno událost pro každou vlastnost objektu vaší firmy a objekt obchodní vytvoření vazby na ovládací prvky s <xref:System.Windows.Forms.BindingSource> nebo upřednostňovanou metodou, ve kterém se implementuje obchodní objekt <xref:System.ComponentModel.INotifyPropertyChanged> rozhraní a vyvolá <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> události při změně hodnoty vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="302ac-112">You can do this by exposing an *PropertyName*Changed event for each property of your business object and binding the business object to controls with the <xref:System.Windows.Forms.BindingSource> or the preferred method in which your business object implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface and raises a <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event when the value of a property changes.</span></span> <span data-ttu-id="302ac-113">Další informace najdete v tématu [postupy: implementace rozhraní INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md).</span><span class="sxs-lookup"><span data-stu-id="302ac-113">For more information, see [How to: Implement the INotifyPropertyChanged Interface](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md).</span></span> <span data-ttu-id="302ac-114">Při použití objektů implementujících <xref:System.ComponentModel.INotifyPropertyChanged> rozhraní, není nutné použít <xref:System.Windows.Forms.BindingSource> o vázání objektu do ovládacího prvku, ale pomocí <xref:System.Windows.Forms.BindingSource> se doporučuje.</span><span class="sxs-lookup"><span data-stu-id="302ac-114">When you use objects that implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface, you do not have to use the <xref:System.Windows.Forms.BindingSource> to bind the object to a control, but using the <xref:System.Windows.Forms.BindingSource> is recommended.</span></span>  
  
## <a name="change-notification-for-list-based-binding"></a><span data-ttu-id="302ac-115">Oznámení o změně pro vazbu na základě seznamu</span><span class="sxs-lookup"><span data-stu-id="302ac-115">Change Notification for List-Based Binding</span></span>  
 <span data-ttu-id="302ac-116">Windows Forms závisí na změnit a vázané seznam zajistit změnu vlastnosti (změní hodnotu vlastnosti položky seznamu) (položka je odstranit nebo přidat do seznamu) informace, které vázané ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="302ac-116">Windows Forms depends on a bound list to provide property change (a list item property value changes) and list changed (an item is deleted or added to the list) information to bound controls.</span></span> <span data-ttu-id="302ac-117">Proto musí implementovat seznamy použitá k vazbě dat <xref:System.ComponentModel.IBindingList>, který poskytuje oba typy oznámení o změně.</span><span class="sxs-lookup"><span data-stu-id="302ac-117">Therefore, lists used for data binding must implement the <xref:System.ComponentModel.IBindingList>, which provides both types of change notification.</span></span> <span data-ttu-id="302ac-118"><xref:System.ComponentModel.BindingList%601> Je obecnou implementaci <xref:System.ComponentModel.IBindingList> a je určená pro použití s Windows Forms – datová vazba.</span><span class="sxs-lookup"><span data-stu-id="302ac-118">The <xref:System.ComponentModel.BindingList%601> is a generic implementation of <xref:System.ComponentModel.IBindingList> and is designed for use with Windows Forms data binding.</span></span> <span data-ttu-id="302ac-119">Můžete vytvořit <xref:System.ComponentModel.BindingList%601> obsahující obchodní typ objektu, který implementuje <xref:System.ComponentModel.INotifyPropertyChanged> a seznamu automaticky převede <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> události <xref:System.ComponentModel.IBindingList.ListChanged> události.</span><span class="sxs-lookup"><span data-stu-id="302ac-119">You can create a <xref:System.ComponentModel.BindingList%601> that contains a business object type that implements <xref:System.ComponentModel.INotifyPropertyChanged> and the list will automatically convert the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events to <xref:System.ComponentModel.IBindingList.ListChanged> events.</span></span> <span data-ttu-id="302ac-120">Pokud není seznam vázané <xref:System.ComponentModel.IBindingList>, je třeba svázat seznam objektů k ovládacím prvkům Windows Forms pomocí <xref:System.Windows.Forms.BindingSource> součásti.</span><span class="sxs-lookup"><span data-stu-id="302ac-120">If the bound list is not an <xref:System.ComponentModel.IBindingList>, you must bind the list of objects to Windows Forms controls by using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="302ac-121"><xref:System.Windows.Forms.BindingSource> Součást poskytne seznam vlastností převod podobná <xref:System.ComponentModel.BindingList%601>.</span><span class="sxs-lookup"><span data-stu-id="302ac-121">The <xref:System.Windows.Forms.BindingSource> component will provide property-to-list conversion similar to that of the <xref:System.ComponentModel.BindingList%601>.</span></span> <span data-ttu-id="302ac-122">Další informace najdete v tématu [postupy: vytváření oznámení o změnách pomocí BindingSource a INotifyPropertyChanged rozhraní](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md).</span><span class="sxs-lookup"><span data-stu-id="302ac-122">For more information, see [How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md).</span></span>  
  
## <a name="change-notification-for-custom-controls"></a><span data-ttu-id="302ac-123">Oznámení o změně pro vlastní ovládací prvky</span><span class="sxs-lookup"><span data-stu-id="302ac-123">Change Notification for Custom Controls</span></span>  
 <span data-ttu-id="302ac-124">Nakonec ze strany řízení musí vystavit *PropertyName*změněno událost pro každou vlastnost navržený tak, aby se vázané na data.</span><span class="sxs-lookup"><span data-stu-id="302ac-124">Finally, from the control side you must expose a *PropertyName*Changed event for each property designed to be bound to data.</span></span> <span data-ttu-id="302ac-125">Změny vlastností ovládacího prvku rozšířeny pak vázaný datový zdroj.</span><span class="sxs-lookup"><span data-stu-id="302ac-125">The changes to the control property are then propagated to the bound data source.</span></span> <span data-ttu-id="302ac-126">Další informace najdete v tématu [postupy: použití vzoru PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="302ac-126">For more information, see [How to: Apply the PropertyNameChanged Pattern](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302ac-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="302ac-127">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 <xref:System.ComponentModel.BindingList%601>  
 [<span data-ttu-id="302ac-128">Windows Forms – datová vazba</span><span class="sxs-lookup"><span data-stu-id="302ac-128">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="302ac-129">Zdroje dat podporované rozhraním Windows Forms</span><span class="sxs-lookup"><span data-stu-id="302ac-129">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [<span data-ttu-id="302ac-130">Datová vazba a systém Windows Forms</span><span class="sxs-lookup"><span data-stu-id="302ac-130">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)