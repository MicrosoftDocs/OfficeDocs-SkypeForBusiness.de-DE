---
title: Erweiterte Edgeserver-DNS-Planung für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: Zeigen Sie Szenarien für Skype for Business Server Bereitstellungsoptionen an. Unabhängig davon, ob Sie einen einzelnen Server wünschen oder einen Serverpool mit DNS oder HLB bevorzugen, sollte dieses Thema hilfreich sein.
ms.openlocfilehash: 208098fe44238d9d96debbde7b8c00daf6622b91
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602350"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Erweiterte Edgeserver-DNS-Planung für Skype for Business Server
 
**Zusammenfassung:** Überprüfen Sie Szenarien für Skype for Business Server Bereitstellungsoptionen. Unabhängig davon, ob Sie einen einzelnen Server wünschen oder einen Serverpool mit DNS oder HLB bevorzugen, sollte dieses Thema hilfreich sein.
  
Wenn es um die Planung des Domain Name System (DNS) für Skype for Business Server geht, können viele Faktoren bei Ihrer Entscheidung eine Rolle spielen. Wenn die Domänenstruktur Ihrer Organisation bereits vorhanden ist, kann es darum gehen, zu überprüfen, wie Sie fortfahren. Wir beginnen mit den folgenden Themen:
  
- [Exemplarische Vorgehensweise für Skype for Business Clients, die Dienste suchen](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS-Notfallwiederherstellung](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Exemplarische Vorgehensweise für Skype for Business Clients, die Dienste suchen
<a name="WalkthroughOfSkype"> </a>

Skype for Business-Clients ähneln früheren Versionen von Lync-Clients in der Art und Weise, wie sie Dienste in Skype for Business Server finden und darauf zugreifen. In diesem Abschnitt wird der Serverspeicherortprozess beschrieben.
  
1. lyncdiscoverinternal.\<domain\>
    
     *Dies ist ein Hostdatensatz für den AutoErmittlungsdienst in den internen Webdiensten.* 
    
2. lyncdiscover.\<domain\>
    
     *Dies ist ein Hostdatensatz für den AutoErmittlungsdienst in den externen Webdiensten.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *Dies ist ein SRV-Eintrag für interne TLS-Verbindungen.* 
    
4. _sip._tls.\<domain\>
    
     *Dies ist ein SRV-Eintrag für externe TLS-Verbindungen.* 
    
5. sipinternal.\<domain\>
    
     *Dies ist ein Hosteintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann.* 
    
6. Sip.\<domain\>
    
     *Dies ist ein Hosteintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann.* 
    
7. sipexternal.\<domain\>
    
     *Dies ist ein Hosteintrag für den Zugriffs-Edgedienst, wenn der Client extern ist.* 
    
Der AutoErmittlungsdienst wird immer bevorzugt, da dies die bevorzugte Methode für den Dienstspeicherort ist, und die anderen sind Fallbackmethoden.
  
> [!NOTE]
> Beim Erstellen von SRV-Einträgen ist es wichtig zu beachten, dass diese auf ein DNS A (und AAAA, wenn Sie IPv6-Adressen verwenden) in derselben Domäne verweisen müssen, in der der DNS-SRV-Eintrag erstellt wird. Wenn sich der SRV-Eintrag z. B. in contoso.com befindet, kann sich der A-Eintrag (und AAAA), auf den er verweist, nicht in fabrikam.com befinden. 
  
Wenn Sie geneigt sind, dies zu tun, können Sie Ihr mobiles Gerät für die manuelle Ermittlung von Diensten einrichten. Wenn Sie dies tun möchten, muss jeder Benutzer seine Einstellungen für mobile Geräte wie folgt mit den vollständigen internen und externen AutoErmittlungsdienst-URIs einschließlich Protokoll und Pfad konfigurieren:
  
- Für externen Zugriff: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- Für internen Zugriff: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
Es wird empfohlen, die automatische Ermittlung im Gegensatz zur manuellen Ermittlung zu verwenden. Wenn Sie jedoch einige Problembehandlungen oder Tests durchführen, können manuelle Einstellungen hilfreich sein.
  
## <a name="split-brain-dns"></a>Split-Brain-DNS
<a name="SplitBrainDNS"> </a>

Hierbei handelt es sich um eine DNS-Konfiguration, bei der Sie über zwei DNS-Zonen mit demselben Namespace verfügen. Die erste DNS-Zone verarbeitet interne Anforderungen, während die zweite DNS-Zone externe Anforderungen verarbeitet.
  
Warum sollte ein Unternehmen dies tun? Möglicherweise müssen sie denselben Namespace intern und extern verwenden. Dies führt natürlich dazu, dass viele DNS-SRV- und A-Einträge für eine zone oder eine andere Zone eindeutig sind, und wenn dupliziert wird, sind die diesen Einträgen zugeordneten IP-Adressen eindeutig.
  
Diese Situation stellt einige Herausforderungen dar. Das Wichtigste ist, dass Split-Brain-DNS für Mobilität **nicht unterstützt** wird. Dies liegt an den LYNCDiscover- und LyncDiscoverInternal-DNS-Einträgen (LyncDiscover muss auf Ihrem externen DNS-Server definiert werden, während LyncDiscoverInternal auf Ihrem internen DNS-Server definiert werden muss).
  
Hier werden die DNS-Einträge für die internen und externen Zonen aufgelistet. Detaillierte Beispiele finden Sie jedoch im Abschnitt zu den Umgebungsanforderungen des Edgeservers.
  
### <a name="internal-dns"></a>Interne DNS-Konfiguration

- Enthält eine DNS-Zone namens (z. B. ) contoso.com, für die sie autoritativ ist.
    
- Diese interne contoso.com enthält Folgendes:
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) für Ihren Front-End-Pool, Directorpool oder Director-Poolnamen und alle internen Server, die Skype for Business Server im Netzwerk Ihrer Organisation ausgeführt werden.
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) für ihre interne Edgeschnittstelle für jeden Skype for Business Server Edgeservers in Ihrem Umkreisnetzwerk.
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) für die interne Schnittstelle jedes Reverseproxyservers in Ihrem Umkreisnetzwerk **(optional** für die Verwaltung eines Reverseproxys).
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) und SRV-Einträge für interne Skype for Business Server Client-Autokonfiguration **(optional).**
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) oder CNAME-Einträge für die automatische Ermittlung von Skype for Business Server Webdiensten **(optional).**
    
