---
title: 'Lync Server 2013: Planen der hohen Verfügbarkeit und der Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-31_

Wie in lync Server 2010 basiert das wichtigste Hochverfügbarkeits-Schema für die meisten Serverrollen in lync Server 2013 auf Server Redundanz über Pooling. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.

Lync Server 2013 fügt neue Disaster Recovery-Maßnahmen für Front-End-Pools hinzu, indem geografische dispersement Ihrer Server in zwei Rechenzentren eingeführt werden, um den Service fortzusetzen, wenn ein ganzer Pool oder eine gesamte Website heruntergefahren wird.

Lync Server 2013 verbessert auch die höhere Verfügbarkeit von Back-End-Servern, indem die synchrone SQL-Spiegelung für Ihre Back-End-Datenbankenunter stützt wird.

In diesem Abschnitt werden diese wichtigen Funktionen für hohe Verfügbarkeit und Disaster Recovery erläutert, und es werden auch die Schritte beschrieben, die Sie für eine hohe Verfügbarkeit und Disaster Recovery für Ihre anderen Serverrollen ausführen können.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Notfallwiederherstellung eines Front-End-Pools in Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Notfallwiederherstellung für Edgeserver in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Anrufverwaltungsfunktionen für die Notfallwiederherstellung in Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

