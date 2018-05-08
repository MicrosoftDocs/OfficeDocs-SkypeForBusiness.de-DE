---
title: Erweiterte DNS-Edge-Server planen Skype für Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Zusammenfassung: Überprüfen Sie Szenarien für Skype für Business Server 2015 Bereitstellungsoptionen. Dieses Thema wird Ihnen helfen, egal ob Sie einen einzelnen Server oder einen Server-Pool mit DNS oder HLB bevorzugen.'
ms.openlocfilehash: 52a083f0df806d719cba2b596ded1e016c838ea8
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server-2015"></a>Erweiterte DNS-Edge-Server planen Skype für Business Server 2015
 
**Zusammenfassung:** Überprüfungsszenario für die Bereitstellungsoptionen von Skype for Business Server 2015. Dieses Thema wird Ihnen helfen, egal ob Sie einen einzelnen Server oder einen Server-Pool mit DNS oder HLB bevorzugen.
  
Wenn es darum geht, Domain Name System (DNS) Planen von Skype für Business Server 2015, gibt es viele Faktoren, die möglicherweise bei der Entscheidung wiedergegeben wird. Falls die Domänenstruktur Ihrer Organisation bereits aufgebaut ist, könnte es nun darum gehen, wie Sie weiter vorgehen. Wir starten mit den folgenden Punkten:
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype für Business-Clients sind mit früheren Versionen von Lync-Clients in ihrer suchen und Zugriff auf Dienste in Skype für Business Server 2015 vergleichbar. Der Inhalt dieses Abschnitts beschreibt das Ausfindigmachen des Servers.
  
1. Lyncdiscoverinternal. \<Domäne\>
    
     *Dies ist ein Host-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten.* 
    
2. Lyncdiscover. \<Domäne\>
    
     *Dies ist ein Host-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten.* 
    
3. _sipinternaltls. \<Domäne\>
    
     *Dies ist ein SRV (Service Locator)-Eintrag für interne TLS-Verbindungen* 
    
4. _sip. \<Domäne\>
    
     *Dies ist ein SRV (Service Locator)-Eintrag für externe TLS-Verbindungen* 
    
5. Sipinternal. \<Domäne\>
    
     *Dies ist ein A-Hosteintrag für den Front-End-Pool oder Directors, nur im internen Netzwerk aufgelöst werden.* 
    
6. SIP. \<Domäne\>
    
     *Dies ist ein A-Hosteintrag für den Front-End-Pool oder Directors, nur im internen Netzwerk aufgelöst werden.* 
    
7. Sipexternal. \<Domäne\>
    
     *Dies ist ein A-Hosteintrag für den Zugriffs-edgedienst, wenn der Client externe ist.* 
    
Der AutoErmittlungsdienst ist immer die bevorzugte Methode zur Dienstidentifizierung. Auf alle anderen Methoden wird nur zurückgegriffen, wenn es nicht anders geht.
  
> [!NOTE]
> Beim Erstellen von SRV-Einträgen muss berücksichtigt werden, dass die Einträge auf einen DNS-A-Eintrag (und DNS-AAAA-Eintrag, wenn Sie IPv6-Adressen nutzen) in derselben Domäne zeigen, in der der DNS-SRV-Eintrag erstellt wird. Wenn sich der SRV-Eintrag z. B. in der Domäne „contoso.com“ befindet, kann sich der A-Eintrag (und AAA-Eintrag) auf den er zeigt, nicht in der Domäne „fabrikam.com“ befinden. 
  
Es steht Ihnen frei, Ihr Mobilgerät auf die manuelle Ermittlung von Diensten einzustellen. In diesem Fall muss jeder Benutzer in den Einstellungen des mobilen Geräts wie folgt die vollständigen internen und externen AutoErmittlungsdienst-URIs konfigurieren, einschließlich Protokoll und Pfad:
  
- Für den externen Zugriff: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- Für den internen Zugriff: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
Wir empfehlen das Verwenden einer automatischen Ermittlung anstelle einer manuellen Ermittlung. Falls Sie aber Fehlersuchen oder Tests durchführen, können die manuellen Einstellungen sehr hilfreich sein.
  
## <a name="split-brain-dns"></a>Split-Brain-DNS
<a name="SplitBrainDNS"> </a>

