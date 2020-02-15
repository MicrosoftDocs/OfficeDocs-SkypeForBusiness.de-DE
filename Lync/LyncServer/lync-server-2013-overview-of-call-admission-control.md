---
title: 'Lync Server 2013: Übersicht über die Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ad2be78d3e2af4c5b016b02e152ba0430d2a1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Übersicht über die Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-22_

Die Echtzeitkommunikation ist anfällig für Latenzprobleme und Paketverluste, wie sie bei überlasteten Netzwerken auftreten können. Der Anrufsteuerungsdienst ermittelt anhand der verfügbaren Netzwerkbandbreite, ob Kommunikationssitzungen (beispielsweise Sprach- oder Videoanrufe) in Echtzeit eingerichtet werden dürfen. Das CAC-Design in lync Server 2013 bietet vier Hauptattribute:

  - Die Bereitstellung und Verwaltung ist einfach, ohne dass zusätzliche Geräte erforderlich sind, wie speziell konfigurierte Router.

  - Es behandelt wichtige Unified Communications-Anwendungsfälle wie Roaming-Benutzer und mehrere Points of Presence. Richtlinien für die Anrufsteuerung werden entsprechend der Position des Endpunkts und nicht des Standorts des Benutzers erzwungen.

  - Zusätzlich zu Sprachanrufen kann es auf anderen Datenverkehr angewendet werden, wie Videoanrufe und Audio/Video-Konferenzsitzungen.

  - Bietet die Flexibilität, die Darstellung verschiedener Arten von Netzwerktopologien zu ermöglichen. Beispiele finden Sie unter [Components and Topologies for CAC in lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Wenn eine neue sprach-oder Videositzung die Bandbreitengrenzwerte überschreitet, die Sie für eine WAN-Verbindung festgelegt haben, wird die Sitzung entweder blockiert oder (nur bei Anrufen) an das PSTN umgeleitet.

Die Anrufsteuerung steuert den echtzeitdatenverkehr nur für Sprache und Video. Der Datenverkehr wird nicht gesteuert.

Administratoren definieren CAC-Richtlinien, die durch den bandbreitenrichtliniendienst erzwungen werden, der mit jeder Front-End-Pool installiert wird. Die Einstellungen für die Anrufsteuerung werden automatisch an alle lync Server-Front-End-Server in Ihrem Netzwerk weitergegeben.

Bei Anrufen, die aufgrund von CAC-Richtlinien fehlschlagen, lautet die Prioritätsreihenfolge für das erneute Routing des Anrufs wie folgt:

1.  Internet

2.  PSTN

3.  Voicemail

Mit der Aufzeichnung von Kommunikationsdatensätzen (KDS) werden Informationen zu anrufen erfasst, die an das PSTN oder an Voicemail umgeleitet werden. In KDS werden keine Informationen zu anrufen erfasst, die an das Internet umgeleitet werden, da das Internet als alternativer Pfad statt als sekundäre Option behandelt wird.

<div>


> [!NOTE]  
> Voicemail-Ablagerungen werden aufgrund von Bandbreiteneinschränkungen nicht verweigert.



</div>

Der bandbreitenrichtliniendienst generiert zwei Typen von Protokolldateien im CSV-Format (Comma Separated Values). In der Protokolldatei **Überprüfen von Fehlern** werden Informationen erfasst, wenn Bandbreitenanforderungen verweigert werden. In der Protokolldatei für die **Link Nutzung** wird eine Momentaufnahme der Netzwerktopologie und der Bandbreitenauslastung der WAN-Verbindung erfasst. Beide Protokolldateien können Sie bei der Feinabstimmung Ihrer CAC-Richtlinien basierend auf der Auslastung unterstützen.

<div>

## <a name="call-admission-control-considerations"></a>Überlegungen zur Anrufsteuerung

Der Administrator wählt den bandbreitenrichtliniendienst im ersten am zentralen Standort konfigurierten Pool aus. Da es einen einzelnen zentralen Standort pro netzwerkregion gibt, gibt es nur einen bandbreitenrichtliniendienst pro netzwerkregion, der die bandbreitenrichtlinie für diese Region, die zugehörigen Standorte und die Links zu diesen Websites verwaltet. Der bandbreitenrichtliniendienst wird als Teil der Front-End-Server ausgeführt, und daher ist die hohe Verfügbarkeit in diesem Pool integriert. Der bandbreitenrichtliniendienst, der auf jedem Front-End-Server ausgeführt wird, wird alle 15 Sekunden synchronisiert. Wenn die Front-End-Pool fehlschlägt, werden CAC-Richtlinien für diesen Standort erst dann erzwungen, wenn der Front-End-Pool und damit der bandbreitenrichtliniendienst wieder betriebsbereit ist. Dies bedeutet, dass alle Anrufe für den Zeitraum, in dem der bandbreitenrichtliniendienst außer Betrieb ist, durchlaufen werden. Daher gibt es die Möglichkeit der Bandbreiten Überzeichnung Ihrer Links während dieses Zeitraums.

Der bandbreitenrichtliniendienst bietet eine hohe Verfügbarkeit innerhalb eines Front-End-Pools; Es bietet jedoch keine Redundanz für Front-End-Pools. Der bandbreitenrichtliniendienst kann kein Failover von einem Front-End-Pool auf einen anderen durch haben. Sobald der Dienst für das Front-End-Pool wiederhergestellt wurde, wird der bandbreitenrichtliniendienst fortgesetzt und kann erneut die Bandbreitenrichtlinien Überprüfung erzwingen.

<div>

## <a name="network-considerations"></a>Überlegungen zum Netzwerk

Obwohl Bandbreiteneinschränkungen für Audio und Video durch den bandbreitenrichtliniendienst in lync Server 2013 erzwungen werden, wird diese Einschränkung nicht auf dem Netzwerkrouter erzwungen (Ebene 2 und 3). Lync Server 2010-Anrufsteuerung kann nicht verhindern, dass eine Daten Anwendung beispielsweise die gesamte Netzwerkbandbreite für eine WAN-Verbindung beansprucht, einschließlich der Bandbreite, die für Audio und Video von der Anruf Steuerungsrichtlinie reserviert ist. Um die erforderliche Bandbreite in Ihrem Netzwerk zu schützen, können Sie ein QoS-Protokoll (Quality of Service) wie unterschiedliche Dienste (Diffserv) bereitstellen. Es empfiehlt sich daher, die von Ihnen definierten Richtlinien für die CAC-Bandbreiten mit allen QoS-Einstellungen zu koordinieren, die Sie bereitstellen können.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Medien-und Signalisierungs Pfade über VPN

Wenn Ihr Unternehmen Medien über VPN unterstützt, stellen Sie sicher, dass entweder sowohl der Mediendatenstrom als auch der Signalisierungsdaten Strom durch das VPN geleitet werden oder beide über das Internet geroutet werden. Standardmäßig durchlaufen die Medien-und Signalisierungsdaten Ströme den VPN-Tunnel.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Anrufsteuerung für externe Benutzer

Die Anrufsteuerung wird nicht für Remotebenutzer erzwungen, bei denen der Netzwerkdatenverkehr über das Internet fließt. Da der Mediendatenverkehr das Internet durchläuft, das nicht von lync Server verwaltet wird, kann die Anrufsteuerung nicht angewendet werden. Für den Teil des Anrufs, der über das Unternehmensnetzwerk fließt, werden jedoch CAC-Prüfungen durchgeführt.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Anrufsteuerung für PSTN-Verbindungen

Die Anrufsteuerung ist auf dem Vermittlungsserver vollstreckbar, unabhängig davon, ob Sie mit einer IP/PBX-Anlage, einem PSTN-Gateway oder einem SIP-Trunk verbunden ist. Da es sich bei dem Vermittlungsserver um einen Back-to-Back-Benutzer-Agent (B2BUA) handelt, werden die Medien beendet. Es hat zwei Verbindungsseiten: eine Seite, die mit lync Server und einer Gatewayseite verbunden ist, die mit PSTN-Gateways, IP/PBX-Anlagen oder SIP-Trunks verbunden ist. Ausführliche Informationen zu PSTN-Verbindungen finden Sie unter [Planning for PSTN Connectivity in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

Die Anrufsteuerung kann auf beiden Seiten des Vermittlungsserver erzwungen werden, es sei denn, die medienumgehung ist aktiviert. Wenn die medienumgehung aktiviert ist, wird der Mediendatenverkehr nicht durchlaufen Vermittlungsserver sondern direkt zwischen dem lync-Client und dem Gateway fließt. In diesem Fall ist keine Anrufsteuerung erforderlich. Ausführliche Informationen finden Sie unter [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

In der folgenden Abbildung wird veranschaulicht, wie die Anrufsteuerung für PSTN-Verbindungen mit und ohne medienumgehung erzwungen wird.

**Erzwingen der Anrufsteuerung für Verbindungen mit dem PSTN**

![VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Kompatibilität der Anrufsteuerung mit früheren Versionen von Office Communications Server

Die Anrufsteuerung kann nur für Endpunkte aktiviert werden, die für lync Server 2010 und höher aktiviert sind.

Die Anrufsteuerung kann nicht für Endpunkte aktiviert werden, die Office Communicator 2007 R2 oder früher durchführen.

**Anwendung der Anrufsteuerung in verschiedenen lync Server Versionen**

![Sprach-CAC-Versionsvergleichs Diagramm](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Sprach-CAC-Versionsvergleichs Diagramm")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

