---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f1e026296745f6fc40171866c81f91818789e01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="textmessageencodingbindingelement"></a>TextMessageEncodingBindingElement
TextMessageEncodingBindingElement  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Metody  
 Třída TextMessageEncodingBindingElement nedefinuje žádné metody.  
  
## <a name="properties"></a>Vlastnosti  
 Třída TextMessageEncodingBindingElement má následující vlastnosti:  
  
### <a name="encoding"></a>Kódování  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Kódování znakové sady, který se má použít pro vysílání zpráv v vazby.  
  
### <a name="maxreadpoolsize"></a>maxReadPoolSize  
 Datový typ: sint32  
  
 Přístup k typu: jen pro čtení  
  
 Celé číslo, které definuje počet zpráv lze číst souběžně bez přidělení nového čtečky.  
  
### <a name="maxwritepoolsize"></a>maxWritePoolSize  
 Datový typ: sint32  
  
 Přístup k typu: jen pro čtení  
  
 Celé číslo, které definuje počet zpráv lze najednou odeslat bez přiděluje nový zapisovače.  
  
### <a name="readerquotas"></a>ReaderQuotas  
 Datový typ: XmlDictionaryReaderQuotas, který  
  
 Přístup k typu: jen pro čtení  
  
 Kvóty čtečky.  
  
## <a name="requirements"></a>Požadavky  
  
|MOF|Deklarované v Servicemodel.mof.|  
|---------|-----------------------------------|  
|Obor názvů|Definované v root\ServiceModel|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
