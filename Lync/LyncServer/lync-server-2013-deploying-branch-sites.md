---
title: 'Lync Server 2013: Bereitstellen von Zweigstellenstandorten'
description: 'Lync Server 2013: Bereitstellen von Zweigstellenstandorten.'
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
ms.openlocfilehash: d653e3f06de832693d97bfb229f122a67c28640e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552641"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a>Bereitstellen von Zweigstellenstandorten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Zweigstellenbenutzer erhalten den Großteil ihrer lync Server 2013 Funktionalität von dem Server am zentralen Standort, dem der Zweigstellenstandort zugeordnet ist. Jede Zweigstelle ist mit genau einem zentralen Standort verbunden. Zum Tätigen und Entgegennehmen von Anrufen aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) kann ein Zweigstellenstandort eine der folgenden Komponenten umfassen:

  - Ein PSTN-Gateway und optional einen Vermittlungsserver

  - Einen SIP-Trunk

  - Eine vorhandene VoIP-Infrastruktur mit einer Nebenstellenanlage

  - Ein Survivable Branch Appliance

  - Ein Survivable Branch Server

Zweigstellenstandorte mit einem Survivable Branch Appliance oder einem Survivable Branch Server sind in Zeiten größerer Netzwerk-oder zentraler Standortausfälle widerstandsfähiger als Zweigstellenstandorte ohne eine dieser Lösungen. Beispielsweise können Benutzer bei einer Website mit einer Survivable Branch Appliance oder einer Survivable Branch Server, die bereitgestellt werden, weiterhin PSTN-Anrufe tätigen und empfangen, wenn das Netzwerk, das den Zweigstellenstandort mit dem zentralen Standort verbindet, nicht aktiv ist. Eine weitere Möglichkeit zum Erreichen von Ausfallsicherheit für Zweigstellenstandorte ist die Verwendung eines PSTN-Gateways oder eines SIP-Trunks mit einer vollständigen lync Server-Bereitstellung am Zweigstellenstandort.

Ausführliche Informationen dazu, welche Zweigstellenbereitstellung für Ihre Organisation geeignet ist, einschließlich Voraussetzungen und anderen Planungsüberlegungen, finden Sie unter [Planning for PSTN Connectivity in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) und [Planning for Branch-Site Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in der Planungsdokumentation.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Bereitstellen der PSTN-Konnektivität an einem Zweigstellenstandort in lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

