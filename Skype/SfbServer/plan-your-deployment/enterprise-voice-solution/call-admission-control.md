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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Erfahren Sie mehr über die Anrufsteuerung, die verhindern kann, dass Anrufe bei schlechter Medienqualität in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 07b1e057e9edc296d0eee694e323e3c3c27ef05f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825955"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Planen der Anrufsteuerung in Skype for Business Server

Erfahren Sie mehr über die Anrufsteuerung, die verhindern kann, dass Anrufe bei schlechter Medienqualität in Skype for Business Server Enterprise-VoIP.

Bei IP-basierten Anwendungen wie Telefonie, Video und Anwendungsfreigabe wird die verfügbare Bandbreite von Unternehmensnetzwerken im Allgemeinen nicht als einschränkungsfaktor innerhalb von LAN-Umgebungen betrachtet. Bei WAN-Verbindungen, die Standorte miteinander verbinden, kann die Netzwerkbandbreite jedoch eingeschränkt werden.

Wenn der Netzwerkdatenverkehr eine WAN-Verbindung überlastet, werden aktuelle Mechanismen wie Warteschlangen, Pufferung und Paketablösung verwendet, um die Überlastung zu beheben. Der zusätzliche Datenverkehr wird in der Regel verzögert, bis sich die Netzwerküberlastung entsenst nen oder, falls erforderlich, der Datenverkehr verworfen wird. Für herkömmlichen Datenverkehr in solchen Situationen kann der empfangende Client wiederhergestellt werden. Bei Echtzeitdatenverkehr wie Unified Communications kann die Netzwerküberlastung jedoch nicht auf diese Weise behoben werden, da der Unified Communications-Datenverkehr sowohl für Latenz als auch für Paketverluste sensibel ist. Überlastungen im WAN können zu einer schlechten QoE (Quality of Experience) für Benutzer führen. Für Echtzeitdatenverkehr unter überlasteten Bedingungen ist es eigentlich besser, Anrufe zu verweigern, als Verbindungen mit schlechter Qualität zu bieten.

Die Anrufsteuerung (Call Admission Control, CAC) bestimmt, ob genügend Netzwerkbandbreite vorhanden ist, um eine Echtzeitsitzung mit akzeptabler Qualität zu erstellen. In Skype for Business Server steuert die Anrufsteuerung den Echtzeitdatenverkehr nur für Audio und Video, wirkt sich jedoch nicht auf den Datenverkehr aus. Wenn der Standard-WAN-Pfad nicht über die erforderliche Bandbreite verfügt, kann die Anrufanrufleitung versuchen, den Anruf über einen Internetpfad oder das Festnetz (Public Switched Telephone Network, PSTN) weiter zu routen.

In diesem Abschnitt wird die Anrufsteuerungsfunktionalität beschrieben und die Planung der Anrufsteuerung erläutert.

> [!NOTE]
> Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP: Anrufsteuerung (Call Admission Control, CAC), Notrufdienste (E9-1-1) und Medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei Features verwendet werden, finden Sie unter "Netzwerkeinstellungen" für die erweiterten Enterprise-VoIP [in Skype for Business Server.](network-settings-for-advanced-features.md)

Der Anrufanrufentwurf in Skype for Business Server bietet vier Hauptattribute:

- Die Bereitstellung und Verwaltung ist einfach, ohne dass zusätzliche Geräte erforderlich sind, z. B. speziell konfigurierte Router.

- Sie befasst sich mit wichtigen Unified Communications-Verwendungsfällen, z. B. Roamingbenutzern und mehreren Anwesenheitspunkten. Richtlinien für die Benutzerfreundlichkeit werden entsprechend dem Standort des Endpunkts und nicht danach erzwungen, wo sich der Benutzer befindet.

- Zusätzlich zu Sprachanrufen kann sie auf anderen Datenverkehr angewendet werden, z. B. Videoanrufe und Audio-/Videokonferenzsitzungen.

- Bietet die Flexibilität, die Darstellung verschiedener Arten von Netzwerktopologien zu ermöglichen.

Wenn eine neue Sprach- oder Videositzung die Bandbreitenbeschränkungen überschreitet, die Sie für eine WAN-Verbindung festgelegt haben, wird die Sitzung entweder blockiert oder (nur für Telefonanrufe) an das PSTN umgeleitet.