Bei dieser DNS-Konfiguration haben Sie zwei DNS-Zonen mit denselben Namespaces. Die erste DNS-Zone ist für interne Anfragen zuständig, während sich die zweite DNS-Zone um externe Anfragen kümmert.
  
Warum sollte sich ein Unternehmen dafür entscheiden? Sie könnten die Anforderung haben, denselben Namespace sowohl intern als auch extern zu verwenden. Natürlich führt dies zu vielen DNS-, SRV- und A-Einträgen, die eindeutig der einen oder der anderen Zone zugewiesen werden. Käme es zu doppelten Einträgen, so wären die mit diesen Einträgen verbundenen IP-Adressen eindeutig.
  
Dies ist mit einigen Herausforderungen verbunden. Die wichtigste ist, dass Split-Brain-DNS für die Mobilität **nicht unterstützt** wird. Der Grund dafür sind die LyncDiscover- und LyncDiscoverInternal-DNS-Einträge („LyncDiscover“ muss auf einem externen DNS-Server und „LyncDiscoverInternal“ muss auf einem internen DNS-Server definiert werden).
  
Wir werden die DNS-Einträge für die internen und externen Zonen hier aufgelistet, aber finden Sie Ausführliche Beispiele auf einem Edge-Server-Abschnitt umgebungsanforderungen.
  
### <a name="internal-dns"></a>Interne DNS-Konfiguration

- Enthält eine DNS-Zone namens (z. B.) „contoso.com“, für die es autoritativ ist.
    
- Die interne „contoso.com“ enthält:
    
  - DNS-A und AAAA (Wenn Sie IPv6-Adressen nutzen) Einträge für den Front-End-Pool, Director-Pool oder Director-Pool-Name und alle internen Server Skype für Business Server 2015 im Netzwerk Ihrer Organisation ausgeführt.
    
  - DNS-A und AAAA (Wenn Sie IPv6-Adressen nutzen) Einträge für die interne Schnittstelle des Edgeservers für jede Skype für Business Server 2015 Edge-Server im Umkreisnetzwerk.
    
  - DNS-A und AAAA (Wenn Sie IPv6-Adressen nutzen) Einträge für die interne Schnittstelle der einzelnen Reverseproxyserver im Umkreisnetzwerk (die **optional** für einen Reverseproxy ist).
    
  - DNS-A und AAAA (Wenn Sie IPv6-Adressen nutzen) und SRV-Einträge für interne Skype für die automatische Clientkonfiguration Business Server 2015-Client (die **optional** ist).
    
  - DNS-A und AAAA (Wenn Sie IPv6-Adressen nutzen) oder CNAME-Einträge für die automatische Ermittlung von Skype für Business Server 2015-Webdienste (die **optional** ist).
    
- Alle Ihre Skype für Business Server 2015 internen edgeschnittstellen in Ihrem Umkreisnetzwerk Verwenden dieser internen DNS-Zone zum Auflösen von Abfragen in "contoso.com".
    
- Alle Server mit Skype für Business Server 2015 und Clients, auf denen Skype für Business Server 2015 im Unternehmensnetzwerk, zeigen Sie auf der internen DNS-Server, um die Abfragen an "contoso.com", oder verwenden sie die Hostdatei auf jedem Edgeserver und Liste A und AAAA, wenn ( Verwenden Sie IPv6-Adressen) Datensätze für den nächsten Hopserver (speziell für den Director oder Director-Pool-VIP, Front-End-Pool-VIP oder Standard Edition-Server).
    
### <a name="external-dns"></a>Externes DNS

- Enthält eine DNS-Zone namens (z. B.) „contoso.com“, für die es autoritativ ist.
    
