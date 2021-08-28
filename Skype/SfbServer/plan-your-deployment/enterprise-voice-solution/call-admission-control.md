---
title: Planen der Anrufsteuerung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Erfahren Sie mehr über die Anrufsteuerung, die verhindern kann, dass Anrufe stattfinden, wenn sie eine schlechte Medienqualität aufweisen, in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 16b134e6d775d84be3fff97698d2f03ce7497c87
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623597"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Planen der Anrufsteuerung in Skype for Business Server

Erfahren Sie mehr über die Anrufsteuerung, die verhindern kann, dass Anrufe stattfinden, wenn sie eine schlechte Medienqualität aufweisen, in Skype for Business Server Enterprise-VoIP.

Bei IP-basierten Anwendungen wie Telefonie, Video und Anwendungsfreigabe wird die verfügbare Bandbreite von Unternehmensnetzwerken in LAN-Umgebungen im Allgemeinen nicht als einschränkend betrachtet. Bei WAN-Verbindungen, die Standorte miteinander verbinden, kann die Netzwerkbandbreite jedoch eingeschränkt sein.

Wenn der Netzwerkdatenverkehr eine WAN-Verbindung überschreibt, werden aktuelle Mechanismen wie Warteschlangen, Pufferung und Paketablage verwendet, um die Überlastung zu beheben. Der zusätzliche Datenverkehr wird in der Regel verzögert, bis sich die Netzwerküberlastung verringert oder, falls erforderlich, der Datenverkehr gelöscht wird. Bei herkömmlichem Datenverkehr in solchen Situationen kann der empfangende Client wiederhergestellt werden. Für Echtzeitdatenverkehr wie Unified Communications kann die Netzwerküberlastung jedoch nicht auf diese Weise behoben werden, da der Unified Communications-Datenverkehr sowohl auf Latenz als auch auf Paketverluste reagiert. Eine Überlastung des WAN kann zu einer schlechten QoE(Quality of Experience) für Benutzer führen. Für Echtzeitdatenverkehr unter überlasteten Bedingungen ist es eigentlich besser, Anrufe zu verweigern, als Verbindungen mit schlechter Qualität bereitzustellen.

Die Anrufsteuerung (Call Admission Control, CAC) bestimmt, ob genügend Netzwerkbandbreite vorhanden ist, um eine Echtzeitsitzung mit akzeptabler Qualität einzurichten. In Skype for Business Server steuert die Anrufsteuerung den Echtzeitdatenverkehr nur für Audio und Video, wirkt sich jedoch nicht auf den Datenverkehr aus. Wenn der Standard-WAN-Pfad nicht über die erforderliche Bandbreite verfügt, kann die Anrufsteuerung versuchen, den Anruf über einen Internetpfad oder das Telefonfestnetz (Public Switched Telephone Network, PSTN) weiterzuleiten.

In diesem Abschnitt wird die Anrufsteuerungsfunktion beschrieben und erläutert, wie Sie die Anrufsteuerung planen.

> [!NOTE]
> Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP Features: Anrufsteuerung (Call Admission Control, CAC), Notrufdienste (E9-1-1) und Medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei dieser Features gelten, finden Sie unter ["Netzwerkeinstellungen" für die erweiterten Enterprise-VoIP-Features in Skype for Business Server.](network-settings-for-advanced-features.md)

Das Cac-Design in Skype for Business Server bietet vier Hauptattribute:

- Die Bereitstellung und Verwaltung ist einfach, ohne dass zusätzliche Geräte erforderlich sind, z. B. speziell konfigurierte Router.

- Es befasst sich mit kritischen Unified Communications-Anwendungsfällen, z. B. Roamingbenutzern und mehreren Anwesenheitspunkten. Anrufsteuerungsrichtlinien werden entsprechend dem Standort des Endpunkts erzwungen, und nicht nach dem Standort, an dem der Benutzer verwaltet wird.

- Zusätzlich zu Sprachanrufen kann es auf anderen Datenverkehr angewendet werden, z. B. Auf Videoanrufe und Audio-/Videokonferenzsitzungen.

- Bietet die Flexibilität, die Darstellung verschiedener Arten von Netzwerktopologien zu ermöglichen.

