---
title: 'Lync Server 2013: Dateispeicherunterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3025534aecb45f230e986016e839af07fe1406cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Dateispeicherunterstützung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Lync Server 2013 verwendet denselben Dateispeicher für alle Dateispeicher. Die Unterstützung für Dateispeicher umfasst Folgendes:

  - Eine Dateifreigabe entweder in Direct Attached Storage (das) oder in einem SAN (Storage Area Network), einschließlich DFS (Distributed File System), und auf einem redundanten Array von unabhängigen Datenträgern (RAID) für Dateispeicher. Details zu den Speicheranforderungen finden Sie unter [Technische Voraussetzungen für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) sowie [Hardware-und Softwareanforderungen für den Director in lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in der Planung. Dokumentation. Ausführliche Informationen zum Betriebssystem DFS für Windows Server 2008 finden Sie in [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)der schrittweisen Anleitung zu DFS für Windows Server 2008 unter.

  - Ein freigegebener Cluster für die Dateifreigabe. Wenn Sie einen freigegebenen Cluster verwenden, sollten Sie Cluster Server mit Windows Server 2008 oder Windows Server 2008 R2 verwenden. Die Verwendung von Clusterservern, auf denen eine ältere Version von Windows ausgeführt wird, kann zu Berechtigungsproblemen führen, die verhindern, dass einige Features verfügbar sind. Verwenden Sie die Cluster Verwaltung, um die Dateifreigaben zu erstellen. Details zur Verwendung des Cluster Administrators finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)Microsoft Knowledge Base-Artikel 284838, "Erstellen einer Server Cluster-Dateifreigabe mit Cluster. exe".

</div>

<span> </span>

</div>

</div>

</div>

