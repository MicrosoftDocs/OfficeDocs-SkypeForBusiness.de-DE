---
title: Anforderungen an den Lastenausgleich für Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Zusammenfassung: Überprüfen Sie den Lastenausgleich Überlegungen vor der Implementierung von Skype für Business Server.'
ms.openlocfilehash: c1b9069d13111955e3957dc0bd199ac0a163fd1a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976478"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Anforderungen an den Lastenausgleich für Skype for Business
 
**Zusammenfassung:** Überprüfen Sie den Lastenausgleich Überlegungen vor der Implementierung von Skype für Business Server.
  
Der Lastenausgleich verteilt Datenverkehr zwischen den Servern in einem Pool. Wenn Sie Front-End-Pools, edgeserverpools oder vermittlungsserverpools haben, müssen Sie für den Lastenausgleich für diese Pools bereitstellen.
  
Skype für Business Server unterstützt zwei Arten von Lösungen für Client-zu-Server-Datenverkehr für den Lastenausgleich: Domain Name System (DNS)-Lastenausgleich und Hardwaregeräte zum Lastenausgleich oft (als Hardwaregeräts zum Lastenausgleich Abkürzung). DNS-Lastenausgleich Lastenausgleich bietet mehrere Vorteile, einschließlich einfachere Verwaltung, effizienter Problembehandlung und die Möglichkeit zum Großteil Ihrer Skype für Business Server Datenverkehr von potenzielle Hardware Load Balancer Probleme zu isolieren.
  
Für sich selbst die lastenausgleichslösung für jeden Pool in Ihrer Bereitstellung eignet sich entscheiden Sie, aber Bedenken Sie die folgenden Einschränkungen: 
  
- Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.
    
- Für einige Arten von Datenverkehr ist ein Hardwaregerät zum Lastenausgleich erforderlich. HTTP-Datenverkehr erfordert beispielsweise ein Hardwaregerät zum Lastenausgleich anstatt eines DNS-Lastenausgleichs. Der DNS-Lastenausgleich funktioniert nicht beim Client-zu-Server-Datenverkehr.
    