- Alle ihre Skype for Business Server internen Edgeschnittstellen in Ihrem Umkreisnetzwerk verwenden diese interne DNS-Zone zum Auflösen von Abfragen an contoso.com.
    
- Alle Server, auf denen Skype for Business Server ausgeführt wird, und Clients, die Skype for Business Server im Unternehmensnetzwerk ausführen, verweisen auf interne DNS-Server zum Auflösen von Abfragen an contoso.com, oder sie verwenden die Hostdatei auf jedem Edgeserver und listen A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) für den nächsten Hopserver (speziell für die Director- oder Directorpool-VIP, die Front-End-Pool-VIP oder Standard Edition-Server) auf.
    
### <a name="external-dns"></a>Externes DNS

- Enthält eine DNS-Zone namens (z. B. ) contoso.com, für die sie autoritativ ist.
    
- Diese externe contoso.com enthält Folgendes:
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) oder CNAME-Einträge für die automatische Ermittlung von Skype for Business Server Webdiensten. Dies ist für die Verwendung mit Mobilität vorgesehen.
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) und SRV-Einträge für die externe Edgeschnittstelle jedes Skype for Business Server Edgeservers oder HLB-VIP (Hardware Load Balanced) im Umkreisnetzwerk.
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) und SRV-Einträge für die externe Schnittstelle des Reverseproxyservers oder (VIP für einen Pool von Reverseproxyservern) im Umkreisnetzwerk.
    
  - DNS A- und AAAA-Einträge (wenn Sie IPv6-Adressen verwenden) und SRV-Einträge für Skype for Business Server Client-Autokonfiguration ( **optional).**
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Automatische Konfiguration ohne Split-Brain-DNS
<a name="NoSplitBrainDNS"> </a>