Die Cac steuert nur den Echtzeitdatenverkehr für Sprach- und Videodaten. Der Datenverkehr wird nicht kontrolliert.

Administratoren definieren Cac policys, die durch den Bandbreitenrichtliniendienst erzwungen werden, der mit jedem Front-End-Pool installiert wird. Anrufanrufeinstellungen werden automatisch an alle Skype for Business Server-Front-End-Server in Ihrem Netzwerk verteilt.

Bei Anrufen, die aufgrund von Anrufanrufrichtlinien fehlschlagen, hat die Anrufumleitung folgende Priorität:

1. Internet

2. PSTN

3. Voicemail

Die Aufzeichnung von Anrufdetaildaten (Call Detail Recording, CDR) erfasst Informationen zu Anrufen, die an das PSTN oder an Voicemail umgeleitet werden. Die CdR erfasst keine Informationen zu Anrufen, die an das Internet umgeleitet werden, da das Internet als alternativer Pfad und nicht als sekundäre Option behandelt wird.

> [!NOTE]
> Voicemailablage wird aufgrund von Bandbreiteneinschränkungen nicht verweigert.

Der Bandbreitenrichtliniendienst generiert zwei Arten von Protokolldateien im CSV-Format. In **der Protokolldatei für Überprüfungsfehler** werden Informationen erfasst, wenn Bandbreitenanforderungen abgelehnt werden. Die **Protokolldatei für die** Linkverwendung erfasst eine Momentaufnahme der Netzwerktopologie und der Bandbreitenauslastung der WAN-Verbindung. Beide Protokolldateien können Sie bei der Optimierung Ihrer Richtlinien für die Benutzersteuerung basierend auf der Auslastung unterstützen.

## <a name="call-admission-control-considerations"></a>Überlegungen zur Anrufsteuerung

Der Administrator wählt die Installation des Bandbreitenrichtliniendiensts im ersten Pool aus, der am zentralen Standort konfiguriert ist. Da es einen zentralen Standort pro Netzwerkregion gibt, gibt es nur einen Bandbreitenrichtliniendienst pro Netzwerkregion, der die Bandbreitenrichtlinie für diese Region, die zugehörigen Standorte und die Verbindungen zu diesen Standorten verwaltet. Der Bandbreitenrichtliniendienst wird als Teil der Front-End-Server ausgeführt, und daher ist hohe Verfügbarkeit in diesem Pool integrierte. Der Bandbreitenrichtliniendienst, der auf jedem Front-End-Server ausgeführt wird, wird alle 15 Sekunden synchronisiert. Wenn der Front-End-Pool ausfällt, werden die Richtlinien für die Authentifizierung für den Standort erst dann erzwungen, wenn der Front-End-Pool und folglich der Bandbreitenrichtliniendienst wieder betriebsbereit sind. Dies bedeutet, dass alle Anrufe für die Dauer des Außerdiensts des Bandbreitenrichtliniendiensts durchgehen. Daher besteht die Möglichkeit, dass die Bandbreite während dieses Zeitraums überzeichnet wird.

Der Bandbreitenrichtliniendienst bietet hohe Verfügbarkeit innerhalb eines Front-End-Pools. Es bietet jedoch keine Redundanz über Front-End-Pools hinweg. Der Bandbreitenrichtliniendienst kann kein Failover von einem Front-End-Pool zu einem anderen ausführen. Nachdem der Dienst für den Front-End-Pool wiederhergestellt wurde, wird der Bandbreitenrichtliniendienst fortgesetzt und kann erneut Bandbreitenrichtlinienüberprüfungen erzwingen.

### <a name="network-considerations"></a>Überlegungen zum Netzwerk

Obwohl die Bandbreiteneinschränkung für Audio und Video vom Bandbreitenrichtliniendienst in Skype for Business Server erzwungen wird, wird diese Einschränkung beim Netzwerkrouter (Ebene 2 und 3) nicht erzwungen. Die Cac kann z. B. nicht verhindern, dass eine Datenanwendung die gesamte Netzwerkbandbreite für eine WAN-Verbindung verbraucht, einschließlich der Bandbreite, die von der Richtlinie für die Audio- und Videokonferenz für Audio und Video reserviert ist. Um die erforderliche Bandbreite in Ihrem Netzwerk zu schützen, können Sie ein Quality of Service (QoS)-Protokoll wie z. B. DiffServ (Differentiated Services) bereitstellen. Daher ist es eine bewährte Methode, die von Ihnen definierten Bandbreitenrichtlinien für die Cac zu koordinieren und die möglicherweise bereitgestellten QoS-Einstellungen zu verwenden.

