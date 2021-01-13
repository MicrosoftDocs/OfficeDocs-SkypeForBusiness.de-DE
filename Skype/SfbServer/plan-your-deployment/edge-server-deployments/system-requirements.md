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
ms.openlocfilehash: e066249498febbd5e622546533f49422320c7c87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813765"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Edgeserversystemanforderungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Systemanforderungen für Edgeserver in Skype for Business Server.
  
Wenn es um Ihre Skype for Business Server-Edgeserver-Bereitstellung geht, müssen Sie dies für die Server oder Server, die sich in der Umgebung selbst befinden, sowie für die Planung der Umgebungsstruktur tun. Weitere Informationen zu Topologie, DNS, Zertifikaten und anderen Infrastrukturaspekten finden Sie in der Dokumentation zu den Umgebungsanforderungen.
  
## <a name="components"></a>Komponenten

Bei der Erörterung der Edgeserverumgebung verweisen wir auf Komponenten, die zum größten Teil in einem Umkreisnetzwerk bereitgestellt werden (d. h. entweder in einer Arbeitsgruppe oder in einer Domäne außerhalb Ihrer Skype for Business Server-Domänenstruktur).
  
Beachten Sie, dass Dies die Komponenten sind, die Sie bei der erfolgreichen Bereitstellung Ihres Edge berücksichtigen müssen:
  
