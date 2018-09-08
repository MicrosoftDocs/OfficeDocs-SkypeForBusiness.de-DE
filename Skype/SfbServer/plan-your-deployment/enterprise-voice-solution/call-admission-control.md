---
title: Plan für die anrufsteuerung in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Lernen Sie die anrufsteuerung, die verhindern kann Anrufe von stattfinden, wenn schlechte Medienqualität in Skype für Business Server Enterprise-VoIP vorhanden wäre.
ms.openlocfilehash: db4b2f7a77885ff96a4b43b01aa2337996418217
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883851"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Plan für die anrufsteuerung in Skype für Business Server

Lernen Sie die anrufsteuerung, die verhindern kann Anrufe von stattfinden, wenn schlechte Medienqualität in Skype für Business Server Enterprise-VoIP vorhanden wäre.

In LAN-Umgebungen stellt die verfügbare Bandbreite von Unternehmensnetzwerken für IP-basierte Anwendungen wie zum Beispiel Telefonie, Video und Anwendungsfreigabe im Allgemeinen keine Einschränkung dar. Wenn Standorte jedoch über ein WAN verbunden sind, kann die Bandbreite eingeschränkt sein.

Wird eine WAN-Verbindung durch übermäßig hohen Netzwerkdatenverkehr überlastet, werden aktuelle Mechanismen wie Queuing, Pufferung und das Verwerfen von Paketen eingesetzt, um das Problem zu lösen. Der zusätzliche Datenverkehr wird üblicherweise verzögert, bis die Überlastung aufgehoben ist, oder gegebenenfalls verworfen. Bei herkömmlichem Datenverkehr kann der Empfängerclient die Daten in solchen Situationen wiederherstellen. Bei Echtzeitdatenverkehr wie Unified Communications lässt sich eine Netzwerküberlastung nicht auf diese Weise beheben, da UC-Datenverkehr sowohl für Latenz als auch für Paketverluste anfällig ist. Eine Überlastung des WAN kann zu einer unzureichenden Erlebnisqualität für Benutzer führen. Bei Echtzeitdatenverkehr in überlasteten Netzwerken ist es besser, Anrufe abzuweisen, als Verbindungen mit schlechter Qualität zuzulassen.

Die Anrufsteuerung (Call Admission Control, CAC) ermittelt, ob ausreichend Netzwerkbandbreite für eine Echtzeitsitzung in akzeptabler Qualität vorhanden ist. In Skype für Business Server CAC steuert in Echtzeit-Datenverkehr nur für Audio und Video, aber es wirkt sich nicht Datenübertragungen. Wenn der WAN-Standardpfad nicht die erforderliche Bandbreite aufweist, kann die Anrufsteuerung versuchen, den Anruf über einen Internetpfad oder das Festnetz zu leiten.

In diesem Abschnitt wird die Funktionsweise der Anrufsteuerung beschrieben und es wird erläutert, wie die Anrufsteuerung geplant werden kann.

> [!NOTE]
> Skype für Business Server verfügt über drei erweiterten Enterprise-VoIP-Funktionen: anrufsteuerung (CAC), notrufdienste (E9-1-1), und die medienumgehung. Eine Übersicht über die Planung von Informationen, die alle drei dieser Features gemeinsam ist, finden Sie unter [Netzwerkeinstellungen für den erweiterten Enterprise-VoIP-Funktionen in Skype für Business Server](network-settings-for-advanced-features.md).

Der Entwurf CAC in Skype für Business Server bietet die folgenden vier wesentlichen Attribute:

- Sie lässt sich problemlos bereitstellen und verwalten, ohne dass zusätzliche Geräte (z. B. speziell konfigurierte Router) erforderlich sind.

- Sie eignet sich für wichtige Unified Communications-Anwendungsfälle, z. B. für Roamingbenutzer und für die Anmeldung auf mehreren Geräten. Anrufsteuerungsrichtlinien werden nicht abhängig davon erzwungen, wo der Benutzer verwaltet wird, sondern basierend auf dem Standort des Endpunkts.

- Zusätzlich zu VoIP-Anrufen kann die Anrufsteuerung auf andere Typen von Datenverkehr angewendet werden, z. B. auf Videoanrufe und Audio/Video-Konferenzsitzungen.

- Dies bietet die Flexibilität, verschiedene Arten von Netzwerktopologien darstellen zu können.

