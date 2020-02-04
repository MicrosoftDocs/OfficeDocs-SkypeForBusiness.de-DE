---
title: 'Lync Server 2013: Vermittlungsserver Komponente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363b277003d7ca1581475ec7c1197bb0f60ccfaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Vermittlungsserver Komponente in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Sie müssen lync Server 2013, Mediation Server bereitstellen, wenn Sie die Enterprise-VoIP-Arbeitsauslastung bereitstellen. In diesem Abschnitt werden grundlegende Funktionen, Abhängigkeiten, grundlegende Topologien und Planungsrichtlinien beschrieben.

Der Vermittlungs Server übersetzt Signalisierungen und in einigen Konfigurationen Medien zwischen dem internen lync Server 2013, der Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem SIP-Stamm (Session Initiation Protocol). Auf der lync Server 2013-Seite lauscht Mediation Server an einer einzelnen MTLS-Transportadresse (Mutual TLS). Auf der Gatewayseite überwacht der Mediation Server alle zugehörigen Abhör-Ports, die mit Trunks verknüpft sind, die im Topologie-Dokument definiert sind. Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden. TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.

Wenn Sie auch über eine vorhandene öffentliche Branch Exchange (PBX) in Ihrer Umgebung verfügen, verarbeitet der Vermittlungs Server Anrufe zwischen Enterprise-VoIP-Benutzern und der Telefonanlage. Wenn es sich bei Ihrer Telefonanlage um eine IP-Telefonanlage handelt, können Sie eine direkte SIP-Verbindung zwischen der Telefonanlage und dem Vermittlungs Server herstellen. Wenn es sich bei Ihrer Telefonanlage um eine TDM-Telefonanlage (Time Division Multiplex) handelt, müssen Sie auch ein PSTN-Gateway zwischen dem Vermittlungs Server und der Telefonanlage bereitstellen.

Der Vermittlungsserver befindet sich standardmäßig mit dem Front-End-Server. Der Vermittlungs Server kann auch aus Leistungsgründen in einem eigenständigen Pool bereitgestellt werden, oder wenn Sie SIP-Trunking bereitstellen, wird in diesem Fall der eigenständige Pool dringend empfohlen.

Wenn Sie direkte SIP-Verbindungen zu einem qualifizierten PSTN-Gateway bereitstellen, das medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungs Server Pool erforderlich. Ein eigenständiger Vermittlungs Server Pool ist nicht erforderlich, da qualifizierte Gateways in der Lage sind, den DNS-Lastenausgleich zu einem Pool von Vermittlungsservern durchzuführen und Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen können.

Wir empfehlen außerdem, dass Sie den Vermittlungs Server in einem Front-End-Pool collocate, wenn Sie IP-PBX-Anlagen bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internet Telefonie-Serveranbieters herstellen, sofern eine der folgenden Bedingungen erfüllt ist:

  - Die IP-PBX-oder SBC-Konfiguration ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver im Pool konfiguriert und kann den Datenverkehr gleicherweise an alle Vermittlungsserver im Pool weiterleiten.

  - Die IP-PBX unterstützt keine medienumgehung, aber der Front-End-Pool, der den Vermittlungs Server hostet, kann die Sprachübertragung für Anrufe in die medienumgehung anwenden.

Sie können das Planungs Tool Microsoft lync Server 2013 verwenden, um zu evaluieren, ob der collocate, in dem Sie den Vermittlungsserver belegen möchten, die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.

Die wichtigsten Funktionen des Vermittlungsservers lauten wie folgt:

  - Verschlüsseln und Entschlüsseln von SRTP auf der lync Server-Seite

  - Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) für SIP über Mutual TLS

  - Übersetzen von Mediendatenströmen zwischen lync Server und dem Gateway-Peer des Vermittlungsservers

  - Verbinden von Clients außerhalb des Netzwerks mit internen ICE-Komponenten, die den Medien Durchlauf von NAT und Firewalls ermöglichen

  - Als Vermittler für Anruf Flüsse fungieren, die von einem Gateway nicht unterstützt werden, beispielsweise Anrufe von Remotemitarbeitern auf einem Enterprise-VoIP-Client

  - In Bereitstellungen, die SIP-Trunking umfassen, arbeiten mit dem SIP-Trunking-Dienstanbieter, um PSTN-Unterstützung bereitzustellen, wodurch kein PSTN-Gateway erforderlich ist

Die folgende Abbildung zeigt die Signalisierungs-und Medienprotokolle, die vom Vermittlungs Server bei der Kommunikation mit einem einfachen PSTN-Gateway und der Enterprise-VoIP-Infrastruktur verwendet werden.

**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**

![Vermittlungsserverprotokolle (Diagramm)](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Vermittlungsserverprotokolle (Diagramm)")

<div>


> [!NOTE]  
> Wenn Sie im Netzwerk zwischen dem PSTN-Gateway und dem Vermittlungs Server TCP-oder RTP-RTCP (statt SRTP oder SRTCP) verwenden, empfiehlt es sich, Maßnahmen zu ergreifen, um die Sicherheit und den Datenschutz des Netzwerks zu gewährleisten.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [M:N trunk in lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Anrufsteuerung und Vermittlungsserver in Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver in Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Medienumgehung und Vermittlungsserver in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Bereitstellungsrichtlinien für den Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