- [Edgeserver](system-requirements.md#EdgeServers)
    
- [Reverse-Proxys](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (diese sind optional, und wenn sie enthalten sind, befinden sie sich in Ihrem internen Netzwerk)
    
- [Lastenausgleichsgeräte](system-requirements.md#LoadBalancers) (Sie können einen #A0 oder ein Hardwaregerät zum Lastenausgleich (Hardware Load Balancer, HLB) verwenden, aber für einen einzelnen Edgeserver ist dies nicht erforderlich.
    
Im Folgenden finden Sie weitere Details zu den einzelnen Beispielen:
  
### <a name="edge-servers"></a>Edgeserver
<a name="EdgeServers"> </a>

Dies sind die Skype for Business-Server, die in Ihrer Umkreisumgebung bereitgestellt werden. Ihre Rolle besteht im Senden und Empfangen von Netzwerkdatenverkehr an externe Benutzer für die Dienste, die von Ihrer internen Skype for Business Server-Bereitstellung angeboten werden. Um dies erfolgreich zu tun, wird jeder Edgeserver ausgeführt:
  
- **Zugriffs-Edgedienst:** Stellt einen einzelnen, vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden Sip-Datenverkehr (Session Initiation Protocol) zur Verfügung.
    
- **Webkonferenz-Edgedienst:** Ermöglicht externen Benutzern die Teilnahme an Besprechungen, die in Ihrer internen Skype for Business Server-Umgebung gehostet werden.
    
- **A/V-Edgedienst:** Stellt Audio, Video, Anwendungsfreigabe und Dateiübertragung für externe Benutzer zur Verfügung.
    
- **XMPP-Proxydienst:** Akzeptiert und sendet XMPP (Extensible Messaging and Presence Protocol)-Nachrichten an und von konfigurierten XMPP-Verbundpartnern.
    
Autorisierte externe Benutzer können Ihre Edgeserver verwenden, um eine Verbindung mit Ihrer internen Skype for Business Server-Bereitstellung herzustellen, aber andernfalls bieten sie keinem anderen Zugriff auf Ihr internes Netzwerk.
  
> [!NOTE]
> Edgeserver werden bereitgestellt, um Verbindungen für aktivierte Skype for Business-Clients und andere Edgeserver (in Verbundszenarien) zu ermöglichen. Sie können keine Verbindung von anderen Client- oder Servertypen für Den Endpunkt herstellen. Der XMPP-Gatewayserver kann Verbindungen mit konfigurierten XMPP-Partnern zulassen. Aber auch dies sind die einzigen Client- und Verbundtypen, die funktionieren. 

> [!NOTE]
> XMPP-Gateways und -Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter ["Migrieren des XMPP-Verbunds".](../../../SfBServer2019/migration/migrating-xmpp-federation.md)
  
### <a name="reverse-proxies"></a>Reverse-Proxys
<a name="ReverseProxies"> </a>

Ein Reverseproxyserver hat keine Skype for Business Server-Rolle, ist aber eine wesentliche Komponente einer Edgeserverbereitstellung. Ein Reverseproxy ermöglicht externen Benutzern:
  
- Herstellen einer Verbindung mit Besprechungen oder Einwahlkonferenzen mithilfe einfacher URLs.
    
- Laden Sie Besprechungsinhalte herunter.
    
- Verteilergruppen erweitern.
    
- Benutzerbasierte Zertifikate für die clientzertifikatbasierte Authentifizierung erhalten
    
- Laden Sie Dateien vom Adressbuchserver herunter, oder senden Sie Abfragen an den Adressbuch-Webabfragedienst.
    
- Abrufen von Updates für Client- und Gerätesoftware.
    
Und für mobile Geräte:
  
- Sie können damit automatisch Front-End-Server ermitteln, die Mobilitätsdienste anbieten.
    
- Es ermöglicht Pushbenachrichtigungen von Microsoft 365 oder Office 365 an mobile Geräte.
    
Unsere aktuellen Reverseproxyempfehlungen finden Sie auf der Seite ["Telefonieinfrastruktur für Skype for Business".](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) Ihr Reverseproxy:
  
- transport layer security (TLS) verwenden können, die in Ihrer Umgebung über öffentliche Zertifikate eingeführt wird, um eine Verbindung mit den veröffentlichten externen Webdiensten von:
    
  - Director oder Director-Pool
    
  - Front-End-Server oder Front-End-Pool
    
- muss in der Lage sein, interne Websites mithilfe von Zertifikaten für die Verschlüsselung oder bei Bedarf unverschlüsselt zu veröffentlichen.
    
- sollte in der Lage sein, eine intern gehostete Website extern mithilfe eines vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) zu veröffentlichen.
    
- muss in der Lage sein, alle Inhalte Ihrer gehosteten Website zu veröffentlichen. Standardmäßig können Sie die _-Direktive verwenden, die von den meisten Webservern als "Alle Inhalte auf dem **/\\** Webserver veröffentlichen" erkannt wird. Sie können auch die Direktive ändern, z. B. _*/Uwca/, \\* *_ was "Alle Inhalte unter dem virtuellen Verzeichnis Ucwa veröffentlichen" bedeutet.
    
- muss TLS-Verbindungen mit Clients benötigen, die Inhalte von Ihrer veröffentlichten Website anfordern.
    
- muss Zertifikate mit Einträgen für alternative Subject Name (SAN) akzeptieren.
    
- muss die Bindung eines Zertifikats an einen Listener oder eine Schnittstelle zulassen können, über die der FQDN der externen Webdienste aufgelöst wird. Listenerkonfigurationen sind Schnittstellen vorzuziehen. Viele Listener können auf einer einzigen Schnittstelle konfiguriert werden.
    
- muss die Konfiguration der Hostheaderverarbeitung zulassen. Häufig muss der ursprüngliche Hostheader, der vom anfordernden Client gesendet wird, transparent übergeben werden, anstatt vom Reverseproxy geändert zu werden.
    
- Überbrückung von TLS-Datenverkehr von einem extern definierten Port (z. B. TCP 443) zu einem anderen definierten Port (z. B. TCP 4443) zulassen. Ihr Reverseproxy kann das Paket beim Empfang entschlüsseln und das Paket dann beim Senden erneut verschlüsseln.
    
- sollte das Überbrücken des unverschlüsselten DATENVERKEHRs von einem Port (z. B. TCP 80) zu einem anderen (z. B. TCP 8080) zulassen.
    
- muss die Konfiguration der NTLM-Authentifizierung, keine Authentifizierung und pass-Through-Authentifizierung zulassen oder akzeptieren.
    
Wenn Ihr Reverseproxy alle Anforderungen in dieser Liste erfüllen kann, sollten Sie dies tun. Beachten Sie jedoch unsere Empfehlungen unter dem oben angegebenen Link.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Sie müssen Ihre Edgebereitstellung hinter einer externen Firewall stellen, es wird jedoch empfohlen, dass zwischen der Edgeumgebung und Ihrer internen Umgebung zwei Firewalls, eine externe und eine interne Firewall, verwendet werden. Alle unsere Dokumentationen in unseren Szenarien verfügen über zwei Firewalls. Wir empfehlen zwei Firewalls, da dadurch ein striktes Routing von einem Netzwerkrand zum anderen sichergestellt wird und der Firewallschutz für Ihr internes Netzwerk verdoppelt wird.
  
### <a name="directors"></a>Directors
<a name="Directors"> </a>

Dies ist eine optionale Rolle. Es kann sich um einen einzelnen Server oder einen Serverpool mit der Directorrolle befinden. Es ist eine Rolle in der internen Skype for Business Server-Umgebung.
  
Der Director ist ein interner Next-Hop-Server, der eingehenden SIP-Datenverkehr von den Edgeservern empfängt, der für interne Skype for Business Server-Server bestimmt ist. Eingehende Anforderungen werden vorab authentifiziert und an den Homepool oder Server eines Benutzers umgeleitet. Mit dieser Vorauthentifizierung können Sie nicht identifizierte Benutzerkontoanforderungen ablegen.
  
Warum ist das wichtig? Eine wichtige Funktion für einen Director ist der Schutz von Standard Edition-Servern und Front-End-Servern oder Front-End-Pools vor bösartigem Datenverkehr, z. B. Denial-of-Service(DoS)-Angriffen. Wenn Ihr Netzwerk mit ungültigem externen Datenverkehr überflutet wird, wird der Datenverkehr am Director angehalten.
  
### <a name="load-balancers"></a>Lastenausgleichsmodule
<a name="LoadBalancers"> </a>

Die skalierte konsolidierte Edgetopologie von Skype for Business Server ist für den DNS-Lastenausgleich für neue Bereitstellungen optimiert. Dies wird empfohlen. Wenn Sie hohe Verfügbarkeit benötigen, empfehlen wir die Verwendung eines Hardwaregeräts zum Lastenausgleich für eine bestimmte Situation:
  
- Exchange UM für Remotebenutzer, die Exchange UM *_* vor * vor Exchange 2013 verwenden.
    
> [!IMPORTANT]
> Es ist wichtig zu beachten, dass Sie keine Lastenausgleichssetter kombinieren können. In Ihrer Skype for Business #A0 müssen alle Schnittstellen ENTWEDER DNS oder HLB verwenden. 
  
> [!NOTE]
> Die NAT für direkte Serverrücklauf (Direct Server Return, DSR) wird für Skype for Business Server nicht unterstützt. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Anforderungen an das Hardwaregerät zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird

Für jeden Edgeserver, auf dem der A/V-Edgedienst ausgeführt wird, gelten die folgenden Anforderungen:
  
- Deaktivieren Sie den TCP-Nagling sowohl für interne als auch für externe Ports 443 (beim Nagling werden mehrere kleine Pakete zu einem einzigen, größeren Paket für eine effizientere Übertragung kombiniert).
    
- Deaktivieren Sie den TCP-Nagling für den externen Portbereich 50000 bis 59999.
    
- Verwenden Sie NAT nicht für Ihre internen oder externen Firewalls.
    
- Die interne Edgeschnittstelle muss sich in einem anderen Netzwerk als die externe Edgeserverschnittstelle befinden, und das Routing zwischen diesen Schnittstellen muss deaktiviert sein.
    
- Die externe Schnittstelle eines Edgeservers, auf dem der A/V-Edgedienst ausgeführt wird, muss öffentlich routingfähige IP-Adressen und keine NAT- oder Portübersetzung für externe Edge-IP-Adressen verwenden.
    
#### <a name="hlb-requirements"></a>HlB-Anforderungen

Skype for Business Server hat nicht viele cookiebasierte Affinitätsanforderungen. Sie müssen also keine cookiebasierte Persistenz **verwenden,** es sei denn (und dies ist Skype for Business Server 2015-spezifisch), sie werden Lync Server 2010-Front-End-Server oder Front-End-Pools in Ihrer Skype for Business Server-Umgebung verwenden. Sie benötigen cookiebasierte Affinität in der für Lync Server 2010 empfohlenen Konfigurationsmethode.
  
> [!NOTE]
> Wenn Sie die cookiebasierte Affinität für Ihren HLB aktivieren, gibt es kein Problem, auch wenn dies in Ihrer Umgebung nicht benötigt wird. 
  
Wenn Ihre Umgebung **keine** cookiebasierte Affinität benötigt:
  
- Legen Sie für die Reverseproxyveröffentlichungsregel für Port 443 den **Weiterleitungshostheader auf** **"True" festgelegt.** Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
Für Bereitstellungen, **die cookiebasierte** Affinität benötigen:
  
- Legen Sie für die Reverseproxyveröffentlichungsregel für Port 443 den **Weiterleitungshostheader auf** **"True" festgelegt.** Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
- Das Cookie für das **Hardwaregerät** zum Lastenausgleich darf nicht als "httpOnly" gekennzeichnet werden.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich **darf keine** Ablaufzeit haben.
    
- Das Cookie für  das Hardwaregerät zum Lastenausgleich muss den Namen **"MS-WSMAN"** haben (dies ist der von den Webdiensten zu erwartende Wert, der nicht geändert werden kann).
    
- Das Cookie für  das Hardwaregerät zum Lastenausgleich muss in jeder HTTP-Antwort festgelegt werden, für die die eingehende HTTP-Anforderung kein Cookie hatte, unabhängig davon, ob eine vorherige HTTP-Antwort für dieselbe TCP-Verbindung ein Cookie erhalten hat. Wenn das Hardwaregerät zum Lastenausgleich das Einfügen von Cookies so optimiert, dass es nur einmal pro TCP-Verbindung erfolgt, darf diese **Optimierung nicht** verwendet werden.
    
> [!NOTE]
> In #A0 werden für #A1 die Quellaffinität und die 20-minütige #A2 verwendet. Dies ist für Skype for Business Server und seine Clients in Ordnung, da der Sitzungsstatus durch Clientnutzung und/oder Anwendungsinteraktion beibehalten wird. 
  
Wenn Sie mobile Geräte bereitstellen, muss Ihr HlB in der Lage sein, einen Lastenausgleich für einzelne Anforderungen innerhalb einer #A0 zu ermöglichen (tatsächlich müssen Sie in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse zu ermöglichen).
  
> [!IMPORTANT]
> #A0 verfügen über ein Feature namens OneConnect. Dadurch wird sichergestellt, dass jede Anforderung innerhalb einer TCP-Verbindung einen individuellen Lastenausgleich hat. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass Der Hersteller des Hardwaregeräteherstellers die gleiche Funktionalität unterstützt. Die neuesten mobilen iOS-Apps erfordern TLS Version 1.2. Wenn Sie mehr wissen müssen, stellt F5 hierin bestimmte Einstellungen zur Verf nkung. 
  
Hier sind die #A0 für den (optionalen) Director und (erforderliche) Front-End-Poolwebdienste:
  
- Legen Sie für ihre internen #A0 Source_addr Persistenz (interner Port 80, 443) auf dem HLB. Bei Skype for Business Server bedeutet Source_addr Persistenz, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse kommen, immer an einen Server gesendet werden, um den Sitzungsstatus auf dem Server zu erhalten.
    
- Verwenden Sie ein TCP-Leerlauftimeout von 1800 Sekunden.
    
- Erstellen Sie in der Firewall zwischen Ihrem Reverseproxy und dem HLB des nächsten Hoppools eine Regel, um https: Datenverkehr an Port 4443 vom Reverseproxy zum HLB zu erlauben. Ihr HLB muss für die Abhörung der Ports 80, 443 und 4443 konfiguriert sein.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Zusammenfassung der #A0

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**FQSN-Affinitätsanforderungen für interne Webdienste**|
|:-----|:-----|:-----|
|Skype for Business Web App (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business Web App (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype for Business Web App (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Portüberwachung für HLBs

Sie definieren die Portüberwachung für Ihre Hardwaregeräte zum Lastenausgleich, um zu bestimmen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind. Wenn beispielsweise der Front-End-Serverdienst (RTCSRV) beendet wird, weil der Front-End-Server oder front-End-Pool ausfällt, sollte die #A0 auch den Empfang von Datenverkehr über die Webdienste beenden. Sie sollten die Portüberwachung auf dem HLB implementieren, um Folgendes für Ihre externe #A0 zu überwachen:
  
|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Wir haben die Hardware- und Softwareanforderungen des Edgeservers in unseren allgemeinen Serveranforderungen für [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und systemanforderungen für Skype for Business Server  [2019](../../../SfBServer2019/plan/system-requirements.md) behandelt.
  
## <a name="collocation"></a>Kollokation

Wir haben die Kollokation von Edgeservern in der Dokumentation zu [den Topologiegrunddaten für Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) behandelt.
  