Wenn eine neue VoIP- oder Videositzung die festgelegten Bandbreiteneinschränkungen einer WAN-Leitung überschreitet, wird die Sitzung entweder blockiert oder (dies gilt nur für Telefonanrufe) an das Festnetz umgeleitet.

Mit der Anrufsteuerung wird lediglich Echtzeitdatenverkehr für VoIP- und Videoanrufe gesteuert. Anderer Datenverkehr wird nicht gesteuert.

Administratoren definieren CAC-Richtlinien, die durch den Bandbreitenrichtliniendienst erzwungen werden, die mit jedem Front-End-Pool installiert ist. CAC Einstellungen werden automatisch auf alle Skype für Business Server-Front-End-Server in Ihrem Netzwerk übertragen.

Bei Anrufen, die aufgrund von Anrufsteuerungsrichtlinien nicht erfolgreich durchgeführt werden können, gilt folgende Reihenfolge für die Anrufumleitung:

1. Internet

2. Telefonfestnetz (PSTN)

3. Voicemail

Bei der Aufzeichnung von Kommunikationsdatensätzen werden Informationen zu Anrufen erfasst, die an das Festnetz oder an einen Voicemaildienst umgeleitet werden. Da das Internet nicht als sekundäre Option, sondern als alternativer Pfad behandelt wird, werden bei der Aufzeichnung von Kommunikationsdatensätzen keine Informationen zu Anrufen erfasst, die an das Internet umgeleitet werden.

> [!NOTE]
> Das Hinterlassen von Voicemails wird aufgrund von Bandbreitenbeschränkungen nicht abgelehnt.

Der Bandbreitenrichtliniendienst generiert zwei Typen von Protokolldateien im CSV-Format (durch Trennzeichen getrennte Datei). In der Protokolldatei für **Fehler bei der Überprüfung** werden Informationen erfasst, wenn Bandbreitenanforderungen abgelehnt werden. In der Protokolldatei zur **Verbindungsauslastung** werden ein Snapshot der Netzwerktopologie sowie die Bandbreitenauslastung der WAN-Verbindung erfasst. Unter Verwendung dieser beiden Protokolldateien können Sie Ihre Anrufsteuerungsrichtlinien basierend auf der Auslastung optimieren.

## <a name="call-admission-control-considerations"></a>Überlegungen zur Anrufsteuerung

Der Administrator wählt aus, dass der Bandbreitenrichtliniendienst auf dem ersten Pool am zentralen Standort konfiguriert wird. Da es pro Netzwerkregion einen einzelnen zentralen Standort gibt, gibt es pro Netzwerkregion auch nur einen einzigen Bandbreitenrichtliniendienst, der die Bandbreitenrichtlinien für die entsprechende Region, die zugeordneten Standorte und die Links zu diesen Standorten verwaltet. Den Bandbreitenrichtliniendienst als Teil der Front-End-Server ausgeführt wird, und aus diesem Grund ist hoher Verfügbarkeit in diesem Pool integriert. Den Bandbreitenrichtliniendienst auf jedem Front-End-Server ausgeführt werden alle 15 Sekunden synchronisiert. Wenn der Front-End-Pool ausfällt, anrufsteuerungsrichtlinien werden bis zu den Front-End-Pool nicht mehr für diese Website umgesetzt und daher den Bandbreitenrichtliniendienst wieder betriebsbereit. Das bedeutet, dass während der Zeit, in der der Bandbreitenrichtliniendienst ausfällt, alle Anrufe durchgehen. Aus diesem Grund besteht in diesem Zeitraum die Möglichkeit einer zu hohen Bandbreitenbelegung Ihrer Links.

Die Bandbreitenrichtliniendienst bietet hohen Verfügbarkeit in einem Front-End-Pool. Es wird jedoch kein Redundanz über Front-End-Pools bereitgestellt. Die Bandbreitenrichtliniendienst kann nicht Failover von einem Front-End-Pool in einen anderen. Nachdem der Dienst auf den Front-End-Pool wiederhergestellt wird, wird der Bandbreitenrichtliniendienst fortgesetzt wird und Bandbreite Richtlinie Prüfungen erneut erzwingen kann.

### <a name="network-considerations"></a>Überlegungen zum Netzwerk