### <a name="media-and-signaling-paths-over-vpn"></a>Medien- und Signalpfade über VPN

Wenn Ihr Unternehmen Medien über VPN unterstützt, stellen Sie sicher, dass sowohl der Mediendatenstrom als auch der Signaldatenstrom über das VPN oder beide über das Internet geroutet werden. Standardmäßig werden die Medien- und Signaldatenströme durch den VPN-Tunnel gestreamt.

### <a name="call-admission-control-of-outside-users"></a>Anrufsteuerung für externe Benutzer

Die Anrufsteuerung wird nicht über die Grenzen der Skype for Business Server-Organisation hinaus erzwungen. Die Anrufbehindung kann nicht auf den Mediendatenverkehr angewendet werden, der das Internet durchquert, der nicht von Skype for Business Server verwaltet wird. Anrufsteuerungsprüfungen werden für den Teil des Anrufs durchgeführt, der durch das Unternehmensnetzwerk fließt, wenn der angerufene Endpunkt zur Organisation gehört und der Edgeserver der Netzwerkkonfiguration hinzugefügt wurde, wie in der Bereitstellung der Anrufsteuerung [beschrieben:](../../deploy/deploy-enterprise-voice/final-checklist.md)abschließende Prüfliste für Skype for Business Server . Wenn der angerufene Endpunkt nicht zur Organisation gehört, z. B. ein Verbundbenutzer oder PIC-Benutzer, werden keine Bandbreitenrichtlinienüberprüfungen durchgeführt, und der ausgehende Anruf ignoriert anrufbehinderte Einschränkungen.

### <a name="call-admission-control-of-pstn-connections"></a>Anrufsteuerung für Festnetzverbindungen

Die Anrufsteuerung kann auf dem Vermittlungsserver erzwungen werden, unabhängig davon, ob sie mit einer IP/PBX-Anlage, einem PSTN-Gateway oder einem SIP-Trunk verbunden ist. Da der Vermittlungsserver ein Back-to-Back-Benutzer-Agent (B2BUA) ist, beendet er Medien. Es verfügt über zwei Verbindungsseiten: eine Seite, die mit Skype for Business Server verbunden ist, und eine Gatewayseite, die mit PSTN-Gateways, IP/PBX-Anlagen oder SIP-Trunks verbunden ist. Weitere Informationen zu PSTN-Verbindungen finden Sie unter [Plan for PSTN connectivity in Skype for Business Server](pstn-connectivity-0.md).

Die Medienumgehung kann auf beiden Seiten des Vermittlungsservers erzwungen werden, es sei denn, die Medienumgehung ist aktiviert. Wenn die Medienumgehung aktiviert ist, durchläuft der Mediendatenverkehr nicht den Vermittlungsserver, sondern fließt direkt zwischen dem Skype for Business-Client und dem Gateway. In diesem Fall ist die Cac nicht erforderlich. Weitere Informationen finden Sie unter ["Planen der Medienumgehung in Skype for Business".](media-bypass.md)

Die folgende Abbildung zeigt, wie die Cac für Festnetzverbindungen mit und ohne aktivierte Medienumgehung erzwungen wird.

**Erzwingung der Anrufsteuerung für Verbindungen mit dem PstN**

