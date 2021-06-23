---
title: Planen der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die Medienumgehung mit Telefonsystem Direct-Routing planen, wodurch Sie den Pfad des Mediendatenverkehrs kürzen und die Leistung verbessern können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d60513dbcf1128d303102f494600a67335b366d
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075398"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planen der Medienumgehung mit direktem Routing

## <a name="about-media-bypass-with-direct-routing"></a>Informationen zur Medienumgehung mit Direct Routing

Mit der Medienumgehung können Sie den Pfad des Mediendatenverkehrs kürzen und die Anzahl der Hops bei der Übertragung verringern, um eine bessere Leistung zu erzielen. Bei der Medienumgehung werden Medien zwischen Session Border Controller (SBC) und dem Client gespeichert, statt sie über das Microsoft-Telefon zu senden. Zum Konfigurieren der Medienumgehung müssen sich SBC und Client am selben Speicherort oder in demselben Netzwerk befinden.

Sie können die Medienumgehung für jeden SBC steuern, indem Sie den **Set-CSOnlinePSTNGateway-Befehl** mit dem Parameter **"-MediaBypass"** auf "true" oder "false" festlegen. Wenn Sie die Medienumgehung aktivieren, bedeutet dies nicht, dass der sämtliche Mediendatenverkehr im Unternehmensnetzwerk bleibt. In diesem Artikel wird der Anruffluss in verschiedenen Szenarien beschrieben.

Die folgenden Diagramme veranschaulichen den Unterschied beim Anruffluss mit und ohne Medienumgehung.

Wenn ein Client einen Aufruf ohne Medienumgehung eingeht oder empfängt, werden die Signalisierung und der Medienfluss zwischen SBC, Microsoft-Telefon-System und Teams-Client wie im folgenden Diagramm dargestellt:

> [!div class="mx-imgBorder"]
> ![Zeigt Signalisierung und Medienfluss ohne Medienumgehung](media/direct-routing-media-bypass-1.png)


Wir gehen aber davon aus, dass sich ein Benutzer im selben Gebäude oder Netzwerk wie der SBC befindet. Nehmen wir beispielsweise an, dass ein Benutzer, der sich in einem Gebäude in Frankfurt befindet, einen Anruf bei einem PSTN-Benutzer macht: 

- **Ohne Medienumgehung** fließen die Medien entweder über Amsterdam oder Dublin (wo Microsoft-Rechenzentren bereitgestellt werden) und zurück zum SBC in Frankfurt. 

  Das Rechenzentrum in Europa wird ausgewählt, da sich der SBC in Europa befindet und Microsoft das Rechenzentrum verwendet, das dem SBC am nächsten liegt. Dieser Ansatz wirkt sich zwar nicht auf die Anrufqualität aufgrund der Optimierung des Datenverkehrsflusses innerhalb von Microsoft-Netzwerken in den meisten Regionen aus, der Datenverkehr verfügt jedoch über eine unnötige Schleife.     

- **Bei der Medienumgehung** werden die Medien direkt zwischen dem Teams und dem SBC gehalten, wie in der folgenden Abbildung dargestellt:

  > [!div class="mx-imgBorder"]
  > ![Zeigt Signalisierung und Medienfluss mit Medienumgehung](media/direct-routing-media-bypass-2.png)

Bei der Medienumgehung werden Protokolle namens Interactive Connectivity Connectivity (ICE) auf dem Teams und ICE Lite auf der SBC verwendet. Diese Protokolle ermöglichen direct-Routing die Verwendung des direkten Medienpfads für optimale Qualität. ICE und ICE Lite sind WebRTC-Standards. Ausführliche Informationen zu diesen Protokollen finden Sie unter RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Anruffluss- und Firewallplanung

Die Anruffluss- und Firewallplanung hängt davon ab, ob der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat und ob sich der Benutzer innerhalb oder außerhalb des Netzwerks befindet.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Anruffluss, wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat

Wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse der SBC hat, erfolgt der Anruffluss wie folgt:

- Für die Medienumgehung muss der Teams Zugriff auf die öffentliche IP-Adresse des SBC selbst über ein internes Netzwerk haben. Wenn direkte Medien nicht gewünscht werden, können die Medien über Transport relays fließen.

- Dies ist die empfohlene Lösung, wenn sich ein Benutzer im selben Gebäude und/oder Netzwerk wie der SBC befindet – entfernen Sie Microsoft Cloud-Komponenten aus dem Medienpfad.

- Signalisierung fließt immer über die Microsoft-Cloud.

