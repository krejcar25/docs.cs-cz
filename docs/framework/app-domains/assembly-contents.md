---
title: "Obsah sestavení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a0af2a90d4951b72f8c5100affd6d78ac7f31ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="assembly-contents"></a>Obsah sestavení
Obecně platí statické sestavení se může skládat ze čtyř prvků:  
  
-   [Manifest sestavení](../../../docs/framework/app-domains/assembly-manifest.md), který obsahuje metadata sestavení.  
  
-   Metadata typu.  
  
-   Microsoft (MSIL intermediate language) kód, který implementuje typy.  
  
-   Sadu prostředků.  
  
 Manifest sestavení není požadována, ale buď typy nebo prostředky je nutné poskytnout sestavení žádné smysluplný funkce.  
  
 Existuje několik způsobů, jak seskupit tyto prvky v sestavení. Můžete seskupit všechny elementy do jednoho fyzického souboru, který je znázorněno na následujícím obrázku.  
  
 ![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")  
Jeden soubor sestavení  
  
 Alternativně elementy sestavení může obsahovat několik souborů. Tyto soubory mohou být moduly zkompilovaného kódu (.netmodule), prostředky (například soubory .bmp nebo .jpg) nebo jiné soubory vyžadované aplikací. Vytváření vícesouborového sestavení, pokud chcete kombinovat moduly, které jsou napsané v různých jazycích tak, že aplikace umístěním málokdy použít typy v modulu, který byl stažen pouze v případě potřeby.  
  
 Na následujícím obrázku má vývojář hypotetické aplikace vybrali oddělení některé nástroj kódu do jiného modulu a udržování velkého souboru prostředků (v tomto případě bitovou kopii .bmp) v jeho původní soubor. Rozhraní .NET Framework stáhne soubor jenom v případě, že je odkazován; udržování zřídka odkazovaného kódu v samostatném souboru z aplikace optimalizuje stahování kódu.  
  
 ![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")  
Vícesouborová sestavení  
  
> [!NOTE]
>  Soubory, které tvoří vícesouborového sestavení nejsou propojeny fyzicky prostřednictvím systému souborů. Místo toho jsou propojeny prostřednictvím manifestu sestavení a modul common language runtime je spravuje jako jednotku.  
  
 V tomto obrázku všechny tři soubory patří sestavení, jak je popsáno v manifestu sestavení součástí MyAssembly.dll. K systému souborů jsou tři samostatné soubory. Soubor Util.netmodule byl zkompilován jako modul, protože neobsahuje žádné informace o sestavení. Při vytváření sestavení byl manifest sestavení přidán do knihovny MyAssembly.dll, čímž je naznačen vztah se soubory Util.netmodule a Graphic.bmp.  
  
 Při navrhování aktuálně vašeho zdrojového kódu, provedete explicitní rozhodnutí o tom, jak oddílu funkci vaší aplikace do jednoho nebo více souborů. Při navrhování kódu rozhraní .NET Framework, budou podobné rozhodnutí o tom, jak oddílu funkce do jednoho nebo více sestavení.  
  
## <a name="see-also"></a>Viz také  
 [Sestavení v modulu CLR (Common Language Runtime)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Manifest sestavení](../../../docs/framework/app-domains/assembly-manifest.md)  
 [Důležité informace o zabezpečení sestavení](../../../docs/framework/app-domains/assembly-security-considerations.md)
