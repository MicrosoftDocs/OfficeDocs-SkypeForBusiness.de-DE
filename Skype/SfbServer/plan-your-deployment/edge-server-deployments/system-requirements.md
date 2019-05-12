---
title: Edge-Server-System Requirements in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Zusammenfassung: Informationen Sie zu den Systemanforderungen für Edge-Server in Skype für Business Server.'
ms.openlocfilehash: b32aa16699bd81047bdd019cc11fe700c841d208
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895503"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Edge-Server-System Requirements in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Systemanforderungen für Edge-Server in Skype für Business Server.
  
Wenn es sich um Ihre Skype für Business Server Edge-Server-Bereitstellung geht, sind dies die Dinge, die Sie benötigen, um für den oder die Server, die in der Umgebung sind, sich selbst als auch für die Umgebungsstruktur planen. Für weitere Informationen zu den Punkten Topologie, DNS, Zertifikate und zu weiteren Infrastrukturfragen, prüfen Sie die Dokumentation zu den Umgebungsanforderungen.
  
## <a name="components"></a>Komponenten

Im Zusammenhang mit die Edge-Server-Umgebung verweisen wir Komponenten, die in den meisten Fällen, in einem Umkreisnetzwerk bereitgestellt werden, (das ist um zu sagen, dass es entweder in einer Arbeitsgruppe oder Domäne, die sich außerhalb Ihrer Skype für Domänenstruktur Business Server handelt).
  
Denken Sie daran, dass Sie die folgenden Komponenten benötigen, um Ihren Edgeserver erfolgreich bereitzustellen:
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (diese sind optional und werden auf Ihrem internen Netzwerk befinden, falls sie enthalten sind)
    
