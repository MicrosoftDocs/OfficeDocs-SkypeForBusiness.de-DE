---
title: Erweiterte Edgeserver DNS-Planung für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Zusammenfassung: Überprüfen der Szenarien für Skype for Business Server Bereitstellungsoptionen. Unabhängig davon, ob Sie einen einzelnen Server oder einen Serverpool mit DNS oder HLB bevorzugen, sollte dieses Thema hilfreich sein.'
ms.openlocfilehash: b3893c11e1ce0cfdf9ab0b0452ef0a30a6442ee7
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887762"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Erweiterte Edgeserver DNS-Planung für Skype for Business Server
 
**Zusammenfassung:** Überprüfen Sie die Szenarien für Skype for Business Server Bereitstellungsoptionen. Unabhängig davon, ob Sie einen einzelnen Server oder einen Serverpool mit DNS oder HLB bevorzugen, sollte dieses Thema hilfreich sein.
  
Wenn es um die Domain Name System (DNS) Planung für Skype for Business Server geht, gibt es viele Faktoren, die bei ihrer Entscheidung möglicherweise wiedergegeben werden. Wenn die Domänenstruktur Ihrer Organisation bereits vorhanden ist, kann dies eine Frage der Überprüfung der Vorgehensweise sein. Zunächst finden Sie die folgenden Themen:
  
- [Exemplarische Vorgehensweise von Skype for Business Clients zum Auffinden von Diensten](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS-Notfallwiederherstellung](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Exemplarische Vorgehensweise von Skype for Business Clients zum Auffinden von Diensten
<a name="WalkthroughOfSkype"> </a>

Skype for Business Clients ähneln früheren Versionen von lync-Clients bei der Suche und dem Zugriff auf Dienste in Skype for Business Server. In diesem Abschnitt wird der Server Standort Prozess ausführlich beschrieben.
  
1. "lyncdiscoverinternal". \< Domäne\>
    
     *Dies ist ein A-Host-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten.* 
    
2. lyncdiscover. \< Domäne\>
    
     *Dies ist ein A-Host-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten.* 
    
3. _sipinternaltls. _tcp. \< Domäne\>
    
     *Hierbei handelt es sich um einen SRV-Eintrag für interne TLS-Verbindungen.* 
    
4. _sip. _tls. \< Domäne\>
    
     *Hierbei handelt es sich um einen SRV-Eintrag für externe TLS-Verbindungen.* 
    
5. sipinternal. \< Domäne\>
    
     *Dies ist ein Hosteintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann.* 
    
6. SIP. \< Domäne\>
    
     *Dies ist ein Hosteintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann.* 
    
7. sipexternal. \< Domäne\>
    
     *Dies ist ein Hosteintrag für den Zugriffs-Edgedienst, wenn der Client extern ist.* 
    
Der AutoErmittlungsdienst wird immer bevorzugt, da dies die bevorzugte Methode für den Dienst Speicherort ist und die anderen Fallback-Methoden.
  
> [!NOTE]
> Beim Erstellen von SRV-Einträgen ist es wichtig, sich daran zu erinnern, dass Sie auf ein DNS-a (und AAAA bei Verwendung der IPv6-Adressierung) in derselben Domäne hindeuten müssen, in der der DNS-SRV-Eintrag erstellt wird. Wenn Sie beispielsweise SRV-Einträge in contoso.com haben, kann der Eintrag a (und AAAA), auf den verwiesen wird, nicht in fabrikam.com sein. 
  
Wenn Sie dazu geneigt sind, können Sie Ihr mobiles Gerät für die manuelle Ermittlung von Diensten einrichten. Wenn Sie dies tun möchten, muss jeder Benutzer seine Einstellungen für mobile Geräte mit den vollständigen internen und externen AutoErmittlungsdienst-URIs, einschließlich Protokoll und Pfad, wie folgt konfigurieren:
  
- Für den externen Zugriff: https:// \< ExtPoolFQDN \> /autodiscover/autodiscoverservice.svc/root
    
- Für den internen Zugriff: https:// \< IntPoolFQDN \> /autodiscover/autodiscover.svc/root
    
Es wird empfohlen, die automatische Ermittlung im Gegensatz zur manuellen Ermittlung zu verwenden. Wenn Sie jedoch einige Fehlerbehebung oder Tests durchführen, können manuelle Einstellungen hilfreich sein.
  
## <a name="split-brain-dns"></a>Split-Brain-DNS
<a name="SplitBrainDNS"> </a>

Hierbei handelt es sich um eine DNS-Konfiguration, in der Sie zwei DNS-Zonen mit dem gleichen Namespace haben. Die erste DNS-Zone verarbeitet interne Anforderungen, während die zweite DNS-Zone externe Anforderungen verarbeitet.
  
Warum sollte ein Unternehmen dies tun? Sie haben möglicherweise die Voraussetzung, dass der gleiche Namespace intern und extern verwendet wird, aber das führt natürlich zu vielen DNS-SRV-Einträgen, und wenn es sich um Duplikate handelt, sind die IP-Adressen, die diesen Datensätzen zugeordnet sind, eindeutig.
  
Dies stellt einige Herausforderungen dar. Das wichtigste ist, dass das Split-Brain-DNS nicht für die Mobilität **unterstützt** wird. Dies liegt an den DNS-Einträgen LyncDiscover und "lyncdiscoverinternal" (LyncDiscover muss auf Ihrem externen DNS-Server definiert sein, während "lyncdiscoverinternal" auf dem internen DNS-Server definiert werden muss).
  
Hier werden die DNS-Einträge für die internen und externen Zonen aufgelistet, aber ausführliche Beispiele finden Sie im Abschnitt Edgeserver Umgebungsanforderungen.
  
### <a name="internal-dns"></a>Interne DNS-Konfiguration

- Enthält eine DNS-Zone namens (zum Beispiel) contoso.com, für die Sie autorisierend ist.
    
- Diese interne contoso.com enthält Folgendes:
    
  - DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für Ihre Front-End-Pool, Directorpool oder Directorpool Namen sowie für alle internen Server, auf denen Skype for Business Server im Netzwerk Ihrer Organisation betrieben werden.
    
  - DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für die interne Edge-Schnittstelle für jede Skype for Business Server Edgeserver in Ihrem Umkreisnetzwerk.
    
  - DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für die interne Schnittstelle aller Reverse-Proxy Server in Ihrem Umkreisnetzwerk ( **optional** für die Verwaltung eines Reverseproxys).
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) und SRV-Einträge für die interne Skype for Business Server Client-Autokonfiguration ( **optional** ).
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Ermittlung von Skype for Business Server Webdienste ( **optional** ).
    
