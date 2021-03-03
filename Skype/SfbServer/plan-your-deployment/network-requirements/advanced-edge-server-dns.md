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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Zusammenfassung: Überprüfen Sie Szenarien für Skype for Business Server-Bereitstellungsoptionen. Unabhängig davon, ob Sie einen einzelnen Server oder einen Serverpool mit DNS oder HLB bevorzugen, sollte dieses Thema hilfreich sein.'
ms.openlocfilehash: 5a41baac30f3bf6a1e20ae34db009dae0cec40af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825325"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Erweiterte Edgeserver-DNS-Planung für Skype for Business Server
 
**Zusammenfassung:** Überprüfen Sie Szenarien für Skype for Business Server-Bereitstellungsoptionen. Unabhängig davon, ob Sie einen einzelnen Server oder einen Serverpool mit DNS oder HLB bevorzugen, sollte dieses Thema hilfreich sein.
  
Wenn es um die Planung des Domain Name System (DNS) für Skype for Business Server geht, gibt es viele Faktoren, die bei Ihrer Entscheidung eine Rolle spielen können. Wenn die Domänenstruktur Ihrer Organisation bereits vorhanden ist, müssen Sie möglicherweise überprüfen, wie Sie fortfahren werden. Wir beginnen mit den folgenden Themen:
  
