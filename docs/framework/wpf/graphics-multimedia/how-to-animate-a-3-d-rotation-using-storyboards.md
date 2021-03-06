---
title: "Postupy: Animace trojrozměrného otočení použitím scénářů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa67db777ee04edcafa6ca3a53a37a638992fe29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Postupy: Animace trojrozměrného otočení použitím scénářů
Následující příklad ukazuje, jak vytvořit objekt 3D otočit při jeho "wobbles" podle animace <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> a <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> vlastnosti <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objektu. To <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objektu určuje otočení transformace 3D objektu, a proto animace jeho vlastnosti vytvoří desire otočení účinek. Ve scénáři <xref:System.Windows.Media.Animation.DoubleAnimation> se používá k animace <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> vlastnost při <xref:System.Windows.Media.Animation.Vector3DAnimation> se používá k animace <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> vlastnost.  
  
## <a name="example"></a>Příklad  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Viz také  
 [Animace trojrozměrného otočení pomocí Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [Animace trojrozměrné rotace pomocí klíčových snímků (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [Přehled 3D grafiky](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Přehled scénářů](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
