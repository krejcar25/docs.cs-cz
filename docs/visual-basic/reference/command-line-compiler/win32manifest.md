---
title: /win32manifest (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a46641181c3ff66882468f8372bb97c3a49a8462
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="win32manifest-visual-basic"></a>/win32manifest (Visual Basic)
Identifikuje uživatelem definované souboru manifestu aplikace Win32, který má být vložen do souboru projektu přenosné spustitelný soubor (PE).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a>Arguments  
  
|Termín|Definice|  
|---|---|  
|`fileName`|Cesta vlastního souboru manifestu.|  
  
## <a name="remarks"></a>Poznámky  
 Ve výchozím nastavení Visual Basic – kompilátor vloží manifest aplikace, která určuje požadovanou úroveň vykonávání asInvoker. Manifest vytvoří ve stejné složce, ve kterém spustitelný soubor je vytvořen, obvykle bin\Debug nebo bin\Release složky při použití sady Visual Studio. Pokud chcete zadat vlastní manifest, např. Chcete-li určit požadovanou úroveň vykonávání highestAvailable nebo requireAdministrator, tuto možnost použijte k zadání názvu souboru.  
  
> [!NOTE]
>  Tuto možnost a [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) se vzájemně vylučují. Pokud se pokusíte použít obě možnosti ve stejném příkazovém řádku, zobrazí se chyba sestavení.  
  
 Aplikace, která nemá žádné aplikace, manifest, který určuje že požadovanou úroveň vykonávání budou platit virtualizaci souborů a registrů pod funkci Řízení uživatelských účtů v systému Windows Vista. Další informace o virtualizaci najdete v tématu [ClickOnce – nasazení v systému Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Aplikace budou platit virtualizace, pokud platí některá z následujících podmínek:  
  
1.  Můžete použít `/nowin32manifest` a neposkytuje manifest v pozdější fázi sestavování nebo jako součást souboru prostředků Windows (.res) pomocí `/win32resource` možnost.  
  
2.  Můžete zadat vlastní manifestu, který není uveden požadovanou úroveň vykonávání.  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]vytvoří výchozí soubor manifest a ukládá je v adresářích debug a release společně se spustitelným souborem. Můžete zobrazit nebo upravit výchozí soubor app.manifest kliknutím **nastavení nástroje Řízení uživatelských účtů zobrazení** na **aplikace** kartě v Návrháři projektu. Další informace najdete v tématu [stránka aplikace, Návrhář projektu (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Manifest aplikace můžete poskytnout jako vlastní krok po sestavení nebo jako součást zdrojového souboru Win32 pomocí `/nowin32manifest` možnost. Stejnou možnost použijte, pokud má vaše aplikace podléhat souborů nebo registru virtualizace v systému Windows Vista. To zabrání kompilátoru z vytváření a vložení manifestu výchozí v souboru PE.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje výchozí manifest, Visual Basic – kompilátor vloží do PE.  
  
> [!NOTE]
>  Kompilátor vloží název standardní aplikace MyApplication.app do manifestu XML. Toto je alternativní řešení Chcete-li povolit aplikací pro spuštění na Windows Server 2003 Service Pack 3.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Basic – kompilátor příkazového řádku](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
