---
title: 'Lync Server 2013: Bestimmen der DNS-Anforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d00f86eb437f673e83e2ea2e610ad9b35dbea082
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522602"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a>Bestimmen der DNS-Anforderungen für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Anhand des folgenden Ablaufdiagramms können Sie die DNS-Anforderungen (Domain Name System) ermitteln. Änderungen für die kumulativen Updates für lync Server 2013: Februar 2013 werden notiert, wo Sie zutreffen.

<div>


> [!IMPORTANT]  
> Microsoft lync Server 2013 unterstützt die Verwendung der IPv6-Adressierung. Um IPv6-Adressen verwenden zu können, müssen Sie auch Unterstützung für IPv6-DNS bereitstellen und DNS-Host-AAAA-Einträge ("Quad-A" bezeichnet) konfigurieren. In Bereitstellungen, in denen sowohl IPv4 als auch IPv6 verwendet werden, empfiehlt es sich, sowohl Host A-Einträge für IPv4 als auch Host-AAAA für IPv6 zu konfigurieren und zu verwalten. Auch wenn Ihre Bereitstellung vollständig auf IPv6 umgestellt ist, sind IPv4-DNS-Hosteinträge möglicherweise noch erforderlich, wenn externe Benutzer weiterhin IPv4 verwenden.



</div>

