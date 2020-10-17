---
title: Lync Server 2013 Failover des zentralen Verwaltungsspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508042"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a>Failover des zentralen Verwaltungsspeichers in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Der zentrale Verwaltungsspeicher enthält Konfigurationsdaten zu Servern und Diensten in ihrer lync 2013-Bereitstellung. Es bietet eine robuste, schematisierten Speicherung der Daten, die für die Definition, Einrichtung, Verwaltung, Verwaltung, Beschreibung und den Betrieb einer lync 2013-Bereitstellung benötigt werden. Darüber hinaus werden die Daten überprüft, um eine konsistente Konfiguration zu gewährleisten.

Jede lync-Bereitstellung umfasst einen zentralen Verwaltungsspeicher, der vom Back-End-Server eines Front-End-Pool gehostet wird.

Wenn Sie eine Pool Kopplung einrichten, die den Pool enthält, der den zentralen Verwaltungsspeicher hostet, wird eine Sicherungsdatenbank für den zentralen Verwaltungsspeicher im Sicherungspool eingerichtet, und die Dienste für den zentralen Verwaltungsspeicher werden in beiden Pools installiert. Eine der beiden Datenbanken des zentralen Verwaltungsspeichers ist zu jedem Zeitpunkt der aktive Master und der andere ein Standby. Der Inhalt wird vom Sicherungsdienst vom aktiven Master in den Standbymodus repliziert.

Während eines Pool Failovers, in dem sich die Pools befinden, die den zentralen Verwaltungsspeicher hosten, muss der Administrator vor dem Failover des Front-End-Pool einen Failover des zentralen Verwaltungsspeichers ausführen.

Nachdem der Notfall repariert wurde, ist es nicht erforderlich, den zentralen Verwaltungsspeicher zurück zu schlagen. Nach der Reparatur kann der zentrale Verwaltungsspeicher im ursprünglichen Sicherungspool als aktiver Master-Manager beibehalten werden.

Die Entwicklungsziele für das Failover des zentralen Verwaltungsspeichers sind 5 Minuten für die Wiederherstellungszeit (Recovery Time Objective, RTO) und 5 Minuten für RPO (Recovery Points Objective).

</div>

<span> </span>

</div>

</div>

</div>

