---
title: 'Lync Server 2013: Neue Funktionen für Notfallwiederherstellung und hohe Verfügbarkeit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Neue Funktionen für Notfallwiederherstellung und hohe Verfügbarkeit in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-20_

Wie in lync Server 2010 basiert das Hauptsystem für hohe Verfügbarkeit (ha) für lync Server 2013 auf Server Redundanz über Pooling. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.

Lync Server 2013 fügt neue Wiederherstellungsmaßnahmen für Notfälle hinzu, indem es Ihnen ermöglicht, Front-End-Pools in zwei Rechenzentren zu koppeln. Wenn eines der gekoppelten Pools ausfällt, kann ein Administrator die Benutzer aus diesem Pool mit dem anderen Pool des Paars Failover, um die Fortsetzung des Diensts zu gewährleisten. Für diese Funktionalität sind keine kostspieligen Netzwerk-oder Hardwarelösungen wie Speichernetzwerke oder freigegebene Datenträger erforderlich.

Lync Server 2013 fügt auch eine höhere Verfügbarkeit für den Back-End-Server hinzu. Hierbei handelt es sich um eine optionale Topologie, in der Sie zwei Back-End-Server für einen Front-End-Pool bereitstellen und die synchrone SQL-Spiegelung für alle lync-Datenbankeneinrichten, die auf den Back-End-Servern ausgeführt werden. Sie können auswählen, ob Sie einen Zeugen für den Spiegel bereitstellen möchten.

<div>

## <a name="see-also"></a>Siehe auch


[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

