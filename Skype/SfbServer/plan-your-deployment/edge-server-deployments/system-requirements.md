---
title: Systemanforderungen für Edge-Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Zusammenfassung: erfahren Sie mehr über die Systemanforderungen für Edgeserver in Skype for Business Server.'
ms.openlocfilehash: 01a5cce8dd1ccb85d322b6c66615d022c8d6c2df
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277146"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Systemanforderungen für Edge-Server in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über die Systemanforderungen für Edgeserver in Skype for Business Server.
  
Wenn es um Ihre Bereitstellung von Skype for Business Server Edge Server geht, müssen Sie für den Server oder die Server, die sich in der Umgebung befinden, und für die Planung der Umgebungsstruktur Vorgehen. Für weitere Informationen zu den Punkten Topologie, DNS, Zertifikate und zu weiteren Infrastrukturfragen, prüfen Sie die Dokumentation zu den Umgebungsanforderungen.
  
## <a name="components"></a>Komponenten

Bei der Diskussion der Edge-Server-Umgebung verweisen wir auf Komponenten, die größtenteils in einem Umkreisnetzwerk bereitgestellt werden (also entweder in einer Arbeitsgruppe oder in einer Domäne außerhalb Ihrer Domänenstruktur von Skype for Business Server).
  
Denken Sie daran, dass Sie die folgenden Komponenten benötigen, um Ihren Edgeserver erfolgreich bereitzustellen:
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (diese sind optional und werden auf Ihrem internen Netzwerk befinden, falls sie enthalten sind)
    
