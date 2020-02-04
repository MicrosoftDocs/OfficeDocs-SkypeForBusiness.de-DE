---
title: 'Lync Server 2013: Bereitstellen von Zweigstellen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: facfda5d1d7ce67ea08f71cbfb943792eeced7a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Bereitstellen von Zweigstellen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Zweigstellenbenutzer erhalten die meisten ihrer lync Server 2013-Funktionen von dem Server am zentralen Standort, dem die Zweigstelle zugeordnet ist. Jede Verzweigungs Website ist genau einem zentralen Standort zugeordnet. Zum Bereitstellen von Anrufen in das und aus dem PSTN (Public Switched Telephone Network) kann eine Verzweigungs Website eine der folgenden Aktionen enthalten:

  - Ein PSTN-Gateway und möglicherweise ein Meditations Server

  - Ein SIP-Trunk

  - Eine vorhandene VoIP-Infrastruktur mit einer PBX (Private Branch Exchange)

  - Eine Survivable-Branch-Appliance

  - Ein Survivable-Branch-Server

Zweigstellen mit einer überlebensfähigen Branch-Appliance oder einem Survivable Branch-Server sind in Zeiten von Wide-Area-Netzwerk-oder zentralen Standortausfällen widerstandsfähiger als Zweigstellen ohne eine dieser Lösungen. Beispielsweise können Benutzer in einer Website mit einer überlebensfähigen Branch-Appliance oder einem Überlebenden Branch-Server weiterhin PSTN-Anrufe tätigen und empfangen, wenn das Netzwerk, das die Verzweigungs Website mit dem zentralen Standort verbindet, ausgefallen ist. Eine weitere Möglichkeit zum Erreichen einer Ausfallsicherheit für Zweigstellen ist die Verwendung eines PSTN-Gateways oder eines SIP-Trunks mit einer vollständigen lync Server-Bereitstellung auf der Zweigstelle.

Details dazu, welche Verzweigungs Website Bereitstellung für Ihre Organisation richtig ist, einschließlich Voraussetzungen und andere Planungsüberlegungen, finden Sie unter [Planen der PSTN-Konnektivität in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) und [Planen der sprach Stabilität von Branch-Site in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in der Planungsdokumentation.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Bereitstellen der PSTN-Konnektivität an einem Zweigstellenstandort in Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

