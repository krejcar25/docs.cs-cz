---
title: "Postupy: nastavení zásad na základě umístění mezipaměti pro aplikaci"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expliciting defining cache behavior
- location-based cache policies
- local cache
- request cache policies
- cache [.NET Framework], location-based policies
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9d54a34b5d7cf40a6eaa9d777b9b05a1be34f177
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a>Postupy: nastavení zásad na základě umístění mezipaměti pro aplikaci
Na základě umístění mezipaměti zásady umožňují aplikace explicitně definujte chování ukládání do mezipaměti na základě umístění požadovaného prostředku. Toto téma popisuje nastavení zásad mezipaměti prostřednictvím kódu programu. Informace o nastavení zásad pro aplikaci pomocí konfiguračních souborů najdete v tématu [ \<requestCaching – > elementu (nastavení sítě)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a>Nastavení zásad na základě umístění mezipaměti pro aplikaci  
  
1.  Vytvoření <xref:System.Net.Cache.RequestCachePolicy> nebo <xref:System.Net.Cache.HttpRequestCachePolicy> objektu.  
  
2.  Objekt zásad nastavte jako výchozí pro doménu aplikace.  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a>Nastavení zásad, která přebírá požadované prostředky z mezipaměti  
  
-   Vytvořit zásadu, která přebírá požadované prostředky z mezipaměti, pokud je k dispozici a jinak, zasílá požadavky na server, nastavením mezipaměti na úrovni <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>. Žádost o lze splnit všechny mezipaměti mezi klientem a serverem, včetně vzdálené mezipamětí.  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a>Chcete-li nastavit zásady, které brání žádné mezipaměti poskytuje prostředky  
  
-   Vytvořit zásadu, která brání poskytnutí požadované prostředky podle nastavení úrovně do mezipaměti žádné mezipaměti <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>. Tato úroveň zásad odebere zdroj z místní mezipaměti, pokud je přítomen a označuje vzdálené mezipamětí, že se mělo odstranit také prostředku.  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a>Nastavení zásad, který vrací požadované prostředky, pouze pokud jsou v místní mezipaměti  
  
-   Vytvořit zásadu, která vrátí požadované prostředky, pouze pokud jsou v místní mezipaměti podle nastavení úrovně do mezipaměti <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>. Pokud požadovaný prostředek není v mezipaměti, <xref:System.Net.WebException> je vyvolána výjimka.  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a>Chcete-li nastavit zásady, které brání poskytuje prostředky místní mezipaměti  
  
-   Vytvořit zásadu, která brání poskytnutí požadované prostředky podle nastavení úrovně do mezipaměti v místní mezipaměti <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>. Pokud požadovaný prostředek je v zprostředkující mezipaměti a znovu je úspěšně ověřeny, zprostředkující mezipaměti můžete poskytnout požadovaný prostředek.  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a>Nastavení zásad, který brání poskytuje všechny mezipaměti požadované prostředky  
  
-   Vytvořit zásadu, která brání poskytnutí požadované prostředky podle nastavení úrovně do mezipaměti žádné mezipaměti <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>. Prostředek vrácená serverem mohou být uloženy v mezipaměti.  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a>Nastavení zásad, která umožňuje všechny mezipaměti k poskytování požadované prostředky, pokud prostředek na daném serveru není novější než kopie uložené v mezipaměti  
  
-   Vytvořit zásadu, která umožňuje všechny mezipaměti k poskytování požadované prostředky, pokud prostředek na daném serveru není novější než kopie uložené v mezipaměti nastavení mezipaměti na úrovni <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Správa mezipaměti pro síťové aplikace](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [Zásady mezipaměti](../../../docs/framework/network-programming/cache-policy.md)  
 [Zásady mezipaměti na základě místa](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [Zásady mezipaměti na základě času](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [\<requestCaching – > elementu (nastavení sítě)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
