---
title: "Přehled zabezpečení přenosu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
caps.latest.revision: "23"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 71325089f2c72f6f01b2179bd150d21a98b3a8e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="transport-security-overview"></a>Přehled zabezpečení přenosu
Přenosu mechanismy zabezpečení v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] závisí na vazby a přenosu používá. Například při použití <xref:System.ServiceModel.WSHttpBinding> třída, přenos, je HTTP a primární mechanismus pro zabezpečení přenosu je Secure Sockets Layer (SSL) prostřednictvím protokolu HTTP, označovaného jako protokol HTTPS. Toto téma popisuje mechanismy zabezpečení hlavní přenos, který je používán [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vazby poskytované systémem.  
  
> [!NOTE]
>  Když se použije zabezpečení SSL v rozhraní .NET Framework 3.5 a později [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta používá k ověřování řetězu certifikátů v zprostředkující certifikáty v úložišti certifikátů i zprostředkující certifikáty obdržel během vyjednávání SSL certifikát služby. Rozhraní .NET framework 3.0 používá jenom nainstalovaná v místním úložišti certifikátů zprostředkující certifikáty.  
  
> [!WARNING]
>  Při zabezpečení přenosu se používá, <!--zz <xref:System.Treading.Thread.CurrentPrincipal%2A> --> `CurrentPrincipal` mohou být přepsány vlastnosti. Aby k této situaci sadu <!--zz <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermission%2A> --> `PrincipalPermission` na hodnotu None. <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>je chování služby, které lze nastavit u popisu služby.  
  
## <a name="basichttpbinding"></a>BasicHttpBinding  
 Ve výchozím nastavení <xref:System.ServiceModel.BasicHttpBinding> třída neposkytuje zabezpečení. Tato vazba je určená pro interoperabilitu se zprostředkovateli webových služeb, které neimplementují zabezpečení. Však můžete přepnout na zabezpečení nastavením <xref:System.ServiceModel.BasicHttpSecurity.Mode%2A> vlastnost na libovolnou hodnotu kromě <xref:System.ServiceModel.BasicHttpSecurityMode.None>. Pokud chcete povolit zabezpečení přenosu, nastavte vlastnost na <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
### <a name="interoperation-with-iis"></a>Vzájemná spolupráce pomocí služby IIS  
 <xref:System.ServiceModel.BasicHttpBinding> Třída se používá hlavně pro spolupráci s existující webové služby a řadu tyto služby jsou hostované pomocí Internetové informační služby (IIS). Zabezpečení přenosu pro tuto vazbu v důsledku toho je určená pro bezproblémové spolupráci s weby služby IIS. Uděláte to pomocí nastavení režimu zabezpečení na <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> a potom nastavení klienta typ přihlašovacích údajů. Hodnoty typu pověření odpovídají mechanismy zabezpečení adresáře služby IIS. Následující kód ukazuje režimu se nastavuje a nastavte typ přihlašovacích údajů k systému Windows. Tuto konfiguraci můžete použít, když klient i server jsou ve stejné doméně systému Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#10)] 
 [!code-vb[c_ProgrammingSecurity#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#10)]  
  
 Nebo v konfiguraci:  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <binding name="SecurityByTransport">  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" />  
       </security>  
     </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 Následující části popisují jiné typy pověření klienta.  
  
#### <a name="basic"></a>Základní  
 To odpovídá základní ověřování ve službě IIS. Při použití tohoto režimu, musí být server služby IIS nakonfigurované uživatelské účty systému Windows a příslušná oprávnění systému souborů NTFS. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], najdete v části [základní ověření povolení a konfigurace název sféry](http://go.microsoft.com/fwlink/?LinkId=88592). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], najdete v části [IIS 7.0 Beta: Konfigurace základní ověřování](http://go.microsoft.com/fwlink/?LinkId=88593).  
  
#### <a name="certificate"></a>certifikát  
 Možnost, aby klienti k přihlášení pomocí certifikátu má služba IIS. Tato funkce také umožňuje službě IIS mapování certifikátu klienta pro účet systému Windows. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], najdete v části [povolení klientských certifikátů ve službě IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88594). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], najdete v části [IIS 7.0 Beta: Konfigurace certifikátů serveru ve službě IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="digest"></a>Ověřování algoritmem Digest  
 Ověřování hodnotou hash je podobná základní ověřování, ale nabízí výhodu v podobě odeslání přihlašovacích údajů jako hodnota hash, místo ve formátu prostého textu. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], najdete v části [ověřování algoritmem Digest ve službě IIS 6.0](http://go.microsoft.com/fwlink/?LinkID=88443). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], najdete v části [IIS 7.0 Beta: Konfigurace ověřování algoritmem Digest](http://go.microsoft.com/fwlink/?LinkId=88596).  
  
#### <a name="windows"></a>Windows  
 To odpovídá integrované ověřování systému Windows ve službě IIS. Pokud nastavíte tuto hodnotu, server také musí existovat v doméně systému Windows, který používá protokol Kerberos jako řadič domény. Pokud server není připojen k doméně založenou na protokolu Kerberos, nebo pokud systému Kerberos nezdaří, můžete použít hodnoty NT LAN Manager (NTLM) popsané v další části. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], najdete v části [integrované ověřování systému Windows ve službě IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88597). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], najdete v části [IIS 7.0 Beta: Konfigurace certifikátů serveru ve službě IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="ntlm"></a>NTLM  
 Díky tomu může server pro ověřování pomocí protokolu NTLM, pokud se protokol Kerberos nezdaří. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Konfigurace služby IIS v [!INCLUDE[iis601](../../../../includes/iis601-md.md)], najdete v části [vynucení ověřování protokolem NTLM](http://go.microsoft.com/fwlink/?LinkId=88598). Pro [!INCLUDE[iisver](../../../../includes/iisver-md.md)], ověřování systému Windows obsahuje ověřování NTLM. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Služby IIS 7.0 Beta: Konfigurace certifikátů serveru ve službě IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=88595).  
  
## <a name="wshttpbinding"></a>WsHttpBinding  
 <xref:System.ServiceModel.WSHttpBinding> Třída je určená pro vzájemná spolupráce pomocí služby, které implementují WS-* specifikace. Zabezpečení přenosu pro tuto vazbu Secure Sockets Layer (SSL) je protokol HTTP nebo HTTPS. Chcete-li vytvořit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace, která používá protokol SSL, který bude hostovat aplikaci používají službu IIS. Případně pokud vytváříte vlastním hostováním aplikací, použijte nástroj HttpCfg.exe pro vazbu certifikátu X.509 konkrétní port, na počítači. Číslo portu je zadaný jako součást [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace jako adresy koncového bodu. Pokud používáte režim přenosu, adresa koncového bodu musí obsahovat protokol HTTPS nebo k výjimce v době běhu. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Zabezpečení přenosu HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Pro ověřování klientů, nastavte <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> vlastnost <xref:System.ServiceModel.HttpTransportSecurity> třída na jednu z <xref:System.ServiceModel.HttpClientCredentialType> hodnot výčtu. Hodnoty výčtu jsou shodné s typy pověření klienta pro <xref:System.ServiceModel.BasicHttpBinding> a jsou navrženy pro hostování s služby IIS.  
  
 Následující příklad ukazuje vazba používá s typu pověření klienta systému Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#11)]
 [!code-vb[c_ProgrammingSecurity#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#11)]  
  
## <a name="wsdualhttpbinding"></a>– WSDualHttpBinding  
 Tuto vazbu poskytuje zabezpečení pouze úroveň zprávy, není transportní vrstvy zabezpečení.  
  
## <a name="nettcpbinding"></a>NetTcpBinding  
 <xref:System.ServiceModel.NetTcpBinding> Třída TCP používá pro přenos zpráv. Zabezpečení pro režim přenosu zajišťuje implementace zabezpečení TLS (Transport Layer) přes protokol TCP. Implementace protokolu TLS zajišťuje operačního systému.  
  
 Můžete také určit typ přihlašovacích údajů klienta nastavením <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> vlastnost <xref:System.ServiceModel.TcpTransportSecurity> třída na jednu z <xref:System.ServiceModel.TcpClientCredentialType> hodnoty, jak je znázorněno v následujícím kódu.  
  
 [!code-csharp[c_ProgrammingSecurity#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#12)]
 [!code-vb[c_ProgrammingSecurity#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#12)]  
  
#### <a name="client"></a>Klient  
 Na klientovi, musíte zadat certifikát pomocí <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> metodu <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> třídy.  
  
> [!NOTE]
>  Pokud používáte zabezpečení systému Windows, certifikát se nevyžaduje.  
  
 Následující kód používá kryptografický otisk certifikátu, která jednoznačně identifikuje. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]certifikáty, najdete v části [práce s certifikáty](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 Můžete taky zadat certifikát v konfiguraci klienta pomocí [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element v části chování.  
  
```xml  
<behaviors>  
  <behavior>  
   <clientCredentials>  
     <clientCertificate findValue= "101010101010101010101010101010000000000"   
      storeLocation="LocalMachine" storeName="My"   
      X509FindType="FindByThumbPrint"/>  
     </clientCertificate>  
   </clientCredentials>  
 </behavior>  
</behaviors>    
```  
  
## <a name="netnamedpipebinding"></a>NetNamedPipeBinding  
 <xref:System.ServiceModel.NetNamedPipeBinding> Třída slouží k efektivní komunikace uvnitř počítače; to znamená, pro procesy spuštění na stejném počítači, i když s názvem kanálu kanály můžete vytvořit mezi dvěma počítači ve stejné síti. Tato vazba poskytuje jenom zabezpečení na úrovni přenosu. Při vytváření aplikace, které používají tuto vazbu, adresy koncových bodů musí obsahovat "net.pipe" jako protokol adresa koncového bodu.  
  
## <a name="wsfederationhttpbinding"></a>– WSFederationHttpBinding  
 Při použití zabezpečení přenosu, této vazby používá protokol SSL přes protokol HTTP, označuje jako HTTPS k tokenu vydaných (<xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential>). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]aplikacemi, najdete v části [federace a vystavené tokeny](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  
 <xref:System.ServiceModel.NetPeerTcpBinding> Třída je zabezpečený přenos, který slouží k efektivní komunikaci pomocí funkce sítě peer-to-peer. Uvádí název třídy a vazbu, je protokol TCP. Když režim zabezpečení je nastavený na přenos, implementuje vazby TLS přes protokol TCP. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]funkci peer-to-peer, najdete v části [Peer-to-Peer sítě](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding a NetMsmqBinding  
 Úplné informace o přenosu zabezpečení pomocí služby Řízení front zpráv (dříve nazývané MSMQ), najdete v části [zabezpečení zabezpečení zprávy přenosu](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md).  
  
## <a name="see-also"></a>Viz také  
 [Programování zabezpečení WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