- Alle Skype for Business Server internen Edge-Schnittstellen in Ihrem Umkreisnetzwerk verwenden diese interne DNS-Zone zum Auflösen von Abfragen in contoso.com.
    
- Alle Server mit Skype for Business Server und Clients, die Skype for Business Server im Unternehmensnetzwerk verwenden, weisen auf interne DNS-Server hin, um Abfragen in contoso.com zu lösen, oder Sie verwenden die Hostdatei auf jedem Edgeserver und Listen A und AAAA (wenn Sie IPv6-Adressierung verwenden) für den Server für den nächsten Hop (speziell für den Director oder Directorpool VIP). , Front-End-Pool VIP oder Standard Edition-Server).
    
### <a name="external-dns"></a>Externes DNS

- Enthält eine DNS-Zone namens (zum Beispiel) contoso.com, für die Sie autorisierend ist.
    
- Diese externe contoso.com enthält Folgendes:
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Ermittlung von Skype for Business Server-Webdiensten. Dies ist für die Verwendung mit Mobility.
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) und SRV-Einträge für die externe Edge-Schnittstelle jedes Skype for Business Server-Edgeserver oder-HLB-VIP (Hardware Lastenausgleich) im Umkreisnetzwerk.
    
  - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die externe Schnittstelle des Reverseproxy-Servers oder (VIP für einen Pool von Reverse-Proxyservern) im Umkreisnetzwerk.
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) und SRV-Einträge für Skype for Business Server Client-Autokonfiguration ( **optional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Automatische Konfiguration ohne Split-Brain-DNS
<a name="NoSplitBrainDNS"> </a>

Wenn Sie kein Split-Brain-DNS verwenden, funktioniert die interne automatische Konfiguration von Clients, auf denen Skype for Business läuft, nur, wenn Sie eine der hier beschriebenen Problemumgehungen verwenden. Warum nicht? Da Skype for Business Server erfordert, dass der SIP-URI des Benutzers mit der Domäne der Front-End-Pool übereinstimmt, die für die automatische Konfiguration festgelegt ist. Dies hat sich gegenüber früheren Versionen von lync Server nicht geändert.
  
Wenn Sie also zwei SIP-Domänen verwenden, benötigen Sie diese DNS-SRV-Einträge:
  
- _sipinternaltls. _tcp. contoso. com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Wenn sich ein Benutzer als Bob@contoso.com anmeldet, funktioniert dieser Datensatz für die automatische Konfiguration, da die SIP-Domäne des Benutzers mit der Domäne der Front-End-Pool (contoso.com) übereinstimmt.* 
    
- _sipinternaltls. _tcp. fabrikam. com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Wenn sich ein Benutzer als Alice@fabrikam.com anmeldet, würde dieser Datensatz für die automatische Konfiguration der zweiten Domäne wieder funktionieren, da die SIP-Domäne mit dem Front-End-Pool für diese Domäne übereinstimmt.* 
    
Um das Beispiel weiter zu nutzen, würde dies nicht funktionieren:
  
- _sipinternaltls. _tcp. litwareinc. com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Ein Benutzer, der sich als Tim@litwareinc.com anmeldet, funktioniert nicht für die automatische Konfiguration, da seine SIP-Domäne (litwareinc.com) nicht mit der Domäne im Pool (fabrikam.com) übereinstimmt.* 
    
Nun, da wir alles wissen, wenn Sie eine automatische Anforderung für Ihre Skype for Business-Clients ohne Split-Brain-DNS benötigen, haben Sie folgende Möglichkeiten:
  
- **Gruppenrichtlinienobjekte**
    
    Mithilfe von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) können Sie die richtigen Server Werte auffüllen.
    
    > [!NOTE]
    > Mit dieser Option wird die automatische Konfiguration nicht aktiviert, die manuelle Konfiguration wird jedoch automatisiert. Wenn dieser Ansatz verwendet wird, sind die der automatischen Konfiguration zugeordneten SRV-Einträge nicht erforderlich. 
  
