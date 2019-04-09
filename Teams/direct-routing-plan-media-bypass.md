---
title: Planen der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lesen Sie in diesem Thema erfahren, wie für die medienumgehung mit Phone System direktem Routing planen.
ms.openlocfilehash: 308150121733f5f135d248404c663634ddaeea7c
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517247"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planen der Medienumgehung mit direktem Routing

## <a name="about-media-bypass-with-direct-routing"></a>Zur medienumgehung mit direktem Routing

Die medienumgehung können Sie den Pfad der Mediendatenverkehr kürzen, und reduzieren Sie die Anzahl von Hops während der Übertragung für eine bessere Leistung. Mit medienumgehung werden Medien zwischen Session Border Controller (SBC) und dem Client anstelle der Microsoft-Telefonsystem per gespeichert. Zum Konfigurieren von Medien muss umgehen, die SBC und dem Client im selben Speicherort oder Netzwerk.

Sie können die medienumgehung für jede SBC steuern, mit dem **Set-CSOnlinePSTNGateway** -Befehl mit dem **MediaBypass -** Parameter auf true oder false festgelegt. Wenn Sie die medienumgehung aktivieren, bedeutet dies nicht, dass alle Mediendatenverkehr innerhalb des Unternehmensnetzwerks während bleibt. Dieser Artikel beschreibt den Anruffluss in verschiedenen Szenarien.    

Die folgenden Diagramme illustrieren den Unterschied Anruffluss mit und ohne medienumgehung.

Ohne medienumgehung Wenn ein Client macht oder einen Anruf erhält flow Signale und Medien zwischen dem SBC, das Telefonsystem Microsoft und der Client Teams wie im folgenden Diagramm dargestellt:

![Zeigt Signale und Medien flow ohne medienumgehung](media/direct-routing-media-bypass-1.png)


Aber nehmen wir an, dass ein Benutzer im gleichen Gebäude oder Netzwerk wie der SBC ist. Nehmen wir beispielsweise an einem Benutzer in einem Gebäude in Frankfurt macht aus einer Anruf an eine PSTN-Benutzer ist: 

- **Ohne Media umgehen**, fließt die Medien über Amsterdam oder Dublin (, auf dem Microsoft-Rechenzentren bereitgestellt werden) und wieder in den SBC in Frankfurt. 

  Die Datacenter in Europa ausgewählt ist, da der SBC in Europa ist und Microsoft die SBC am nächsten Datencenter verwendet. Während dieser Ansatz Anrufqualität infolge der Optimierung des Datenverkehrs innerhalb von Microsoft-Netzwerke in den meisten Regionen nicht beeinträchtigt wird, hat der Datenverkehr eine Schleife nicht erforderliche.     

- **Mit Medien umgehen**, bleibt die Medien direkt zwischen den Benutzer Teams und der SBC wie im folgenden Diagramm dargestellt:

![Zeigt Signale und Medien Flussdiagramm mit medienumgehung](media/direct-routing-media-bypass-2.png)

Die medienumgehung nutzt Protokolle Interactive Connectivity Establishment (ICE) auf dem Client Teams und ICE auf den SBC light aufgerufen. Diese Protokolle aktivieren direkte Weiterleitung an die direkte Medienpfad für eine optimale Qualität verwenden. ICE und ICE Lite sind WebRTC Standards. Ausführliche Informationen zu diesen Protokollen finden Sie unter RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Anruffluss und Planung firewall

Anruffluss und Planung Firewall hängt gibt an, ob der Benutzer den direkten Zugriff auf die öffentliche IP-Adresse die SBC hat und ob der Benutzer innerhalb oder außerhalb des Netzwerks ist.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Rufen Sie Fluss auf, wenn der Benutzer den direkten Zugriff auf die öffentliche IP-Adresse die SBC verfügt

Wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse die SBC hat, ist der Anruffluss wie folgt:

- Für die medienumgehung muss der Teams Client Access der öffentlichen IP-Adresse von den SBC auch nicht von einem internen Netzwerk sein. Wenn direkte Medien nicht erwünscht ist, können die Medien über Transport Relays übertragen werden.

