---
title: Anforderungen an den Lastenausgleich für Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Zusammenfassung: Überprüfen Sie die Überlegungen zum Lastenausgleich vor der Implementierung von Skype for Business Server.'
ms.openlocfilehash: 2db9b7aa37f71d445feb3cfd9a09e49f44ca48f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297057"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Anforderungen an den Lastenausgleich für Skype for Business
 
**Zusammenfassung:** Überprüfen Sie die Überlegungen zum Lastenausgleich, bevor Sie Skype for Business Server implementieren.
  
Der Lastenausgleich verteilt den Datenverkehr zwischen den Servern in einem Pool. Wenn Sie über Front-End-Pools, Mediation Server-Pools oder Edge-Server-Pools verfügen, müssen Sie den Lastenausgleich für diese Pools bereitstellen.
  
Skype for Business Server unterstützt zwei Arten von Lastenausgleichslösungen für Client-zu-Server-Datenverkehr: Domain Name System (DNS)-Lastenausgleich und Hardwarelastenausgleich (häufig abgekürzt als HLB). Der DNS-Lastenausgleich bietet zahlreiche Vorteile, darunter eine einfachere Verwaltung, effizientere Problembehandlung und die Möglichkeit, einen Großteil Ihres Skype for Business Server-Datenverkehrs von möglichen Problemen beim Hardware-Lastenausgleichsmodul zu isolieren.
  
Entscheiden Sie selbst, welche Lastenausgleichslösung für jeden Pool in Ihrer Bereitstellung geeignet ist, aber beachten Sie die folgenden Einschränkungen: 
  
- Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.
    
- Für einige Arten von Datenverkehr ist ein Hardwaregerät zum Lastenausgleich erforderlich. HTTP-Datenverkehr erfordert beispielsweise ein Hardwaregerät zum Lastenausgleich anstatt eines DNS-Lastenausgleichs. Der DNS-Lastenausgleich funktioniert nicht beim Client-zu-Server-Datenverkehr.
    