Obwohl die Einschränkung der Bandbreite für Audio- und Videofunktionen für Business Server durch den Bandbreitenrichtliniendienst in Skype erzwungen wird, wird diese Einschränkung nicht am Netzwerkrouter (Layer 2 und 3) erzwungen. Mithilfe der Anrufsteuerung kann nicht verhindert werden, dass z. B. eine Datenanwendung die gesamte Netzwerkbandbreite einer WAN-Leitung belegt (einschließlich der Bandbreite, die durch Ihre Anrufsteuerungsrichtlinie für Audio und Video reserviert ist). Um sicherzustellen, dass die erforderliche Bandbreite in Ihrem Netzwerk reserviert wird, können Sie ein QoS-Protokoll (Quality of Service) wie Differenzierte Dienste (DiffServ) bereitstellen. Daher empfiehlt es sich, die definierten Bandbreitenrichtlinien der Anrufsteuerung auf QoS-Einstellungen abzustimmen, die Sie gegebenenfalls bereitstellen.

### <a name="media-and-signaling-paths-over-vpn"></a>Medien- und Signalpfade über ein VPN

Wenn Ihr Unternehmen die Medienübermittlung über ein VPN unterstützt, müssen Sie sicherstellen, dass sowohl der Medien- als auch der Signaldatenstrom über das VPN verarbeitet werden bzw. beide Datenströme über das Internet geroutet werden. In der Standardeinstellung werden die Medien- und Signaldatenströme durch den VPN-Tunnel verarbeitet.

### <a name="call-admission-control-of-outside-users"></a>Anrufsteuerung für externe Benutzer

Call Admission Control nicht über die Grenzen eines der Skype für Business Server Organisation erzwungen wird. CAC kann nicht angewendet werden, zu der Mediendatenverkehr Traversieren im Internet, die nicht von Skype für Business Server verwaltet wird. CAC Prüfungen auf den Teil des Anrufs, die über das Unternehmensnetzwerk fließt Zugehörigkeit gewählte Endpunkts für die Organisation ausgeführt werden, und der Edge-Server hinzugefügt wurde die Netzwerkkonfiguration gemäß [die anrufsteuerung Bereitstellung: endgültige Checkliste für Skype für Business Server](../../deploy/deploy-enterprise-voice/final-checklist.md). Wenn der angerufene Endpunkt nicht zur Organisation gehört, wie beispielsweise ein Partnerverbund- oder PIC-Benutzer, werden keine Überprüfungen der Bandbreitenrichtlinie durchgeführt und beim ausgehenden Anruf werden alle Beschränkungen der Anrufsteuerung ignoriert.

### <a name="call-admission-control-of-pstn-connections"></a>Anrufsteuerung für PSTN-Verbindungen

Die anrufsteuerung ist durchsetzbar auf dem Vermittlungsserver, unabhängig davon, ob sie mit einer IP-PBX, ein PSTN-Gateway oder einen SIP-Trunk verbunden ist. Da der Vermittlungsserver eine Back-Benutzer-Agent (B2BUA) ist, Medien beendet wird. Es hat zwei Connection-Seiten: eine Seite, die mit Skype verbunden ist, für die Business Server und einem Gateway-Seite, die mit PSTN-Gateways, IP-Nebenstellenanlagen oder SIP-Trunks verbunden ist. Ausführliche Informationen zu PSTN-Verbindungen finden Sie unter [Planen der PSTN-Konnektivität in Skype für Business Server](pstn-connectivity-0.md).

CAC kann auf beiden Seiten des Vermittlungsservers erzwungen werden, es sei denn, die medienumgehung aktiviert ist. Wenn die medienumgehung aktiviert ist, der Mediendatenverkehr den Vermittlungsserver durchlaufen nicht jedoch stattdessen direkt zwischen den Skype für Business-Client und dem Gateway fließt. In diesem Fall wird die Anrufsteuerung nicht benötigt. Weitere Informationen hierzu finden Sie unter [Plan für Medien in Skype für Unternehmen zu umgehen](media-bypass.md).

Die folgende Abbildung zeigt, wie die Anrufsteuerung für PSTN-Verbindungen mit und ohne Medienumgehung erzwungen wird.

**Erzwingen der Anrufsteuerung für Verbindungen mit dem PSTN**

