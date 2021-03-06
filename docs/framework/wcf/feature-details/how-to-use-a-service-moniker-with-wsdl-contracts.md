---
title: "Postupy: Použití monikeru služby u kontraktů WSDL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c36ac73ced510c1ba3b7e16c71f764c46d6c8f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>Postupy: Použití monikeru služby u kontraktů WSDL
Pokud chcete mít zcela samostatné klienta zprostředkovatel komunikace s objekty COM, existují situace. Koncový bod MEX a klienta WCF, které pravděpodobně není registrována knihovny DLL pro zprostředkovatel komunikace s objekty COM, nemusí vystavit službu, kterou chcete volat. V těchto případech můžete vytvořit soubor WSDL, který popisuje službu a předejte ji do monikeru služby WCF. Toto téma popisuje, jak volat ukázku získávání spuštění WCF pomocí Přezdívka WCF WSDL.  
  
### <a name="using-the-wsdl-service-moniker"></a>Použití monikeru služby WSDL  
  
1.  Otevření a sestavení GettingStarted ukázkové řešení.  
  
2.  Otevřete Internet Explorer a přejděte k http://localhost/ServiceModelSamples/Service.svc Ujistěte se, že služba funguje.  
  
3.  V souboru Service.cs přidejte následující atribut na třídě CalculatorService:  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4.  Přidáte obor názvů vazbu ke službě App.config:  
  
  
  
5.  Vytvořte soubor WSDL pro aplikace pro čtení. Protože obory názvů byly přidány v krocích 3 a 4, můžete se dotázat na celý popis WSDL služby procházením http://localhost/ServiceModelSamples/Service.svc?wsdl aplikace Internet Explorer. Pak můžete soubor uložte z aplikace Internet Explorer jako serviceWSDL.xml. Pokud nezadáte obory názvů v krocích 3 a 4, nebudou vrácená z dotazu výše uvedenou adresu URL dokumentu WSDL dokončení WSDL. Dokument WSDL vrátil bude obsahovat několik příkazů importu, které import jiné dokumenty WSDL. Je nutné projít každý příkaz import a vytvořit úplný dokument WSDL kombinování WSDL vrácená ze služby s WSDL importovat.  
  
6.  Otevřete Visual Basic 6.0 a vytvořte nový soubor standardní .exe. Přidání tlačítka do formuláře a dvakrát klikněte na tlačítko pro přidání do obslužná rutina kliknutí na následující kód:  
  
    ```  
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    >  Pokud Přezdívka je poškozený nebo pokud služba není dostupná volání `GetObject` se vrátí chyba s oznámením "Neplatná syntaxe".  Pokud se zobrazí tato chyba, ujistěte se, kterou používáte Přezdívka je správný a služba není k dispozici.  
  
7.  Spuštění aplikace Visual Basic. Zobrazí se okno se zprávou s výsledky volání Subtract (145, 76.54).  
  
## <a name="see-also"></a>Viz také  
 [Začínáme](../../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Přehled integrace s aplikacemi modelu COM](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
