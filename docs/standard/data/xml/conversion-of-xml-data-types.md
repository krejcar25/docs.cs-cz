---
title: "Převod XML datových typů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d18b69c2d5baeac77cbdf45bebd6f0c9d5c94d9f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="conversion-of-xml-data-types"></a>Převod XML datových typů
Většina metody nalezen v **XmlConvert** třída slouží k převodu dat mezi řetězci a formáty silného typu. Metody jsou nezávislé národní prostředí. To znamená, že není berou v úvahu žádné nastavení národního prostředí při provádění převod.  
  
## <a name="reading-string-as-types"></a>Čtení řetězec jako typy  
 Následující příklad načte řetězec a převede jej na **data a času** typu.  
  
 Zadané následující vstup XML:  
  
 **Vstup**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 Převede řetězec na tento kód **data a času** formátu:  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>Zápis řetězců jako typy  
 Následující ukázkové čtení **Int32** a převede jej na řetězec.  
  
 Zadané následující vstup XML:  
  
 **Vstup**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Převede tento kód **Int32** do **řetězec**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>Viz také  
 [Převádění řetězců na datové typy rozhraní .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [Převádění typů rozhraní .NET Framework na řetězce](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
