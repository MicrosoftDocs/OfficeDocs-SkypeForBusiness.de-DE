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
ms.openlocfilehash: 5b2f3cd153a6dc8d101f44a3f087f0ccedfa9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Bereitstellungsoptionen für PSTN-Gateways in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>PSTN Gateways

PSTN-Gateways (Public Switched Telephone Network) sind Hardwarekomponenten von Drittanbietern, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über die Verbindung zu SIP-Stämmen. In beiden Topologien beendet das Gateway das PSTN. Das Gateway ist in seinem eigenen Subnetz isoliert und wird über den Vermittlungs Server mit dem Unternehmensnetzwerk verbunden.

In einem Unternehmen mit mehreren Websites werden in der Regel mindestens ein Gateway an jedem Standort bereitgestellt. Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über eine Survivable Branch-Appliance herstellen, die Gateway und Server in einem einzigen Feld kombiniert. Wenn Verzweigungs Websites ein Gateway verwenden, sind auf der Website sowohl eine Registrierungsstelle als auch ein Vermittlungs Server erforderlich, es sei denn, die WAN-Verbindung ist widerstandsfähig. Auf einem oder mehreren Vermittlungsservern, die sich auf Front-End-Servern befinden, können Anrufe an die einen oder mehrere Gateways an jedem Standort weitergeleitet werden. Wir empfehlen, dass die auf der Website erforderliche Registrierungsstelle, der Vermittlungs Server und das Gateway als Survivable Branch Appliance bereitgestellt werden.

Die Ermittlung von Anzahl, Größe und Standort von PSTN-Gateways ist vielleicht die wichtigste und kostspieligste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.

Here are the main questions to consider. Beachten Sie, dass die Antworten auf diese Fragen alle voneinander abhängig sind.

  - How many PSTN gateways are needed? Die Antwort richtet sich nach der Anzahl der Benutzer, der voraussichtlichen Anzahl von gleichzeitigen anrufen (Traffic Load) und der Anzahl der Websites (jeder Standort benötigt einen).

  - What size should the gateways be? Die Antwort hängt von der Anzahl der Benutzer auf der Website und von der Auslastung des Datenverkehrs ab.

  - Where should the gateways be located? Die Antwort hängt teilweise von der Topologie und teilweise von der geografischen Verteilung Ihrer Organisation ab.

 You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).

<div>

## <a name="mn-trunk-support"></a>M:N Trunk Support

Die Vermittlungsserver können Anrufe über mehrere Gateways (Session Border Controllers, SBCS), die von Internet-Telefoniedienst-Anbietern bereitgestellt werden, oder eine Kombination der beiden leiten. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route, die zwischen einem Vermittlungs Server und einem Gateway definiert wird, wird als *trunk*bezeichnet. Wenn ein interner Benutzer einen PSTN-Anruf annimmt, wählt die ausgehende Routinglogik im Front-End-Pool aus, welcher trunk über alle möglichen Kombinationen weitergeleitet werden soll, die möglicherweise für das Routing dieses bestimmten Anrufs verfügbar sind. Wenn ein Anruf aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool durch einen DNS-Lastenausgleich nicht erreicht wird, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.

Ausführliche Informationen zur Planung mehrerer Gateways finden Sie unter [M:N trunk in lync Server 2013](lync-server-2013-m-n-trunk.md).

Details zu weiteren Verbesserungen des ausgehenden Routings finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Gateway Topologies

Führen Sie die folgenden Schritte aus, wenn Sie die grundlegenden Fragen der Gateway-Bereitstellung beachten:

1.  Zählen Sie die Websites, auf denen Sie PSTN-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.

2.  Schätzen Sie den Datenverkehr an jeder Website (Anzahl der Benutzer und durchschnittliche Anzahl von Anrufen pro Stunde pro Benutzer).

3.  Bereitstellen eines oder mehrerer Gateways an jedem Standort, um den erwarteten Datenverkehr zu verarbeiten

Die resultierende verteilte Gateway-Topologie wird in der folgenden Abbildung gezeigt.

**Topologie des verteilten Gateways**

