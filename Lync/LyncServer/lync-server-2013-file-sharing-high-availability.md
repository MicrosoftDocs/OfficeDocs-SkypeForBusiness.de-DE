---
title: 'Lync Server 2013: höchst verfügbare Dateifreigabe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="d50ec-102">Höhere Verfügbarkeit von Dateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50ec-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d50ec-103">_**Letztes Änderungsdatum des Themas:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="d50ec-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="d50ec-104">Wenn Sie eine höhere Verfügbarkeit der lync Server-Dateifreigabe in einem einzigen Rechenzentrum sicherstellen möchten, können Sie das verteilte Datei System (Distributed File System, DFS) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d50ec-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="d50ec-105">DFS unterstützt Failover von einem Dateiserver auf einen anderen innerhalb desselben Rechenzentrums.</span><span class="sxs-lookup"><span data-stu-id="d50ec-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="d50ec-106">Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d50ec-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="d50ec-107">Je nach Größe Ihres Netzwerks und dem gewünschten Maß an Flexibilität können Sie mit einem Serverpaar alle Dateifreigaben auf einer Website hosten oder ein paar pro Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="d50ec-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="d50ec-108">Bei DFS handelt es sich um einen Best Effort-Datei Replikationsmechanismus, bei dem keine RTO-oder Recovery Point Objective (RPO)-Zusicherungen veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="d50ec-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="d50ec-109">Das Failover zwischen den DFS-Servern sollte schnell abgeschlossen sein, aber die Daten Replikationsverzögerung kann verhindern, dass Benutzer die Arbeit in Bearbeitung fortsetzen können, wenn das Failover erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d50ec-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="d50ec-110">Wenn Sie DFS verwenden und der Datenspeicher in der FileShare-Datei wichtig ist, sollten Sie die Dateifreigaben häufig sichern, beispielsweise alle 4 bis 8 Stunden.</span><span class="sxs-lookup"><span data-stu-id="d50ec-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="d50ec-111">Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt des ausgefallenen Servers auf dem anderen Server wiederherzustellen, der mit dem jetzt nicht mehr verfügbaren Server kombiniert ist.</span><span class="sxs-lookup"><span data-stu-id="d50ec-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

