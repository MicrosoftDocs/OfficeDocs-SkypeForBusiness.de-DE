---
title: Lastenausgleichsanforderungen für Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Zusammenfassung: Überprüfen Sie die Überlegungen zum Lastenausgleich, bevor Sie Skype for Business Server implementieren.'
ms.openlocfilehash: 5790ef1ba0d32774ced45be5af257f70fc4cf594
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834375"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Lastenausgleichsanforderungen für Skype for Business
 
**Zusammenfassung:** Überprüfen Sie die Überlegungen zum Lastenausgleich, bevor Sie Skype for Business Server implementieren.
  
Der Lastenausgleich verteilt den Datenverkehr auf die Server in einem Pool. Wenn Sie über Front-End-Pools, Vermittlungsserverpools oder Edgeserverpools verfügen, müssen Sie den Lastenausgleich für diese Pools bereitstellen.
  
Skype for Business Server unterstützt zwei Arten von Lastenausgleichslösungen für Client-zu-Server-Datenverkehr: #A0 (Domain Name System) und Hardwarelastenausgleich (häufig als HLB abgekürzt). Der DNS-Lastenausgleich bietet mehrere Vorteile, darunter eine einfachere Verwaltung, eine effizientere Problembehandlung und die Möglichkeit, einen großen Teil des Skype for Business Server-Datenverkehrs von potenziellen Problemen mit dem Hardwaregerät zum Lastenausgleich zu isolieren.
  
Entscheiden Sie selbst, welche Lastenausgleichslösung für jeden Pool in Ihrer Bereitstellung geeignet ist, beachten Sie jedoch die folgenden Einschränkungen: 
  
- Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.
    
- Für einige Arten von Datenverkehr ist ein Hardwaregerät zum Lastenausgleich erforderlich. HTTP-Datenverkehr erfordert beispielsweise ein Hardwaregerät zum Lastenausgleich anstatt eines DNS-Lastenausgleichs. Der DNS-Lastenausgleich funktioniert nicht beim Client-zu-Server-Datenverkehr.
    
