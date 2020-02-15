---
title: 'Lync Server 2013: Bereitstellungsoptionen für PSTN-Gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e4d8f35ecf2b384ad51482547b22baad63fcf31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Bereitstellungsoptionen für PSTN-Gateways in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>PSTN-Gateways

PSTN-Gateways (Public Switched Telephone Network) sind Drittanbieter-Hardwarekomponenten, die Signal-und Medien Verbindungen zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über die Verbindung mit SIP-Trunks. In beiden Topologien stellt das Gateway den Endpunkt für das Telefonfestnetz dar. Das Gateway ist in seinem eigenen Subnetz isoliert und über das Vermittlungsserver mit dem Unternehmensnetzwerk verbunden.

In einem Unternehmen mit mehreren Standorten wird üblicherweise mindestens ein Gateway pro Standort bereitgestellt. Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über ein Survivable Branch Appliance herstellen, der Gateway und Server in einem einzigen Feld kombiniert. Wenn Zweigstellenstandorte ein Gateway verwenden, sind sowohl eine Registrierungsstelle als auch Vermittlungsserver vor Ort erforderlich, es sei denn, die WAN-Verbindung ist widerstandsfähig. Ein oder mehrere Vermittlungsserver, die auf Front-End-Servern zusammengestellt sind, können Anrufe für ein oder mehrere Gateways an jedem Standort weiterleiten. Es wird empfohlen, die für die Website erforderlichen Registrierungsstellen, Vermittlungsserver und Gateways als Survivable Branch Appliance bereitzustellen.

Die Ermittlung der Anzahl, Größe und des Speicherorts von PSTN-Gateways ist vielleicht die wichtigste und teuerste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.

Sie müssen folgende wichtige Fragen bedenken. Keine dieser Fragen kann unabhängig von den anderen beantwortet werden.

  - Wie viele PSTN-Gateways sind erforderlich? Die Antwort richtet sich nach der Anzahl von Benutzern, der erwarteten Anzahl gleichzeitiger Anrufe (Datenverkehr) und der Anzahl von Standorten (jeder Standort benötigt ein Gateway).

  - Wie groß sollen die Gateways sein? Die Antwort richtet sich nach der Anzahl von Benutzern am Standort und dem zu erwartenden Datenverkehr.

  - Wo sollen sich die Gateways befinden? Die Antwort richtet sich zum Teil nach der Topologie und zum Teil nach der geografischen Verteilung Ihrer Organisation.

Sie sollten auch die Optionen für die Gatewaytopologie berücksichtigen (weitere Informationen hierzu finden Sie im Abschnitt "Gatewaytopologien" weiter unten in diesem Thema).

<div>

## <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Die Vermittlungsserver können Anrufe über mehrere Gateways, Session Border Controller (SBCS), die von Internet Telefonie-Dienstanbietern bereitgestellt werden, oder eine Kombination aus beiden weiterleiten. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route, die zwischen einem Vermittlungsserver und einem Gateway definiert wird, wird *trunk*genannt. Wenn ein interner Benutzer einen PSTN-Anruf tätigt, wählt die ausgehende Routinglogik auf dem Front-End-Pool aus, welcher trunk alle möglichen Kombinationen weiterleiten soll, die möglicherweise für das Routing dieses bestimmten Anrufs verfügbar sind. Wenn beim DNS-Lastenausgleich ein Anruf aufgrund eines Problems mit einer bestimmten Vermittlungsserver im Pool nicht zu einem Gateway gelangt, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.

Ausführliche Informationen zur Planung mehrerer Gateways finden Sie unter [m:n-trunk trunk in lync Server 2013](lync-server-2013-m-n-trunk.md).

Ausführliche Informationen zu weiteren Verbesserungen beim ausgehenden Routing finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Gatewaytopologien

Halten Sie sich bei Ihren Überlegungen zu den grundlegenden Fragen zur Gatewaybereitstellung an die folgenden Schritte:

1.  Zählen Sie die Standorte, an denen Sie die PSTN-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.

2.  Schätzen Sie den zu erwartenden Datenverkehr für jeden Standort (Anzahl von Benutzern und durchschnittliche Anzahl von Anrufen pro Stunde und Benutzer).

3.  Stellen Sie mindestens ein Gateway an jedem Standort bereit, um den zu erwartenden Datenverkehr zu verarbeiten.

Die folgende Abbildung zeigt die verteilte Gatewaytopologie, die Sie auf diese Weise erhalten.