**Ablaufdiagramm zur Ermittlung der DNS-Anforderungen**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> Standardmäßig ist der Computername eines Computers, der nicht einer Domäne angehört, ein Hostname, kein vollqualifizierter Domänenname (FQDN). Der Topologie-Generator verwendet FQDNs und keine Hostnamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (also A–Z, a–z, 0–9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt. Weitere Informationen finden Sie unter <A href="lync-server-2013-configure-dns-host-records.md">Konfigurieren von DNS-Host Einträgen für lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>So finden lync-Clients Dienste

Microsoft lync 2010, lync 2013 und lync Mobile ähneln der Art und Weise, in der der Clientdienste in lync Server 2013 findet und zugreift. Die wichtigste Ausnahme ist die lync Windows Store-App, die einen anderen Dienststandort Prozess verwendet. In diesem Abschnitt werden zwei Szenarien beschrieben, wie die Clients Dienste suchen, zunächst die herkömmliche Methode, die eine Reihe von SRV-und Hosteinträgen verwendet, und zweitens nur die Datensätze des AutoErmittlungsdiensts. Kumulierte Aktualisierungen der Desktop Clients ändern den DNS-Standort Prozess von lync Server 2010 für alle Clients, der DNS-Abfrageprozess wird fortgesetzt, bis eine erfolgreiche Abfrage zurückgegeben wird, oder die Liste der möglichen DNS-Einträge ist erschöpft, und der letzte Fehler wird an den Client zurückgegeben.

Für alle Clients **mit Ausnahme** der lync Windows Store-App während der DNS-Suche werden SRV-Einträge abgefragt und in der folgenden Reihenfolge an den Client zurückgegeben:

1.  "lyncdiscoverinternal". \<domain\>     Ein (Host)-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten

2.  lyncdiscover. \<domain\>     Ein (Host)-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten

3.  \_sipinternaltls. \_ TCP. \<domain\>     SRV (Service Locator)-Eintrag für interne TLS-Verbindungen

4.  \_sipinternal. \_ TCP. \<domain\>     SRV (Service Locator)-Eintrag für interne TCP-Verbindungen (nur ausgeführt, wenn TCP zulässig ist)

5.  \_SIP. \_ TLS. \<domain\>     SRV (Service Locator)-Eintrag für externe TLS-Verbindungen

6.  sipinternal. \<domain\>     Ein (Host-) Eintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann

7.  SIP. \<domain\>     Ein (Host-) Eintrag für den Front-End-Pool oder Director im internen Netzwerk oder die Zugriffs-Edgedienst, wenn der Client extern ist

8.  sipexternal. \<domain\>     Ein (Host-) Eintrag für den Zugriffs-Edgedienst, wenn der Client extern ist

Die lync Windows Store-App ändert den Prozess vollständig, da zwei Datensätze verwendet werden:

1.  "lyncdiscoverinternal". \<domain\>     Ein (Host)-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten

2.  lyncdiscover. \<domain\>     Ein (Host)-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten

Es gibt kein Fallback auf die anderen Datensatztypen.

Der Unterschied zwischen den Methoden, die für neuere Clients im Vergleich zu älteren Clients verwendet werden, besteht darin, dass der AutoErmittlungsdienst die bevorzugte Methode zum Auffinden aller Dienste wird.

Wenn eine Verbindung erfolgreich hergestellt wurde, gibt der AutoErmittlungsdienst alle Webdienste-URLs für den privaten Pool des Benutzers zurück, einschließlich des mobilitätsdiensts (bekannt als MCX durch das virtuelle Verzeichnis, das in IIS für den Dienst erstellt wurde), Microsoft lync Web App-und Webplaner-URLs. Jedoch ist sowohl die interne als auch die externe URL des Mobilitätsdiensts dem externen Webdienste-FQDN zugeordnet. Daher stellt das mobile Gerät (egal, ob es sich innerhalb oder außerhalb des Netzwerks befindet) immer extern über den Reverseproxy eine Verbindung mit dem Mobilitätsdienst her.

Wenn die kumulativen Updates für lync Server 2013:2013 Februar installiert wurde, gibt der AutoErmittlungsdienst auch Verweise auf Internal/UCWA, External/UCWA und UCWA zurück. Diese Einträge verweisen auf die Unified Communications Web API (UCWA)-Webkomponente. Derzeit wird nur der Eintrag UCWA verwendet, und es wird ein Verweis auf eine URL für die Webkomponente bereitgestellt. UCWA wird von lync 2013 mobilen Clients anstelle des MCX-mobilitätsdiensts verwendet, der von den lync 2010 Mobile Clients verwendet wird.

<div>


> [!NOTE]  
> Beim Erstellen von SRV-Einträgen ist es wichtig, sich daran zu erinnern, dass Sie auf einen DNS-Eintrag (wenn Sie IPv6-Adressierung verwenden) in derselben Domäne, in der der DNS-SRV-Eintrag erstellt wird, hinweisen müssen. Wenn sich der SRV-Eintrag beispielsweise in contoso.com befindet, zeigt der Eintrag A und AAAA (wenn Sie IPv6-Adressierung verwenden) auf nicht in fabrikam.com.



</div>

<div>


> [!TIP]  
> Die Standardkonfiguration besteht darin, den gesamten mobilen Client Datenverkehr über den externen Standort zu leiten. Sie können Einstellungen so ändern, dass nur die interne URL zurückgegeben wird, wenn dies für Ihre Anforderungen vorzuziehen ist. Bei dieser Konfiguration können Benutzer auf ihren mobilen Geräten mobile Lync-Anwendungen nur verwenden, wenn sie sich im Firmennetzwerk befinden. Um diese Konfiguration zu definieren, verwenden Sie das Cmdlet " <STRONG>CsMcxConfiguration</STRONG> ".



</div>

<div>


> [!NOTE]  
> Obwohl mobile Anwendungen auch eine Verbindung mit anderen lync Server 2013 Diensten wie dem Adressbuchdienst herstellen können, werden Webanforderungen für interne Mobile Webanwendungen nur für den Mobilitätsdienst an den externen webfqdn des Webs weitergeben. Für andere Dienstanforderungen, beispielsweise Adressbuchanforderungen, ist diese Konfiguration nicht erforderlich.



</div>

Mobile Geräte unterstützen die manuelle Ermittlung von Diensten. In diesem Fall muss jeder Benutzer in den Einstellungen des mobilen Geräts wie folgt die vollständigen internen und externen AutoErmittlungsdienst-URIs konfigurieren, einschließlich Protokoll und Pfad:

  - https://- \<ExtPoolFQDN\> /autodiscover/autodiscoverservice.svc/root für externen Zugriff

  - https://- \<IntPoolFQDN\> /autodiscover/autodiscover.svc/root für internen Zugriff

Es wird empfohlen, die automatische Ermittlung anstelle von manueller Ermittlung zu verwenden. Manuelle Einstellungen können jedoch bei der Behandlung von Problemen mit der Konnektivität mobiler Geräte hilfreich sein.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Konfigurieren Split-Brain DNS mit lync Server

Split-Brain-DNS ist durch eine Reihe von Namen bekannt, beispielsweise geteilte DNS oder Split-Horizon-DNS. Es wird lediglich eine DNS-Konfiguration beschrieben, in der zwei DNS-Zonen mit dem gleichen Namespace vorhanden sind – nur interne Anforderungen für DNS-Zonen Dienste und die anderen DNS-Zonen Dienste, die nur extern angefordert werden. Eine Vielzahl der DNS-SRV- und DNS-A-Einträge in der internen DNS-Konfiguration sind jedoch nicht in der externen DNS-Konfiguration enthalten und umgekehrt. In Fällen, in denen derselbe DNS-Eintrag sowohl im internen als auch im externen DNS vorhanden ist (beispielsweise www.contoso.com), unterscheidet sich die zurückgegebene IP-Adresse je nachdem, wo (intern oder extern) die Abfrage initiiert wurde.

<div>


> [!IMPORTANT]  
> Derzeit wird Split-Brain DNS für die Mobilität oder genauer gesagt für die LyncDiscover-und "lyncdiscoverinternal"-DNS-Einträge nicht unterstützt. LyncDiscover muss auf einem externen DNS-Server definiert sein, und "lyncdiscoverinternal" muss auf einem internen DNS-Server definiert sein.



</div>

Im Rahmen dieser Themen wird der Begriff Split-Brain-DNS verwendet.

Wenn Sie Split-Brain-DNS konfigurieren, umfassen die folgenden internen und externen Zonen eine Übersicht über die Typen von DNS-Einträgen, die in jeder Zone erforderlich sind. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Interne DNS-Konfiguration:**

  - Enthält eine DNS-Zone "contoso.com", für die die DNS-Konfiguration autoritativ ist

  - Die interne Zone "contoso.com" umfasst Folgendes:
    
      - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) und SRV-Einträge für die interne lync Server 2013 Client-Autokonfiguration (optional)
    
      - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Ermittlung von lync Server 2013 Webdienste (optional)
    
      - DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für Front-End-Pool Namen, den Director oder den Directorpool Namen sowie alle internen Server mit lync Server 2013 im Unternehmensnetzwerk
    
      - DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für die interne Edge-Schnittstelle jedes lync Server 2013 Edgeserver im Umkreisnetzwerk
    
      - DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für die interne Schnittstelle jedes Reverse-Proxyservers im Umkreisnetzwerk (optional für die Verwaltung des Reverseproxys)
    
      - Alle lync Server 2013 Edgeserver internen Edge-Schnittstellen im Umkreisnetzwerk verwenden die interne DNS-Zone zum Auflösen von Abfragen in contoso.com
    
      - Alle Server mit lync Server 2013 und Clients, auf denen lync 2013 im Unternehmensnetzwerk läuft, weisen auf die internen DNS-Server hin, um Abfragen an contoso.com zu lösen, oder Sie können die Hosts-Datei auf jedem Edgeserver und Listen A und AAAA (wenn Sie IPv6-Adressierung verwenden) für den nächsten Hop-Server, insbesondere den Director oder Director VIP, Front-End-Pool VIP oder Standard Edition-Server

