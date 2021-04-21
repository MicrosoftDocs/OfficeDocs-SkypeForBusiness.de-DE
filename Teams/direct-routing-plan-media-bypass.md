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
description: Erfahren Sie, wie Sie die Medienumgehung mit dem Direkten Routing für Telefonsystem planen, wodurch Sie den Pfad des Mediendatenverkehrs kürzen und die Leistung verbessern können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2cbe739a567588b44bef87f7b852ed8de965ad3
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899096"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planen der Medienumgehung mit direktem Routing

## <a name="about-media-bypass-with-direct-routing"></a>Informationen zur Medienumgehung mit Direct Routing

Mit der Medienumgehung können Sie den Pfad des Mediendatenverkehrs kürzen und die Anzahl der Hops verringern, die im Transit sind, um eine bessere Leistung zu erzielen. Bei der Medienumgehung werden Medien zwischen dem Session Border Controller (SBC) und dem Client gespeichert, anstatt sie über das Microsoft Phone System zu senden. Zum Konfigurieren der Medienumgehung müssen sich der SBC und der Client an demselben Speicherort oder Netzwerk befinden.

Sie können die Medienumgehung für jeden SBC steuern, indem Sie den Befehl **Set-CSOnlinePSTNGateway** verwenden, wobei der **-MediaBypass-Parameter** auf "true" oder "false" festgelegt ist. Wenn Sie die Medienumgehung aktivieren, bedeutet dies nicht, dass der ganze Mediendatenverkehr im Unternehmensnetzwerk bleibt. In diesem Artikel wird der Anruffluss in verschiedenen Szenarien beschrieben.

Die folgenden Diagramme veranschaulichen den Unterschied beim Anruffluss mit und ohne Medienumgehung.

Ohne Medienumgehung, wenn ein Client einen Anruf abnimmt oder empfängt, werden sowohl Signalisierung als auch Medienfluss zwischen dem SBC, dem Microsoft Phone System und dem Teams-Client ausgeführt, wie in der folgenden Abbildung dargestellt:

> [!div class="mx-imgBorder"]
> ![Zeigt Signalisierung und Medienfluss ohne Medienumgehung an](media/direct-routing-media-bypass-1.png)


Angenommen, ein Benutzer befindet sich im selben Gebäude oder Netzwerk wie der SBC. Angenommen, ein Benutzer, der sich in einem Gebäude in Frankfurt befindet, anruft einen PSTN-Benutzer: 

- **Ohne Medienumgehung** werden Medien entweder über Amsterdam oder Dublin (wo Microsoft-Rechenzentren bereitgestellt werden) und zurück zum SBC in Frankfurt fließen. 

  Das Rechenzentrum in Europa wird ausgewählt, da sich der SBC in Europa befindet und Microsoft das Rechenzentrum verwendet, das dem SBC am nächsten kommt. Dieser Ansatz hat zwar keine Auswirkungen auf die Anrufqualität aufgrund der Optimierung des Datenverkehrsflusses innerhalb von Microsoft-Netzwerken in den meisten Regionen, der Datenverkehr verfügt jedoch über eine unnötige Schleife.     

- **Bei der Medienumgehung** werden die Medien direkt zwischen dem Teams-Benutzer und dem SBC gehalten, wie in der folgenden Abbildung dargestellt:

  > [!div class="mx-imgBorder"]
  > ![Zeigt Signalisierung und Medienfluss mit Medienumgehung an](media/direct-routing-media-bypass-2.png)

Bei der Medienumgehung werden Protokolle namens Interactive Connectivity Establishment (ICE) im Teams-Client und ICE lite auf dem SBC verwendet. Diese Protokolle ermöglichen direct Routing die Verwendung des direktesten Medienpfads für optimale Qualität. ICE und ICE Lite sind WebRTC-Standards. Ausführliche Informationen zu diesen Protokollen finden Sie unter RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Anruffluss- und Firewallplanung

Die Anruffluss- und Firewallplanung hängt davon ab, ob der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat und ob sich der Benutzer innerhalb oder außerhalb des Netzwerks befindet.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Anruffluss, wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat

Wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat, lautet der Anruffluss wie folgt:

- Für die Medienumgehung muss der Teams-Client auch über ein internes Netzwerk Zugriff auf die öffentliche IP-Adresse des SBC haben. Wenn direkte Medien nicht gewünscht werden, können die Medien über Transportrelais fließen.

- Dies ist die empfohlene Lösung, wenn sich ein Benutzer im gleichen Gebäude und/oder Netzwerk wie der SBC befindet – entfernen Sie Microsoft Cloud-Komponenten aus dem Medienpfad.