Wenn Sie für einen Pool den DNS-Lastenausgleich verwenden möchten, aber dennoch Hardwaregeräte zum Lastenausgleich benötigen, beispielsweise für den HTTP-Datenverkehr, ist die Verwaltung der Hardwaregeräte zum Lastenausgleich jetzt erheblich einfacher. Ein Beispiel hierfür ist, dass ausschließlich der HTTP- und HTTPS-Datenverkehr verwaltet wird, während alle anderen Protokolle vom DNS-Lastenausgleich verwaltet werden. Ausführliche Informationen finden Sie unter [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Für den Server-zu-Server-Datenverkehr verwendet Skype for Business Server einen Topologie-bezogenen Lastenausgleich. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie abzurufen und den Datenverkehr automatisch auf die Server zu verteilen. Administratoren müssen diese Art des Lastenausgleichs weder konfigurieren noch verwalten. 
  
Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen. 
  
## <a name="hardware-load-balancer-requirements"></a>Anforderungen an das Hardwaregerät zum Lastenausgleich

Die von Skype for Business Server skalierte konsolidierte Edge-Topologie ist für den DNS-Lastenausgleich für neue Bereitstellungen optimiert, die sich hauptsächlich mit anderen Organisationen mit Skype for Business Server oder lync Server verbinden. Wenn für eines der folgenden Szenarien eine hohe Verfügbarkeit erforderlich ist, muss ein Hardware-Lastenausgleichsmodul für Edge-Server-Pools verwendet werden, um Folgendes zu tun: 
  
- Föderation mit Organisationen, die Office Communications Server 2007 R2 oder Office Communications Server 2007 verwenden
    
- Exchange um für Remotebenutzer mit Exchange um vor Exchange 2010 mit SP1
    
- Verbindung mit Benutzern öffentlicher Chatdienste
    
> [!IMPORTANT]
> Das Verfahren, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden, wird nicht unterstützt. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden. 
  
> [!NOTE]
> Wenn Sie ein Hardwaregerät zum Lastenausgleich einsetzen, muss der Lastenausgleich für Verbindungen mit dem internen Netzwerk so konfiguriert werden, dass nur für den Datenverkehr zu Servern, auf denen der Zugriffs-Edgedienst und der A/V-Edgedienst ausgeführt werden, ein Lastenausgleich stattfindet. Es kann kein Lastenausgleich für den Datenverkehr zum internen Webkonferenz-Edgedienst oder zum internen XMPP-Proxydienst durchgeführt werden. 
  
> [!NOTE]
> Die direkte Server Rückgabe (DSR) NAT wird von Skype for Business Server nicht unterstützt. 
  
Wenn Sie feststellen möchten, ob Ihr Hardware-Lastenausgleichsmodul die erforderlichen Funktionen unterstützt, die von Skype for Business Server benötigt werden, lesen Sie [Infrastruktur für Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird

Im folgenden finden Sie die Anforderungen des Hardwarelastenausgleichs für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird:
  
- Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443. Mit diesem Algorithmus werden mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammengefasst.
    
- Deaktivieren Sie die TCP-Nagling für den externen Portbereich 50.000-59.999. 
    
- Verwenden Sie keine Netzwerkadressenübersetzung für die interne oder externe Firewall. 
    
- Die interne Schnittstelle für Edge muss sich in einem anderen Netzwerk befinden als die externe Schnittstelle des Edge-Servers, und das Routing zwischen diesen muss deaktiviert sein. 
    
- Die externe Schnittstelle des Edgeserver, auf dem der A/V-Edgedienst ausgeführt wird, muss öffentlich routingfähige IP-Adressen und keine NAT-oder Portübersetzung für beliebige externe IP-Adressen verwenden. 
    
- Die Quelladresse des Clients darf durch den Lastenausgleich nicht geändert werden.
    
### <a name="other-hardware-load-balancer-requirements"></a>Andere Anforderungen an das Hardware-Lastenausgleichsmodul

In Skype for Business Server für Web Services sind die Anforderungen an die Cookie-basierte Affinität stark reduziert. Wenn Sie Skype for Business Server bereitstellen und keine lync Server 2010-Front-End-Server oder Front-End-Pools beibehalten, benötigen Sie keine Cookie-basierte Persistenz. Wenn Sie jedoch vorübergehend oder dauerhaft alle lync Server 2010-Front-End-Server oder Front-End-Pools behalten, verwenden Sie weiterhin Cookie-basierte Persistenz, während Sie für lync Server 2010 bereitgestellt und konfiguriert werden. 
  
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
> Typische Hardware-Lastenausgleichsmodul-Konfigurationen verwenden eine Quell Adress Affinität und eine 20-minütige TCP-Sitzungslebensdauer, was für lync Server-und lync 2013-Clients in Ordnung ist, da der Sitzungszustand über die Clientnutzung und/oder die Anwendungs Interaktion verwaltet wird. 
  
Wenn Sie mobile Geräte bereitstellen, muss das Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).
  
> [!CAUTION]
> Wenn Sie mobile Geräte bereitstellen, muss Ihr Hardwarelastenausgleich in der Lage sein, jede Anforderung innerhalb einer TCP-Verbindung einzeln zu Lasten. Für die neuesten mobilen Apps für Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich.  
  
> [!CAUTION]
> Details zu Lastenausgleichsgeräten von Drittanbietern finden Sie unter [Infrastruktur für Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
Im Folgenden sind die Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Director- und Front-End-Pool-Webdienste aufgeführt:
  
- Legen Sie für interne virtuelle IP-Adressen der Webdienste die Dauerhaftigkeit von Quelladressen (interner Port 80, 443) für das Hardwaregerät zum Lastenausgleich fest. Bei Skype for Business Server bedeutet Source_addr-Persistenz, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse kommen, immer an einen Server gesendet werden, um den Sitzungsstatus beizubehalten.
    
- Legen Sie ein TCP-Leerlauftimeout von 1.800 Sekunden fest.
    
- Erstellen Sie auf der Firewall zwischen dem Reverseproxy und dem Hardwarelastenausgleich des nächsten Hop-Pools eine Regel zum Zulassen von https: Datenverkehr auf Port 4443 vom Reverse-Proxy zum Hardware-Lastenausgleichsmodul. Das Hardwaregerät zum Lastenausgleich muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Zusammenfassung der Affinitätsanforderungen an das Hardwaregerät zum Lastenausgleich

|**Client-/Benutzerstandort**|**Affinitätsanforderungen an den externen Webdienste-FQDN**|**Affinitätsanforderungen an den internen Webdienste-FQDN**|
|:-----|:-----|:-----|
|Lync Web App (interne und externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Lync Web App (nur externe Benutzer)  <br/> Mobiles Gerät (interne und externe Benutzer)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
|Lync Web App (nur interne Benutzer)  <br/> Mobiles Gerät (nicht bereitgestellt)  <br/> |Keine Affinität  <br/> |Quelladressenaffinität  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Portüberwachung für Hardwaregeräte zum Lastenausgleich

Sie definieren die Portüberwachung für Hardwaregeräte zum Lastenausgleich (Hardware Load Balancers, HLB), um festzustellen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind. Wenn beispielsweise der Front-End-Server Dienst (RTCSRV) angehalten wird, weil der Front-End-Server oder der Front-End-Pool fehlschlägt, sollte die HLB-Überwachung auch den Empfang von Datenverkehr über die Webdienste beenden. Sie können die HLB-Portüberwachung implementieren, um Folgendes zu überwachen:
  
**Front-End-Server-Benutzer Pool – HLB-interne Schnittstelle**

|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool\>Web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-End  <br/> 5061  <br/> |Quelle  <br/> |HTTPS  <br/> |
|\<Pool\>Web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-End  <br/> 5061  <br/> |Quelle  <br/> |HTTP  <br/> |
   
**Front-End-Server-Benutzer Pool – HLB-externe Schnittstelle**

|**Virtuelle IP/Port**|**Knoten Port**|**Knoten Computer/Monitor**|**Persistenzprofil**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|\<Pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTPS  <br/> |
|\<Pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Keine  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BKMK_DNSLoadBalancing"> </a>

Skype for Business Server ermöglicht DNS Load Balancing, eine Softwarelösung, die den Verwaltungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich verringern kann. Der DNS-Lastenausgleich balanciert den Netzwerkverkehr, der für Skype for Business Server eindeutig ist, wie etwa SIP-Datenverkehr und Medien Verkehr.
  
Wenn Sie den DNS-Lastenausgleich bereitstellen, wird der Verwaltungsaufwand Ihres Unternehmens für Hardware-Lastenausgleichs Komponenten minimiert. Darüber hinaus wird eine komplexe Problembehandlung von Problemen im Zusammenhang mit der Fehlkonfiguration von Last-Balancern für den SIP-Datenverkehr eliminiert. Sie können auch Serververbindungen verhindern, damit Sie Server offline schalten können. Durch den DNS-Lastenausgleich wird auch sichergestellt, dass die Probleme mit dem Hardwarelastenausgleich keine Auswirkungen auf Elemente des SIP-Datenverkehrs wie einfaches Anrufrouting haben.

Das folgende Diagramm zeigt ein Beispiel, das sowohl internen als auch externen DNS-Lastenausgleich umfasst: 
  
**Diagramm eines Edgenetzwerks, in dem öffentliche IPv4-Adressen verwendet werden**

![Beispiel eines DNS-Netzwerkdiagramms](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Wenn Sie den DNS-Lastenausgleich verwenden, sind Sie möglicherweise auch in der Lage, kostengünstigere Hardwarelastenausgleichs zu erwerben, als wenn Sie den Hardwarelastenausgleich für alle Arten von Datenverkehr verwendet haben. Sie sollten Load-Balancer verwenden, die Interoperabilitäts Qualifizierungstests mit Skype for Business Server bestanden haben. Ausführliche Informationen zum Testen der Lastenausgleichsmodul-Interoperabilität finden Sie unter [lync Server 2010 Load Balancer-Partner](https://go.microsoft.com/fwlink/p/?linkId=202452). Die dort behandelten Inhalte gelten für Skype for Business Server.
  
Der DNS-Lastenausgleich wird für Front-End-Pools, Edge-Server-Pools, Director-Pools und eigenständige Vermittlungsserver Pools unterstützt.
  
Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert. Die Anwendung (beispielsweise ein Client, auf dem Skype for Business ausgeführt wird) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem eine Verbindung mit einer der IP-Adressen hergestellt wird, die von der DNS a-und AAAA-Daten Satz Abfrage für den vollqualifizierten Domänennamen (FQDN) des Pools zurückgegeben werden. 
  
Wenn beispielsweise drei Front-End-Server in einem Pool mit dem Namen pool01.contoso.com vorhanden sind, geschieht Folgendes:
  
- Clients mit Skype for Business-Abfrage-DNS für pool01.contoso.com. Die Abfrage gibt drei IP-Adressen zurück und speichert Sie wie folgt (nicht unbedingt in dieser Reihenfolge):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Der Client versucht, eine TCP-Verbindung (Transmission Control Protocol) mit einer der IP-Adressen einzurichten. Wenn dies fehlschlägt, versucht der Client die nächste IP-Adresse im Cache.
    
- Bei erfolgreicher TCP-Verbindung handelt der Client die Verwendung von TLS zur Verbindungsherstellung mit der primären Registrierung in „pool01.contoso.com“ aus.
    
- Wenn der Client alle zwischengespeicherten Einträge ohne eine erfolgreiche Verbindung versucht, wird der Benutzer benachrichtigt, dass zurzeit keine Server mit Skype for Business Server verfügbar sind.
    
> [!NOTE]
> DNS-basierter Lastenausgleich unterscheidet sich von DNS-Round-Robin (DNS-RR), die sich normalerweise auf den Lastenausgleich bezieht, indem DNS eine andere Reihenfolge der IP-Adressen bereitstellt, die den Servern in einem Pool entsprechen. In der Regel aktiviert DNS-RR nur die Lastverteilung, aktiviert aber kein Failover. Wenn beispielsweise die Verbindung mit der einzigen IP-Adresse, die von der DNS-Abfrage a und AAAA zurückgegeben wird (wenn Sie eine IPv6-Adressierung verwenden) fehlschlägt, schlägt die Verbindung fehl. Aus diesem Grund ist DNS Round Robin selbst weniger zuverlässig als DNS-basierter Lastenausgleich. Sie können DNS Round Robin in Verbindung mit dem DNS-Lastenausgleich verwenden. 
  
DNS-Lastenausgleich wird für Folgendes verwendet:
  
- Lastenausgleich von Server-zu-Server-SIP auf die Edgeserver
    
- Lastenausgleich für Unified Communications Application Services (UCAS)-Anwendungen wie automatische Konferenzzentrale, Reaktionsgruppe und Anruf Park
    
- Verhindern neuer Verbindungen zu UCAS-Anwendungen (auch bekannt als "Draining")
    
- Lastenausgleich für den gesamten Client-zu-Server-Datenverkehr zwischen Clients und Edgeserver
    
Der DNS-Lastenausgleich kann für Folgendes nicht verwendet werden:
  
- Client-zu-Server-Webverkehr an Director-oder Front-End-Server
    
DNS-Load-Balancing und Federated-Traffic:
  
Wenn mehrere DNS-Einträge von einer DNS-SRV-Abfrage zurückgegeben werden, wählt der Access-Edgedienst immer den DNS-SRV-Eintrag mit der niedrigsten numerischen Priorität und dem höchsten numerischen Gewicht aus. Das Internet Engineering Task Force-Dokument "ein DNS-Eintrag für die Angabe des Standorts von Diensten (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) , gibt an, dass, wenn mehrere DNS-SRV-Einträge definiert sind, Priorität zuerst verwendet wird, und dann Gewichtung. DNS-SRV-Eintrag a hat beispielsweise eine Gewichtung von 20 und eine Priorität von 40 und DNS-SRV-Eintrag B hat eine Gewichtung von 10 und eine Priorität von 50. DNS-SRV-Eintrag A mit Priorität 40 wird ausgewählt. Für die Auswahl des DNS-SRV-Eintrags gelten die folgenden Regeln:
  
- Priorität wird zuerst berücksichtigt. Ein Client muss versuchen, den vom DNS-SRV-Eintrag definierten Ziel Host mit der niedrigsten nummerierten Priorität zu kontaktieren, die er erreichen kann. Ziele mit der gleichen Priorität sollten in einer Reihenfolge ausprobiert werden, die durch das gewichtungsfeld definiert ist.
    
- Das Feld "Gewichtung" gibt eine relative Gewichtung für Einträge mit der gleichen Priorität an. Bei größeren gewichten sollte eine proportional höhere Wahrscheinlichkeit für die Auswahl angegeben werden. DNS-Administratoren sollten Weight 0 verwenden, wenn keine Serverauswahl vorhanden ist. In Anwesenheit von Datensätzen mit einer Gewichtung von mehr als 0 sollten Datensätze mit der Gewichtung 0 eine sehr geringe Wahrscheinlichkeit haben, ausgewählt zu werden.
    
Wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden, wählt der Access-Edgedienst den SRV-Eintrag aus, der zuerst vom DNS-Server empfangen wurde.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>DNS-Lastenausgleich in Front-End-Pools und Director-Pools

Sie können den DNS-Lastenausgleich für den SIP-Datenverkehr in Front-End-Pools und Director-Pools verwenden. Wenn der DNS-Lastenausgleich bereitgestellt wird, müssen Sie weiterhin Hardwarelastenausgleichs für diese Pools verwenden, jedoch nur für den HTTPS-Datenverkehr zwischen Client und Server. Das Hardware-Lastenausgleichsmodul wird für HTTPS-Datenverkehr von Clients über Ports 443 und 80 verwendet. 
  
Obwohl Sie weiterhin Hardwarelastenausgleichs für diese Pools benötigen, werden deren Einrichtung und Verwaltung in erster Linie für den HTTPS-Datenverkehr verwendet, den die Administratoren von Hardwarelastenausgleich-Geräten gewohnt sind.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS-Lastenausgleich und Unterstützung älterer Clients und Server

Der DNS-Lastenausgleich unterstützt das automatische Failover nur für Server mit Skype for Business Server oder lync Server 2010 sowie für lync 2013-und Skype for Business-Clients. Frühere Versionen von Clients und Office Communications Server können weiterhin mit Pools verbunden werden, auf denen der DNS-Lastenausgleich ausgeführt wird, doch wenn Sie keine Verbindung mit dem ersten Server herstellen können, auf den der DNS-Lastenausgleich verweist, kann ein Failover zu einem anderen Server im Pool nicht durchgeführt werden. . 
  
Wenn Sie Exchange um verwenden, müssen Sie außerdem mindestens Exchange 2010 SP1 verwenden, um Unterstützung für den DNS-Lastenausgleich für Skype for Business Server zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, verfügen Ihre Benutzer nicht über Failoverfunktionen für diese Exchange um-Szenarien:
  
- Wiedergeben Ihrer Enterprise-Voicemail auf dem Telefon
    
- Übertragen von Anrufen von einer automatischen Exchange UM-Telefonzentrale
    
Alle anderen Exchange um-Szenarien funktionieren ordnungsgemäß.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Director-Pools
<a name="BK_FE_Dir"> </a>

Für die Bereitstellung des DNS-Lastenausgleichs in Front-End-Pools und Director-Pools müssen Sie einige zusätzliche Schritte mit FQDNs und DNS-Einträgen durchführen.
  
- Ein Pool, der den DNS-Lastenausgleich verwendet, muss zwei FQDNs aufweisen: den regulären Pool-FQDN, der vom DNS-Lastenausgleich (wie pool01.contoso.com) verwendet wird, und er wird in die physischen IPS der Server im Pool aufgelöst, und ein anderer FQDN für die Webdienste des Pools (wie web01.contoso.com), der in die virtuelle IP-Adresse des Pools aufgelöst wird. 
    
    Wenn Sie im Topologie-Generator den DNS-Lastenausgleich für einen Pool bereitstellen möchten, müssen Sie zum Erstellen dieses zusätzlichen FQDN für die Webdienste des Pools das Kontrollkästchen **FQDN des internen Webdienste-Pool außer Kraft setzen** aktivieren, und geben Sie den FQDN in die Webdienste **-URLs angeben für ein. Seite dieses Pools** .
    
- Zur Unterstützung des vom DNS-Lastenausgleich verwendeten FQDN müssen Sie DNS bereitstellen, um den Pool-FQDN (wie pool01.contoso.com) in die IP-Adressen aller Server im Pool aufzulösen (beispielsweise 192.168.1.1, 192.168.1.2 usw.). Sie sollten nur die IP-Adressen der Server einbeziehen, die derzeit bereitgestellt werden.
    
    > [!CAUTION]
    > Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als **pool01.contoso.com**definieren, können Sie **pool01.contoso.com** nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie beschließen, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>DNS-Lastenausgleich auf Edgeserver-Pools
<a name="BK_Edge"> </a>

Sie können den DNS-Lastenausgleich auf Edgeserver-Pools bereitstellen. Wenn Sie dies tun, müssen Sie sich mit einigen Überlegungen vertraut machen.
  
Die Verwendung des DNS-Lastenausgleichs auf Ihren Edge-Servern führt in den folgenden Szenarien zu einem Verlust der Failover-Fähigkeit:
  
- Föderation mit Organisationen, die Versionen von Skype for Business Server ausführen, die vor lync Server 2010 veröffentlicht wurden.
    
- Instant-Message-Austausch mit Nutzern von öffentlichen Instant Messaging-Diensten (im) AOL und Yahoo!, zusätzlich zu XMPP-basierten Anbietern und Servern wie Google Talk, dem derzeit einzigen unterstützten XMPP-Partner.
    
Diese Szenarien funktionieren so lange, wie alle Edgeserver im Pool ausgeführt werden, aber wenn ein Edgeserver nicht verfügbar ist, werden alle Anforderungen für diese Szenarien, die an ihn gesendet werden, nicht mehr an einen anderen Edgeserver weitergeleitet.
  
 Wenn Sie Exchange um verwenden, müssen Sie mindestens Exchange 2013 verwenden, um Unterstützung für den DNS-Lastenausgleich von Skype for Business Server auf Edge zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, verfügen die Remotebenutzer nicht über Failoverfunktionen für diese Exchange um-Szenarien:
  
- Wiedergeben Ihrer Enterprise-Voicemail auf dem Telefon
    
- Übertragen von Anrufen von einer automatischen Exchange UM-Telefonzentrale
    
Alle anderen Exchange um-Szenarien funktionieren ordnungsgemäß.
  
Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Bereitstellen des DNS-Lastenausgleichs auf Edgeserver-Pools

Zum Bereitstellen des DNS-Lastenausgleichs auf der externen Schnittstelle Ihres Edge-Server Pools benötigen Sie die folgenden DNS-Einträge:
  
- Für den Access Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Access-Edgedienst (beispielsweise SIP.contoso.com) in die IP-Adresse des Access Edge-Diensts auf einem der Edgeserver im Pool auflösen.
    
- Für den Web Conferencing Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Webkonferenz-Edgedienst (beispielsweise webconf.contoso.com) in die IP-Adresse des Webkonferenz-Edgedienst auf einem der Edgeserver im Pool auflösen.
    
- Für den Audio/Video Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des A/V Edge-Diensts auf einem der Edgeserver im Pool auflösen.
    
Zum Bereitstellen des DNS-Lastenausgleichs auf der internen Schnittstelle Ihres Edge-Server Pools müssen Sie einen DNS-A-Eintrag hinzufügen, der den internen FQDN des Edge-Server Pools in die IP-Adresse jedes Servers im Pool auflöst.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Verwenden des DNS-Lastenausgleichs in Vermittlungs Server Pools
<a name="BK_Mediation"> </a>

Sie können den DNS-Lastenausgleich für eigenständige Vermittlungs Server Pools verwenden. Der gesamte SIP-und Mediendatenverkehr wird durch den DNS-Lastenausgleich ausgeglichen.
  
Zum Bereitstellen des DNS-Lastenausgleichs in einem Vermittlungs Server Pool müssen Sie DNS bereitstellen, um den Pool-FQDN (beispielsweise mediationpool1.contoso.com) in die IP-Adressen aller Server im Pool aufzulösen (beispielsweise 192.168.1.1, 192.168.1.2 usw.).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blockieren des Datenverkehrs auf einem Server mit DNS-Lastenausgleich
<a name="BK_Mediation"> </a>

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen. 
  
Beachten Sie, dass Skype for Business Server für den Server-zu-Server-Datenverkehr Topologie-bewusste Lastenverteilung verwendet. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie abzurufen und den Datenverkehr automatisch auf die Server zu verteilen. Wenn Sie verhindern möchten, dass ein Server Server-zu-Server-Datenverkehr empfängt, müssen Sie den Server aus der Topologie entfernen. 
  