Wenn eine neue VoIP- oder Videositzung die Bandbreiteneinschränkungen überschreitet, die Sie für eine WAN-Verbindung festgelegt haben, wird die Sitzung entweder blockiert oder (nur für Telefonanrufe) an das Festnetz umgeleitet.

Die Anrufsteuerung steuert den Echtzeitdatenverkehr nur für VoIP und Video. Der Datenverkehr wird nicht gesteuert.

Administratoren definieren Anrufsteuerungsrichtlinien, die vom Bandbreitenrichtliniendienst erzwungen werden, der mit jedem Front-End-Pool installiert wird. Anrufsteuerungseinstellungen werden automatisch an alle Skype for Business Server Front-End-Server in Ihrem Netzwerk weitergegeben.

Bei Anrufen, die aufgrund von Anrufsteuerungsrichtlinien fehlschlagen, lautet die Rangfolge für die Umleitung des Anrufs wie folgt:

1. Internet

2. Telefonfestnetz (Public Switched Telephone Network, PSTN)

3. Voicemail

Die Aufzeichnung von Kommunikationsdatensätzen (KDS) erfasst Informationen zu Anrufen, die an das Telefonfestnetz oder an Voicemail umgeleitet werden. KDS erfasst keine Informationen zu Anrufen, die an das Internet umgeleitet werden, da das Internet als alternativer Pfad und nicht als sekundäre Option behandelt wird.

> [!NOTE]
> Voicemails werden aufgrund von Bandbreiteneinschränkungen nicht verweigert.

Der Bandbreitenrichtliniendienst generiert zwei Typen von Protokolldateien im CSV-Format (Kommastrennte Werte). Die Protokolldatei mit **den Überprüfungsfehlern** erfasst Informationen, wenn Bandbreitenanforderungen abgelehnt werden. Die Protokolldatei für die **Verbindungsauslastung** erfasst eine Momentaufnahme der Netzwerktopologie und der BANDBREITEnauslastung der WAN-Verbindung. Beide Protokolldateien können Sie bei der Optimierung Ihrer Anrufsteuerungsrichtlinien basierend auf der Nutzung unterstützen.

## <a name="call-admission-control-considerations"></a>Überlegungen zur Anrufsteuerung

Der Administrator wählt aus, den Bandbreitenrichtliniendienst im ersten Pool zu installieren, der am zentralen Standort konfiguriert ist. Da es einen einzelnen zentralen Standort pro Netzwerkregion gibt, gibt es nur einen Bandbreitenrichtliniendienst pro Netzwerkregion, der die Bandbreitenrichtlinie für diese Region, die zugehörigen Standorte und die Verbindungen zu diesen Standorten verwaltet. Der Bandbreitenrichtliniendienst wird als Teil der Front-End-Server ausgeführt, und daher ist hohe Verfügbarkeit in diesem Pool integriert. Der Bandbreitenrichtliniendienst, der auf jedem Front-End-Server ausgeführt wird, wird alle 15 Sekunden synchronisiert. Wenn der Front-End-Pool fehlschlägt, werden die Anrufsteuerungsrichtlinien für diesen Standort erst dann erzwungen, wenn der Front-End-Pool ausgeführt wird und der Bandbreitenrichtliniendienst wieder betriebsbereit ist. Dies bedeutet, dass alle Anrufe für die Dauer durchgehen, in der der Bandbreitenrichtliniendienst nicht mehr funktioniert. Daher besteht die Möglichkeit einer Bandbreitenüberlastung Ihrer Links während dieses Zeitraums.

Der Bandbreitenrichtliniendienst bietet eine hohe Verfügbarkeit innerhalb eines Front-End-Pools. Es bietet jedoch keine Redundanz in Front-End-Pools. Der Bandbreitenrichtliniendienst kann kein Failover von einem Front-End-Pool zu einem anderen ausführen. Nachdem der Dienst für den Front-End-Pool wiederhergestellt wurde, wird der Bandbreitenrichtliniendienst fortgesetzt und kann erneut Bandbreitenrichtlinienüberprüfungen erzwingen.

### <a name="network-considerations"></a>Überlegungen zum Netzwerk

