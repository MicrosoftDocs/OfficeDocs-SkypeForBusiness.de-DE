---
title: Advanced Edge Server-DNS-Planung für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Zusammenfassung: Überprüfen von Szenarien für die Skype for Business Server-Bereitstellungsoptionen. Dieses Thema wird Ihnen helfen, egal ob Sie einen einzelnen Server oder einen Server-Pool mit DNS oder HLB bevorzugen.'
ms.openlocfilehash: 497126188b830a61804bedb44c5e50eedec11dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277188"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Advanced Edge Server-DNS-Planung für Skype for Business Server
 
**Zusammenfassung:** Überprüfen Sie Szenarien für die Skype for Business Server-Bereitstellungsoptionen. Dieses Thema wird Ihnen helfen, egal ob Sie einen einzelnen Server oder einen Server-Pool mit DNS oder HLB bevorzugen.
  
Wenn es um die DNS-Planung (Domain Name System) für Skype for Business Server geht, gibt es viele Faktoren, die bei ihrer Entscheidung auftreten können. Falls die Domänenstruktur Ihrer Organisation bereits aufgebaut ist, könnte es nun darum gehen, wie Sie weiter vorgehen. Wir starten mit den folgenden Punkten:
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype for Business-Clients ähneln älteren Versionen von lync-Clients in der Art und Weise, wie Sie in Skype for Business Server Dienste finden und darauf zugreifen. Der Inhalt dieses Abschnitts beschreibt das Ausfindigmachen des Servers.
  
1. lyncdiscoverinternal. \<Domäne\>
    
     *Dies ist ein Host-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten.* 
    
2. lyncdiscover. \<Domäne\>
    
     *Dies ist ein Host-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten.* 
    
3. _sipinternaltls._tcp. \<Domäne\>
    
     *Dies ist ein SRV (Service Locator)-Eintrag für interne TLS-Verbindungen* 
    
4. _sip._tls. \<Domäne\>
    
     *Dies ist ein SRV (Service Locator)-Eintrag für externe TLS-Verbindungen* 
    
5. sipinternal. \<Domäne\>
    
     *Hierbei handelt es sich um einen Hosteintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann.* 
    
6. SIP. \<Domäne\>
    
     *Hierbei handelt es sich um einen Hosteintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann.* 
    
7. sipexternal. \<Domäne\>
    
     *Hierbei handelt es sich um einen Hosteintrag für den Access Edge-Dienst, wenn der Client extern ist.* 
    
Der AutoErmittlungsdienst ist immer die bevorzugte Methode zur Dienstidentifizierung. Auf alle anderen Methoden wird nur zurückgegriffen, wenn es nicht anders geht.
  
> [!NOTE]
> Beim Erstellen von SRV-Einträgen muss berücksichtigt werden, dass die Einträge auf einen DNS-A-Eintrag (und DNS-AAAA-Eintrag, wenn Sie IPv6-Adressen nutzen) in derselben Domäne zeigen, in der der DNS-SRV-Eintrag erstellt wird. Wenn sich der SRV-Eintrag z. B. in der Domäne „contoso.com“ befindet, kann sich der A-Eintrag (und AAA-Eintrag) auf den er zeigt, nicht in der Domäne „fabrikam.com“ befinden. 
  
Es steht Ihnen frei, Ihr Mobilgerät auf die manuelle Ermittlung von Diensten einzustellen. In diesem Fall muss jeder Benutzer in den Einstellungen des mobilen Geräts wie folgt die vollständigen internen und externen AutoErmittlungsdienst-URIs konfigurieren, einschließlich Protokoll und Pfad:
  
- Für externen Zugriff: https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root
    
- Für internen Zugriff: https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root
    
Wir empfehlen das Verwenden einer automatischen Ermittlung anstelle einer manuellen Ermittlung. Falls Sie aber Fehlersuchen oder Tests durchführen, können die manuellen Einstellungen sehr hilfreich sein.
  
