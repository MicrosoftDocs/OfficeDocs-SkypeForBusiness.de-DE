---
title: 'Lync Server 2013: Anrufsteuerung und Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Anrufsteuerung und Vermittlungsserver in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die Anrufannahme Steuerung (CAC), die erstmals in lync Server 2010 eingeführt wurde, verwaltet die Echtzeit-Sitzungseinrichtung auf der Grundlage der verfügbaren Bandbreite, um zu verhindern, dass Benutzer in überlasteten Netzwerken eine schlechte Arbeitsqualität (QoE) erzielen. Zur Unterstützung dieser Funktion ist der Vermittlungs Server, der eine Signalisierungs-und Medienübersetzung zwischen der Enterprise-VoIP-Infrastruktur und einem Gateway-oder SIP-Trunking-Anbieter bereitstellt, für die Bandbreitenverwaltung für die beiden Interaktionen in lync verantwortlich. Server seitig und auf der Einstiegsseite. Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung. Die Gateway-Peers (PSTN-Gateway, IP-PBX, SBC), mit denen der Vermittlungsserver auf der Einstiegsseite interagiert, unterstützen keine lync Server 2013-Anrufsteuerung. Daher muss der Vermittlungs Server Bandbreiten Interaktionen im Auftrag seines Gateway-Peers verarbeiten. Wenn möglich, reserviert der Vermittlungs Server im Voraus eine Bandbreite. Wenn dies nicht möglich ist (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert. Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.

Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus. Wenn für einen Anruf eine medienumgehung verwendet wird, wird für diesen Anruf keine Anrufsteuerung durchgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden. Wenn die Anrufsteuerung für einen bestimmten Anruf verwendet wird, der den Vermittlungs Server einbezieht, kann dieser Anruf keine medienumgehung verwenden.

Details zur medienumgehung oder zur Anrufsteuerung finden Sie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) oder [Planen der Anrufsteuerung in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