- Die externe „contoso.com“ enthält:
    
  - DNS-A und AAAA (Wenn Sie IPv6-Adressen nutzen) oder CNAME aufgezeichnet, für die automatische Ermittlung von Skype für Business Server 2015-Webdienste. Dies betrifft die Nutzung für Mobilität.
    
  - DNS-A und AAAA (Wenn Sie IPv6-Adressen nutzen) und SRV-Einträge für die externe edgeschnittstelle der einzelnen Skype für Business Server 2015 Edge-Server oder Hardwaregerät zum Lastenausgleich (Hardwarelastenausgleich) VIP-Adresse im Umkreisnetzwerk.
    
  - DNS-A- und DNS-AAAA (Wenn Sie IPv6-Adressen nutzen) und SRV-Einträge für die externe Schnittstelle des Reverseproxyservers oder (VIP-Adresse für einen Pool von Reverse-Proxyserver), im Umkreisnetzwerk.
    
  - DNS-A und AAAA (Wenn Sie IPv6-Adressen nutzen) und SRV-Einträge für Skype für Business Server 2015 Automatische-Clientkonfiguration (**optional**).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Automatische Konfiguration ohne Split-Brain-DNS
<a name="NoSplitBrainDNS"> </a>

Wenn Sie Split-Brain-DNS nicht verwenden, interne automatische Konfiguration von Clients, auf denen Skype für Unternehmen, funktionieren nicht, wenn Sie eine der Methoden verwenden, die wir hier haben. Warum funktioniert sie nicht? Da Skype für Business Server 2015 SIP-URI des Benutzers entsprechend die Domäne des Front-End-Pools festgelegt werden, damit die automatische Konfiguration erforderlich ist. Dies noch nicht von früheren Versionen von Lync Server geändert.
  
Wenn Sie z. B. zwei SIP-Domänen verwenden, sind die zwei folgenden DNS-SRV-Einträge erforderlich:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Wenn ein Benutzer als bob@contoso.com anmeldet, funktioniert dieser Eintrag für die automatische Konfiguration wie der Benutzer-SIP-Domäne der Domäne des Front-End-Pools (contoso.com) entspricht.* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Wenn ein Benutzer als alice@fabrikam.com anmeldet, funktioniert dieser Eintrag für die automatische Konfiguration der zweiten Domäne erneut, da die SIP-Domäne den Front-End-Pool für diese Domäne übereinstimmt.* 
    
Zur weiteren Veranschaulichung sei hier ein Beispiel aufgeführt, das nicht funktioniert:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Wenn sich ein Benutzer als „tim@litwareinc.com“ anmeldet, kann sein Eintrag nicht für die automatische Konfiguration verwendet werden, da seine SIP-Domäne (litwareinc.com) nicht mit der Domäne des Pools (fabrikam.com) übereinstimmt.* 
    
Nun, wir all dies erkennen, ob die automatische Anforderung für Ihre Skype für Business Clients ohne Split-Brain DNS erforderlich sind, müssen Sie also diese Optionen:
  
- **Gruppenrichtlinien**
    
    Sie können Gruppenrichtlinienobjekte zum Auffüllen der richtigen Serverwerte verwenden.
    
    > [!NOTE]
    > Mit dieser Option wird die automatische Konfiguration nicht aktiviert, der Prozess der manuellen Konfiguration wird jedoch automatisiert. Daher werden die SRV-Einträge für die automatische Konfiguration bei Verwendung dieses Ansatzes nicht benötigt. 
  
- **Übereinstimmende interne Zone**
    
    Sie benötigen, erstellen Sie eine Zone in Ihren internen DNS-Server, die mit externe DNS-Zone (zum Beispiel: contoso.com) übereinstimmt, und erstellen Sie DNS-A (und AAAA, wenn Sie IPv6-Adressen nutzen) Datensätze, die die Skype für Business Server 2015-Pools für automatische entsprechen, Konfiguration.
    
    Beispielsweise wenn Sie haben ein Benutzer, die sich in pool01.contoso.net, jedoch auf Anzeichen für in Skype für Business als bob@contoso.com, erstellen Sie eine interne DNS-Zone "contoso.com" aufgerufen und darin, den Sie zum Erstellen einer DNS-A (und AAAA Wenn IPv6-Adressen verwendet wird) müssen für aufzeichnen "pool01.contoso.com".
    
