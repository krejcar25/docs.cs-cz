---
title: "Použití grafických kontejnerů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 244f8e8a280369798daf12f8a61519826f937a4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-graphics-containers"></a>Použití grafických kontejnerů
A <xref:System.Drawing.Graphics> objekt poskytuje metody, jako například <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, a <xref:System.Drawing.Graphics.DrawString%2A> pro zobrazení vektoru obrázky, rastrové obrázky a text. A <xref:System.Drawing.Graphics> objekt má také několik vlastností, které ovlivňují kvality a orientaci položky, které se mají vykreslovat. Například vlastnost režim vyhlazování Určuje, zda se použije vyhlazení u čar a křivek a vlastnost Světové transformace vliv pozice a oběh položek, které se mají vykreslovat.  
  
 A <xref:System.Drawing.Graphics> objekt je přidružený ke konkrétní zobrazení zařízení. Při použití <xref:System.Drawing.Graphics> objektu k vykreslení v okně <xref:System.Drawing.Graphics> objektu je taky přiřazený dané konkrétní okno.  
  
 A <xref:System.Drawing.Graphics> objekt si lze představit jako kontejner vzhledem k tomu, že obsahuje sadu vlastností, které ovlivňují kreslení a je propojen informace o zařízení. Můžete vytvořit kontejner sekundární v rámci existující <xref:System.Drawing.Graphics> objekt voláním <xref:System.Drawing.Graphics.BeginContainer%2A> metoda této <xref:System.Drawing.Graphics> objektu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Správa stavu grafického objektu](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Popisuje, jak spravovat nastavení kvality, výstřižek oblasti a transformace z <xref:System.Drawing.Graphics> objektu.  
  
 [Použití vnořených grafických kontejnerů](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Ukazuje, jak použít k řízení stavu kontejnery <xref:System.Drawing.Graphics> objektu.