**Externe DNS-Konfiguration:**

  - Enthält eine DNS-Zone "contoso.com", für die die DNS-Konfiguration autoritativ ist

  - Die externe Zone "contoso.com" umfasst Folgendes:
    
      - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) und SRV-Einträge für lync Server 2013 Client-Autokonfiguration (optional)
    
      - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Ermittlung von lync Server 2013 Webdienste für die Verwendung mit Mobility
    
      - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die externe Edge-Schnittstelle jedes lync Server 2013, Edgeserver oder die virtuelle IP des Hardware Lastenausgleichs im Umkreisnetzwerk
    
      - DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für die externe Schnittstelle des Reverseproxy-Servers oder VIP für einen Pool von Reverse-Proxyservern im Umkreisnetzwerk

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Automatische Konfiguration ohne Split-Brain-DNS

Bei Verwendung von Split-Brain-DNS kann ein lync Server 2013 Benutzer, der sich intern anmeldet, die automatische Konfiguration nutzen, wenn die interne DNS-Zone eine \_ sipinternaltls enthält. \_ TCP-SRV-Eintrag für jede verwendete SIP-Domäne. Wenn Sie jedoch nicht Split-Brain-DNS verwenden, funktioniert die interne automatische Konfiguration von Clients, auf denen lync ausgeführt wird, nur, wenn eine der in diesem Abschnitt weiter unten beschriebenen Problemumgehungen implementiert ist. Dies liegt daran, dass lync Server 2013 erfordert, dass der SIP-URI des Benutzers mit der Domäne der Front-End-Pool übereinstimmt, die für die automatische Konfiguration festgelegt ist. Dies war auch bei früheren Versionen von Communicator der Fall.

