---
title: "Postupy: Přístup ke službám WCF pomocí jednosměrných kontraktů a kontraktů požadavek-odpověď"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e10d3a5-fcf4-4a4b-a8d6-92ee2c988b3b
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 20d9cad52c0f528b521b031173b5dce1cb4f2a50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-access-wcf-services-with-one-way-and-request-reply-contracts"></a><span data-ttu-id="e4269-102">Postupy: Přístup ke službám WCF pomocí jednosměrných kontraktů a kontraktů požadavek-odpověď</span><span class="sxs-lookup"><span data-stu-id="e4269-102">How to: Access WCF Services with One-Way and Request-Reply Contracts</span></span>
<span data-ttu-id="e4269-103">Následující postupy popisují, jak získat přístup [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] služby jednosměrného kontraktu a kontraktů požadavek odpověď, který definuje a která nepoužívá vzoru duplexní komunikace.</span><span class="sxs-lookup"><span data-stu-id="e4269-103">The following procedures describe how to access a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that defines a one-way contract and a request-reply contract and that does not use the duplex communication pattern.</span></span>  
  
### <a name="to-define-the-service"></a><span data-ttu-id="e4269-104">Chcete-li definovat službu</span><span class="sxs-lookup"><span data-stu-id="e4269-104">To define the service</span></span>  
  
1.  <span data-ttu-id="e4269-105">Deklarujte kontrakt služby.</span><span class="sxs-lookup"><span data-stu-id="e4269-105">Declare the service contract.</span></span> <span data-ttu-id="e4269-106">Operace, které mají být jednosměrná musí mít `IsOneWay` nastavena na `true` v rámci <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e4269-106">The operations that are to be one-way must have `IsOneWay` set to `true` within the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="e4269-107">Následující kód deklaruje `IOneWayCalculator` smlouvu, která má jednosměrný operací pro `Add`, `Subtract`, `Multiply`, a `Divide`.</span><span class="sxs-lookup"><span data-stu-id="e4269-107">The following code declares the `IOneWayCalculator` contract that has one-way operations for `Add`, `Subtract`, `Multiply`, and `Divide`.</span></span> <span data-ttu-id="e4269-108">Definuje také operace odpovědi žádost o názvem `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="e4269-108">It also defines a request response operation called `SayHello`.</span></span>  
  
    ```csharp  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface IOneWayCalculator  
    {  
        [OperationContract(IsOneWay = true)]  
        void Add(double n1, double n2);  
        [OperationContract(IsOneWay = true)]  
        void Subtract(double n1, double n2);  
        [OperationContract(IsOneWay = true)]  
        void Multiply(double n1, double n2);  
        [OperationContract(IsOneWay = true)]  
        void Divide(double n1, double n2);  
        [OperationContract]  
        string SayHello(string name);  
    }  
    ```  
  
