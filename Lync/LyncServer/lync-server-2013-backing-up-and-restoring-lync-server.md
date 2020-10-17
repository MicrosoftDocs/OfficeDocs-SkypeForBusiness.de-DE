---
title: 'Lync Server 2013: Sichern und Wiederherstellen lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947035af0021090596348b1aab873c60b930e00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532732"
---
# <a name="backing-up-and-restoring-lync-server-2013"></a>Sichern und Wiederherstellen lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

In diesem Abschnitt finden Sie die bewährten Methoden zum Sichern Ihrer lync Server 2013 Daten sowie zum Wiederherstellen bei einem Fehler. Diese bewährten Methoden gelten für die folgenden Situationen:

  - Ein ganzer lync Server Pool eines beliebigen Typs (Front-End-Server, Edgeserver, Vermittlungsserver, beständiger Chat Server oder Director) oder ein einzelner Server in einem dieser Pools.

  - Der zentrale Verwaltungs Server

  - Ein Standard Edition-Server

  - Ein Enterprise Edition-Back-End-Server

  - Ein Dateispeicher

  - Eine Datenbank für Archivierungsdatenbank, Überwachungsdatenbank oder beständigen Chat

Dieser Abschnitt enthält keine Informationen zum Wiederherstellen einer gesamten Website oder zum Entwickeln einer Standby-Website. Ausführliche Informationen zum Entwickeln einer Notfallwiederherstellungslösung mit gepaarten Front-End-Pools finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Dies ist die empfohlene Methode für die Planung der Notfallwiederherstellung.

Wenn Sie gekoppelte Front-End-Pools bereitgestellt haben und einer dieser Pools fehlschlägt und nicht mehr wiederhergestellt werden kann, können Sie diesen Pool mit einem neuen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) aus dem gekoppelten Pool wiederherstellen. Ausführliche Informationen zu den Schritten zum Durchführen dieser Wiederherstellung finden Sie unter [failing over a Pool in lync Server 2013](lync-server-2013-failing-over-a-pool.md). Wenn Sie später einen fehlerhaften und nicht behebbaren Pool erneut erstellen möchten, der Teil eines Front-End-Paars war, können Sie die Schritte unter [Durchführen eines ABC-Front-End-Pool-Failovers in lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md)verwenden.

Bei der hier beschriebenen Methodik werden besondere Überlegungen während der Planungsphase mit berücksichtigt. Ausführliche Informationen finden Sie unter [Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Vorbereiten der lync Server 2013 Sicherung und-Wiederherstellung](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Sichern von Daten und Einstellungen in lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Wiederherstellen von Daten und Einstellungen in lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Arbeitsblätter zur Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

