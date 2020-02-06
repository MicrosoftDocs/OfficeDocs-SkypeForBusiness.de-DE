---
title: Planen der Anrufsteuerung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Informieren Sie sich über die Anrufsteuerung, mit der Sie in Skype for Business Server Enterprise-VoIP verhindern können, dass Anrufe stattfinden, wenn Sie schlechte Medienqualität aufweisen.
ms.openlocfilehash: 33aad955d0d1c592900683213a13e50433265a10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803235"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Planen der Anrufsteuerung in Skype for Business Server

Informieren Sie sich über die Anrufsteuerung, mit der Sie in Skype for Business Server Enterprise-VoIP verhindern können, dass Anrufe stattfinden, wenn Sie schlechte Medienqualität aufweisen.

In LAN-Umgebungen stellt die verfügbare Bandbreite von Unternehmensnetzwerken für IP-basierte Anwendungen wie zum Beispiel Telefonie, Video und Anwendungsfreigabe im Allgemeinen keine Einschränkung dar. Wenn Standorte jedoch über ein WAN verbunden sind, kann die Bandbreite eingeschränkt sein.

Wird eine WAN-Verbindung durch übermäßig hohen Netzwerkdatenverkehr überlastet, werden aktuelle Mechanismen wie Queuing, Pufferung und das Verwerfen von Paketen eingesetzt, um das Problem zu lösen. Der zusätzliche Datenverkehr wird üblicherweise verzögert, bis die Überlastung aufgehoben ist, oder gegebenenfalls verworfen. Bei herkömmlichem Datenverkehr kann der Empfängerclient die Daten in solchen Situationen wiederherstellen. Bei Echtzeitdatenverkehr wie Unified Communications lässt sich eine Netzwerküberlastung nicht auf diese Weise beheben, da UC-Datenverkehr sowohl für Latenz als auch für Paketverluste anfällig ist. Eine Überlastung des WAN kann zu einer unzureichenden Erlebnisqualität für Benutzer führen. Bei Echtzeitdatenverkehr in überlasteten Netzwerken ist es besser, Anrufe abzuweisen, als Verbindungen mit schlechter Qualität zuzulassen.

Die Anrufsteuerung (Call Admission Control, CAC) ermittelt, ob ausreichend Netzwerkbandbreite für eine Echtzeitsitzung in akzeptabler Qualität vorhanden ist. In Skype for Business Server steuert CAC den Echtzeitverkehr nur für Audio und Video, hat aber keinen Einfluss auf den Datenverkehr. Wenn der WAN-Standardpfad nicht die erforderliche Bandbreite aufweist, kann die Anrufsteuerung versuchen, den Anruf über einen Internetpfad oder das Festnetz zu leiten.

In diesem Abschnitt wird die Funktionsweise der Anrufsteuerung beschrieben und es wird erläutert, wie die Anrufsteuerung geplant werden kann.

> [!NOTE]
> Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP-Features: Anrufannahme Steuerung (CAC), Notfalldienste (E9-1-1) und medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei Features üblich sind, finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server](network-settings-for-advanced-features.md).

Das CAC-Design in Skype for Business Server bietet vier Hauptattribute:

- Sie lässt sich problemlos bereitstellen und verwalten, ohne dass zusätzliche Geräte (z. B. speziell konfigurierte Router) erforderlich sind.

- Sie eignet sich für wichtige Unified Communications-Anwendungsfälle, z. B. für Roamingbenutzer und für die Anmeldung auf mehreren Geräten. Anrufsteuerungsrichtlinien werden nicht abhängig davon erzwungen, wo der Benutzer verwaltet wird, sondern basierend auf dem Standort des Endpunkts.

- Zusätzlich zu VoIP-Anrufen kann die Anrufsteuerung auf andere Typen von Datenverkehr angewendet werden, z. B. auf Videoanrufe und Audio/Video-Konferenzsitzungen.

- Dies bietet die Flexibilität, verschiedene Arten von Netzwerktopologien darstellen zu können.

Wenn eine neue VoIP- oder Videositzung die festgelegten Bandbreiteneinschränkungen einer WAN-Leitung überschreitet, wird die Sitzung entweder blockiert oder (dies gilt nur für Telefonanrufe) an das Festnetz umgeleitet.

Mit der Anrufsteuerung wird lediglich Echtzeitdatenverkehr für VoIP- und Videoanrufe gesteuert. Anderer Datenverkehr wird nicht gesteuert.