2.  <span data-ttu-id="e4269-109">Implementujte kontrakt služby.</span><span class="sxs-lookup"><span data-stu-id="e4269-109">Implement the service contract.</span></span> <span data-ttu-id="e4269-110">Následující kód implementuje `IOnewayCalculator` rozhraní.</span><span class="sxs-lookup"><span data-stu-id="e4269-110">The following code implements the `IOnewayCalculator` interface.</span></span>  
  
    ```csharp  
    [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.PerCall)]  
    public class CalculatorService : IOneWayCalculator  
    {  
        public void Add(double n1, double n2)  
        {  
           double result = n1 + n2;  
           Console.WriteLine("Add({0},{1}) = {2} ", n1, n2, result);  
        }  
  
        public void Subtract(double n1, double n2)  
        {  
           double result = n1 - n2;  
           Console.WriteLine("Subtract({0},{1}) = {2}", n1, n2, result);  
        }  
  
        public void Multiply(double n1, double n2)  
        {  
            double result = n1 * n2;  
            Console.WriteLine("Multiply({0},{1}) = {2}", n1, n2, result);  
        }  
  
        public void Divide(double n1, double n2)  
        {  
            double result = n1 / n2;  
            Console.WriteLine("Divide({0},{1}) = {2}", n1, n2, result);  
        }  
  
        public string SayHello(string name)  
        {  
            Console.WriteLine("SayHello({0})", name);  
            return "Hello " + name;  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="e4269-111">Hostovat službu v konzolové aplikaci.</span><span class="sxs-lookup"><span data-stu-id="e4269-111">Host the service in a console application.</span></span> <span data-ttu-id="e4269-112">Následující kód ukazuje, jak k hostování služby.</span><span class="sxs-lookup"><span data-stu-id="e4269-112">The following code shows how to host the service.</span></span>  
  
    ```csharp  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
       // Define the base address for the service.  
       Uri baseAddress = new Uri("http://localhost:8000/servicemodelsamples/service");  
  
       // Create a ServiceHost for the CalculatorService type and provide the base address.  
       using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))  
       {  
            // Add an endpoint using the IOneWayCalculator contract and the WSHttpBinding  
            serviceHost.AddServiceEndpoint(typeof(IOneWayCalculator), new WSHttpBinding(), "");  
  
          // Turn on the metadata behavior, this allows svcutil to get metadata for the service.  
          ServiceMetadataBehavior smb = (ServiceMetadataBehavior) serviceHost.Description.Behaviors.Find<ServiceMetadataBehavior>();  
          if (smb == null)  
          {  
                smb = new ServiceMetadataBehavior();  
                smb.HttpGetEnabled = true;  
                serviceHost.Description.Behaviors.Add(smb);  
          }  
  
          // Open the ServiceHostBase to create listeners and start listening for messages.  
          serviceHost.Open();  
  
          // The service can now be accessed.  
          Console.WriteLine("The service is ready.");  
          Console.WriteLine("Press <ENTER> to terminate service.");  
          Console.WriteLine();  
          Console.ReadLine();  
        }  
    }  
    ```  
  
### <a name="to-access-the-service"></a><span data-ttu-id="e4269-113">Přístup ke službě</span><span class="sxs-lookup"><span data-stu-id="e4269-113">To access the service</span></span>  
  
1.  <span data-ttu-id="e4269-114">Spustit [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) pomocí adresa koncového bodu metadat systému exchange pro vytvoření třídy klienta pro službu pomocí následující příkazový řádek: `Svcutil http://localhost:8000/Service` [ServiceModel Nástroj pro metadata Utility (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generuje sadu rozhraní a třídy, jak je znázorněno v následujícím ukázkovém kódu.</span><span class="sxs-lookup"><span data-stu-id="e4269-114">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) using the metadata exchange endpoint address to create the client class for the service using the following command line: `Svcutil http://localhost:8000/Service` The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generates a set of interfaces and classes, as shown in the following sample code.</span></span>  
  
    ```csharp  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
    [System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.ServiceModel.Samples", ConfigurationName="IOneWayCalculator")]  
    public interface IOneWayCalculator  
    {  
  
        [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.ServiceModel.Samples/IOneWayCalculator/Add")]  
        void Add(double n1, double n2);  
  
        [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.ServiceModel.Samples/IOneWayCalculator/Subtract")]  
        void Subtract(double n1, double n2);  
  
        [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.ServiceModel.Samples/IOneWayCalculator/Multiply")]  
        void Multiply(double n1, double n2);  
  
        [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.ServiceModel.Samples/IOneWayCalculator/Divide")]  
        void Divide(double n1, double n2);  
  
        [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/IOneWayCalculator/SayHello", ReplyAction="http://Microsoft.ServiceModel.Samples/IOneWayCalculator/SayHelloResponse")]  
        string SayHello(string name);  
    }  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
    public interface IOneWayCalculatorChannel : IOneWayCalculator, System.ServiceModel.IClientChannel  
    {  
    }  
  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
    public partial class OneWayCalculatorClient : System.ServiceModel.ClientBase<IOneWayCalculator>, IOneWayCalculator  
    {  
  
        public OneWayCalculatorClient()  
        {  
        }  
  
        public OneWayCalculatorClient(string endpointConfigurationName) :   
                base(endpointConfigurationName)  
        {  
        }  
  
        public OneWayCalculatorClient(string endpointConfigurationName, string remoteAddress) :   
                base(endpointConfigurationName, remoteAddress)  
        {  
        }  
  
        public OneWayCalculatorClient(string endpointConfigurationName, System.ServiceModel.EndpointAddress remoteAddress) :   
                base(endpointConfigurationName, remoteAddress)  
        {  
        }  
  
        public OneWayCalculatorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress remoteAddress) :   
                base(binding, remoteAddress)  
        {  
        }  
  
        public void Add(double n1, double n2)  
        {  
            base.Channel.Add(n1, n2);  
        }  
  
        public void Subtract(double n1, double n2)  
        {  
            base.Channel.Subtract(n1, n2);  
        }  
  
        public void Multiply(double n1, double n2)  
        {  
            base.Channel.Multiply(n1, n2);  
        }  
  
        public void Divide(double n1, double n2)  
        {  
            base.Channel.Divide(n1, n2);  
        }  
  
        public string SayHello(string name)  
        {  
            return base.Channel.SayHello(name);  
        }  
    }  
    ```  
  
     <span data-ttu-id="e4269-115">Všimněte si v `IOneWayCalculator` rozhraní, které mají operací jednosměrné služby <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> atribut nastaven na `true` a operace služby požadavku a odpovědi má nastaven na výchozí hodnotu, atribut `false`.</span><span class="sxs-lookup"><span data-stu-id="e4269-115">Notice in the `IOneWayCalculator` interface that the one-way service operations have the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> attribute set to `true` and the request-reply service operation has the attribute set to the default value, `false`.</span></span> <span data-ttu-id="e4269-116">Všimněte si také `OneWayCalculatorClient` třídy.</span><span class="sxs-lookup"><span data-stu-id="e4269-116">Also notice the `OneWayCalculatorClient` class.</span></span> <span data-ttu-id="e4269-117">Toto je třída, která budete používat pro volání služby.</span><span class="sxs-lookup"><span data-stu-id="e4269-117">This is the class that you will use to call the service.</span></span>  
  
