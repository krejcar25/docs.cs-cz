---
title: "Postupy: Pokračování služby systému Windows (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 73b16a5e5834f7279ae551d4e7efd26cc86c1d07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>Postupy: Pokračování služby systému Windows (Visual Basic)
Tento příklad používá <xref:System.ServiceProcess.ServiceController> součást pokračujte Správa služby IIS v místním počítači.  
  
## <a name="example"></a>Příklad  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Tento příklad kódu je také k dispozici jako IntelliSense fragment kódu. V Sběrač fragmentů kódu je umístěn v **operačního systému Windows > služby systému Windows**. Další informace najdete v tématu [fragmenty kódu](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkaz na projekt na System.serviceprocess.dll.  
  
-   Přístup k členům <xref:System.ServiceProcess> oboru názvů. Přidat `Imports` příkaz, pokud jste nejsou kvalifikující plně názvy členů v kódu. Další informace najdete v tématu [příkaz Imports (Namespace .NET a typ)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Robustní programování  
 <xref:System.ServiceProcess.ServiceController.MachineName%2A> Vlastnost <xref:System.ServiceProcess.ServiceController> třída je ve výchozím nastavení místním počítači. Chcete-li služby systému Windows na jiný počítač, změňte <xref:System.ServiceProcess.ServiceController.MachineName%2A> vlastnost na název tohoto počítače.  
  
 Nelze volat <xref:System.ServiceProcess.ServiceController.Continue%2A> metoda na službě, dokud je stav služby řadiče <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.  
  
 Následující podmínky mohou způsobit výjimku:  
  
-   Službu nelze obnovit. (<xref:System.InvalidOperationException>)  
  
-   Došlo k chybě při přístupu k systému rozhraní API. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework  
 Řízení služeb v počítači může být omezena pomocí <xref:System.ServiceProcess.ServiceControllerPermissionAccess> výčtu nastavit oprávnění <xref:System.ServiceProcess.ServiceControllerPermission> třídy.  
  
 Přístup k informacím o služby může být omezena pomocí <xref:System.Security.Permissions.PermissionState> výčtu nastavit oprávnění <xref:System.Security.Permissions.SecurityPermission> třídy.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [Postupy: Pozastavení služby systému Windows (Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
