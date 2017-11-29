---
title: "Aspekty hostování ovládacího prvku ActiveX ve formuláři Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3ec828ca0b2bd8231d0baca72bf97bef566f2651
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a><span data-ttu-id="ad896-102">Aspekty hostování ovládacího prvku ActiveX ve formuláři Windows</span><span class="sxs-lookup"><span data-stu-id="ad896-102">Considerations When Hosting an ActiveX Control on a Windows Form</span></span>
<span data-ttu-id="ad896-103">I když Windows Forms jsou optimalizovány na hostitele Windows Forms – ovládací prvky, můžete dál používat ovládací prvky ActiveX.</span><span class="sxs-lookup"><span data-stu-id="ad896-103">Although Windows Forms have been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="ad896-104">Při plánování aplikace, která používá ovládací prvky ActiveX, mít na paměti následující aspekty:</span><span class="sxs-lookup"><span data-stu-id="ad896-104">Keep the following considerations in mind when planning an application that uses ActiveX controls:</span></span>  
  
-   <span data-ttu-id="ad896-105">**Zabezpečení** modul common language runtime se rozšířily s ohledem na zabezpečení přístupu kódu.</span><span class="sxs-lookup"><span data-stu-id="ad896-105">**Security** The common language runtime has been enhanced with regard to code access security.</span></span> <span data-ttu-id="ad896-106">U aplikací s Windows Forms můžete spustit v plně důvěryhodný pro prostředí bez problém a v případě polovičním důvěryhodného prostředí s většinou funkcí, které jsou dostupné.</span><span class="sxs-lookup"><span data-stu-id="ad896-106">Applications featuring Windows Forms can run in a fully trusted environment without issue and in a semi-trusted environment with most of the functionality accessible.</span></span> <span data-ttu-id="ad896-107">Ovládací prvky Windows Forms může být hostovaný v prohlížeči se žádné komplikace.</span><span class="sxs-lookup"><span data-stu-id="ad896-107">Windows Forms controls can be hosted in a browser with no complications.</span></span> <span data-ttu-id="ad896-108">V rozhraní Windows Forms – ovládací prvky ActiveX nelze však využít výhod těchto vylepšení zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="ad896-108">However, ActiveX controls on Windows Forms cannot take advantage of these security enhancements.</span></span> <span data-ttu-id="ad896-109">Používání ovládacího prvku ActiveX vyžaduje oprávnění nespravovaného kódu, který je nastaven s <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="ad896-109">Running an ActiveX control requires unmanaged code permission, which is set with the <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ad896-110">Další informace o zabezpečení a oprávnění nespravovaného kódu najdete v tématu <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ad896-110">For more information about security and unmanaged code permission, see <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span></span>  
  
-   <span data-ttu-id="ad896-111">**Celkové náklady na vlastnictví** ovládací prvky ActiveX přidán do formuláře Windows jsou nasazeny pomocí tohoto formuláře Windows jako celek, které můžete přidat výrazně velikost souborů vytvořit.</span><span class="sxs-lookup"><span data-stu-id="ad896-111">**Total Cost of Ownership** ActiveX controls added to a Windows Form are deployed with that Windows Form in their entirety, which can add significantly to the size of the file(s) created.</span></span> <span data-ttu-id="ad896-112">Použití ovládacích prvků ActiveX v rozhraní Windows Forms navíc vyžaduje zápis do registru.</span><span class="sxs-lookup"><span data-stu-id="ad896-112">Additionally, using ActiveX controls on Windows Forms requires writing to the registry.</span></span> <span data-ttu-id="ad896-113">To je na počítači uživatele než ovládací prvky Windows Forms, které se to nevyžaduje.</span><span class="sxs-lookup"><span data-stu-id="ad896-113">This is more invasive to a user's computer than Windows Forms controls, which do not require this.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ad896-114">Práce s prvku ActiveX ovládacího prvku vyžaduje použití Obálka zprostředkovatele komunikace s objekty COM.</span><span class="sxs-lookup"><span data-stu-id="ad896-114">Working with an ActiveX control requires the use of a COM interop wrapper.</span></span> <span data-ttu-id="ad896-115">Další informace najdete v tématu [interoperabilita modelů COM v jazyce Visual Basic a Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ad896-115">For more information, see [COM Interoperability in Visual Basic and Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ad896-116">Pokud název člena ovládacího prvku ActiveX odpovídá názvu definované v [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], pak bude import ovládacích prvků ActiveX předpony název člena s **Ctl** při vytvoří <xref:System.Windows.Forms.AxHost> odvozené třídy.</span><span class="sxs-lookup"><span data-stu-id="ad896-116">If the name of a member of the ActiveX control matches a name defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], then the ActiveX Control Importer will prefix the member name with **Ctl** when it creates the <xref:System.Windows.Forms.AxHost> derived class.</span></span> <span data-ttu-id="ad896-117">Například, pokud má vlastní ovládací prvek ActiveX člen s názvem **rozložení**, bude přejmenován **CtlLayout** ve třídě odvozené AxHost protože **rozložení** událost je definována v rámci [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad896-117">For example, if your ActiveX control has a member named **Layout**, it is renamed **CtlLayout** in the AxHost-derived class because the **Layout** event is defined within the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad896-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="ad896-118">See Also</span></span>  
 [<span data-ttu-id="ad896-119">Postupy: Přidání ovládacích prvků ActiveX do formulářů Windows</span><span class="sxs-lookup"><span data-stu-id="ad896-119">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="ad896-120">Zabezpečení přístupu kódu</span><span class="sxs-lookup"><span data-stu-id="ad896-120">Code Access Security</span></span>](../../../../docs/framework/misc/code-access-security.md)  
 [<span data-ttu-id="ad896-121">Ovládací prvky a programovatelný objekty porovnání v různých jazycích a knihovny</span><span class="sxs-lookup"><span data-stu-id="ad896-121">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="ad896-122">Umístění ovládacích prvků ve formulářích Windows</span><span class="sxs-lookup"><span data-stu-id="ad896-122">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="ad896-123">Ovládací prvky Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad896-123">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)