![Erzwingung der Medienumgehung für die Sprachsteuerung](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definieren der Anforderungen für die Anrufsteuerung

Zur Planung der Anrufsteuerung (Call Admission Control, CAC) sind detaillierte Informationen zur Netzwerktopologie Ihres Unternehmens erforderlich. Führen Sie die folgenden Schritte aus, um Richtlinien für die Anrufsteuerung zu planen.

1. Identifizieren Sie die Hubs/Backbones (als Netzwerkregionen bezeichnet) in Ihrem Unternehmensnetzwerk.

2. Identifizieren Sie die Niederlassungen oder Standorte (als Netzwerkstandorte bezeichnet) innerhalb jeder Netzwerkregion.

3. Definieren Sie eine Netzwerkroute zwischen jedem Netzwerkregionenpaar.

4. Ermitteln Sie die Bandbreiteneinschränkungen für jede WAN-Verbindung.

    > [!NOTE]
    > Bandbreitenbeschränkungen beziehen sich auf den Bandbreitenbedarf einer WAN-Verbindung, der Enterprise-VoIP Audio-/Videodatenverkehr zugeordnet wird. Wenn eine WAN-Verbindung als "bandbreitenbeschränkt" beschrieben wird, hat die WAN-Verbindung eine Bandbreitenbeschränkung, die niedriger ist als der erwartete Spitzendatenverkehr über die Verbindung.

5. Identifizieren Sie die IP-Subnetze, die jedem Netzwerkstandort zugewiesen sind.

Zur Erläuterung dieser Konzepte verwenden wir die in der folgenden Abbildung gezeigte Beispielnetzwerktopologie.

**Beispieltopologie für die Anrufsteuerung**

![Litware Inc. Network Topology (Beispiel)](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Alle Netzwerkstandorte sind einer Netzwerkregion zugeordnet. Beispielsweise sind die Standorte "Portland", "Reno" und "Albuquerque" in der Region "Nordamerika" enthalten. In dieser Abbildung werden nur WAN-Verbindungen mit Bandbreiteneinschränkungen gezeigt, auf die Anrufsteuerungsrichtlinien angewendet werden. Die Netzwerkstandorte "Chicago", "New York" und "Detroit" werden innerhalb des Regionenovals "Nordamerika" angezeigt, da sie keine Bandbreiteneinschränkungen aufweisen und für diese Standorte daher keine Richtlinien für die Anrufsteuerung erforderlich sind.

Die Komponenten in dieser Beispieltopologie werden in den folgenden Abschnitten erläutert. Details zur Planung dieser Topologie, einschließlich der Bandbreitenbeschränkungen, finden Sie unter Beispiel: Erfassen der Anforderungen für die Anrufsteuerung [in Skype for Business Server.](example-gathering-requirements.md)

### <a name="identify-network-regions"></a>Identifizieren der Netzwerkregionen

Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub.

Ein Netzwerkbackbone oder Hub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.

Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält eine Reihe von Netzwerkstandorten (siehe Definition in diesem Thema). Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verwendeten Netzwerkregionen zu identifizieren.

### <a name="associating-a-central-site-with-each-network-region"></a>Zuordnen eines zentralen Standorts zu jeder Netzwerkregion

Die Anruf anruft erfordert, dass für jede Netzwerkregion ein zentraler Skype for Business Server-Standort definiert ist. Ausgewählt wird der zentrale Standort, der die beste Netzwerkverbindung und die höchste Bandbreite aller Standorte in dieser Netzwerkregion bietet. In der oben gezeigten beispielhaften Netzwerktopologie sind drei Netzwerkregionen aufgeführt, jede mit einem zentralen Standort zur Verwaltung der Entscheidungen im Rahmen der Anrufsteuerung. Die geeignete Zuordnung für das vorangehende Beispiel wird in der folgenden Tabelle gezeigt.

> [!NOTE]
> Zentrale Standorte entsprechen nicht unbedingt Netzwerkstandorten. In den Beispielen in dieser Dokumentation haben einige zentrale Standorte – Chicago, London und Beijing – denselben Namen wie die Netzwerkstandorte. Selbst wenn ein zentraler Standort und ein Netzwerkstandort denselben Namen haben, ist der zentrale Standort ein Element der Skype for Business Server-Topologie, während der Netzwerkstandort Teil des Gesamtnetzwerks ist, in dem sich die Skype for Business Server-Topologie befindet.

**Netzwerkregionen, zentrale Standorte und Netzwerkstandorte**

|**Netzwerkregion**|**Zentraler Standort**|**Netzwerkstandorte**|
|:-----|:-----|:-----|
|Nordamerika  <br/> |Chicago  <br/> |Chicago  <br/> New York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |London  <br/> |London  <br/> Berlin  <br/> |
|APAC  <br/> |Beijing  <br/> |Beijing  <br/> 1000  <br/> |

### <a name="identify-network-sites"></a>Identifizieren von Netzwerkstandorten

Ein Netzwerkstandort repräsentiert einen Ort, an dem Ihre Organisation über Büros, einen Gebäudekomplex oder ein Gelände verfügt. Ein physischer Standort mit einem LAN und einer WAN-Verbindung zu anderen Standorten wird als Netzwerkstandort klassifiziert. Beginnen Sie, indem Sie alle Büros Ihrer Organisation inventarisierungen. In der verwendeten Beispieltopologie umfasst die Netzwerkregion "Nordamerika" die folgenden Netzwerkstandorte: New York, Chicago, Detroit, Portland, Reno und Albuquerque.

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
> Alle Bandbreitenwerte für die Cac stellen die maximalen  *unidirektionalen Bandbreitengrenzwerte*  dar.

> [!NOTE]
> Die Skype for Business Server-Voicerichtlinienfeatures bieten die Möglichkeit, Bandbreitenrichtlinienüberprüfungen für eingehende Anrufe an den Benutzer außer Kraft zu setzen (nicht für ausgehende Anrufe, die vom Benutzer durchgeführt werden). Nachdem die Sitzung eingerichtet wurde, wird die Bandbreitenauslastung genau berechnet. Diese Einstellung sollte mit Bedacht verwendet werden. Ausführliche Informationen finden Sie in der Bereitstellungsdokumentation unter "Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen [in Skype for Business"](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) oder "Ändern einer Voicerichtlinie und Konfigurieren von [PSTN-Verwendungsdatensätzen".](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx)