2.  <span data-ttu-id="e4269-118">Vytvořte objekt klienta.</span><span class="sxs-lookup"><span data-stu-id="e4269-118">Create the client object.</span></span>  
  
    ```csharp  
    // Create a client  
    WSHttpBinding binding = new WSHttpBinding();  
    EndpointAddress epAddress = new EndpointAddress("http://localhost:8000/servicemodelsamples/service");  
    OneWayCalculatorClient client = new OneWayCalculatorClient(binding, epAddress);  
    ```  
  
3.  <span data-ttu-id="e4269-119">Volání operací služby.</span><span class="sxs-lookup"><span data-stu-id="e4269-119">Call service operations.</span></span>  
  
    ```csharp  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1})", value1, value2);  
  
    // Call the Subtract service operation.  
    value1 = 145.00D;  
    value2 = 76.54D;  
    client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1})", value1, value2);  
  
    // Call the Multiply service operation.  
    value1 = 9.00D;  
    value2 = 81.25D;  
    client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1})", value1, value2);  
  
    // Call the Divide service operation.  
    value1 = 22.00D;  
    value2 = 7.00D;  
    client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1})", value1, value2);  
  
    // Call the SayHello service operation  
    string name = "World";  
    string response = client.SayHello(name);  
    Console.WriteLine("SayHello([0])", name);  
    Console.WriteLine("SayHello() returned: " + response);  
    ```  
  
4.  <span data-ttu-id="e4269-120">Zavřete klientovi ukončit připojení a vyčištění prostředků.</span><span class="sxs-lookup"><span data-stu-id="e4269-120">Close the client to close connections and clean up resources.</span></span>  
  
    ```csharp  
    //Closing the client gracefully closes the connection and cleans up resources  
    client.Close();  
    ```  
  
## <a name="example"></a><span data-ttu-id="e4269-121">Příklad</span><span class="sxs-lookup"><span data-stu-id="e4269-121">Example</span></span>  
 <span data-ttu-id="e4269-122">Níže je úplný seznam všech kód použitý v tomto tématu.</span><span class="sxs-lookup"><span data-stu-id="e4269-122">The following is a complete listing of the code used  in this topic.</span></span>  
  