Obwohl die Bandbreiteneinschränkung für Audio und Video vom Bandbreitenrichtliniendienst in Skype for Business Server erzwungen wird, wird diese Einschränkung nicht am Netzwerkrouter (Ebene 2 und 3) erzwungen. Die Anrufsteuerung kann nicht verhindern, dass eine Datenanwendung beispielsweise die gesamte Netzwerkbandbreite auf einer WAN-Verbindung verbraucht, einschließlich der Bandbreite, die von Ihrer Anrufsteuerungsrichtlinie für Audio und Video reserviert wird. Um die erforderliche Bandbreite in Ihrem Netzwerk zu schützen, können Sie ein QoS-Protokoll (Quality of Service) wie differentiated Services (DiffServ) bereitstellen. Daher empfiehlt es sich, die von Ihnen definierten Bandbreitenrichtlinien für die Anrufsteuerung mit allen QoS-Einstellungen zu koordinieren, die Sie möglicherweise bereitstellen.

### <a name="media-and-signaling-paths-over-vpn"></a>Medien- und Signalpfade über VPN

Wenn Ihr Unternehmen Medien über VPN unterstützt, stellen Sie sicher, dass sowohl der Mediendatenstrom als auch der Signaldatenstrom über das VPN geleitet werden oder beide über das Internet weitergeleitet werden. Standardmäßig durchlaufen die Medien- und Signaldatenströme den VPN-Tunnel.

### <a name="call-admission-control-of-outside-users"></a>Anrufsteuerung für externe Benutzer

Die Anrufsteuerung wird nicht über die Grenzen der Skype for Business Server Organisation hinaus erzwungen. Die Anrufsteuerung kann nicht auf den Über das Internet übertragenen Mediendatenverkehr angewendet werden, der nicht von Skype for Business Server verwaltet wird. Cac checks will be performed on the portion of the call that flows through the enterprise network if the called endpoint belongs to the organization, and the Edge Server has been added to the network configuration, as described in [Call admission control deployment: final checklist for Skype for Business Server](../../deploy/deploy-enterprise-voice/final-checklist.md). Wenn der aufgerufene Endpunkt nicht zur Organisation gehört, z. B. ein Verbundbenutzer oder PIC-Benutzer, werden keine Bandbreitenrichtlinienüberprüfungen durchgeführt, und der ausgehende Anruf ignoriert alle Einschränkungen der Anrufsteuerung.

### <a name="call-admission-control-of-pstn-connections"></a>Anrufsteuerung für PSTN-Verbindungen

Die Anrufsteuerung kann auf dem Vermittlungsserver erzwungen werden, unabhängig davon, ob sie mit einer IP-/Nebenstellenanlage, einem PSTN-Gateway oder einem SIP-Trunk verbunden ist. Da der Vermittlungsserver ein Back-to-Back-Benutzer-Agent (B2BUA) ist, werden die Medien beendet. Es verfügt über zwei Verbindungsseiten: eine Seite, die mit Skype for Business Server verbunden ist, und eine Gatewayseite, die mit PSTN-Gateways, IP-/Nebenstellenanlagen oder SIP-Trunks verbunden ist. Ausführliche Informationen zu PSTN-Verbindungen finden Sie unter [Plan for PSTN connectivity in Skype for Business Server](pstn-connectivity-0.md).

Die Anrufsteuerung kann auf beiden Seiten des Vermittlungsservers erzwungen werden, es sei denn, die Medienumgehung ist aktiviert. Wenn die Medienumgehung aktiviert ist, durchläuft der Mediendatenverkehr nicht den Vermittlungsserver, sondern fließt direkt zwischen dem Skype for Business-Client und dem Gateway. In diesem Fall ist die Anrufsteuerung nicht erforderlich. Ausführliche Informationen finden Sie unter [Plan for media bypass in Skype for Business](media-bypass.md).

Die folgende Abbildung zeigt, wie die Anrufsteuerung für PSTN-Verbindungen mit und ohne aktivierte Medienumgehung erzwungen wird.

**Erzwingung der Anrufsteuerung für Verbindungen mit dem PSTN**

