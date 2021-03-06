---
title: "Pokud není k nasazení do systému Windows kontejnery"
description: "Architektura Mikroslužeb .NET pro aplikace .NET Kontejnerizované | Pokud není k nasazení do systému Windows kontejnery"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c74b71f9c80ab51cabe0e3c4abf32f292da30763
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/23/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Pokud není k nasazení do systému Windows kontejnery

Některé technologie systému Windows nepodporuje kontejnery systému Windows. V takových případech musíte stále migraci virtuálních počítačů standardy, obvykle s pouze systém Windows a služby IIS.

Nepodporované ve Windows kontejnery od mid 2017 případech:

-   Microsoft služby Řízení front zpráv (MSMQ) není aktuálně podporována v kontejnerech Windows.

    -   [Fórum požadavek UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Diskusní fórum](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Microsoft Distributed Transaction Coordinator služba MSDTC () aktuálně není podporována v systému Windows kontejnery

    -   [Problém Githubu](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Aplikace Microsoft Office aktuálně nepodporuje kontejnery

    -   [Fórum požadavek UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

Další-nepodporované scénáře a požadavky od komunity, najdete v části UserVoice fórum pro Windows kontejnery: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Další zdroje

-   **Virtuální počítače a kontejnerů v Azure**

    [https://docs.microsoft.com/Azure/Virtual-Machines/Windows/Containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Předchozí](deploy-existing-net-apps-as-windows-containers.md)
[další](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