- **Übereinstimmende interne Zone**
    
    Sie müssen eine Zone in Ihrem internen DNS erstellen, die ihrer externen DNS-Zone entspricht (beispielsweise contoso.com), und dann DNS a (und AAAA bei Verwendung von IPv6-Adressierungs Datensätzen) erstellen, die dem Skype for Business Server Pool entsprechen, der für die automatische Konfiguration verwendet wird.
    
    Wenn Sie beispielsweise einen Benutzer in pool01.contoso.net haben, sich jedoch in Skype for Business als Bob@contoso.com befinden, eine interne DNS-Zone namens Contoso.com erstellen möchten, müssen Sie einen DNS-Eintrag (und AAAA if IPv6 Addressing wird verwendet) für pool01.contoso.com erstellen.
    
- **Interne Pin-Punkt Zone**
    
    Wenn Sie eine gesamte Zone in Ihrem internen DNS erstellen, können Sie keine PIN-Punkt-Zonen (dediziert) erstellen, die den für die automatische Konfiguration erforderlichen SRV-Einträgen entsprechen, und diese Zonen mit dnscmd.exe auffüllen. Dnscmd.exe ist erforderlich, da die DNS-Benutzeroberfläche die Erstellung von PIN-Punkt-Zonen nicht unterstützt.
    
    Wenn Ihre SIP-Domäne beispielsweise contoso.com ist und Sie über eine Front-End-Pool namens pool01 verfügen, die zwei Front-End-Server enthält, benötigen Sie die folgenden Pin-Punkt-Zonen und Datensätze im internen DNS:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Möglicherweise verfügen Sie über eine zweite SIP-Domäne in Ihrer Umgebung. In diesem Fall benötigen Sie die folgenden Pin-Punkt-Zonen und Datensätze in Ihrem internen DNS:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Sie sehen, dass die Front-End-Pool FQDN zweimal angezeigt wird, jedoch mit zwei unterschiedlichen IP-Adressen. Das liegt daran, dass DNS-Lastenausgleich verwendet wird. Wenn HLB verwendet wird, gäbe es nur einen einzigen Front-End-Pool Eintrag. 
  
