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
description: In diesem Thema erfahren Sie, wie Sie die medienumgehung mit dem direkten Routing des Telefonsystems planen.
ms.openlocfilehash: cdfeb5313416730c703a1d0f10e2c7ccdddee1cc
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572157"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planen der Medienumgehung mit direktem Routing

## <a name="about-media-bypass-with-direct-routing"></a>Informationen zur medienumgehung mit direktem Routing

Mit der medienumgehung können Sie den Pfad des Mediendatenverkehrs verkürzen und die Anzahl der Hops auf der Übertragung reduzieren, um eine bessere Leistung zu erzielen. Bei der medienumgehung werden Medien zwischen dem Session Border Controller (SBC) und dem Client aufbewahrt, anstatt Sie über das Microsoft Phone-System zu senden. Um die medienumgehung zu konfigurieren, muss sich der SBC und der Client am gleichen Standort oder im gleichen Netzwerk befinden.

Sie können die medienumgehung für jeden SBC mithilfe des Befehls " **CSOnlinePSTNGateway** " Steuern, wobei der **-MediaBypass-** Parameter auf "true" oder "false" festgelegt ist. Wenn Sie die medienumgehung aktivieren, bedeutet dies nicht, dass der gesamte Mediendatenverkehr im Unternehmensnetzwerk verbleibt. In diesem Artikel wird der Anruffluss in verschiedenen Szenarien beschrieben.    

Die folgenden Diagramme veranschaulichen den Unterschied beim Anruffluss mit und ohne medienumgehung.

Ohne medienumgehung wird, wenn ein Client einen Anruf tätigt oder empfängt, sowohl der Signalisierungs-als auch der Medienfluss zwischen dem SBC, dem Microsoft Phone-System und dem Teams-Client erfolgen, wie in der folgenden Abbildung dargestellt:

![Zeigt Signalisierungs-und Medienfluss ohne medienumgehung](media/direct-routing-media-bypass-1.png)


Angenommen, ein Benutzer befindet sich im selben Gebäude oder Netzwerk wie der SBC. Angenommen, ein Benutzer, der sich in einem Gebäude in Frankfurt befindet, führt einen Anruf an einen PSTN-Benutzer durch: 

- **Ohne medienumgehung**fließen Medien entweder über Amsterdam oder Dublin (wo Microsoft-Rechenzentren bereitgestellt werden) und zurück zum SBC in Frankfurt. 

  Das Rechenzentrum in Europa ist ausgewählt, da sich der SBC in Europa befindet, und Microsoft verwendet das Rechenzentrum, das dem SBC am nächsten ist. Dieser Ansatz hat zwar keine Auswirkungen auf die Anrufqualität aufgrund einer Optimierung des Datenverkehrs in Microsoft-Netzwerken in den meisten Regionen, aber der Datenverkehr hat eine unnötige Schleife.     

- **Bei der medienumgehung**wird das Medium direkt zwischen dem Team Benutzer und dem SBC aufbewahrt, wie in der folgenden Abbildung dargestellt:

![Zeigt Signalisierungs-und Medienfluss mit medienumgehung](media/direct-routing-media-bypass-2.png)

Die medienumgehung nutzt die Protokolle namens Interactive Connectivity Establishment (ICE) auf dem Microsoft Teams-Client und Ice lite auf dem SBC. Mithilfe dieser Protokolle können Sie Direktes Routing verwenden, um den direktesten Medienpfad für optimale Qualität zu verwenden. Ice und Ice lite sind WebRTC-Standards. Ausführliche Informationen zu diesen Protokollen finden Sie unter RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Anruffluss-und Firewall-Planung

Die Planung des Anrufflusses und der Firewall hängt davon ab, ob der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat und ob sich der Benutzer innerhalb oder außerhalb des Netzwerks befindet.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Anruffluss, wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat

Wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat, sieht der Anruffluss wie folgt aus:

- Bei der medienumgehung muss der Team-Clientzugriff auf die öffentliche IP-Adresse des SBC haben, auch über ein internes Netzwerk. Wenn kein direktes Medium erwünscht ist, kann das Medium über Transport-Relays fließen.

- Dies ist die empfohlene Lösung, wenn sich ein Benutzer im gleichen Gebäude und/oder im gleichen Netzwerk wie der SBC befindet – entfernen Sie Microsoft Cloud-Komponenten aus dem Medienpfad.

- Die Signalübertragung fließt immer über die Microsoft-Cloud.

Das folgende Diagramm zeigt den Anruffluss, wenn die medienumgehung aktiviert ist, der Client intern ist und der Client die öffentliche IP-Adresse des SBC (Direct Media) erreichen kann: 