## <a name="split-brain-dns"></a>Split-Brain-DNS
<a name="SplitBrainDNS"> </a>

Bei dieser DNS-Konfiguration haben Sie zwei DNS-Zonen mit denselben Namespaces. Die erste DNS-Zone ist für interne Anfragen zuständig, während sich die zweite DNS-Zone um externe Anfragen kümmert.
  
Warum sollte sich ein Unternehmen dafür entscheiden? Sie könnten die Anforderung haben, denselben Namespace sowohl intern als auch extern zu verwenden. Natürlich führt dies zu vielen DNS-, SRV- und A-Einträgen, die eindeutig der einen oder der anderen Zone zugewiesen werden. Käme es zu doppelten Einträgen, so wären die mit diesen Einträgen verbundenen IP-Adressen eindeutig.
  
Dies ist mit einigen Herausforderungen verbunden. Das wichtigste ist, dass das Split-Brain-DNS für Mobilität **nicht unterstützt** wird. Der Grund dafür sind die LyncDiscover- und LyncDiscoverInternal-DNS-Einträge („LyncDiscover“ muss auf einem externen DNS-Server und „LyncDiscoverInternal“ muss auf einem internen DNS-Server definiert werden).
  
Hier werden die DNS-Einträge für die internen und externen Zonen aufgelistet, aber detaillierte Beispiele finden Sie im Abschnitt Edge Server Environmental Requirements.
  
### <a name="internal-dns"></a>Interne DNS-Konfiguration

- Enthält eine DNS-Zone namens (z. B.) „contoso.com“, für die es autoritativ ist.
    
- Die interne „contoso.com“ enthält:
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) für Ihren Front-End-Pool, Director Pool oder Director Pool Name sowie für alle internen Server, auf denen Skype for Business Server im Netzwerk Ihrer Organisation ausgeführt wird.
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) für Ihre Edge-interne Schnittstelle für jeden Skype for Business Server-Edgeserver in Ihrem Umkreisnetzwerk.
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) für die interne Schnittstelle jedes Reverse-Proxyservers in Ihrem Umkreisnetzwerk (Dies ist **optional** für die Verwaltung eines Reverse-Proxys).
    
  - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die interne Skype for Business Server-Client-Autokonfiguration ( **optional** ).
    
  - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Erkennung von Skype for Business Server-Webdiensten ( **optional** ).
    
- Alle Skype for Business Server-internen Edge-Schnittstellen in Ihrem Umkreisnetzwerk verwenden diese interne DNS-Zone zum Auflösen von Abfragen in contoso.com.
    
- Alle Server, auf denen Skype for Business Server ausgeführt wird, und Clients, auf denen Skype for Business Server im Unternehmensnetzwerk ausgeführt wird, verweisen auf interne DNS-Server zum Auflösen von Abfragen an contoso.com, oder Sie verwenden die Hostdatei auf jedem Edgeserver und Listen a und AAAA (wenn Sie IPv6 Addressing)-Einträge für den Next Hop-Server (speziell für den Director oder Director Pool VIP, Front-End-Pool VIP oder Standard Edition-Server).
    
### <a name="external-dns"></a>Externes DNS

- Enthält eine DNS-Zone namens (z. B.) „contoso.com“, für die es autoritativ ist.
    