![Erzwingung der Verbindungserzwingung der Medienumgehung für die Sprachsteuerung](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definieren der Anforderungen für die Anrufsteuerung

Zur Planung der Anrufsteuerung (Call Admission Control, CAC) sind detaillierte Informationen zur Netzwerktopologie Ihres Unternehmens erforderlich. Führen Sie die folgenden Schritte aus, um Richtlinien für die Anrufsteuerung zu planen.

1. Identifizieren Sie die Hubs/Backbones (als Netzwerkregionen bezeichnet) in Ihrem Unternehmensnetzwerk.

2. Identifizieren Sie die Niederlassungen oder Standorte (als Netzwerkstandorte bezeichnet) innerhalb jeder Netzwerkregion.

3. Definieren Sie eine Netzwerkroute zwischen jedem Netzwerkregionenpaar.

4. Ermitteln Sie die Bandbreiteneinschränkungen für jede WAN-Verbindung.

    > [!NOTE]
    > Bandbreiteneinschränkungen beziehen sich darauf, wie viel Bandbreite auf einer WAN-Verbindung Enterprise-VoIP und Audio-/Videodatenverkehr zugeordnet wird. Wenn eine WAN-Verbindung als "Bandbreiteneinschränkung" beschrieben wird, weist die WAN-Verbindung eine Bandbreitenbeschränkung auf, die niedriger ist als der erwartete Spitzendatenverkehr über die Verbindung.

5. Identifizieren Sie die IP-Subnetze, die jedem Netzwerkstandort zugewiesen sind.

Um diese Konzepte zu erläutern, verwenden wir die Beispielnetzwerktopologie in der folgenden Abbildung.

**Beispieltopologie für die Anrufsteuerung**

![Litware Inc. Netzwerktopologie (Beispiel)](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Alle Netzwerkstandorte sind einer Netzwerkregion zugeordnet. Beispielsweise sind die Standorte "Portland", "Reno" und "Albuquerque" in der Region "Nordamerika" enthalten. In dieser Abbildung werden nur WAN-Verbindungen mit Bandbreiteneinschränkungen gezeigt, auf die Anrufsteuerungsrichtlinien angewendet werden. Die Netzwerkstandorte "Chicago", "New York" und "Detroit" werden innerhalb des Regionenovals "Nordamerika" angezeigt, da sie keine Bandbreiteneinschränkungen aufweisen und für diese Standorte daher keine Richtlinien für die Anrufsteuerung erforderlich sind.

Die Komponenten in dieser Beispieltopologie werden in den folgenden Abschnitten erläutert. Ausführliche Informationen zur Planung dieser Topologie, einschließlich der Bandbreiteneinschränkungen, finden Sie unter Beispiel: Erfassen von Anforderungen für die [Anrufsteuerung in Skype for Business Server.](example-gathering-requirements.md)

### <a name="identify-network-regions"></a>Identifizieren der Netzwerkregionen

Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub.

Ein Netzwerkbackbone oder Hub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.

Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält eine Reihe von Netzwerkstandorten (siehe Definition in diesem Thema). Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verwendeten Netzwerkregionen zu identifizieren.

### <a name="associating-a-central-site-with-each-network-region"></a>Zuordnen eines zentralen Standorts zu jeder Netzwerkregion

Die Anrufsteuerung erfordert, dass für jede Netzwerkregion ein Skype for Business Server zentraler Standort definiert ist. Ausgewählt wird der zentrale Standort, der die beste Netzwerkverbindung und die höchste Bandbreite aller Standorte in dieser Netzwerkregion bietet. In der oben gezeigten beispielhaften Netzwerktopologie sind drei Netzwerkregionen aufgeführt, jede mit einem zentralen Standort zur Verwaltung der Entscheidungen im Rahmen der Anrufsteuerung. Die geeignete Zuordnung für das vorangehende Beispiel wird in der folgenden Tabelle gezeigt.

> [!NOTE]
> Zentrale Standorte entsprechen nicht notwendigerweise Netzwerkstandorten. In den Beispielen in dieser Dokumentation haben einige zentrale Standorte – Chicago, London und China – denselben Namen wie die Netzwerkstandorte. Selbst wenn ein zentraler Standort und ein Netzwerkstandort denselben Namen haben, ist der zentrale Standort ein Element der Skype for Business Server Topologie, während der Netzwerkstandort Teil des Gesamtnetzwerks ist, in dem sich die Skype for Business Server-Topologie befindet.

**Netzwerkregionen, zentrale Standorte und Netzwerkstandorte**

|**Netzwerkregion**|**Zentraler Standort**|**Netzwerkstandorte**|
|:-----|:-----|:-----|
|Nordamerika  <br/> |Chicago  <br/> |Chicago  <br/> New York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |London  <br/> |London  <br/> Köln  <br/> |
|APAC  <br/> |Peking  <br/> |Peking  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identifizieren von Netzwerkstandorten

Ein Netzwerkstandort repräsentiert einen Ort, an dem Ihre Organisation über Büros, einen Gebäudekomplex oder ein Gelände verfügt. Ein physischer Standort mit einem LAN und einer WAN-Verbindung zu anderen Standorten wird als Netzwerkstandort klassifiziert. Beginnen Sie, indem Sie alle Büros Ihrer Organisation inventarisieren. In der verwendeten Beispieltopologie umfasst die Netzwerkregion "Nordamerika" die folgenden Netzwerkstandorte: New York, Chicago, Detroit, Portland, Reno und Albuquerque.

Sie müssen jeden Netzwerkstandort einer Netzwerkregion zuordnen. Abhängig davon, ob der Netzwerkstandort über eine eingeschränkte WAN-Verbindung verfügt oder nicht, wird dem Netzwerkstandort eine Bandbreitenrichtlinie zugeordnet. Ausführliche Informationen zu Anrufsteuerungsrichtlinien und der Bandbreite, die Sie über die Richtlinienverwendung zuweisen, finden Sie im Abschnitt "Definieren von Bandbreitenrichtlinien" weiter unten in diesem Thema. Zum Konfigurieren der Anrufsteuerung ordnen Sie Netzwerkstandorte Netzwerkregionen zu. Anschließend erstellen Sie Richtlinien zur Bandbreitenzuweisung, die auf Verbindungen mit Bandbreiteneinschränkungen zwischen einem Standort oder einer Region und die WAN-Verbindungen zwischen den Standorten und Regionen angewendet werden.

### <a name="identify-network-links"></a>Identifizieren von Netzwerkverbindungen

Netzwerkverbindungen repräsentieren Verbindungen zum physischen WAN, das unterschiedliche Regionen und Standorte verknüpft. In der Beispieltopologie sind zwei regionale Netzwerkverbindungen enthalten, fünf Netzwerkverbindungen zwischen Regionen und Standorten und eine Netzwerkverbindung zwischen zwei Standorten.

Die zwei regionalen Verbindungen befinden sich zwischen "Nordamerika" und "EMEA", dargestellt als "NA-EMEA-LINK", und zwischen "APAC" und "EMEA", dargestellt als "EMEA-APAC-LINK".

Die Standortverbindungen kennzeichnen die Leitungen zur Verbindung von "Portland", "Reno" und "Albuquerque" mit der Region "Nordamerika", zur Verbindung von "Manila" mit der Region "APAC" und zur Verbindung von "Köln" mit der Region "EMEA".  Die Verbindung zwischen "Reno" und "Albuquerque" kennzeichnet eine direkte Netzwerkverbindung zwischen diesen zwei Standorten.

### <a name="define-bandwidth-policies"></a>Definieren von Bandbreitenrichtlinien

Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verfügbare WAN-Bandbreite für in Echtzeit übertragenen Audio- und Videodatenverkehr über die WAN-Verbindungen in Ihrer Organisation zu ermitteln. Bandbreitenrichtlinien werden üblicherweise auf WAN-Verbindungen angewendet, wenn die Bandbreite eingeschränkt ist, wenn also der erwartete Datenverkehr die Bandbreite übersteigt, die für Audio- und Videodaten zugewiesen werden kann.

Bandbreitenrichtlinien für die Anrufsteuerung definieren, wie viel Bandbreite für in Echtzeit übertragene Audio- und Videodaten reserviert ist. Da die Bandbreite für anderen Datenverkehr bei der Anrufsteuerung nicht begrenzt wird, kann nicht verhindert werden, dass dieser die gesamte Netzwerkbandbreite durch Aktionen wie das Übertragen großer Dateien oder das Streamen von Musik beansprucht.

Bandbreitenrichtlinien für die Anrufsteuerung können einige oder alle der folgenden Werte definieren:

- Maximal reservierte Gesamtbandbreite für Audiodaten

- Maximal reservierte Gesamtbandbreite für Videodaten

- Maximal reservierte Bandbreite für einen einzelnen Audioanruf (Sitzung)

- Maximal reservierte Bandbreite für einen einzelnen Videoanruf (Sitzung)

> [!NOTE]
> Alle Bandbreitenwerte der Anrufsteuerung stellen die maximalen  *unidirektionalen Bandbreiteneinschränkungen*  dar.

> [!NOTE]
> Die Funktionen Skype for Business Server VoIP-Richtlinie bieten die Möglichkeit, Bandbreitenrichtlinienüberprüfungen für eingehende Anrufe an den Benutzer außer Kraft zu setzen (nicht für ausgehende Anrufe, die vom Benutzer getätigt werden). Nachdem die Sitzung eingerichtet wurde, wird die Bandbreitenauslastung genau berechnet. Diese Einstellung sollte mit Bedacht verwendet werden. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) oder Ändern einer [VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records) in der Bereitstellungsdokumentation.

Zur Optimierung der Bandbreitenauslastung auf Sitzungsebene sollten Sie sich Gedanken über die verwendeten Audio- und Videocodecs machen. Vermeiden Sie insbesondere eine zu geringe Bandbreitenzuweisung für einen Codec, der erwartungsgemäß häufig verwendet wird. Umgekehrt sollten Sie die maximale Bandbreite pro Sitzung sehr niedrig ansetzen, wenn Sie verhindern möchten, dass für Mediendaten ein Codec mit hohen Bandbreitenanforderungen verwendet wird. Für Audiodaten ist nicht jeder Codec für jedes Szenario verfügbar. Beispiel:

- Peer-to-Peer-Audioanrufe zwischen Skype for Business Endpunkten verwenden entweder RTAudio (8 kHz) oder RTAudio (16 kHz), wenn Sie die Bandbreite und Priorisierung von Codecs berücksichtigen.

- Konferenzanrufe zwischen Skype for Business Endpunkten und dem A/V-Konferenzdienst verwenden entweder G.722 oder Siren.

- Anrufe an das Telefonfestnetz (PUBLIC Switched Telephone Network, PSTN) an oder von Skype for Business Endpunkten verwenden entweder G.711 oder RTAudio (8 kHz).

Verwenden Sie die folgende Tabelle, um die maximalen Bandbreiteneinstellungen pro Sitzung zu optimieren.

**Bandbreitenauslastung nach Codec**

|**Codec**|**Bandbreitenanforderung ohne Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)**|**Bandbreitenanforderung mit Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)**|
|:-----|:-----|:-----|
|RTAudio (8 KHz)  <br/> |49,8 KBit/s  <br/> |61,6 KBit/s  <br/> |
|RTAudio (16 KHz)  <br/> |67 KBit/s  <br/> |96 KBit/s  <br/> |
|Sirene  <br/> |57,6 KBit/s  <br/> |73,6 KBit/s  <br/> |
|G.711  <br/> |102 KBit/s  <br/> |166 KBit/s  <br/> |
|G.722  <br/> |105,6 KBit/s  <br/> |169,6 KBit/s  <br/> |
|RTVideo (CIF mit 15 F/s)  <br/> |260 KBit/s  <br/> |Nicht zutreffend  <br/> |
|RTVideo (VGA mit 30 F/s)  <br/> |610 KBit/s  <br/> |Nicht zutreffend  <br/> |