> [!NOTE]
> Außerdem ändern sich die Front-End-Pool-FQDN-Werte zwischen den contoso.com-und fabrikam.com-Beispielen, aber die IP-Adressen bleiben gleich. Das liegt daran, dass Benutzer, die sich über eine der SIP-Domänen anmelden, dieselbe Front-End-Pool für die automatische Konfiguration verwenden werden. 
  
## <a name="dns-disaster-recovery"></a>DNS-Notfallwiederherstellung
<a name="DNSDR"> </a>

Sie müssen einen DNS-Anbieter verwenden, der GeoDNS unterstützt, um DNS so zu konfigurieren, dass Skype for Business Server Webdatenverkehr an Ihre Notfall Wiederherstellungs-und Failover-Websites umgeleitet wird. Sie können Ihre DNS-Einträge so einrichten, dass die Notfallwiederherstellung unterstützt wird, sodass Features, die Webdienste verwenden, auch dann fortgesetzt werden, wenn ein ganzer Front-End-Pool ausfällt. Dieses Dr-Feature unterstützt die AutoErmittlung, Besprechung und Einwahl einfache URLs.
  
Sie definieren und konfigurieren zusätzliche DNS-Host-a-Einträge (AAAA bei Verwendung von IPv6) für die interne und externe Lösung von Webdiensten bei Ihrem GeoDNS-Anbieter. Die folgenden Details setzen voraus, dass gekoppelte Pools geografisch verteilt sind und dass das GeoDNS, das von Ihrem Anbieter unterstützt wird, **entweder** Round-Robin-DNS aufweist **oder** für die Verwendung von pool1 als primäres Objekt konfiguriert ist und bei einem Kommunikationsverlust oder einem Stromausfall ein Failover auf Pool2 durchführt.
  
Beispiele hierfür sind alle DNS-Einträge in dieser Tabelle.
  
|**GeoDNS-Datensatz**|**Pool Einträge**|**CNAME-Einträge**|**DNS-Einstellungen (Wählen Sie eine Option aus)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, Verbindung mit Sekundär herstellen, wenn ein Fehler vorliegt  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, Verbindung mit Sekundär herstellen, wenn ein Fehler vorliegt  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, Verbindung mit Sekundär herstellen, wenn ein Fehler vorliegt  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, Verbindung mit Sekundär herstellen, wenn ein Fehler vorliegt  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, Verbindung mit Sekundär herstellen, wenn ein Fehler vorliegt  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, Verbindung mit Sekundär herstellen, wenn ein Fehler vorliegt  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, Verbindung mit Sekundär herstellen, wenn ein Fehler vorliegt  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, Verbindung mit Sekundär herstellen, wenn ein Fehler vorliegt  <br/> |
   
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="DNSLB"> </a>

Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert. Die Anwendung (beispielsweise ein Client, der Skype for Business ausführt) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem eine Verbindung mit einer der IP-Adressen hergestellt wird, die von der DNS-Adresse "a" und "AAAA (falls IPv6-Adressierung verwendet)" für den Pool-FQDN zurückgegeben werden.
  
Wenn beispielsweise drei Front-End-Server in einem Pool mit dem Namen "pool01.contoso.com" vorhanden sind, würde folgendes passieren:
  
- Clients, auf denen Skype for Business DNS-Abfrage für pool01.contoso.com. Die Abfrage gibt drei IP-Adressen zurück und speichert diese wie folgt (in beliebiger Reihenfolge):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Der Client versucht, eine TCP-Verbindung mit einer der IP-Adressen herzustellen. Wenn dies fehlschlägt, wird versucht, die nächste IP-Adresse, die es aus dieser Liste zwischengespeichert wird.
    
