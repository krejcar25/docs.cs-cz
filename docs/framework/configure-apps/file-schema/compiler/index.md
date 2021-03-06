---
title: "Schéma nastavení kompilátoru a poskytovatele jazyka"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ff278413e2fc91201eeca26fccf9dc5b4fb9d1a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="compiler-and-language-provider-settings-schema"></a>Schéma nastavení kompilátoru a poskytovatele jazyka
Kompilátoru a poskytovatele nastavení jazyka zadejte kompilátor – elementy konfigurace pro zprostředkovatele dostupný jazyk. Každý prvek konfigurace kompilátoru Určuje kód název typu poskytovatele, parametry kompilátoru jazyka názvy podporu a podporu přípony souborů.  
  
 Rozhraní .NET Framework definuje nastavení počáteční kompilátoru v konfiguračním souboru počítače (Machine.config). Vývojářům a dodavatelům kompilátoru můžete přidat nastavení konfigurace pro novou <xref:System.CodeDom.Compiler.CodeDomProvider> implementace. Použití <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metoda prostřednictvím kódu programu výčet zprostředkovatele a kompilátoru konfigurace nastavení jazyka v počítači.  
  
 [\<Konfigurace > elementu](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<System.CodeDom – >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [\<Kompilátory >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [\<kompilátoru >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<System.CodeDom – >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Určuje kompilátor – nastavení konfigurace pro zprostředkovatele dostupný jazyk.|  
|[\<Kompilátory >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Kontejner pro kompilátor – elementy konfigurace; obsahuje nula nebo více [ \<kompilátoru >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementy.|  
|[\<kompilátoru >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Kompilátor – konfigurační atributy Určuje jazyk zprostředkovatele.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje prvek typické kompilátoru konfigurace.  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [Schéma konfiguračního souboru](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<kompilátoru > elementu](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