Administratoren definieren CAC-Richtlinien, die vom bandbreitenrichtliniendienst erzwungen werden, der mit jedem Front-End-Pool installiert wird. Die CAC-Einstellungen werden automatisch an alle Skype for Business Server-Front-End-Server in Ihrem Netzwerk weitergegeben.

Bei Anrufen, die aufgrund von Anrufsteuerungsrichtlinien nicht erfolgreich durchgeführt werden können, gilt folgende Reihenfolge für die Anrufumleitung:

1. Internet

2. Telefonfestnetz (PSTN)

3. Voicemail

Bei der Aufzeichnung von Kommunikationsdatensätzen werden Informationen zu Anrufen erfasst, die an das Festnetz oder an einen Voicemaildienst umgeleitet werden. Da das Internet nicht als sekundäre Option, sondern als alternativer Pfad behandelt wird, werden bei der Aufzeichnung von Kommunikationsdatensätzen keine Informationen zu Anrufen erfasst, die an das Internet umgeleitet werden.

> [!NOTE]
> Das Hinterlassen von Voicemails wird aufgrund von Bandbreitenbeschränkungen nicht abgelehnt.

Der Bandbreitenrichtliniendienst generiert zwei Typen von Protokolldateien im CSV-Format (durch Trennzeichen getrennte Datei). In der Protokolldatei für **Fehler bei der Überprüfung** werden Informationen erfasst, wenn Bandbreitenanforderungen abgelehnt werden. In der Protokolldatei zur **Verbindungsauslastung** werden ein Snapshot der Netzwerktopologie sowie die Bandbreitenauslastung der WAN-Verbindung erfasst. Unter Verwendung dieser beiden Protokolldateien können Sie Ihre Anrufsteuerungsrichtlinien basierend auf der Auslastung optimieren.

## <a name="call-admission-control-considerations"></a>Überlegungen zur Anrufsteuerung

Der Administrator wählt aus, dass der Bandbreitenrichtliniendienst auf dem ersten Pool am zentralen Standort konfiguriert wird. Da es pro Netzwerkregion einen einzelnen zentralen Standort gibt, gibt es pro Netzwerkregion auch nur einen einzigen Bandbreitenrichtliniendienst, der die Bandbreitenrichtlinien für die entsprechende Region, die zugeordneten Standorte und die Links zu diesen Standorten verwaltet. Der bandbreitenrichtliniendienst wird als Teil der Front-End-Server ausgeführt, und daher ist eine höhere Verfügbarkeit innerhalb dieses Pools integriert. Der bandbreitenrichtliniendienst, der auf jedem Front-End-Server ausgeführt wird, synchronisiert alle 15 Sekunden. Wenn der Front-End-Pool ausfällt, werden die CAC-Richtlinien für diese Website erst dann erzwungen, wenn der Front-End-Pool und damit der bandbreitenrichtliniendienst wieder in Betrieb genommen wird. Das bedeutet, dass während der Zeit, in der der Bandbreitenrichtliniendienst ausfällt, alle Anrufe durchgehen. Aus diesem Grund besteht in diesem Zeitraum die Möglichkeit einer zu hohen Bandbreitenbelegung Ihrer Links.

Der bandbreitenrichtliniendienst bietet eine große Verfügbarkeit innerhalb eines Front-End-Pools. Es bietet jedoch keine Redundanz über Front-End-Pools. Der bandbreitenrichtliniendienst kann nicht von einem Front-End-Pool zu einem anderen Failover. Nachdem der Service für den Front-End-Pool wiederhergestellt wurde, wird der bandbreitenrichtliniendienst fortgesetzt und kann die Überprüfung der Bandbreitenrichtlinien erneut erzwingen.

### <a name="network-considerations"></a>Überlegungen zum Netzwerk

Obwohl die Bandbreitenbeschränkung für Audio und Video durch den bandbreitenrichtliniendienst in Skype for Business Server erzwungen wird, wird diese Einschränkung beim Netzwerkrouter nicht erzwungen (Layer 2 und 3). Mithilfe der Anrufsteuerung kann nicht verhindert werden, dass z. B. eine Datenanwendung die gesamte Netzwerkbandbreite einer WAN-Leitung belegt (einschließlich der Bandbreite, die durch Ihre Anrufsteuerungsrichtlinie für Audio und Video reserviert ist). Um sicherzustellen, dass die erforderliche Bandbreite in Ihrem Netzwerk reserviert wird, können Sie ein QoS-Protokoll (Quality of Service) wie Differenzierte Dienste (DiffServ) bereitstellen. Daher empfiehlt es sich, die definierten Bandbreitenrichtlinien der Anrufsteuerung auf QoS-Einstellungen abzustimmen, die Sie gegebenenfalls bereitstellen.

