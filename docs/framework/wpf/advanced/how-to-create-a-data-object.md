---
title: "Postupy: Vytvoření datového objektu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 014d5229026a6fdaab203c82932742c7b2c7639e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-object"></a>Postupy: Vytvoření datového objektu
Následující příklady ukazují různé způsoby, jak vytvořit objekt dat pomocí konstruktorů poskytované <xref:System.Windows.DataObject> třídy.  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad kódu vytvoří nový objekt dat a používá jednu z přetížené konstruktory (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) k inicializaci objektu data řetězcem.  V takovém případě formátu příslušná data je určena automaticky podle typu uložených dat a automaticky převádění uložených dat je povoleno ve výchozím nastavení.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a>Popis  
 Následující příklad kódu je zhuštěný verzi výše uvedeném kódu.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad kódu vytvoří nový objekt dat a používá jednu z přetížené konstruktory (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) k inicializaci objektu data s řetězec a formátu zadaná data.  V takovém případě formát dat je zadán řetězcem; <xref:System.Windows.DataFormats> třída poskytuje sadu předdefinovaných typ řetězce. Automatický převod uložených dat je ve výchozím nastavení povolena.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a>Popis  
 Následující příklad kódu je zhuštěný verzi výše uvedeném kódu.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad kódu vytvoří nový objekt dat a používá jednu z přetížené konstruktory (<xref:System.Windows.DataObject.%23ctor%2A>) k inicializaci objektu data s řetězec a formátu zadaná data.  V takovém případě je zadána formát dat <xref:System.Type> parametr.  Automatický převod uložených dat je ve výchozím nastavení povolena.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a>Popis  
 Následující příklad kódu je zhuštěný verzi výše uvedeném kódu.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad kódu vytvoří nový objekt dat a používá jednu z přetížené konstruktory (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) k inicializaci objektu data s řetězec a formátu zadaná data.  V takovém případě formát dat je zadán řetězcem; <xref:System.Windows.DataFormats> třída poskytuje sadu předdefinovaných typ řetězce. Toto přetížení konkrétní konstruktor umožňuje volajícímu zadat, zda je povolen převedení automaticky.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a>Popis  
 Následující příklad kódu je zhuštěný verzi výše uvedeném kódu.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.IDataObject>
