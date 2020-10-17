---
title: 'Lync Server 2013: Planen der hohen Verfügbarkeit und Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a44a3b5f83814bf4d4b975dc8f9d548661294e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522112"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-31_

Wie in lync Server 2010 basiert das Hauptsystem für hohe Verfügbarkeit für die meisten Serverrollen in lync Server 2013 auf der Serverredundanz über das Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers. Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.

Lync Server 2013 fügt neue Notfall Wiederherstellungsmaßnahmen für Front-End-Pools hinzu, indem die geografische Verteilung Ihrer Server in zwei Rechenzentren eingeführt wird, um den Dienst fortzusetzen, wenn ein ganzer Pool oder eine gesamte Website ausfällt.

Lync Server 2013 verbessert auch die hohe Verfügbarkeit von Back-End-Servern, indem die synchrone SQL-Spiegelung für Ihre Back-End-Datenbankenunter stützt wird.

In diesem Abschnitt werden diese wichtigen Features für hohe Verfügbarkeit und Notfallwiederherstellung erläutert. Zudem wird erklärt, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für Ihre anderen Serverrollen ausführen können.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Front-End-Pool Notfallwiederherstellung in lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Edgeserver Notfallwiederherstellung in lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Anrufverwaltungsfunktionen für die Notfallwiederherstellung in lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Ausfallsicherheit für lync Server 2010 Metropole-Standort](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