- Wenn die TCP-Verbindung erfolgreich ist, verhandelt der Client TLS, um eine Verbindung mit der primären Registrierungsstelle in pool01.contoso.com herzustellen.
    
- Wenn der Client alle zwischengespeicherten Einträge ohne erfolgreiche Verbindung versucht, erhält der Benutzer eine Benachrichtigung, dass derzeit keine Server mit Skype for Business Server zur Verfügung stehen.
    
> [!NOTE]
> DNS-basierter Lastenausgleich unterscheidet sich von DNS-Round Robin (DNS-RR), die in der Regel auf Lastenausgleich verweist, indem DNS eine andere Reihenfolge der IP-Adressen für die Server in Ihrem Pool abgibt. In der Regel ermöglicht DNS-RR die Lastenverteilung, aber Sie können das Failover nicht aktivieren. Wenn beispielsweise die Verbindung mit der einzigen IP-Adresse, die von Ihrer DNS-A-Abfrage (oder AAAA in einer IPv6-Szenario) zurückgegeben wird, fehlschlägt, tritt bei dieser Verbindung ein Fehler auf. Dadurch wird DNS-RR weniger zuverlässig als DNS-basierter Lastenausgleich. Sie können weiterhin DNS-RR in Verbindung mit dem DNS-basierten Lastenausgleich verwenden, wenn Sie dies tun müssen. 
  
Verwenden Sie den DNS-Lastenausgleich für Folgendes:
  
- Lastenausgleich für Server-zu-Server-SIP auf die Edgeserver.
    
- Lastenausgleich Unified Communication Application Services (UCAS)-Anwendungen, wie automatische Telefonzentrale für Konferenzen, Reaktionsgruppe und Parken von anrufen.
    
- Verhindern neuer Verbindungen mit UCAS-Anwendungen (auch als Entwässerung bezeichnet).
    
- Lastenausgleich für den gesamten Client-zu-Server-Datenverkehr zwischen Clients und Edge-Servern.
    
Sie können den DNS-Lastenausgleich nicht für Folgendes verwenden:
  
- Client-zu-Server-Webdatenverkehr zu Ihren Front-End-Servern oder einem Director.
    
Wenn Sie ein wenig ausführlicher darüber erfahren möchten, wie ein DNS-SRV-Eintrag ausgewählt wird, wenn mehreren-DNS-Einträge von einer Abfrage zurückgegeben werden, wählt der Zugriffs-Edgedienst den Datensatz immer mit der niedrigsten numerischen Priorität und, falls erforderlich, die höchste numerische Gewichtung aus. Dies steht im Einklang mit der [Dokumentation zum Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Wenn beispielsweise der erste DNS-SRV-Eintrag eine Gewichtung von 20 und eine Priorität von 40 hat und Ihr zweiter DNS-SRV-Eintrag eine Gewichtung von 10 und eine Priorität von 50 hat, wird der erste Datensatz ausgewählt, da er die niedrigere Priorität von 40 hat. Priorität wird immer zuerst verwendet, und dies ist der Host, den ein Client zuerst abzielt. Was geschieht, wenn zwei Ziele mit derselben Priorität vorhanden sind? 
  
In diesem Fall wird die Gewichtung berücksichtigt. Größere Gewichtungen sollten in diesem Fall mit hoher Wahrscheinlichkeit ausgewählt werden. DNS-Administratoren sollten die Gewichtung 0 verwenden, wenn keine Serverauswahl erforderlich ist. Bei vorhanden sein von Datensätzen, die die Gewichtung größer als 0 enthalten, haben Datensätze mit einer Gewichtung von 0 eine sehr geringe Chance, die Option "ausgewählt" zu holen.
  
Was geschieht also, wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden? In dieser Situation wählt der Zugriffs-Edgedienst zuerst den SRV-Eintrag aus, den er vom DNS-Server erhalten hat.
  