Wenn Sie z. B. zwei SIP-Domänen verwenden, sind die zwei folgenden DNS-SRV-Einträge erforderlich:

  - Wenn sich ein Benutzer als Bob@contoso.com anmeldet, funktioniert der folgende SRV-Eintrag für die automatische Konfiguration, da die SIP-Domäne (contoso.com) des Benutzers mit der Domäne der automatischen Konfigurations Front-End-Pool) übereinstimmt:
    
     \_sipinternaltls. \_ TCP.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Wenn sich ein Benutzer als Alice@fabrikam.com anmeldet, funktioniert der folgende DNS-SRV-Eintrag für die automatische Konfiguration der zweiten SIP-Domäne.
    
     \_sipinternaltls. \_ TCP.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Wenn sich ein Benutzer als Tim@litwareinc.com anmeldet, kann der folgende DNS-SRV-Eintrag zum Vergleich nicht für die automatische Konfiguration verwendet werden, da die SIP-Domäne (litwareinc.com) des Clients nicht mit der Domäne übereinstimmt, in der sich der Pool befindet (fabrikam.com):

 \_sipinternaltls. \_ TCP.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Wenn für Clients, die lync ausführen, die automatische Konfiguration erforderlich ist, wählen Sie eine der folgenden Optionen aus:

  - **Gruppenrichtlinienobjekte**     Verwenden Sie Gruppenrichtlinienobjekte (Group Policy Objects, GPOs), um die richtigen Server Werte aufzufüllen.
    
    <div>
    

    > [!NOTE]  
    > Mit dieser Option wird die automatische Konfiguration nicht aktiviert, der Prozess der manuellen Konfiguration wird jedoch automatisiert. Daher werden die SRV-Einträge für die automatische Konfiguration bei Verwendung dieses Ansatzes nicht benötigt.

    
    </div>

  - **Übereinstimmende interne Zone**     Erstellen Sie eine Zone im internen DNS, die mit der externen DNS-Zone übereinstimmt (beispielsweise contoso.com), und erstellen Sie DNS a und AAAA (wenn Sie IPv6-Adressierung verwenden), die dem lync Server 2013 Pool entsprechen, der für die automatische Konfiguration verwendet wird. Wenn ein Benutzer beispielsweise in pool01.contoso.NET verwaltet wird, sich jedoch als Bob@contoso.com in lync befindet, erstellen Sie eine interne DNS-Zone namens Contoso.com, und erstellen Sie in dieser einen DNS-Eintrag a und AAAA (falls IPv6-Adressierung verwendet wird) für pool01.contoso.com.

  - **Interne Pin-Punkt Zone**     Wenn Sie eine gesamte Zone im internen DNS erstellen, ist keine Option, sondern Sie können PIN-Punkt-(dedizierte) Zonen erstellen, die den SRV-Einträgen entsprechen, die für die automatische Konfiguration erforderlich sind, und diese Zonen mit dnscmd.exe auffüllen. Dnscmd.exe ist erforderlich, da die DNS-Benutzeroberfläche die Erstellung von PIN-Punkt-Zonen nicht unterstützt. Wenn die SIP-Domäne beispielsweise contoso.com ist und Sie über eine Front-End-Pool namens pool01 verfügen, die zwei Front-End-Server enthält, benötigen Sie die folgenden Pin-Punkt-Zonen und einen Eintrag in Ihrem internen DNS:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Wenn Ihre Umgebung eine zweite SIP-Domäne (z. B. "fabrikam.com") umfasst, benötigen Sie die folgenden dedizierten Zonen und DNS-A-Einträge in Ihrem internen DNS:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> Der FQDN des Front-End-Pools wird zweimal aufgeführt, jedoch mit unterschiedlichen IP-Adressen. Der Grund dafür ist, dass ein DNS-Lastenausgleich verwendet wird. Bei Verwendung von Hardwarelastenausgleich wäre nur ein einzelner Front-End-Pool-Eintrag vorhanden. Zudem weisen die Beispiele "contoso.com" und "fabrikam.com" unterschiedliche FQDN-Werte des Front-End-Pools auf, die IP-Adressen sind jedoch gleich. Der Grund dafür ist, dass Benutzer, die sich über eine der SIP-Domänen anmelden, denselben Front-End-Pool für die automatische Konfiguration verwenden.