> [!NOTE]
> Bandbreitenanforderungen berücksichtigen einen Overhead für: Ethernet II, IP, User Datagram Protocol (UDP), RTP (Real-Time Transport Protocol) und SRTP (Secure Real-Time Transport Protocol). Ebenfalls enthalten ist ein Overhead von 10 KBit/s für RTCP.

Die Codecs G.722.1 und Siren sind ähnlich, unterscheiden sich jedoch in den Bitraten.

G.722, der Standardcodec für Skype for Business Server Konferenzen, unterscheidet sich vollständig von den Codecs G.722.1 und Siren.

Der Siren-Codec wird in Skype for Business Server in den folgenden Situationen verwendet:

- Wenn die Bandbreitenrichtlinie zu niedrig festgelegt ist, um eine Verwendung von G.722 zuzulassen

- Wenn ein Communications Server 2007- oder Communications Server 2007 R2-Client eine Verbindung mit einem Skype for Business Server-Konferenzdienst herstellt (da diese Clients den G.722-Codec nicht unterstützen).

**Bandbreitenauslastung nach Szenario**

|**Szenario**|**Bandbreitenanforderung für Menge optimiert (KBit/s)**|**Bandbreitenanforderung für Ausgleichsmodus optimiert (KBit/s)**|**Bandbreitenanforderung für Qualität optimiert (KBit/s)**|
|:-----|:-----|:-----|:-----|
|Peer-zu-Peer-Audioanrufe  <br/> |45 KBit/s  <br/> |62 KBit/s  <br/> |91 KBit/s  <br/> |
|Telefonkonferenz  <br/> |53 KBit/s  <br/> |101 KBit/s  <br/> |165 KBit/s  <br/> |
|PSTN-Anrufe (zwischen Skype for Business und PSTN-Gateway, mit Medienumgehung)  <br/> |97 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|PSTN-Anrufe (zwischen Skype for Business und Vermittlungsserver ohne Medienumgehung)  <br/> |45 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|PSTN-Anrufe (zwischen Vermittlungsserver und PSTN-Gateway, ohne Medienumgehung)  <br/> |97 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|Skype for Business – Polycom-Aufrufe  <br/> |101 KBit/s  <br/> |101 KBit/s  <br/> |101 KBit/s  <br/> |

