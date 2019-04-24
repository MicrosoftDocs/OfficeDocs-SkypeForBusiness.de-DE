---
title: Anforderungen an den Lastenausgleich für Skype for Business
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Zusammenfassung: Überprüfen Sie den Lastenausgleich Überlegungen vor der Implementierung von Skype für Business Server.'
ms.openlocfilehash: a7e8e70088c83276c36334c5d9a1e3be1538ca38
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206487"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Anforderungen an den Lastenausgleich für Skype for Business
 
**Zusammenfassung:** Überprüfen Sie den Lastenausgleich Überlegungen vor der Implementierung von Skype für Business Server.
  
Der Lastenausgleich verteilt Datenverkehr zwischen den Servern in einem Pool. Wenn Sie Front-End-Pools, edgeserverpools oder vermittlungsserverpools haben, müssen Sie für den Lastenausgleich für diese Pools bereitstellen.
  
Skype für Business Server unterstützt zwei Arten von Lösungen für Client-zu-Server-Datenverkehr für den Lastenausgleich: Domain Name System (DNS)-Lastenausgleich und Hardwaregeräte zum Lastenausgleich oft (als Hardwaregeräts zum Lastenausgleich Abkürzung). DNS-Lastenausgleich Lastenausgleich bietet mehrere Vorteile, einschließlich einfachere Verwaltung, effizienter Problembehandlung und die Möglichkeit zum Großteil Ihrer Skype für Business Server Datenverkehr von potenzielle Hardware Load Balancer Probleme zu isolieren.
  
Für sich selbst die lastenausgleichslösung für jeden Pool in Ihrer Bereitstellung eignet sich entscheiden Sie, aber Bedenken Sie die folgenden Einschränkungen: 
  
- Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.
    
- Für einige Arten von Datenverkehr ist ein Hardwaregerät zum Lastenausgleich erforderlich. HTTP-Datenverkehr erfordert beispielsweise ein Hardwaregerät zum Lastenausgleich anstatt eines DNS-Lastenausgleichs. Der DNS-Lastenausgleich funktioniert nicht beim Client-zu-Server-Datenverkehr.
    