![VoIP-Anrufsteuerung: Medienumgehung – Verbindungserzwingung](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung

Zur Planung der Anrufsteuerung (Call Admission Control, CAC) sind detaillierte Informationen zur Netzwerktopologie Ihres Unternehmens erforderlich. Führen Sie die folgenden Schritte aus, um Richtlinien für die Anrufsteuerung zu planen.

1. Identifizieren Sie die Hubs/Backbones (als Netzwerkregionen bezeichnet) in Ihrem Unternehmensnetzwerk.

2. Identifizieren Sie die Niederlassungen oder Standorte (als Netzwerkstandorte bezeichnet) innerhalb jeder Netzwerkregion.

3. Definieren Sie eine Netzwerkroute zwischen jedem Netzwerkregionenpaar.

4. Ermitteln Sie die Bandbreiteneinschränkungen für jede WAN-Verbindung.

    > [!NOTE]
    > Bandbreiteneinschränkungen finden Sie unter wie viel Bandbreite für eine WAN-Verbindung Enterprise-VoIP und Audio/Video-Datenverkehr zugewiesen wird. Wenn eine WAN-Verbindung als "bandbreiteneinschränkungen" beschrieben wird, ist die WAN-Verbindung Bandbreite begrenzt, die niedriger als die erwartete maximale Datenverkehr über dem Hyperlink befindet.

5. Identifizieren Sie die IP-Subnetze, die jedem Netzwerkstandort zugewiesen sind.

Zur Erläuterung dieser Konzepte, verwenden wir die Beispiel-Netzwerktopologie in der folgenden Abbildung dargestellt.

**Beispieltopologie für die Anrufsteuerung**

![Litware Inc.: Netzwerktopologiebeispiel](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Alle Netzwerkstandorte sind einer Netzwerkregion zugeordnet. Beispielsweise sind die Standorte „Portland“, „Reno“ und „Albuquerque“ in der Region „Nordamerika“ enthalten. In dieser Abbildung werden nur WAN-Verbindungen mit Bandbreiteneinschränkungen gezeigt, auf die Anrufsteuerungsrichtlinien angewendet werden. Die Netzwerkstandorte „Chicago“, „New York“ und „Detroit“ werden innerhalb des Regionenovals „Nordamerika“ angezeigt, da sie keine Bandbreiteneinschränkungen aufweisen und für diese Standorte daher keine Richtlinien für die Anrufsteuerung erforderlich sind.

Die Komponenten in dieser Beispieltopologie werden in den folgenden Abschnitten erläutert. Ausführliche Informationen zum wie diese Topologie, einschließlich der bandbreiteneinschränkungen geplant wurde finden [Beispiel: Sammeln von Anforderungen für die anrufsteuerung in Skype für Business Server](example-gathering-requirements.md).

### <a name="identify-network-regions"></a>Identifizieren der Netzwerkregionen

Eine Netzwerkregion steht für einen Netzwerkbackbone oder einen Netzwerkhub.

Ein Netzwerkbackbone oder -hub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.

Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält eine Reihe von Netzwerkstandorten (siehe Definition in diesem Thema). Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verwendeten Netzwerkregionen zu identifizieren.

### <a name="associating-a-central-site-with-each-network-region"></a>Zuordnen eines zentralen Standorts zu jeder Netzwerkregion

CAC erfordert, dass eine Skype für Business Server zentralen Standort für jede netzwerkregion definiert ist. Ausgewählt wird der zentrale Standort, der die beste Netzwerkverbindung und die höchste Bandbreite aller Standorte in dieser Netzwerkregion bietet. In der oben gezeigten beispielhaften Netzwerktopologie sind drei Netzwerkregionen aufgeführt, jede mit einem zentralen Standort zur Verwaltung der Entscheidungen im Rahmen der Anrufsteuerung. Die geeignete Zuordnung für das vorangehende Beispiel wird in der folgenden Tabelle gezeigt.

> [!NOTE]
> Zentrale Standorte entsprechen nicht unbedingt zu Netzwerkstandorten. In den Beispielen in dieser Dokumentation, einige zentrale Standorte – Chicago, London und Peking – den gleichen Namen wie der Netzwerkstandorte freigeben. Auch wenn Sie einen zentralen Standort und Netzwerkstandort denselben Namen aufweisen, ist jedoch am zentrale Standort ein Element von der Skype für Business Server-Topologie der Netzwerkstandort ein Teil des gesamten Netzwerks ist in der sich die Skype für Business Server-Topologie befindet.

**Netzwerkregionen, zentrale Standorte und Netzwerkstandorte**

|**Netzwerkregion**|**Zentraler Standort**|**Netzwerkstandorte**|
|:-----|:-----|:-----|
|Nordamerika  <br/> |Chicago  <br/> |Chicago  <br/> New York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |London  <br/> |London  <br/> Köln  <br/> |
|APAC  <br/> |Peking  <br/> |Peking  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identifizieren von Netzwerkstandorten

Ein Netzwerkstandort ist ein Ort, an dem Ihre Organisation über Büros, einen Gebäudekomplex oder ein Gelände verfügt. Ein physischer Standort mit einem LAN und einer WAN-Verbindung zu anderen Standorten wird als Netzwerkstandort klassifiziert. Starten Sie, indem Bestandsaufnahme aller Ihrer Organisation Büros. In der verwendeten Beispieltopologie umfasst die Netzwerkregion „Nordamerika“ die folgenden Netzwerkstandorte: New York, Chicago, Detroit, Portland, Reno und Albuquerque.

Sie müssen jeden Netzwerkstandort einer Netzwerkregion zuordnen. Abhängig davon, ob der Netzwerkstandort über eine eingeschränkte WAN-Verbindung verfügt oder nicht, wird dem Netzwerkstandort eine Bandbreitenrichtlinie zugeordnet. Ausführliche Informationen zu Anrufsteuerungsrichtlinien und der Bandbreite, die Sie über die Richtlinienverwendung zuweisen, finden Sie im Abschnitt „Definieren von Bandbreitenrichtlinien“ weiter unten in diesem Thema. Zum Konfigurieren der Anrufsteuerung ordnen Sie Netzwerkstandorte Netzwerkregionen zu. Anschließend erstellen Sie Richtlinien zur Bandbreitenzuweisung, die auf zwischen Standorten und Regionen bestehende Verbindungen mit Bandbreiteneinschränkungen und WAN-Verbindungen angewendet werden.

### <a name="identify-network-links"></a>Identifizieren von Netzwerkverbindungen

Netzwerkverbindungen sind Verbindungen zu einem physischen WAN, das unterschiedliche Regionen und Standorte verknüpft. In der Beispieltopologie sind zwei regionale Netzwerkverbindungen, fünf Netzwerkverbindungen zwischen Regionen und Standorten sowie eine Netzwerkverbindung zwischen zwei Standorten enthalten.

Die zwei regionalen Verbindungen befinden sich zwischen „Nordamerika“ und „EMEA“, dargestellt als „NA-EMEA-LINK“, und zwischen „APAC“ und „EMEA“, dargestellt als „EMEA-APAC-LINK“.

Die Standortverbindungen kennzeichnen die Leitungen zur Verbindung von „Portland“, „Reno“ und „Albuquerque“ mit der Region „Nordamerika“, zur Verbindung von „Manila“ mit der Region „APAC“ und zur Verbindung von „Köln“ mit der Region „EMEA“. Die Verbindung zwischen „Reno“ und „Albuquerque“ kennzeichnet eine direkte Netzwerkverbindung zwischen diesen zwei Standorten.

### <a name="define-bandwidth-policies"></a>Definieren von Bandbreitenrichtlinien

Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verfügbare WAN-Bandbreite für in Echtzeit übertragenen Audio- und Videodatenverkehr über die WAN-Verbindungen in Ihrer Organisation zu ermitteln. Bandbreitenrichtlinien werden üblicherweise auf WAN-Verbindungen angewendet, wenn die Bandbreite eingeschränkt ist, wenn also der erwartete Datenverkehr die Bandbreite übersteigt, die für Audio- und Videodaten zugewiesen werden kann.

Bandbreitenrichtlinien für die Anrufsteuerung definieren, wie viel Bandbreite für in Echtzeit übertragene Audio- und Videodaten reserviert ist. Da die Bandbreite für anderen Datenverkehr bei der Anrufsteuerung nicht begrenzt wird, kann nicht verhindert werden, dass dieser die gesamte Netzwerkbandbreite durch Aktionen wie das Übertragen großer Dateien oder das Streamen von Musik beansprucht.

Bandbreitenrichtlinien für die Anrufsteuerung können einige oder alle der folgenden Werte definieren:

- Maximal reservierte Gesamtbandbreite für Audiodaten

- Maximal reservierte Gesamtbandbreite für Videodaten

- Maximal reservierte Bandbreite für einen einzelnen Audioanruf (Sitzung)

- Maximal reservierte Bandbreite für einen einzelnen Videoanruf (Sitzung)

> [!NOTE]
> Alle Bandbreitenwerte CAC die Grenzwerte für die maximale *unidirektional* Bandbreite.

> [!NOTE]
> Die Skype für Business Server VoIP-Richtlinie Features bieten die Möglichkeit, überschreiben bandbreitenrichtlinie prüft, ob eingehende Anrufe an den Benutzer (nicht für ausgehende Anrufe, die vom Benutzer befinden). Nachdem die Sitzung eingerichtet wurde, wird die Bandbreitenauslastung genau berechnet. Diese Einstellung sollte mit Bedacht verwendet werden. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Unternehmen](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) oder [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) in der Bereitstellungsdokumentation.

Zur Optimierung der Bandbreitenauslastung auf Sitzungsebene sollten Sie sich Gedanken über die verwendeten Audio- und Videocodecs machen. Vermeiden Sie insbesondere eine zu geringe Bandbreitenzuweisung für einen Codec, der erwartungsgemäß häufig verwendet wird. Umgekehrt sollten Sie die maximale Bandbreite pro Sitzung sehr niedrig ansetzen, wenn Sie verhindern möchten, dass für Mediendaten ein Codec mit hohen Bandbreitenanforderungen verwendet wird. Für Audiodaten ist nicht jeder Codec für jedes Szenario verfügbar. Beispiel:

- Peer-zu-Peer-Audioanrufe zwischen Skype für Business-Endpunkte werden entweder RTAudio (8kHz) oder RTAudio (16kHz) verwenden, wenn Sie die Bandbreite und Priorisierung von Codecs berücksichtigen.

- Konferenzanrufe zwischen Skype für Business-Endpunkten und dem A / V-Konferenzdienst verwenden entweder g. 722 oder Siren.

- Anrufe an das öffentliche Telefonfestnetz (PSTN) oder von Skype für Business-Endpunkte verwenden entweder g. 711 oder RTAudio (8 kHz).

Verwenden Sie die folgende Tabelle, um die maximalen Bandbreiteneinstellungen pro Sitzung zu optimieren.

**Bandbreitenauslastung nach Codec**

|**Codec**|**Bandbreitenanforderung ohne Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)**|**Bandbreitenanforderung mit Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)**|
|:-----|:-----|:-----|
|RTAudio (8 KHz)  <br/> |49,8 KBit/s  <br/> |61,6 KBit/s  <br/> |
|RTAudio (16 kHz)  <br/> |67 KBit/s  <br/> |96 KBit/s  <br/> |
|Siren  <br/> |57,6 KBit/s  <br/> |73,6 KBit/s  <br/> |
|G. 711  <br/> |102 KBit/s  <br/> |166 KBit/s  <br/> |
|G. 722  <br/> |105,6 KBit/s  <br/> |169,6 KBit/s  <br/> |
|RTVideo (CIF mit 15 F/s)  <br/> |260 KBit/s  <br/> |Nicht zutreffend  <br/> |
|RTVideo (VGA mit 30 F/s)  <br/> |610 KBit/s  <br/> |Nicht zutreffend  <br/> |

