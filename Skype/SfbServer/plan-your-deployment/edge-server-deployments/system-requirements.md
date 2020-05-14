---
title: Edgeserver Systemanforderungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Zusammenfassung: Hier finden Sie Informationen zu den Systemanforderungen für Edgeserver in Skype for Business Server.'
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221025"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Edgeserver Systemanforderungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Systemanforderungen für Edgeserver in Skype for Business Server.
  
Wenn es um Ihre Skype for Business Server Edgeserver-Bereitstellung geht, müssen Sie diese Schritte für den Server oder Server in der Umgebung selbst sowie für die Planung der Umgebungsstruktur durchführen. Weitere Informationen zu Topologie, DNS, Zertifikaten und anderen Infrastrukturproblemen finden Sie in der Dokumentation zu Umgebungsanforderungen.
  
## <a name="components"></a>Komponenten

Bei der Erörterung der Edgeserver Umgebung verweisen wir auf Komponenten, die größtenteils in einem Umkreisnetzwerk bereitgestellt werden (d. h., es handelt sich entweder um eine Arbeitsgruppe oder eine Domäne außerhalb der Domänenstruktur des Skype for Business Server).
  
Berücksichtigen Sie dabei die Komponenten, die Sie für die erfolgreiche Bereitstellung Ihrer Edge beachten müssen:
  