- Dies ist die empfohlene Lösung, wenn ein Benutzer in der gleichen Gebäude und/oder Netzwerk wie der SBC ist – Microsoft Cloud-Komponenten aus dem Medienpfad entfernt.

- Immer Signale werden über die Microsoft-Cloud übertragen.

Das folgende Diagramm zeigt die Anruffluss, wenn die medienumgehung aktiviert ist, ist ein interner Client und der Client die öffentliche IP-Adresse die SBC (direct Medien) erreichen kann: 

- Die Pfeile und numerische Werte der Pfade sind gemäß den Microsoft-Teams Online-Anrufflüsse Dokument.

- Die SIP-Signale immer akzeptiert Pfade 4 und 4' (abhängig von der Richtung des Datenverkehrs). Medien bleibt lokalen und Pfad 5 b akzeptiert.

![Zeigt Anruffluss mit Medienumgehung aktiviert, Client ist ein interner und Erreichen der öffentlichen IP-Adresse des der Session Border Controller (direct Medien)](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Rufen Sie Fluss auf, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse die SBC

Im folgenden werden Anruffluss, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse die SBC beschrieben. 

Nehmen wir beispielsweise an, der Benutzer ist externe und der mandantenadministrator entschieden, nicht für die öffentliche IP-Adresse die SBC für jede Person in das Internet, aber nur für Microsoft-Cloud zu öffnen. Die internen Komponenten des Datenverkehrs können über die Teams Transport Relays übertragen werden. Dies ist die empfohlene Konfiguration für Benutzer außerhalb des Firmennetzwerks befinden. Beachten Sie dabei Folgendes:

- Teams Transport Relays dienen.

- Für die medienumgehung verwendet Microsoft eine Version der Transport Relays, die erforderlich sind, öffnen Ports 50 000 zu 59 999 zwischen Teams Transport Relays und die SBC (in der Zukunft, den, die wir planen, auf die Version zu verschieben, die nur 3478 und 3479 Ports erforderlich ist).

- Microsoft empfiehlt für Medien Optimierung verwendet öffnen die öffentliche IP-Adresse die SBC nur für Teams Transport Relays. Für Clients außerhalb des Firmennetzwerks befinden empfiehlt es sich über Transport Relays anstatt die öffentliche IP-Adresse die SBC direkt zu erreichen.

Das folgende Diagramm zeigt die Anruffluss, wenn die medienumgehung aktiviert ist, befindet sich außerhalb des Clients und der Client kann nicht die öffentliche IP-Adresse der Session Border Controller (Medien werden von Teams Transport Relay weitergeleitet) erreichen.

- Die Pfeile und numerische Werte der Pfade sind gemäß den Microsoft-Teams Online-Anrufflüsse Dokument.

- Medien wird über Pfade 3, 3', 4 weitergeleitet und 4'

![Anruffluss wird, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des den SBC)](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Rufen Sie Fluss auf, wenn ein Benutzer außerhalb des Netzwerks befindet und Zugriff auf die öffentliche IP-Adresse des den SBC hat

> [!NOTE]
> Dies ist keine empfohlene Konfiguration, da es nicht Teams Transport Relays nutzen ist. In diesem Fall sollten Sie erwägen, vorherige Szenario, in dem der Benutzer an die öffentliche IP-Adresse die SBC keinen Zugriff. 

Das folgende Diagramm zeigt die Anruffluss, wenn die medienumgehung aktiviert ist, befindet sich außerhalb des Clients und der Client die öffentliche IP-Adresse die SBC (direct Medien) erreichen kann.

- Die Pfeile und numerische Werte der Pfade sind gemäß den Microsoft-Teams Online-Anrufflüsse Dokument.

- Die SIP-Signale immer akzeptiert Pfade 3 und 3' (abhängig von der Richtung des Datenverkehrs). Media fließt Pfad 2 verwenden.

![Anruffluss wird, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des den SBC)](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Verwendung von Medienprozessoren und Transport Relays

Es gibt zwei Komponenten in der Microsoft-Cloud, die in den Pfad der Mediendatenverkehr werden können: Media Prozessoren und Transport Relays. 

- Der Media-Prozessor ist eine öffentliche internetbasierte Komponente, die verarbeitet Medien in Fällen keine Umgehung und verarbeitet Medien für VoIP-Anwendungen.

   Media-Prozessoren werden immer in den Pfad für Endbenutzer nicht umgangen Anrufe, jedoch nie im Pfad zum umgangener Anrufe. Media-Prozessoren werden immer in den Pfad für alle VoIP-Anwendungen wie Anruf parken, Organisationseinheit automatische Telefonzentrale und Warteschlangen aufrufen.

- Transport-Relay wird zum Herstellen einer Verbindung zum Senden von Echtzeit-Datenverkehr am nächsten Transportdienst verwendet.

   Transport-Relays möglicherweise oder ist möglicherweise nicht in den Pfad für umgangener Anrufe--stammt oder bestimmt für Endbenutzer – je nachdem, wo der Benutzer ist und wie das Netzwerk konfiguriert ist.

Die folgende Abbildung zeigt zwei anrufflüssen – eine Vorlage mit medienumgehung aktiviert und die zweite mit Medien umgehen deaktiviert. Hinweis das Diagramm veranschaulicht nur Datenverkehr aus--stammt oder an – Endbenutzer bestimmt.  
- Der Datenträger-Controller ist eine Microservice in Azure, die weist Media Prozessoren und bietet gegebenenfalls Session Description Protocol (SDP) erstellt.

- Der SIP-Proxy ist eine Komponente, die HTTP REST Signale verwendet in Teams in SIP übersetzt.    

![Zeigt zeigt zwei anrufflüssen – eine mit Medienumgehung aktiviert und deaktiviert die zweite mit Medienumgehung)](media/direct-routing-media-bypass-6.png)