Wenn Sie für einen Pool den DNS-Lastenausgleich verwenden möchten, aber dennoch Hardwaregeräte zum Lastenausgleich benötigen, beispielsweise für den HTTP-Datenverkehr, ist die Verwaltung der Hardwaregeräte zum Lastenausgleich jetzt erheblich einfacher. Ein Beispiel hierfür ist, dass ausschließlich der HTTP- und HTTPS-Datenverkehr verwaltet wird, während alle anderen Protokolle vom DNS-Lastenausgleich verwaltet werden. Ausführliche Informationen finden Sie unter [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
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
> Wenn Sie mobile Geräte bereitstellen, Ihr Hardwaregerät zum Lastenausgleich muss möglicherweise einzeln laden jeder Anforderung in einer TCP-Verbindung zu erreichen. Für die neuesten mobilen Apps für Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich.  
  
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

|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool\>Web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-End  <br/> 5061  <br/> |Quelle  <br/> |HTTPS  <br/> |
|\<Pool\>Web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-End  <br/> 5061  <br/> |Quelle  <br/> |HTTP  <br/> |
   
**Front-End-Server-Benutzerpool – externe HLB-Schnittstelle**

|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<Pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BKMK_DNSLoadBalancing"> </a>

Skype für Business Server ermöglicht DNS-Lastenausgleich, eine Software-Lösung, die die Verwaltung Wartungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich beeinträchtigen können. DNS-Lastenausgleich gleicht den Netzwerkdatenverkehr, der für Skype für Business Server, wie etwa SIP-Datenverkehr und der Mediendatenverkehr eindeutig ist.
  
Wenn Sie die DNS-Lastenausgleich bereitstellen, wird Ihre Organisation Administration Wartungsaufwand für Hardwaregeräte zum Lastenausgleich minimiert. Darüber hinaus werden komplexe Problembehandlung von Problemen im Zusammenhang mit einer fehlerhaften Konfiguration des Systems zum Lastenausgleich für SIP-Datenverkehr ausgeschlossen werden. Sie können auch Server-Verbindungen verhindern, sodass Sie die Server offline schalten können. DNS-Lastenausgleich wird sichergestellt, dass Hardware Load Balancer Probleme Elemente des SIP-Datenverkehr, wie Sie grundlegende Anrufrouting nicht beeinträchtigen.

Das folgende Diagramm zeigt ein Beispiel, das sowohl interne und externe DNS-Lastenausgleich: 
  
**Diagramm eines Edgenetzwerks, in dem öffentliche IPv4-Adressen verwendet werden**

![Beispiel eines DNS-Netzwerkdiagramms](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Wenn Sie die DNS-Lastenausgleich verwenden, können Sie möglicherweise auch niedrigeren Kosten Hardwaregeräte zum Lastenausgleich als, wenn Sie die Hardwaregeräte zum Lastenausgleich für alle Arten von Datenverkehr verwendet erwerben. Sie sollten den Systemen zum Lastenausgleich verwenden, die Interoperabilität Qualifikation Testen mit Skype für Business Server übergeben haben. Ausführliche Informationen zur Interoperabilität das Testen des Lastenausgleichs finden Sie unter [Lync Server 2010 Load Balancer Partners](https://go.microsoft.com/fwlink/p/?linkId=202452). Der Inhalt es gilt für Skype für Business Server.
  
DNS-Lastenausgleich wird für Front-End-Pools, edgeserverpools, Director-Pools und eigenständige vermittlungsserverpools unterstützt.
  
DNS-Lastenausgleich wird in der Regel auf der Anwendungsebene implementiert. Die Anwendung (beispielsweise in einem Client unter Skype für Unternehmen), versucht, Verbindung mit einem Server in einem Pool eine Verbindung zu einer IP-Adressen zurückgegeben, die von den DNS-A und AAAA (Wenn IPv6-Adressen verwendet wird) Abfrage für den vollqualifizierten Domänennamen (FQDN) von Pools aufzeichnen. 
  
Beispielsweise, wenn es sind drei Front-End-Servern in einem Pool mit dem Namen "pool01.contoso.com", passiert Folgendes:
  
- Clients, auf denen Skype für Unternehmen DNS-Abfrage für "pool01.contoso.com". Die Abfrage gibt drei IP-Adressen und speichert diese wie folgt (nicht unbedingt in dieser Reihenfolge):
    
    "pool01.contoso.com" 192.168.10.90
    
    "pool01.contoso.com" 192.168.10.91
    
    "pool01.contoso.com" 192.168.10.92
    
- Der Client versucht, eine Verbindung (TCP = Transmission Control Protocol) auf eine IP-Adressen herzustellen. Wenn dies nicht funktioniert, versucht der Client die nächste IP-Adresse im Cache.
    
- Bei erfolgreicher TCP-Verbindung handelt der Client die Verwendung von TLS zur Verbindungsherstellung mit der primären Registrierung in „pool01.contoso.com“ aus.
    
- Wenn der Client alle zwischengespeicherten Einträge eine erfolgreiche Verbindung versucht, wird der Benutzer benachrichtigt, dass gegenwärtig keine Server mit Skype für Business Server verfügbar sind.
    
> [!NOTE]
> DNS-Lastenausgleich unterscheidet sich vom DNS Round-Robin (DNS-Ressourceneintrag) in der Regel bezieht sich dies auf Lastenausgleich mithilfe der vertrauenden Seite DNS zum Bereitstellen einer anderen Reihenfolge von IP-Adressen, die Server in einem Pool entspricht. In der Regel die DNS-RR nur ermöglicht Verteilung geladen werden jedoch nicht Failover zu ermöglichen. Beispiel: bei die Verbindung mit der eine IP-Adresse durch die DNS-A und AAAA zurückgegeben (Wenn Sie IPv6-Adressen nutzen) Abfrage fehlschlägt, schlägt die Verbindung. Aus diesem Grund DNS Round-Robin allein weniger als DNS-Lastenausgleich zuverlässig ist. Sie können DNS Round-Robin in Verbindung mit DNS-Lastenausgleich. 
  
DNS-Lastenausgleich wird für Folgendes verwendet:
  
- Lastenausgleich für Server-zu-Server-SIP an den Edge-Servern
    
- Unified Communications Application Services (UCAS) Anwendungen wie Konferenzen Auto Attendant, die Reaktionsgruppenanwendung und Parken von Anrufen für den Lastenausgleich
    
- Verhindern neuer Verbindungen mit UCAS Applications (auch bekannt als "serverausgleich")
    
- Alle Client-zu-Server-Datenverkehr zwischen Clients und Edge-Server-Lastenausgleich
    
DNS-Lastenausgleich kann für Folgendes verwendet werden:
  
- Client-zu-Server-Webdatenverkehr zu Director oder Front-End-Servern
    
DNS-Lastenausgleich Lastenausgleich und Datenverkehr:
  
Wenn mehrere DNS-Datensätze von einer DNS-SRV-Abfrage zurückgegeben werden, tragen der Zugriffs-Edgeserver Service immer die DNS-SRV wählt mit der niedrigsten numerischen Priorität und numerische Gewichtung. Internet Engineering Task Force "Einen DNS-Ressourceneintrag für die Angabe des Speicherorts der Dienste (DNS SRV)" Dokument [RFC 2782, DNS-SRV-Ressourceneintrag](https://www.ietf.org/rfc/rfc2782.txt) gibt an, dass mehrere DNS-SRV Datensätze definiert sind, Priorität zuerst verwendet wird, klicken Sie dann weight. Beispielsweise DNS-SRV-Eintrag A hat eine Stärke Gewichtung 20 und eine Priorität von 40 und DNS-SRV-Eintrag B hat eine Stärke von 10 und Priorität von 50. DNS-SRV-Eintrag A mit Priorität 40 wird ausgewählt. Die folgenden Regeln gelten für DNS-SRV-Eintrag Auswahl:
  
- Priorität wird zuerst berücksichtigt. Ein Client muss versuchen, wenden Sie sich an den Zielhost definiert durch den DNS-SRV-Eintrag mit der niedrigsten nummerierten Priorität, die er erreichen kann. Ziele mit derselben Priorität sollten in der Reihenfolge von Feld Gewicht definierten versucht werden.
    
- Feld Gewicht gibt eine relative Gewichtung für Einträge mit derselben Priorität. Größere Weights gegeben proportional steigt die Wahrscheinlichkeit eines ausgewählt werden kann. DNS-Administratoren sollten Gewichtung den Wert 0 verwenden, wenn keine Aktionen-Serverauswahl vorhanden ist. In Anwesenheit Datensätze, die größer als 0 Weights sollte Datensätze mit Gewichtung den Wert 0 eine sehr kleine Chance ausgewählt werden kann.
    
Wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden, wählt der Zugriffs-edgedienst den SRV-Eintrag, der zunächst von der DNS-Server empfangen wurde.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>DNS-Lastenausgleichs für Front-End-Pools und Director-Pools

Sie können die DNS-Lastenausgleich für den SIP-Datenverkehr auf Front-End-Pools und Director-Pools verwenden. Mit der DNS-Lastenausgleich bereitgestellt haben, müssen Sie dennoch auch Hardwaregeräte zum Lastenausgleich für diese Pools, jedoch nur für HTTPS-Datenverkehr von Client-zu-Server verwenden. Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über Port 443 und 80 verwendet. 
  
Obwohl Sie noch Hardwaregeräte zum Lastenausgleich für diese Pools benötigen, werden die Einrichtung und Verwaltung in erster Linie für HTTPS-Datenverkehr sein, die die Administratoren von Hardwaregeräten zum Lastenausgleich mit vertraut sind.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS-Lastenausgleich Lastenausgleich und Unterstützung älterer Clients und Server

DNS-Lastenausgleich Lastenausgleich unterstützt Automatisches Failover nur für Server unter Skype für Business Server oder Lync Server 2010 sowie für Lync 2013 und Skype für Business-Clients. Frühere Versionen von Clients und Office Communications Server können weiterhin eine Verbindung mit Pools der DNS-Lastenausgleich ausgeführt, wenn sie einer Verbindung mit dem ersten Server nicht ausgeführt werden können, dass DNS-Lastenausgleich zu verweist, werden aber kann nicht zum Failover auf einen anderen Server im pool . 
  
Wenn Sie Exchange UM verwenden, müssen Sie darüber hinaus ein Minimum von Exchange 2010 SP1 verwenden, um Unterstützung für Skype für Business Server DNS-Lastenausgleich zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, müssen Ihre Benutzer nicht Failover-Funktionen für diese Exchange UM-Szenarien:
  
- Ihre Enterprise-Voicemail wiedergeben über ein Telefon
    
- Weiterleiten von Anrufen von einem Exchange UM-Telefonzentrale
    
Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director Pools
<a name="BK_FE_Dir"> </a>

Bereitstellen von DNS müssen-Lastenausgleich in Front-End-Pools und Director-Pools Sie einige zusätzliche Schritte mit FQDNs und DNS-Einträge ausführen.
  
- Ein Pool, der DNS-Lastenausgleich verwendet, benötigen zwei FQDNs: der reguläre Pool-FQDN, die von DNS verwendet wird Lastenausgleichs (beispielsweise "pool01.contoso.com") und ergibt die physischen IP-Adressen der Server im Pool zu laden und eine andere FQDN für den Pool-Web services (z. b. web01.contoso.com), die virtuelle IP-Adresse des Pools aufgelöst wird. 
    
    Im Topologie-Generator Wenn Sie DNS-Lastenausgleich für einen Pool bereitstellen möchten müssen, um diese zusätzlichen FQDN für den Pool-Webdienste zu erstellen Sie aktivieren Sie das Kontrollkästchen **interne Webdienste außer Kraft setzen pool-FQDN** und geben Sie den FQDN, in der **Angeben der Webdienst-URLs für In diesem Pool** Seite.
    
- Sie müssen DNS zum Auflösen des Pools-FQDN (beispielsweise "pool01.contoso.com") in die IP-Adressen aller Server im Pool bereitstellen, zur Unterstützung der des FQDN von DNS-Lastenausgleich verwendet (zum Beispiel: 192.168.1.1, 192.168.1.2 usw.). Sie sollten nur die IP-Adressen der Server einschließen, die derzeit bereitgestellt werden.
    
    > [!CAUTION]
    > Wenn Sie mehrere Front-End-Pool oder Front-End-Server verfügen muss die externen Webdienste FQDN eindeutig sein. Wenn Sie die externen Webdienste-FQDN des Front-End-Server als **"pool01.contoso.com"** definieren, können nicht Sie beispielsweise **"pool01.contoso.com"** für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Director-Server bereitstellen, die externe Webdienste-FQDN für alle Director definierten oder Director-Pool muss aus einem anderen eindeutig sein Director oder Director-Pools sowie alle Front-End-Pool oder Front-End-Server Wenn Sie die internen Webdienste mit einem selbstdefinierten FQDN überschreiben, jeder FQDN muss von einem beliebigen anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>DNS-Lastenausgleich in Edgeserverpools
<a name="BK_Edge"> </a>

Sie können die DNS-Lastenausgleich in edgeserverpools bereitstellen. Wenn Sie dies tun, müssen Sie einige Punkte beachten sein.
  
Bei Verwendung des DNS-Lastenausgleichs auf Edge-Servern kein Failover mehr möglich in den folgenden Szenarien:
  
- Partnerverbund mit Organisationen, die Versionen von Skype für Business Server veröffentlicht werden, bevor Sie Lync Server 2010 ausgeführt werden.
    
- Austauschen von Sofortnachrichten mit Benutzern eines öffentlichen instant messaging (IM) Services AOL und Yahoo!, zusätzlich zu XMPP-basierten Anbieter und Server, wie Google Talk derzeit die einzige unterstützte XMPP-Partner.
    
Diese Szenarien funktionieren, solange alle Edge-Server im Pool ausgeführt werden, wenn ein Edge-Server nicht verfügbar ist, alle Anforderungen für diese Szenarien, die an sie gesendete fehl schlägt, anstelle der Weiterleitung an einen anderen Edge-Server.
  
 Wenn Sie Exchange UM verwenden, müssen Sie mindestens Exchange 2013 zum Abrufen von Unterstützung für Skype für Business Server DNS-Lastenausgleich in Edge verwenden. Wenn Sie eine frühere Version von Exchange verwenden, müssen Ihre Remotebenutzer nicht Failover-Funktionen für diese Exchange UM-Szenarien:
  
- Ihre Enterprise-Voicemail wiedergeben über ein Telefon
    
- Weiterleiten von Anrufen von einem Exchange UM-Telefonzentrale
    
Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.
  
Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Bereitstellen von DNS-Lastenausgleich in Edgeserverpools

Zum Bereitstellen von DNS-Lastenausgleichs für die externe Schnittstelle Ihres edgeserverpools benötigen Sie die folgenden DNS-Einträge:
  
- Für den Zugriffs-edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Zugriffs-edgediensts (zum Beispiel sip.contoso.com) in die IP-Adresse des Zugriffs-edgediensts auf einem Edge-Server im Pool aufgelöst werden.
    
- Für den Webkonferenz-edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Webkonferenz-Edgeserver-Diensts (beispielsweise webconf.contoso.com) in die IP-Adresse des Webkonferenz-Edgeserver-Dienstes auf einem Edge-Server im Pool aufgelöst werden.
    
- Für den a/v-edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des a/v-edgediensts (beispielsweise av.contoso.com) beheben, zur IP-Adresse des A / V-edgedienst auf einem Edge-Server im Pool.
    
Zum Bereitstellen von DNS-Lastenausgleichs für die interne Schnittstelle des Edgeservers Pools müssen Sie einen DNS-A-Datensatz hinzufügen, der den internen FQDN des Edge-Server-Pools in die IP-Adresse der einzelnen Server im Pool aufgelöst wird.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Mithilfe von DNS-Lastenausgleichs in Vermittlungsserverpools
<a name="BK_Mediation"> </a>

DNS-Lastenausgleichs für eigenständige vermittlungsserverpools können. Alle Medien und SIP-Datenverkehr wird von der DNS-Lastenausgleich ausgeglichen.
  
Zum Bereitstellen von DNS-Lastenausgleich in einem Pool Mediation Server müssen Sie DNS, um den vollqualifizierten Domänennamen (z. B. mediationpool1.contoso.com) des Pools aufgelöst bereitstellen, den IP-Adressen aller Server im Pool (zum Beispiel: 192.168.1.1, 192.168.1.2 usw.).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blockieren von Datenverkehr an einen Server mit DNS-Lastenausgleich
<a name="BK_Mediation"> </a>

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen. 
  
Beachten Sie, dass für Server-zu-Server-Datenverkehr Topologie berücksichtigen Lastenausgleich Skype für Business Server verwendet wird. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher erhalten Sie die FQDNs der Server in der Topologie, und automatisch den Datenverkehr zwischen den Servern zu verteilen. Um einen Server erhalten, Server-zu-Server-Datenverkehr zu blockieren, müssen Sie den Server aus der Topologie entfernen. 
  

