---
title: "Přístup ke službám pomocí klienta WCF"
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
helpviewer_keywords: clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f33d64e9ec1881b1ef7b93ba29d233f2f580c29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-services-using-a-wcf-client"></a>Přístup ke službám pomocí klienta WCF
Po vytvoření služby je dalším krokem je vytvoření [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proxy serveru klienta. Klientská aplikace používá [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proxy serveru klienta ke komunikaci se službou. Klientské aplikace obvykle importovat metadata služby pro generování [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kód klienta, který slouží k vyvolání služby.  
  
 Základní kroky pro vytváření [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klienta zahrnují následující:  
  
1.  Kompilace kódu služby.  
  
2.  Vygenerovat [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proxy serveru klienta.  
  
3.  Vytvoří instanci proxy serveru klienta WCF.  
  
 Proxy server klienta WCF může být generována ručně v nástroji Service modelu Metadata Utility (SvcUtil.exe) pro další informace najdete [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Proxy server klienta WCF lze vygenerovat také v sadě Visual Studio pomocí funkce Přidat odkaz na službu. Ke generování proxy serveru klienta WCF pomocí některé z metod služby musí být spuštěna. Pokud služba se hostuje sama je nutné spustit hostitele. Pokud je služba hostovaná ve službě IIS / není potřeba dělat žádné další kroky.  
  
## <a name="servicemodel-metadata-utility-tool"></a>Nástroj ServiceModel Metadata Utility  
 [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) je nástroj příkazového řádku pro generování kódu z metadat. Použijte následující je příklad základní Svcutil.exe příkazu.  
  
```  
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
```  
  
 Alternativně můžete Svcutil.exe webové služby popis Language (WSDL) a schématu XML soubory s definicemi jazyk (XSD) v systému souborů.  
  
```  
Svcutil.exe <list of WSDL and XSD files on file system>  
```  
  
 Výsledkem je soubor kód, který obsahuje [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kód klienta, který klientská aplikace můžete použít k vyvolání služby.  
  
 Můžete taky nástroj pro generování konfigurační soubory.  
  
```  
Svcutil.exe <file1 [,file2]>  
```  
  
 Pokud jenom jeden název souboru není uveden, který je název výstupního souboru. Pokud jsou dva názvy souborů, první soubor je soubor vstupní konfigurace, jejichž obsah je sloučen s vygenerované konfigurace a zapíše do druhého pole. [!INCLUDE[crabout](../../../includes/crabout-md.md)]konfigurace, najdete v části [Konfigurace vazeb pro služby](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).  
  
> [!IMPORTANT]
>  Požadavků na metadata zabezpečená představovat určité rizika stejným způsobem, který nemá žádnou nezabezpečené síti žádostí: Pokud si nejste jisti, že koncový bod komunikuje se kdo ho informacemi o tom je, můžete načíst informace může být metadata z škodlivý služby.  
  
## <a name="add-service-reference-in-visual-studio"></a>Přidání odkazu služby v sadě Visual Studio  
 Služba spuštěna, klikněte pravým tlačítkem na projekt, který bude obsahovat proxy serveru klienta WCF a zvolte **přidat odkaz na službu**. V **dialogové okno Přidat odkaz na služby** zadejte adresu URL služby, kterou chcete volat a klikněte na tlačítko **přejděte** tlačítko. Dialogové okno se zobrazí seznam služeb, které jsou k dispozici na adrese, které zadáte. Dvakrát klikněte na službu, naleznete v kontraktech a operací, které jsou k dispozici, zadejte obor názvů pro generovaný kód a klikněte na **OK** tlačítko.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje kontraktu služby vytvořené pro službu.  
  
```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```
  
```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```
  
 Nástroj ServiceModel Metadata nástroj a přidat odkaz na službu v sadě Visual Studio generuje následující [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] třída klienta. Třídy dědí z obecná <xref:System.ServiceModel.ClientBase%601> třídy a implementuje `ICalculator` rozhraní. Nástroj vytvoří také `ICalculator` rozhraní (není tady zobrazené).  
  
```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```  
  
```vb  
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```
  
## <a name="using-the-wcf-client"></a>Pomocí klienta WCF  
 Použít [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klienta, vytvořte instanci [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klienta a pak zavolají její metody, jak je znázorněno v následujícím kódu.  
  
```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```
  
```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```
  
## <a name="debugging-exceptions-thrown-by-a-client"></a>Ladění výjimky vyvolané klienta  
 Mnoho výjimky vyvolané [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klienta jsou způsobeny výjimku ve službě. Příkladem takových jsou:  
  
-   <xref:System.Net.Sockets.SocketException>: Stávající připojení bylo vzdáleným hostitelem nuceně uzavřeno.  
  
-   <xref:System.ServiceModel.CommunicationException>: Základní připojení bylo ukončeno neočekávaně.  
  
-   <xref:System.ServiceModel.CommunicationObjectAbortedException>: Připojení soketu bylo přerušeno. Příčinou může být k chybě při zpracování zprávy, vypršení časového limitu příjmu, překročení vzdáleného hostitele nebo základní problém síťových prostředků.  
  
 Pokud dojde k těchto typů výjimek, je nejlepší způsob, jak problém vyřešit zapnutím trasování na straně služby a zjistit, jaké výjimky došlo k chybě došlo. [!INCLUDE[crabout](../../../includes/crabout-md.md)]trasování, najdete v části [trasování](../../../docs/framework/wcf/diagnostics/tracing/index.md) a [pomocí trasování řešení vaše aplikace](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření klienta](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Postupy: Přístup ke službám pomocí duplexního kontraktu](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [Postupy: Asynchronní volání operací služby](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)  
 [Postupy: Přístup ke službám pomocí jednosměrných kontraktů a kontraktů žádost-odpověď](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)  
 [Postupy: Přístup ke službě WSE 3.0](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)  
 [Principy generovaného klientského kódu](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)  
 [Postupy: Vylepšení doby spouštění klientských aplikací WCF pomocí XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)  
 [Nastavení chování klienta za běhu](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [Konfigurace chování klienta](../../../docs/framework/wcf/configuring-client-behaviors.md)
