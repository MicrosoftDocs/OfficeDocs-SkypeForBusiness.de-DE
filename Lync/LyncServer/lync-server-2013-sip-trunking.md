---
title: 'Lync Server 2013: SIP-Trunking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adf8dcee7ccd7adb393c8d13f7e9a8b186d2bb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519662"
---
# <a name="sip-trunking-in-lync-server-2013"></a>SIP-Trunking in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-13_

SIP (Session Initiation Protocol) wird zum Initiieren und Verwalten von VoIP-Kommunikationssitzungen (Voice over IP) für grundlegende Telefondienste und zusätzliche Echtzeitkommunikationsdienste wie Instant Messaging, Konferenzfunktionen, Anwesenheitserkennung und Multimediafunktionen verwendet. Dieser Abschnitt umfasst Planungsinformationen für die Implementierung von *SIP-Trunks*, eine Art von SIP-Verbindung, die über die Grenzen Ihres lokalen Netzwerks hinausgeht.

<div>

## <a name="what-is-sip-trunking"></a>Was ist SIP-Trunking?

Bei einem SIP-Trunk handelt es sich um eine IP-Verbindung für die SIP-Kommunikation zwischen Ihrer Organisation und einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP), die über Ihre Firewall hinausgeht. Ein SIP-Trunk wird typischerweise verwendet, um den zentralen Standort Ihrer Organisation mit einem ITSP zu verbinden. In einigen Fällen können Sie das SIP-Trunking auch zum Verbinden einer Zweigstelle mit einem ITSP nutzen.

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>SIP-Trunks im Vergleich zu direkten SIP-Verbindungen

Der Begriff *Trunk* wurde aus der leitungsvermittelten Technologie abgeleitet. Er bezieht sich auf eine dedizierte physische Leitung zur Verbindung von Telefonvermittlungsanlagen. Wie bei ihren Vorgänger-, Time Division Multiplexing (TDM)-Trunks sind SIP-Trunks Verbindungen zwischen zwei getrennten SIP-Netzwerken – dem lync Server 2013 Enterprise und dem ITSP. Im Gegensatz zu leitungsvermittelten Trunks handelt es sich bei SIP-Trunks um virtuelle Verbindungen, die über jeden der unterstützten Typen von SIP-Trunkingverbindungen hergestellt werden können. Ausführliche Informationen zu den unterstützten Verbindungstypen finden Sie unter [wie kann ich SIP-Trunking in lync Server 2013 implementieren?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Bei direkten SIP-Verbindungen hingegen handelt es sich um SIP-Verbindungen, die nicht über die Grenzen des lokalen Netzwerks hinausgehen (das heißt, es wird eine Verbindung mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) oder einer Nebenstellenanlage (Private Branch Exchange, PBX) innerhalb des internen Netzwerks hergestellt). Ausführliche Informationen dazu, wie Sie direkte SIP-Verbindungen mit lync Server 2013 verwenden können, finden Sie unter [Direct SIP Connections in lync Server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Übersicht über das SIP-Trunking in lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Wie kann ich SIP-Trunking in lync Server 2013 implementieren?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Komponenten und Topologien für SIP-Trunking in lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [SIP-Trunking für Zweigstellenstandorte in lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Prüfliste für SIP-Trunk Bereitstellung für lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