> [!NOTE]
> Bandbreitenanforderungen berücksichtigen einen Overhead für: Ethernet II, IP, User Datagram Protocol (UDP), RTP (Real-Time Transport Protocol) und SRTP (Secure Real-Time Transport Protocol). Ebenfalls enthalten ist ein Overhead von 10 KBit/s für RTCP.

Die Codecs G.722.1 und Siren sind ähnlich, unterscheiden sich jedoch in den Bitraten.

G. 722, der Standardcodec für Skype für Business Server-Konferenzen, unterscheidet sich vollständig von der G.722.1 und Siren-Codec.

Der Siren-Codec wird in Skype für Business Server in den folgenden Situationen verwendet:

- Wenn die Bandbreitenrichtlinie zu niedrig festgelegt ist, um eine Verwendung von G.722 zuzulassen

- Wenn ein Communications Server 2007 oder Communications Server 2007 R2-Client (, da diese Clients den g. 722-Codec nicht unterstützen) mit einer Skype für Konferenzdienst Business Server verbunden ist.

**Bandbreitenauslastung nach Szenario**

|**Szenario**|**Bandbreitenanforderung für Menge optimiert (KBit/s)**|**Bandbreitenanforderung für Ausgleichsmodus optimiert (KBit/s)**|**Bandbreitenanforderung für Qualität optimiert (KBit/s)**|
|:-----|:-----|:-----|:-----|
|Peer-zu-Peer-Audioanrufe  <br/> |45 KBit/s  <br/> |62 KBit/s  <br/> |91 KBit/s  <br/> |
|Telefonkonferenz  <br/> |53 KBit/s  <br/> |101 KBit/s  <br/> |165 KBit/s  <br/> |
|PSTN-Anrufe (zwischen Skype für Geschäfts- und PSTN-Gateway, mit medienumgehung)  <br/> |97 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|PSTN-Anrufe zwischen (Skype für Unternehmen) und Vermittlungsserver, ohne medienumgehung  <br/> |45 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|PSTN-Anrufe (zwischen Vermittlungsserver und PSTN-Gateway, ohne medienumgehung)  <br/> |97 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|Skype für Unternehmen – ruft Polycom  <br/> |101 KBit/s  <br/> |101 KBit/s  <br/> |101 KBit/s  <br/> |

