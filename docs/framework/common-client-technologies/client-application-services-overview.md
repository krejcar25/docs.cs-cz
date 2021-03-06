---
title: "Přehled klientských aplikačních služeb"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client application services, classes
- client application services, about client application services
ms.assetid: f0a2da13-e282-4fd7-88a1-f9102c9aeab1
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55b4ab154f9f3a9b17274697c30ca826218322ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="client-application-services-overview"></a>Přehled klientských aplikačních služeb
Klient aplikačních služeb poskytují zjednodušenou přístup k [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] přihlášení, rolí a profilu služby z aplikací Windows Forms a Windows Presentation Foundation (WPF). [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]aplikace služby jsou součástí Microsoft ASP.NET 2.0 AJAX rozšíření, která je součástí [!INCLUDE[vs_orcas_long](../../../includes/vs-orcas-long-md.md)] a [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)]. Tyto služby umožňují více Web a aplikace pro systém Windows sdílet informace o uživateli a správu uživatelů funkci z jednoho serveru.  
  
 Klient aplikačních služeb zahrnují poskytovatelé služeb klienta, které se připojí k model rozšíření webových služeb k povolení následujících funkcí pro aplikace založené na systému Windows:  
  
-   Konfigurace jednoduchého klienta. Můžete povolit a nakonfigurovat přihlašovací údaje, rolí a profilu služby pomocí [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] projektu návrháře nebo zadáním poskytovatelé služeb klienta v souboru App.config vašeho projektu. Další informace najdete v tématu [postupy: Konfigurace klientských aplikačních služeb](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
-   Jednoduché programovatelnosti. Po povolené a nakonfigurované klientské aplikační služby, poskytovatelé služeb přístup nepřímo prostřednictvím existující [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] členství, role a třídy nastavení aplikace. Můžete také přímo přistupovat [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] třídy, které implementují klientské aplikační služby. Ve většině případů je však nepotřebné přímý přístup. Další informace o třídách služby klienta aplikace najdete v části "Třídy klienta aplikace služby" v tomto tématu.  
  
-   Podporu offline režimu. Aplikace pro systém Windows mají často pracovat v příležitostně připojených prostředích. Pokud vaše aplikace je online, poskytovatelů služeb klienta mezipaměti hodnoty získané ze serveru pro použití, když je aplikace do režimu offline.  
  
-   Integrace s [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] návrháře nastavení aplikací. Když přidáte do projektu v nastavení [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], můžete zadat nastavení, které se mají přistupovat prostřednictvím poskytovatele služeb nastavení klienta.  
  
 Následující části popisují tyto funkce podrobněji. Další informace o [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] aplikační služby, najdete v části [aplikace ASP.NET: Přehled služby](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).  
  
## <a name="authentication"></a>Ověřování  
 Klient aplikačních služeb můžete použít k ověření uživatele prostřednictvím existující [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] ověřovací služby. Uživatele můžete ověřit pomocí ověřování systému Windows nebo formuláře. Ověřování systému Windows znamená, že identita uživatele se s klíčem dodaným v operačním systému, když se uživatel přihlásí do počítače nebo domény. Obvykle použijete ověřování systému Windows pomocí aplikace pro nasazení v podnikovém intranetu. Ověřování pomocí formulářů znamená, že musí zahrnovat přihlašovací ovládací prvky v aplikaci a předávat získal přihlašovací údaje pro zprostředkovatele ověřování. Obvykle použijete ověřování pomocí formulářů s aplikace nasazené na Internetu.  
  
 Chcete-li ověřit uživatele, zavolejte `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> metoda. Tato metoda přistupuje k poskytovateli služby klienta nakonfigurovaný pro vaše aplikace a vrátí <xref:System.Boolean> hodnotu, která určuje, zda uživatel je platný. Další informace najdete v tématu [postupy: implementace přihlášení uživatele u klientských aplikačních služeb](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md).  
  
 Pokud používáte ověřování systému Windows, je nutné předat prázdné řetězce nebo `null` jako parametry <xref:System.Web.Security.Membership.ValidateUser%2A> metoda. Pokud používáte ověřování systému Windows, toto volání metody vždy vrátí `true`.  
  
 Pomocí ověřování pomocí formulářů <xref:System.Web.Security.Membership.ValidateUser%2A> metoda vrátí hodnotu, která určuje, zda vzdálené služby ověření uživatele. Pokud je ověření úspěšné, soubor cookie ověřování je uložený na místním pevném disku. Tento soubor cookie se používá k potvrzení ověření při přístupu k role a nastavení služby.  
  
 Pokud používáte ověřování pomocí formulářů, můžete předat uživatelské jméno a heslo k <xref:System.Web.Security.Membership.ValidateUser%2A> metoda. Můžete předat také prázdné řetězce nebo `null` jako parametry pro použití poskytovatele přihlašovacích údajů. Přihlašovací údaje poskytovatele je třída, která poskytují a zadejte v konfiguraci vaší aplikace. Musí implementovat třídu poskytovatele přihlašovacích údajů <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> rozhraní, které obsahuje jedinou metodu s názvem <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>. Pomocí poskytovatele pověření umožňuje sdílet jeden přihlašovací dialogové okno mezi více aplikacemi. Další informace najdete v tématu [postupy: Konfigurace klientských aplikačních služeb](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
 Při konfiguraci vaší aplikace pro použití poskytovatele přihlašovacích údajů se ověřování pomocí formulářů, je nutné předat prázdné řetězce nebo `null` jako parametry <xref:System.Web.Security.Membership.ValidateUser%2A> metoda. Pak zavolá poskytovatele služeb vaší <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType> implementace metod. Obvykle bude Implementujte tuto metodu zobrazit dialogové okno a vrátíte se vyplněná <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> objektu.  
  
 Další informace o ověřování najdete v tématu [ověřování pomocí technologie ASP.NET](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1). Informace o tom, jak nastavit [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] Služba ověřování najdete v části [použití ověřování pomocí formulářů s Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e).  
  
## <a name="roles"></a>Role  
 Klient aplikačních služeb můžete použít k načtení informací o rolích ze stávajícího [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] služby rolí. Chcete-li zjistit, zda je aktuální, ověřený uživatel v konkrétní roli, zavolejte <xref:System.Security.Principal.IPrincipal.IsInRole%2A> metodu <xref:System.Security.Principal.IPrincipal> z načíst odkaz `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> vlastnost. <xref:System.Security.Principal.IPrincipal.IsInRole%2A> Metoda přebírá jako parametr název role a vrátí <xref:System.Boolean> hodnotu, která určuje, zda má aktuální uživatel je v zadané roli. Tato metoda vrátí `false` Pokud uživatel není ověřen nebo není v zadané roli.  
  
 Informace o tom, jak nastavit [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] služby rolí, najdete v části [pomocí rolí informací pomocí Microsoft Ajax](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d).  
  
## <a name="settings"></a>Nastavení  
 Klient aplikačních služeb můžete použít k načtení nastavení uživatele aplikace z existující [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] profilu služby. Klient aplikačních služeb, funkce nastavení webu integruje s funkcí nastavení aplikace, který je součástí [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)]. Pokud chcete načíst nastavení webu, nejprve generovat `Settings` – třída (přístup jako `Properties.Settings.Default` v jazyce C# a `My.Settings` v [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) pro váš projekt pomocí **nastavení** kartě [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Návrhář projektu. Na **nastavení** kartě, můžete použít **zatížení nastavení webové** tlačítko Načíst nastavení webu a přidat je do vygenerovaného `Settings` třídy. Můžete použít nastavení webové nakonfigurovaný na používání všem ověřeným uživatelům nebo všichni anonymní uživatelé.  
  
 Další informace o nastavení aplikace najdete v tématu [přehled nastavení aplikace](../../../docs/framework/winforms/advanced/application-settings-overview.md). Informace o tom, jak implementovat vlastní třída nastavení, místo aby generovala v [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], najdete v části [postupy: vytvoření nastavení aplikace](../../../docs/framework/winforms/advanced/how-to-create-application-settings.md). Informace o tom, jak nastavit [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] profilu služby najdete v tématu [pomocí informací o profilu s Microsoft Ajax](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61).  
  
## <a name="client-application-services-classes"></a>Klientská aplikace služby třídy  
 Následující tabulka popisuje třídy, které implementují funkce klienta aplikace služby.  
  
 Aplikace, které používají pouze primární ověřování, rolí a funkcí nastavení nebude mít přístup k tyto třídy přímo. Místo toho tyto aplikace budou přistupovat k poskytovatelů služeb aplikací klienta nepřímo pomocí konfigurace aplikace a rozhraní API popsané v předchozích částech. Budete přistupovat k tyto třídy přímo k implementaci další funkce, jako je například odhlášení uživatele a v režimu offline.  
  
> [!NOTE]
>  Všechny klientské aplikační služby rozhraní API jsou synchronní. Klient aplikačních služeb přímo nepodporují asynchronní chování.  
  
 Poskytovatelů služeb aplikací klienta implementovat nebo rozšířit standard [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] typy, ale nezadávejte není implementace každý člen a funkce definované tyto typy. Poskytovatelů služeb aplikací klienta nelze například použít k implementaci správu uživatelů aplikace pro vytváření nových uživatelů a správu členství role. Pokud chcete tuto funkci implementovat, musíte použít aktuálně webové aplikace a kódu na straně serveru. Pokud chcete zjistit, kteří členové nejsou implementované, najdete v dokumentaci odkaz, kterým můžete přistupovat z odkazy v této tabulce.  
  
|Třída|Popis|  
|-----------|-----------------|  
|<xref:System.Web.ClientServices.ClientFormsIdentity>|Tato třída spravuje uživatele identit a ověření souborů cookie pro ověřování pomocí formulářů.<br /><br /> Hlavním důvodem k přímý přístup Tato třída je volat <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> metodu, která bezobslužně revalidates uživatele (například při přepnutí z offline na online režim).<br /><br /> Po ověření uživatele pomocí ověřování pomocí formulářů můžete načíst instance této třídy prostřednictvím <xref:System.Security.Principal.IPrincipal.Identity%2A> vlastnost <xref:System.Security.Principal.IPrincipal> odkaz získat pomocí `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> vlastnost.|  
|<xref:System.Web.ClientServices.ClientRolePrincipal>|Tato třída spravuje role uživatelů.<br /><br /> Tato třída nemá žádné členy, které nebudou přístupné nepřímo. Po ověření uživatele, můžete však přístup instance této třídy prostřednictvím `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> vlastnost.|  
|<xref:System.Web.ClientServices.ConnectivityStatus>|Tato třída poskytuje `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> vlastnost, která slouží k přepínači vaší aplikace do režimu offline.|  
|<xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>|Tato třída reprezentuje přihlašovací údaje uživatele.<br /><br /> Tato třída bude používat pouze jako návratová hodnota typ <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> metoda při implementaci <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> rozhraní.|  
|<xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>|Tato třída spravuje přístup ke službě vzdálené ověření pro ověřování pomocí formulářů.<br /><br /> Hlavním důvodem k přímý přístup Tato třída je použití jeho <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> a <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.UserValidated> členy, které nejsou implementované základní <xref:System.Web.Security.MembershipProvider> třídy. Můžete také nastavit umístění služby programově pomocí <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.ServiceUri%2A> vlastnost.<br /><br /> Můžete načíst instance této třídy prostřednictvím `static` <xref:System.Web.Security.Membership.Provider%2A?displayProperty=nameWithType> vlastnost.|  
|<xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>|Tato třída slouží ke správě ověřování systému Windows.<br /><br /> Hlavním důvodem k přímý přístup Tato třída je volat jeho <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider.Logout%2A> metoda. Po odhlášení uživatel bude ověřen stále pro Windows, ale nebude možné získat přístup ke službám vzdálené aplikace.<br /><br /> Můžete načíst instance této třídy prostřednictvím `static` <xref:System.Web.Security.Membership.Provider%2A?displayProperty=nameWithType> vlastnost.|  
|<xref:System.Web.ClientServices.Providers.ClientRoleProvider>|Tato třída spravuje přístup ke službě vzdálené role.<br /><br /> Hlavním důvodem pro přístup k této třídy je volat jeho <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ResetCache%2A> metoda. To může být užitečné, pokud vaše aplikace je nakonfigurovaný na použití hodnotu časového limitu mezipaměti služby role nulová. Další informace najdete v tématu [postupy: Konfigurace klientských aplikačních služeb](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md). Můžete také nastavit umístění služby programově pomocí <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ServiceUri%2A> vlastnost.<br /><br /> Můžete načíst instance této třídy prostřednictvím `static` <xref:System.Web.Security.Roles.Provider%2A?displayProperty=nameWithType> vlastnost.|  
|<xref:System.Web.ClientServices.Providers.ClientSettingsProvider>|Tato třída spravuje přístup k vzdálené webové nastavení služby.<br /><br /> Hlavním důvodem pro přístup k této třídy je zpracování <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> událostí. Můžete také nastavit umístění služby programově pomocí <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.ServiceUri%2A> vlastnost.|  
|<xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>|Toto rozhraní umožňuje nepřímých způsobem pro vaši aplikaci získat přihlašovací údaje uživatele pro ověření, jak je popsáno výše v části ověření v tomto tématu. Další informace najdete v tématu [postupy: Konfigurace klientských aplikačních služeb](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).|  
|<xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>|Tato třída poskytuje <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs.FailedSettingsList%2A> vlastnost pro použití v rámci <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> obslužné rutiny události.|  
|<xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>|Tato třída poskytuje <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs.UserName%2A> vlastnost pro použití v rámci <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.UserValidated> obslužné rutiny události.|  
  
## <a name="see-also"></a>Viz také  
 [Klientské aplikační služby](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Postupy: Konfigurace klientských aplikačních služeb](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [Postupy: Implementace přihlášení uživatele u klientských aplikačních služeb](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 [Návod: Použití klientských aplikačních služeb](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [Přehled nastavení aplikace](../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [Přehled služby aplikace ASP.NET](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [Použití ověřování pomocí formulářů s technologií Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [Pomocí informací o rolí s technologií Microsoft Ajax](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [Informace o profilu pomocí Microsoft Ajax](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [Ověřování pomocí technologie ASP.NET](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 [Řízení autorizací pomocí rolí](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  
 [Vytváření a konfiguraci databázi aplikace služby systému SQL Server](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)