### <a name="media-and-signaling-paths-over-vpn"></a>Medien- und Signalpfade über ein VPN

Wenn Ihr Unternehmen die Medienübermittlung über ein VPN unterstützt, müssen Sie sicherstellen, dass sowohl der Medien- als auch der Signaldatenstrom über das VPN verarbeitet werden bzw. beide Datenströme über das Internet geroutet werden. In der Standardeinstellung werden die Medien- und Signaldatenströme durch den VPN-Tunnel verarbeitet.

### <a name="call-admission-control-of-outside-users"></a>Anrufsteuerung für externe Benutzer

Die Anrufsteuerung wird nicht über die Grenzen der Skype for Business Server-Organisation hinaus erzwungen. CAC kann nicht auf den Medien Verkehr angewendet werden, der das Internet durchläuft, was nicht von Skype for Business Server verwaltet wird. CAC-Prüfungen werden für den Teil des Anrufs durchgeführt, der durch das Unternehmensnetzwerk geleitet wird, wenn der aufgerufene Endpunkt zur Organisation gehört und der Edgeserver der Netzwerkkonfiguration hinzugefügt wurde, wie unter [Bereitstellung von Anrufsteuerung: endgültige Checkliste für Skype for Business Server](../../deploy/deploy-enterprise-voice/final-checklist.md)beschrieben. Wenn der angerufene Endpunkt nicht zur Organisation gehört, wie beispielsweise ein Partnerverbund- oder PIC-Benutzer, werden keine Überprüfungen der Bandbreitenrichtlinie durchgeführt und beim ausgehenden Anruf werden alle Beschränkungen der Anrufsteuerung ignoriert.

### <a name="call-admission-control-of-pstn-connections"></a>Anrufsteuerung für PSTN-Verbindungen

Die Anrufsteuerung ist auf dem Vermittlungs Server unabhängig davon durchsetzbar, ob Sie mit einer IP/PBX-Anlage, einem PSTN-Gateway oder einem SIP-Trunk verbunden ist. Da es sich bei dem Vermittlungs Server um einen Back-to-Back-Benutzer-Agent (B2BUA) handelt, wird der Mediendienst beendet. Es hat zwei Verbindungsseiten: eine Seite, die mit dem Skype for Business-Server verbunden ist, und eine Gateway-Seite, die mit PSTN-Gateways, IP/PBX-Anlagen oder SIP-Stämmen verbunden ist. Details zu PSTN-Verbindungen finden Sie unter [Planen der PSTN-Konnektivität in Skype for Business Server](pstn-connectivity-0.md).

CAC kann auf beiden Seiten des Vermittlungsservers erzwungen werden, es sei denn, die medienumgehung ist aktiviert. Wenn die medienumgehung aktiviert ist, wird der Mediendatenverkehr nicht durch den Vermittlungs Server durchlaufen, sondern direkt zwischen dem Skype for Business-Client und dem Gateway. In diesem Fall wird die Anrufsteuerung nicht benötigt. Ausführliche Informationen finden Sie unter [Planen der medienumgehung in Skype for Business](media-bypass.md).

Die folgende Abbildung zeigt, wie die Anrufsteuerung für PSTN-Verbindungen mit und ohne Medienumgehung erzwungen wird.

**Erzwingen der Anrufsteuerung für Verbindungen mit dem PSTN**