- [Lastenausgleich](system-requirements.md#LoadBalancers) (Sie können DNS-Lastenausgleich oder ein Hardwarelastenausgleich (Hardware Load Balancer, HLB), aber für einen einzelnen Edgeserver haben, ist dies nicht erforderlich)
    
Zu jedem der unteren Punkte gibt es weitere Details:
  
### <a name="edge-servers"></a>Edgeservers
<a name="EdgeServers"> </a>

Hierbei handelt es sich um die Skype for Business-Server, die in ihrer Umkreis Umgebung bereitgestellt werden. Ihre Rolle ist das Senden und empfangen von Netzwerkdatenverkehr an externe Benutzer für die Dienste, die von ihrer internen Skype for Business Server-Bereitstellung angeboten werden. Um dies erfolgreich durchführen zu können, wird jeder Edgeserver ausgeführt:
  
- **Access**-Edgedienst: stellt einen einzelnen, vertrauenswürdigen Verbindungspunkt für ausgehende und eingehende SIP-Datenverkehr (Session Initiation Protocol) bereit.
    
- **Webkonferenz-Edgedienst**: ermöglicht externen Benutzern, an Besprechungen teilzunehmen, die in ihrer internen Skype for Business Server-Umgebung gehostet werden.
    
- **A/V**-Edgedienst: ermöglicht externen Benutzern die Bereitstellung von Audio, Video, Anwendungsfreigabe und Dateiübertragung.
    
- **XMPP-Proxy Dienst**: akzeptiert und sendet Nachrichten zu und von konfigurierten XMPP-Verbundpartnern (Extensible Messaging and Presence Protocol).
    
Autorisierte externe Benutzer können Ihre Edgeserver verwenden, um eine Verbindung mit ihrer internen Skype for Business Server-Bereitstellung herzustellen, aber ansonsten bieten Sie keinen anderen Zugriff auf Ihr internes Netzwerk für andere.
  
> [!NOTE]
> Edgeserver werden bereitgestellt, um Verbindungen für aktivierte Skype for Business-Clients und andere Edgeserver (in Verbundszenarien) bereitzustellen. Sie können keine Verbindungen von anderen Endpunktclients oder Servertypen herstellen. Der XMPP-Gatewayserver kann für die Verbindungen mit konfigurierten XMPP-Partnern eingesetzt werden. Denken Sie daran, dass dies die einzigen Client- und Verbundtypen sind, die funktionieren. 

> [!NOTE]
> XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Reverseproxys
<a name="ReverseProxies"> </a>

Ein Reverse Proxy-Server (RP) verfügt über keine Skype for Business-Serverrolle, ist aber eine wichtige Komponente einer Edge-Server-Bereitstellung. Ein Reverse-Proxy ermöglicht externen Benutzern Folgendes:
  
- Die Teilnahme an Besprechungen oder Einwahlkonferenzen über einfache URLs.
    
- Das Herunterladen von Besprechungsinhalten.
    
- Das Erweitern von Verteilergruppen.
    
- Das Erhalten von benutzerbasierten Zertifikaten für die auf Clientzertifikaten basierenden Authentifizierungen.
    
- Laden Sie Dateien vom Adressbuch Server herunter, oder senden Sie Abfragen an den Adressbuch-Webabfrage Dienst.
    
- Das Abrufen von Updates für Client- und Gerätesoftware.
    
Und für mobile Geräte:
  
- Damit können Sie Front-End-Server, die Mobilitätsdienste anbieten, automatisch erkennen.
    
- Es ermöglicht Push-Benachrichtigungen von Office 365 auf mobile Geräte.
    
Unsere aktuellen Reverse-Proxy-Empfehlungen finden Sie auf der Seite [Telefonie-Infrastruktur für Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Ihr Reverse-Proxy:
  
- TLS (Transport Layer Security)-Verbindungen zu verwenden, die in Ihrer Umgebung über öffentliche Zertifikate bereitgestellt werden, um eine Verbindung mit den folgenden veröffentlichten externen Webdiensten herzustellen:
    
  - Director-oder Director-Pool
    
  - Front-End-Server oder Front-End-Pool
    
- Interne Websites mithilfe von Zertifikaten für die Verschlüsselung zu veröffentlichen oder diese bei Bedarf unverschlüsselt zu veröffentlichen.
    
- Eine intern gehostete Website extern mit einem voll qualifizierten Domänennamen (FQDN) zu veröffentlichen.
    
- Alle Inhalte Ihrer gehosteten Website zu veröffentlichen. Standardmäßig können Sie die ** / **von den meisten Webservern erkannte *-Direktive verwenden, um "alle Inhalte auf dem Webserver veröffentlichen" zu verstehen. Sie können die Direktive auch ändern, beispielsweise * */UWCA/\\* * *, was bedeutet, dass "alle Inhalte im virtuellen Verzeichnis Ucwa veröffentlicht werden".
    
- TLS-Verbindungen mit Clients voraussetzen, die Inhalte von Ihrer veröffentlichten Website anfordern.
    
- Zertifikate zu akzeptieren, die über „SAN-Einträge“ (alternative Antragstellernamen) verfügen.
    
- Die Zertifikatbindung an Listener oder Schnittstellen zu erlauben, über die der externe Webdienste-FQDN aufgelöst wird. Listenerkonfigurationen sind Schnittstellen vorzuziehen. Viele Listener können in einer einzelnen Schnittstelle konfiguriert werden.
    
- Die Konfiguration der Hostheaderbehandlung zuzulassen. Häufig muss der vom anfordernden Client gesendete ursprüngliche Hostheader transparent übergeben werden, anstatt vom Reverse-Proxy geändert zu werden.
    
- Das Überbrücken des TLS-Datenverkehrs von einem extern definierten Port (z. B. TCP 443) zu einem anderen definierten Port (z. B. TCP 4443) zu erlauben. Ihr umgekehrter Proxy entschlüsselt das Paket möglicherweise beim Empfang und verschlüsselt das Paket beim Senden erneut.
    
- Das Überbrücken des unverschlüsselten TCP-Datenverkehrs von einem Port (z. B. TCP 80) zu einem anderen Port (z. B. TCP 8080) zu erlauben.
    
- Konfiguration von NTLM-Authentifizierung, keiner Authentifizierung und Pass-Through-Authentifizierung zu erlauben oder zu akzeptieren.
    
Wenn Ihr Reverse-Proxy alle Anforderungen in dieser Liste erfüllen kann, sollten Sie gut gehen, aber bitte beachten Sie unsere Empfehlungen unter dem oben angegebenen Link.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Sie müssen Ihre Edgebereitstellung hinter einer externen Firewall platzieren. Wir raten Ihnen aber dazu, über zwei Firewalls, eine externe und eine interne, zwischen der Edge-Umgebung und Ihrer internen Umgebung zu verfügen. Die Dokumentationen in unseren Szenarien haben alle zwei Firewalls. Wir empfehlen deshalb zwei Firewalls, weil dies ein striktes Routing von einer Netzwerkedge zur anderen sicherstellt. Außerdem verdoppelt dies den Firewall-Schutz für Ihr internes Netzwerk.
  
### <a name="directors"></a>Directors
<a name="Directors"> </a>

Dies ist eine optionale Rolle. Hierbei kann es sich um einen einzelnen Server oder einen Serverpool handeln, auf dem die Director-Rolle ausgeführt wird. Diese Rolle befindet sich in der internen Skype for Business Server-Umgebung.
  
Der Director ist ein interner Server für den nächsten Hop, der eingehenden SIP-Datenverkehr von den Edge-Servern empfängt, die für Skype for Business Server-interne Server bestimmt sind. Er authentifiziert vorab eingehende Anfragen und leitet diese an den Home-Pool oder Server eines Benutzers weiter. Diese Vorabauthentifizierung erlaubt es Ihnen, Anfragen von unbekannten Nutzerkontos zu verwerfen.
  
Warum ist das von Bedeutung? Eine wichtige Funktion eines Directors besteht darin, Standard Edition-Server und-Front-End-Server oder Front-End-Pools vor böswilligem Datenverkehr wie DOS-Attacken (Denial-of-Service) zu schützen. Wenn Ihr Netzwerk mit einem ungültigen externen Datenverkehr überflutet wird, wird der Datenverkehr beim Director angehalten.
  
### <a name="load-balancers"></a>Lastenausgleichsysteme
<a name="LoadBalancers"> </a>

Die von Skype for Business Server skalierte konsolidierte Edge-Topologie ist für den DNS-Lastenausgleich für neue Bereitstellungen optimiert, und wir empfehlen dies. Wenn Sie eine hohe Verfügbarkeit benötigen, empfehlen wir die Verwendung eines Hardware-Lastenausgleichs für eine bestimmte Situation:
  
- Exchange um für Remotebenutzer, die Exchange um **vor** Exchange 2013 verwenden.
    
> [!IMPORTANT]
> Es ist wichtig, zu beachten, dass Sie Lastenausgleichssysteme nicht miteinander kombinieren können. In Ihrer Skype for Business Server-Umgebung müssen alle Schnittstellen entweder DNS oder HLB verwenden. 
  
> [!NOTE]
> Die direkte Server Rückgabe (DSR) NAT wird für Skype for Business Server nicht unterstützt. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Anforderungen an den Hardwarelastenausgleich für Edgeserver-Edgeserver mit dem A/V-Edgedienst

Für jeden Edgeserver, auf dem der A/V-Edgedienst ausgeführt wird, gelten die folgenden Voraussetzungen:
  
- Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443 (der Nagle-Algorithmus fasst mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammen).
    
- Deaktivieren Sie den Nagle-Algorithmus für TCP für den Bereich der externen Ports 50000 bis 59999.
    
- Verwenden Sie keine Netzwerkadressenübersetzung (NAT) für Ihre interne oder externe Firewall.
    
- Ihre Edge-interne Schnittstelle muss sich in einem anderen Netzwerk als die externe Edge-Server-Schnittstelle befinden, und das Routing zwischen diesen muss deaktiviert sein.
    
- Die externe Schnittstelle eines beliebigen Edgeserver, auf dem der A/V-Edgedienst ausgeführt wird, muss öffentlich routingfähige IP-Adressen und keine NAT-oder Portübersetzung für beliebige externe IP-Adressen verwenden.
    
#### <a name="hlb-requirements"></a>HLB-Anforderungen

Für Skype for Business Server gibt es keine hohen Anforderungen an die Affinität auf Cookies. Sie müssen also keine Cookie-basierte Persistenz verwenden **, es sei denn** (und das ist Skype for Business Server 2015-spezifisch), dass Sie lync Server 2010-Front-End-Server oder Front-End-Pools in Ihrer Skype for Business Server-Umgebung haben werden. Sie benötigen eine auf Cookies basierende Affinität in der für lync Server 2010 empfohlenen Konfigurationsmethode.
  
> [!NOTE]
> Wenn Sie sich dafür entscheiden, die cookiebasierte Affinität für Ihre Hardware zum Lastenausgleich (HLB) zu aktivieren, können Sie dies problemlos tun, selbst wenn es für Ihre Umgebung nicht notwendig ist. 
  
Wenn Ihre Umgebung **keine** cookiebasierte Affinität benötigt:
  
- Legen Sie in der Reverse Proxy-Veröffentlichungsregel für Port 443 den **Header Forward Host** auf **true**fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
Für Bereitstellungen, in denen die cookiebasierte Affinität **verwendet** wird:
  
- Legen Sie in der Reverse Proxy-Veröffentlichungsregel für Port 443 den **Header Forward Host** auf **true**fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
- Das Hardware-Lastenausgleichsmodul-Cookie **darf nicht** als HttpOnly markiert sein.
    
- Das Hardware-Lastenausgleichsmodul-Cookie **darf keine** Ablaufzeit aufweisen.
    
- Das Hardware-Lastenausgleichsmodul-Cookie **muss** den Namen **MS-WSMAN** haben (Dies ist der Wert, den die Webdienste erwarten, und kann nicht geändert werden).
    
- Das Hardware-Lastenausgleichsmodul-Cookie **muss** in jeder HTTP-Antwort festgesetzt werden, für die die eingehende HTTP-Anforderung kein Cookie besaß, unabhängig davon, ob eine vorherige HTTP-Antwort auf derselben TCP-Verbindung ein Cookie erhalten hat. Wenn Ihr Hardware-Lastenausgleichsmodul die Cookie-Einfügung so optimiert, dass Sie nur einmal pro TCP-Verbindung ausgeführt wird, darf diese Optimierung **nicht** verwendet werden.
    
> [!NOTE]
> Es ist typisch für HLB-Konfigurationen, die Quell Affinität und 20-minütige TCP-Sitzungslebensdauer zu verwenden, was für Skype for Business Server und seine Clients in Ordnung ist, da der Sitzungszustand über die Clientnutzung und/oder die Anwendungs Interaktion verwaltet wird. 
  
Wenn Sie mobile Geräte bereitstellen, muss Ihr Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).
  
> [!IMPORTANT]
> F5-Hardwaregeräte zum Lastenausgleich sind mit einer Funktion namens „OneConnect“ ausgestattet. Sie stellt sicher, dass für jede Anforderung in einer TCP-Verbindung ein individueller Lastenausgleich vorgenommen wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass der Hersteller des Hardwaregeräts für den Lastenausgleich dieselbe Funktion unterstützt. Für die neuesten mobilen Apps von Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich. F5 stellt hierfür bestimmte Einstellungen bereit. 
  
Hier sind die HLB-Anforderungen für die (optionalen) Director-und (required)-Front-End-Pool-Webdienste:
  
- Für Ihre internen Webdienste VIPs setzen Sie Source_addr-Persistenz (interner Port 80, 443) auf Ihrer HLB-Website. Bei Skype for Business Server bedeutet Source_addr-Persistenz, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse kommen, immer an einen Server gesendet werden, um den Sitzungsstatus beizubehalten.
    
- Verwenden Sie ein TCP-Leerlauftimeout von 1.800 Sekunden.
    
- Erstellen Sie auf der Firewall zwischen dem Reverseproxy und dem HLB des nächsten Hop-Pools eine Regel, die https: Traffic auf Port 4443, vom Reverse-Proxy an Ihre HLB zulässt. Das HLB muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Zusammenfassung der HLB-Affinitätsanforderungen

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**Affinitätsanforderungen an den internen Webdienste-FQSN**|
|:-----|:-----|:-----|
|Skype for Business Web App (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business Web App (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business Web App (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Portüberwachung für Hardwaregeräte zum Lastenausgleich

Sie definieren die Portüberwachung für Ihre Hardwarelastenausgleichs, um zu ermitteln, wann bestimmte Dienste aufgrund von Hardware-oder Kommunikationsfehlern nicht mehr zur Verfügung stehen. Wenn beispielsweise der Front-End-Server Dienst (RTCSRV) angehalten wird, weil der Front-End-Server oder der Front-End-Pool fehlschlägt, sollte die HLB-Überwachung auch den Empfang von Datenverkehr über die Webdienste beenden. Sie sollten die HLB-Portüberwachung implementieren, um Folgendes für die externe Schnittstelle Ihres HLBs zu überwachen:
  
|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<Pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Wir haben die Hardware-und Softwareanforderungen für Edge-Server in unseren allgemeinen [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und die [System Anforderungen für die Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) -Dokumentation berücksichtigt.
  
## <a name="collocation"></a>Kollokation

In unseren [Topologie-Grundlagen für die Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) -Dokumentation haben wir die Edge-Server-Zusammenarbeit abgedeckt.
  