- [Edgeserver](system-requirements.md#EdgeServers)
    
- [Reverse-Proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (diese sind optional, und wenn Sie enthalten sind, befinden Sie sich im internen Netzwerk)
    
- [Lasten](system-requirements.md#LoadBalancers) Ausgleichs Module (Sie können DNS-Lastenausgleich oder ein Hardwaregerät zum Lastenausgleich (HLB) haben, für einen einzelnen Edgeserver ist dies jedoch nicht erforderlich)
    
Wir haben ausführlichere Informationen zu den folgenden Themen:
  
### <a name="edge-servers"></a>Edgeserver
<a name="EdgeServers"> </a>

Dies sind die Skype for Business Server, die in ihrer Umkreis Umgebung bereitgestellt werden. Ihre Rolle besteht darin, Netzwerkdatenverkehr an externe Benutzer für die von ihrer internen Skype for Business Server-Bereitstellung angebotenen Dienste zu senden und zu empfangen. Um dies erfolgreich zu tun, wird jeder Edgeserver ausgeführt:
  
- **Zugriffs-Edgedienst**: stellt einen einzelnen vertrauenswürdigen Verbindungspfad für ausgehenden und eingehenden SIP-Datenverkehr (Session Initiation Protocol) bereit.
    
- **Webkonferenz-Edgedienst**: ermöglicht externen Benutzern, an Besprechungen teilzunehmen, die in ihrer internen Skype for Business Server Umgebung gehostet werden.
    
- **A/V-Edgedienst**: ermöglicht externen Benutzern das Bereitstellen von Audio-, Video-, Anwendungsfreigabe und Dateiübertragung.
    
- **XMPP-Proxy Dienst**: akzeptiert und sendet XMPP-Nachrichten (Extensible Messaging and Presence Protocol) an und von konfigurierten XMPP-Verbundpartnern.
    
Autorisierte externe Benutzer können Ihre Edgeserver verwenden, um eine Verbindung mit ihrer internen Skype for Business Server-Bereitstellung herzustellen, ansonsten bieten Sie jedoch keinen anderen Zugriff auf Ihr internes Netzwerk für andere Personen.
  
> [!NOTE]
> Edgeserver werden bereitgestellt, um Verbindungen für aktivierte Skype for Business Clients und andere Edgeserver (in Verbundszenarien) bereitzustellen. Sie können keine Verbindung von anderen End-Punkt-Client-oder Servertypen herstellen. Der XMPP-Gatewayserver kann Verbindungen mit konfigurierten XMPP-Partnern zulassen. Aber auch dies sind die einzigen Client-und Verbundtypen, die funktionieren werden. 

> [!NOTE]
> XMPP-Gateways und-Proxys stehen in Skype for Business Server 2015 zur Verfügung, werden in Skype for Business Server 2019 jedoch nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Reverse-Proxies
<a name="ReverseProxies"> </a>

Ein Reverseproxy-Server (Reverse Proxy) hat keine Skype for Business Server Rolle, ist jedoch eine wichtige Komponente einer Edgeserver-Bereitstellung. Ein Reverseproxy ermöglicht externen Benutzern Folgendes:
  
- Stellen Sie eine Verbindung zu Besprechungen oder Einwahlkonferenzen mithilfe einfacher URLs her.
    
- Laden Sie Besprechungsinhalte herunter.
    
- Erweitern Sie Verteilergruppen.
    
- Abrufen von benutzerbasierten Zertifikaten für die Clientzertifikat basierte Authentifizierung
    
- Laden Sie Dateien vom Adressbuch Server herunter, oder senden Sie Abfragen an die Adressbuch-Webabfragedienst.
    
- Abrufen von Updates für Client-und Geräte Software.
    
Und für mobile Geräte:
  
- Damit können Sie Front-End-Server, die Mobilitätsdienste anbieten, automatisch ermitteln.
    
- es aktiviert Push-Benachrichtigungen von Microsoft 365 oder Office 365 auf mobilen Geräten.
    
Unsere aktuellen Reverse-Proxy-Empfehlungen finden Sie auf der Seite [Telefonie-Infrastruktur für Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Also Ihr Reverse-Proxy:
  
- sollte in der Lage sein, TLS (Transport Layer Security), das in Ihrer Umgebung eingeführt wurde, über öffentliche Zertifikate zu verwenden, um eine Verbindung mit den veröffentlichten externen Webdiensten von herzustellen:
    
  - Director oder Director-Pool
    
  - Front-End-Server oder Front-End-Pool
    
- muss in der Lage sein, interne Websites mit Zertifikaten für die Verschlüsselung zu veröffentlichen oder Sie bei Bedarf über einen unverschlüsselten Weg zu veröffentlichen.
    
- sollte in der Lage sein, eine intern gehostete Website extern mit einem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) zu veröffentlichen.
    
- muss in der Lage sein, alle Inhalte der gehosteten Website zu veröffentlichen. Standardmäßig können Sie die *- **/\\** Direktive verwenden, die von den meisten Webservern erkannt wird, um "alle Inhalte auf dem Webserver veröffentlichen" zu verstehen. Sie können die Direktive auch ändern, beispielsweise * */UWCA/ \\ * * *, was bedeutet, dass alle Inhalte im virtuellen Verzeichnis Ucwa veröffentlicht werden.
    
- Es müssen TLS-Verbindungen mit Clients erforderlich sein, die Inhalte von ihrer veröffentlichten Website anfordern.
    
- Zertifikate mit den Einträgen des alternativen Antragstellernamens (Subject Alternative Name, San) akzeptiert.
    
- muss in der Lage sein, die Bindung eines Zertifikats an einen Listener oder eine Schnittstelle zuzulassen, über die der FQDN der externen Webdienste aufgelöst wird. Listener-Konfigurationen sind Schnittstellen vorzuziehen. Viele Listener können auf einer einzigen Schnittstelle konfiguriert werden.
    
- die Konfiguration der Hostheader Behandlung muss zugelassen werden. Häufig muss der vom anfordernden Client gesendete ursprüngliche Hostheader transparent übergeben werden, anstatt vom Reverseproxy geändert zu werden.
    
- sollte die Überbrückung von TLS-Datenverkehr von einem extern definierten Port (beispielsweise TCP 443) an einen anderen definierten Port ermöglichen (beispielsweise TCP 4443). Ihr Reverseproxy kann das Paket beim Empfang entschlüsseln und dann das Paket beim Senden erneut verschlüsseln.
    
- sollte das überbrücken von unverschlüsseltem TCP-Datenverkehr von einem Port (beispielsweise TCP 80) an einen anderen ermöglichen (beispielsweise TCP 8080).
    
- die Konfiguration oder Annahme, NTLM-Authentifizierung, keine Authentifizierung und Pass-Through-Authentifizierung muss zugelassen werden.
    
Wenn Ihr Reverseproxy alle Anforderungen in dieser Liste erfüllen kann, sollten Sie gut Vorgehen, aber denken Sie daran, dass Sie unsere Empfehlungen unter dem oben angegebenen Link beachten sollten.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Sie müssen die Edge-Bereitstellung hinter einer externen Firewall platzieren, es wird jedoch empfohlen, zwei Firewalls, eine externe und eine interne zwischen der Edge-Umgebung und ihrer internen Umgebung zu haben. Die gesamte Dokumentation in unseren Szenarien verfügt über zwei Firewalls. Wir empfehlen zwei Firewalls, da dadurch ein striktes Routing von einem Netzwerk-Edge zum anderen gewährleistet wird und der Firewallschutz für Ihr internes Netzwerk verdoppelt wird.
  
### <a name="directors"></a>Verwaltungsrat
<a name="Directors"> </a>

Dies ist eine optionale Rolle. Dabei kann es sich um einen einzelnen Server oder einen Pool von Servern handeln, auf denen die Director-Rolle läuft. Es handelt sich um eine Rolle, die in der internen Skype for Business Server Umgebung gefunden wird.
  
Der Director ist ein interner Server für den nächsten Hop, der eingehenden SIP-Datenverkehr von den Edgeserver empfängt, die für Skype for Business Server internen Servern bestimmt sind. Sie authentifiziert eingehende Anforderungen und leitet Sie an den privaten Pool oder Server eines Benutzers weiter. Mit dieser Vorauthentifizierung können Sie nicht identifizierte Benutzerkonto Anforderungen löschen.
  
Warum ist das wichtig? Eine wichtige Funktion für einen Director besteht darin, Standard Edition-Server und Front-End-Server oder Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen (DOS) zu schützen. Wenn Ihr Netzwerk mit ungültigem externem Datenverkehr überflutet wird, wird der Datenverkehr beim Director angehalten.
  
### <a name="load-balancers"></a>Lastenausgleichsmodule
<a name="LoadBalancers"> </a>

Die Skype for Business Server skalierte konsolidierte Edge-Topologie wurde für den DNS-Lastenausgleich für neue Bereitstellungen optimiert, und dies wird empfohlen. Wenn Sie hohe Verfügbarkeit benötigen, empfehlen wir die Verwendung eines Hardwaregerät zum Lastenausgleich für eine bestimmte Situation:
  
- Exchange um für Remotebenutzer, die Exchange um **vor** Exchange 2013 verwenden.
    
> [!IMPORTANT]
> Es ist wichtig zu beachten, dass Sie Lastenausgleichsmodule nicht kombinieren können. In Ihrer Skype for Business Server Umgebung müssen alle Schnittstellen entweder DNS oder HLB verwenden. 
  
> [!NOTE]
> DSR-NAT (Direct Server Return) wird für Skype for Business Server nicht unterstützt. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Hardwareanforderungen für den Lastenausgleich für Edgeserver, auf denen die A/V-Edgedienst

Für alle Edgeserver, die die A/V-Edgedienst durchführen, sind dies die Voraussetzungen:
  
- Deaktivieren Sie die TCP-Nagle sowohl für interne als auch für externe Ports 443 (Nagle ist der Prozess der Kombination mehrerer kleiner Pakete in einem einzigen, größeren Paket für eine effizientere Übertragung).
    
- Deaktivieren Sie die TCP-Nagle für den externen Portbereich 50000-59999.
    
- Verwenden Sie NAT nicht in ihren internen oder externen Firewalls.
    
- Die interne Edge-Schnittstelle muss sich in einem anderen Netzwerk befinden als die Edgeserver externe Schnittstelle, und das Routing zwischen diesen muss deaktiviert sein.
    
- Die externe Schnittstelle aller Edgeserver, die das A/V-Edgedienst ausführt, muss öffentlich routingfähige IP-Adressen und keine NAT-oder Portübersetzung für eine externe IP-Adresse der Edge verwenden.
    
#### <a name="hlb-requirements"></a>HLB-Anforderungen

Skype for Business Server hat keine Menge an Cookie-basierten Affinitäts Anforderungen. Sie müssen also keine Cookie-basierte Persistenz verwenden, **es sei denn** (und dies ist Skype for Business Server 2015 spezifisch), dass Sie lync Server 2010-Front-End-Server oder Front-End-Pools in Ihrer Skype for Business Server Umgebung haben werden. Sie benötigen eine auf Cookies basierende Affinität in der Konfigurationsmethode, die für lync Server 2010 empfohlen wird.
  
> [!NOTE]
> Wenn Sie sich entscheiden, die Cookie-basierte Affinität für Ihre HLB zu aktivieren, gibt es kein Problem, auch wenn Sie von Ihrer Umgebung nicht benötigt werden. 
  
Wenn Ihre Umgebung **keine** Cookie-basierte Affinität benötigt:
  
- Legen Sie in der Reverseproxy-Veröffentlichungsregel für Port 443 **Forward Hostheader** auf **true**fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
Für Bereitstellungen, **die eine** Cookie-basierte Affinität benötigen:
  
- Legen Sie in der Reverseproxy-Veröffentlichungsregel für Port 443 **Forward Hostheader** auf **true**fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
- Das Hardwaregerät zum Lastenausgleich **darf nicht** als "HttpOnly" gekennzeichnet werden.
    
- Das Hardwaregerät zum Lastenausgleich **darf keine** Ablaufzeit haben.
    
- Das Hardwaregerät zum Lastenausgleich **muss** den Namen **MS-WSMAN haben** haben (Dies ist der Wert, den die Webdienste erwarten und nicht geändert werden kann).
    
- Das Hardwaregerät zum Lastenausgleich **muss** in jeder HTTP-Antwort festgelegt werden, für die die eingehende HTTP-Anforderung kein Cookie besaß, unabhängig davon, ob eine vorherige HTTP-Antwort bei derselben TCP-Verbindung ein Cookie erhalten hat. Wenn Ihr Hardwaregerät zum Lastenausgleich die Cookie-Einfügung so optimiert, dass Sie nur einmal pro TCP-Verbindung erfolgt, darf diese Optimierung **nicht** verwendet werden.
    
> [!NOTE]
> Es ist typisch für HLB-Konfigurationen, die Quell Affinität und 20-minütige TCP-Sitzungslebensdauer zu verwenden, was für Skype for Business Server und seine Clients in Ordnung ist, da der Sitzungsstatus über die Clientnutzung und/oder die Anwendungs Interaktion verwaltet wird. 
  
Wenn Sie mobile Geräte bereitstellen, muss Ihre HLB in der Lage sein, einen Lastenausgleich für einzelne Anforderungen innerhalb einer TCP-Sitzung durchgeführt zu werden (tatsächlich müssen Sie in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse durchgeführt zu haben).
  
> [!IMPORTANT]
> F5 HLBs verfügen über ein Feature namens OneConnect. Dadurch wird sichergestellt, dass jede Anforderung innerhalb einer TCP-Verbindung einzeln Lastenausgleich erfolgt. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass Ihr HLB-Anbieter die gleiche Funktionalität unterstützt. Die neuesten IOS-Mobile Apps erfordern TLS-Version 1,2. Wenn Sie weitere Informationen benötigen, enthält F5 spezifische Einstellungen dafür. 
  
Hier sind die HLB-Anforderungen für den (optionalen) Director und (erforderlich) Front-End-Pool Webdienste:
  
- Legen Sie für Ihre internen Webdienste VIPs Source_addr Dauerhaftigkeit (interner Port 80, 443) auf Ihrer HLB fest. Für Skype for Business Server bedeutet Source_addr Persistenz, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse stammen, immer an einen Server gesendet werden, um den Sitzungsstatus beizubehalten.
    
- Verwenden Sie ein TCP-Leerlauftimeout von 1800 Sekunden.
    
- Erstellen Sie auf der Firewall zwischen dem Reverseproxy und dem HLB des nächsten Hop-Pools eine Regel, die https: Datenverkehr auf Port 4443 von Ihrem Reverseproxy zu ihrer HLB zulässt. Ihre HLB muss so konfiguriert werden, dass die Ports 80, 443 und 4443 überwacht werden.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Zusammenfassung der Anforderungen an die HLB-Affinität

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**Affinitäts Anforderungen für interne Webdienste-FQSN**|
|:-----|:-----|:-----|
|Skype for Business-Webanwendung (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business-Webanwendung (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business-Webanwendung (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Port Überwachung für HLBs

Sie definieren die Portüberwachung für Ihre Hardwarelastenausgleichs, um zu ermitteln, wann bestimmte Dienste aufgrund von Hardware-oder Kommunikationsfehlern nicht mehr verfügbar sind. Wenn beispielsweise der Front-End-Server Dienst (RTCSRV) angehalten wird, da die Front-End-Server oder Front-End-Pool fehlschlägt, sollte die HLB-Überwachung auch den Empfang von Datenverkehr auf dem Webdienste beenden. Sie sollten die Portüberwachung auf der HLB implementieren, um Folgendes für Ihre externe HLB-Schnittstelle zu überwachen:
  
|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool \> web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<Pool \> web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Wir haben Edgeserver Hardware-und Softwareanforderungen in den allgemeinen [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [System Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) -Dokumentation behandelt.
  
## <a name="collocation"></a>Kollokation

Wir haben Edgeserver-Zusammenstellungs [Grundlagen in den Grundlagen der Topologie für Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) Dokumentation behandelt.
  