Wenn Sie split-brain DNS nicht verwenden, funktioniert die interne automatische Konfiguration von Clients, die Skype for Business ausgeführt werden, nur, wenn Sie eine der hier aufgeführten Problemumgehungen verwenden. Warum nicht? Da Skype for Business Server erfordert, dass der SIP-URI des Benutzers mit der Domäne des Front-End-Pools übereinstimmt, der für die automatische Konfiguration vorgesehen ist. Dies hat sich gegenüber früheren Versionen von Lync Server nicht geändert.
  
Wenn Sie also zwei SIP-Domänen verwenden, benötigen Sie diese DNS-SRV-Einträge:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Wenn sich ein Benutzer als bob@contoso.com anmeldet, funktioniert dieser Eintrag für die automatische Konfiguration, da die SIP-Domäne des Benutzers mit der Domäne des Front-End-Pools (contoso.com) übereinstimmt.* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Wenn sich ein Benutzer als alice@fabrikam.com anmeldet, funktioniert dieser Eintrag für die automatische Konfiguration der zweiten Domäne, da die SIP-Domäne mit dem Front-End-Pool für diese Domäne übereinstimmt.* 
    
Um das Beispiel weiter zu verwenden, würde dies nicht funktionieren:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Ein Benutzer, der sich als tim@litwareinc.com anmeldet, funktioniert nicht für die automatische Konfiguration, da seine SIP-Domäne (litwareinc.com) nicht mit der Domäne im Pool (fabrikam.com) übereinstimmt.* 
    
Wenn Sie also eine automatische Anforderung für Ihre Skype for Business-Clients ohne Split-Brain-DNS benötigen, haben Sie folgende Optionen:
  
- **Gruppenrichtlinienobjekte**
    
    Sie können Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) verwenden, um die richtigen Serverwerte aufzufüllen.
    
    > [!NOTE]
    > Mit dieser Option wird die automatische Konfiguration nicht aktiviert, die manuelle Konfiguration wird jedoch automatisiert. Wenn dieser Ansatz verwendet wird, sind die der automatischen Konfiguration zugeordneten SRV-Einträge nicht erforderlich. 
  
- **Übereinstimmende interne Zone**
    
    Sie müssen eine Zone in Ihrem internen DNS erstellen, die ihrer externen DNS-Zone entspricht (z. B. contoso.com), und dann DNS A-Einträge (und AAAA, wenn Sie IPv6-Adressen verwenden) erstellen, die dem Skype for Business Server Pool entsprechen, der für die automatische Konfiguration verwendet wird.
    
    Wenn Sie beispielsweise einen Benutzer auf pool01.contoso.net verwaltet haben, sich jedoch als bob@contoso.com bei Skype for Business anmelden, erstellen Sie eine interne DNS-Zone mit dem Namen contoso.com, und erstellen Sie darin einen DNS A-Eintrag (und AAAA, wenn die IPv6-Adresse verwendet wird) für pool01.contoso.com.
    
- **Interne Pin-Punkt-Zone**
    
    Wenn das Erstellen einer vollständigen Zone in Ihrem internen DNS keine Option für Sie ist, können Sie Pinpunktzonen (dedizierte) Zonen erstellen, die den für die automatische Konfiguration erforderlichen SRV-Einträgen entsprechen, und diese Zonen mit dnscmd.exe auffüllen. Dnscmd.exe ist erforderlich, da die DNS-Benutzeroberfläche die Erstellung von Pin-Point-Zonen nicht unterstützt.
    
    Wenn Ihre SIP-Domäne beispielsweise contoso.com ist und Sie über einen Front-End-Pool namens "pool01" verfügen, der zwei Front-End-Server enthält, benötigen Sie die folgenden Pin-Point-Zonen und A-Einträge in Ihrem internen DNS:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Möglicherweise befindet sich eine zweite SIP-Domäne in Ihrer Umgebung. In diesem Fall benötigen Sie die folgenden Pin-Point-Zonen und A-Einträge in Ihrem internen DNS:
    
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
> Der FQDN des Front-End-Pools wird zweimal angezeigt, jedoch mit zwei verschiedenen IP-Adressen. Der Grund dafür ist, dass der DNS-Lastenausgleich verwendet wird. Wenn HLB verwendet wird, gibt es nur einen einzigen Front-End-Pooleintrag. 
  
