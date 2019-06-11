---
title: 'Lync Server 2013: Sichern und Wiederherstellen von lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0cf9f9baabd095e54373c31acd4f4522974a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Sichern und Wiederherstellen von lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In diesem Abschnitt finden Sie die bewährten Methoden zum Sichern Ihrer lync Server 2013-Daten sowie zum Wiederherstellen bei einem Fehler. Diese bewährten Methoden gelten für die folgenden Situationen:

  - Ein gesamter lync Server-Pool eines beliebigen Typs (Front-End-Server, Edgeserver, Vermittlungsserver, beständiger Chat Server oder Director) oder ein einzelner Server in einem dieser Pools.

  - Der zentrale Verwaltungs Server

  - Ein Standard Edition-Server

  - Ein Enterprise Edition-Back-End-Server

  - Ein Dateispeicher

  - Eine Archivierungsdatenbank, eine Überwachungsdatenbank oder eine persistente Chat Datenbank

Dieser Abschnitt enthält keine Informationen zum Wiederherstellen einer gesamten Website oder zur Entwicklung einer Standby-Website. Details zur Entwicklung einer Disaster Recovery-Lösung mit gekoppelten Front-End-Pools finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Dies ist die empfohlene Methode für die Planung der Notfallwiederherstellung.

Wenn Sie gekoppelte Front-End-Pools bereitgestellt haben, können Sie diesen Pool mit einem neuen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) aus dem gekoppelten Pool wiederherstellen, wenn eines dieser Pools ausfällt und nicht wiederhergestellt werden kann. Ausführliche Informationen zu den Schritten zum Durchführen dieser Wiederherstellung finden Sie unter [Failover eines Pools in lync Server 2013](lync-server-2013-failing-over-a-pool.md). Wenn Sie später einen fehlerhaften und nicht behebbaren Pool erstellen möchten, der Teil eines Front-End-Paars war, können Sie die Schritte unter [Durchführen eines Failovers des ABC-Front-End-Pools in lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md)verwenden.

Die in diesem Dokument beschriebene Methodik umfasst besondere Aspekte in der Planungsphase. Ausführliche Informationen finden Sie unter [Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Vorbereiten der Sicherung und Wiederherstellung von lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Sichern von Daten und Einstellungen in lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Wiederherstellen von Daten und Einstellungen in lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Arbeitsblätter zum Sichern und Wiederherstellen für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

