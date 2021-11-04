---
title: Systemanforderungen für Edgeserver in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Zusammenfassung: Erfahren Sie mehr über die Systemanforderungen für Edgeserver in Skype for Business Server.'
ms.openlocfilehash: 573c9c71493c4bed59ce6fbde4dafa95848b469f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763493"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Systemanforderungen für Edgeserver in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Systemanforderungen für Edgeserver in Skype for Business Server.
  
Wenn es um Ihre Skype for Business Server-Edgeserverbereitstellung geht, müssen Sie dies für den Server oder die Server tun, die sich in der Umgebung befinden, sowie die Planung der Umgebungsstruktur. Weitere Informationen zu Topologie, DNS, Zertifikaten und anderen Infrastrukturaspekten finden Sie in der Dokumentation zu den Umgebungsanforderungen.
  
## <a name="components"></a>Komponenten

Bei der Erläuterung der Edgeserverumgebung verweisen wir auf Komponenten, die größtenteils in einem Umkreisnetzwerk bereitgestellt werden (d. a. entweder in einer Arbeitsgruppe oder einer Domäne, die sich außerhalb Ihrer Skype for Business Server Domänenstruktur befindet).
  
Beachten Sie, dass dies die Komponenten sind, die Sie berücksichtigen müssen, um Ihren Edge erfolgreich bereitzustellen:
  