![Topologie-Diagramm für verteilte Gateways](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Topologie-Diagramm für verteilte Gateways")

Bei dieser Topologie werden Anrufe zwischen Mitarbeitern an jedem Standort und zwischen Websites über Ihr Intranet weitergeleitet. Anrufe an das PSTN werden über das Enterprise IP-Netzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Was aber, wenn Ihre Organisation Dutzende oder Hunderte oder sogar Tausende von Websites unterstützt, die sich über einen oder mehrere Kontinente verteilen, wie es viele Finanzinstitute und andere große Unternehmen tun? In solchen Fällen ist die Bereitstellungeines separaten Gateways an jedem Standort nicht praktikabel.

Um dieses Problem zu beheben, bevorzugen viele große Unternehmen, wie in der nachstehenden Abbildung zu sehen, ein oder einige wenige große Telefonie-Zentrale Standorte bereitzustellen.

**Topologie des zentralen Telefonie-Standorts**

![Datencenter-Gateway-Topologie](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Datencenter-Gateway-Topologie")

In dieser Topologie sind mehrere große Gateways, die für die erwartete Benutzerauslastung ausreichend sind, an jedem zentralen Standort bereitgestellt. Alle Anrufe an Benutzer im Unternehmen werden vom Telefondienstanbieter des Unternehmens an einen zentralen Standort weitergeleitet. Die Routing Logik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder das PSTN weitergeleitet werden soll.

</div>

<div>

## <a name="gateway-location"></a>Gateway Location

Der Gateway-Speicherort kann auch die von Ihnen ausgewählten Typen von Gateways und Ihre Konfiguration ermitteln. Es gibt Dutzende von PSTN-Protokollen, von denen keiner weltweit Standard ist. Wenn sich alle Ihre Gateways in einem einzelnen Land/einer Region befinden, handelt es sich nicht um ein Problem, aber wenn Sie Gateways in verschiedenen Ländern/Regionen finden, müssen die einzelnen Gateways entsprechend den PSTN-Standards für dieses Land/diese Region konfiguriert werden. Darüber hinaus sind Gateways, die für den Einsatz in Kanada zertifiziert sind, möglicherweise nicht in Indien, Brasilien oder der Europäischen Union zertifiziert.

</div>

<div>

## <a name="gateway-size-and-number"></a>Gateway Size and Number

Die PSTN-Gateways, die in den meisten Organisationen für die Bereitstellung von Bereichsgröße von 2 bis so viele 960-Ports in Frage kommen. (Es gibt sogar größere Gateways, die aber hauptsächlich von Telefondienstanbietern verwendet werden.) Verwenden Sie die folgenden Richtlinien, wenn Sie die Anzahl der von Ihrer Organisation benötigten Ports schätzen:

  - Organisationen mit leichter Telefonie-Nutzung (ein PSTN-Anruf pro Benutzer pro Stunde) sollten für alle 15 Benutzer einen Port zuteilen. Wenn Sie beispielsweise 20 Benutzer haben, benötigen Sie ein Gateway mit zwei Anschlüssen.

  - Organisationen mit mittlerer Telefonie-Nutzung (zwei PSTN-Anrufe pro Benutzer pro Stunde) sollten einem Port für alle 10 Nutzer zugeteilt werden. Wenn Sie beispielsweise über 100-Benutzer verfügen, benötigen Sie insgesamt 10 Ports, die einem oder mehreren Gateways zugewiesen sind.

  - Organisationen mit hoher Telefonnutzung (drei oder mehr PSTN-Anrufe pro Benutzer pro Stunde) sollten für alle fünf Benutzer einen Port zuteilen. Wenn Sie beispielsweise über 47.000-Benutzer verfügen, benötigen Sie insgesamt 9.400-Ports, die unter mindestens 10 große Gateways zugeteilt sind.

  - Zusätzliche Ports können abgerufen werden, wenn die Anzahl der Benutzer oder der Datenverkehr in Ihrer Organisation zunimmt.

Für eine bestimmte Anzahl von Benutzern, die Sie unterstützen müssen, haben Sie die Wahl, weniger, größere Gateways oder kleinere bereitzustellen. In der Regel werden mindestens zwei Gateways für eine Organisation empfohlen, um die Verfügbarkeit zu gewährleisten, wenn ein Gateway ausfällt.

Jedes von Ihnen bereitgestellte PSTN-Gateway muss mindestens über einen entsprechenden Vermittlungs Server verfügen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

