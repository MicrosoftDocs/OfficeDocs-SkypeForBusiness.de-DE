---
title: 'Lync Server 2013: höchst verfügbare Dateifreigabe'
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
ms.openlocfilehash: f67fc8cfffc0b5dbecaf6da212b3a8e5414b18ef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Höhere Verfügbarkeit von Dateien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-03-30_

Wenn Sie eine höhere Verfügbarkeit der lync Server-Dateifreigabe in einem einzigen Rechenzentrum sicherstellen möchten, können Sie das verteilte Datei System (Distributed File System, DFS) verwenden. DFS unterstützt Failover von einem Dateiserver auf einen anderen innerhalb desselben Rechenzentrums. Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden.

Je nach Größe Ihres Netzwerks und dem gewünschten Maß an Flexibilität können Sie mit einem Serverpaar alle Dateifreigaben auf einer Website hosten oder ein paar pro Front-End-Pool verwenden.

Bei DFS handelt es sich um einen Best Effort-Datei Replikationsmechanismus, bei dem keine RTO-oder Recovery Point Objective (RPO)-Zusicherungen veröffentlicht werden. Das Failover zwischen den DFS-Servern sollte schnell abgeschlossen sein, aber die Daten Replikationsverzögerung kann verhindern, dass Benutzer die Arbeit in Bearbeitung fortsetzen können, wenn das Failover erfolgt.

Wenn Sie DFS verwenden und der Datenspeicher in der FileShare-Datei wichtig ist, sollten Sie die Dateifreigaben häufig sichern, beispielsweise alle 4 bis 8 Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt des ausgefallenen Servers auf dem anderen Server wiederherzustellen, der mit dem jetzt nicht mehr verfügbaren Server kombiniert ist.

</div>

<span> </span>

</div>

</div>

</div>