</div>

Ausführliche Informationen finden Sie im DMTF-Blog Artikel "Communicator Automatic Configuration and Split-Brain DNS" unter [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) .

<div>


> [!NOTE]  
> Der Inhalt jedes Blogs und die dazugehörige URL kann ohne vorherige Ankündigung geändert werden.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Konfigurieren des DNS (Domain Name System) für die Notfallwiederherstellung

Sie müssen einen DNS-Anbieter verwenden, der GeoDNS unterstützt, um DNS so zu konfigurieren, dass lync Server 2013 Webdatenverkehr auf Ihre Notfallwiederherstellung und Failover-Websites umgeleitet wird. Sie können Ihre DNS-Einträge für das Internet so einrichten, dass die Notfallwiederherstellung unterstützt wird, sodass Features, die Webdienste verwenden, auch dann fortgesetzt werden, wenn ein ganzer Front-End-Pool ausfällt. Diese Notfallwiederherstellungsfunktion unterstützt die AutoErmittlung (Lyncdiscover-URL), Meet and Dial-in Simple URLs.

Sie definieren und konfigurieren zusätzliche DNS-Hosteinträge (A und AAAA bei Verwendung von IPv6) für die interne und externe Auflösung von Webdiensten bei Ihrem GeoDNS-Anbieter. Die folgenden Details setzen voraus, dass gekoppelte Pools, geografisch verteilte und GeoDNS, die von Ihrem Anbieter entweder mit Round-Robin-DNS unterstützt oder für die Verwendung von pool1 als Primary konfiguriert sind, und führen ein Failover auf Pool2 im Falle eines Kommunikations Verlusts oder eines Hardwarefehlers durch.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>GeoDNS-Eintrag (Beispiel)</th>
<th>Pool Einträge (Beispiel)</th>
<th>CNAME-Einträge (Beispiel)</th>
<th>DNS-Einstellungen (Wählen Sie eine Option aus)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS-Lastenausgleich

Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert. Die Anwendung (beispielsweise ein Client, der lync ausführt) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem eine Verbindung mit einer der IP-Adressen hergestellt wird, die von der DNS-Adresse "a" und "AAAA (falls IPv6-Adressierung verwendet)" für den vollqualifizierten Domänennamen (FQDN) des Pools zurückgegeben werden.

Wenn z. B. drei Front-End-Server im Pool "pool01.contoso.com" vorhanden sind, werden folgende Schritte ausgeführt:

  - Clients, auf denen lync Query DNS für pool01.contoso.com. Die Abfrage gibt drei IP-Adressen zurück und speichert diese wie folgt (nicht notwendigerweise in dieser Reihenfolge) zwischen:
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - Der Client versucht, eine TCP-Verbindung (Transmission Control Protocol) mit einer der IP-Adressen herzustellen. Ist dies nicht möglich, versucht der Client, eine Verbindung mit der nächsten IP-Adresse im Zwischenspeicher herzustellen.

  - Wenn die TCP-Verbindung erfolgreich ist, verhandelt der Client TLS, um eine Verbindung mit der primären Registrierungsstelle in pool01.contoso.com herzustellen.

  - Wenn der Client alle zwischengespeicherten Einträge ohne erfolgreiche Verbindung versucht, wird der Benutzer benachrichtigt, dass derzeit keine Server mit lync Server 2013 zur Verfügung stehen.