- Die externe „contoso.com“ enthält:
    
  - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Erkennung von Skype for Business Server-Webdiensten. Dies betrifft die Nutzung für Mobilität.
    
  - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die Edge-externe Schnittstelle jedes Skype for Business Server-Edgeserver-oder Hardware Load Balanced (HLB)-VIP im Umkreisnetzwerk.
    
  - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die externe Schnittstelle des Reverse Proxyservers oder (VIP für einen Pool von Reverse-Proxyservern) im Umkreisnetzwerk.
    
  - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die Autokonfiguration des Skype for Business Server-Clients ( **optional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Automatische Konfiguration ohne Split-Brain-DNS
<a name="NoSplitBrainDNS"> </a>

Wenn Sie nicht mit dem Split-Brain-DNS arbeiten, funktioniert die interne automatische Konfiguration von Clients, die Skype for Business ausführen, nur, wenn Sie eine der hier beschriebenen Problemumgehungen verwenden. Warum funktioniert sie nicht? Da Skype for Business Server erfordert, dass der SIP-URI des Benutzers mit der Domäne des Front-End-Pools übereinstimmt, der für die automatische Konfiguration vorgesehen ist. Dies hat sich in früheren Versionen von lync Server nicht geändert.
  
Wenn Sie z. B. zwei SIP-Domänen verwenden, sind die zwei folgenden DNS-SRV-Einträge erforderlich:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Wenn sich ein Benutzer als Bob@contoso.com anmeldet, funktioniert dieser Eintrag für die automatische Konfiguration, da die SIP-Domäne des Benutzers der Domäne des Front-End-Pools (contoso.com) entspricht.* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Wenn sich ein Benutzer als Alice@fabrikam.com anmeldet, würde dieser Eintrag für die automatische Konfiguration der zweiten Domäne wieder funktionieren, da die SIP-Domäne dem Front-End-Pool für diese Domäne entspricht.* 
    
Zur weiteren Veranschaulichung sei hier ein Beispiel aufgeführt, das nicht funktioniert:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Wenn sich ein Benutzer als „tim@litwareinc.com“ anmeldet, kann sein Eintrag nicht für die automatische Konfiguration verwendet werden, da seine SIP-Domäne (litwareinc.com) nicht mit der Domäne des Pools (fabrikam.com) übereinstimmt.* 
    
Nun, da wir alles wissen, wenn Sie eine automatische Anforderung für Ihre Skype for Business-Clients ohne Split-Brain-DNS benötigen, haben Sie folgende Möglichkeiten:
  
- **Gruppenrichtlinien**
    
    Sie können Gruppenrichtlinienobjekte zum Auffüllen der richtigen Serverwerte verwenden.
    
    > [!NOTE]
    > Mit dieser Option wird die automatische Konfiguration nicht aktiviert, der Prozess der manuellen Konfiguration wird jedoch automatisiert. Daher werden die SRV-Einträge für die automatische Konfiguration bei Verwendung dieses Ansatzes nicht benötigt. 
  
- **Übereinstimmende interne Zone**
    
    Sie müssen eine Zone in Ihrem internen DNS erstellen, die ihrer externen DNS-Zone entspricht (beispielsweise contoso.com), und dann DNS a (und AAAA, wenn Sie IPv6-Adressierung verwenden), Datensätze erstellen, die dem Skype for Business-Server Pool entsprechen, der für die automatische Verwendung verwendet wird. Konfiguration.
    
    Wenn Sie beispielsweise einen Benutzer in pool01.contoso.net haben, sich aber in Skype for Business als Bob@contoso.com anmelden, erstellen Sie eine interne DNS-Zone mit dem Namen contoso.com, und in Ihr müssen Sie einen DNS-Eintrag (und AAAA, wenn IPv6-Adressierung verwendet wird) erstellen. pool01.contoso.com.
    
- **Interne dedizierte Zone**
    
    Wenn die Erstellung einer vollständigen internen DNS-Zone nicht möglich ist, können Sie dezidierte (zugeordnete) Zonen erstellen, die den für die automatische Konfiguration erforderlichen SRV-Einträgen entsprechen und diese Zonen mithilfe von „dnscmd.exe“ auffüllen. „Dnscmd.exe“ wird benötigt, da die Benutzeroberfläche für DNS das Erstellen von internen Zonen nicht unterstützt.
    
    Wenn Ihre SIP-Domäne beispielsweise contoso.com ist und Sie über einen Front-End-Pool mit dem Namen pool01 verfügen, der zwei Front-End-Server enthält, benötigen Sie die folgenden Pin-Punkt Zonen und eine Datensätze in Ihrem internen DNS:
    
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
> Sie sehen, dass der FQDN des Front-End-Pools zweimal angezeigt wird, jedoch mit zwei unterschiedlichen IP-Adressen. Das liegt daran, dass der DNS-Lastenausgleich verwendet wird. Wenn HLB verwendet wird, gibt es nur einen einzigen Front-End-Pool Eintrag. 
  
> [!NOTE]
> Außerdem ändern sich die FQDN-Werte des Front-End-Pools zwischen den contoso.com-und fabrikam.com-Beispielen, aber die IP-Adressen bleiben identisch. Das liegt daran, dass Benutzer, die sich über eine der SIP-Domänen anmelden, denselben Front-End-Pool für die automatische Konfiguration verwenden. 
  
## <a name="dns-disaster-recovery"></a>DNS-Notfallwiederherstellung
<a name="DNSDR"> </a>

Um DNS so zu konfigurieren, dass der Web-Traffic von Skype for Business Server auf Ihre Disaster Recover (Dr)-und Failover-Websites umgeleitet wird, müssen Sie einen DNS-Anbieter verwenden, der GeoDNS unterstützt. Sie können Ihre DNS-Einträge für die Unterstützung von Disaster Recovery einrichten, damit Features, die Webdienste verwenden, auch dann fortgesetzt werden, wenn ein ganzer Front-End-Pool ausfällt. Diese Notfallwiederherstellungsfunktion unterstützt AutoErmittlung, einfache URLs für Besprechungen und Einwahl.
  
Sie definieren und konfigurieren zusätzliche DNS-Host-A-Einträge (AAAA, wenn Sie IPv6 verwenden) für die interne und externe Auflösung von Webdiensten bei Ihrem GeoDNS-Anbieter. Die folgenden Beispiele gehen von kombinierten Pools aus, die geografisch zerstreut sind, sowie davon, dass Ihr Anbieter GeoDNS **entweder** mit Roundrobin-DNS unterstützt **oder** dass es für die Verwendung von Pool1 als primärem Pool und Failover nach Pool2 konfiguriert ist, falls die Kommunikation abbricht oder die Hardware ausfällt.
  
Alle DNS-Einträge in dieser Tabelle sind Beispiele.
  
|**GeoDNS-Eintrag**|**Pool-Einträge**|**CNAME-Einträge**|**DNS-Einstellungen (wählen Sie eine Option aus)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com zu Meet-int.geolb.contoso.com  <br/>   <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com zu Meet-ext.geolb.contoso.com  <br/>   <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com zu Meet-int.geolb.contoso.com   <br/>  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com zu Meet-ext.geolb.contoso.com  <br/>  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com zu Meet-int.geolb.contoso.com   <br/>   <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com zu Meet-ext.geolb.contoso.com  <br/>  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com zu Meet-int.geolb.contoso.com   <br/>  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com zu Meet-ext.geolb.contoso.com   <br/>  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäre verwenden, bei Fehler mit der sekundären verbinden  <br/> |
   
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="DNSLB"> </a>

Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert. Die Anwendung (beispielsweise ein Client, auf dem Skype for Business ausgeführt wird) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem eine Verbindung mit einer der IP-Adressen hergestellt wird, die von der DNS a-und AAAA-Daten Satz Abfrage für den Pool-FQDN zurückgegeben werden.
  
Wenn es beispielsweise drei Front-End-Server in einem Pool mit dem Namen "pool01.contoso.com" gibt, würde folgendes passieren:
  
- Clients mit Skype for Business-Abfrage-DNS für pool01.contoso.com. Die Anfrage gibt drei IP-Adressen zurück und speichert diese wie folgt im Zwischenspeicher (nicht unbedingt in dieser Reihenfolge):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Der Client versucht, eine TCP-Verbindung zu einer der IP-Adressen herzustellen. Funktioniert dies nicht, wird er es bei der nächsten auf der Liste zwischengespeicherten IP-Adresse versuchen.
    
- Bei erfolgreicher TCP-Verbindung handelt der Client die Verwendung von TLS zur Verbindungsherstellung mit der primären Registrierung in „pool01.contoso.com“ aus.
    
- Wenn der Client alle zwischengespeicherten Einträge ohne erfolgreiche Verbindung versucht, erhält der Benutzer eine Benachrichtigung, dass derzeit keine Server mit Skype for Business Server verfügbar sind.
    
> [!NOTE]
> Der DNS-basierte Lastenausgleich unterscheidet sich von DNS-Roundrobin (DNS RR). Dieser Mechanismus bezieht sich normalerweise auf einen Lastenausgleich, bei dem DNS zur Bereitstellung einer anderen Reihenfolge von IP-Adressen für die Server in einem Pool eingesetzt wird. Mit DNS RR ist üblicherweise nur ein Lastenausgleich, jedoch kein Failover möglich. Wenn z. B. die Verbindung mit der IP-Adresse, die über die DNS-A-Abfrage (oder DNS-AAAA-Abfrage, wenn Sie IPv6-Adressen nutzen) zurückgegeben wurde, nicht hergestellt werden kann, tritt für die Verbindungsherstellung ein Fehler auf. Daher ist DNS-Roundrobin allein weniger zuverlässig als der DNS-basierte Lastenausgleich. Sie können DNS-Roundrobin dennoch gemeinsam mit dem DNS-Lastenausgleich verwenden, wenn es nötig ist. 
  
Funktionen des DNS-Lastenausgleichs:
  
- Laden Sie das Server-zu-Server-SIP-Guthaben auf die Edgeserver.
    
- Lastenausgleich für Anwendungen der Unified Communications-Anwendungsdienste, z. B. automatische Konferenztelefonzentrale, Reaktionsgruppen und die Anwendung zum Parken von Anrufen.
    
- Verhindern neuer Verbindungen mit Anwendungen der Unified Communications-Anwendungsdienste (auch als „Serverausgleich“ bekannt).
    
- Lastenausgleich für den gesamten Client-zu-Server-Datenverkehr zwischen Clients und Edgeserver.
    
Keine Funktionen des DNS-Lastenausgleichs:
  
- Client-zu-Server-Webdatenverkehr zu Ihren Front-End-Servern oder einem Director.
    
Wenn Sie etwas ausführlicher darüber erfahren möchten, wie ein DNS-SRV-Eintrag ausgewählt wird, wenn Vielfaches-DNS-Einträge von einer Abfrage zurückgegeben werden, wählt der Access-Edgedienst immer den Datensatz mit der niedrigsten numerischen Priorität und, wenn ein Tie-Breaker erforderlich ist, die höchste numerische Gewichtung aus. Dies ist mit der [Internet Engineering Task Force-Dokumentation](https://www.ietf.org/rfc/rfc2782.txt)konsistent.
  
Angenommen der DNS-SRV-Eintrag A hat eine Gewichtung von 20 und eine Priorität von 40 und der DNS-SRV-Eintrag B hat eine Gewichtung von 10 und eine Priorität von 50. In diesem Fall wird der erste Eintrag ausgewählt, da er die niedrigere Priorität von 40 hat. Es kommt auf die Priorität an und den Host mit der niedrigeren steuert ein Client als erstes an. Was passiert, wenn zwei Ziele die gleiche Priorität haben? 
  
In diesem Fall kommt es dann auch die Gewichtung an. Größere Gewichtungen sollten mit proportional höherer Wahrscheinlichkeit gewählt werden. DNS-Administratoren sollten eine Gewichtung von 0 verwenden, wenn keine Serverauswahl getroffen werden muss. Wenn Server mit größeren Gewichtungen als 0 vorhanden sind, werden Einträge mit der Gewichtung 0 höchstwahrscheinlich nicht ausgewählt.
  
Was passiert also, wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden? In diesem Fall wählt der Access-Edgedienst zuerst den SRV-Eintrag aus, den er vom DNS-Server erhalten hat.
  