![Voice CAC Media Bypass-Verbindungserzwingung](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung

Zur Planung der Anrufsteuerung (Call Admission Control, CAC) sind detaillierte Informationen zur Netzwerktopologie Ihres Unternehmens erforderlich. Führen Sie die folgenden Schritte aus, um Richtlinien für die Anrufsteuerung zu planen.

1. Identifizieren Sie die Hubs/Backbones (als Netzwerkregionen bezeichnet) in Ihrem Unternehmensnetzwerk.

2. Identifizieren Sie die Niederlassungen oder Standorte (als Netzwerkstandorte bezeichnet) innerhalb jeder Netzwerkregion.

3. Definieren Sie eine Netzwerkroute zwischen jedem Netzwerkregionenpaar.

4. Ermitteln Sie die Bandbreiteneinschränkungen für jede WAN-Verbindung.

    > [!NOTE]
    > Bandbreitengrenzwerte beziehen sich auf den Umfang der Bandbreite einer WAN-Verbindung, der Enterprise-VoIP-und Audio/Video-Datenverkehr zugewiesen ist. Wenn eine WAN-Verbindung als "Bandbreitenabhängig" bezeichnet wird, weist die WAN-Verbindung eine Bandbreitenbeschränkung auf, die kleiner als der erwartete Spitzenverkehr über den Link ist.

5. Identifizieren Sie die IP-Subnetze, die jedem Netzwerkstandort zugewiesen sind.

Zur Erläuterung dieser Konzepte verwenden wir die Beispiel Netzwerktopologie, die in der folgenden Abbildung dargestellt ist.

**Beispieltopologie für die Anrufsteuerung**

![Beispiel für eine Netzwerktopologie in Litware Inc.](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Alle Netzwerkstandorte sind einer Netzwerkregion zugeordnet. Beispielsweise sind die Standorte „Portland“, „Reno“ und „Albuquerque“ in der Region „Nordamerika“ enthalten. In dieser Abbildung werden nur WAN-Verbindungen mit Bandbreiteneinschränkungen gezeigt, auf die Anrufsteuerungsrichtlinien angewendet werden. Die Netzwerkstandorte „Chicago“, „New York“ und „Detroit“ werden innerhalb des Regionenovals „Nordamerika“ angezeigt, da sie keine Bandbreiteneinschränkungen aufweisen und für diese Standorte daher keine Richtlinien für die Anrufsteuerung erforderlich sind.

Die Komponenten in dieser Beispieltopologie werden in den folgenden Abschnitten erläutert. Ausführliche Informationen zur Planung dieser Topologie, einschließlich der Bandbreitenbeschränkungen, finden Sie unter [Beispiel: Erfassen von Anforderungen für die Anrufsteuerung in Skype for Business Server](example-gathering-requirements.md).

### <a name="identify-network-regions"></a>Identifizieren der Netzwerkregionen

Eine Netzwerkregion steht für einen Netzwerkbackbone oder einen Netzwerkhub.

Ein Netzwerkbackbone oder -hub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.

Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält eine Reihe von Netzwerkstandorten (siehe Definition in diesem Thema). Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verwendeten Netzwerkregionen zu identifizieren.

### <a name="associating-a-central-site-with-each-network-region"></a>Zuordnen eines zentralen Standorts zu jeder Netzwerkregion

Für CAC ist es erforderlich, dass eine Skype for Business Server Central-Website für jede netzwerkregion definiert ist. Ausgewählt wird der zentrale Standort, der die beste Netzwerkverbindung und die höchste Bandbreite aller Standorte in dieser Netzwerkregion bietet. In der oben gezeigten beispielhaften Netzwerktopologie sind drei Netzwerkregionen aufgeführt, jede mit einem zentralen Standort zur Verwaltung der Entscheidungen im Rahmen der Anrufsteuerung. Die geeignete Zuordnung für das vorangehende Beispiel wird in der folgenden Tabelle gezeigt.

> [!NOTE]
> Zentrale Websites entsprechen nicht unbedingt Netzwerk Websites. In den Beispielen in dieser Dokumentation geben einige zentrale Websites (Chicago, London und Peking) denselben Namen wie die Netzwerk Websites. Auch wenn ein zentraler Standort und eine Netzwerk Website denselben Namen haben, ist die zentrale Website ein Element der Skype for Business Server-Topologie, während die Netzwerk Website Teil des Gesamtnetzwerks ist, in dem sich die Skype for Business Server-Topologie befindet.

**Netzwerkregionen, zentrale Standorte und Netzwerkstandorte**

|**Netzwerkregion**|**Zentraler Standort**|**Netzwerkstandorte**|
|:-----|:-----|:-----|
|Nordamerika  <br/> |Chicago  <br/> |Chicago  <br/> New York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |London  <br/> |London  <br/> Köln  <br/> |
|APAC  <br/> |Beijing (Peking)  <br/> |Peking  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identifizieren von Netzwerkstandorten

Ein Netzwerkstandort ist ein Ort, an dem Ihre Organisation über Büros, einen Gebäudekomplex oder ein Gelände verfügt. Ein physischer Standort mit einem LAN und einer WAN-Verbindung zu anderen Standorten wird als Netzwerkstandort klassifiziert. Beginnen Sie, indem Sie alle Niederlassungen Ihrer Organisation inventarisieren. In der verwendeten Beispieltopologie umfasst die Netzwerkregion „Nordamerika“ die folgenden Netzwerkstandorte: New York, Chicago, Detroit, Portland, Reno und Albuquerque.

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
> Alle CAC-Bandbreitenwerte stellen die maximalen *unidirektionalen* Bandbreitengrenzwerte dar.

> [!NOTE]
> Die VoIP-Richtlinienfeatures von Skype for Business Server bieten die Möglichkeit, die Bandbreitenrichtlinien Überprüfung für eingehende Anrufe an den Benutzer außer Kraft zu setzen (nicht für ausgehende Anrufe, die vom Benutzer getätigt werden). Nachdem die Sitzung eingerichtet wurde, wird die Bandbreitenauslastung genau berechnet. Diese Einstellung sollte mit Bedacht verwendet werden. Ausführliche Informationen finden Sie unter [erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) oder [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) in der Bereitstellungsdokumentation.

Zur Optimierung der Bandbreitenauslastung auf Sitzungsebene sollten Sie sich Gedanken über die verwendeten Audio- und Videocodecs machen. Vermeiden Sie insbesondere eine zu geringe Bandbreitenzuweisung für einen Codec, der erwartungsgemäß häufig verwendet wird. Umgekehrt sollten Sie die maximale Bandbreite pro Sitzung sehr niedrig ansetzen, wenn Sie verhindern möchten, dass für Mediendaten ein Codec mit hohen Bandbreitenanforderungen verwendet wird. Für Audiodaten ist nicht jeder Codec für jedes Szenario verfügbar. Beispiel:

- Für Peer-to-Peer-Audioanrufe zwischen Skype for Business-Endpunkten wird entweder RTAudio (8kHz) oder RTAudio (16kHz) verwendet, wenn Sie die Bandbreite und Priorisierung von Codecs berücksichtigen.

- Für Konferenzgespräche zwischen Skype for Business-Endpunkten und dem A/V-Konferenzdienst wird entweder G. 722 oder Siren verwendet.

- Für Anrufe an das öffentlich geschaltete Telefonnetz (PSTN) an oder von Skype for Business-Endpunkten wird entweder G. 711 oder RTAudio (8kHz) verwendet.

Verwenden Sie die folgende Tabelle, um die maximalen Bandbreiteneinstellungen pro Sitzung zu optimieren.

**Bandbreitenauslastung nach Codec**

|**Codec**|**Bandbreitenanforderung ohne Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)**|**Bandbreitenanforderung mit Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)**|
|:-----|:-----|:-----|
|RTAudio (8 KHz)  <br/> |49,8 KBit/s  <br/> |61,6 KBit/s  <br/> |
|RTAudio (16 kHz)  <br/> |67 KBit/s  <br/> |96 KBit/s  <br/> |
|Siren  <br/> |57,6 KBit/s  <br/> |73,6 KBit/s  <br/> |
|G.711  <br/> |102 KBit/s  <br/> |166 KBit/s  <br/> |
|G.722  <br/> |105,6 KBit/s  <br/> |169,6 KBit/s  <br/> |
|RTVideo (CIF mit 15 F/s)  <br/> |260 KBit/s  <br/> |Nicht zutreffend  <br/> |
|RTVideo (VGA mit 30 F/s)  <br/> |610 KBit/s  <br/> |Nicht zutreffend  <br/> |

