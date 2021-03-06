---
title: TCP UDP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f62475e8b44d9cdda13322dc223509572c4ae541
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="tcp-udp"></a>TCP UDP
Aplikace můžete použít protokol TCP (Transmission Control) a protokolu UDP (User Datagram) služby pomocí <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, a <xref:System.Net.Sockets.UdpClient> třídy. Tyto třídy protokolu jsou postavený na <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> třídy a postará o podrobnosti o přenosu dat.  
  
 Třídy protokol použít synchronní metody sady **soketu** třídy poskytují jednoduchá a přímočará přístup k síťovým službám bez nutnosti zachování informací o stavu nebo znát podrobnosti o nastavení sokety specifické pro protokol. Použít asynchronní **soketu** metod, můžete použít asynchronní metody poskytl <xref:System.Net.Sockets.NetworkStream> třídy. Pro přístup k funkcím z **soketu** třídy nejsou viditelné protocol třídami, je nutné použít **soketu** – třída.  
  
 **TcpClient** a **TcpListener** představují síti pomocí **NetworkStream** třídy. Můžete použít <xref:System.Net.Sockets.TcpClient.GetStream%2A> má metoda vrátit datový proud sítě a pak zavolají datový proud <xref:System.Net.Sockets.NetworkStream.Read%2A> a <xref:System.Net.Sockets.NetworkStream.Write%2A> metody. **NetworkStream** nevlastní protokol třídy základní soketu, takže zavřením nemá vliv na soket.  
  
 **UdpClient** třída používá pro uložení datagramů UDP pole bajtů. Můžete použít <xref:System.Net.Sockets.UdpClient.Send%2A> metodu pro odeslání dat do sítě a <xref:System.Net.Sockets.UdpClient.Receive%2A> metodu datagramu příchozí.  
  
## <a name="see-also"></a>Viz také  
 [Použití služeb TCP](../../../docs/framework/network-programming/using-tcp-services.md)  
 [Použití služeb UDP](../../../docs/framework/network-programming/using-udp-services.md)  
 [Použití streamů v síti](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [Použití asynchronního serverového soketu](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [Použití asynchronního klientského soketu](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [Použití aplikačních protokolů](../../../docs/framework/network-programming/using-application-protocols.md)
