---
title: Edgeserversystemanforderungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Erfahren Sie mehr über die Systemanforderungen für Edgeserver in Skype for Business Server.'
ms.openlocfilehash: d5003a265a53c3603892133077a961f54c974401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112741"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Edgeserversystemanforderungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Systemanforderungen für Edgeserver in Skype for Business Server.
  
Wenn es um Ihre Skype for Business Server Edge Server-Bereitstellung geht, müssen Sie dies für die Server oder Server, die sich in der Umgebung selbst befinden, sowie für die Planung der Umgebungsstruktur tun. Weitere Informationen zu Topologie, DNS, Zertifikaten und anderen Infrastrukturbedenken finden Sie in der Dokumentation zu den Umweltanforderungen.
  
## <a name="components"></a>Komponenten

Bei der Erörterung der Edgeserverumgebung verweisen wir auf Komponenten, die zum größten Teil in einem Umkreisnetzwerk bereitgestellt werden (d. h. entweder in einer Arbeitsgruppe oder einer Domäne außerhalb Ihrer Skype for Business Server-Domänenstruktur).
  
Beachten Sie, dass dies die Komponenten sind, die Sie bei der erfolgreichen Bereitstellung Ihres Edge berücksichtigen müssen:
  
- [Edgeserver](system-requirements.md#EdgeServers)
    
- [Reverse-Proxys](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (diese sind optional, und wenn sie enthalten sind, befinden sie sich in Ihrem internen Netzwerk)
    
- [Lastenausgleichsgeräte](system-requirements.md#LoadBalancers) (Sie können den #A0 oder einen Hardwaregerät zum Lastenausgleich (Hardware Load Balancer, HLB) verwenden, aber für einen einzelnen Edgeserver ist dies nicht erforderlich.
    
Nachfolgend finden Sie weitere Details zu den folgenden Informationen:
  
### <a name="edge-servers"></a>Edgeserver
<a name="EdgeServers"> </a>

Dies sind die Skype for Business-Server, die in Ihrer Umkreisumgebung bereitgestellt werden. Ihre Rolle besteht in dem Senden und Empfangen von Netzwerkdatenverkehr an externe Benutzer für die Von Ihrer internen Skype for Business Server-Bereitstellung angebotenen Dienste. Um dies erfolgreich zu tun, wird jeder Edgeserver ausgeführt:
  
- **Access Edge-Dienst:** Stellt einen einzelnen, vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden Sip-Datenverkehr (Session Initiation Protocol) zur Verfügung.
    
- **Webkonferenz-Edgedienst:** Ermöglicht externen Benutzern, an Besprechungen teilzunehmen, die in Ihrer internen Skype for Business Server-Umgebung gehostet werden.
    
- **A/V-Edgedienst:** Stellt Audio, Video, Anwendungsfreigabe und Dateiübertragung für externe Benutzer zur Verfügung.
    
- **XMPP-Proxydienst:** Akzeptiert und sendet XMPP-Nachrichten (Extensible Messaging and Presence Protocol) an und von konfigurierten XMPP-Verbundpartnern.
    
Autorisierte externe Benutzer können Ihre Edgeserver verwenden, um eine Verbindung mit Ihrer internen Skype for Business Server-Bereitstellung herzustellen, aber andernfalls bieten sie keinem anderen Zugriff auf Ihr internes Netzwerk.
  
> [!NOTE]
> Edgeserver werden bereitgestellt, um Verbindungen für aktivierte Skype for Business-Clients und andere Edgeserver (in Verbundszenarien) zu ermöglichen. Sie können keine Verbindung von anderen Client- oder Servertypen des Endpunkts herstellen. Der XMPP-Gatewayserver kann Verbindungen mit konfigurierten XMPP-Partnern zulassen. Aber auch dies sind die einzigen Client- und Verbundtypen, die funktionieren. 

> [!NOTE]
> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter Migrieren des [XMPP-Verbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)
  
### <a name="reverse-proxies"></a>Reverse-Proxys
<a name="ReverseProxies"> </a>

Ein Reverseproxyserver hat keine Skype for Business Server-Rolle, ist aber eine wesentliche Komponente einer Edgeserverbereitstellung. Ein Reverseproxy ermöglicht externen Benutzern:
  
- Herstellen einer Verbindung mit Besprechungen oder Einwahlkonferenzen mithilfe einfacher URLs.
    
- Herunterladen von Besprechungsinhalten.
    
- Verteilergruppen erweitern.
    
- Benutzerbasierte Zertifikate für die clientzertifikatbasierte Authentifizierung erhalten
    
- Laden Sie Dateien vom Adressbuchserver herunter, oder senden Sie Abfragen an den Adressbuchwebabfragedienst.
    
- Abrufen von Updates für Client- und Gerätesoftware.
    
Und für mobile Geräte:
  
- Sie können damit automatisch Front-End-Server ermitteln, die Mobilitätsdienste anbieten.
    
- Es ermöglicht Pushbenachrichtigungen von Microsoft 365 oder Office 365 auf mobile Geräte.
    
Unsere aktuellen Reverseproxyempfehlungen finden Sie auf der [Seite Telefonieinfrastruktur für Skype for Business.](../../../SfbPartnerCertification/certification/infra-gateways.md) Ihr Reverseproxy:
  
- sollte in der Lage sein, transport layer security (TLS) zu verwenden, die über öffentliche Zertifikate in Ihre Umgebung eingeführt wird, um eine Verbindung mit den veröffentlichten externen Webdiensten von:
    
  - Director oder Director-Pool
    
  - Front-End-Server oder Front-End-Pool
    
- muss in der Lage sein, interne Websites mithilfe von Zertifikaten für die Verschlüsselung zu veröffentlichen oder sie bei Bedarf unverschlüsselt zu veröffentlichen.
    
- sollte in der Lage sein, eine intern gehostete Website mithilfe eines vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) extern zu veröffentlichen.
    
- muss in der Lage sein, alle Inhalte Ihrer gehosteten Website zu veröffentlichen. Standardmäßig können Sie die _-Direktive verwenden, die von den meisten Webservern als "Veröffentlichen aller Inhalte auf dem **/\\** Webserver" erkannt wird. Sie können auch die Direktive ändern, z. B. _*/Uwca/ ***, was "Veröffentlichen aller Inhalte unter dem virtuellen Verzeichnis \\ Ucwa" bedeutet.
    
- muss TLS-Verbindungen mit Clients erfordern, die Inhalte von Ihrer veröffentlichten Website anfordern.
    
- muss Zertifikate mit alternativen Namen (Subject Alternative Name, SAN) akzeptieren.
    
- muss die Bindung eines Zertifikats an einen Listener oder eine Schnittstelle zulassen können, über die der FQDN der externen Webdienste aufgelöst wird. Listenerkonfigurationen sind Schnittstellen vorzuziehen. Viele Listener können auf einer einzelnen Schnittstelle konfiguriert werden.
    
- muss die Konfiguration der Hostheaderbehandlung zulassen. Häufig muss der ursprüngliche Vom anfordernden Client gesendete Hostheader transparent übergeben werden, anstatt vom Reverseproxy geändert zu werden.
    
- sollte eine Überbrückung des TLS-Datenverkehrs von einem extern definierten Port (z. B. TCP 443) zu einem anderen definierten Port (z. B. TCP 4443) ermöglichen. Ihr Reverseproxy entschlüsselt das Paket möglicherweise beim Empfang und verschlüsselt das Paket dann beim Senden erneut.
    
- sollte eine Überbrückung des unverschlüsselten TCP-Datenverkehrs von einem Port (z. B. TCP 80) zu einem anderen (z. B. TCP 8080) ermöglichen.
    
- muss die Konfiguration der NTLM-Authentifizierung, keine Authentifizierung und pass-through-Authentifizierung zulassen oder akzeptieren.
    
Wenn Ihr Reverseproxy alle Anforderungen in dieser Liste erfüllen kann, sollten Sie dies tun, aber beachten Sie bitte unsere Empfehlungen unter dem oben angegebenen Link.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Sie müssen Ihre Edgebereitstellung hinter einer externen Firewall stellen, es wird jedoch empfohlen, zwei Firewalls zu verwenden, eine externe und eine interne zwischen der Edgeumgebung und Ihrer internen Umgebung. Alle unsere Dokumentationen in unseren Szenarien verfügen über zwei Firewalls. Wir empfehlen zwei Firewalls, da sie ein striktes Routing von einem Netzwerkrand zum anderen sicherstellen und den Firewallschutz für Ihr internes Netzwerk verdoppeln.
  
### <a name="directors"></a>Directors
<a name="Directors"> </a>

Dies ist eine optionale Rolle. Dabei kann es sich um einen einzelnen Server oder einen Serverpool mit der Directorrolle befinden. Es ist eine Rolle, die in der internen Skype for Business Server-Umgebung gefunden wird.
  
Der Director ist ein interner Next-Hop-Server, der eingehenden SIP-Datenverkehr von den Edgeservern empfängt, die für interne Skype for Business Server-Server bestimmt sind. Eingehende Anforderungen werden vorab authentifiziert und an den Startpool oder Server eines Benutzers umgeleitet. Mit dieser Vorabauthentifizierung können Sie nicht identifizierte Benutzerkontoanforderungen löschen.
  
Warum spielt das eine Rolle? Eine wichtige Funktion für einen Director ist der Schutz von Standard Edition-Servern und Front-End-Servern oder Front-End-Pools vor schädlichem Datenverkehr, z. B. Denial-of-Service(DoS)-Angriffen. Wenn Ihr Netzwerk mit ungültigem externen Datenverkehr überflutet wird, wird der Datenverkehr am Director angehalten.
  
### <a name="load-balancers"></a>Lastenausgleichsmodule
<a name="LoadBalancers"> </a>

Die skalierte konsolidierte Edgetopologie von Skype for Business Server ist für den DNS-Lastenausgleich für neue Bereitstellungen optimiert. Dies wird empfohlen. Wenn Sie hohe Verfügbarkeit benötigen, empfehlen wir die Verwendung eines Hardwaregeräts zum Lastenausgleich für eine bestimmte Situation:
  
- Exchange UM für Remotebenutzer, die Exchange UM **vor** Exchange 2013 verwenden.
    
> [!IMPORTANT]
> Es ist wichtig zu beachten, dass Sie lastenausgleicher nicht kombinieren können. In Ihrer Skype for Business #A0 müssen alle Schnittstellen ENTWEDER DNS oder HLB verwenden. 
  
> [!NOTE]
> Die DIREKTE Serverrücklauf-NAT (Direct Server Return, DSR) wird für Skype for Business Server nicht unterstützt. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Hardwarelastenausgleichsanforderungen für Edgeserver-Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird

Für jeden Edgeserver, auf dem der A/V-Edgedienst ausgeführt wird, gelten die folgenden Anforderungen:
  
- Deaktivieren Sie das TCP-Nagling für interne und externe Ports 443 (Nagling ist der Prozess, mehrere kleine Pakete in einem einzigen, größeren Paket zu kombinieren, um eine effizientere Übertragung zu erhalten).
    
- Deaktivieren Sie das TCP-Nagling für den externen Portbereich 50000 - 59999.
    
- Verwenden Sie NAT nicht für Ihre internen oder externen Firewalls.
    
- Die interne Edgeschnittstelle muss sich in einem anderen Netzwerk als die externe Edgeserverschnittstelle befinden, und das Routing zwischen ihnen muss deaktiviert sein.
    
- Die externe Schnittstelle eines Edgeservers, auf dem der A/V-Edgedienst ausgeführt wird, muss öffentlich routingfähige IP-Adressen und keine NAT- oder Portübersetzung für eine der externen Edge-IP-Adressen verwenden.
    
#### <a name="hlb-requirements"></a>#A0

Skype for Business Server hat nicht viele cookiebasierte Affinitätsanforderungen. Daher müssen Sie keine cookiebasierte Persistenz **verwenden,** es sei denn (und dies ist Skype for Business Server 2015-spezifisch), werden Sie Lync Server 2010-Front-End-Server oder Front-End-Pools in Ihrer Skype for Business Server-Umgebung haben. Sie benötigen cookiebasierte Affinität in der für Lync Server 2010 empfohlenen Konfigurationsmethode.
  
> [!NOTE]
> Wenn Sie entscheiden, die cookiebasierte Affinität für Ihre HLB zu aktivieren, gibt es kein Problem dabei, auch wenn Ihre Umgebung sie nicht benötigt. 
  
Wenn Ihre Umgebung **keine** cookiebasierte Affinität benötigt:
  
- Legen Sie für die Reverseproxyveröffentlichungsregel für Port 443 **Den Hostheader weiterleiten auf** True **.** Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
Für Bereitstellungen, **die cookiebasierte** Affinität benötigen:
  
- Legen Sie für die Reverseproxyveröffentlichungsregel für Port 443 **Den Hostheader weiterleiten auf** True **.** Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
- Das Hardwaregerät zum Lastenausgleich **darf nicht** als httpOnly gekennzeichnet werden.
    
- Das Hardwaregerät zum Lastenausgleich **darf keine** Ablaufzeit haben.
    
- Das Cookie für  den Hardwaregerät zum Lastenausgleich muss den Namen **MS-WSMAN** haben (dies ist der von den Webdiensten erwartete Wert, der nicht geändert werden kann).
    
- Das Hardwaregerät zum  Lastenausgleich muss in jeder HTTP-Antwort festgelegt werden, für die die eingehende HTTP-Anforderung kein Cookie hatte, unabhängig davon, ob eine vorherige HTTP-Antwort für dieselbe TCP-Verbindung ein Cookie erhalten hat. Wenn Ihr Hardwaregerät zum Lastenausgleich die Cookieeinfügung so optimiert, dass sie nur einmal pro TCP-Verbindung erfolgt, darf diese **Optimierung nicht** verwendet werden.
    
> [!NOTE]
> Es ist für #A0 typisch, quellaffin und 20 Minuten #A1 zu verwenden, was für Skype for Business Server und seine Clients in Ordnung ist, da der Sitzungsstatus über die Clientverwendung und/oder Anwendungsinteraktion beibehalten wird. 
  
Wenn Sie mobile Geräte bereitstellen, muss Ihr HLB in der Lage sein, einzelne Anforderungen innerhalb einer #A0 zu lasten (tatsächlich müssen Sie in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse zu ermöglichen).
  
> [!IMPORTANT]
> F5 HLBs verfügen über ein Feature namens OneConnect. Dadurch wird sichergestellt, dass jede Anforderung innerhalb einer TCP-Verbindung einzeln lastenausgleicht wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass ihr #A0 die gleiche Funktionalität unterstützt. Die neuesten mobilen iOS-Apps erfordern TLS Version 1.2. Wenn Sie mehr wissen müssen, bietet F5 bestimmte Einstellungen dafür. 
  
Hier sind die #A0 für den (optionalen) Director und (erforderlich) Front-End-Poolwebdienste:
  
- Legen Sie für ihre internen Webdienste-VIPs Source_addr (interner Port 80, 443) auf Ihrer HLB ein. Bei Skype for Business Server bedeutet Source_addr, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse kommen, immer an einen Server gesendet werden, um den Sitzungsstatus zu erhalten.
    
- Verwenden Sie ein TCP-Leerlaufzeitlimit von 1800 Sekunden.
    
- Erstellen Sie in der Firewall zwischen Ihrem Reverseproxy und dem HLB des nächsten Hoppools eine Regel, um https zu erlauben: Datenverkehr an Port 4443, von Ihrem Reverseproxy zu Ihrer HLB. Ihre HLB muss so konfiguriert sein, dass sie die Ports 80, 443 und 4443 abhört.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Zusammenfassung der #A0

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**FQSN-Affinitätsanforderungen für interne Webdienste**|
|:-----|:-----|:-----|
|Skype for Business Web App (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business Web App (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business Web App (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Portüberwachung für HLBs

Sie definieren die Portüberwachung für Ihre Hardwaregeräte zum Lastenausgleich, um zu bestimmen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind. Wenn der Front-End-Serverdienst (RTCSRV) beispielsweise beendet wird, weil der Front-End-Server oder der Front-End-Pool ausfällt, sollte die #A0 auch den Datenverkehr auf den Webdiensten beenden. Sie sollten die Portüberwachung auf dem HLB implementieren, um Folgendes für Ihre externe #A0 zu überwachen:
  
|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Wir haben die Hardware- und Softwareanforderungen des Edgeservers in der Dokumentation zu den allgemeinen Serveranforderungen für [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und Systemanforderungen für Skype for Business Server  [2019](../../../SfBServer2019/plan/system-requirements.md) behandelt.
  
## <a name="collocation"></a>Collocation

Wir haben die Edgeserverkolokation in der [Dokumentation zu Topologiegrunddaten für Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) behandelt.