Wenn Sie für einen Pool den DNS-Lastenausgleich verwenden möchten, aber dennoch Hardwaregeräte zum Lastenausgleich benötigen, beispielsweise für den HTTP-Datenverkehr, ist die Verwaltung der Hardwaregeräte zum Lastenausgleich jetzt erheblich einfacher. Beispielsweise ist das Konfigurieren des Hardwaregeräts zum Lastenausgleich einfacher, da nur der HTTP- und der HTTPS-Datenverkehr verwaltet werden, während alle anderen Protokolle durch den DNS-Lastenausgleich verwaltet werden. Ausführliche Informationen finden Sie unter [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Für Den Server-zu-Server-Datenverkehr verwendet Skype for Business Server einen Topologie-igen Lastenausgleich. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie zu erhalten, und verteilen den Datenverkehr automatisch auf die Server. Administratoren müssen diese Art des Lastenausgleichs weder einrichten noch verwalten. 
  
Wenn Sie den DNS-Lastenausgleich verwenden und Datenverkehr zu einem bestimmten Computer blockieren müssen, reicht es nicht aus, nur die Einträge der IP-Adresse aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen. 
  
## <a name="hardware-load-balancer-requirements"></a>Anforderungen an das Hardwaregerät zum Lastenausgleich

Die skalierte konsolidierte Edgetopologie von Skype for Business Server ist für den DNS-Lastenausgleich für neue Bereitstellungen optimiert, die hauptsächlich mit anderen Organisationen zusammenarbeiten, die Skype for Business Server oder Lync Server verwenden. Wenn hohe Verfügbarkeit für eines der folgenden Szenarien erforderlich ist, muss ein Hardwaregerät zum Lastenausgleich in Edgeserverpools für Folgendes verwendet werden: 
  
- Verbund mit Organisationen, die Office Communications Server 2007 R2 oder Office Communications Server 2007 verwenden
    
- Exchange UM für Remotebenutzer, die Exchange UM vor Exchange 2010 mit SP1 verwenden
    
- Verbindung mit Benutzern öffentlicher Chatdienste
    
> [!IMPORTANT]
> Es wird nicht unterstützt, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden. 
  
> [!NOTE]
> Wenn Sie ein Hardwaregerät zum Lastenausgleich einsetzen, muss der Lastenausgleich für Verbindungen mit dem internen Netzwerk so konfiguriert werden, dass nur für den Datenverkehr zu Servern, auf denen der Zugriffs-Edgedienst und der A/V-Edgedienst ausgeführt werden, ein Lastenausgleich stattfindet. Es kann kein Lastenausgleich für den Datenverkehr zum internen Webkonferenz-Edgedienst oder zum internen XMPP-Proxydienst durchgeführt werden. 
  
> [!NOTE]
> Die Nata für den direkten Serverrücklauf (Direct Server Return, DSR) wird mit Skype for Business Server nicht unterstützt. 
  
Informationen dazu, ob Ihr Hardwaregerät zum Lastenausgleich die für Skype for Business Server erforderlichen Funktionen unterstützt, finden Sie unter ["Infrastruktur für Skype for Business".](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird

Nachfolgend finden Sie die Anforderungen für das Hardwaregerät zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird:
  
- Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443. Mit diesem Algorithmus werden mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammengefasst.
    
- Deaktivieren Sie den TCP-Nagling für den externen Portbereich von 50.000 bis 59.999. 
    
- Verwenden Sie keine Netzwerkadressenübersetzung für die interne oder externe Firewall. 
    
- Die interne Edgeschnittstelle muss sich in einem anderen Netzwerk als die externe Edgeserverschnittstelle befinden, und das Routing zwischen diesen Schnittstellen muss deaktiviert werden. 
    
- Die externe Schnittstelle des Edgeservers, auf dem der A/V-Edgedienst ausgeführt wird, muss öffentlich routingfähige IP-Adressen und keine NAT- oder Portübersetzung für externe Edge-IP-Adressen verwenden. 
    
- Der Lastenausgleich darf die Quelladresse des Clients nicht ändern.
    
### <a name="other-hardware-load-balancer-requirements"></a>Andere Anforderungen an das Hardwaregerät zum Lastenausgleich

Cookiebasierte Affinitätsanforderungen werden in Skype for Business Server für Webdienste erheblich reduziert. Wenn Sie Skype for Business Server bereitstellen und keine Lync Server 2010-Front-End-Server oder Front-End-Pools beibehalten, benötigen Sie keine cookiebasierte Persistenz. Wenn Sie jedoch vorübergehend oder dauerhaft Lync Server 2010-Front-End-Server oder Front-End-Pools beibehalten, verwenden Sie bei der Bereitstellung und Konfiguration für Lync Server 2010 weiterhin cookiebasierte Persistenz. 
  
> [!NOTE]
> **Wenn Sie sich entscheiden, die cookiebasierte Persistenz zu verwenden, obwohl dies für Ihre**-Bereitstellung nicht erforderlich ist, hat dies keine negative Auswirkung. 
  
Für Bereitstellungen, in denen die cookiebasierte Affinität **nicht verwendet** wird:
  
- Legen Sie für die Reverseproxyveröffentlichungsregel für Port 4443 den **Weiterleitungshostheader auf** "True" festgelegt. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
Für Bereitstellungen, in denen die cookiebasierte Affinität **verwendet** wird:
  
- Legen Sie für die Reverseproxyveröffentlichungsregel für Port 4443 den **Weiterleitungshostheader auf** "True" festgelegt. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich DARF NICHT als "httpOnly" gekennzeichnet sein.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich DARF KEINE Ablaufzeit haben.
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS den Namen **MS-WSMAN** haben (dies ist der von den Webdiensten erwartete Wert, der nicht geändert werden kann).
    
- Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS in jeder HTTP-Antwort festgelegt sein, für die die eingehende HTTP-Anforderung kein Cookie enthielt, unabhängig davon, ob für eine vorherige HTTP-Antwort für dieselbe TCP-Verbindung bereits ein Cookie abgerufen wurde. Wenn der Lastenausgleich das Einfügen von Cookies so optimiert, dass sie nur einmal pro TCP-Verbindung erfolgt, darf diese Optimierung NICHT verwendet werden.
    
> [!NOTE]
> In typischen Konfigurationen für das Hardwaregerät zum Lastenausgleich werden die Quelladressenaffinität und eine 20 Min. TCP-Sitzungsdauer verwendet, was für Lync Server- und Lync 2013-Clients in Ordnung ist, da der Sitzungsstatus durch Clientverwendung und/oder Anwendungsinteraktion beibehalten wird. 
  
Wenn Sie mobile Geräte bereitstellen, muss das Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).
  
> [!CAUTION]
> Wenn Sie mobile Geräte bereitstellen, muss ihr Hardwaregerät zum Lastenausgleich in der Lage sein, jeden Lastenausgleich für jede Anforderung innerhalb einer TCP-Verbindung einzeln zu lasten. Für die neuesten mobilen Apps für Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich.  
  
> [!CAUTION]
> Weitere Informationen zu Hardwaregerät zum Lastenausgleich von Drittanbietern finden Sie unter ["Infrastruktur für Skype for Business".](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)  
  
Im Folgenden sind die Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Director- und Front-End-Pool-Webdienste aufgeführt:
  
- Legen Sie für interne virtuelle IP-Adressen der Webdienste die Dauerhaftigkeit von Quelladressen (interner Port 80, 443) für das Hardwaregerät zum Lastenausgleich fest. Bei Skype for Business Server bedeutet Source_addr Dauerhaftigkeit, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse kommen, immer an einen Server gesendet werden, um den Sitzungsstatus auf dem Server zu erhalten.
    
- Legen Sie ein TCP-Leerlauftimeout von 1.800 Sekunden fest.
    
- Erstellen Sie in der Firewall zwischen dem Reverseproxy und dem Hardwaregerät zum Lastenausgleich des nächsten Hoppools eine Regel zum Zulassen von https:-Datenverkehr an Port 4443 vom Reverseproxy zum Hardwaregerät zum Lastenausgleich. Das Hardwaregerät zum Lastenausgleich muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Zusammenfassung der Affinitätsanforderungen an das Hardwaregerät zum Lastenausgleich

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**Affinitätsanforderungen an den internen Webdienste-FQDN**|
|:-----|:-----|:-----|
|Lync Web App (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Lync Web App (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Lync Web App (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Portüberwachung für Hardwaregeräte zum Lastenausgleich

Sie definieren die Portüberwachung für Hardwaregeräte zum Lastenausgleich (Hardware Load Balancers, HLB), um festzustellen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind. Wenn beispielsweise der Front-End-Serverdienst (RTCSRV) beendet wird, weil der Front-End-Server oder front-End-Pool ausfällt, sollte die HlB-Überwachung auch den Empfang von Datenverkehr für die Webdienste beenden. Sie können die HLB-Portüberwachung implementieren, um Folgendes zu überwachen:
  
**Front-End-Serverbenutzerpool – interne #A0**

|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>Web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-End-  <br/> 5061  <br/> |Source  <br/> |HTTPS  <br/> |
|\<pool\>Web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-End-  <br/> 5061  <br/> |Source  <br/> |HTTP  <br/> |
   
**Front-End-Serverbenutzerpool – externe #A0**

|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End-  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="BKMK_DNSLoadBalancing"> </a>

Skype for Business Server ermöglicht den DNS-Lastenausgleich, eine Softwarelösung, die den Verwaltungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich reduzieren kann. Der DNS-Lastenausgleich ausgeglichen den Netzwerkdatenverkehr, der für Skype for Business Server einzigartig ist, z. B. SIP-Datenverkehr und Mediendatenverkehr.
  
Wenn Sie den DNS-Lastenausgleich bereitstellen, wird der Verwaltungsaufwand für Hardwaregeräte zum Lastenausgleich in Ihrer Organisation minimiert. Darüber hinaus entfällt die komplexe Problembehandlung zur Beseitigung von Fehlern, die durch eine falsche Konfiguration des Lastenausgleichs für SIP-Datenverkehr entstehen. Zudem können Sie Serververbindungen verhindern, sodass Sie Server offline schalten können. Der DNS-Lastenausgleich stellt ferner sicher, dass sich durch Hardwarelastenausgleich hervorgerufene Probleme nicht auf den SIP-Datenverkehr auswirken, etwa auf die grundlegende Anrufweiterleitung.

Das folgende Diagramm zeigt ein Beispiel, das sowohl den internen als auch den externen DNS-Lastenausgleich umfasst: 
  
**Edgenetzwerkdiagramm mit öffentlichen IPv4-Adressen**

![Beispiel für ein DNS-Netzwerkdiagramm](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Wenn Sie DNS-Lastenausgleich verwenden, können Sie möglicherweise auch kostengünstigere Hardwaregeräte zum Lastenausgleich anschaffen, da diese nicht für alle Arten von Datenverkehr eingesetzt werden müssen. Sie sollten Lastenausgleichssetter verwenden, die die Tests der Interoperabilitätsqualifizierung mit Skype for Business Server bestanden haben. Weitere Informationen zum Testen der Interoperabilität des Lastenausgleichs finden Sie unter [Lync Server 2010 Load Balancer Partners](https://go.microsoft.com/fwlink/p/?linkId=202452). Der Inhalt bezieht sich auf Skype for Business Server.
  
Der DNS-Lastenausgleich wird für Front-End-Pools, Edgeserverpools, Director-Pools und eigenständige Vermittlungsserverpools unterstützt.
  
Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert. Die Anwendung (z. B. ein Client, auf dem Skype for Business ausgeführt wird) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem sie eine Verbindung mit einer der von der DNS-A- und AAAA -Eintragsabfrage (wenn die IPv6-Adressierung verwendet wird) zurückgegebenen IP-Adressen für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools herstellen. 
  
Wenn z. B. drei Front-End-Server im Pool "pool01.contoso.com" vorhanden sind, werden folgende Schritte ausgeführt:
  
- Clients, die Skype for Business ausführen, fragen DNS für pool01.contoso.com. Die Abfrage gibt drei IP-Adressen zurück und speichert sie wie folgt zwischen (nicht unbedingt in dieser Reihenfolge):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Der Client versucht, eine TCP (Transmission Control Protocol)-Verbindung mit einer der IP-Adressen herzustellen. Ist dies nicht möglich, versucht der Client, eine Verbindung mit der nächsten IP-Adresse im Zwischenspeicher herzustellen.
    
- Wenn die TCP-Verbindung erfolgreich ist, handelt der Client TLS aus, um eine Verbindung mit der primären Registrierungsstelle auf dem pool01.contoso.com.
    
- Wenn der Client versucht, alle zwischengespeicherten Einträge ohne erfolgreiche Verbindung zu verwenden, wird der Benutzer benachrichtigt, dass derzeit keine Server mit Skype for Business Server verfügbar sind.
    
> [!NOTE]
> Der DNS-basierte Lastenausgleich ist anders als DNS RoundRobin (DNS RR), der sich in der Regel auf den Lastenausgleich bezieht, indem dns verwendet wird, um eine andere Reihenfolge der IP-Adressen, die den Servern in einem Pool entspricht, zur Verfügung zu stellen. In der Regel aktiviert DNS RR nur die Lastverteilung, aber kein Failover. Wenn beispielsweise die Verbindung mit einer von der DNS-A- und AAAA-Abfrage zurückgegebenen IP-Adresse (wenn Sie die IPv6-Adressierung verwenden) fehlschlägt, schlägt die Verbindung fehl. Daher ist der DNS-Roundrobin allein weniger zuverlässig als der DNS-basierte Lastenausgleich. Sie können den DNS-Roundrobin in Verbindung mit dem DNS-Lastenausgleich verwenden. 
  
DNS-Lastenausgleich wird für folgende Szenarien eingesetzt:
  
- Lastenausgleich zwischen Server-zu-Server-SIP mit den Edgeservern
    
- Lastenausgleich für Anwendungen der Unified Communications-Anwendungsdienste, z. B. automatische Konferenzzentrale, Reaktionsgruppen und die Anwendung zum Parken von Anrufen
    
- Verhindern neuer Verbindungen mit Anwendungen der Unified Communications-Anwendungsdienste (auch als "Serverausgleich" bezeichnet)
    
- Lastenausgleich für den gesamten Datenverkehr zwischen Clients und Edgeservern
    
DNS-Lastenausgleich kann für folgende Szenarien nicht eingesetzt werden:
  
- Client-zu-Server-Webdatenverkehr zu Director- oder Front-End-Servern
    
DNS-Lastenausgleich und Datenverkehr im Partnerverbund:
  
Wenn mehrere DNS-Einträge von einer DNS-SRV-Abfrage zurückgegeben werden, wählt der Zugriffs-Edgedienst immer den DNS-SRV-Eintrag mit der niedrigsten numerischen Priorität und der höchsten numerischen Gewichtung aus. Das Internet Engineering Task Force-Dokument "A DNS RR for specifying the location of services (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) gibt an, dass priorität zuerst verwendet wird, wenn mehrere DNS-SRV-Einträge definiert sind, und dann die Gewichtung. Dns-SRV-Eintrag A hat beispielsweise eine Gewichtung von 20 und eine Priorität von 40, und DNS-SRV-Eintrag B hat eine Gewichtung von 10 und Priorität 50. DNS-SRV-Eintrag A mit Priorität 40 wird ausgewählt. Die folgenden Regeln gelten für die Auswahl von DNS-SRV-Einträgen:
  
- Priorität wird zuerst betrachtet. Ein Client MUSS versuchen, den durch den DNS-SRV-Eintrag definierten Zielhost mit der niedrigsten nummerierten Priorität zu kontaktieren, die er erreichen kann. Ziele mit derselben Priorität sollten in einer durch das Gewichtungsfeld definierten Reihenfolge ausprobiert werden.
    
- Das Gewichtungsfeld gibt eine relative Gewichtung für Einträge mit derselben Priorität an. Größere Gewichtungen sollten mit einer proportional höheren Wahrscheinlichkeit für die Auswahl angegeben werden. DNS-Administratoren sollten Gewichtung 0 verwenden, wenn keine Serverauswahl erforderlich ist. Wenn Datensätze mit Gewichtungen größer als 0 sind, sollte die Wahrscheinlichkeit, dass Datensätze mit der Gewichtung 0 ausgewählt werden, sehr gering sein.
    
Wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden, wählt der Zugriffs-Edgedienst den SRV-Eintrag aus, der zuerst vom DNS-Server empfangen wurde.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>DNS-Lastenausgleich in Front-End-Pools und Director-Pools

Sie können den DNS-Lastenausgleich für den SIP-Datenverkehr in Front-End-Pools und Director-Pools verwenden. Auch wenn Sie einen DNS-Lastenausgleich konfiguriert haben, müssen Sie dennoch auch Hardwaregeräte zum Lastenausgleich für diese Pools verwenden, jedoch nur für den HTTPS-Datenverkehr von Client zu Server. Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über die Ports 443 und 80 verwendet. 
  
Auch wenn für diese Pools weiterhin Hardwaregeräte zum Lastenausgleich benötigt werden, müssen diese vornehmlich für den HTTPS-Datenverkehr eingerichtet und verwaltet werden. Dies stellt für Administratoren von Hardwaregeräten zum Lastenausgleich jedoch eine gängige Aufgabe dar.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS-Lastenausgleich und Unterstützung älterer Clients und Server

Der DNS-Lastenausgleich unterstützt automatisches Failover nur für Server mit Skype for Business Server oder Lync Server 2010 sowie für Lync 2013- und Skype for Business-Clients. Frühere Versionen von Clients und Office Communications Server können weiterhin verbindungen zu Pools herstellen, die den DNS-Lastenausgleich ausführen. Wenn sie jedoch keine Verbindung mit dem ersten Server herstellen können, auf den sie durch den DNS-Lastenausgleich verweist, können sie kein Failover auf einen anderen Server im Pool ausführen. 
  
Darüber hinaus müssen Sie bei Verwendung von Exchange UM mindestens Exchange 2010 SP1 verwenden, um Unterstützung für den Skype for Business Server-DNS-Lastenausgleich zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, verfügen Ihre Benutzer nicht über Failoverfunktionen für diese Exchange UM-Szenarien:
  
- Wiedergeben der Enterprise-Voicemail auf dem Telefon
    
- Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale
    
Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools
<a name="BK_FE_Dir"> </a>

Für die Bereitstellung von DNS-Lastenausgleich in Front-End-Pools und Director-Pools müssen einige zusätzliche Schritte im Zusammenhang mit FQDNs und DNS-Einträgen ausgeführt werden.
  
- Ein Pool, der den DNS-Lastenausgleich verwendet, muss zwei FQDNs haben: den regulären Pool-FQDN, der vom DNS-Lastenausgleich verwendet wird (z. B. pool01.contoso.com), und wird in die physischen IPs der Server im Pool aufgelöst, und ein weiterer FQDN für die Webdienste des Pools (z. B. web01.contoso.com), der in die virtuellen IP-Adressen des Pools aufgelöst wird. 
    
    Wenn Sie im Topologie-Generator den DNS-Lastenausgleich für einen Pool bereitstellen möchten, müssen Sie zum Erstellen dieses zusätzlichen FQDN für die Webdienste des Pools das Kontrollkästchen **FQDN** des internen Webdienstepools außer Kraft setzen und den FQDN auf der Seite "Webdienste-URLs für diesen Pool angeben" eingeben. 
    
- Um den vom DNS-Lastenausgleich verwendeten FQDN zu unterstützen, müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. pool01.contoso.com) in die IP-Adressen aller Server im Pool bereitstellen (z. B. 192.168.1.1, 192.168.1.2 usw.). Schließen Sie nur die IP-Adressen von Servern ein, die gegenwärtig bereitgestellt sind.
    
    > [!CAUTION]
    > Wenn Sie über mehrere Front-End-Pools oder Front-End-Server verfügen, muss der externe Webdienste-FQDN eindeutig sein. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Servers als **pool01.contoso.com** definieren, können Sie pool01.contoso.com nicht für einen anderen Front-End-Pool oder **Front-End-Server** verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN der externen Webdienste, der für einen Director oder Directorpool definiert ist, von allen anderen Director- oder Directorpools sowie front-End-Pools oder Front-End-Servern eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder Directorpool eindeutig sein.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>DNS-Lastenausgleich in Edgeserverpools
<a name="BK_Edge"> </a>

Sie können den DNS-Lastenausgleich in Edgeserverpools bereitstellen. In diesem Fall müssen einige Faktoren berücksichtigt werden.
  
Bei Verwendung des DNS-Lastenausgleichs auf Ihren Edgeservern verfügen Sie in den folgenden Szenarien nicht länger über eine Failoverfunktion:
  
- Verbund mit Organisationen, in denen Versionen von Skype for Business Server ausgeführt werden, die vor Lync Server 2010 veröffentlicht wurden.
    
- Chatnachrichtenaustausch mit Benutzern der öffentlichen Chatdienste AOL und Yahoo!, zusätzlich zu XMPP-basierten Anbietern und Servern wie Google Talk, derzeit der einzige unterstützte XMPP-Partner.
    
Diese Szenarien werden unterstützt, solange alle Edgeserver im Pool verfügbar sind und ausgeführt werden. Wenn jedoch einer der Edgeserver ausfällt, werden Anforderungen für diese Szenarien nicht an einen anderen Edgeserver weitergeleitet, sondern können nicht verarbeitet werden.
  
 Wenn Sie Exchange UM verwenden, müssen Sie mindestens Exchange 2013 verwenden, um Unterstützung für den Skype for Business Server-DNS-Lastenausgleich auf Edge zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, verfügen Die Remotebenutzer nicht über Failoverfunktionen für diese Exchange UM-Szenarien:
  
- Wiedergeben der Enterprise-Voicemail auf dem Telefon
    
- Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale
    
Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.
  
Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Bereitstellen von DNS-Lastenausgleich in Edgeserverpools

Zur Bereitstellung des DNS-Lastenausgleichs für die externe Schnittstelle Ihres Edgeserverpools benötigen Sie die folgenden DNS-Einträge:
  
- Für den Zugriffs-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Zugriffs-Edgediensts (z. B. sip.contoso.com) in die IP-Adresse des Zugriffs-Edgediensts auf einem der Edgeserver im Pool auflösen.
    
- Für den Webkonferenz-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Webkonferenz-Edgediensts (z. B. webconf.contoso.com) in die IP-Adresse des Webkonferenz-Edgediensts auf einem der Edgeserver im Pool auflösen.
    
- Für den Audio-/Video-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Audio-/Video-Edgediensts (z. B. av.contoso.com) in die IP-Adresse des A/V-Edgediensts auf einem der Edgeserver im Pool auflösen.
    
Zur Bereitstellung des DNS-Lastenausgleichs für die interne Schnittstelle Ihres Edgeserverpools müssen Sie einen DNS-A-Eintrag hinzufügen, der den internen FQDN des Edgeserverpools in die IP-Adressen der einzelnen Server innerhalb des Pools auflöst.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools
<a name="BK_Mediation"> </a>

Sie können den DNS-Lastenausgleich in eigenständigen Vermittlungsserverpools verwenden. Der gesamte SIP- und Mediendatenverkehr wird durch den DNS-Lastenausgleich verteilt.
  
Zur Bereitstellung des DNS-Lastenausgleichs in einem Vermittlungsserverpool müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. mediationpool1.contoso.com) in die IP-Adressen aller Server im Pool (z.<B. 192.168.1.1, 192.168.1.2 usw.) bereitstellen.
.
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blockieren von Datenverkehr zu einem Server mit DNS-Lastenausgleich
<a name="BK_Mediation"> </a>

Wenn Sie den DNS-Lastenausgleich verwenden und Datenverkehr zu einem bestimmten Computer blockieren müssen, reicht es nicht aus, nur die Einträge der IP-Adresse aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen. 
  
Beachten Sie, dass Skype for Business Server für Server-zu-Server-Datenverkehr topologien-entigen Lastenausgleich verwendet. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie zu erhalten, und verteilen den Datenverkehr automatisch auf die Server. Um zu blockieren, dass ein Server Server-zu-Server-Datenverkehr empfängt, müssen Sie den Server aus der Topologie entfernen. 
  