### <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Im hier verwendeten Beispiel sind dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Angenommen, der Benutzer Bob, der üblicherweise in Detroit arbeitet, reist für eine Schulung in das New Yorker Büro. Wenn er seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" reserviert sind, beispielsweise die Adresse 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Skype for Business Client verwendet seine lokale IP-Adresse und maskiert die IP-Adresse mit der zugeordneten Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung, aber keine Medienumgehung bereitstellen, funktioniert die Anrufsteuerung auch dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.) Wenn sich ein Client beispielsweise auf einem Computer mit der IP-Adresse 172.29.81.57 mit der IP-Subnetzmaske 255.255.255.0 anmeldet, fordert Skype for Business die Umgehungs-ID an, die dem Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau wie von Skype for Business Clients bereitgestellt (die während der Netzwerkkonfiguration entweder statisch oder über DHCP mit Subnetzen bereitgestellt werden).

## <a name="best-practices-for-call-admission-control"></a>Bewährte Methoden für die Anrufsteuerung

Halten Sie sich bei der Bereitstellung der Anrufsteuerung an die folgenden bewährten Methoden, um die Leistung zu verbessern und die Bereitstellung zu vereinfachen:

- Stellen Sie sicher, dass WANs für den aktuellen und den erwarteten Mediendatenverkehr angemessen ausgelegt sind.

    > [!NOTE]
    > Es empfiehlt sich, bei der Bandbreiteneinschränkungen einen Puffer einzurechnen. Manche Szenarien, zum Beispiel Racebedingungen, wirken sich auf die verwendete Gesamtbandbreite aus und können zu Situationen führen, in denen die Bandbreiteneinschränkung überschritten wird. Wenn beispielsweise zwei Anrufe gestartet werden, während der Mediendatenverkehr sich einer Bandbreiteneinschränkung nähert, wird möglicherweise einer der beiden Anrufe abgewiesen, weil der andere zuerst gestartet wurde.

- Überwachen Sie die Netzwerkbelegung und die Kommunikationsdatensätze, damit Sie die optimalen Einstellungen für die Anrufsteuerung wählen und diese bei Änderungen in der Netzwerkbelegung aktualisieren können.

- Verwenden Sie Richtlinien für die Anrufsteuerung zur Ergänzung der QoS-Einstellungen.

- Wenn Sie blockierte Anrufe in das Telefonfestnetz umleiten möchten, überprüfen Sie die PSTN-Funktionalität und -Kapazität. Ausführliche Informationen finden Sie unter [Planen des Routings ausgehender Anrufe](/previous-versions/office/lync-server-2013/lync-server-2013-planning-outbound-voice-routing).

    > [!NOTE]
    > Kapazität bezieht sich auf die Anzahl der Ports, die Sie zur Unterstützung einer möglichen PSTN-Umleitung öffnen müssen.