Zur Optimierung der Bandbreitenauslastung auf Sitzungsebene sollten Sie sich Gedanken über die verwendeten Audio- und Videocodecs machen. Vermeiden Sie insbesondere eine zu geringe Bandbreitenzuweisung für einen Codec, der erwartungsgemäß häufig verwendet wird. Umgekehrt sollten Sie die maximale Bandbreite pro Sitzung sehr niedrig ansetzen, wenn Sie verhindern möchten, dass für Mediendaten ein Codec mit hohen Bandbreitenanforderungen verwendet wird. Für Audiodaten ist nicht jeder Codec für jedes Szenario verfügbar. Beispiel:

- Peer-to-Peer-Audioanrufe zwischen Skype for Business-Endpunkten verwenden entweder RTAudio (8 KHz) oder RTAudio (16 KHz), wenn Sie die Bandbreite und Priorisierung von Codecs einplanen.

- Konferenzanrufe zwischen Skype for Business-Endpunkten und dem A/V-Konferenzdienst verwenden entweder G.722 oder Siren.

- Anrufe an das Festnetz (Public Switched Telephone Network, PSTN) an oder von Skype for Business-Endpunkten verwenden entweder G.711 oder RTAudio (8 KHz).

Verwenden Sie die folgende Tabelle, um die maximalen Bandbreiteneinstellungen pro Sitzung zu optimieren.

**Bandbreitenauslastung nach Codec**

|**Codec**|**Bandbreitenanforderung ohne Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)**|**Bandbreitenanforderung mit Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)**|
|:-----|:-----|:-----|
|RTAudio (8 KHz)  <br/> |49,8 KBit/s  <br/> |61,6 KBit/s  <br/> |
|RTAudio (16 KHz)  <br/> |67 KBit/s  <br/> |96 KBit/s  <br/> |
|Siren  <br/> |57,6 KBit/s  <br/> |73,6 KBit/s  <br/> |
|G.711  <br/> |102 KBit/s  <br/> |166 KBit/s  <br/> |
|G.722  <br/> |105,6 KBit/s  <br/> |169,6 KBit/s  <br/> |
|RTVideo (CIF mit 15 F/s)  <br/> |260 KBit/s  <br/> |Nicht zutreffend  <br/> |
|RTVideo (VGA mit 30 F/s)  <br/> |610 KBit/s  <br/> |Nicht zutreffend  <br/> |

> [!NOTE]
> Bandbreitenanforderungen berücksichtigen einen Overhead für: Ethernet II, IP, User Datagram Protocol (UDP), RTP (Real-Time Transport Protocol) und SRTP (Secure Real-Time Transport Protocol). Ebenfalls enthalten ist ein Overhead von 10 KBit/s für RTCP.

Die Codecs G.722.1 und Siren sind ähnlich, unterscheiden sich jedoch in den Bitraten.

G.722, der Standardcodec für Skype for Business Server-Konferenzen, ist vollständig anders als die Codecs G.722.1 und Siren.

Der Codec Siren wird in Skype for Business Server in den folgenden Situationen verwendet:

- Wenn die Bandbreitenrichtlinie zu niedrig festgelegt ist, um eine Verwendung von G.722 zuzulassen