- [Edgeserver](system-requirements.md#EdgeServers)
    
- [Reverse-Proxys](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (diese sind optional, und wenn sie enthalten sind, befinden sie sich in Ihrem internen Netzwerk)
    
- [Lastenausgleichsmodule](system-requirements.md#LoadBalancers) (Sie können einen DNS-Lastenausgleich oder ein Hardwaregerät zum Lastenausgleich (Hardware Load Balancer, HLB) verwenden, für einen einzelnen Edgeserver ist dies jedoch nicht erforderlich.
    
Nachfolgend finden Sie weitere Details zu den einzelnen Themen:
  
### <a name="edge-servers"></a>Edgeserver
<a name="EdgeServers"> </a>

Dies sind die Skype for Business Server, die in Ihrer Umkreisumgebung bereitgestellt werden. Ihre Rolle besteht darin, Netzwerkdatenverkehr an externe Benutzer für die Dienste zu senden und zu empfangen, die von Ihrer internen Skype for Business Server-Bereitstellung angeboten werden. Um dies erfolgreich zu tun, wird auf jedem Edgeserver Folgendes ausgeführt:
  
- **Zugriffs-Edgedienst:** Stellt einen einzelnen vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden SIP-Datenverkehr (Session Initiation Protocol) bereit.
    
- **Webkonferenz-Edgedienst:** Ermöglicht externen Benutzern die Teilnahme an Besprechungen, die in Ihrer internen Skype for Business Server umgebung gehostet werden.
    
- **A/V-Edgedienst:** Macht Audio, Video, Anwendungsfreigabe und Dateiübertragung für externe Benutzer verfügbar.
    
- **XMPP-Proxydienst:** Akzeptiert und sendet XMPP-Nachrichten (Extensible Messaging and Presence Protocol) an und von konfigurierten XMPP-Verbundpartnern.
    
Autorisierte externe Benutzer können Ihre Edgeserver verwenden, um eine Verbindung mit Ihrer internen Skype for Business Server-Bereitstellung herzustellen, aber andernfalls gewähren sie keinen anderen Zugriff auf Ihr internes Netzwerk für andere Benutzer.
  
> [!NOTE]
> Edgeserver werden bereitgestellt, um Verbindungen für aktivierte Skype for Business Clients und andere Edgeserver (in Verbundszenarien) bereitzustellen. Sie können keine Verbindung von anderen Endpunktclient- oder Servertypen herstellen. Der XMPP-Gatewayserver kann Verbindungen mit konfigurierten XMPP-Partnern zulassen. Aber auch hier sind dies die einzigen Client- und Verbundtypen, die funktionieren. 

> [!NOTE]
> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)
  
### <a name="reverse-proxies"></a>Reverse-Proxys
<a name="ReverseProxies"> </a>

Ein Reverseproxyserver (RP) hat keine Skype for Business Server Rolle, ist aber eine wesentliche Komponente einer Edgeserverbereitstellung. Ein Reverseproxy ermöglicht externen Benutzern Folgendes:
  
- Stellen Sie über einfache URLs eine Verbindung mit Besprechungen oder Einwahlkonferenzen her.
    
- Besprechungsinhalte herunterladen.
    
- Verteilergruppen erweitern.
    
- Abrufen von benutzerbasierten Zertifikaten für die clientzertifikatbasierte Authentifizierung
    
- Dateien vom Adressbuchserver herunterladen oder Abfragen an den Adressbuchwebabfragedienst senden.
    
- Updates für Client- und Gerätesoftware erhalten.
    
Und für mobile Geräte:
  
- Dadurch können sie Front-End-Server, die Mobilitätsdienste anbieten, automatisch ermitteln.
    
- Es ermöglicht Pushbenachrichtigungen von Microsoft 365 oder Office 365 an mobile Geräte.
    
Unsere aktuellen Empfehlungen für Reverseproxys finden Sie auf der Seite ["Telefonieinfrastruktur für Skype for Business".](../../../SfbPartnerCertification/certification/infra-gateways.md) Ihr Reverseproxy also:
  
- transport layer security (TLS) verwenden können, die über öffentliche Zertifikate in Ihre Umgebung eingeführt wurde, um eine Verbindung mit den veröffentlichten externen Webdiensten herzustellen:
    
  - Director oder Director-Pool
    
  - Front-End-Server oder Front-End-Pool
    
- muss in der Lage sein, interne Websites mitHilfe von Zertifikaten für die Verschlüsselung zu veröffentlichen oder sie bei Bedarf unverschlüsselt zu veröffentlichen.
    
- sollte in der Lage sein, eine intern gehostete Website mithilfe eines vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) extern zu veröffentlichen.
    
- muss in der Lage sein, alle Inhalte Ihrer gehosteten Website zu veröffentlichen. Standardmäßig können Sie die **/\\** _-Direktive verwenden, die von den meisten Webservern als "Alle Inhalte auf dem Webserver veröffentlichen" erkannt wird. Sie können auch die Direktive ändern, z. B. _*/Uwca/ \\ ., was "Alle Inhalte im virtuellen Verzeichnis Ucwa veröffentlichen" bedeutet.
    
- müssen TLS-Verbindungen mit Clients erfordern, die Inhalte von Ihrer veröffentlichten Website anfordern.
    
- muss Zertifikate mit San-Einträgen (Subject Alternative Name) akzeptieren.
    
- muss die Bindung eines Zertifikats an einen Listener oder eine Schnittstelle zulassen können, über die der externe Webdienst-FQDN aufgelöst wird. Listenerkonfigurationen sind Schnittstellen vorzuziehen. Viele Listener können auf einer einzigen Schnittstelle konfiguriert werden.
    
- muss die Konfiguration der Hostheaderbehandlung zulassen. Häufig muss der ursprüngliche Hostheader, der vom anfordernden Client gesendet wird, transparent übergeben werden, anstatt vom Reverseproxy geändert zu werden.
    
- sollte das Überbrücken von TLS-Datenverkehr von einem extern definierten Port (z. B. TCP 443) zu einem anderen definierten Port (z. B. TCP 4443) zulassen. Ihr Reverseproxy kann das Paket beim Empfang entschlüsseln und das Paket dann beim Senden erneut entschlüsseln.
    
- sollte das Überbrücken des unverschlüsselten TCP-Datenverkehrs von einem Port (z. B. TCP 80) zu einem anderen zulassen (z. B. TCP 8080).
    
- muss die Konfiguration der NTLM-Authentifizierung, keine Authentifizierung und Pass-Through-Authentifizierung zulassen oder akzeptieren.
    
Wenn Ihr Reverseproxy alle Anforderungen in dieser Liste erfüllen kann, sollten Sie gut zu gehen, aber bitte beachten Sie unsere Empfehlungen unter dem oben angegebenen Link.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Sie müssen ihre Edgebereitstellung hinter einer externen Firewall platzieren, es wird jedoch empfohlen, zwei Firewalls, eine externe und eine interne, zwischen der Edgeumgebung und Ihrer internen Umgebung zu verwenden. Die gesamte Dokumentation in unseren Szenarien wird über zwei Firewalls verfügen. Wir empfehlen zwei Firewalls, da sie ein striktes Routing von einem Netzwerkrand zum anderen sicherstellen und den Firewallschutz für Ihr internes Netzwerk verdoppelt.
  
### <a name="directors"></a>Directors
<a name="Directors"> </a>

Dies ist eine optionale Rolle. Dies kann ein einzelner Server oder ein Pool von Servern sein, auf denen die Directorrolle ausgeführt wird. Es handelt sich um eine Rolle in der internen Skype for Business Server Umgebung.
  
Der Director ist ein interner nächster Hopserver, der eingehenden SIP-Datenverkehr von den Edgeservern empfängt, die für Skype for Business Server interne Server bestimmt sind. Eingehende Anforderungen werden vorab authentifiziert und an den Homepool oder Server eines Benutzers umgeleitet. Mit dieser Vorauthentifizierung können Sie nicht identifizierte Benutzerkontoanforderungen ablegen.
  
Warum ist das wichtig? Eine wichtige Funktion für einen Director besteht darin, Standard Edition Server und Front-End-Server oder Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service (DoS)-Angriffen zu schützen. Wenn Ihr Netzwerk mit ungültigen externen Datenverkehr überschwemmt wird, wird der Datenverkehr beim Director beendet.
  
### <a name="load-balancers"></a>Lastenausgleichsmodule
<a name="LoadBalancers"> </a>

Die Skype for Business Server skalierte konsolidierte Edgetopologie ist für den DNS-Lastenausgleich für neue Bereitstellungen optimiert. Dies wird empfohlen. Wenn Sie hohe Verfügbarkeit benötigen, empfehlen wir die Verwendung eines Hardwaregeräts zum Lastenausgleich für eine bestimmte Situation:
  
- Exchange UM für Remotebenutzer, die Exchange UM **vor** Exchange 2013 verwenden.
    
> [!IMPORTANT]
> Es ist wichtig zu beachten, dass Sie Lastenausgleichsmodule nicht kombinieren können. In Ihrer Skype for Business Server Umgebung müssen alle Schnittstellen entweder DNS oder HLB verwenden. 
  
> [!NOTE]
> Die NAT für direkte Serverrückgabe (Direct Server Return, DSR) wird für Skype for Business Server nicht unterstützt. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Anforderungen an das Hardwaregerät zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird

Für jeden Edgeserver, auf dem der A/V-Edgedienst ausgeführt wird, gelten die folgenden Anforderungen:
  
- Deaktivieren Sie tcp nagling für interne und externe Ports 443 (Nagling ist der Prozess der Kombination mehrerer kleiner Pakete in einem einzigen, größeren Paket für eine effizientere Übertragung).
    
- Deaktivieren Sie tcp nagling für den externen Portbereich 50000 - 59999.
    
- Verwenden Sie NAT nicht für Ihre internen oder externen Firewalls.
    
- Die interne Edgeschnittstelle muss sich in einem anderen Netzwerk als die externe Edgeserverschnittstelle befinden, und das Routing zwischen diesen muss deaktiviert sein.
    
- Die externe Schnittstelle eines Edgeservers, auf dem der A/V-Edgedienst ausgeführt wird, muss öffentlich routingfähige IP-Adressen und keine NAT- oder Portübersetzung für externe Edge-IP-Adressen verwenden.
    
#### <a name="hlb-requirements"></a>HLB-Anforderungen

Skype for Business Server hat nicht viele cookiebasierte Affinitätsanforderungen. Sie müssen also keine cookiebasierte Persistenz verwenden, **es sei denn** (und dies ist Skype for Business Server 2015-spezifisch) werden Lync Server 2010-Front-End-Server oder Front-End-Pools in Ihrer Skype for Business Server Umgebung haben. Sie benötigen cookiebasierte Affinität in der für Lync Server 2010 empfohlenen Konfigurationsmethode.
  
> [!NOTE]
> Wenn Sie sich dafür entscheiden, die cookiebasierte Affinität für Ihre HLB zu aktivieren, gibt es kein Problem, dies zu tun, auch wenn Ihre Umgebung sie nicht benötigt. 
  
Wenn Ihre Umgebung **keine** cookiebasierte Affinität benötigt:
  
- Legen Sie in der Reverseproxy-Veröffentlichungsregel für Port 443 den **Forward-Hostheader** auf **"True"** fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
Für **Bereitstellungen,** die cookiebasierte Affinität benötigen:
  
- Legen Sie in der Reverseproxy-Veröffentlichungsregel für Port 443 den **Forward-Hostheader** auf **"True"** fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich **darf nicht** als "httpOnly" gekennzeichnet werden.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich **darf keine** Ablaufzeit haben.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich **muss** **"MS-WSMAN"** heißen (dies ist der Wert, den die Webdienste erwarten, und er kann nicht geändert werden).
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich **muss** in jeder HTTP-Antwort festgelegt werden, für die die eingehende HTTP-Anforderung kein Cookie hatte, unabhängig davon, ob eine vorherige HTTP-Antwort auf derselben TCP-Verbindung ein Cookie erhalten hat. Wenn Ihr Hardwaregerät zum Lastenausgleich das Einfügen von Cookies so optimiert, dass es nur einmal pro TCP-Verbindung auftritt, darf diese Optimierung **nicht** verwendet werden.
    
> [!NOTE]
> Es ist typisch für HLB-Konfigurationen, die Quellaffinität und die 20-minütige TCP-Sitzungsdauer zu verwenden, was für Skype for Business Server und deren Clients geeignet ist, da der Sitzungsstatus über die Clientverwendung und/oder Anwendungsinteraktion beibehalten wird. 
  
Wenn Sie mobile Geräte bereitstellen, muss Ihr HLB in der Lage sein, einzelne Anforderungen innerhalb einer TCP-Sitzung zu lasten (tatsächlich müssen Sie in der Lage sein, eine einzelne Anforderung basierend auf der Ziel-IP-Adresse zu laden).
  
> [!IMPORTANT]
> F5-HLBs verfügen über ein Feature namens OneConnect. Es wird sichergestellt, dass jede Anforderung innerhalb einer TCP-Verbindung einzeln geladen wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass Ihr HlB-Anbieter die gleiche Funktionalität unterstützt. Für die neuesten mobilen iOS-Apps ist TLS Version 1.2 erforderlich. Wenn Sie mehr wissen müssen, stellt F5 bestimmte Einstellungen dafür bereit. 
  
Hier sind die HLB-Anforderungen für die (optionalen) Director- und (erforderlichen) Front-End-Poolwebdienste:
  
- Legen Sie für die internen WEBDIENSTE-VIPs Source_addr Persistenz (interner Port 80, 443) auf dem HLB fest. Für Skype for Business Server bedeutet Source_addr Persistenz, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse stammen, immer an einen Server gesendet werden, um den Sitzungsstatus aufrechtzuerhalten.
    
- Verwenden Sie ein TCP-Leerlauftimeout von 1800 Sekunden.
    
- Erstellen Sie in der Firewall zwischen dem Reverseproxy und dem HLB des nächsten Hoppools eine Regel, die https: Datenverkehr an Port 4443 von Ihrem Reverseproxy zu Ihrem HLB zulässt. Ihr HlB muss für das Überwachen der Ports 80, 443 und 4443 konfiguriert sein.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Zusammenfassung der HLB-Affinitätsanforderungen

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**FQSN-Affinitätsanforderungen für interne Webdienste**|
|:-----|:-----|:-----|
|Skype for Business-Web-App (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business-Web-App (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business-Web-App (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Portüberwachung für HLBs

Sie definieren die Portüberwachung für Ihre Hardwaregeräte zum Lastenausgleich, um zu bestimmen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind. Wenn beispielsweise der Front-End-Serverdienst (RTCSRV) beendet wird, weil der Front-End-Server oder Front-End-Pool fehlschlägt, sollte die HLB-Überwachung auch den Empfang von Datenverkehr in den Webdiensten beenden. Sie sollten die Portüberwachung auf der HLB implementieren, um Folgendes für die externe HLB-Schnittstelle zu überwachen:
  
|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Wir haben die Hardware- und Softwareanforderungen des Edgeservers in unseren allgemeinen [Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [Systemanforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) behandelt.
  
## <a name="collocation"></a>Kollokation

Wir haben die Edgeserverkollokation in unseren [Topologiegrundlagen für Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) Dokumentation behandelt.