- [Exemplarische Vorgehensweise zum Suchen von Diensten durch Skype for Business-Clients](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatische Konfiguration ohne Split-Brain-DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS-Notfallwiederherstellung](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS-Lastenausgleich](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Exemplarische Vorgehensweise zum Suchen von Diensten durch Skype for Business-Clients
<a name="WalkthroughOfSkype"> </a>

Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server. In diesem Abschnitt wird der Serverspeicherortprozess beschrieben.
  
1. lyncdiscoverinternal.\<domain\>
    
     *Dies ist ein A-Hostdatensatz für den AutoErmittlungsdienst in den internen Webdiensten.* 
    
2. lyncdiscover.\<domain\>
    
     *Dies ist ein A-Hostdatensatz für den AutoErmittlungsdienst in den externen Webdiensten.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *Dies ist ein SRV-Eintrag für interne TLS-Verbindungen.* 
    
4. _sip._tls.\<domain\>
    
     *Dies ist ein SRV-Eintrag für externe TLS-Verbindungen.* 
    
5. sipinternal.\<domain\>
    
     *Dies ist ein A-Host-Eintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann.* 
    
6. sip.\<domain\>
    
     *Dies ist ein A-Host-Eintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann.* 
    
7. sipexternal.\<domain\>
    
     *Dies ist ein A-Host-Eintrag für den Zugriffs-Edgedienst, wenn der Client extern ist.* 
    
Der AutoErmittlungsdienst wird immer bevorzugt, da dies die bevorzugte Methode für den Dienstspeicherort ist, und die anderen sind Fallbackmethoden.
  
> [!NOTE]
> Beachten Sie beim Erstellen von SRV-Einträgen, dass sie auf ein DNS A (und AAAA, wenn Sie die IPv6-Adressierung verwenden) in derselben Domäne verweisen müssen, in der der DNS-SRV-Eintrag erstellt wird. Wenn sie z. B. den Eintrag "SRV" in contoso.com, kann der A- (und AAAA)-Eintrag, auf den er verweist, nicht in der fabrikam.com. 
  
Wenn Sie nicht dazu bereit sind, können Sie Ihr mobiles Gerät für die manuelle Suche nach Diensten einrichten. Wenn Sie dies tun möchten, muss jeder Benutzer seine Einstellungen für mobile Geräte mit den vollständigen internen und externen AUTOErmittlungsdienst-URIs, einschließlich Protokoll und Pfad, wie folgt konfigurieren:
  
- Für den externen Zugriff: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- Für internen Zugriff: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
Es wird empfohlen, die automatische Ermittlung im Gegensatz zur manuellen Ermittlung zu verwenden. Wenn Sie jedoch einige Problembehandlungen oder Tests durchführen, können manuelle Einstellungen sehr hilfreich sein.
  
## <a name="split-brain-dns"></a>Split-Brain-DNS
<a name="SplitBrainDNS"> </a>

Dies ist eine DNS-Konfiguration, in der Zwei -DNS-Zonen mit demselben Namespace vorhanden sind. Die erste DNS-Zone verarbeitet interne Anforderungen, während die zweite DNS-Zone externe Anforderungen verarbeitet.
  
Warum sollte ein Unternehmen dies tun? Möglicherweise ist es erforderlich, denselben Namespace intern und extern zu verwenden, aber natürlich führt dies dazu, dass viele DNS-SRV- und A-Einträge für eine Zone oder eine andere zone eindeutig sind, und wenn doppelte Einträge vorhanden sind, sind die diesen Einträgen zugeordneten IP-Adressen eindeutig.
  
Dies stellt einige Herausforderungen dar. Der wichtigste Punkt ist, dass Split-Brain-DNS **für Mobilität** nicht unterstützt wird. Dies liegt an den LyncDiscover- und LyncDiscoverInternal-DNS-Einträgen (LyncDiscover muss auf Ihrem externen DNS-Server definiert werden, während "LyncDiscoverInternal" auf Ihrem internen DNS-Server definiert werden muss).
  
Hier werden die DNS-Einträge für die internen und externen Zonen aufgeführt, detaillierte Beispiele finden Sie jedoch im Abschnitt zu den Umgebungsanforderungen für Edgeserver.
  
### <a name="internal-dns"></a>Interne DNS-Konfiguration

- Enthält eine DNS-Zone, die beispielsweise als contoso.com bezeichnet wird und für die sie autoritativ ist.
    
- Diese interne contoso.com enthält:
    
  - DNS-A- und DNS-AAAA-Einträge (wenn Sie die IPv6-Adressierung verwenden) für Ihren Front-End-Pool, Directorpool- oder Directorpoolnamen sowie alle internen Server, auf denen Skype for Business Server im Netzwerk Ihrer Organisation ausgeführt wird.
    
  - DNS-A- und DNS-AAAA-Einträge (wenn Sie die IPv6-Adressierung verwenden) für Ihre interne Edgeschnittstelle für jeden Skype for Business Server-Edgeserver in Ihrem Umkreisnetzwerk.
    
  - DNS-A- und DNS-AAAA-Einträge (wenn Sie die IPv6-Adressierung verwenden) für  die interne Schnittstelle jedes Reverseproxyservers in Ihrem Umkreisnetzwerk (optional für die Verwaltung eines Reverseproxys).
    
  - DNS-A- und DNS-AAAA-Einträge (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die automatische Konfiguration des internen Skype for Business Server-Clients **(optional).**
    
  - DNS-A- und DNS-AAAA-Einträge (wenn Sie #A0 verwenden) oder #A1 für die automatische Ermittlung von Skype for Business #A2 **(optional).**
    
- Alle internen Skype for Business Server-Edgeschnittstellen in Ihrem Umkreisnetzwerk verwenden diese interne DNS-Zone, um Abfragen zu contoso.com.
    
- Alle Server, auf denen Skype for Business Server ausgeführt wird, und Clients, auf denen Skype for Business Server im Unternehmensnetzwerk ausgeführt wird, verweisen auf interne DNS-Server, um Abfragen an contoso.com auflösbar zu machen, oder sie verwenden die Hostdatei auf jedem Edgeserver und listen A- und AAAA-Einträge (wenn Sie die IPv6-Adressierung verwenden) für den nächsten Hopserver (speziell für die VIP des Director- oder Directorpools) auf. , front-End-Pool-VIP oder Standard Edition-Server).
    
### <a name="external-dns"></a>Externes DNS

- Enthält eine DNS-Zone, die beispielsweise als contoso.com bezeichnet wird und für die sie autoritativ ist.
    
- Diese externe contoso.com enthält:
    
  - DNS-A- und #A0 (wenn Sie #A1 verwenden) oder #A2 für die automatische Ermittlung von Skype for Business Server-Webdiensten. Dies ist für die Verwendung mit Mobilität.
    
  - DNS-A- und DNS-AAAA-Einträge (bei Verwendung der IPv6-Adressierung) und #A0 für die externe Edgeschnittstelle jedes Skype for Business #A1 oder #A2 (Hardware Load Balanced, HARDWARElastenausgleich) im Umkreisnetzwerk.
    
  - DNS-A- und DNS-AAAA-Einträge (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die externe Schnittstelle des Reverseproxyservers oder (VIP für einen Pool von Reverseproxyservern) im Umkreisnetzwerk.
    
  - DNS-A- und DNS-AAAA-Einträge (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die automatische Konfiguration des Skype for Business Server-Clients **(optional).**
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Automatische Konfiguration ohne Split-Brain-DNS
<a name="NoSplitBrainDNS"> </a>

Wenn Sie split-brain-DNS nicht verwenden, funktioniert die interne automatische Konfiguration von Clients mit Skype for Business nur, wenn Sie eine der hier beschriebenen Problemumgehungen verwenden. Warum nicht? Da Skype for Business Server erfordert, dass der SIP-URI des Benutzers mit der Domäne des Front-End-Pools, der für die automatische Konfiguration bestimmt ist, übereinstimmen muss. Dies hat sich nicht von früheren Versionen von Lync Server geändert.
  
Wenn Sie also zwei SIP-Domänen verwenden, benötigen Sie diese DNS-SRV-Einträge:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Wenn sich ein Benutzer als bob@contoso.com meldet, funktioniert dieser Eintrag für die automatische Konfiguration, da die SIP-Domäne des Benutzers mit der Domäne des Front-End-Pools (contoso.com) contoso.com.* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Wenn sich ein Benutzer als alice@fabrikam.com meldet, funktioniert dieser Eintrag für die automatische Konfiguration der zweiten Domäne, da die SIP-Domäne dem Front-End-Pool für diese Domäne entspricht.* 
    
Um das Beispiel weiter zu nutzen, würde dies nicht funktionieren:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Benutzer, die sich als tim@litwareinc.com anmelden, funktionieren nicht für die automatische Konfiguration, da seine SIP-Domäne (litwareinc.com) nicht mit der Domäne im Pool (fabrikam.com) fabrikam.com.* 
    
Wenn Sie also eine automatische Anforderung für Ihre Skype for Business-Clients ohne Split-Brain-DNS benötigen, haben Sie die folgenden Optionen:
  
- **Gruppenrichtlinienobjekte**
    
    Sie können Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) verwenden, um die richtigen Serverwerte zu füllen.
    
    > [!NOTE]
    > Mit dieser Option wird die automatische Konfiguration nicht aktiviert, aber die manuelle Konfiguration wird automatisiert. Wenn dieser Ansatz verwendet wird, sind die srV-Einträge, die der automatischen Konfiguration zugeordnet sind, nicht erforderlich. 
  
- **Übereinstimmende interne Zone**
    
    Sie müssen eine Zone in Ihrem internen DNS erstellen, die Ihrer externen DNS-Zone entspricht (z. B. contoso.com), und dann DNS-A-Einträge (und AAAA, wenn Sie die IPv6-Adressierung verwenden) erstellen, die dem Skype for Business Server-Pool entsprechen, der für die automatische Konfiguration verwendet wird.
    
    Wenn Sie beispielsweise einen Benutzer in pool01.contoso.net verwaltet haben, sich aber als bob@contoso.com bei Skype for Business anmelden, erstellen Sie eine interne DNS-Zone namens contoso.com, und innerhalb dieser müssen Sie einen DNS A-Eintrag (und AAAA, wenn die IPv6-Adressierung verwendet wird) für pool01.contoso.com erstellen.
    
- **Interne Pinpunktzone**
    
    Wenn das Erstellen einer vollständigen Zone in Ihrem internen DNS keine Option für Sie ist, können Sie Pin-Point-Zonen (dedizierte) Zonen erstellen, die den für die automatische Konfiguration erforderlichen SRV-Einträgen entsprechen, und diese Zonen mithilfe von dnscmd.exe. Dnscmd.exe ist erforderlich, da die Dns-Benutzeroberfläche die Erstellung von Pin-Point-Zonen nicht unterstützt.
    
    Wenn Ihre SIP-Domäne z. B. contoso.com ist und Sie über einen Front-End-Pool namens "pool01" mit zwei Front-End-Servern verfügen, benötigen Sie die folgenden Pin-Point-Zonen und A-Einträge in Ihrem internen DNS:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Möglicherweise verfügen Sie in Ihrer Umgebung über eine zweite SIP-Domäne. In diesem Fall benötigen Sie die folgenden Pinpunktzonen und A-Einträge in Ihrem internen DNS:
    
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
> Der FQDN des Front-End-Pools wird zweimal angezeigt, jedoch mit zwei unterschiedlichen IP-Adressen. Der Grund dafür ist, dass der DNS-Lastenausgleich verwendet wird. Wenn hlB verwendet wird, gibt es nur einen einzigen Front-End-Pooleintrag. 
  
> [!NOTE]
> Außerdem ändern sich die FQDN-Werte des Front-End-Pools zwischen contoso.com und fabrikam.com Beispielen, die IP-Adressen bleiben jedoch unverändert. Der Grund dafür ist, dass Benutzer, die sich von einer der beiden SIP-Domänen anmelden, denselben Front-End-Pool für die automatische Konfiguration verwenden. 
  
## <a name="dns-disaster-recovery"></a>DNS-Notfallwiederherstellung
<a name="DNSDR"> </a>

Um DNS so zu konfigurieren, dass Skype for Business Server-Webdatenverkehr an Ihre Notfallwiederherstellungs- und Failoverwebsites umgeleitet wird, müssen Sie einen DNS-Anbieter verwenden, der GeoDNS unterstützt. Sie können Ihre DNS-Einträge für die Unterstützung der Notfallwiederherstellung einrichten, damit Features, die Webdienste verwenden, auch dann fortgesetzt werden, wenn ein gesamter Front-End-Pool aus dem System geht. Dieses Feature für den Notruf unterstützt die einfachen URLs autoErmittlung, Meet und Dial-In.
  
Sie definieren und konfigurieren zusätzliche DNS-Host-A-Einträge (AAAA bei Verwendung von IPv6) für die interne und externe Auflösung von Webdiensten bei Ihrem GeoDNS-Anbieter. In den folgenden Details wird davon ausgegangen, dass gekoppelte Pools geografisch  verteilt sind und dass der geoDNS, der von Ihrem Anbieter unterstützt wird, entweder über Roundrobin-DNS  verfügt oder für die Verwendung von Pool1 als primärem Pool konfiguriert ist und bei Kommunikationsverlusten oder Stromausfällen zu Pool2 überfällt.
  
Alle in dieser Tabelle aufgeführten DNS-Einträge sind Beispiele.
  
|**GeoDNS-Eintrag**|**Pooldatensätze**|**#A0**|**DNS-Einstellungen (Wählen Sie eine Option aus)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com  <br/> |RoundRobin zwischen Pools  <br/> **ODER** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundären Verbindungen bei einem Fehler  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com  <br/> |Roundrobin zwischen Pools  <br/> **ODER** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundären Verbindungen bei einem Fehler  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com  <br/> |RoundRobin zwischen Pools  <br/> **ODER** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundären Verbindungen bei einem Fehler  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com  <br/> |RoundRobin zwischen Pools  <br/> **ODER** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundären Verbindungen bei einem Fehler  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com  <br/> |RoundRobin zwischen Pools  <br/> **ODER** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundären Verbindungen bei einem Fehler  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com  <br/> |RoundRobin zwischen Pools  <br/> **ODER** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundären Verbindungen bei einem Fehler  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com  <br/> |RoundRobin zwischen Pools  <br/> **ODER** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundären Verbindungen bei einem Fehler  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com  <br/> |RoundRobin zwischen Pools  <br/> **ODER** <br/> Primäres Verwenden, Herstellen einer Verbindung mit sekundären Verbindungen bei einem Fehler  <br/> |
   
## <a name="dns-load-balancing"></a>DNS-Lastenausgleich
<a name="DNSLB"> </a>

Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert. Die Anwendung (z. B. ein Client mit Skype for Business) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem sie eine Verbindung mit einer der VON der DNS-A- und AAAA-Eintragsabfrage (wenn die IPv6-Adressierung verwendet wird) zurückgegebenen IP-Adressen für den Pool-FQDN herstellen.
  
Wenn sich beispielsweise drei Front-End-Server in einem Pool mit dem Namen pool01.contoso.com befinden, würde Folgendes passieren:
  
- Clients, die Skype for Business ausführen, fragen DNS für pool01.contoso.com. Die Abfrage gibt drei IP-Adressen zurück und speichert sie wie folgt zwischen (in einer bestimmten Reihenfolge):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Der Client versucht, eine TCP-Verbindung mit einer der IP-Adressen herzustellen. Wenn dies fehlschlägt, wird die nächste IP-Adresse aus dieser Liste zwischengespeichert.
    
- Wenn die TCP-Verbindung erfolgreich ist, handelt der Client TLS aus, um eine Verbindung mit der primären Registrierungsstelle auf dem pool01.contoso.com.
    
- Wenn der Client versucht, alle zwischengespeicherten Einträge ohne erfolgreiche Verbindung zu verwenden, erhält der Benutzer eine Benachrichtigung, dass derzeit keine Server mit Skype for Business Server verfügbar sind.
    
> [!NOTE]
> Der DNS-basierte Lastenausgleich ist anders als DNS RoundRobin (DNS RR), der sich in der Regel auf den Lastenausgleich bezieht, indem dns verwendet wird, um eine andere Reihenfolge von IP-Adressen für die Server in Ihrem Pool zu erstellen. In der Regel ermöglicht DNS RR die Lastverteilung, ermöglicht jedoch nicht die Aktivierung des Failovers. Wenn z. B. die Verbindung mit der von Ihrer DNS-A-Abfrage (oder AAAA in einem IPv6-Szenario) zurückgegebenen ip-Adresse fehlschlägt, schlägt diese Verbindung fehl. Dies macht DNS RR weniger zuverlässig als DNS-basierter Lastenausgleich. Sie können DNS RR weiterhin in Verbindung mit DNS-basiertem Lastenausgleich verwenden, wenn Sie dies tun müssen. 
  
Sie verwenden den DNS-Lastenausgleich für:
  
- Lastenausgleich zwischen Server-zu-Server-SIP mit den Edgeservern.
    
- Lastenausgleich für Unified Communication Application Services (UKAS)-Anwendungen, z. B. Automatische Telefonzentrale, Reaktionsgruppe und Das Parken von Anrufen.
    
- Verhindern neuer Verbindungen mit UKAS-Anwendungen (auch als "Draining" bekannt).
    
- Lastenausgleich für den sämtlichen Client-zu-Server-Datenverkehr zwischen Clients und Edgeservern.
    
Sie können den DNS-Lastenausgleich nicht für:
  
- Client-zu-Server-Webdatenverkehr zu Ihren Front-End-Servern oder einem Director.
    
Um etwas detaillierter zu erfahren, wie ein DNS-SRV-Eintrag ausgewählt wird, wenn die Mutiple-DNS-Einträge von einer Abfrage zurückgegeben werden, wählt der Zugriffs-Edgedienst immer den Eintrag mit der niedrigsten numerischen Priorität und, wenn ein Gleichungsschalter erforderlich ist, die höchste numerische Gewichtung aus. Dies entspricht der [Dokumentation zur Internet Engineering Task Force.](https://www.ietf.org/rfc/rfc2782.txt)
  
Wenn Ihr erster DNS-SRV-Eintrag beispielsweise eine Gewichtung von 20 und eine Priorität von 40 hat und Ihr zweiter DNS-SRV-Eintrag eine Gewichtung von 10 und eine Priorität von 50 hat, wird der erste Eintrag ausgewählt, da er die niedrigere Priorität von 40 hat. Priorität steht immer an erster Stelle, und dies ist der Host, auf den ein Client zuerst abzielt. Was passiert, wenn es zwei Ziele mit derselben Priorität gibt? 
  
In diesem Fall wird die Gewichtung berücksichtigt. Größere Gewichtungen sollten mit hoher Wahrscheinlichkeit ausgewählt werden. Wenn keine Serverauswahl erforderlich ist, sollten sie die Gewichtung 0 verwenden. Wenn Datensätze mit Gewichtungen größer als 0 sind, haben Datensätze mit der Gewichtung 0 eine sehr geringe Wahrscheinlichkeit, ausgewählt zu werden.
  
Was passiert also, wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden? In diesem Fall wählt der Zugriffs-Edgedienst zuerst den SRV-Eintrag aus, den er vom DNS-Server erhalten hat.
  

