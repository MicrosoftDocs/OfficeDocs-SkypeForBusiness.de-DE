---
title: Unterstützung von lync Server 2013 Dateispeicher
description: Lync Server 2013 Unterstützung von Dateispeicher.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03b7c3379c6aad6283f6a55b991ebaec50044bda
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543371"
---
# <a name="file-storage-support-in-lync-server-2013"></a>Unterstützung von Dateispeicher in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-16_

Lync Server 2013 verwendet denselben Dateispeicher für alle Dateispeicher. Die Dateispeicherunterstützung umfasst Folgendes:

  - Eine Dateifreigabe auf einer DAS-Lösung (Direct Attached Storage) oder auf einer SAN-Lösung (Storage Area Network), einschließlich DFS (Distributed File System), sowie auf einem RAID (Redundant Array of Independent Disks) für Dateispeicher. Ausführliche Informationen zu den Speicheranforderungen finden Sie unter [Technische Anforderungen für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) sowie [Hardware-und Softwareanforderungen für den Director in lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in der Planungsdokumentation. Ausführliche Informationen zu DFS für Windows Server 2008 Betriebssystem finden Sie in der schrittweisen Anleitung zu DFS für Windows Server 2008 unter [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) .

  - Einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie einen freigegebenen Cluster verwenden, sollten Sie Clusterserver mit Windows Server 2008 oder Windows Server 2008 R2 verwenden. Das Verwenden von Clusterservern mit einer älteren Version von Windows kann zu Berechtigungsproblemen führen, die verhindern, dass einige Features verfügbar sind. Verwenden Sie die Clusterverwaltung, um die Dateifreigaben zu erstellen. Ausführliche Informationen zur Verwendung der Cluster Verwaltung finden Sie im Microsoft Knowledge Base-Artikel 284838, "Erstellen einer Server Cluster-Dateifreigabe mit Cluster.exe" unter [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899) .

</div>

<span> </span>

</div>

</div>

</div>

