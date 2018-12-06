---
title: 'Lync Server 2013: Übersicht über die Anrufsteuerung'
TOCTitle: Übersicht über die Anrufsteuerung
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398529(v=OCS.15)
ms:contentKeyID: 49294359
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Die Echtzeitkommunikation ist anfällig für Latenzprobleme und Paketverluste, wie sie bei überlasteten Netzwerken auftreten können. Mithilfe der Anrufsteuerung wird basierend auf der verfügbaren Netzwerkbandbreite festgelegt, ob Echtzeitkommunikationssitzungen (z. B. Sprach- oder Videoanrufe) hergestellt werden können. Die Anrufsteuerung in Lync Server 2013 ist durch vier Hauptmerkmale gekennzeichnet:

  - Sie lässt sich problemlos bereitstellen und verwalten, ohne dass zusätzliche Geräte (z. B. speziell konfigurierte Router) erforderlich sind.

  - Sie eignet sich für wichtige Unified Communications-Anwendungsfälle, z. B. für Roamingbenutzer und für die Anmeldung auf mehreren Geräten. Anrufsteuerungsrichtlinien werden nicht abhängig davon erzwungen, wo der Benutzer verwaltet wird, sondern basierend auf dem Standort des Endpunkts.

  - Zusätzlich zu VoIP-Anrufen kann die Anrufsteuerung auf andere Typen von Datenverkehr angewendet werden, z. B. auf Videoanrufe und Audio/Video-Konferenzsitzungen.

  - Dies bietet die Flexibilität, verschiedene Arten von Netzwerktopologien darstellen zu können. Beispiele finden Sie unter [Komponenten und Topologien für die Anrufsteuerung in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Wenn eine neue VoIP- oder Videositzung die festgelegten Bandbreiteneinschränkungen einer WAN-Leitung überschreitet, wird die Sitzung entweder blockiert oder (dies gilt nur für Telefonanrufe) an das Festnetz umgeleitet.

Mit der Anrufsteuerung wird lediglich Echtzeitdatenverkehr für VoIP- und Videoanrufe gesteuert. Anderer Datenverkehr wird nicht gesteuert.

Administratoren definieren Anrufsteuerungsrichtlinien, die durch den Bandbreitenrichtliniendienst erzwungen werden, der mit jedem Front-End-Pool installiert wird. Die Anrufsteuerungseinstellungen werden automatisch für alle Lync Server- Front-End-Server in Ihrem Netzwerk übernommen.

Für Anrufe, die aufgrund von Anrufsteuerungsrichtlinien nicht erfolgreich durchgeführt werden können, gilt folgende Reihenfolge für die Anrufumleitung:

1.  Internet

2.  Telefonfestnetz (PSTN)

3.  Voicemail

Bei der Aufzeichnung von Kommunikationsdatensätzen werden Informationen zu Anrufen erfasst, die an das Festnetz oder an einen Voicemaildienst umgeleitet werden. Da das Internet nicht als sekundäre Option, sondern als alternativer Pfad behandelt wird, werden bei der Aufzeichnung von Kommunikationsdatensätzen keine Informationen zu Anrufen erfasst, die an das Internet umgeleitet werden.


> [!NOTE]
> Das Hinterlassen von Voicemail wird aufgrund von Bandbreitenbeschränkungen nicht abgelehnt.



Der Bandbreitenrichtliniendienst generiert zwei Typen von Protokolldateien im CSV-Format (durch Trennzeichen getrennte Datei). In der Protokolldatei für Fehler bei der Überprüfung werden Informationen erfasst, wenn Bandbreitenanforderungen abgelehnt werden. In der Protokolldatei zur Verbindungsauslastung wird ein Snapshot der Netzwerktopologie sowie die Bandbreitenauslastung der WAN-Verbindung erfasst. Unter Verwendung dieser beiden Protokolldateien können Sie Ihre Anrufsteuerungsrichtlinien basierend auf der Auslastung optimierten.

## Überlegungen zur Anrufsteuerung

Der Administrator wählt aus, dass der Bandbreitenrichtliniendienst auf dem ersten Pool am zentralen Standort konfiguriert wird. Da es pro Netzwerkregion einen einzelnen zentralen Standort gibt, gibt es pro Netzwerkregion auch nur einen einzigen Bandbreitenrichtliniendienst, der die Bandbreitenrichtlinien für die entsprechende Region, die zugeordneten Standorte und die Links zu diesen Standorten verwaltet. Der Bandbreitenrichtliniendienst wird als Teil der Front-End-Server ausgeführt, sodass eine hohe Verfügbarkeit im entsprechenden Pool integriert ist. Der auf jedem einzelnen Front-End-Server ausgeführte Bandbreitenrichtliniendienst wird alle 15 Sekunden synchronisiert. Falls der Front-End-Pool ausfällt, werden die Anrufsteuerungsrichtlinien solange nicht mehr für den Standort erzwungen, bis der Front-End-Pool und damit einhergehend der Bandbreitenrichtliniendienst wieder in Betrieb sind. Das bedeutet, dass während der Zeit, in der der Bandbreitenrichtliniendienst ausfällt, alle Anrufe durchgehen. Aus diesem Grund besteht in diesem Zeitraum die Möglichkeit einer zu hohen Bandbreitenbelegung Ihrer Links.

Für den Bandbreitenrichtliniendienst ist eine hohe Verfügbarkeit innerhalb eines Front-End-Pools gewährleistet; er bietet jedoch keine Redundanz über sämtliche Front-End-Pools hinweg. Mit dem Bandbreitenrichtliniendienst ist keine Failover von einem Front-End-Pool auf einen anderen möglich. Sobald der Dienst für den Front-End-Pool wiederhergestellt ist, wird der Bandbreitenrichtliniendienst wieder aufgenommen und kann wieder Bandbreitenrichtlinienprüfungen durchführen.

## Überlegungen zum Netzwerk

Wenngleich Bandbreitenbeschränkungen für Audio und Video durch den Bandbreitenrichtliniendienst in Lync Server 2013 erzwungen werden, werden diese Beschränkungen nicht auf dem Netzwerkrouter (Layer 2 und 3) erzwungen. Mithilfe der Anrufsteuerung in Lync Server 2010 kann nicht verhindert werden, dass z. B. eine Datenanwendung die gesamte Netzwerkbandbreite einer WAN-Leitung belegt (einschließlich der Bandbreite, die durch Ihre Anrufsteuerungsrichtlinie für Audio und Video reserviert ist). Um sicherzustellen, dass die erforderliche Bandbreite in Ihrem Netzwerk reserviert wird, können Sie ein QoS-Protokoll (Quality of Service) wie differenzierte Dienste (DiffServ) bereitstellen. Daher empfiehlt es sich, die definierten Bandbreitenrichtlinien der Anrufsteuerung auf QoS-Einstellungen abzustimmen, die Sie gegebenenfalls bereitstellen.

## Medien- und Signalpfade über ein VPN

Wenn Ihr Unternehmen die Medienübermittlung über ein VPN unterstützt, müssen Sie sicherstellen, dass sowohl der Medien- als auch der Signaldatenstrom über das VPN verarbeitet werden bzw. beide Datenströme über das Internet geroutet werden. In der Standardeinstellung werden die Medien- und Signaldatenströme durch den VPN-Tunnel verarbeitet.

## Anrufsteuerung für externe Benutzer

Die Anrufsteuerung wird für Remotebenutzer nicht erzwungen, bei denen der Netzwerkdatenverkehr über das Internet verarbeitet wird. Da der Mediendatenverkehr über das Internet geleitet wird und somit nicht durch Lync Server verwaltet werden kann, kann die Anrufsteuerung nicht angewendet werden. Für den Teil des Anrufs, der über das Unternehmensnetzwerk verarbeitet wird, werden jedoch Überprüfungen der Anrufsteuerung ausgeführt.

## Anrufsteuerung für PSTN-Verbindungen

Die Anrufsteuerung kann auf dem Vermittlungsserver unabhängig davon erzwungen werden, ob dieser mit einer IP-Nebenstellenanlage, einem PSTN-Gateway oder einem SIP-Trunk verbunden ist. Da es sich beim Vermittlungsserver um einen B2BUA-Server (Back-to-Back User Agent) handelt, dient er als Endpunkt für die Mediendaten. Der Server verfügt über zwei Verbindungen: Auf der einen Seite ist der Server mit Lync Server, auf der Gatewayseite mit PSTN-Gateways, IP-Nebenstellenanlagen oder SIP-Trunks verbunden. Ausführliche Informationen zu PSTN-Verbindungen finden Sie unter [Planen der PSTN-Konnektivität in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

Sofern keine Medienumgehung aktiviert ist, kann die Anrufsteuerung auf beiden Seiten des Vermittlungsservers erzwungen werden. Wenn die Medienumgehung aktiviert ist, wird der Mediendatenverkehr nicht über den Vermittlungsserver verarbeitet, sondern direkt zwischen dem Lync-Client und dem Gateway übermittelt. In diesem Fall wird die Anrufsteuerung nicht benötigt. Ausführliche Informationen finden Sie unter [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

Die folgende Abbildung zeigt, wie die Anrufsteuerung für PSTN-Verbindungen mit und ohne Medienumgehung erzwungen wird.

**Erzwingen der Anrufsteuerung für Verbindungen mit dem Festnetz**

![VoIP-Anrufsteuerung: Medienumgehung – Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "VoIP-Anrufsteuerung: Medienumgehung – Verbindungserzwingung")

## Kompatibilität der Anrufsteuerung mit früheren Versionen von Office Communications Server

Die Anrufsteuerung kann nur auf Endpunkten aktiviert werden, die für Lync Server 2010 und höher aktiviert sind.

Auf Endpunkten, die für Office Communicator 2007 R2 oder früher aktiviert sind, kann die Anrufsteuerung nicht aktiviert werden.

**Anwendung der Anrufsteuerung auf verschiedenen Lync Server-Versionen**

![VoIP-Anrufsteuerung – Versionsvergleich (Diagramm)](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "VoIP-Anrufsteuerung – Versionsvergleich (Diagramm)")

