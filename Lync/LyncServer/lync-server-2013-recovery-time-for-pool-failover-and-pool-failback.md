---
title: Lync Server 2013 Wiederherstellungszeit für Pool-Failover und Pool-Failback
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb165fa762b23bd271dde56c0846ccb18adfbf7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Wiederherstellungszeit für Pool-Failover und Pool-Failback in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-10_

Für Pool-Failover und Pool-Failback liegt das Entwicklungsziel für das Recovery Time Objective (RTO) bei 30 Minuten. Dies ist die Zeit, die erforderlich ist, bis das Failover stattfindet, nachdem Administratoren festgestellt haben, dass ein Notfall vorliegt, und die Failover-Prozeduren initiiert haben. Hierin ist die Zeit, die Administratoren für die Bewertung der Situation und die Entscheidungsfindung benötigen, nicht enthalten. Auch nicht enthalten ist die Zeit, die Benutzer nach Abschluss des Failovers für die Anmeldung benötigen.

Für Pool-Failover und Pool-Failback liegt das Entwicklungsziel für das Recovery Time Objective (RTO) bei 30 Minuten. Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Backupdienstes verloren gehen können. Wenn ein Pool beispielsweise um 10:00 Uhr ausfällt und der RPO-Wert 30 Minuten beträgt, werden die Daten zwischen 9:30 Uhr in den Pool geschrieben. und 10:00 A. M. wurde möglicherweise nicht in den Sicherungspool repliziert und würde verloren gehen.

Bei allen RTO-und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass sich die beiden Rechenzentren in der gleichen Weltregion mit einem Transport mit hoher Geschwindigkeit und niedriger Latenz zwischen den beiden Standorten befinden. Diese Nummern werden für einen Pool mit 40.000 gleichzeitig aktiven Benutzern und 200.000 für lync aktivierten Benutzern im Hinblick auf ein vordefiniertes Benutzermodell gemessen, bei dem kein Rückstand in der Datenreplikation vorliegt. Sie können auf der Grundlage von Leistungstests und Überprüfung Änderungen unterliegen.

</div>

<span> </span>

</div>

</div>

</div>

