---
title: 'Lync Server 2013: Bereitstellen von Vermittlungsservern und Definieren von Peers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03eca427f644d6f94ae7a52900b80320e2517ed2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Die Enterprise-VoIP-Arbeitsauslastung, Einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (Reaktionsgruppenanwendung, Anwendung zum Parken von anrufen, Anrufsteuerung (CAC) usw.) stehen in Front-End-Pools zur Verfügung. Mit lync Server 2013 ist die Funktionalität der Vermittlungsserver in den Front-End-Server integriert. Ein separater eigenständiger Vermittlungsserver ist nicht mehr erforderlich. Front-End-Pools können direkt mit unterstützten Gateways (einem PSTN-Gateway (Public Switched Telephone Network) oder einer IP-Nebenstellenanlage kommunizieren, sodass ein Vermittlungsserver nicht als Vermittler fungieren muss.

Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar. Um Ihre Enterprise-VoIP-Infrastruktur mit Ihrem SIP-Trunk Anbieter zu verbinden, muss ein separates Vermittlungsserver bereitgestellt werden.

Die Verbindung zwischen lync Server (der Vermittlungsserver Komponente auf einem Front-End-Pool oder einem eigenständigen Vermittlungsserver) und einem Gateway ist als logische Zuordnung als *trunk*definiert. In den Themen in diesem Abschnitt werden die Definition eines Trunks und die Bereitstellung eines eigenständigen Vermittlungsservers beschrieben, wenn Sie eine Verbindung mit einem SIP-Trunk herstellen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Definieren eines Vermittlungsserver im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definieren eines Gateways im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Installieren der Dateien für Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Verwandte Abschnitte

[Konfigurieren von Einwahlkonferenzen in lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