- [Systeme zum Lastenausgleich](system-requirements.md#LoadBalancers) (können Sie DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich (Hardwarelastenausgleich) verfügen, aber dies ist nicht für einen einzelnen Edgeserver erforderlich)
    
Zu jedem der unteren Punkte gibt es weitere Details:
  
### <a name="edge-servers"></a>Edgeservers
<a name="EdgeServers"> </a>

Dies sind die Skype für Business Server in Ihrer Umgebung Umkreisnetzwerk bereitgestellt. Ihre Rolle ist zum Senden und Empfangen von Netzwerkdatenverkehr an externe Benutzer für die Dienste, die von Ihrem internen Skype für Business Server-Bereitstellung angeboten. Hierzu erfolgreich ausgeführt wird jedem Edgeserver:
  
- **Zugriffs-edgedienst**: Stellt einen einzelnen, vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden Datenverkehr von Session Initiation Protocol (SIP) bereit.
    
- **Webkonferenz-edgedienst**: ermöglicht externen Benutzern, an Besprechungen teilzunehmen, die gehostet werden in Ihrer internen Skype für Business Server-Umgebung.
    
- **A / V-edgedienst**: Audio, Video, Anwendungsfreigabe und Datei für externe Benutzer übertragen wird.
    
- **XMPP-Proxydienst**: akzeptiert und sendet extensible messaging und Anwesenheit Protocol (XMPP) Nachrichten zu und von konfigurierten XMPP-Verbundpartner.
    
Autorisierte externe Benutzer können Ihrer Edge-Server verwenden, um die Verbindung mit Ihrer internen Skype für Business Server-Bereitstellung, aber anderenfalls bieten keinen anderen Zugriff auf das interne Netzwerk für jeden Benutzer.
  
> [!NOTE]
> Edge-Server werden bereitgestellt, um Verbindungen für aktivierten Skype für Business-Clients und anderen Edge-Server (in Verbundszenarien) bereitzustellen. Sie können keine Verbindungen von anderen Endpunktclients oder Servertypen herstellen. Der XMPP-Gatewayserver kann für die Verbindungen mit konfigurierten XMPP-Partnern eingesetzt werden. Denken Sie daran, dass dies die einzigen Client- und Verbundtypen sind, die funktionieren. 

> [!NOTE]
> XMPP-Gateways und -Proxys werden stehen in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype für Business Server 2019. Weitere Informationen finden Sie unter [Migrieren von XMPP-Verbund](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Reverseproxys
<a name="ReverseProxies"> </a>

Ein Reverseproxyserver (RP) hat keine Skype für Business Server-Role, jedoch ist ein wesentlicher Bestandteil einer Edge-Server-Bereitstellung. Ein Reverseproxy ermöglicht externen Benutzern an:
  
- Die Teilnahme an Besprechungen oder Einwahlkonferenzen über einfache URLs.
    
- Das Herunterladen von Besprechungsinhalten.
    
- Das Erweitern von Verteilergruppen.
    
- Das Erhalten von benutzerbasierten Zertifikaten für die auf Clientzertifikaten basierenden Authentifizierungen.
    
- Laden Sie Dateien aus der Adressbuchserver oder zum Senden von Abfragen an den Adressbuch-Webabfragedienst-Dienst.
    
- Das Abrufen von Updates für Client- und Gerätesoftware.
    
Und für mobile Geräte:
  
- Außerdem können sie die automatische Ermittlung von Front-End-Servern, die Mobilitätsdienste.
    
- Sie können Pushbenachrichtigungen von Office 365 für mobile Geräte.
    
Die aktuellen Reverseproxy Empfehlungen finden Sie auf der Seite [Telefonie-Infrastruktur für Skype für Unternehmen](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . So Ihren Reverseproxy aufrufen:
  
- TLS (Transport Layer Security)-Verbindungen zu verwenden, die in Ihrer Umgebung über öffentliche Zertifikate bereitgestellt werden, um eine Verbindung mit den folgenden veröffentlichten externen Webdiensten herzustellen:
    
  - Director oder Director-pool
    
  - Front-End-Server oder Front-End-pool
    
- Interne Websites mithilfe von Zertifikaten für die Verschlüsselung zu veröffentlichen oder diese bei Bedarf unverschlüsselt zu veröffentlichen.
    
- Eine intern gehostete Website extern mit einem voll qualifizierten Domänennamen (FQDN) zu veröffentlichen.
    
- Alle Inhalte Ihrer gehosteten Website zu veröffentlichen. Standardmäßig können die ** / ***-Direktive, die von den meisten Webservern erkannt wird, bedeutet "Alle Inhalte auf dem Webserver veröffentlichen". Sie können auch die Richtlinie ändern – beispielsweise ** /Uwca/\\***, was bedeutet, dass "Veröffentlichen sämtliche Inhalte unter das virtuelle Verzeichnis Ucwa."
    
- TLS-Verbindungen mit Clients voraussetzen, die Inhalte von Ihrer veröffentlichten Website anfordern.
    
- Zertifikate zu akzeptieren, die über „SAN-Einträge“ (alternative Antragstellernamen) verfügen.
    
- Die Zertifikatbindung an Listener oder Schnittstellen zu erlauben, über die der externe Webdienste-FQDN aufgelöst wird. Listenerkonfigurationen sind Schnittstellen vorzuziehen. Viele Listener können in einer einzelnen Schnittstelle konfiguriert werden.
    
- Die Konfiguration der Hostheaderbehandlung zuzulassen. Häufig muss der ursprünglichen Hostheader vom anfordernden Client gesendet transparent übergeben werden, anstelle der Reverseproxy geändert wird.
    
- Das Überbrücken des TLS-Datenverkehrs von einem extern definierten Port (z. B. TCP 443) zu einem anderen definierten Port (z. B. TCP 4443) zu erlauben. Ihren Reverseproxy aufrufen kann das Paket nach Erhalt entschlüsseln und Zeitabständen klicken Sie dann das Paket auf senden.
    
- Das Überbrücken des unverschlüsselten TCP-Datenverkehrs von einem Port (z. B. TCP 80) zu einem anderen Port (z. B. TCP 8080) zu erlauben.
    
- Konfiguration von NTLM-Authentifizierung, keiner Authentifizierung und Pass-Through-Authentifizierung zu erlauben oder zu akzeptieren.
    
Wenn Sie Ihren Reverseproxy aufrufen aller Anforderungen in dieser Liste erfüllt werden kann, sollten Sie können gut zu wechseln, aber Bitte bedenken Sie unsere Empfehlungen unter dem oben angegebenen Link.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Sie müssen Ihre Edgebereitstellung hinter einer externen Firewall platzieren. Wir raten Ihnen aber dazu, über zwei Firewalls, eine externe und eine interne, zwischen der Edge-Umgebung und Ihrer internen Umgebung zu verfügen. Die Dokumentationen in unseren Szenarien haben alle zwei Firewalls. Wir empfehlen deshalb zwei Firewalls, weil dies ein striktes Routing von einer Netzwerkedge zur anderen sicherstellt. Außerdem verdoppelt dies den Firewall-Schutz für Ihr internes Netzwerk.
  
### <a name="directors"></a>Directors
<a name="Directors"> </a>

Dies ist eine optionale Rolle. Es kann einen einzelnen Server oder einen Pool von Servern, auf denen die Director-Rolle sein. Es ist eine Rolle finden Sie auf der internen Skype für Business Server-Umgebung.
  
Der Director ist ein nächsten internen Hopservers die eingehenden SIP-Datenverkehr von Edge-Server empfängt, die für Skype für interne Server Business Server bestimmt ist. Er authentifiziert vorab eingehende Anfragen und leitet diese an den Home-Pool oder Server eines Benutzers weiter. Diese Vorabauthentifizierung erlaubt es Ihnen, Anfragen von unbekannten Nutzerkontos zu verwerfen.
  
Warum ist das von Bedeutung? Eine wichtige Funktion für einen Director ist um Standard Edition-Servern und Front-End-Servern oder Front-End-Pools bösartigem Datenverkehr wie Denial-of-Service (DoS)-Angriffen zu schützen. Wenn Ihr Netzwerk bereits mit externen Datenverkehr ungültig ist, wird der Datenverkehr des Directors beendet.
  
### <a name="load-balancers"></a>Lastenausgleichsysteme
<a name="LoadBalancers"> </a>

Die Skype ist für Business Server eine skalierte edgetopologie konsolidierte optimiert für DNS-Lastenausgleich für die neue Bereitstellung, und es wird, dies empfohlen. Wenn Sie hohen Verfügbarkeit benötigen, sollten ein Hardwaregerät zum Lastenausgleich für eine bestimmte Situation verwenden:
  
- Exchange UM für Remotebenutzer, die mit Exchange UM **früheren** Exchange 2013.
    
> [!IMPORTANT]
> Es ist wichtig, zu beachten, dass Sie Lastenausgleichssysteme nicht miteinander kombinieren können. In Ihrer Skype für Business Server-Umgebung müssen alle Schnittstellen DNS oder Hardwarelastenausgleich verwenden. 
  
> [!NOTE]
> Direct Server zurück, dass (DSR)-NAT für Skype für Business Server nicht unterstützt wird. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Anforderungen für Hardware bei zum Lastenausgleich für Edge-Servern Edge-Server mit dem A / V-edgedienst

Für Edge Server mit dem A / V-Edgeserver Dies sind die Anforderungen:
  
- Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443 (der Nagle-Algorithmus fasst mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammen).
    
- Deaktivieren Sie den Nagle-Algorithmus für TCP für den Bereich der externen Ports 50000 bis 59999.
    
- Verwenden Sie keine Netzwerkadressenübersetzung (NAT) für Ihre interne oder externe Firewall.
    
- Interne edgeschnittstelle muss sich in einem anderen Netzwerk als die externe Schnittstelle des Edge-Server und routing zwischen diesen Schnittstellen muss deaktiviert sein.
    
- Die externe Schnittstelle von alle Edge-Server, die des A / V-edgedienst verwenden, öffentlich routingfähige IP-Adressen und darf keine NETZWERKADRESSEN- oder portübersetzung Edge externe IP-Adressen muss.
    
#### <a name="hlb-requirements"></a>HLB-Anforderungen

Skype für Business Server verfügt nicht über viele cookiebasierte Affinität Anforderungen. So Sie keine cookiebasierte Persistenz **, sofern nicht** verwenden müssen (und dies Skype für Business Server 2015-spezifischen ist) benötigen Sie Lync Server 2010 Front-End-Servern oder Front-End-Pools in Ihrer Skype für Business Server-Umgebung haben. Sie müssten die cookiebasierte Affinität in der Konfigurationsmethode für Lync Server 2010 empfohlen.
  
> [!NOTE]
> Wenn Sie sich dafür entscheiden, die cookiebasierte Affinität für Ihre Hardware zum Lastenausgleich (HLB) zu aktivieren, können Sie dies problemlos tun, selbst wenn es für Ihre Umgebung nicht notwendig ist. 
  
Wenn Ihre Umgebung **keine** cookiebasierte Affinität benötigt:
  
- Klicken Sie auf der Reverseproxy-Veröffentlichungsregel für Port 443 **Forward Hostheader** auf **True**festgelegt. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
Für Bereitstellungen, in denen die cookiebasierte Affinität **verwendet** wird:
  
- Klicken Sie auf der Reverseproxy-Veröffentlichungsregel für Port 443 **Forward Hostheader** auf **True**festgelegt. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
- Die Hardware Load zum Lastenausgleich Cookie **darf nicht** markiert werden HttpOnly.
    
- Die Hardware Load zum Lastenausgleich Cookie **darf nicht** haben Ablaufzeit.
    
- Die Hardware Load zum Lastenausgleich Cookie **muss** den Namen **MS-wsman haben** (Dies ist der Wert, den die Webdienste erwarten und kann nicht geändert werden).
    
- Der Hardware Load Balancer Cookie **muss** festgelegt werden in jeder HTTP-Antwort für die eingehende HTTP-Anforderung hatten ein Cookie, unabhängig davon, ob eine vorherige HTTP-Antwort in der gleichen TCP-Verbindung ein Cookie gelangt hatte. Wenn Ihr Hardwaregerät zum Lastenausgleich, Cookie einfügen optimiert, um auftreten nur einmal pro TCP-Verbindung, Optimierung **muss nicht** verwendet werden.
    
> [!NOTE]
> Es ist normalerweise für Hardwaregeräts zum Lastenausgleich Konfigurationen Quelle Affinität und 20 Minuten TCP Sitzungsdauer, die Ordnung für Skype für Business Server und den zugehörigen Clients ist, da Sitzungsstatus über Clientverwendung und/oder Interaktion der Anwendung verwaltet wird. 
  
Wenn Sie mobile Geräte bereitstellen, muss Ihr Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).
  
> [!IMPORTANT]
> F5-Hardwaregeräte zum Lastenausgleich sind mit einer Funktion namens „OneConnect“ ausgestattet. Sie stellt sicher, dass für jede Anforderung in einer TCP-Verbindung ein individueller Lastenausgleich vorgenommen wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass der Hersteller des Hardwaregeräts für den Lastenausgleich dieselbe Funktion unterstützt. Für die neuesten mobilen Apps von Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich. F5 stellt hierfür bestimmte Einstellungen bereit. 
  
Hier sind die Anforderungen Hardwaregeräts zum Lastenausgleich für den Director (optional) und (erforderlich) Front-End-Pool-Webdienste:
  
- Festlegen von für Ihre internen Web Services-Ends Source_addr Persistenz (interner Port 80, 443) für Ihre Hardwaregeräts zum Lastenausgleich. Für Skype für Business Server also Source_addr Persistenz immer auf einem Server mehrere Verbindungen, die von einer einzelnen IP-Adresse gesendet werden, den Sitzungszustand beibehalten.
    
- Verwenden Sie ein TCP-Leerlauftimeout von 1.800 Sekunden.
    
- In der Firewall zwischen Ihren Reverseproxy aufrufen und den nächsten hoppool Hardwaregeräts zum Lastenausgleich, erstellen Sie eine Regel zum Zulassen von Https: Verkehr auf Port 4443, aus Ihren Reverseproxy aufrufen, um Ihre Hardwaregeräts zum Lastenausgleich. Das HLB muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Zusammenfassung der HLB-Affinitätsanforderungen

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**Affinitätsanforderungen an den internen Webdienste-FQSN**|
|:-----|:-----|:-----|
|Skype für Business Web App (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype für Business Web App (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Skype für Business Web App (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Portüberwachung für Hardwaregeräte zum Lastenausgleich

Sie definieren Port-Überwachung Ihrer Hardwaregeräte zum Lastenausgleich, um zu bestimmen, wann bestimmte Dienste nicht mehr verfügbar ist, aufgrund von Hardware-oder Communications sind. Angenommen, wenn der Front-End-Server-Dienst (RTCSRV) beendet wurde, da der Front-End-Server oder Front-End-Pool fällt aus, sollte die Überwachung des Hardwaregeräts zum Lastenausgleich ebenfalls beendet-Datenverkehr an die Webdienste empfangen. Sie sollten die HLB-Portüberwachung implementieren, um Folgendes für die externe Schnittstelle Ihres HLBs zu überwachen:
  
|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<Pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Wir haben in unserer allgemeinen [Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [Systemanforderungen für Skype für Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) Dokumentation Edge-Server-Hardware und Software-Anforderungen behandelt.
  
## <a name="collocation"></a>Kollokation

Wir haben Kollokation Edge-Server in der [Topologiegrundlagen der Skype für Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) -Dokumentation behandelt.
  