> [!NOTE]
> Außerdem ändern sich die FQDN-Werte des Front-End-Pools zwischen dem contoso.com und fabrikam.com Beispielen, aber die IP-Adressen bleiben gleich. Der Grund dafür ist, dass Benutzer, die sich von einer der SIP-Domänen anmelden, den gleichen Front-End-Pool für die automatische Konfiguration verwenden. 
  
## <a name="dns-disaster-recovery"></a>DNS-Notfallwiederherstellung
<a name="DNSDR"> </a>

Um DNS so zu konfigurieren, dass Skype for Business Server Webdatenverkehr an Ihre Notfallwiederherstellungs- und Failoverwebsites umgeleitet wird, müssen Sie einen DNS-Anbieter verwenden, der GeoDNS unterstützt. Sie können Ihre DNS-Einträge so einrichten, dass die Notfallwiederherstellung unterstützt wird, sodass Features, die Webdienste verwenden, auch dann fortgesetzt werden, wenn ein ganzer Front-End-Pool ausfällt. Dieses Dr-Feature unterstützt die einfachen URLs für AutoErmittlung, Besprechung und Einwahl.
  
Sie definieren und konfigurieren zusätzliche DNS-Host-A-Einträge (AAAA bei Verwendung von IPv6)-Einträgen für die interne und externe Auflösung von Webdiensten bei Ihrem GeoDNS-Anbieter. In den folgenden Details wird davon ausgegangen, dass gepaarte Pools geografisch verteilt sind und dass der von Ihrem Anbieter unterstützte GeoDNS **entweder** über Roundrobin-DNS **verfügt oder** für die Verwendung von Pool1 als primärer Pool konfiguriert ist und bei Kommunikationsverlust oder Stromausfällen zu Pool2 übergeht.
  
Alle DNS-Einträge in dieser Tabelle sind Beispiele.
  
|**GeoDNS-Eintrag**|**Pooldatensätze**|**CNAME-Einträge**|**DNS-Einstellungen (wählen Sie eine Option aus)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Alias für Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **OR** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundärer Verbindung, wenn ein Fehler auftritt  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **OR** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundärer Verbindung, wenn ein Fehler auftritt  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com Alias für Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **OR** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundärer Verbindung, wenn ein Fehler auftritt  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **OR** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundärer Verbindung, wenn ein Fehler auftritt  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **OR** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundärer Verbindung, wenn ein Fehler auftritt  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com Alias für Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **OR** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundärer Verbindung, wenn ein Fehler auftritt  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com Alias für Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com Alias für Pool2InternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **OR** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundärer Verbindung, wenn ein Fehler auftritt  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com Alias für Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **OR** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundärer Verbindung, wenn ein Fehler auftritt  <br/> |
   
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="DNSLB"> </a>

Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert. Die Anwendung (z. B. ein Client, auf dem Skype for Business ausgeführt wird) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem eine Verbindung mit einer der IP-Adressen hergestellt wird, die von der DNS A- und AAAA-Eintragsabfrage (wenn IPv6-Adressen verwendet werden) für den Pool-FQDN zurückgegeben werden.
  
Wenn beispielsweise drei Front-End-Server in einem Pool mit dem Namen pool01.contoso.com vorhanden sind, würde Folgendes passieren:
  
- Clients, die Skype for Business Dns für pool01.contoso.com abfragen. Die Abfrage gibt drei IP-Adressen zurück und speichert sie wie folgt (in einer bestimmten Reihenfolge):
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Der Client versucht, eine TCP-Verbindung mit einer der IP-Adressen herzustellen. Wenn dies fehlschlägt, wird die nächste IP-Adresse versucht, die in dieser Liste zwischengespeichert wird.
    