> [!NOTE]
> Bandbreitenanforderungen berücksichtigen einen Overhead für: Ethernet II, IP, User Datagram Protocol (UDP), RTP (Real-Time Transport Protocol) und SRTP (Secure Real-Time Transport Protocol). Ebenfalls enthalten ist ein Overhead von 10 KBit/s für RTCP.

Die Codecs G.722.1 und Siren sind ähnlich, unterscheiden sich jedoch in den Bitraten.

G. 722, der Standard-Codec für Skype for Business Server Conferencing, unterscheidet sich völlig vom g. 722.1-und Sirene-Codec.

Der Sirene-Codec wird in den folgenden Situationen in Skype for Business Server verwendet:

- Wenn die Bandbreitenrichtlinie zu niedrig festgelegt ist, um eine Verwendung von G.722 zuzulassen

- Wenn ein Communications Server 2007-oder Communications Server 2007 R2-Client eine Verbindung mit einem Skype for Business Server-Konferenzdienst herstellt (weil diese Clients den G. 722-Codec nicht unterstützen).

**Bandbreitenauslastung nach Szenario**

|**Szenario**|**Bandbreitenanforderung für Menge optimiert (KBit/s)**|**Bandbreitenanforderung für Ausgleichsmodus optimiert (KBit/s)**|**Bandbreitenanforderung für Qualität optimiert (KBit/s)**|
|:-----|:-----|:-----|:-----|
|Peer-zu-Peer-Audioanrufe  <br/> |45 KBit/s  <br/> |62 KBit/s  <br/> |91 KBit/s  <br/> |
|Telefonkonferenz  <br/> |53 KBit/s  <br/> |101 KBit/s  <br/> |165 KBit/s  <br/> |
|PSTN-Anrufe (zwischen Skype for Business und PSTN-Gateway, mit medienumgehung)  <br/> |97 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|PSTN-Anrufe (zwischen Skype for Business und Mediation Server ohne medienumgehung)  <br/> |45 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|PSTN-Anrufe (zwischen Vermittlungs Server und PSTN-Gateway ohne medienumgehung)  <br/> |97 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|Skype for Business – Polycom-Anrufe  <br/> |101 KBit/s  <br/> |101 KBit/s  <br/> |101 KBit/s  <br/> |

