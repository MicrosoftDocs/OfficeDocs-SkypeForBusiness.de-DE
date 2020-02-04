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
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Übersicht über die Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Echtzeitkommunikation ist sensibel für Latenz-und Paketverluste, die in überlasteten Netzwerken auftreten können. Der Anrufsteuerungsdienst ermittelt anhand der verfügbaren Netzwerkbandbreite, ob Kommunikationssitzungen (beispielsweise Sprach- oder Videoanrufe) in Echtzeit eingerichtet werden dürfen. Das CAC-Design in lync Server 2013 bietet vier Hauptattribute:

  - Sie lässt sich problemlos bereitstellen und verwalten, ohne dass zusätzliche Geräte (z. B. speziell konfigurierte Router) erforderlich sind.

  - Sie eignet sich für wichtige Unified Communications-Anwendungsfälle, z. B. für Roamingbenutzer und für die Anmeldung auf mehreren Geräten. Anrufsteuerungsrichtlinien werden nicht abhängig davon erzwungen, wo der Benutzer verwaltet wird, sondern basierend auf dem Standort des Endpunkts.

  - Zusätzlich zu VoIP-Anrufen kann die Anrufsteuerung auf andere Typen von Datenverkehr angewendet werden, z. B. auf Videoanrufe und Audio/Video-Konferenzsitzungen.

  - Dies bietet die Flexibilität, verschiedene Arten von Netzwerktopologien darstellen zu können. Beispiele finden Sie unter [Komponenten und Topologien für CAC in lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Wenn eine neue VoIP- oder Videositzung die festgelegten Bandbreiteneinschränkungen einer WAN-Leitung überschreitet, wird die Sitzung entweder blockiert oder (dies gilt nur für Telefonanrufe) an das Festnetz umgeleitet.

Mit der Anrufsteuerung wird lediglich Echtzeitdatenverkehr für VoIP- und Videoanrufe gesteuert. Anderer Datenverkehr wird nicht gesteuert.

Administratoren definieren CAC-Richtlinien, die vom bandbreitenrichtliniendienst erzwungen werden, der mit jedem Front-End-Pool installiert wird. Die CAC-Einstellungen werden automatisch an alle lync Server-Front-End-Server in Ihrem Netzwerk weitergegeben.

Bei Anrufen, die aufgrund von Anrufsteuerungsrichtlinien nicht erfolgreich durchgeführt werden können, gilt folgende Reihenfolge für die Anrufumleitung:

1.  Internet

2.  Telefonfestnetz (PSTN)

3.  Voicemail

Bei der Aufzeichnung von Kommunikationsdatensätzen werden Informationen zu Anrufen erfasst, die an das Festnetz oder an einen Voicemaildienst umgeleitet werden. Da das Internet nicht als sekundäre Option, sondern als alternativer Pfad behandelt wird, werden bei der Aufzeichnung von Kommunikationsdatensätzen keine Informationen zu Anrufen erfasst, die an das Internet umgeleitet werden.

<div>


> [!NOTE]  
> Das Hinterlassen von Voicemails wird aufgrund von Bandbreitenbeschränkungen nicht abgelehnt.



</div>

Der Bandbreitenrichtliniendienst generiert zwei Typen von Protokolldateien im CSV-Format (durch Trennzeichen getrennte Datei). In der Protokolldatei für **Fehler bei der Überprüfung** werden Informationen erfasst, wenn Bandbreitenanforderungen abgelehnt werden. In der Protokolldatei zur **Verbindungsauslastung** werden ein Snapshot der Netzwerktopologie sowie die Bandbreitenauslastung der WAN-Verbindung erfasst. Unter Verwendung dieser beiden Protokolldateien können Sie Ihre Anrufsteuerungsrichtlinien basierend auf der Auslastung optimieren.

<div>

## <a name="call-admission-control-considerations"></a>Überlegungen zur Anrufsteuerung

Der Administrator wählt aus, dass der Bandbreitenrichtliniendienst auf dem ersten Pool am zentralen Standort konfiguriert wird. Da es pro Netzwerkregion einen einzelnen zentralen Standort gibt, gibt es pro Netzwerkregion auch nur einen einzigen Bandbreitenrichtliniendienst, der die Bandbreitenrichtlinien für die entsprechende Region, die zugeordneten Standorte und die Links zu diesen Standorten verwaltet. Der bandbreitenrichtliniendienst wird als Teil der Front-End-Server ausgeführt, und daher ist eine höhere Verfügbarkeit innerhalb dieses Pools integriert. Der bandbreitenrichtliniendienst, der auf jedem Front-End-Server ausgeführt wird, synchronisiert alle 15 Sekunden. Wenn der Front-End-Pool ausfällt, werden die CAC-Richtlinien für diese Website erst dann erzwungen, wenn der Front-End-Pool und damit der bandbreitenrichtliniendienst wieder in Betrieb genommen wird. Das bedeutet, dass während der Zeit, in der der Bandbreitenrichtliniendienst ausfällt, alle Anrufe durchgehen. Aus diesem Grund besteht in diesem Zeitraum die Möglichkeit einer zu hohen Bandbreitenbelegung Ihrer Links.

Der bandbreitenrichtliniendienst bietet eine große Verfügbarkeit innerhalb eines Front-End-Pools. Es bietet jedoch keine Redundanz über Front-End-Pools. Der bandbreitenrichtliniendienst kann nicht von einem Front-End-Pool zu einem anderen Failover. Nachdem der Service für den Front-End-Pool wiederhergestellt wurde, wird der bandbreitenrichtliniendienst fortgesetzt und kann die Überprüfung der Bandbreitenrichtlinien erneut erzwingen.

<div>

## <a name="network-considerations"></a>Überlegungen zum Netzwerk

Obwohl die Bandbreitenbeschränkung für Audio und Video vom bandbreitenrichtliniendienst in lync Server 2013 erzwungen wird, wird diese Einschränkung beim Netzwerkrouter nicht erzwungen (Layer 2 und 3). Lync Server 2010 CAC kann eine Daten Anwendung beispielsweise nicht daran hindern, die gesamte Netzwerkbandbreite einer WAN-Verbindung zu nutzen, einschließlich der Bandbreite, die von ihrer CAC-Richtlinie für Audio und Video reserviert ist. Um sicherzustellen, dass die erforderliche Bandbreite in Ihrem Netzwerk reserviert wird, können Sie ein QoS-Protokoll (Quality of Service) wie Differenzierte Dienste (DiffServ) bereitstellen. Daher empfiehlt es sich, die definierten Bandbreitenrichtlinien der Anrufsteuerung auf QoS-Einstellungen abzustimmen, die Sie gegebenenfalls bereitstellen.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Medien- und Signalpfade über ein VPN

Wenn Ihr Unternehmen die Medienübermittlung über ein VPN unterstützt, müssen Sie sicherstellen, dass sowohl der Medien- als auch der Signaldatenstrom über das VPN verarbeitet werden bzw. beide Datenströme über das Internet geroutet werden. In der Standardeinstellung werden die Medien- und Signaldatenströme durch den VPN-Tunnel verarbeitet.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Anrufsteuerung für externe Benutzer

Die Anrufsteuerung wird nicht für Remotebenutzer erzwungen, bei denen der Netzwerkdatenverkehr über das Internet fließt. Da der Mediendatenverkehr das Internet durchläuft, das nicht von lync Server verwaltet wird, kann CAC nicht angewendet werden. Für den Teil des Anrufs, der über das Unternehmensnetzwerk fließt, werden jedoch CAC-Prüfungen durchgeführt.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Anrufsteuerung für PSTN-Verbindungen

Die Anrufsteuerung ist auf dem Vermittlungs Server unabhängig davon durchsetzbar, ob Sie mit einer IP/PBX-Anlage, einem PSTN-Gateway oder einem SIP-Trunk verbunden ist. Da es sich bei dem Vermittlungs Server um einen Back-to-Back-Benutzer-Agent (B2BUA) handelt, wird der Mediendienst beendet. Es hat zwei Verbindungsseiten: eine Seite, die mit dem lync-Server verbunden ist, und eine Gatewayseite, die mit PSTN-Gateways, IP/PBX-Anlagen oder SIP-Stämmen verbunden ist. Details zu PSTN-Verbindungen finden Sie unter [Planen der PSTN-Konnektivität in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

CAC kann auf beiden Seiten des Vermittlungsservers erzwungen werden, es sei denn, die medienumgehung ist aktiviert. Wenn die medienumgehung aktiviert ist, wird der Mediendatenverkehr nicht durch den Vermittlungs Server durchlaufen, sondern direkt zwischen dem lync-Client und dem Gateway. In diesem Fall wird die Anrufsteuerung nicht benötigt. Ausführliche Informationen finden Sie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

Die folgende Abbildung zeigt, wie die Anrufsteuerung für PSTN-Verbindungen mit und ohne Medienumgehung erzwungen wird.

**Erzwingen der Anrufsteuerung für Verbindungen mit dem PSTN**

![Voice CAC Media Bypass-Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass-Verbindungserzwingung")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Kompatibilität der Anrufsteuerung mit früheren Versionen von Office Communications Server

Die Anrufsteuerung kann nur auf Endpunkten aktiviert werden, die für lync Server 2010 und höher aktiviert sind.

Die Anrufsteuerung kann auf Endpunkten mit Office Communicator 2007 R2 oder früheren Versionen nicht aktiviert werden.

**Anwendung von CAC in verschiedenen lync Server-Versionen**

![Sprach-CAC-Versionsvergleichs Diagramm](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Sprach-CAC-Versionsvergleichs Diagramm")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

