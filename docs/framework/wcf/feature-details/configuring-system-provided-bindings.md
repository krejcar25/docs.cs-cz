---
title: "Konfigurace vazeb poskytovaných systémem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], system-provided bindings
- WCF [WCF], system-provided bindings
- bindings [WCF], system-provided
ms.assetid: 443f8d65-f1f2-4311-83b3-4d8fdf7ccf16
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e77cf5cc271e86c02e8355dde6f721fe7751416
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-system-provided-bindings"></a>Konfigurace vazeb poskytovaných systémem
Vazby zadejte komunikační mechanizmus použít při komunikaci se koncový bod a určují, jak se připojit k koncový bod. Vazby obsahovat prvky, které definují jak [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kanály jsou vrstvený nahoru a zajistit tak funkce vyžaduje komunikaci. Vazba obsahuje tři typy elementů:  
  
-   Prvky vazeb kanálu protokolu, které určují nastavení zabezpečení, spolehlivost, nastavení tok kontextu nebo uživatelem definované protokolů pro použití s zprávy, které se odesílají do koncového bodu.  
  
-   Kanál elementů přenosové vazby, které určují podkladový přenosový protokol mají použít při odesílání zprávy do koncového bodu, například TCP nebo HTTP.  
  
-   Kódování prvky vazby, které určují přenosová kódování použité pro zprávy, které se odesílají do koncového bodu, například text/XML, binární, zpráva nebo zpráva přenosu optimalizace mechanismus (MTOM).  
  
 Toto téma představuje všechny poskytované systémem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] vazby. Pokud žádná z nich splňuje požadavky na přesný pro vaši aplikaci, můžete vytvořit vazbu pomocí <xref:System.ServiceModel.Channels.CustomBinding> třídy. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]vytváření vlastních vazeb, najdete v části [vlastní vazby](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
> [!IMPORTANT]
>  Vyberte vazbu s povoleným zabezpečením. Ve výchozím nastavení jsou všechny vazby, s výjimkou <xref:System.ServiceModel.BasicHttpBinding> vazby, mají povoleno zabezpečení. Pokud nevyberete zabezpečené vazby, nebo pokud zakážete zabezpečení, ujistěte se, že vaše síť výměnu jsou chráněny jiným způsobem, jako je například v zabezpečené datovém centru nebo v izolované síti.  
  
> [!IMPORTANT]
>  Nepoužívejte duplexní kontrakty vazby, která nepodporují zabezpečení, nebo jež mají zabezpečení zakázáno, pokud exchange sítě je zabezpečená jiným způsobem.  
  
## <a name="system-provided-bindings"></a>Vazby poskytované systémem  
 Následující vazby dodávané se [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
|Vazba|Konfigurační Element|Popis|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Vazba, který je vhodný pro komunikaci s profilu WS-Basic vyhovující webové služby, například webových služeb ASP.NET (ASMX) – na základě služby. Tato vazba používá protokol HTTP jako přenosu a text/XML jako výchozí kódování zprávy.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Zabezpečení a vzájemná spolupráce vazby, který je vhodný pro kontraktů služby duplexní režim.|  
|<xref:System.ServiceModel.WS2007HttpBinding>|[\<– ws2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|Zabezpečení a vzájemná spolupráce vazbu, která poskytuje podporu pro správné verze <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, a <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> elementů vazby.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<– wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Zabezpečení a vzájemná spolupráce vazby, který je vhodný pro služby duplexní kontrakty nebo komunikaci prostřednictvím protokolu SOAP zprostředkovatelů.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<– wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Zabezpečení a vzájemná spolupráce vazbu, podporuje protokol WS-Federation, povolení organizace, které jsou ve federaci efektivní ověřování a autorizaci uživatelů.|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|[\<– ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)|Zabezpečení a vzájemná spolupráce vazbu, která je odvozena z <xref:System.ServiceModel.WS2007HttpBinding> a podporuje federované zabezpečení.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Zabezpečení a optimalizované vazbu vhodný pro komunikaci mezi počítači mezi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace.|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<– netNamedPipeBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|Bezpečné, spolehlivé a optimalizované vazby, který je vhodný pro-počítače komunikace mezi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace.|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<– netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Vazbu zařazených do fronty, který je vhodný pro komunikaci mezi počítači mezi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace.|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|Vazba, která umožňuje komunikaci zabezpečené, víc počítačů.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Vazba použitá ke konfiguraci koncových bodů pro [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] webové služby, které se zveřejňují přes požadavky HTTP místo protokolu SOAP zprávy.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Vazba, který je vhodný pro komunikaci mezi počítači mezi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace a stávající aplikace služby Řízení front zpráv (MSMQ).|  
  
## <a name="binding-features"></a>Vazba funkce  
 V další tabulce jsou uvedeny některé klíčové funkce každé vazby poskytované systémem zadat. Vazby jsou uvedena ve sloupci první a informace týkající se funkce jsou popsány v tabulce. Následující tabulka poskytuje klíč pro zkratky vazby použít. Vyberte vazbu, určete, který sloupec splňuje všechny funkce řádků, které potřebujete.  
  
|Vazba|Interoperabilita|Režim zabezpečení (výchozí)|Relace<br /><br /> (Výchozí)|Transakce|Duplex|  
|-------------|----------------------|----------------------------------|-----------------------------|------------------|------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(None), přenos zpráv, ve smíšeném|Žádný, (žádný)|(Žádný)|není k dispozici|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|Smíšený NONE, přenos, (zprávy)|(None), přenosu, spolehlivé relace|Ano (none),|není k dispozici|  
|<xref:System.ServiceModel.WS2007HttpBinding>|WS-zabezpečení, WS-Trust, WS-SecureConversation, WS-SecurityPolicy|Smíšený NONE, přenos, (zprávy)|(None), přenosu, spolehlivé relace|Ano (none),|není k dispozici|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|Žádný (zprávy)|(Spolehlivé relace)|Ano (none),|Ano|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|Smíšený NONE, (zprávy)|(None), spolehlivé relace|Ano (none),|Ne|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|WS-Federation|Smíšený NONE, (zprávy)|(None), spolehlivé relace|Ano (none),|Ne|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|Žádný (přenos), zprávy<br /><br /> Ve smíšeném|Spolehlivá relace (přenos)|Ano (none),|Ano|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|NONE,<br /><br /> (Přenos)|Žádný (přenos)|Ano (none),|Ano|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Žádné zprávy (přenos), obě|(Žádný)|Ano (none),|Ne|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|sdílené|Žádné zprávy (přenos), ve smíšeném|(Žádný)|(Žádný)|Ano|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|Žádný (přenos)|(Žádný)|Ano (none),|není k dispozici|  
  
 Následující tabulka popisuje možnosti, které najdete v předchozí tabulce.  
  
|Funkce|Popis|  
|-------------|-----------------|  
|Typ interoperability|Název protokolu nebo technologii, se kterým zajišťuje vazby vzájemná spolupráce.|  
|Zabezpečení|Určuje, jak jsou zabezpečená kanál:<br /><br /> -None: Není zabezpečené zprávu protokolu SOAP a klient není ověřen.<br />-Přenos: V přenosové vrstvě jsou splněné požadavky na zabezpečení.<br />-Zpráva: Ve vrstvě zprávy jsou splněny požadavky na zabezpečení.<br />-Ve smíšeném: Tento režim zabezpečení se označuje jako `TransportWithMessageCredentials`. Zpracovává přihlašovací údaje na úrovni zpráv a přenosová vrstva byly splněny požadavky na integrity a důvěrnosti.<br />-Obě: Se používají oba úroveň a přenosu úrovně zabezpečení zpráv. Tato možnost je jedinečná <xref:System.ServiceModel.NetMsmqBinding>.|  
|Relace|Určuje, jestli tato vazba podporuje kontrakty relace.|  
|Transakce|Určuje, zda je povoleno transakce.|  
|Duplex|Určuje, zda jsou podporovány duplexní kontrakty. Všimněte si, že tato funkce vyžaduje podporu pro relace vazba.|  
|streamování|Určuje, zda je podporováno zpráva streamování.|  
  
## <a name="see-also"></a>Viz také  
 [Přehled vytváření koncových bodů](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Používání vazeb ke konfiguraci služeb a klientů](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Základní programování WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)