- Die Signalisierung erfolgt immer über die Microsoft-Cloud.

Das folgende Diagramm zeigt den Anruffluss, wenn die Medienumgehung aktiviert ist, der Client intern ist und der Client die öffentliche IP-Adresse des SBC (Direct Media) erreichen kann: 

- Die Pfeile und numerischen Werte der Pfade sind mit den [Microsoft Teams-Anrufflüssen in Einklang.](./microsoft-teams-online-call-flows.md)

- Die SIP-Signalisierung verwendet immer die Pfade 4 und 4' (abhängig von der Verkehrsrichtung). Medien bleiben lokal und gehen den Pfad 5b ein.

> [!div class="mx-imgBorder"]
> ![Zeigt den Anruffluss mit aktivierter Medienumgehung an, der Client ist intern](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Anruffluss, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat

Im Folgenden wird der Anruffluss beschrieben, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat. 

Angenommen, der Benutzer ist extern, und der Mandantenadministrator hat entschieden, die öffentliche IP-Adresse des SBC nicht für alle Benutzer im Internet, sondern nur für die Microsoft Cloud zu öffnen. Die internen Komponenten des Datenverkehrs können über die Teams Transport Relays fließen. Berücksichtigen Sie dabei Folgendes:

- Teams Transport Relays werden verwendet.

- Für die Medienumgehung verwendet Microsoft eine Version von Transport relays, die das Öffnen der Ports 50 000 bis 59 999 zwischen den Teams Transport Relays und dem SBC erfordert (in Zukunft planen wir, zur Version zu wechseln, die nur 3478 und 3479 Ports erfordert).


Das folgende Diagramm zeigt den Anruffluss, wenn die Medienumgehung aktiviert ist, der Client extern ist und der Client die öffentliche IP-Adresse des Session Border Controllers nicht erreichen kann (Medien werden von Teams Transport Relay übertragen).

- Die Pfeile und numerischen Werte der Pfade sind mit den [Microsoft Teams-Anrufflüssen in Einklang.](./microsoft-teams-online-call-flows.md)

- Medien werden über die Pfade 3, 3', 4 und 4'

> [!div class="mx-imgBorder"]
> ![Zeigt den Anruffluss an, wenn der Benutzer keinen Zugriff auf die öffentliche IP des SBC hat](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Anruffluss, wenn sich ein Benutzer außerhalb des Netzwerks befindet und Zugriff auf die öffentliche IP des SBC hat

> [!NOTE]
> Dies ist keine empfohlene Konfiguration, da die Vorteile von Teams Transport Relays nicht genutzt werden. Berücksichtigen Sie stattdessen das vorherige Szenario, in dem der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat. 

Das folgende Diagramm zeigt den Anruffluss, wenn die Medienumgehung aktiviert ist, der Client extern ist und der Client die öffentliche IP-Adresse des SBC (Direct Media) erreichen kann.

- Die Pfeile und numerischen Werte der Pfade sind in Übereinstimmung mit dem [Artikel "Microsoft Teams-Anrufflüsse".](./microsoft-teams-online-call-flows.md)

- Die SIP-Signalisierung verwendet immer die Pfade 3 und 3' (abhängig von der Verkehrsrichtung). Medienflüsse mithilfe von Pfad 2.

> [!div class="mx-imgBorder"]
> ![Zeigt den Anruffluss an, wenn der Benutzer keinen Zugriff auf die öffentliche IP des SBC hat](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Verwendung von Medienprozessoren und Transportrelais

Es gibt zwei Komponenten in der Microsoft Cloud, die sich im Pfad des Mediendatenverkehrs befinden können: Medienprozessoren und Transportrelais. 

- Der Medienprozessor ist eine öffentlich zugängliche Komponente, die Medien in Nichtumgehungsfällen behandelt und Medien für Sprachanwendungen behandelt.

   Medienprozessoren befinden sich immer im Pfad für nicht umgangene Aufrufe des Endbenutzers, aber nie im Pfad für umgangene Anrufe. Medienprozessoren befinden sich immer im Pfad für alle Sprachanwendungen wie Anrufpark, Organisationsrichtlinien automatische Telefonzentrale und Anrufwarteschlangen.

- Das Transportrelais wird verwendet, um eine Verbindung mit dem nächstgelegenen Transportdienst herzustellen, um Echtzeitdatenverkehr zu senden.

   Transportrelais befinden sich möglicherweise oder nicht im Pfad für umgangene Anrufe – die von Endbenutzern stammen oder für Endbenutzer bestimmt sind – je nachdem, wo sich der Benutzer befindet und wie das Netzwerk konfiguriert ist.

Das folgende Diagramm zeigt zwei Anrufflüsse: einen mit aktivierter Medienumgehung und einen mit deaktivierter Medienumgehung.

> [!NOTE]
> Das Diagramm zeigt nur Datenverkehr, der von -- oder bestimmten An-End-Benutzern stammt.  

- Der Mediencontroller ist ein Mikrodienst in Azure, der Medienprozessoren zuzuordnen und SDP-Angebote (Session Description Protocol) erstellt.

- Der SIP-Proxy ist eine Komponente, die die in Teams verwendete HTTP-REST-Signalisierung in SIP übersetzt.    

> [!div class="mx-imgBorder"]
> ![Zeigt Anrufflüsse mit aktivierter und deaktivierter Medienumgehung an.](media/direct-routing-media-bypass-6.png)


In der nachstehenden Tabelle ist der Unterschied zwischen Medienprozessoren und Transportrelais zusammengefasst.

|    | Medienprozessoren | Transportrelais|
| :--------------|:---------------|:------------|
Im Medienpfad für nicht umgangene Anrufe für Endbenutzer | Immer | Wenn der Client den Medienprozessor nicht direkt erreichen kann | 
Im Medienpfad für umgangene Anrufe für Endbenutzer | Niemals | Wenn der Client den SBC nicht über die öffentliche IP-Adresse erreichen kann | 
Im Medienpfad für Sprachanwendungen | Immer | Niemals | 
Kann Transcodieren (B2BUA)\* | Ja | Nein, gibt nur Audio zwischen Endpunkten weiter. | 
Anzahl der Instanzen weltweit und Standort | 10 gesamt: 2 in OST und West der USA; 2 in Amsterdam und Dublin; 2 in Hongkong und Singapur; 2 in Japan ; 2 in Australien Ost und Südosten | Mehrere

Die IP-Bereiche sind:
- 52.112.0.0/14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254)
- 52.120.0.0/14 (IP-Adressen von 52.120.0.1 bis 52.123.255.254)

\* Erläuterung zur Transcodierung: 

- Medienprozessor ist B2BUA, was bedeutet, dass er einen Codec ändern kann (z. B. SILK vom Teams-Client in MP und G.711 zwischen MP und SBC).

- Transportrelais sind keine B2BUA, was bedeutet, dass der Codec nie zwischen dem Client und dem SBC geändert wird – auch wenn der Datenverkehr über Relays fließt.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Verwendung von Teams Media Processors, wenn Trunk für die Medienumgehung konfiguriert ist

Teams Media Processors werden in den folgenden Szenarien immer in den Medienpfad eingefügt:

- Anruf wird von 1:1 auf einen Gruppenanruf eskaliert
- Anruf wird an einen Teamteambenutzer
- Anruf wird an einen Skype for Business-Benutzer weitergeleitet oder übertragen

Stellen Sie sicher, dass Ihr SBC wie unten beschrieben Zugriff auf die Bereiche Medienprozessoren und Transportrelais hat.    


## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs

Bei SIP-Signalisierungen sind die Anforderungen für FQDN und Firewall dieselben wie für nicht umgangene Fälle. 

Direct Routing wird in den folgenden Microsoft 365- oder Office 365-Umgebungen angeboten:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD Erfahren Sie mehr über [Office 365-](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) und US-Regierungsumgebungen wie GCC, GCC High und DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365-, Office 365- und Office 365-GCC-Umgebungen

Die Verbindungspunkte für Direct Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – Globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung zum Auflösen dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure-Rechenzentrum verweisen soll, das dem SBC zugewiesen ist. Die Zuordnung basiert auf Leistungsmetriken der Rechenzentren und der geografischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.

- **sip2.pstnhub.microsoft.com** – Sekundäres FQDN – geografisch der zweiten Prioritätsregion zu.

- **sip3.pstnhub.microsoft.com** – Tertiärer FQDN – geografische Zuordnung zur dritten Prioritätsregion.

Sie müssen diese drei FQDNs platzieren, um Folgendes zu können:

- Sorgen Sie für optimale Benutzererfahrung (weniger geladen und dem SBC-Rechenzentrum am nächsten, das durch Abfragen des ersten FQDNs zugewiesen wurde).

- Stellen Sie einen Failover bereit, wenn eine Verbindung von einem SBC zu einem Rechenzentrum hergestellt wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie weiter unten unter Failovermechanismus.


Die FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** und **sip3.pstnhub.microsoft.com** werden in eine der folgenden IP-Adressen aufgelöst:
- 52.114.148.0
- 52.114.132.46
- 52.114.16.74
- 52.114.20.29
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalisierung zu ermöglichen. Wenn Ihre Firewall DNS-Namen unterstützt,  wird der FQDN sip-all.pstnhub.microsoft.com auf alle diese IP-Adressen aufgelöst. 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC-DoD-Umgebung

Der Verbindungspunkt für Direct Routing ist der folgende FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – Globaler FQDN. Da die Office 365 DoD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Die FQDNs – sip.pstnhub.dod.teams.microsoft.us werden in eine der folgenden IP-Adressen aufgelöst:

- 52.127.64.33
- 52.127.68.34

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalisierung zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN sip.pstnhub.dod.teams.microsoft.us auf alle diese IP-Adressen aufgelöst. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

Der Verbindungspunkt für Direct Routing ist der folgende FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – Globaler FQDN. Da die GCC High-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Die FQDNs – sip.pstnhub.gov.teams.microsoft.us werden in eine der folgenden IP-Adressen aufgelöst:

- 52.127.88.59
- 52.127.92.64

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr an und von den Adressen für die Signalisierung zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN sip.pstnhub.gov.teams.microsoft.us auf alle diese IP-Adressen aufgelöst. 

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Ports

Die Portanforderungen sind für alle Office 365-Umgebungen identisch, in denen Direct Routing angeboten wird:
- Microsoft 365 oder Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Sie müssen die folgenden Ports verwenden:

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP-Proxy | SBC | 1024 - 65535 | Definiert im SBC |
| SIP/TLS | SBC | SIP-Proxy | Definiert im SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Mediendatenverkehr: IP- und Portbereiche

Der Mediendatenverkehr fließt zwischen dem SBC- und dem Teams-Client, wenn eine direkte Verbindung verfügbar ist, oder über Teams Transport Relays, wenn der Client den SBC nicht über die öffentliche IP-Adresse erreichen kann.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Anforderungen für den direkten Medienverkehr (zwischen dem Teams-Client und dem SBC) 

Der Client muss Zugriff auf die angegebenen Ports (siehe Tabelle) der öffentlichen IP-Adresse des SBC haben. 

> [!NOTE]
> Wenn sich der Client in einem internen Netzwerk befindet, fließen die Medien an die öffentliche IP-Adresse des SBC. Sie können das Anheften von Haaren auf Ihrem NAT-Gerät konfigurieren, damit der Datenverkehr die Geräte des Unternehmensnetzwerks nie verlässt.

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Client | SBC | 50 000 – 50 019  | Definiert im SBC |
| UDP/SRTP | SBC | Client | Definiert im SBC | 50 000 – 50 019  |


> [!NOTE]
> Wenn Sie über ein Netzwerkgerät verfügen, das die Quellports des Clients übersetzt, stellen Sie sicher, dass übersetzte Ports zwischen dem Netzwerkgerät und dem SBC geöffnet werden. 

### <a name="requirements-for-using-transport-relays"></a>Anforderungen für die Verwendung von Transportrelais

Transportrelais befinden sich im gleichen Bereich wie Medienprozessoren (für Nichtumgehungsfälle): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365-, Office 365- und Office 365-GCC-Umgebungen

- 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC-DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

- 52.127.88.0/21


Der Portbereich der Teams Transport Relays (gilt für alle Umgebungen) wird in der folgenden Tabelle angezeigt:


| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Transport Relay | SBC | 50 000 -59 999    | Definiert im SBC |
| UDP/SRTP | SBC | Transport Relay | Definiert im SBC | 50 000 – 59 999, 3478, 3479     |


> [!NOTE]
> Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigem Aufruf des SBC. Da Microsoft über zwei Versionen von Transport relays verfügt, sind die folgenden Erforderlich:
> 
> - v4, das nur mit Portbereich 50 000 bis 59 999 funktionieren kann
> 
> - v6, das mit den Ports 3478, 3479 funktioniert

Derzeit unterstützt die Medienumgehung nur v4-Version von Transportrelais. Wir werden in Zukunft die Unterstützung von v6 einführen. 

Sie müssen die Ports 3478 und 3479 für den Übergang öffnen. Wenn Microsoft Unterstützung für v6-Transportrelais mit Medienumgehung einstellt, müssen Sie Ihre Netzwerkgeräte oder SBCs nicht neu konfigurieren. 

### <a name="requirements-for-using-media-processors"></a>Anforderungen für die Verwendung von Medienprozessoren

Medienprozessoren befinden sich immer im Medienpfad für Sprachanwendungen und für Webclients (z. B. Teams-Clients in Edge oder Google Chrome). Die Anforderungen entsprechen den Anforderungen für die Konfiguration ohne Umgehung.


Der IP-Bereich für Mediendatenverkehr ist 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365- und Office 365-GCC-Umgebungen

- 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC-DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

- 52.127.88.0/21

Der Portbereich der Medienprozessoren (gilt für alle Umgebungen) wird in der folgenden Tabelle angezeigt:

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Medienprozessor | SBC | 3478, 3479 und 49 152 – 53 247    | Definiert im SBC |
| UDP/SRTP | SBC | Medienprozessor | Definiert im SBC | 3478, 3479 und 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Konfigurieren separater Trunks für die Medienumgehung und nicht mediale Umgehung  

Wenn Sie zur Medienumgehung von einer nicht medialen Umgehung migrieren und die Funktionalität bestätigen möchten, bevor Sie die ganze Verwendung zur Medienumgehung migrieren, können Sie einen separaten Trunk und eine separate Online Voice Routing-Richtlinie erstellen, um zum Medienumgehungs-Trunk zu migrieren und bestimmten Benutzern zuzuordnen. 

Konfigurationsschritte auf hoher Ebene:

- Identifizieren Sie Benutzer, die die Medienumgehung testen sollen.

- Erstellen Sie zwei separate Trunks mit unterschiedlichen FQDNs: einen, der für die Medienumgehung aktiviert ist; die andere nicht. 

  Beide Trunks zeigen auf denselben SBC. Die Ports für die TLS-SIP-Signalisierung müssen unterschiedlich sein. Die Ports für Medien müssen identisch sein.

- Erstellen Sie eine neue Online voice routing-Richtlinie, und weisen Sie den Medienumgehungs-Trunk den entsprechenden Routen zu, die der PSTN-Nutzung für diese Richtlinie zugeordnet sind.

- Weisen Sie die neue Online voice routing-Richtlinie Benutzern zu, die Sie zum Testen der Medienumgehung identifiziert haben.

Das folgende Beispiel veranschaulicht diese Logik.

| Gruppe von Benutzern | Anzahl der Benutzer | Trunk FQDN zugewiesen in OVRP | Medienumgehung aktiviert |
| :------------ |:----------------- |:--------------|:--------------|
Benutzer mit nicht medialem Bypass trunk | 980 | sbc1.contoso.com:5061 | false |
Benutzer mit Medienumgehungs-Trunk | 20 | sbc2.contoso.com:5060 | True | 

Beide Trunks können auf denselben SBC mit derselben öffentlichen IP-Adresse verweisen. Die TLS-Signalports auf dem SBC müssen unterschiedlich sein, wie in der folgenden Abbildung dargestellt. Beachten Sie, dass Sie sicherstellen müssen, dass ihr Zertifikat beide Trunks unterstützt. In SAN benötigen Sie zwei Namen **(sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.

> [!div class="mx-imgBorder"]
> ![Zeigt, dass beide Trunks auf denselben SBC mit derselben öffentlichen IP verweisen können](media/direct-routing-media-bypass-7.png)

Informationen zum Konfigurieren von zwei Trunks auf demselben SBC finden Sie in der Dokumentation ihres SBC-Anbieters:

 - [Dokumentation zur Audiocodes-Bereitstellung](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Dokumentation zur Oracle-Bereitstellung](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Dokumentation zur Bereitstellung von Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Te-Systems (Anynode)-Bereitstellungsdokumentation](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Clientendpunkte, die mit der Medienumgehung unterstützt werden

Die Medienumgehung wird von allen eigenständigen Teams-Desktopclients, Android- und iOS-Clients und Teams Phone-Geräten unterstützt. 

Für alle anderen Endpunkte, die die Medienumgehung nicht unterstützen, konvertieren wir den Anruf in eine Nichtumgehung, auch wenn er als Umgehungsaufruf gestartet wurde. Dies geschieht automatisch und erfordert keine Aktionen des Administrators. Dies umfasst Skype for Business 3PIP-Telefone und Teams-Webclients, die Direkte Routinganrufe unterstützen (WebRTC-basierte Clients, die auf Microsoft Edge, Google Chrome, Mozilla Firefox ausgeführt werden). 
 
## <a name="see-also"></a>Mehr dazu

[Konfigurieren der Medienumgehung mit direktem Routing](direct-routing-configure-media-bypass.md)