Das folgende Diagramm zeigt den Anruffluss, wenn die Medienumgehung aktiviert ist, der Client intern ist und der Client die öffentliche IP-Adresse des SBC (direkte Medien) erreichen kann: 

- Die Pfeile und numerischen Werte der Pfade sind in Übereinstimmung mit [Microsoft Teams Anrufflüssen.](./microsoft-teams-online-call-flows.md)

- Die SIP-Signalisierung verwendet immer die Pfade 4 und 4' (je nach Richtung des Datenverkehrs). Medien bleiben lokal und gehen auf Pfad 5b ein.

> [!div class="mx-imgBorder"]
> ![Anruffluss mit aktivierter Medienumgehung, der Client ist intern](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Anruffluss, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat

Im Folgenden wird der Anruffluss beschrieben, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat. 

Angenommen, der Benutzer ist extern, und der Mandantenadministrator hat sich entschieden, die öffentliche IP-Adresse des SBC nicht für alle Benutzer im Internet, sondern nur für die Microsoft-Cloud zu öffnen. Die internen Komponenten des Datenverkehrs können über die Transport relays Teams fließen. Berücksichtigen Sie dabei Folgendes:

- Teams Transport Relays werden verwendet.

- Zur Medienumgehung verwendet Microsoft eine Version von Transport Relays, für die das Öffnen der Ports 50 000 bis 59 999 zwischen den Teams-Transport relays und dem SBC erforderlich ist (in Zukunft ist der Wechsel zur Version geplant, für die 3478-3481 Ports erforderlich sind).


Das folgende Diagramm zeigt den Anruffluss, wenn die Medienumgehung aktiviert ist, der Client extern ist und der Client die öffentliche IP-Adresse des Session Border Controllers nicht erreichen kann (Die Medien werden über Teams Transport Relay übertragen).

- Die Pfeile und numerischen Werte der Pfade sind in Übereinstimmung mit [Microsoft Teams Anrufflüssen.](./microsoft-teams-online-call-flows.md)

- Medien werden über die Pfade 3, 3', 4 und 4' per Relay vermittelt.

> [!div class="mx-imgBorder"]
> ![Zeigt den Anruffluss an, wenn der Benutzer keinen Zugriff auf die öffentliche IP der SBC hat.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Anruffluss, wenn sich ein Benutzer außerhalb des Netzwerks befindet und Zugriff auf die öffentliche IP des SBC hat

> [!NOTE]
> Dies ist keine empfohlene Konfiguration, da sie die Vorteile Ihres Transport-Relays Teams nutzt. Betrachten Sie stattdessen das vorherige Szenario, in dem der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat. 

Das folgende Diagramm zeigt den Anruffluss, wenn die Medienumgehung aktiviert ist, der Client extern ist und der Client die öffentliche IP-Adresse des SBC erreichen kann (direkte Medien).

- Die Pfeile und numerischen Werte der Pfade sind in Übereinstimmung mit dem Artikel Microsoft Teams [Anrufflüssen.](./microsoft-teams-online-call-flows.md)

- Die SIP-Signalisierung verwendet immer die Pfade 3 und 3' (je nach Richtung des Datenverkehrs). Medienflüsse mithilfe von Pfad 2.

> [!div class="mx-imgBorder"]
> ![Zeigt den Anruffluss an, wenn der Benutzer keinen Zugriff auf die öffentliche IP der SBC hat.](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Verwenden von Medienprozessoren und Transport relays

Es gibt zwei Komponenten in der Microsoft-Cloud, die sich im Pfad des Mediendatenverkehrs befinden können: Medienprozessoren und Transportre relays. 

- Der Medienprozessor ist eine öffentlich zugängliche Komponente, die Medien in Nichtumgehungsfällen behandelt und Medien für Sprachanwendungen behandelt.

   Medienprozessoren befinden sich immer im Pfad für nicht umgehende Aufrufe von Endbenutzern, jedoch nie im Pfad für Umgehungsaufrufe. Medienprozessoren befinden sich immer im Pfad für alle Sprachanwendungen, z. B. Anruf parken, Organisations- automatische Telefonzentrale und Anrufwarteschleifen.

- Das Transport relay wird verwendet, um eine Verbindung mit dem nächstgelegenen Transportdienst herzustellen, um Echtzeitdatenverkehr zu senden.

   Transport Relays befinden sich abhängig davon, wo sich der Benutzer befindet und wie das Netzwerk konfiguriert ist, möglicherweise im Pfad für umgangene Aufrufe –die von stammen oder an Endbenutzer bestimmt sind .

Das folgende Diagramm zeigt zwei Anrufflüsse– einen mit aktivierter Medienumgehung und den zweiten mit deaktivierter Medienumgehung.

> [!NOTE]
> Das Diagramm zeigt nur Den Datenverkehr, der von -- oder bestimmten An-End-Benutzern stammt.  

- Der Mediencontroller ist ein Mikroservice in Azure, der Medienprozessoren zu weist und SDP-Angebote (Session Description Protocol) erstellt.

- Der SIP-Proxy ist eine Komponente, die die in der Sip-Teams HTTP-REST-Signalisierung übersetzt.    

> [!div class="mx-imgBorder"]
> ![Anrufflüsse mit aktivierter und deaktivierter Medienumgehung](media/direct-routing-media-bypass-6.png)


In der folgenden Tabelle ist der Unterschied zwischen Medienprozessoren und Transport relays zusammengefasst.

|    | Medienprozessoren | Transport Relays|
| :--------------|:---------------|:------------|
Im Medienpfad für nicht umgangene Aufrufe für Endbenutzer | Immer | Wenn der Client den Medienprozessor nicht direkt erreichen kann | 
Im Medienpfad für umgangene Aufrufe für Endbenutzer | Nie | Wenn der Client den SBC über die öffentliche IP-Adresse nicht erreichen kann | 
Im Medienpfad für Sprachanwendungen | Immer | Nie | 
Transcodieren kann (B2BUA)\* | Ja | Nein, leitet nur Audiodaten zwischen Endpunkten weiter. | 
Anzahl der Vorkommen weltweit und Standort | 10 insgesamt: 2 in "USA, Ost" und "West"; 2 in Amsterdam und Dublin; 2 in Hongkong und Singapur; 2 in Japan ; 2 in Australien, Osten und Südosten | Mehrere

Die IP-Bereiche sind:
- 52.112.0.0/14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254)
- 52.120.0.0/14 (IP-Adressen von 52.120.0.1 bis 52.123.255.254)

\* Erläuterung zum Transcodieren: 

- Der Medienprozessor ist B2BUA, d. h., er kann Codecs ändern (z. B. SILK von Teams-Client in MP und G.711 zwischen MP und SBC).

- Transport Relays sind nicht B2BUA, d. h., der Codec wird nie zwischen dem Client und dem SBC geändert– auch dann nicht, wenn Datenverkehr über Relays fließt.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Verwendung Teams Medienprozessoren, wenn der Trunk für die Medienumgehung konfiguriert ist

Teams Medienprozessoren werden in den folgenden Szenarien immer in den Medienpfad eingefügt:

- Anruf wird von 1:1 zu einem Gruppenanruf eskaliert
- Anruf wird an einen Partnerbenutzer Teams
- Der Anruf wird an einen Anderen weitergeleitet oder Skype for Business weitergeleitet.

Stellen Sie sicher, dass Ihr SBC auf die Bereiche "Medienprozessoren" und "Transport relays" zugreifen kann, wie unten beschrieben.    


## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs

Bei SIP-Signalisierungen gelten für den FQDN und die Firewall die gleichen Anforderungen wie für nicht umgangene Fälle. 

Direct Routing wird in den folgenden Microsoft 365 oder Office 365 angeboten:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC Hoch
- Office 365 DoD Erfahren Sie mehr [über Office 365 und US Government-Umgebungen](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie GCC, GCC High und DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 und Office 365 GCC Umgebung

Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – Globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung zum Auflösen dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure-Rechenzentrum verweisen, das dem SBC zugewiesen ist. Die Zuordnung basiert auf Leistungsmetriken der Rechenzentren und der geografischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.

- **sip2.pstnhub.microsoft.com** – Sekundärer FQDN – geografische Zuordnung zur zweiten Prioritätsregion.

- **sip3.pstnhub.microsoft.com** – Drittgrößter FQDN – geografische Zuordnung zur dritten Region mit Priorität.

Sie müssen diese drei FQDNs platzieren, um Folgendes zu können:

- Stellen Sie eine optimale Erfahrung (weniger geladen und dem SBC-Rechenzentrum am nächsten, das durch Abfragen des ersten FQDNs zugeordnet ist) zur Verfügung.

- Stellen Sie Failover bereit, wenn eine Verbindung von einem SBC zu einem Rechenzentrum hergestellt wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie unten unter Failovermechanismus.


Die FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** und **sip3.pstnhub.microsoft.com** werden in IP-Adressen aus den folgenden Subnetzen aufgelöst:
- 52.112.0.0/14
- 52.120.0.0/14

Sie müssen Ports für alle diese IP-Bereiche in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für Signale zu ermöglichen. Wenn Ihre Firewall DNS-Namen unterstützt, wird **sip-all.pstnhub.microsoft.com** FQDN in alle diese IP-Subnetze aufgelöst. 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD-Umgebung

Der Verbindungspunkt für Direct-Routing ist der folgende FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – Globaler FQDN. Da die Office 365 doD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und dritten FQDNs.

Die FQDN sip.pstnhub.dod.teams.microsoft.us wird in eine IP-Adresse aus dem folgenden Subnetz aufgelöst:

- 52.127.64.0/21

Sie müssen Ports für alle diese IP-Bereiche in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für Signale zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN sip.pstnhub.dod.teams.microsoft.us in alle diese IP-Subnetze aufgelöst. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

Der Verbindungspunkt für Direct-Routing ist der folgende FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – Globaler FQDN. Da die GCC High-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und drittrangig vorhandenen FQDNs.

Die FQDN sip.pstnhub.gov.teams.microsoft.us wird in eine IP-Adresse aus dem folgenden Subnetz aufgelöst:

- 52.127.64.0/21

Sie müssen Ports für alle diese IP-Bereiche in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für Signale zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN sip.pstnhub.gov.teams.microsoft.us in alle diese IP-Subnetze aufgelöst. 

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Ports

Portanforderungen sind für alle Office 365, in denen Direct-Routing angeboten wird, identisch:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC Hoch
- Office 365 DoD

Sie müssen die folgenden Ports verwenden:

| Verkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP-Proxy | SBC | 1024 - 65535 | Definiert im SBC |
| SIP/TLS | SBC | SIP-Proxy | Definiert im SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Medienverkehr: IP- und Portbereiche

Der Mediendatenverkehr fließt zwischen SBC und Teams-Client, wenn direkte Verbindung verfügbar ist, oder über Teams-Transport relays, wenn der Client den SBC nicht über die öffentliche IP-Adresse erreichen kann.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Anforderungen für direkten Medienverkehr (zwischen dem Teams und dem SBC) 

Der Client muss Zugriff auf die angegebenen Ports (siehe Tabelle) an der öffentlichen IP-Adresse des SBC haben. 

> [!NOTE]
> Befindet sich der Client in einem internen Netzwerk, fließen die Medien an die öffentliche IP-Adresse des SBC. Sie können das Anheften von Haarnadeln an Ihr NAT-Gerät so konfigurieren, dass der Datenverkehr die Ausrüstung des Unternehmensnetzwerks nie verlässt.

| Verkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Client | SBC | 3478-3481 und 49152 – 53247| Definiert im SBC |
| UDP/SRTP | SBC | Client | Definiert im SBC | 3478-3481 und 49152 – 53247  |


> [!NOTE]
> Wenn Sie über ein Netzwerkgerät verfügen, das die Quellports des Clients übersetzt, stellen Sie sicher, dass übersetzte Ports zwischen der Netzwerkausrüstung und dem SBC geöffnet werden. 

### <a name="requirements-for-using-transport-relays"></a>Anforderungen für die Verwendung von Transport relays

Transport Relays befinden sich im gleichen Bereich wie Medienprozessoren (für Fälle, in denen die Umgehung nicht möglich ist): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 und Office 365 GCC Umgebung

- 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

- 52.127.88.0/21


Der Portbereich des Teams Transport relays (gilt für alle Umgebungen) wird in der folgenden Tabelle angezeigt:


| Verkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Transport Relay | SBC | 50 000 -59 999    | Definiert im SBC |
| UDP/SRTP | SBC | Transport Relay | Definiert im SBC | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigem Aufruf des SBC. Da Microsoft über zwei Versionen von Transportre relays verfügt, sind folgende Schritte erforderlich:
> 
> - v4, die nur für Port 50 000 bis 59 999 funktionieren kann
> 
> - v6, funktioniert mit den Ports 3478-3481

Derzeit unterstützt die Medienumgehung nur die v4-Version von Transport relays. In Zukunft wird v6 unterstützt. 

Sie müssen die Ports 3478-3481 für den Übergang öffnen. Wenn Microsoft die Unterstützung für v6-Transport relays mit Medienumgehung einstellt, müssen Sie Ihre Netzwerkgeräte oder SBCs nicht neu konfigurieren. 

### <a name="requirements-for-using-media-processors"></a>Anforderungen für die Verwendung von Medienprozessoren

Medienprozessoren befinden sich immer im Medienpfad für Sprachanwendungen und Webclients (z. B. Teams-Clients in Edge oder Google Chrome). Die Anforderungen sind dieselben wie für die Konfiguration ohne Umgehung.


Der IP-Bereich für den Medienverkehr ist 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 und Office 365 GCC Umgebungen

- 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High-Umgebung

- 52.127.88.0/21

Der Portbereich der Medienprozessoren (gilt für alle Umgebungen) ist in der folgenden Tabelle aufgeführt:

| Verkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Medienprozessor | SBC | 3478-3481 und 49 152 – 53 247    | Definiert im SBC |
| UDP/SRTP | SBC | Medienprozessor | Definiert im SBC | 3478-3481 und 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Konfigurieren separater Trunks für die Medienumgehung und die Nicht-Medienumgehung  

Wenn Sie von der Nicht-Medienumgehung zur Medienumgehung migrieren und die Funktionalität vor der Migration der sämtlichen Verwendung zur Medienumgehung bestätigen möchten, können Sie einen separaten Trunk und eine separate Richtlinie für das Online-Voicerouting erstellen, um die Route zum Medienumgehungs-Trunk zu erstellen und bestimmten Benutzern zuzuordnen. 

Konfigurationsschritte auf hoher Ebene:

- Identifizieren Sie benutzer, um die Medienumgehung zu testen.

- Erstellen sie zwei separate Trunks mit unterschiedlichen FQDNs: einen für die Medienumgehung aktiviert; die andere nicht. 

  Beide Trunks zeigen auf denselben SBC. Die Ports für TLS SIP-Signalisierung müssen unterschiedlich sein. Die Ports für Medien müssen identisch sein.

- Erstellen Sie eine neue Online-Voiceroutingrichtlinie, und weisen Sie den Medienumgehungs-Trunk den entsprechenden Routen zu, die der PSTN-Nutzung für diese Richtlinie zugeordnet sind.

- Weisen Sie die neue Online-Voiceroutingrichtlinie Benutzern zu, die Sie zum Testen der Medienumgehung identifiziert haben.

Das folgende Beispiel veranschaulicht diese Logik.

| Gruppe von Benutzern | Anzahl der Benutzer | Trunk-FQDN in OVRP zugewiesen | Aktivierte Medienumgehung |
| :------------ |:----------------- |:--------------|:--------------|
Benutzer mit nicht medienfreiem Umgehungsstamm | 980 | sbc1.contoso.com:5061 | false |
Benutzer mit Medienumgehungs-Trunk | 20 | sbc2.contoso.com:5060 | True | 

Beide Trunks können auf denselben SBC mit derselben öffentlichen IP-Adresse verweisen. Die TLS-Signalisierungsports am SBC müssen unterschiedlich sein, wie in der folgenden Abbildung dargestellt. Beachten Sie, dass Ihr Zertifikat beide Trunks unterstützt. In SAN müssen zwei Namen **(sbc1.contoso.com** und **sbc2.contoso.com)** oder ein Platzhalterzertifikat verwendet werden.

> [!div class="mx-imgBorder"]
> ![Zeigt, dass beide Trunks auf denselben SBC mit derselben öffentlichen IP verweisen können.](media/direct-routing-media-bypass-7.png)

Informationen zum Konfigurieren von zwei Trunks auf demselben SBC finden Sie in der Dokumentation Ihres SBC-Anbieters:

 - [AudioCodes-Bereitstellungsdokumentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Dokumentation zur Bereitstellung von Kommunikationen im Menüband](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Dokumentation zur TE-Systems-Bereitstellung (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Von der Medienumgehung unterstützte Clientendpunkte

Die Medienumgehung wird von allen eigenständigen Teams Desktopclients, Android- und iOS-Clients und Teams Telefon unterstützt. 

Für alle anderen Endpunkte, die die Medienumgehung nicht unterstützen, konvertieren wir den Anruf in eine Nichtumgehung, auch wenn er als Umgehungsanruf gestartet wurde. Dies geschieht automatisch und erfordert keine Aktionen des Administrators. Dies umfasst Skype for Business 3PIP-Telefone und Teams-Webclients, die Direct Routing Calling (WebRTC-basierte Clients, die auf Microsoft Edge, Google Chrome und Mozilla Firefox ausgeführt werden) unterstützen. 
 
## <a name="see-also"></a>Mehr dazu

[Konfigurieren der Medienumgehung mit direktem Routing](direct-routing-configure-media-bypass.md)