In der folgenden Tabelle werden die Unterschiede zwischen Media Prozessoren und Transport Relays zusammengefasst.

|    | Media-Prozessoren | Transport-Relays|
| :--------------|:---------------|:------------|
In Medienpfad für nicht umgangen Anrufe für Endbenutzer | Immer | Nie | 
In Medienpfad für umgangener Anrufe für Endbenutzer | Nie | Wenn der Client den SBC die öffentliche IP-Adresse nicht erreichen kann | 
In Medienpfad für VoIP-Anwendungen | Immer | Nie | 
Möglichkeiten transcodieren (B2BUA)\* | Ja | Nein, leitet nur Audio zwischen Endpunkten | 
Anzahl der Instanzen weltweit und Ort | insgesamt 8: 2 in uns Osten und Westen; 2 in Amsterdam und Dublin; 2 in Hongkong und Singapur; 2 in Japan (wird in Q1CY2019 hinzugefügt)  | Mehrere

Der IP-Adressbereich ist 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254). 

\*Transcodieren Erläuterung finden Sie unter: 

- Media-Prozessor ist B2BUA, was bedeutet, dass eine Codecs (beispielsweise SEIDE von Teams Client VA und g. 711 zwischen VA und SBC) geändert werden kann.

- Transport-Relays sind nicht B2BUA, bedeutet, dass der Codec nie zwischen dem Client und dem SBC--geändert wird, auch wenn über Relays Datenverkehr fließt.

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>Umgehen der Verwendung von Teams Transport Relays im Ausweitung Szenarien Wenn Trunk für Medien konfiguriert ist

Teams Transport Relays sind immer in der Medienpfad in den folgenden Szenarien:

- Anruf wird zu einem gruppenanruf von 1:1 eskaliert.
- Anruf schlägt an ein Verbundbenutzer Teams
- Anruf wird weitergeleitet oder in einen Skype für Geschäftsbenutzer übertragen

Stellen Sie sicher, dass für Ihren SBC beziehen, Zugriff auf die Relays Transport ist, wie unten beschrieben.    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a>SIP-Signalisierung: FQDNs und Firewallports

Für SIP-Signale sind die FQDN und Firewall für die gleichen wie bei Fällen nicht umgangen. 

Die Verbindungspunkte für direkte Routing sind die folgenden drei FQDNs:

- **sip.pstnhub.microsoft.com** – globale FQDN – müssen zuerst versucht werden. Wenn der SBC eine Anforderung an diesen Namen auflösen sendet, zurückgeben die Microsoft Azure DNS-Server eine IP-Adresse, die im primären Datencenter Azure zeigen die SBC zugewiesen. Die Zuordnung basiert auf Leistungsmetriken der Rechenzentren und geografische in der Nähe der SBC. Die zurückgegebene IP-Adresse entspricht des primären FQDN.