- Die Pfeile und numerischen Werte der Pfade entsprechen dem [Microsoft Teams Call Flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) -Artikel.

- Das SIP-Signal nimmt immer die Pfade 4 und 4 auf (je nach Verkehrsrichtung). Das Medium bleibt lokal und nimmt den Pfad 5B.

![Anzeige des Anrufflusses mit aktivierter medienumgehung, Client ist intern](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Anruffluss, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat

Im folgenden wird der Anruffluss beschrieben, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat. 

Angenommen, der Benutzer ist extern, und der mandantenadministrator hat entschieden, die öffentliche IP-Adresse des SBC nicht für jeden im Internet, sondern nur für die Microsoft-Cloud zu öffnen. Die internen Komponenten des Datenverkehrs können über die Teams-Transport-Relays fließen. Dies ist die empfohlene Konfiguration für Benutzer außerhalb des Unternehmensnetzwerks. Beachten Sie dabei Folgendes:

- Es werden Transport-Relays für Teams verwendet.

- Bei der medienumgehung verwendet Microsoft eine Version von Transport-Relays, die das Öffnen von Ports 50 000 bis 59 999 zwischen den Teams-Transport-Relays und dem SBC erfordert (in Zukunft planen wir, zu der Version zu wechseln, die nur 3478-und 3479-Ports erfordert).

- Zu Zwecken der Medienoptimierung empfiehlt Microsoft, die öffentliche IP-Adresse des SBC nur für Teams-Transport-Relays zu öffnen. Für Clients außerhalb des Unternehmensnetzwerks empfiehlt Microsoft die Verwendung von Transport-Relays, anstatt die öffentliche IP-Adresse des SBC direkt zu erreichen.

Das folgende Diagramm zeigt den Anruffluss, wenn die medienumgehung aktiviert ist, der Client ist extern, und der Client kann die öffentliche IP-Adresse des Session Border Controllers nicht erreichen (Medien werden von Teams Transport Relay weitergeleitet).

- Die Pfeile und numerischen Werte der Pfade entsprechen dem [Microsoft Teams Call Flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) -Artikel.

- Medien werden über die Pfade 3, 3 ', 4 und 4 ' weitergeleitet

![Zeigt den Anruffluss an, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Anruffluss, wenn sich ein Benutzer außerhalb des Netzwerks befindet und Zugriff auf die öffentliche IP des SBC hat

> [!NOTE]
> Diese Konfiguration wird nicht empfohlen, da Sie nicht die Vorteile von Teams-Transport-Relays nutzt. Stattdessen sollten Sie das vorherige Szenario berücksichtigen, in dem der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat. 

Das folgende Diagramm zeigt den Anruffluss, wenn die medienumgehung aktiviert ist, der Client ist extern, und der Client kann die öffentliche IP-Adresse des SBC (Direct Media) erreichen.

- Die Pfeile und numerischen Werte der Pfade entsprechen dem [Microsoft Teams Call Flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) -Artikel.

- Das SIP-Signal nimmt immer die Pfade 3 und 3 auf (abhängig von der Richtung des Datenverkehrs). Mediendatenströme mit Pfad 2.

![Zeigt den Anruffluss an, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Verwendung von Medien Prozessoren und Transport-Relays

Es gibt zwei Komponenten in der Microsoft-Cloud, die sich im Pfad des Medien Verkehrs befinden können: Medien Prozessoren und Transport-Relays. 

- Der medienprozessor ist eine öffentlich zugängliche Komponente, die Medien in nicht-Bypass-Fällen verarbeitet und Medien für Sprachanwendungen verarbeitet.

   Medien Prozessoren sind für Endbenutzer, die keine Umgehungs Anrufe führen, immer im Pfad, aber niemals im Pfad für umgegangene Anrufe. Medien Prozessoren sind immer im Pfad für alle Sprachanwendungen wie "Parken von Anrufen", "organisatorische automatische Telefonzentrale" und "Anrufwarteschlangen".

- Das Transport-Relay wird verwendet, um eine Verbindung mit dem nächstgelegenen Transportdienst herzustellen, um Echtzeitverkehr zu senden.

   Transport-Relays befinden sich möglicherweise nicht im Pfad für umgeleitete Anrufe – die von Endbenutzern stammen oder dazu bestimmt sind – je nachdem, wo sich der Benutzer befindet und wie das Netzwerk konfiguriert ist.

Das folgende Diagramm zeigt zwei Anruf Flüsse: eine mit aktivierter medienumgehung und die zweite mit deaktivierter medienumgehung. Hinweis Das Diagramm zeigt nur Datenverkehr, der von--oder bestimmten-Endbenutzern stammt.  
- Der Medien Controller ist ein microservice in Azure, der Medien Prozessoren zuordnet und SDP-Angebote (Session Description Protocol) erstellt.

- Der SIP-Proxy ist eine Komponente, die http-Ruhe Signalisierungen übersetzt, die in Teams für SIP verwendet werden.    

![Zeigt Anruf Flüsse mit aktivierter und deaktivierter medienumgehung](media/direct-routing-media-bypass-6.png)


In der nachstehenden Tabelle werden die Unterschiede zwischen Medien Prozessoren und Transport-Relays zusammengefasst.

|    | Medien Prozessoren | Transport-Relays|
| :--------------|:---------------|:------------|
Im Medienpfad für nicht Umgehungs Anrufe für Endbenutzer | Immer | Nie | 
Im Medienpfad für umgehende Anrufe für Endbenutzer | Nie | Wenn der Client den SBC für die öffentliche IP-Adresse nicht erreichen kann | 
In Medienpfad für Sprachanwendungen | Immer | Nie | 
Can do Transcodierung (B2BUA)\* | Ja | Nein, nur Audio zwischen Endpunkten weiterleiten | 
Anzahl der Instanzen weltweit und Standort | 8 gesamt: 2 in den USA Ost und West; 2 in Amsterdam und Dublin; 2 in Hongkong und Singapur; 2 in Japan (wird in Q1CY2019 hinzugefügt)  | Mehrere

Der IP-Bereich ist 52.112.0.0/14 (IP-Adressen von 52.112.0.1 zu 52.115.255.254). 

\*Erläuterung der Transcodierung: 

- Der medienprozessor ist B2BUA, was bedeutet, dass er einen Codec ändern kann (beispielsweise Seide vom Microsoft Teams-Client zu MP und G. 711 zwischen MP und SBC).

- Transport-Relays sind nicht B2BUA, was bedeutet, dass der Codec nie zwischen dem Client und dem SBC geändert wird – auch wenn der Datenverkehr über Relays abläuft.

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>Verwendung von Teams Transport-Relays in Eskalationsszenarien, wenn trunk für die medienumgehung konfiguriert ist

Teams-Transport-Relays befinden sich immer im Medienpfad in den folgenden Szenarien:

- Anruf wird von 1:1 zu einem Gruppenanruf eskaliert
- Der Anruf wird an einen Benutzer von Federated Teams weiterleiten.
- Der Anruf wird an einen Skype for Business-Nutzer weitergeleitet oder übertragen

Stellen Sie sicher, dass Ihr SBC wie unten beschrieben auf die Transport-Relays zugreifen kann.    


## <a name="sip-signaling-fqdns"></a>SIP-Signalisierung: FQDNs

Für SIP-Signalisierungen sind die Anforderungen für FQDN und Firewall dieselben wie für nicht Umgehungs Fälle. 

Das direkte Routing wird in den folgenden Office 365-Umgebungen angeboten:
- Office 365
- Office 365 gcc
- Office 365 gcc-höchst
- Office 365 DoD Weitere Informationen zu [Office 365-und US Government-Umgebungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie gcc, gcc-groß und DoD.

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 und Office 365 gcc-Umgebungen

Die Verbindungspunkte für die direkte Weiterleitung sind die folgenden drei FQDNs:

- **SIP.pstnhub.Microsoft.com** – globaler FQDN – muss zuerst ausprobiert werden. Wenn der SBC eine Anforderung zum Beheben dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure Datacenter verweist, das dem SBC zugewiesen ist. Die Aufgabe basiert auf den Leistungs Metriken der Rechenzentren und der geographischen Nähe zum SBC. Die zurückgegebene IP-Adresse entspricht dem primären FQDN.

- **sip2.pstnhub.Microsoft.com** – sekundärer FQDN – wird geografisch dem zweiten Prioritätsbereich zugeordnet.

- **sip3.pstnhub.Microsoft.com** – tertiärer FQDN – ordnet geographisch dem dritten Prioritätsbereich zu.

Sie müssen diese drei FQDNs platzieren, um Folgendes zu tun:

- Optimale Benutzerfreundlichkeit (geringere Belastung und Nähe zum SBC-Rechenzentrum, das durch Abfragen des ersten FQDN zugeordnet ist).

- Stellen Sie ein Failover bereit, wenn eine Verbindung von einem SBC zu einem Datacenter hergestellt wird, bei dem ein temporäres Problem auftritt. Weitere Informationen finden Sie unten unter Failover-Mechanismus.


Die FQDNs **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**und **sip3.pstnhub.Microsoft.com** werden in eine der folgenden IP-Adressen aufgelöst:
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen. Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN- **SIP-all.pstnhub.Microsoft.com** in alle diese IP-Adressen aufgelöst. 

### <a name="office-365-gcc-dod-environment"></a>Office 365 gcc DoD-Umgebung

Der Verbindungspunkt für das direkte Routing ist der folgende FQDN:

**SIP.pstnhub.DoD.Teams.Microsoft.US** – globaler FQDN. Da die Office 365 DoD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Die FQDNs – SIP.pstnhub.DoD.Teams.Microsoft.US werden in eine der folgenden IP-Adressen aufgelöst:

- 52.127.64.33
- 52.127.68.34

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN-SIP.pstnhub.DoD.Teams.Microsoft.US in alle diese IP-Adressen aufgelöst. 

### <a name="office-365-gcc-high-environment"></a>Office 365 gcc-höchst Umgebung

Der Verbindungspunkt für das direkte Routing ist der folgende FQDN:

**SIP.pstnhub.gov.Teams.Microsoft.US** – globaler FQDN. Da die gcc-höchst Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.

Die FQDNs – SIP.pstnhub.gov.Teams.Microsoft.US werden in eine der folgenden IP-Adressen aufgelöst:

- 52.127.88.59
- 52.127.92.64

Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen.  Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN-SIP.pstnhub.gov.Teams.Microsoft.US in alle diese IP-Adressen aufgelöst. 

## <a name="sip-signaling-ports"></a>SIP-Signalisierung: Anschlüsse

Die Port Anforderungen sind für alle Office 365-Umgebungen identisch, in denen Direktes Routing angeboten wird:
- Office 365
- Office 365 gcc
- Office 365 gcc-höchst
- Office 365 DoD

Sie müssen die folgenden Ports verwenden:

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP-Proxy | Sbchttps | 1024-65535 | Im SBC definiert |
| SIP/TLS | Sbchttps | SIP-Proxy | Im SBC definiert | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Mediendatenverkehr: IP-und Port Bereiche

Der Mediendatenverkehr fließt zwischen dem SBC-und dem Teams-Client, wenn direkte Konnektivität verfügbar ist, oder über Teams Transport Relays, wenn der Client den SBC nicht über die öffentliche IP-Adresse erreichen kann.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Voraussetzungen für direkten Medien Verkehr (zwischen dem Teams-Client und dem SBC) 

Der Client muss Zugriff auf die angegebenen Ports (siehe Tabelle) für die öffentliche IP-Adresse des SBC haben. 

Hinweis: Wenn sich der Client in einem internen Netzwerk befindet, fließt das Medium an die öffentliche IP-Adresse des SBC. Sie können hairpinning auf Ihrem NAT-Gerät so konfigurieren, dass der Datenverkehr nie das Netzwerkequipment des Unternehmens verlässt.

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Client | Sbchttps | 50 000 – 50 019  | Im SBC definiert |
| UDP/SRTP | Sbchttps | Client | Im SBC definiert | 50 000 – 50 019  |


Hinweis: Wenn Sie über ein Netzwerkgerät verfügen, das die Quell Anschlüsse des Clients übersetzt, stellen Sie sicher, dass übersetzte Ports zwischen dem Netzwerkgerät und dem SBC geöffnet sind. 

### <a name="requirements-for-using-transport-relays"></a>Voraussetzungen für die Verwendung von Transport-Relays

Transport-Relays befinden sich im gleichen Bereich wie Medien Prozessoren (für nicht-Bypass-Fälle): 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 und Office 365 gcc-Umgebungen

-52.112.0.0/14 (IP-Adressen von 52.112.0.1 nach 52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Office 365 gcc DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 gcc-höchst Umgebung

- 52.127.88.0/21


Der Portbereich der Teams-Transport-Relays (für alle Umgebungen) ist in der folgenden Tabelle aufgeführt:


| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Transport-Relay | Sbchttps | 50 000-59 999    | Im SBC definiert |
| UDP/SRTP | Sbchttps | Transport-Relay | Im SBC definiert | 50 000 – 59 999, 3478, 3479     |


Hinweis: Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigen Anruf im SBC. Da Microsoft über zwei Versionen von Transport-Relays verfügt, müssen Sie Folgendes ausführen:

- V4, das nur mit Portbereich 50 000 bis 59 999 funktionieren kann

- V6, das mit Ports 3478, 3479, kompatibel ist

Zu diesem Zeitpunkt unterstützt Media Bypass nur die V4-Version von Transport-Relays. Wir werden die Unterstützung von V6 in Zukunft vorstellen. 

Sie müssen Ports 3478 und 3479 für den Übergang öffnen. Wenn Microsoft Unterstützung für V6-Transport-Relays mit Media Bypass einführt, müssen Sie Ihre Netzwerkausrüstung oder SBCS nicht neu konfigurieren. 

### <a name="requirements-for-using-media-processors"></a>Voraussetzungen für die Verwendung von Medien Prozessoren

Medien Prozessoren sind immer im Medienpfad für Sprachanwendungen und für Webclients (beispielsweise Teams-Clients in Edge oder Google Chrome). Die Anforderungen sind identisch mit der Konfiguration ohne Bypass.


Der IP-Bereich für den Medien Verkehr ist 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 und Office 365 gcc-Umgebungen

-52.112.0.0/14 (IP-Adressen von 52.112.0.1 nach 52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Office 365 gcc DoD-Umgebung

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 gcc-höchst Umgebung

- 52.127.88.0/21

In der folgenden Tabelle wird der Portbereich der Medien Prozessoren (für alle Umgebungen) angezeigt:

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Medienprozessor | Sbchttps | 49 152 – 53 247    | Im SBC definiert |
| UDP/SRTP | Sbchttps | Medienprozessor | Im SBC definiert | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>Überlegungen, ob Skype for Business-Telefone in Ihrem Netzwerk vorhanden sind  

Wenn Sie über Skype for Business-Endpunkte in Ihrem Netzwerk verfügen, die Direktes Routing verwenden – beispielsweise kann ein Team Benutzer über ein 3PIP-Telefon verfügen, das auf dem Skype for Business-Client basiert – die medienumgehung auf dem Stamm, der diesen Benutzern dient, muss deaktiviert sein.

Sie können einen separaten trunk für diese Benutzer erstellen und ihm eine Online-VoIP-Routing Richtlinie zuweisen.

Konfigurationsschritte auf höherer Ebene:

- Benutzer nach Typ teilen – je nachdem, ob der Benutzer ein 3PIP-Telefon hat oder nicht.

- Erstellen Sie zwei getrennte Stämme mit unterschiedlichen FQDNs: eine für die medienumgehung aktivierte Option; der andere nicht. 

  Beide Trunks zeigen auf denselben SBC. Die Ports für TLS-SIP-Signalisierungen müssen unterschiedlich sein. Die Ports für Medien müssen identisch sein.

- Weisen Sie den richtigen trunk abhängig vom Typ des Benutzers in der Online-VoIP-Routing Richtlinie zu.

Im folgenden Beispiel wird diese Logik veranschaulicht.

| Gruppe von Benutzern | Anzahl der Benutzer | In OVRP zugewiesener trunk-FQDN | Medienumgehung aktiviert |
| :------------ |:----------------- |:--------------|:--------------|
Benutzer mit Teams-Clients und 3PIP-Telefonen | 20 | sbc1.contoso.com:5061 | false | 
Benutzer mit nur Teams-Endpunkten (einschließlich neuer Telefone, die für Teams zertifiziert sind) | 980 | sbc2.contoso.com:5060 | True

Beide Trunks können auf denselben SBC mit der gleichen öffentlichen IP-Adresse verweisen. Die TLS-Signalisierungs Anschlüsse auf dem SBC müssen unterschiedlich sein, wie in der nachstehenden Abbildung zu sehen ist. Hinweis Sie müssen sicherstellen, dass Ihr Zertifikat beide Trunks unterstützt. In San benötigen Sie zwei Namen (**sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.


![Zeigt, dass beide Trunks auf denselben SBC mit der gleichen öffentlichen IP-Adresse verweisen können.](media/direct-routing-media-bypass-7.png)

Informationen zum Konfigurieren von zwei Stämmen im gleichen SBC finden Sie in der Dokumentation Ihres SBC-Anbieters:

 - [AudioCodes-Bereitstellungsdokumentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode)-Bereitstellungsdokumentation](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Mit der medienumgehung unterstützte Client Endpunkte

Die medienumgehung wird für alle Endpunkte von Teams unterstützt.

Hinweis für Webclients (Teams Web App in Microsoft Edge, Google Chrome oder Mozilla Firefox) werden wir den Anruf an non-Bypass verdecken, auch wenn er als Bypass-Anruf gestartet wurde. Dies geschieht automatisch und erfordert keine Aktionen des Administrators. 
 
## <a name="see-also"></a>Siehe auch

[Konfigurieren der Medienumgehung mit direktem Routing](direct-routing-configure-media-bypass.md)



