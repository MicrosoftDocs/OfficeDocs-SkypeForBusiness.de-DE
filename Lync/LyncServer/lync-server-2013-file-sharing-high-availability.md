---
title: 'Lync Server 2013: hohe Verfügbarkeit von Dateifreigaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453b4c63f58f6153092dae0259155dbfa72b5eca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="ac293-102">Hohe Verfügbarkeit der Dateifreigabe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac293-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac293-103">_**Letztes Änderungsstand des Themas:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="ac293-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="ac293-104">Um eine hohe Verfügbarkeit für lync Server Dateifreigabe in einem einzelnen Rechenzentrum sicherzustellen, können Sie das verteilte Datei System (DFS) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac293-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="ac293-105">DFS unterstützt Failover von einem Dateiserver auf einen anderen Dateiserver innerhalb des gleichen Rechenzentrums.</span><span class="sxs-lookup"><span data-stu-id="ac293-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="ac293-106">Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="ac293-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="ac293-107">Abhängig von der Größe Ihres Netzwerks und der gewünschten Ausfallsicherheit können Sie ein Serverpaar zum Hosten von sämtlichen Dateifreigaben eines Standorts oder ein Paar je Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac293-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="ac293-p102">DFS ist ein "Best Effort"-Mechanismus für die Dateireplikation ohne veröffentlichte Zusagen für Wiederherstellungszeit (Recovery Time Objective - RTO) oder Wiederherstellungspunkt (Recovery Point Objective - RPO). Der Failover zwischen den DFS-Servern sollte schnell abgeschlossen werden, jedoch kann eine Verzögerung bei der Datenreplikation verhindern, dass Benutzer ihre laufende Arbeit fortsetzen können, wenn der Failover auftritt.</span><span class="sxs-lookup"><span data-stu-id="ac293-p102">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment. The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="ac293-p103">Wenn Sie DFS verwenden und Datenspeicher bei der Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben öfters speichern, zum Beispiel alle vier bis acht Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt auf dem ausgefallenen Server auf den anderen Server wiederherzustellen, der mit dem Server kombiniert ist, welcher jetzt nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ac293-p103">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