### <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Im hier verwendeten Beispiel sind dem Standort „New York“ in der Region „Nordamerika“ die folgenden IP-Subnetze zugewiesen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Angenommen, der Benutzer Bob, der üblicherweise in Detroit arbeitet, reist für eine Schulung in das New Yorker Büro. Wenn er seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für „New York“ reserviert sind, beispielsweise 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Einen Skype für Business-Client nimmt seine lokale IP-Adresse und die IP-Adresse mit der zugehörigen Subnetzmaske maskiert. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die anrufsteuerung bereitstellen, aber keine medienumgehung, die anrufsteuerung funktioniert, auch wenn Sie virtuelle Subnetze konfigurieren.) Beispielsweise wenn ein Client auf einem Computer mit der IP-Adresse 172.29.81.57 IP-Subnetzmaske 255.255.255.0 anmeldet, anfordern Skype für Unternehmen die umgehungs-ID zugeordnet Subnetz 172.29.81.0. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Aus diesem Grund ist es wichtig, dass der Administrator Subnetze gibt genau wie von Skype für Business Clients bereitgestellt wird (die mit Subnetze während der Netzwerkkonfiguration statisch oder von DHCP bereitgestellt werden.)

## <a name="best-practices-for-call-admission-control"></a>Bewährte Methoden für die Anrufsteuerung