- **sip2.pstnhub.microsoft.com** – sekundären FQDN – ordnet geografisch zweiten Bereich Priorität.

- **sip3.pstnhub.microsoft.com** – tertiäre FQDN – ordnet geografisch die dritte Priorität Region.

Sie müssen diese drei FQDNs zu platzieren:

- Geben Sie optimale Erfahrungen (weniger geladen und dem SBC-Rechenzentrum durch Abfragen den ersten FQDN zugewiesen am nächsten).

- Bereitzustellen Sie Failover, wenn eine Verbindung über einen SBC in einem Rechenzentrum hergestellt wird, die ein vorübergehendes Problem aufgetreten ist. Weitere Informationen finden Sie unter Failover-Mechanismus unten.


Die FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**und **sip3.pstnhub.microsoft.com** werden auf eine der folgenden IP-Adressen aufgelöst werden:
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Sie müssen zum Öffnen von Ports für diese IP-Adressen in Ihrer Firewall für eingehenden und ausgehenden Datenverkehr zu und von der Adressen für Signale zu ermöglichen. Wenn die Firewall DNS-Namen unterstützt, die FQDN- **Sip-all.pstnhub.microsoft.com** in alle oben genannten IP-Adressen aufgelöst wird. Sie müssen die folgenden Ports verwenden:

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP-Proxy | SBC | 1024 - 65535 | Klicken Sie auf die SBC definiert |
| SIP/TLS | SBC | SIP-Proxy | Klicken Sie auf die SBC definiert | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Mediendatenverkehr: IP-Adresse und Port Bereiche

Media Datenfluss zwischen dem SBC und Teams Client Wenn direkte Verbindung verfügbar ist oder über Teams Transport Relays, wenn der Client den SBC mit der öffentlichen IP-Adresse nicht erreichen kann.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Anforderungen für die direkte Mediendatenverkehr (zwischen dem Client Teams und der SBC) 

Der Client benötigen Zugriff auf die angegebenen Ports (siehe Tabelle) auf der öffentlichen IP-Adresse die SBC. 

Hinweis: Wenn der Client in einem internen Netzwerk ist, die Medien an die öffentliche IP-Adresse die SBC fließt. Sie können Hairpinning so Datenverkehr nie bewirkt, die Enterprise-Netzwerkgeräte dass auf Ihr NAT-Gerät konfigurieren.

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Client | SBC | 50 000 – 50 019  | Klicken Sie auf die SBC definiert |
| UDP/SRTP | SBC | Client | Klicken Sie auf die SBC definiert | 50 000 – 50 019  |


Hinweis: Wenn Sie ein Netzwerkgerät, die die Quelle der Clientports übersetzt verfügen, stellen Sie sicher, dass die übersetzte Ports zwischen dem Netzwerkgeräte und die SBC geöffnet werden. 

### <a name="requirements-for-using-transport-relays"></a>Anforderungen für die Verwendung von Transport Relays

Transport-Relays handelt es sich im selben Bereich als Media Prozessoren (für Fällen keine Umgehung): 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254).

Der Portbereich Teams Transport Relays wird in der folgenden Tabelle gezeigt:


| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Transport-Relay | SBC | 50 000-59 999    | Klicken Sie auf die SBC definiert |
| UDP/SRTP | SBC | Transport-Relay | Klicken Sie auf die SBC definiert | 50 000 – 59 999, 3478, 3479     |


Hinweis: Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigem Anruf auf die SBC. Da Microsoft zwei Versionen von Transport Relays verfügt, wird Folgendes benötigt:

- v4, der nur Portbereich 50 000 zu 59 999 arbeiten kann

- V6, die mit der Ports 3478, 3479 verwendet

Zu diesem Zeitpunkt die medienumgehung v4 Version Transport Relays nur unterstützt. Wir werden in der Zukunft Unterstützung für v6 vorgestellt. 

Sie müssen die Ports 3478 und 3479 für den Übergang zu öffnen. Wenn Microsoft Unterstützung für v6 Transport Relays mit Medienumgehung eingeführt wird, müssen Sie nicht Ihre Netzwerkgeräte oder SBCs neu konfigurieren. 

