---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73fad36b5bf14745ca70d297fa988b90d46990df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="servicecredentials"></a>ServiceCredentials
ServiceCredentials  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a>Metody  
 Třída – ServiceCredentials nejsou definovány žádné metody.  
  
## <a name="properties"></a>Vlastnosti  
 Třída – ServiceCredentials má následující vlastnosti:  
  
### <a name="clientcertificate"></a>ClientCertificate  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Certifikát ověřování a zřizování nastavení klienta pro tuto službu.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Aktuální vydaný nastavení ověření pomocí tokenu pro tuto službu.  
  
### <a name="peer"></a>sdílené  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Aktuální přihlašovací údaje, ověřování a nastavení, která má být používána koncových bodů přenosu pro vytváření.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Určuje aktuální nastavení zabezpečené konverzaci.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Certifikát přidružený k této službě.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Nastavení uživatelského jména a hesla pro tuto službu.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Nastavení ověřování systému Windows pro tuto službu.  
  
## <a name="requirements"></a>Požadavky  
  
|MOF|Deklarované v Servicemodel.mof.|  
|---------|-----------------------------------|  
|Obor názvů|Definované v root\ServiceModel|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Description.ServiceCredentials>