- Wenn die TCP-Verbindung erfolgreich ist, handelt der Client TLS aus, um eine Verbindung mit der primären Registrierungsstelle auf pool01.contoso.com herzustellen.
    
- Wenn der Client alle zwischengespeicherten Einträge ohne erfolgreiche Verbindung versucht, erhält der Benutzer eine Benachrichtigung, dass derzeit keine Server verfügbar sind, auf denen Skype for Business Server ausgeführt werden.
    
> [!NOTE]
> Der DNS-basierte Lastenausgleich unterscheidet sich vom DNS-Roundrobin (DNS RR), der sich in der Regel auf den Lastenausgleich bezieht, indem dns verwendet wird, um eine andere Reihenfolge von IP-Adressen für die Server in Ihrem Pool zu geben. In der Regel ermöglicht DNS-RR die Lastverteilung, aber kein Failover. Wenn beispielsweise die Verbindung mit der ip-Adresse, die von Ihrer DNS A-Abfrage (oder AAAA in einem IPv6-Szenario) zurückgegeben wird, fehlschlägt, schlägt diese Verbindung fehl. Dies macht DNS RR weniger zuverlässig als DNS-basierten Lastenausgleich. Sie können dns-RR weiterhin in Verbindung mit dnsbasiertem Lastenausgleich verwenden, wenn Sie dies tun müssen. 
  
Sie verwenden den DNS-Lastenausgleich für Folgendes:
  
- Lastenausgleich von Server-zu-Server-SIP zu den Edgeservern.
    
- Load balance Unified Communication Application Services (UCS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.
    
- Verhindern neuer Verbindungen mit UCS-Anwendungen (auch als Entleeren bezeichnet).
    
- Lastenausgleich für den gesamten Client-zu-Server-Datenverkehr zwischen Clients und Edgeservern.
    
Sie können den DNS-Lastenausgleich nicht für Folgendes verwenden:
  
- Client-zu-Server-Webdatenverkehr zu Ihren Front-End-Servern oder einem Director.
    
Um etwas ausführlicher zu erfahren, wie ein DNS-SRV-Eintrag ausgewählt wird, wenn mehrere DNS-Einträge von einer Abfrage zurückgegeben werden, wählt der Zugriffs-Edgedienst immer den Eintrag mit der niedrigsten numerischen Priorität und, wenn ein Tiebreaker erforderlich ist, die höchste numerische Gewichtung aus. Dies entspricht der Dokumentation der [Internet Engineering Task Force.](https://www.ietf.org/rfc/rfc2782.txt)
  
Wenn Ihr erster DNS-SRV-Eintrag beispielsweise eine Gewichtung von 20 und eine Priorität von 40 hat und Ihr zweiter DNS-SRV-Eintrag eine Gewichtung von 10 und eine Priorität von 50 hat, wird der erste Eintrag ausgewählt, da er die niedrigere Priorität von 40 hat. Priorität wird immer an erster Stelle, und dies ist der Host, auf den ein Client zuerst ausgerichtet wird. Was geschieht, wenn zwei Ziele mit derselben Priorität vorhanden sind? 
  
In diesem Fall wird die Gewichtung berücksichtigt. Größere Gewichtungen sollten unter diesen Umständen mit hoher Wahrscheinlichkeit ausgewählt werden. DNS-Administratoren sollten die Gewichtung 0 verwenden, wenn keine Serverauswahl erforderlich ist. Wenn Datensätze mit einer Gewichtung größer als 0 vorhanden sind, haben Datensätze mit der Gewichtung 0 eine sehr geringe Wahrscheinlichkeit, dass sie ausgewählt werden.
  
Was geschieht also, wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung wie zurückgegeben werden? In diesem Fall wählt der Zugriffs-Edgedienst zuerst den SRV-Eintrag aus, den er vom DNS-Server erhalten hat.
  