- Wenn ein Communications Server 2007- oder Communications Server 2007 -R2-Client eine Verbindung mit einem Skype for Business Server-Konferenzdienst herstellt (da diese Clients den G.722-Codec nicht unterstützen).

**Bandbreitenauslastung nach Szenario**

|**Szenario**|**Bandbreitenanforderung für Menge optimiert (KBit/s)**|**Bandbreitenanforderung für Ausgleichsmodus optimiert (KBit/s)**|**Bandbreitenanforderung für Qualität optimiert (KBit/s)**|
|:-----|:-----|:-----|:-----|
|Peer-zu-Peer-Audioanrufe  <br/> |45 KBit/s  <br/> |62 KBit/s  <br/> |91 KBit/s  <br/> |
|Telefonkonferenz  <br/> |53 KBit/s  <br/> |101 KBit/s  <br/> |165 KBit/s  <br/> |
|Festnetzanrufe (zwischen Skype for Business und PSTN-Gateway, mit Medienumgehung)  <br/> |97 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|Festnetzanrufe (zwischen Skype for Business und Vermittlungsserver, ohne Medienumgehung)  <br/> |45 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|Festnetzanrufe (zwischen Vermittlungsserver und PSTN-Gateway, ohne Medienumgehung)  <br/> |97 KBit/s  <br/> |97 KBit/s  <br/> |161 KBit/s  <br/> |
|Skype for Business – Polycom-Anrufe  <br/> |101 KBit/s  <br/> |101 KBit/s  <br/> |101 KBit/s  <br/> |

### <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Im hier verwendeten Beispiel sind dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Angenommen, der Benutzer Bob, der üblicherweise in Detroit arbeitet, reist für eine Schulung in das New Yorker Büro. Wenn er seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" reserviert sind, beispielsweise die Adresse 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Skype for Business-Client verwendet seine lokale IP-Adresse und maskiert die IP-Adresse mit der zugeordneten Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung bereitstellen, jedoch keine Medienumgehung, funktioniert die Anrufsteuerung auch dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.) Wenn sich ein Client beispielsweise auf einem Computer mit der IP-Adresse 172.29.81.57 mit der IP-Subnetzmaske 255.255.255.0 anpasst, wird von Skype for Business die Umgehungs-ID des Subnetzes 172.29.81.0 anfordern. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau wie von Skype for Business-Clients bereitgestellt ein (die während der Netzwerkkonfiguration statisch oder über DHCP mit Subnetzen bereitgestellt werden).

## <a name="best-practices-for-call-admission-control"></a>Bewährte Methoden für die Anrufsteuerung

Halten Sie sich bei der Bereitstellung der Anrufsteuerung an die folgenden bewährten Methoden, um die Leistung zu verbessern und die Bereitstellung zu vereinfachen:

- Stellen Sie sicher, dass WANs für den aktuellen und den erwarteten Mediendatenverkehr angemessen ausgelegt sind.

    > [!NOTE]
    > Es empfiehlt sich, bei der Bandbreiteneinschränkungen einen Puffer einzurechnen. Manche Szenarien, zum Beispiel Racebedingungen, wirken sich auf die verwendete Gesamtbandbreite aus und können zu Situationen führen, in denen die Bandbreiteneinschränkung überschritten wird. Wenn beispielsweise zwei Anrufe gestartet werden, während der Mediendatenverkehr sich einer Bandbreiteneinschränkung nähert, wird möglicherweise einer der beiden Anrufe abgewiesen, weil der andere zuerst gestartet wurde.

- Überwachen Sie die Netzwerkbelegung und die Kommunikationsdatensätze, damit Sie die optimalen Einstellungen für die Anrufsteuerung wählen und diese bei Änderungen in der Netzwerkbelegung aktualisieren können.

- Verwenden Sie Richtlinien für die Anrufsteuerung zur Ergänzung der QoS-Einstellungen.

- Wenn Sie blockierte Anrufe in das Telefonfestnetz umleiten möchten, überprüfen Sie die PSTN-Funktionalität und -Kapazität. Ausführliche Informationen finden Sie unter [Planen des Routings ausgehender Anrufe](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).

    > [!NOTE]
    > Kapazität bezieht sich auf die Anzahl der Ports, die Sie zur Unterstützung einer möglichen PSTN-Umleitung öffnen müssen.


