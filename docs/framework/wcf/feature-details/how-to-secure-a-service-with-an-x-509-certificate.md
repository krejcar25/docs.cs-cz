---
title: "Postupy: Zabezpečení služby certifikátem X.509"
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
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e1ad7cd844ffbd3f45517f7d812ad3f5fa1ae3c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a>Postupy: Zabezpečení služby certifikátem X.509
Zabezpečení služby certifikátem X.509 je základní technika, většina vazeb v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] použít. Toto téma vás provede kroky konfigurace služba s vlastním hostováním společně s certifikátem X.509.  
  
 Předpokladem je platný certifikát, který slouží k ověření serveru. Certifikát musí být k serveru vydán důvěryhodnou certifikační autoritou. Pokud certifikát platný není, všechny klient pokouší použít službu nebude důvěřovat služby a v důsledku toho budou provedeny žádné připojení. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]pomocí certifikátů, najdete v tématu [práce s certifikáty](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a>Pro konfiguraci služby pomocí certifikátu pomocí kódu  
  
1.  Vytvoření kontraktu služby a implementovaná službu. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Navrhování a implementace služeb](../../../../docs/framework/wcf/designing-and-implementing-services.md).  
  
2.  Vytvoření instance <xref:System.ServiceModel.WSHttpBinding> třídy a nastavte režim zabezpečení na <xref:System.ServiceModel.SecurityMode.Message>, jak je znázorněno v následujícím kódu.  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3.  Vytvořte dvě <xref:System.Type> proměnné, jednu pro typ smlouvy a implementovaná kontrakt, jak je znázorněno v následujícím kódu.  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4.  Vytvoření instance <xref:System.Uri> třídy pro bázovou adresu služby. Protože `WSHttpBinding` používá přenos HTTP, identifikátor URI (Uniform Resource) musí začínat řetězcem schématu, nebo [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] vyvolá výjimku při otevření službu.  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5.  Vytvořit novou instanci třídy <xref:System.ServiceModel.ServiceHost> se proměnná typu implementovaná kontraktu a identifikátor URI.  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6.  Přidat <xref:System.ServiceModel.Description.ServiceEndpoint> služby pomocí <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> metoda. Předejte kontrakt, vazbu a adresu koncového bodu do konstruktoru, jak je znázorněno v následujícím kódu.  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7.  Volitelné. Načtení metadat ze služby, vytvořte novou <xref:System.ServiceModel.Description.ServiceMetadataBehavior> objektu a nastavte <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> vlastnost `true`.  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8.  Použití <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> metodu <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> třída přidat platný certifikát pro službu. Metodu můžete použít některou z několika metod se najít certifikát. Tento příklad používá <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> výčtu. Výčet Určuje, že zadaná hodnota je název sady entit, který certifikát byl vydán.  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. Volání <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> metoda zahájit naslouchání služby. Pokud vytvoříte konzolovou aplikaci, zavolejte <xref:System.Console.ReadLine%2A> metoda zachovat služby ve stavu naslouchání.  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a>Příklad  
 Následující příklad používá <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> metoda pro konfiguraci služby pomocí certifikátu X.509.  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Následující obory názvů jsou nezbytné pro kompilaci kódu:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.Web.Services.Description>  
  
-   <xref:System.Security.Cryptography.X509Certificates>  
  
-   <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a>Viz také  
 [Práce s certifikáty](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