### <a name="requirements-for-using-media-processors"></a>Anforderungen für die Verwendung von Medienprozessoren

Media-Prozessoren werden immer in der Medienpfad für VoIP-Anwendungen. Die Anforderungen sind die gleichen wie bei keine Umgehung Konfiguration.


Der IP-Adressbereich für Mediendatenverkehr ist 52.112.0.0 /14 (IP-Adressen von 52.112.0.1 bis 52.115.255.254).

Der Portbereich von des Prozessors Medien wird in der folgenden Tabelle gezeigt:

| Datenverkehr | Von | Bis | Quellport | Zielport|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Media-Prozessor | SBC | 49 152 – 53 247    | Klicken Sie auf die SBC definiert |
| UDP/SRTP | SBC | Media-Prozessor | Klicken Sie auf die SBC definiert | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>Aspekte, wenn Sie Skype für Business-Telefone in Ihrem Netzwerk verfügen  

Wenn Sie Skype für Business Endpunkte in Ihrem Netzwerk verfügen, die direkte Routing--verwenden muss beispielsweise ein Benutzer ein Telefon 3PIP sein kann, die für die Business-Client auf Skype basiert Teams die medienumgehung auf den Trunk, der diese Benutzer fungiert deaktiviert werden.

Sie können einen separaten Trunk für diese Benutzer erstellen und zuweisen eine Richtlinie für den Online-VoIP-Routing.

Allgemeine Konfigurationsschritte:

- Teilen Sie die Benutzer nach Typ – je nachdem, ob der Benutzer ein Telefon 3PIP verfügt.

- Erstellen Sie zwei separate Trunks mit unterschiedlichen FQDNs: eine aktiviert für die medienumgehung; andere nicht. 

  Beide Trunks zeigen Sie auf der gleichen SBC. Die Ports für TLS SIP-Signale müssen anders lauten. Die Ports für die müssen identisch sein.

- Weisen Sie den richtigen Trunk je nach Typ des Benutzers in der Online-VoIP-Routing-Richtlinie.

Im folgenden Beispiel wird die Logik.

| Gruppe von Benutzern | Anzahl von Benutzern | Trunk FQDN im OVRP zugewiesen | Medienumgehung |
| :------------ |:----------------- |:--------------|:--------------|
Benutzer mit Teams Clients und 3PIP Telefone | 20 | sbc1.contoso.com:5061 | false | 
Benutzer mit nur Teams Endpunkte (einschließlich neuer Telefone zertifiziert für Teams) | 980 | sbc2.contoso.com:5060 | True

Beide Trunks können auf der gleichen SBC mit derselben öffentlichen IP-Adresse verweisen. Die TLS-Ports in dem SBC Signale müssen unterschiedlich sein, wie in der folgenden Abbildung dargestellt. Beachten Sie, dass Sie benötigen, um sicherzustellen, dass Ihr Zertifikat beide Trunks unterstützt. SAN müssen Sie zwei Namen (**sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.


![Zeigt, die beide Trunks auf den gleichen SBC mit der gleichen öffentliche IP-Adresse verweisen können)](media/direct-routing-media-bypass-7.png)

Informationen zum Konfigurieren von zwei Trunks auf der gleichen SBC finden Sie in der Dokumentation Ihrer SBC-Herstellers:

- AudioCodes
- Bändchen
- TE-Systems (Anynode)   

## <a name="client-endpoints-supported-with-media-bypass"></a>Unterstützt mit Medien Clientendpunkte umgehen

Die medienumgehung wird mit allen Teams Endpunkten, mit Ausnahme von Teams Webclients bis auf Weiter unterstützt. 

Wenn Ihre Benutzer Teams Web-app in Microsoft Edge, Google Chrome oder Mozilla Firefox, lieber muss die medienumgehung für solche Benutzer deaktiviert. Eine Einführung in wird mithilfe eines Media Bypass aktiviert Trunks in der Zukunft aufrufen.   
 
## <a name="see-also"></a>Siehe auch

[Konfigurieren der Medienumgehung mit direktem Routing](direct-routing-configure-media-bypass.md)