**Verteilte Gatewaytopologie**

![Topologie-Diagramm für verteilte Gateways](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Topologie-Diagramm für verteilte Gateways")

In dieser Topologie werden alle Anrufe zwischen Mitarbeitern innerhalb jedes Standorts sowie zwischen den Standorten über Ihr Intranet weitergeleitet. Anrufe in das Telefonfestnetz werden über das IP-Unternehmensnetzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Wie sollte die Bereitstellung jedoch aussehen, wenn Ihre Organisation Dutzende, Hunderte oder sogar Tausende von Standorten unterstützt, die über mehrere Kontinente verteilt sind – was beispielsweise bei vielen Finanzinstituten und anderen großen Unternehmen der Fall ist? In solchen Fällen ist es nicht empfehlenswert, an jedem Standort ein separates Gateway bereitzustellen.

Um dieses Problem zu beheben, bevorzugen viele große Unternehmen die Bereitstellungeines oder mehrerer großer Telefonie-zentraler Standorte, wie in der folgenden Abbildung dargestellt.

**Topologie mit einem zentralen Standort für die Telefonie**

![Rechenzentrums-Gateway-Topologie](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Rechenzentrums-Gateway-Topologie")

In dieser Topologie werden an jedem zentralen Standort mehrere große Gateways bereitgestellt, die für die erwartete Benutzerlast ausreichend sind. Alle Anrufe bei Benutzern im Unternehmen werden durch den Telefondienstanbieter des Unternehmens an einen zentralen Standort weitergeleitet. Die Routing Logik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder das PSTN weitergeleitet werden soll.

</div>

<div>

## <a name="gateway-location"></a>Gatewaystandort

Auch der Gatewaystandort bestimmt möglicherweise, welche Typen von Gateways Sie auswählen und wie Sie diese konfigurieren können. Es gibt Dutzende von PSTN-Protokollen, von denen jedoch keines weltweiter Standard ist. Wenn sich all Ihre Gateways in einem einzigen Land bzw. einer einzigen Region befinden, stellt dies kein Problem dar. Wenn Sie jedoch Gateways in mehreren Ländern/Regionen platzieren, muss jedes Gateway gemäß den dort verwendeten PSTN-Standards konfiguriert werden. Außerdem sind die Gateways, die beispielsweise für den Betrieb in Kanada zugelassen sind, in Indien, Brasilien oder der Europäischen Union möglicherweise nicht zugelassen.

</div>

<div>

## <a name="gateway-size-and-number"></a>Größe und Anzahl von Gateways

Die Größe der PSTN-Gateways, deren Bereitstellung für die meisten Organisationen in Betracht kommt, liegt im Bereich von 2 bis 960 Ports. (Es gibt sogar noch größere Gateways; diese werden jedoch hauptsächlich von Telefonanbietern verwendet.) Um zu schätzen, wie viele Ports in Ihrer Organisation benötigt werden, beachten Sie die folgenden Richtlinien:

  - Wenn in Ihrer Organisation wenig telefoniert wird (ein PSTN-Anruf pro Benutzer und Stunde), sollten Sie einen Port für jeweils 15 Benutzer zuordnen. Wenn beispielsweise 20 Benutzer vorhanden sind, benötigen Sie ein Gateway mit zwei Ports.

  - Wenn in Ihrer Organisation mäßig viel telefoniert wird (zwei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 10 Benutzer zuordnen. Wenn beispielsweise 100 Benutzer vorhanden sind, benötigen Sie insgesamt 10 Ports, die Sie auf einem oder auf mehreren Gateways zuordnen können.

  - Wenn in Ihrer Organisation viel telefoniert wird (mindestens drei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 5 Benutzer zuordnen. Wenn beispielsweise 47.000 Benutzer vorhanden sind, benötigen Sie insgesamt 9.400 Ports, die Sie auf mindestens 10 großen Gateways zuordnen sollten.

  - Zusätzliche Ports können erworben werden, wenn die Benutzeranzahl oder der Umfang des Datenverkehrs in Ihrer Organisation steigt.

Für jede zu unterstützende Benutzeranzahl können Sie entweder wenige größere Gateways oder mehrere kleine bereitstellen. Prinzipiell werden für jede Organisation mindestens zwei Gateways empfohlen, um die Verfügbarkeit sicherzustellen, falls ein Gateway ausfällt.

Jedes von Ihnen bereitgestellte PSTN-Gateway muss mindestens über eine entsprechende Vermittlungsserver verfügen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

