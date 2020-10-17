---
title: 'Lync Server 2013: Vermittlungsserver-Komponente'
description: 'Lync Server 2013: Vermittlungsserver-Komponente.'
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
ms.openlocfilehash: 08c11bff3ee7077d991204cda5a9885787c50ec2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568641"
---
# <a name="mediation-server-component-in-lync-server-2013"></a>Vermittlungsserver Komponente in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Sie müssen lync Server 2013 bereitstellen, Vermittlungsserver, wenn Sie die Enterprise-VoIP-Arbeitsauslastung bereitstellen. In diesem Abschnitt werden die grundlegende Funktionalität, Abhängigkeiten, grundlegende Topologien sowie Richtlinien für die Planung beschrieben.

Das Vermittlungsserver übersetzt das signalisieren und in einigen Konfigurationen Medien zwischen dem internen lync Server 2013, der Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem SIP-Trunk (Session Initiation Protocol). Auf der lync Server 2013 Seite überwacht Vermittlungsserver eine einzelne MTLS-Transportadresse (Mutual TLS). Aufseiten des Gateways überwacht der Vermittlungsserver alle zugehörigen Überwachungsports für die Trunks, die im Topologiedokument definiert wurden. Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden. TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.

Wenn in Ihrer Umgebung auch eine Nebenstellenanlage vorhanden ist, verarbeitet Vermittlungsserver Anrufe zwischen Enterprise-VoIP-Benutzern und der Nebenstellenanlage. Wenn es sich bei Ihrer Nebenstellenanlage um eine IP-Nebenstellenanlage handelt, können Sie eine direkte SIP-Verbindung zwischen der Nebenstellenanlage und der Vermittlungsserver erstellen. Wenn es sich bei Ihrer Nebenstellenanlage um eine TDM-Nebenstellenanlage (Time Division Multiplex) handelt, müssen Sie auch ein PSTN-Gateway zwischen Vermittlungsserver und der Nebenstellenanlage bereitstellen.

Das Vermittlungsserver wird standardmäßig mit dem Front-End-Server zusammengefasst. Das Vermittlungsserver kann auch aus Leistungsgründen in einem eigenständigen Pool bereitgestellt werden, oder wenn Sie das SIP-Trunking bereitstellen, wird der eigenständige Pool in diesem Fall dringend empfohlen.

Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger fea-mediation-pool erforderlich. Der Grund ist, dass qualifizierte Gateways einen DNS-Lastenausgleich (Domain Name System) für einen Pool aus Vermittlungsservern implementieren und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können.

Die Verbindung des Vermittlungsservers mit einem Front-End-Pool wird auch empfohlen, wenn Sie IP-Nebenstellenanlagen oder einen von einem Internettelefoniedienstanbieter bereitgestellten SBC (Session Border Controller) verwenden, sofern eine der folgenden Bedingungen erfüllt ist:

  - Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

  - Die IP-Nebenstellenanlage unterstützt keine medienumgehung, aber die Front-End-Pool, die die Vermittlungsserver hostet, kann die Sprachübertragung für Anrufe verarbeiten, für die die medienumgehung nicht gilt.

Mit dem Microsoft lync Server 2013 Planungs Tool können Sie auswerten, ob der Front-End-Pool, in dem Sie die Vermittlungsserver collocate möchten, die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

Die Hauptfunktionen des Vermittlungsserver lauten wie folgt:

  - Verschlüsseln und Entschlüsseln von SRTP auf der lync Server Seite

  - Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) in SIP über Mutual TLS

  - Übersetzen von Mediendatenströmen zwischen lync Server und dem Gateway-Peer des Vermittlungsserver

  - Herstellen von Verbindungen zwischen Clients außerhalb des Netzwerks und internen ICE-Komponenten, damit Medien NAT und Firewalls passieren können

  - Fungieren als Vermittler für Anruf Flüsse, die von einem Gateway nicht unterstützt werden, beispielsweise Anrufe von Remotemitarbeitern auf einem Enterprise-VoIP-Client

  - Verwenden des SIP-Trunking-Dienstanbieters für das Telefonfestnetz, sodass kein PSTN-Gateway erforderlich ist (gilt für Bereitstellungen mit SIP-Trunking)

In der folgenden Abbildung sind die Signalisierungs-und Medienprotokolle dargestellt, die vom Vermittlungsserver bei der Kommunikation mit einem einfachen PSTN-Gateway und der Enterprise-VoIP-Infrastruktur verwendet werden.

**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**

![Diagramm für Vermittlungsserver Protokolle](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramm für Vermittlungsserver Protokolle")

<div>


> [!NOTE]  
> Wenn Sie TCP oder RTP/RTCP (anstelle von SRTP oder SRTCP) im Netzwerk zwischen dem PSTN-Gateway und dem Vermittlungsserver verwenden, wird empfohlen, Maßnahmen zu ergreifen, um die Sicherheit und den Datenschutz des Netzwerks sicherzustellen.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [M:n-trunk trunk in lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Anrufsteuerung und Vermittlungsserver in lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Enhanced 9-1-1 (E9-1-1) und Vermittlungsserver in lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Medienumgehung und Vermittlungsserver in lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Komponenten und Topologien für Vermittlungsserver in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