```csharp  
// Service.cs  
using System;  
using System.Configuration;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    // Define a service contract.   
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface IOneWayCalculator  
    {  
        [OperationContract(IsOneWay = true)]  
        void Add(double n1, double n2);  
        [OperationContract(IsOneWay = true)]  
        void Subtract(double n1, double n2);  
        [OperationContract(IsOneWay = true)]  
        void Multiply(double n1, double n2);  
        [OperationContract(IsOneWay = true)]  
        void Divide(double n1, double n2);  
        [OperationContract]  
        string SayHello(string name);  
    }  
  
    // Service class which implements the service contract.  
    // Added code to write output to the console window  
    [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.PerCall)]  
    public class CalculatorService : IOneWayCalculator  
    {  
        public void Add(double n1, double n2)  
        {  
            double result = n1 + n2;  
            Console.WriteLine("Add({0},{1}) = {2} ", n1, n2, result);  
        }  
  
        public void Subtract(double n1, double n2)  
        {  
            double result = n1 - n2;  
            Console.WriteLine("Subtract({0},{1}) = {2}", n1, n2, result);  
        }  
  
        public void Multiply(double n1, double n2)  
        {  
            double result = n1 * n2;  
            Console.WriteLine("Multiply({0},{1}) = {2}", n1, n2, result);  
        }  
  
        public void Divide(double n1, double n2)  
        {  
            double result = n1 / n2;  
            Console.WriteLine("Divide({0},{1}) = {2}", n1, n2, result);  
        }  
  
        public string SayHello(string name)  
        {  
            Console.WriteLine("SayHello({0})", name);  
            return "Hello " + name;  
        }  
  
        // Host the service within this EXE console application.  
        public static void Main()  
        {  
            // Define the base address for the service.  
            Uri baseAddress = new Uri("http://localhost:8000/servicemodelsamples/service");  
  
            // Create a ServiceHost for the CalculatorService type and provide the base address.  
            using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))  
            {  
                // Add an endpoint using the IOneWayCalculator contract and the WSHttpBinding  
                serviceHost.AddServiceEndpoint(typeof(IOneWayCalculator), new WSHttpBinding(), "");  
  
                // Turn on the metadata behavior, this allows svcutil to get metadata for the service.  
                ServiceMetadataBehavior smb = (ServiceMetadataBehavior) serviceHost.Description.Behaviors.Find<ServiceMetadataBehavior>();  
                if (smb == null)  
                {  
                    smb = new ServiceMetadataBehavior();  
                    smb.HttpGetEnabled = true;  
                    serviceHost.Description.Behaviors.Add(smb);  
                }  
  
                // Open the ServiceHostBase to create listeners and start listening for messages.  
                serviceHost.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
            }  
        }  
    }  
} 
```

```csharp
// client.cs  
using System;  
using System.ServiceModel;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    //The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.  
  
    //Client implementation code.  
    class Client  
    {  
        static void Main()  
        {  
            // Create a client  
            WSHttpBinding binding = new WSHttpBinding();  
            EndpointAddress epAddress = new EndpointAddress("http://localhost:8000/servicemodelsamples/service");  
            OneWayCalculatorClient client = new OneWayCalculatorClient(binding, epAddress);  
  
            // Call the Add service operation.  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
            client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1})", value1, value2);  
  
            // Call the Subtract service operation.  
            value1 = 145.00D;  
            value2 = 76.54D;  
            client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1})", value1, value2);  
  
            // Call the Multiply service operation.  
            value1 = 9.00D;  
            value2 = 81.25D;  
            client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1})", value1, value2);  
  
            // Call the Divide service operation.  
            value1 = 22.00D;  
            value2 = 7.00D;  
            client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1})", value1, value2);  
  
            // Call the SayHello service operation  
            string name = "World";  
            string response = client.SayHello(name);  
            Console.WriteLine("SayHello([0])", name);  
            Console.WriteLine("SayHello() returned: " + response);  
            //Closing the client gracefully closes the connection and cleans up resources  
            client.Close();  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4269-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="e4269-123">See Also</span></span>  
 [<span data-ttu-id="e4269-124">Jednosměrné služby</span><span class="sxs-lookup"><span data-stu-id="e4269-124">One-Way Services</span></span>](../../../../docs/framework/wcf/feature-details/one-way-services.md)