<div>


> [!NOTE]  
> DNS-basierter Lastenausgleich unterscheidet sich von DNS-Round Robin (DNS-Ressourceneintrag), der in der Regel auf Lastenausgleich verweist, indem DNS eine andere Reihenfolge von IP-Adressen bereitstellt, die den Servern in einem Pool entsprechen. Normalerweise aktiviert DNS-RR nur die Lastenverteilung, aktiviert jedoch kein Failover. Wenn beispielsweise die Verbindung mit der einzigen IP-Adresse, die von der DNS-A-und der AAAA-Abfrage (wenn Sie IPv6-Adressierung verwenden) zurückgegeben wird, schlägt die Verbindung fehl. Daher ist DNS Round Robin selbst weniger zuverlässig als DNS-basierter Lastenausgleich. Sie können DNS-Roundrobin in Verbindung mit dem DNS-Lastenausgleich verwenden.



</div>

DNS-Lastenausgleich wird für folgende Szenarien eingesetzt:

  - Lastenausgleich zwischen Server-zu-Server-SIP-Servern und Edgeserver

  - Lastenausgleich für Anwendungen der Unified Communications-Anwendungsdienste, z. B. automatische Konferenzzentrale, Reaktionsgruppen und die Anwendung zum Parken von Anrufen

  - Verhindern neuer Verbindungen mit Anwendungen der Unified Communications-Anwendungsdienste (auch als "Serverausgleich" bezeichnet)

  - Lastenausgleich für den gesamten Datenverkehr zwischen Clients und Edgeservern

DNS-Lastenausgleich kann für folgende Szenarien nicht eingesetzt werden:

  - Client-zu-Server-Webdatenverkehr für Director-oder Front-End-Server

DNS-Lastenausgleich und Datenverkehr im Partnerverbund:

Wenn mehrere DNS-Einträge von einer DNS-SRV-Abfrage zurückgegeben werden, wählt der Zugriffs-Edgedienst immer den DNS-SRV-Eintrag mit der niedrigsten numerischen Priorität und der höchsten numerischen Gewichtung aus. Das Internet Engineering Task Force-Dokument "ein DNS-Ressourceneintrag für die Angabe des Speicherorts von Diensten (DNS-SRV)" <http://www.ietf.org/rfc/rfc2782.txt> gibt an, dass wenn mehrere DNS-SRV-Einträge definiert sind, Priorität zuerst verwendet wird, dann die Gewichtung. Beispielsweise hat DNS-SRV-Eintrag a eine Gewichtung von 20 und eine Priorität von 40 und DNS-SRV-Eintrag B eine Gewichtung von 10 und eine Priorität von 50. DNS-SRV-Eintrag A mit Priorität 40 wird ausgewählt. Die folgenden Regeln gelten für die Auswahl des DNS-SRV-Eintrags:

  - Priorität wird als erstes betrachtet. Ein Client muss versuchen, den vom DNS-SRV-Eintrag definierten Ziel Host mit der niedrigsten nummerierten Priorität zu kontaktieren, die er erreichen kann. Ziele mit derselben Priorität sollten in einer durch das gewichtungsfeld definierten Reihenfolge ausprobiert werden.

  - Das Feld Gewichtung gibt eine relative Gewichtung für Einträge mit derselben Priorität an. Größere Gewichtungen sollten eine proportional höhere Wahrscheinlichkeit für die Auswahl erhalten. DNS-Administratoren sollten die Gewichtung 0 verwenden, wenn keine Serverauswahl erforderlich ist. Bei vorhanden sein von Datensätzen, die die Gewichtung größer als 0 enthalten, sollten Datensätze mit einer Gewichtung von 0 eine sehr geringe Chance haben, ausgewählt zu werden.

Wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden, wählt der Zugriffs-Edgedienst den SRV-Eintrag aus, der zuerst vom DNS-Server empfangen wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

