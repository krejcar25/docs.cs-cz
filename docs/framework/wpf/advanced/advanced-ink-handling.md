---
title: "Upřesnění zpracování inkoustu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AutoGeneratedOrientationPage
helpviewer_keywords:
- System.Windows.Input.StylusPlugIns classes
- InkCanvas control [WPF]
- ink [WPF], advanced handling
ms.assetid: abc8481a-f983-416f-b051-9168ac8b2ba3
caps.latest.revision: "52"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ac7bb57f06f0d7021f3c060005033d25ec448b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="advanced-ink-handling"></a>Upřesnění zpracování inkoustu
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Se dodává s verzí <xref:System.Windows.Controls.InkCanvas>, a je element můžete umístit v aplikaci k okamžitému spuštění shromažďování a zobrazení rukopisu. Ale pokud <xref:System.Windows.Controls.InkCanvas> řízení neposkytuje dost dobře úroveň kontroly, můžete zachovat kontrolu na vyšší úrovni přizpůsobením vlastní rozpoznávání rukopisu a třídy vykreslování rukopisu pomocí <xref:System.Windows.Input.StylusPlugIns>.  
  
 <xref:System.Windows.Input.StylusPlugIns> Třídy poskytují mechanismus pro implementaci nízké úrovně řízení přes <xref:System.Windows.Input.Stylus> vstup a dynamicky vykreslování rukopisu. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Třída poskytuje mechanismus pro implementaci vlastního chování a použijte ho pro datový proud dat pocházejících z pera zařízení k zajištění optimálního výkonu. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, Speciální <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, umožňuje přizpůsobit dynamicky vykreslování rukopisu dat v reálném čase to znamená, že <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> nevykresluje digitálního okamžitě jako <xref:System.Windows.Input.StylusPoint> data byla vygenerována, takže se zdá, že "toku" z pera zařízení.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Rukopis s vlastním vykreslováním](../../../../docs/framework/wpf/advanced/custom-rendering-ink.md)  
  [Přijetí vstupu z pera](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)  
  [Vytvoření ovládacího prvku vstupu rukopisu](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)  
  [Model vláken rukopisu](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md)
