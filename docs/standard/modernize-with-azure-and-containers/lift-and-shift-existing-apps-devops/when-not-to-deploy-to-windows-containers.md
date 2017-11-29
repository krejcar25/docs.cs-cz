---
title: "Pokud není k nasazení do systému Windows kontejnery"
description: "Architektura Mikroslužeb .NET pro aplikace .NET Kontejnerizované | Pokud není k nasazení do systému Windows kontejnery"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 538cb518cd169f42b3e8b7324ca108a1d366137a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="2a76e-103">Pokud není k nasazení do systému Windows kontejnery</span><span class="sxs-lookup"><span data-stu-id="2a76e-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="2a76e-104">Některé technologie systému Windows nepodporuje kontejnery systému Windows.</span><span class="sxs-lookup"><span data-stu-id="2a76e-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="2a76e-105">V takových případech musíte stále migraci virtuálních počítačů standardy, obvykle s pouze systém Windows a služby IIS.</span><span class="sxs-lookup"><span data-stu-id="2a76e-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="2a76e-106">Nepodporované ve Windows kontejnery od mid 2017 případech:</span><span class="sxs-lookup"><span data-stu-id="2a76e-106">Cases not supported in Windows Containers, as of mid-2017:</span></span>

-   <span data-ttu-id="2a76e-107">Microsoft služby Řízení front zpráv (MSMQ) není aktuálně podporována v kontejnerech Windows.</span><span class="sxs-lookup"><span data-stu-id="2a76e-107">Microsoft Message Queuing (MSMQ) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="2a76e-108">Fórum požadavek UserVoice</span><span class="sxs-lookup"><span data-stu-id="2a76e-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="2a76e-109">Diskusní fórum</span><span class="sxs-lookup"><span data-stu-id="2a76e-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="2a76e-110">Microsoft Distributed Transaction Coordinator služba MSDTC () aktuálně není podporována v systému Windows kontejnery</span><span class="sxs-lookup"><span data-stu-id="2a76e-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers</span></span>

    -   [<span data-ttu-id="2a76e-111">Problém Githubu</span><span class="sxs-lookup"><span data-stu-id="2a76e-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="2a76e-112">Aplikace Microsoft Office aktuálně nepodporuje kontejnery</span><span class="sxs-lookup"><span data-stu-id="2a76e-112">Microsoft Office currently does not support containers</span></span>

    -   [<span data-ttu-id="2a76e-113">Fórum požadavek UserVoice</span><span class="sxs-lookup"><span data-stu-id="2a76e-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

<span data-ttu-id="2a76e-114">Další-nepodporované scénáře a požadavky od komunity, najdete v části UserVoice fórum pro Windows kontejnery: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="2a76e-114">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="2a76e-115">Další zdroje</span><span class="sxs-lookup"><span data-stu-id="2a76e-115">Additional resources</span></span>

-   <span data-ttu-id="2a76e-116">**Virtuální počítače a kontejnerů v Azure**</span><span class="sxs-lookup"><span data-stu-id="2a76e-116">**Virtual machines and containers in Azure**</span></span>

    [<span data-ttu-id="2a76e-117">https://docs.microsoft.com/Azure/Virtual-Machines/Windows/Containers</span><span class="sxs-lookup"><span data-stu-id="2a76e-117">https://docs.microsoft.com/azure/virtual-machines/windows/containers</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="2a76e-118">[Předchozí](deploy-existing-net-apps-as-windows-containers.md)
[další](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="2a76e-118">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>