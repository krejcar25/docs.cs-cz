---
title: "PNRP při vývoji aplikací"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d11f1b284ebb4e4a44d1dad442f727692fa26ffa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="pnrp-in-application-development"></a>PNRP při vývoji aplikací
V systému Windows Vista, síťové aplikace mohou přistupovat k název publikace a funkce řešení prostřednictvím zjednodušené PNRP aplikačního programovacího rozhraní (API).  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Implementace protokolu Peer Name Resolution Protocol  
 S zjednodušené rozhraní API PNRP nejsou explicitně zadané cloudy k registraci názvu a adresy; součást PNRP automaticky určuje příslušné cloud pro připojení a adresy publikovat v rámci cloudy.  
  
 Pro vysoce zjednodušené PNRP překlad IP adres v systému Windows Vista jsou integrovány do getaddrinfo() funkce Windows Sockets teď PNRP názvy. Pokud chcete použít PNRP přeložit název na adresu IPv6, aplikace můžete použít funkci getaddrinfo() vyřešit name.prnp.net plně kvalifikovaný název domény (FQDN), který název je název partnerského zařízení přeloženy. Doména pnrp.net je vyhrazené domény v systému Windows Vista PNRP překladu IP adres.  
  
 Předávání mezi aplikacemi PeerToPeer zpráv se stále provádí základní architektury, jako je například PeerChannel a WCF [velkého množství dat a Streaming](http://go.microsoft.com/fwlink/?LinkID=179652).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Net.PeerToPeer>