### <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Im hier verwendeten Beispiel sind dem Standort „New York“ in der Region „Nordamerika“ die folgenden IP-Subnetze zugewiesen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Angenommen, der Benutzer Bob, der üblicherweise in Detroit arbeitet, reist für eine Schulung in das New Yorker Büro. Wenn er seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für „New York“ reserviert sind, beispielsweise 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Skype for Business-Client übernimmt die lokale IP-Adresse und maskiert die IP-Adresse mit der zugehörigen Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung, aber nicht die medienumgehung bereitstellen, funktioniert die Anrufsteuerung auch dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.) Wenn sich ein Client beispielsweise auf einem Computer mit einer IP-Adresse von 172.29.81.57 mit einer IP-Subnetzmaske von 255.255.255.0 anmeldet, fordert Skype for Business die Bypass-ID an, die dem Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – auch wenn der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau so eingibt, wie dies von Skype for Business-Clients bereitgestellt wird (die mit Subnetzen während der Netzwerkkonfiguration entweder statisch oder per DHCP bereitgestellt werden).

## <a name="best-practices-for-call-admission-control"></a>Bewährte Methoden für die Anrufsteuerung

Halten Sie sich bei der Bereitstellung der Anrufsteuerung an die folgenden bewährten Methoden, um die Leistung zu verbessern und die Bereitstellung zu vereinfachen:

- Stellen Sie sicher, dass WANs für den aktuellen und den erwarteten Mediendatenverkehr angemessen ausgelegt sind.

    > [!NOTE]
    > Es empfiehlt sich, bei der Bandbreiteneinschränkungen einen Puffer einzurechnen. Manche Szenarien, z. B. Racebedingungen, wirken sich auf die verwendete Gesamtbandbreite aus und können zu Situationen führen, in denen die Bandbreitengrenze überschritten wird. Wenn beispielsweise zwei Anrufe gestartet werden, während der Mediendatenverkehr sich einer Bandbreitengrenze nähert, wird möglicherweise einer der beiden Anrufe abgewiesen, weil der andere zuerst gestartet wurde.

- Überwachen Sie die Netzwerkbelegung und die Kommunikationsdatensätze, damit Sie die optimalen Einstellungen für die Anrufsteuerung wählen und diese bei Änderungen in der Netzwerkbelegung aktualisieren können.

- Verwenden Sie Richtlinien für die Anrufsteuerung zur Ergänzung der QoS-Einstellungen.

- Wenn Sie blockierte Anrufe zum PSTN umleiten möchten, überprüfen Sie die Funktionalität und die Kapazität des PSTN. Weitere Informationen hierzu finden Sie unter [Planning Outbound Call Routing](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).

    > [!NOTE]
    > „Kapazität“ bezieht sich auf die Anzahl der Ports, die Sie zur Unterstützung einer möglichen PSTN-Umleitung öffnen müssen.


