---
title: 'Lync Server 2013: Bereitstellen von Vermittlungsservern und Definieren von Peers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01ccf2e3822933842249df012877b13d10baef3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die Enterprise-VoIP-Arbeitsauslastung, Einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (reaktionsgruppenanwendung, Anruf Park Anwendung, Anrufsteuerung (CAC) usw.) stehen in Front-End-Pools zur Verfügung. Mit lync Server 2013 ist die Funktionalität des Vermittlungsservers in den Front-End-Server integriert. Ein separater eigenständiger Vermittlungs Server ist nicht mehr erforderlich. Front-End-Pools können direkt mit unterstützten Gateways (einem Public Switched Telephone Network (PSTN)-Gateway oder einer IP-Telefonanlage) kommunizieren, wodurch die Notwendigkeit eines Vermittlungsservers, der als Vermittler fungiert, entfernt wird.

Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar. Wenn Sie Ihre Enterprise-VoIP-Infrastruktur mit Ihrem SIP-Trunk-Anbieter verbinden möchten, muss ein separater Vermittlungs Server bereitgestellt werden.

Die Verbindung zwischen lync Server (der Vermittlungsserver Komponente in einem Front-End-Pool oder einem eigenständigen Vermittlungsserver) und einem Gateway wird als logische Zuordnung als " *trunk*" definiert. In den Themen in diesem Abschnitt wird beschrieben, wie Sie einen trunk definieren und wie Sie einen eigenständigen Vermittlungs Server bereitstellen, wenn Sie eine Verbindung mit einem SIP-Stamm herstellen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Definieren eines Vermittlungsservers im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definieren eines Gateways im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Installieren der Dateien für den Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Verwandte Abschnitte

[Konfigurieren von Einwahlkonferenzen in Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