- **Interne dedizierte Zone**
    
    Wenn die Erstellung einer vollständigen internen DNS-Zone nicht möglich ist, können Sie dezidierte (zugeordnete) Zonen erstellen, die den für die automatische Konfiguration erforderlichen SRV-Einträgen entsprechen und diese Zonen mithilfe von „dnscmd.exe“ auffüllen. „Dnscmd.exe“ wird benötigt, da die Benutzeroberfläche für DNS das Erstellen von internen Zonen nicht unterstützt.
    
    Beispielsweise wenn Ihre SIP-Domäne "contoso.com" ist und Sie haben einen Front-End-Pool aufgerufen pool01, die beiden Front-End-Server enthält, benötigen die folgenden Zonen für die Pin-Nummer und A-Einträge im internen DNS Sie Folgendes:
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Wenn Ihre Umgebung eine zweite SIP-Domäne enthält, benötigen Sie die folgenden dedizierten Zonen und DNS-A-Einträge in Ihrem internen DNS:
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Sie sehen den Front-End-Pool FQDN zweimal, jedoch mit zwei verschiedenen IP-Adressen angezeigt wird. Dies liegt daran DNS-Lastenausgleich verwendet wird. Wenn Hardwaregeräts zum Lastenausgleich verwendet wird, sind vorhanden nur ein einzelner Eintrag des Front-End-Pool. 
  
> [!NOTE]
> Darüber hinaus die Front-End-Pool-FQDN-Werte zwischen den Beispielen contoso.com und fabrikam.com ändern, aber die IP-Adressen, bleiben unverändert. Dies liegt daran Benutzer, die entweder SIP-Domäne anmelden sind den gleichen Front-End-Pool für die automatische Konfiguration verwenden werden. 
  
## <a name="dns-disaster-recovery"></a>DNS-Notfallwiederherstellung
<a name="DNSDR"> </a>

Zum Konfigurieren von DNS, um Skype für Business Server 2015 Webdatenverkehr zu Ihrer Disaster Recovery (DR) und Failover Websites umzuleiten, müssen Sie einen DNS-Anbieter verwenden, der GeoDNS unterstützt. Sie können Ihren DNS-Datensätzen einrichten zur Unterstützung von Disaster Recovery, sodass Features, die Webdienste verwenden fortgesetzt, auch wenn eine gesamte Front-End-Pool ausfällt. Diese Notfallwiederherstellungsfunktion unterstützt AutoErmittlung, einfache URLs für Besprechungen und Einwahl.
  
Sie definieren und konfigurieren zusätzliche DNS-Host-A-Einträge (AAAA, wenn Sie IPv6 verwenden) für die interne und externe Auflösung von Webdiensten bei Ihrem GeoDNS-Anbieter. Die folgenden Beispiele gehen von kombinierten Pools aus, die geografisch zerstreut sind, sowie davon, dass Ihr Anbieter GeoDNS **entweder** mit Roundrobin-DNS unterstützt **oder** dass es für die Verwendung von Pool1 als primärem Pool und Failover nach Pool2 konfiguriert ist, falls die Kommunikation abbricht oder die Hardware ausfällt.
  
Alle DNS-Einträge in dieser Tabelle sind Beispiele.
  
|**GeoDNS-Datensatz**|**Pooldatensätze**|**CNAME-Einträge**|**DNS-Einstellungen (Wählen Sie eine Option aus)**|
|:-----|:-----|:-----|:-----|
|Sofortbesprechung int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Sofortbesprechung ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Lyncdiscoverint int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Lyncdiscover ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
   
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="DNSLB"> </a>

DNS-Lastenausgleich wird in der Regel auf der Anwendungsebene implementiert. Die Anwendung (beispielsweise in einem Client unter Skype für Unternehmen), versucht, Verbindung mit einem Server in einem Pool eine Verbindung zu einer IP-Adressen zurückgegeben, die von den DNS-A und AAAA (Wenn IPv6-Adressen verwendet wird) Abfrage für den Pool-FQDN aufzeichnen.
  
Beispielsweise wenn drei Front-End-Servern in einem Pool mit dem Namen "pool01.contoso.com" vorhanden sind, Folgendes geschieht:
  
- Clients, auf denen Skype für Unternehmen DNS-Abfrage für "pool01.contoso.com". Die Abfrage gibt drei IP-Adressen und speichert diese wie folgt (in einigen Reihenfolge):
    
   |||
   |:-----|:-----|
   |"pool01.contoso.com"  <br/> |192.168.10.90  <br/> |
   |"pool01.contoso.com"  <br/> |192.168.10.91  <br/> |
   |"pool01.contoso.com"  <br/> |192.168.10.92  <br/> |
   
