---
title: "Postupy: Definice šablony GroupBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6022f4a521fa64246a24b7aab21c368f5f72af8d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-define-a-groupbox-template"></a>Postupy: Definice šablony GroupBox
Tento příklad ukazuje, jak vytvořit šablonu pro <xref:System.Windows.Controls.GroupBox> ovládacího prvku.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu definuje <xref:System.Windows.Controls.GroupBox> šablony ovládacího prvku pomocí <xref:System.Windows.Controls.Grid> řízení rozložení. Šablona používá <xref:System.Windows.Controls.BorderGapMaskConverter> k definování ohraničení <xref:System.Windows.Controls.GroupBox> tak, aby ohraničení není skrývat <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> obsah.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Controls.GroupBox>  
 [Groupbox – postupy témata](http://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