Halten Sie sich bei der Bereitstellung der Anrufsteuerung an die folgenden bewährten Methoden, um die Leistung zu verbessern und die Bereitstellung zu vereinfachen:

- Stellen Sie sicher, dass WANs für den aktuellen und den erwarteten Mediendatenverkehr angemessen ausgelegt sind.

    > [!NOTE]
    > Es empfiehlt sich, bei der Bandbreiteneinschränkungen einen Puffer einzurechnen. Manche Szenarien, z. B. Racebedingungen, wirken sich auf die verwendete Gesamtbandbreite aus und können zu Situationen führen, in denen die Bandbreitengrenze überschritten wird. Wenn beispielsweise zwei Anrufe gestartet werden, während der Mediendatenverkehr sich einer Bandbreitengrenze nähert, wird möglicherweise einer der beiden Anrufe abgewiesen, weil der andere zuerst gestartet wurde.

- Überwachen Sie die Netzwerkbelegung und die Kommunikationsdatensätze, damit Sie die optimalen Einstellungen für die Anrufsteuerung wählen und diese bei Änderungen in der Netzwerkbelegung aktualisieren können.

- Verwenden Sie Richtlinien für die Anrufsteuerung zur Ergänzung der QoS-Einstellungen.

- Wenn Sie blockierte Anrufe zum PSTN umleiten möchten, überprüfen Sie die Funktionalität und die Kapazität des PSTN. Weitere Informationen hierzu finden Sie unter [Planen des Routings ausgehender Anrufe](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).

    > [!NOTE]
    > „Kapazität“ bezieht sich auf die Anzahl der Ports, die Sie zur Unterstützung einer möglichen PSTN-Umleitung öffnen müssen.