- Der Client versucht, eine TCP-Verbindung zu einer der IP-Adressen herzustellen. Funktioniert dies nicht, wird er es bei der nächsten auf der Liste zwischengespeicherten IP-Adresse versuchen.
    
- Bei erfolgreicher TCP-Verbindung handelt der Client die Verwendung von TLS zur Verbindungsherstellung mit der primären Registrierung in „pool01.contoso.com“ aus.
    
- Wenn der Client keinem der zwischengespeicherten Einträge eine Verbindung versucht, erhält der Benutzer eine Benachrichtigung, dass gegenwärtig keine Server mit Skype für Business Server 2015 verfügbar sind.
    
> [!NOTE]
> Der DNS-basierte Lastenausgleich unterscheidet sich von DNS-Roundrobin (DNS RR). Dieser Mechanismus bezieht sich normalerweise auf einen Lastenausgleich, bei dem DNS zur Bereitstellung einer anderen Reihenfolge von IP-Adressen für die Server in einem Pool eingesetzt wird. Mit DNS RR ist üblicherweise nur ein Lastenausgleich, jedoch kein Failover möglich. Wenn z. B. die Verbindung mit der IP-Adresse, die über die DNS-A-Abfrage (oder DNS-AAAA-Abfrage, wenn Sie IPv6-Adressen nutzen) zurückgegeben wurde, nicht hergestellt werden kann, tritt für die Verbindungsherstellung ein Fehler auf. Daher ist DNS-Roundrobin allein weniger zuverlässig als der DNS-basierte Lastenausgleich. Sie können DNS-Roundrobin dennoch gemeinsam mit dem DNS-Lastenausgleich verwenden, wenn es nötig ist. 
  
Funktionen des DNS-Lastenausgleichs:
  
- Lastenausgleich Server-zu-Server-SIP an den Edge-Servern.
    
- Lastenausgleich für Anwendungen der Unified Communications-Anwendungsdienste, z. B. automatische Konferenztelefonzentrale, Reaktionsgruppen und die Anwendung zum Parken von Anrufen.
    
- Verhindern neuer Verbindungen mit Anwendungen der Unified Communications-Anwendungsdienste (auch als „Serverausgleich“ bekannt).
    
- Lastenausgleich alle Client-zu-Server-Datenverkehr zwischen Clients und Edge-Server.
    
Keine Funktionen des DNS-Lastenausgleichs:
  
- -Client-zu-Server-Webdatenverkehr an den Front-End-Servern oder eines Directors.
    
Gehen Sie etwas ausführlicheren auf einen DNS-SRV-Eintrag wie ausgewählt, mehrerer-DNS-Datensätze von einer Abfrage, die Zugriffs-edgedienst immer zurückgegeben werden Record-Objekts mit der niedrigsten numerischen Priorität auswählt und Lösen von Konflikten ist erforderlich, numerische Gewichtung. Dies entspricht der [Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt)-Dokumentation.
  
Angenommen der DNS-SRV-Eintrag A hat eine Gewichtung von 20 und eine Priorität von 40 und der DNS-SRV-Eintrag B hat eine Gewichtung von 10 und eine Priorität von 50. In diesem Fall wird der erste Eintrag ausgewählt, da er die niedrigere Priorität von 40 hat. Es kommt auf die Priorität an und den Host mit der niedrigeren steuert ein Client als erstes an. Was passiert, wenn zwei Ziele die gleiche Priorität haben? 
  
In diesem Fall kommt es dann auch die Gewichtung an. Größere Gewichtungen sollten mit proportional höherer Wahrscheinlichkeit gewählt werden. DNS-Administratoren sollten eine Gewichtung von 0 verwenden, wenn keine Serverauswahl getroffen werden muss. Wenn Server mit größeren Gewichtungen als 0 vorhanden sind, werden Einträge mit der Gewichtung 0 höchstwahrscheinlich nicht ausgewählt.
  
Was passiert also, wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden? In diesem Fall der Zugriffs-Edgeserver wird Service den SRV-Eintrag auswählen, den es von der DNS-Server erste erhalten haben.
  