Wenn Sie für einen Pool den DNS-Lastenausgleich verwenden möchten, aber dennoch Hardwaregeräte zum Lastenausgleich benötigen, beispielsweise für den HTTP-Datenverkehr, ist die Verwaltung der Hardwaregeräte zum Lastenausgleich jetzt erheblich einfacher. Ein Beispiel hierfür ist, dass ausschließlich der HTTP- und HTTPS-Datenverkehr verwaltet wird, während alle anderen Protokolle vom DNS-Lastenausgleich verwaltet werden. Weitere Informationen hierzu finden Sie unter [DNS-Lastenausgleich](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Für Server-zu-Server-Datenverkehr Skype für Business Server Topologie berücksichtigen zum Lastenausgleich verwendet wird. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher erhalten Sie die FQDNs der Server in der Topologie, und automatisch den Datenverkehr zwischen den Servern zu verteilen. Administratoren müssen diese Art des Lastenausgleichs weder konfigurieren noch verwalten. 
  
Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen. 
  
## <a name="hardware-load-balancer-requirements"></a>Anforderungen an das Hardwaregerät zum Lastenausgleich

Die Skype für eine skalierte Business Server für einen konsolidierten Edgeserver Topologie optimiert ist für DNS-Lastenausgleich für neue Bereitstellungen in erster Linie mit anderen Organisationen mit Skype für Business Server oder Lync Server zusammenfassen. Wenn hoher Verfügbarkeit für eines der folgenden Szenarien erforderlich ist, muss ein Hardwaregerät zum Lastenausgleich auf Edge-Server-Pools für Folgendes verwendet werden: 
  
- Partnerverbund mit Organisationen, die mit Office Communications Server 2007 R2 oder Office Communications Server 2007
    
- Exchange UM für Remotebenutzer, die mit Exchange UM vor Exchange 2010 SP1
    
- Verbindung mit Benutzern öffentlicher Chatdienste
    
> [!IMPORTANT]
> Das Verfahren, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden, wird nicht unterstützt. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden. 
  
> [!NOTE]
> Wenn Sie ein Hardwaregerät zum Lastenausgleich einsetzen, muss der Lastenausgleich für Verbindungen mit dem internen Netzwerk so konfiguriert werden, dass nur für den Datenverkehr zu Servern, auf denen der Zugriffs-Edgedienst und der A/V-Edgedienst ausgeführt werden, ein Lastenausgleich stattfindet. Es kann kein Lastenausgleich für den Datenverkehr zum internen Webkonferenz-Edgedienst oder zum internen XMPP-Proxydienst durchgeführt werden. 
  
> [!NOTE]
> Direct Server Return (DSR) NAT wird mit Skype für Business Server nicht unterstützt. 
  
Um zu bestimmen, ob Ihr Hardwaregerät zum Lastenausgleich die benötigten Features von Skype für Business Server unterstützt, finden Sie unter [Infrastruktur für Skype für Unternehmen](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird

Folgen die Hardware Load-Anforderungen zum Lastenausgleich für Edge-Servern, die mit der A / V-edgedienst:
  
- Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443. Mit diesem Algorithmus werden mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammengefasst.
    
- Deaktivieren Sie Nagling für externe Portbereich 50.000 – 59.999 TCP aus. 
    
- Verwenden Sie keine Netzwerkadressenübersetzung für die interne oder externe Firewall. 
    
- Die interne edgeschnittstelle muss sich in einem anderen Netzwerk als die externe Schnittstelle des Edgeservers und routing zwischen diesen Schnittstellen muss deaktiviert sein. 
    
- Die externe Schnittstelle des Edgeservers mit den A / V-Edgedienst verwenden, öffentlich routingfähige IP-Adressen und darf keine NETZWERKADRESSEN- oder portübersetzung Edge externe IP-Adressen müssen. 
    
- Die Quelladresse des Clients darf durch den Lastenausgleich nicht geändert werden.
    
### <a name="other-hardware-load-balancer-requirements"></a>Sonstige Anforderungen Hardwaregerät zum Lastenausgleich

Cookie-basierte Affinität Anforderungen sind erheblich für Webdienste in Skype für Business Server reduziert. Wenn Sie Skype für Business Server bereitstellen und den Lync Server 2010 Front-End-Servern oder Front-End-Pools werden nicht beibehalten, benötigen Sie keine cookiebasierte Persistenz. Jedoch, wenn Sie temporär oder dauerhaft von Lync Server 2010 Front-End-Servern oder Front-End-Pools beizubehalten, verwenden Sie weiterhin cookiebasierte Persistenz wie es ist bereitgestellt und für Lync Server 2010 konfiguriert. 
  
> [!NOTE]
> **Wenn Sie sich entscheiden, die cookiebasierte Persistenz zu verwenden, obwohl dies für Ihre**-Bereitstellung nicht erforderlich ist, hat dies keine negative Auswirkung. 
  
Für Bereitstellungen, in denen die cookiebasierte Affinität **nicht verwendet** wird:
  
- Legen Sie für die Veröffentlichungsregel des Reverseproxys für Port 4443 **Forward host header** auf „True“ fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
Für Bereitstellungen, in denen die cookiebasierte Affinität **verwendet** wird:
  
- Legen Sie für die Veröffentlichungsregel des Reverseproxys für Port 4443 **Forward host header** auf „True“ fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich DARF NICHT als „httpOnly“ gekennzeichnet sein.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich DARF KEINE Ablaufzeit haben.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS den Namen **MS-WSMAN** haben (dies ist der von den Webdiensten erwartete Wert, der nicht geändert werden kann).
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS in jeder HTTP-Antwort festgelegt sein, für die die eingehende HTTP-Anforderung kein Cookie enthielt, unabhängig davon, ob für eine vorherige HTTP-Antwort für dieselbe TCP-Verbindung bereits ein Cookie abgerufen wurde. Wenn der Lastenausgleich das Einfügen von Cookies so optimiert, dass sie nur einmal pro TCP-Verbindung erfolgt, darf diese Optimierung NICHT verwendet werden.
    
> [!NOTE]
> Typische Load Balancer Hardwarekonfigurationen Quelladresse Affinität und eine 20 min. TCP verwenden Sitzungsdauer, die Ordnung für Lync Server und Lync 2013-Clients ist, da durch Clientverwendung des Sitzungsstatus beibehalten wird und/oder und Interaktion der Anwendung. 
  
Wenn Sie mobile Geräte bereitstellen, muss das Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).
  
> [!CAUTION]
> F5-Hardwaregeräte zum Lastenausgleich sind mit einer Funktion namens OneConnect ausgestattet, mit der sichergestellt wird, dass für jede Anforderung in einer TCP-Verbindung ein individueller Lastenausgleich vorgenommen wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass der Hersteller des Hardwaregeräts für den Lastenausgleich dieselbe Funktion unterstützt. Für die neuesten mobilen Apps für Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich. F5 stellt hierfür bestimmte Einstellungen bereit. 
  
> [!CAUTION]
> Ausführliche Informationen zum Drittanbieter Hardwaregeräte zum Lastenausgleich finden Sie unter [Infrastruktur für Skype für Unternehmen](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
Im Folgenden sind die Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Director- und Front-End-Pool-Webdienste aufgeführt:
  
- Legen Sie für interne virtuelle IP-Adressen der Webdienste die Dauerhaftigkeit von Quelladressen (interner Port 80, 443) für das Hardwaregerät zum Lastenausgleich fest. Für Skype für Business Server also Source_addr Persistenz immer auf einem Server mehrere Verbindungen, die von einer einzelnen IP-Adresse gesendet werden, den Sitzungszustand beibehalten.
    
- Legen Sie ein TCP-Leerlauftimeout von 1.800 Sekunden fest.
    
- In der Firewall zwischen dem Reverseproxy und den nächsten hoppool Hardwaregerät zum Lastenausgleich, erstellen Sie eine Regel zum Zulassen von Https: Datenverkehr an Port 4443, aus dem Reverseproxy an die Hardware des Systems zum Lastenausgleich. Das Hardwaregerät zum Lastenausgleich muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Zusammenfassung der Affinitätsanforderungen an das Hardwaregerät zum Lastenausgleich

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**Affinitätsanforderungen an den internen Webdienste-FQDN**|
|:-----|:-----|:-----|
|Lync Web App (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Lync Web App (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Lync Web App (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Portüberwachung für Hardwaregeräte zum Lastenausgleich

Sie definieren die Portüberwachung für Hardwaregeräte zum Lastenausgleich (Hardware Load Balancers, HLB), um festzustellen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind. Angenommen, wenn der Front-End-Server-Dienst (RTCSRV) beendet wurde, da der Front-End-Server oder Front-End-Pool fällt aus, sollte die Überwachung des Hardwaregeräts zum Lastenausgleich ebenfalls beendet-Datenverkehr an die Webdienste empfangen. Sie können die HLB-Portüberwachung implementieren, um Folgendes zu überwachen:
  
**Front-End-Server-Benutzerpool – interne HLB-Schnittstelle**

|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool\>Web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-End  <br/> 5061  <br/> |Quelle  <br/> |HTTPS  <br/> |
|\<Pool\>Web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-End  <br/> 5061  <br/> |Quelle  <br/> |HTTP  <br/> |
   
**Front-End-Server-Benutzerpool – externe HLB-Schnittstelle**

|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<Pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="BKMK_DNSLoadBalancing"> </a>

Skype für Business Server ermöglicht DNS-Lastenausgleich, eine Software-Lösung, die die Verwaltung Wartungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich beeinträchtigen können. DNS-Lastenausgleich gleicht den Netzwerkdatenverkehr, der für Skype für Business Server, wie etwa SIP-Datenverkehr und der Mediendatenverkehr eindeutig ist.
  
Wenn Sie die DNS-Lastenausgleich bereitstellen, wird Ihre Organisation Administration Wartungsaufwand für Hardwaregeräte zum Lastenausgleich minimiert. Darüber hinaus entfällt die komplexe Problembehandlung zur Beseitigung von Fehlern, die durch eine falsche Konfiguration des Lastenausgleichs für SIP-Datenverkehr entstehen. Zudem können Sie Serververbindungen verhindern, sodass Sie Server offline schalten können. Der DNS-Lastenausgleich stellt ferner sicher, dass durch Hardwarelastenausgleich hervorgerufene Probleme sich nicht auf den SIP-Datenverkehr, etwa auf die grundlegende Anrufweiterleitung, auswirken.

Das folgende Diagramm zeigt ein Beispiel, das sowohl interne und externe DNS-Lastenausgleich: 
  
**Diagramm eines Edgenetzwerks, in dem öffentliche IPv4-Adressen verwendet werden**

![Beispiel eines DNS-Netzwerkdiagramms](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Wenn Sie DNS-Lastenausgleich verwenden, können Sie möglicherweise auch kostengünstigere Hardwaregeräte zum Lastenausgleich anschaffen, da diese nicht für alle Arten von Datenverkehr eingesetzt werden müssen. Sie sollten den Systemen zum Lastenausgleich verwenden, die Interoperabilität Qualifikation Testen mit Skype für Business Server übergeben haben. Ausführliche Informationen zur Interoperabilität das Testen des Lastenausgleichs finden Sie unter [Lync Server 2010 Load Balancer Partners](https://go.microsoft.com/fwlink/p/?linkId=202452). Der Inhalt es gilt für Skype für Business Server.
  
Der DNS-Lastenausgleich wird für Front-End-Pools, Edgeserverpools, Directorpools und eigenständige Vermittlungsserverpools unterstützt.
  
DNS-Lastenausgleich wird in der Regel auf der Anwendungsebene implementiert. Die Anwendung (beispielsweise in einem Client unter Skype für Unternehmen), versucht, Verbindung mit einem Server in einem Pool eine Verbindung zu einer IP-Adressen zurückgegeben, die von den DNS-A und AAAA (Wenn IPv6-Adressen verwendet wird) Abfrage für den vollqualifizierten Domänennamen (FQDN) von Pools aufzeichnen. 
  
Wenn z. B. drei Front-End-Server im Pool „pool01.contoso.com“ vorhanden sind, werden folgende Schritte ausgeführt:
  
- Clients, auf denen Skype für Unternehmen DNS-Abfrage für "pool01.contoso.com". Die Anfrage gibt drei IP-Adressen zurück und speichert diese wie folgt im Zwischenspeicher (nicht unbedingt in dieser Reihenfolge):
    
    "pool01.contoso.com" 192.168.10.90
    
    "pool01.contoso.com" 192.168.10.91
    
    "pool01.contoso.com" 192.168.10.92
    
- Der Client versucht, eine TCP-Verbindung (Transmission Control Protocol) mit einer der IP-Adressen herzustellen. Wenn dies nicht gelingt, versucht der Client, eine Verbindung mit der nächsten IP-Adresse im Zwischenspeicher herzustellen.
    
- Bei erfolgreicher TCP-Verbindung handelt der Client die Verwendung von TLS zur Verbindungsherstellung mit der primären Registrierung in „pool01.contoso.com“ aus.
    
- Wenn der Client alle zwischengespeicherten Einträge eine erfolgreiche Verbindung versucht, wird der Benutzer benachrichtigt, dass gegenwärtig keine Server mit Skype für Business Server verfügbar sind.
    
> [!NOTE]
> Der DNS-basierte Lastenausgleich unterscheidet sich von DNS-Roundrobin (DNS RR). Dieser letztgenannte Mechanismus bezieht sich normalerweise auf einen Lastenausgleich, bei dem DNS zur Bereitstellung einer anderen Reihenfolge von IP-Adressen für die Server in einem Pool eingesetzt wird. Mit DNS RR ist typischerweise nur ein Lastenausgleich, jedoch kein Failover möglich. Wenn die Verbindung mit der IP-Adresse, die über die DNS-A- und DNS-AAAA-Abfrage (wenn Sie IPv6-Adressen nutzen) zurückgegeben wurde, nicht hergestellt werden kann, tritt für die Verbindungsherstellung ein Fehler auf. Daher ist DNS-Roundrobin allein weniger zuverlässig als der DNS-basierte Lastenausgleich. Sie können DNS-Roundrobin gemeinsam mit dem DNS-Lastenausgleich verwenden. 
  
DNS-Lastenausgleich wird für folgende Szenarien eingesetzt:
  
- Lastenausgleich zwischen SIP- und Edgeservern
    
- Lastenausgleich für Anwendungen der Unified Communications-Anwendungsdienste, z. B. automatische Konferenzzentrale, Reaktionsgruppen und die Anwendung zum Parken von Anrufen
    
- Verhindern neuer Verbindungen mit Anwendungen der Unified Communications-Anwendungsdienste (auch als „Serverausgleich“ bezeichnet)
    
- Lastenausgleich für den gesamten Datenverkehr zwischen Clients und Edgeservern
    
DNS-Lastenausgleich kann für folgende Szenarien nicht eingesetzt werden:
  
- Webdatenverkehr zu Director- oder Front-End-Servern
    
DNS-Lastenausgleich und Datenverkehr im Partnerverbund:
  
Wenn eine DNS-SRV-Abfrage mehrere DNS-Einträge zurückgibt, wählt der Zugriffs-Edgedienst immer den DNS-SRV-Eintrag aus, dessen Priorität durch die kleinste Zahl und dessen Gewichtung durch die größte Zahl gekennzeichnet ist. Internet Engineering Task Force "Einen DNS-Ressourceneintrag für die Angabe des Speicherorts der Dienste (DNS SRV)" Dokument [RFC 2782, DNS-SRV-Ressourceneintrag](https://www.ietf.org/rfc/rfc2782.txt) gibt an, dass mehrere DNS-SRV Datensätze definiert sind, Priorität zuerst verwendet wird, klicken Sie dann weight. Angenommen, DNS-SRV-Eintrag A hat eine Gewichtung von 20 und eine Priorität von 40 und DNS-SRV-Eintrag B hat eine Gewichtung von 10 und eine Priorität von 50. DNS-SRV-Eintrag A mit Priorität 40 wird ausgewählt. Für die Auswahl von DNS-SRV-Einträgen gelten folgende Regeln:
  
- Die Priorität wird zuerst berücksichtigt. Ein Client MUSS versuchen, den Zielhost zu kontaktieren, der vom DNS-SRV-Eintrag mit der niedrigsten Prioritätszahl definiert ist, die erreicht werden kann. Ziele mit derselben Priorität SOLLTEN in einer durch das Gewichtungsfeld definierten Reihenfolge zu kontaktieren versucht werden.
    
- Das Gewichtungsfeld gibt eine relative Gewichtung für Einträge mit derselben Priorität an. Größere Gewichtungen SOLLTEN mit proportional höherer Wahrscheinlichkeit gewählt werden. DNS-Administratoren sollten Gewichtung den Wert 0 verwenden, wenn keine Aktionen-Serverauswahl vorhanden ist. Wenn Server mit größeren Gewichtungen als 0 vorhanden sind, werden Einträge mit der Gewichtung 0 höchstwahrscheinlich nicht ausgewählt.
    
Wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden, wählt der Zugriffs-Edgedienst den SRV-Eintrag aus, der zuerst vom DNS-Server empfangen wurde.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>DNS-Lastenausgleich in Front-End-Pools und Directorpools

Sie können den DNS-Lastenausgleich für den SIP-Datenverkehr in Front-End-Pools und Directorpools verwenden. Auch wenn Sie einen DNS-Lastenausgleich konfiguriert haben, müssen Sie trotzdem auch Hardwaregeräte zum Lastenausgleich für diese Pools verwenden, jedoch nur für den HTTPS-Datenverkehr von Client zu Server. Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über die Ports 443 und 80 verwendet. 
  
Auch wenn für diese Pools weiterhin Hardwaregeräte zum Lastenausgleich benötigt werden, müssen diese vornehmlich für den HTTPS-Datenverkehr eingerichtet und verwaltet werden. Dies stellt für Administratoren von Hardwaregeräten zum Lastenausgleich jedoch eine gängige Aufgabe dar.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS-Lastenausgleich und Unterstützung älterer Clients und Server

DNS-Lastenausgleich Lastenausgleich unterstützt Automatisches Failover nur für Server unter Skype für Business Server oder Lync Server 2010 sowie für Lync 2013 und Skype für Business-Clients. Frühere Versionen von Clients und Office Communications Server können weiterhin eine Verbindung mit Pools der DNS-Lastenausgleich ausgeführt, wenn sie einer Verbindung mit dem ersten Server nicht ausgeführt werden können, dass DNS-Lastenausgleich zu verweist, werden aber kann nicht zum Failover auf einen anderen Server im pool . 
  
Wenn Sie Exchange UM verwenden, müssen Sie darüber hinaus ein Minimum von Exchange 2010 SP1 verwenden, um Unterstützung für Skype für Business Server DNS-Lastenausgleich zu erhalten. Bei Verwendung früherer Exchange-Versionen verfügen Sie nicht über Failoverfunktionen für diese Exchange UM-Szenarien:
  
- Wiedergeben ihrer Enterprise-Voicemail auf ihrem Telefon
    
- Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale
    
Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Directorpools
<a name="BK_FE_Dir"> </a>

Für die Bereitstellung von DNS-Lastenausgleich in Front-End-Pools und Directorpools müssen einige zusätzliche Schritte im Zusammenhang mit FQDNs und DNS-Einträgen ausgeführt werden.
  
- Ein Pool, der DNS-Lastenausgleich verwendet, benötigen zwei FQDNs: der reguläre Pool-FQDN, die von DNS verwendet wird Lastenausgleichs (beispielsweise "pool01.contoso.com") und ergibt die physischen IP-Adressen der Server im Pool zu laden und eine andere FQDN für den Pool-Web services (z. b. web01.contoso.com), die virtuelle IP-Adresse des Pools aufgelöst wird. 
    
    Im Topologie-Generator Wenn Sie DNS-Lastenausgleich für einen Pool bereitstellen möchten müssen, um diese zusätzlichen FQDN für den Pool-Webdienste zu erstellen Sie aktivieren Sie das Kontrollkästchen **interne Webdienste außer Kraft setzen pool-FQDN** und geben Sie den FQDN, in der **Angeben der Webdienst-URLs für In diesem Pool** Seite.
    
- Um den vom DNS-Lastenausgleich verwendeten FQDN zu unterstützen, müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. pool01.contoso.com) in die IP-Adressen aller Server im Pool bereitstellen (z. B. 192.168.1.1, 192.168.1.2 usw.). Berücksichtigen Sie nur die IP-Adressen von Servern, die gegenwärtig bereitgestellt sind.
    
    > [!CAUTION]
    > Wenn Sie mehrere Front-End-Pool oder Front-End-Server verfügen muss die externen Webdienste FQDN eindeutig sein. Wenn Sie die externen Webdienste-FQDN des Front-End-Server als **"pool01.contoso.com"** definieren, können nicht Sie beispielsweise **"pool01.contoso.com"** für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Director-Server bereitstellen, die externe Webdienste-FQDN für alle Director definierten oder Director-Pool muss aus einem anderen eindeutig sein Director oder Director-Pools sowie alle Front-End-Pool oder Front-End-Server Wenn Sie die internen Webdienste mit einem selbstdefinierten FQDN überschreiben, jeder FQDN muss von einem beliebigen anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>DNS-Lastenausgleich in Edgeserverpools
<a name="BK_Edge"> </a>

Sie können DNS-Lastenausgleich in Edgeserverpools bereitstellen. In diesem Fall müssen einige Faktoren berücksichtigt werden.
  
Bei Verwendung des DNS-Lastenausgleichs auf Ihren Edgeservern verfügen Sie in den folgenden Szenarien nicht mehr über eine Failoverfunktion:
  
- Partnerverbund mit Organisationen, die Versionen von Skype für Business Server veröffentlicht werden, bevor Sie Lync Server 2010 ausgeführt werden.
    
- Austauschen von Sofortnachrichten mit Benutzern eines öffentlichen instant messaging (IM) Services AOL und Yahoo!, zusätzlich zu XMPP-basierten Anbieter und Server, wie Google Talk derzeit die einzige unterstützte XMPP-Partner.
    
Diese Szenarien werden unterstützt, solange alle Edgeserver im Pool verfügbar sind und ausgeführt werden. Wenn jedoch einer der Edgeserver ausfällt, werden Anforderungen für diese Szenarien nicht an einen anderen Edgeserver weitergeleitet, sondern können nicht verarbeitet werden.
  
 Wenn Sie Exchange UM verwenden, müssen Sie mindestens Exchange 2013 zum Abrufen von Unterstützung für Skype für Business Server DNS-Lastenausgleich in Edge verwenden. Bei Verwendung früherer Exchange-Versionen verfügen Ihre Remotebenutzer nicht über Failoverfunktionen für diese Exchange UM-Szenarien:
  
- Wiedergeben ihrer Enterprise-Voicemail auf ihrem Telefon
    
- Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale
    
Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.
  
Für die interne und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Bereitstellen von DNS-Lastenausgleich in Edgeserverpools

Zur Bereitstellung des DNS-Lastenausgleichs für die externe Schnittstelle Ihres Edgeserverpools benötigen Sie die folgenden DNS-Einträge:
  
- Für den Zugriffs-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Zugriffs-Edgediensts (z. B. „sip.contoso.com“) in die IP-Adresse des Zugriffs-Edgediensts auf einem der Edgeserver im Pool auflösen.
    
- Für den Webkonferenz-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Webkonferenz-Edgediensts (z. B. „webconf.contoso.com“) in die IP-Adresse des Webkonferenz-Edgediensts auf einem der Edgeserver im Pool auflösen.
    
- Für den A/V-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des a/v-edgediensts (beispielsweise av.contoso.com) beheben, zur IP-Adresse des A / V-edgedienst auf einem Edge-Server im Pool.
    
Zur Bereitstellung des DNS-Lastenausgleichs für die interne Schnittstelle Ihres Edgeserverpools müssen Sie einen DNS-A-Eintrag hinzufügen, der den internen FQDN des Edgeserverpools in die IP-Adressen der einzelnen Server innerhalb des Pools auflöst.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools
<a name="BK_Mediation"> </a>

Sie können den DNS-Lastenausgleich in eigenständigen Vermittlungsserverpools verwenden. Der gesamte SIP- und Mediendatenverkehr wird durch den DNS-Lastenausgleich verteilt.
  
Zur Bereitstellung des DNS-Lastenausgleichs in einem Vermittlungsserverpool müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. mediationpool1.contoso.com) in die IP-Adressen aller Server im Pool (z. B. 192.168.1.1, 192.168.1.2 usw.) bereitstellen.
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blockieren von Datenverkehr an einen Server mit dem DNS-Lastenausgleich
<a name="BK_Mediation"> </a>

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen. 
  
Beachten Sie, dass für Server-zu-Server-Datenverkehr Topologie berücksichtigen Lastenausgleich Skype für Business Server verwendet wird. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher erhalten Sie die FQDNs der Server in der Topologie, und automatisch den Datenverkehr zwischen den Servern zu verteilen. Um den Datenverkehr zwischen Servern für einen bestimmten Server zu blockieren, müssen Sie diesen Server aus der Topologie entfernen. 
  

