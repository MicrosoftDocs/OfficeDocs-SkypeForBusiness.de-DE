---
title: 'Lync Server 2013: Ermitteln von DNS-Anforderungen'
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
ms.openlocfilehash: fd8c1c95c3b8ba3671735447f098eca9173111ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>Ermitteln von DNS-Anforderungen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Mithilfe des folgenden Flussdiagramms können Sie DNS-Anforderungen (Domain Name System) ermitteln. Die Änderungen für die kumulativen Updates für lync Server 2013: Februar 2013 werden an deren Anwendung notiert.

<div>


> [!IMPORTANT]  
> Microsoft lync Server 2013 unterstützt die Verwendung der IPv6-Adressierung. Um IPv6-Adressen verwenden zu können, müssen Sie auch IPv6-DNS unterstützen und DNS-Host AAAA-Datensätze (so genannte "Quad-A") konfigurieren. In Bereitstellungen, in denen sowohl IPv4 als auch IPv6 verwendet werden, empfiehlt es sich, sowohl Host A Records für IPv4 als auch Host AAAA für IPv6 zu konfigurieren und zu verwalten. Auch wenn Ihre Bereitstellung vollständig auf IPv6 umgestellt wurde, sind möglicherweise IPv4-DNS-Hosteinträge erforderlich, wenn externe Benutzer weiterhin IPv4 verwenden.



</div>

**Ermitteln des Flussdiagramms für DNS-Anforderungen**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> Standardmäßig ist der Computername eines Computers, der nicht zu einer Domäne gehört, ein Hostname, nicht ein vollständig qualifizierter Domänenname (FQDN). Der Topologie-Generator verwendet FQDNs, keine Hostnamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt. Weitere Informationen finden Sie unter <A href="lync-server-2013-configure-dns-host-records.md">Konfigurieren von DNS-Host Einträgen für lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Suchen nach Diensten durch lync-Clients

Microsoft lync 2010, lync 2013 und lync Mobile ähneln der Art und Weise, wie der Clientdienste in lync Server 2013 findet und zugreift. Die wichtigste Ausnahme ist die lync Windows Store-App, die einen anderen Dienststandort Prozess verwendet. In diesem Abschnitt werden zwei Szenarien erläutert, wie die Clients Dienste finden, zunächst die herkömmliche Methode, die eine Reihe von SRV-und a-Host Datensätzen verwendet, und zweitens nur die Datensätze des AutoErmittlungsdiensts. Kumulative Updates für die Desktop Clients ändern den DNS-Standort Prozess von lync Server 2010 für alle Clients, der DNS-Abfrageprozess wird fortgesetzt, bis eine erfolgreiche Abfrage zurückgegeben wird oder die Liste der möglichen DNS-Einträge erschöpft ist, und der endgültige Fehler wird an zurückgegeben. der Client.

Für alle Clients **mit Ausnahme** der lync Windows Store-App während der DNS-Suche werden SRV-Einträge abgefragt und an den Client in der folgenden Reihenfolge zurückgegeben:

1.  lyncdiscoverinternal. \<Domänen\> -a (Host)-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten

2.  lyncdiscover. \<Domänen\> -a (Host)-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten

3.  \_sipinternaltls. \_TCP. \<Domänen\> -SRV-Eintrag (Dienst Locator) für interne TLS-Verbindungen

4.  \_sipinternal. \_TCP. \<Domänen\> -SRV-Eintrag (Dienst Locator) für interne TCP-Verbindungen (nur ausgeführt, wenn TCP zulässig ist)

5.  \_SIP. \_TLS. \<Domänen\> -SRV-Eintrag (Dienst Locator) für externe TLS-Verbindungen

6.  sipinternal. \<Domänen\> -a (Host)-Eintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann

7.  SIP. \<Domänen\> -a (Host)-Eintrag für den Front-End-Pool oder Director im internen Netzwerk oder den Access Edge-Dienst, wenn der Client extern ist

8.  sipexternal. \<Domänen\> -a (Host)-Eintrag für den Access-Edgedienst, wenn der Client extern ist

Die lync Windows Store-App ändert den Prozess vollständig, da zwei Datensätze verwendet werden:

1.  lyncdiscoverinternal. \<Domänen\> -a (Host)-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten

2.  lyncdiscover. \<Domänen\> -a (Host)-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten

Es gibt keinen Fallback auf die anderen Datensatztypen.

Der Unterschied zwischen den Methoden, die für neuere Clients im Vergleich zu älteren Clients verwendet werden, besteht darin, dass der AutoErmittlungsdienst zur bevorzugten Methode zum Auffinden aller Dienste wird.

Wenn eine Verbindung erfolgreich ist, gibt der AutoErmittlungsdienst alle Webdienste-URLs für den privaten Pool des Benutzers zurück, einschließlich des mobilitätsdiensts (bekannt als MCX durch das für den Dienst in IIS erstellte virtuelle Verzeichnis), Microsoft lync Web App und Web Scheduler-URLs. Die URL für den internen Mobilitätsdienst und die URL für den externen Mobilitätsdienst sind jedoch mit dem FQDN der externen Webdienste verbunden. Unabhängig davon, ob ein mobiles Gerät intern oder extern für das Netzwerk ist, stellt das Gerät immer extern über den Reverse-Proxy eine Verbindung mit dem Mobilitätsdienst her.

Wenn die kumulativen Updates für lync Server 2013: Februar 2013 installiert wurden, gibt der AutoErmittlungsdienst auch Verweise auf Internal/UCWA, External/UCWA und UCWA zurück. Diese Einträge beziehen sich auf die Web-Komponente "Unified Communications Web API (UCWA)". Derzeit wird nur der Eintrag UCWA verwendet, und es wird ein Verweis auf eine URL für die Webkomponente bereitgestellt. UCWA wird von lync 2013-mobilen Clients anstelle des MCX-mobilitätsdiensts verwendet, der von den mobilen lync 2010-Clients verwendet wird.

<div>


> [!NOTE]  
> Beim Erstellen von SRV-Einträgen ist zu beachten, dass Sie auf einen DNS-Eintrag in der gleichen Domäne verweisen müssen, in der der DNS-SRV-Eintrag erstellt wird (wenn Sie IPv6-Adressierung verwenden). Wenn sich der SRV-Eintrag beispielsweise in contoso.com befindet, wird in der a-und AAAA-Datei (bei Verwendung der IPv6-Adressierung) der Eintrag auf kann nicht in fabrikam.com.



</div>

<div>


> [!TIP]  
> Die Standardkonfiguration besteht darin, den gesamten mobilen Client Datenverkehr über die externe Website zu leiten. Sie können Einstellungen so ändern, dass nur die interne URL zurückgegeben wird, wenn dies für Ihre Anforderungen vorzuziehen ist. Mit dieser Konfiguration können Benutzer lync Mobile-Anwendungen auf Ihren mobilen Geräten nur verwenden, wenn Sie sich im Unternehmensnetzwerk befinden. Zum Definieren dieser Konfiguration verwenden Sie das Cmdlet " <STRONG>Satz-CsMcxConfiguration</STRONG> ".



</div>

<div>


> [!NOTE]  
> Obwohl mobile Anwendungen auch eine Verbindung mit anderen lync Server 2013-Diensten herstellen können, wie etwa dem Adressbuchdienst, werden Webanforderungen für interne Mobile Webanwendungen nur für den Mobilitätsdienst an den externen Web-FQDN weiter verwendet. Für andere Dienstanforderungen wie Adressbuch Anforderungen ist diese Konfiguration nicht erforderlich.



</div>

Mobile Geräte unterstützen die manuelle Ermittlung von Diensten. In diesem Fall muss jeder Benutzer die Einstellungen für das Mobile Gerät mit den vollständigen internen und externen AutoErmittlungsdienst-URIs, einschließlich Protokoll und Pfad, wie folgt konfigurieren:

  - https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root für externen Zugriff

  - https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root für internen Zugriff

Es wird empfohlen, die automatische Ermittlung anstelle der manuellen Ermittlung zu verwenden. Manuelle Einstellungen können jedoch bei der Behandlung von Problemen mit der mobilen Gerätekonnektivität hilfreich sein.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Konfigurieren von Split-Brain-DNS mit lync Server

Das Split-Brain-DNS ist unter einer Reihe von Namen bekannt, beispielsweise Split-DNS oder Split-Horizon-DNS. Sie beschreibt einfach eine DNS-Konfiguration, in der zwei DNS-Zonen mit dem gleichen Namespace vorhanden sind, aber nur interne Anforderungen für DNS-Zonen Dienste und die anderen nur für externe DNS-Zonen Dienste Anforderungen. Viele der DNS-SRV-und A-Einträge, die im internen DNS enthalten sind, sind jedoch nicht im externen DNS enthalten, und umgekehrt ist auch der Fall. In Fällen, in denen derselbe DNS-Eintrag sowohl im internen als auch im externen DNS vorhanden ist (beispielsweise www.contoso.com), ist die zurückgegebene IP-Adresse abhängig davon, wo (intern oder extern) die Abfrage initiiert wurde, anders.

<div>


> [!IMPORTANT]  
> Zurzeit wird Split-Brain-DNS nicht für die Mobilität oder insbesondere für die DNS-Einträge LyncDiscover und LyncDiscoverInternal unterstützt. LyncDiscover muss auf einem externen DNS-Server definiert sein, und LyncDiscoverInternal muss auf einem internen DNS-Server definiert sein.



</div>

Für die Zwecke dieser Themen wird der Begriff "Split-Brain DNS" verwendet.

Wenn Sie das Split-Brain-DNS konfigurieren, enthalten die folgenden internen und externen Zonen eine Zusammenfassung der Typen von DNS-Einträgen, die in den einzelnen Zonen erforderlich sind. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Interner DNS-Name:**

  - Enthält eine DNS-Zone mit dem Namen "contoso.com", für die Sie autorisierend ist

  - Die interne contoso.com Zone enthält Folgendes:
    
      - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die interne lync Server 2013-Client Autokonfiguration (optional)
    
      - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Ermittlung von lync Server 2013-Webdiensten (optional)
    
      - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) Datensätze für den Namen des Front-End-Pools, Director-oder Director-Poolname und alle internen Server, auf denen lync Server 2013 im Unternehmensnetzwerk ausgeführt wird
    
      - DNS A und AAAA (bei Verwendung von IPv6-Adressierungs Datensätzen) für die interne Edge-Schnittstelle jedes lync Server 2013, Edgeserver im Umkreisnetzwerk
    
      - DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) für die interne Schnittstelle jedes Reverse-Proxyservers im Umkreisnetzwerk (optional für die Verwaltung des Reverse-Proxys)
    
      - Alle lync Server 2013-Edgeserver-Schnittstellen im Umkreisnetzwerk verwenden die interne DNS-Zone zum Auflösen von Abfragen in contoso.com
    
      - Alle Server mit lync Server 2013 und Clients, auf denen lync 2013 im Unternehmensnetzwerk ausgeführt wird, verweisen auf die internen DNS-Server zum Auflösen von Abfragen an contoso.com oder auf die Verwendung der Hosts-Datei auf jedem Edgeserver sowie auf Listen A und AAAA (wenn Sie IPv6-Adressierung verwenden)-Einträge für Nächster Hop-Server, insbesondere Director oder Director VIP, Front-End-Pool VIP oder Standard Edition-Server

**Externer DNS-Name:**

  - Enthält eine DNS-Zone mit dem Namen "contoso.com", für die Sie autorisierend ist

  - Die externe contoso.com Zone enthält Folgendes:
    
      - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die Autokonfiguration des lync Server 2013-Clients (optional)
    
      - DNS A und AAAA (wenn Sie eine IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Erkennung von lync Server 2013-Webdiensten zur Verwendung mit Mobility
    
      - DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die externe Edge-Schnittstelle jeder lync Server 2013, Edgeserver oder des Hardware-Lastenausgleichsmoduls (Virtual IP (VIP)) im Umkreisnetzwerk
    
      - DNS a und AAAA (wenn Sie IPv6-Adressierung verwenden) Einträge für die externe Schnittstelle des Reverse Proxyservers oder VIP für einen Pool von Reverse-Proxyservern im Umkreisnetzwerk

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Automatische Konfiguration ohne Split-Brain-DNS

Bei Verwendung von Split-Brain-DNS kann ein lync Server 2013-Benutzer, der sich intern anmeldet, die automatische Konfiguration nutzen, wenn \_die interne DNS-Zone eine sipinternaltls enthält. \_TCP-SRV-Eintrag für jede verwendete SIP-Domäne Wenn Sie jedoch kein Split-Brain-DNS verwenden, funktioniert die interne automatische Konfiguration von Clients, auf denen lync ausgeführt wird, nicht, es sei denn, eine der in diesem Abschnitt weiter unten beschriebenen Problemumgehungen wird implementiert. Dies liegt daran, dass für lync Server 2013 der SIP-URI des Benutzers mit der Domäne des Front-End-Pools übereinstimmt, der für die automatische Konfiguration vorgesehen ist. Dies war auch bei früheren Versionen von Communicator der Fall.

Wenn Sie beispielsweise über zwei SIP-Domänen verfügen, müssen die folgenden DNS-Diensteinträge (SRV) verwendet werden:

  - Wenn sich ein Benutzer als Bob@contoso.com anmeldet, funktioniert der folgende SRV-Eintrag für die automatische Konfiguration, da die SIP-Domäne (contoso.com) des Benutzers der Domäne des Front-End-Pools für die automatische Konfiguration entspricht:
    
     \_sipinternaltls. \_TCP.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Wenn sich ein Benutzer als Alice@fabrikam.com anmeldet, funktioniert der folgende DNS-SRV-Eintrag für die automatische Konfiguration der zweiten SIP-Domäne.
    
     \_sipinternaltls. \_TCP.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Zum Vergleich: Wenn sich ein Benutzer als Tim@litwareinc.com anmeldet, funktioniert der folgende DNS-SRV-Eintrag nicht für die automatische Konfiguration, da die SIP-Domäne (litwareinc.com) des Clients nicht der Domäne entspricht, in der sich der Pool befindet (fabrikam.com):

 \_sipinternaltls. \_TCP.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Wenn für Clients, die lync ausführen, die automatische Konfiguration erforderlich ist, wählen Sie eine der folgenden Optionen aus:

  - **Gruppenrichtlinienobjekte**   verwenden Gruppenrichtlinienobjekte (Group Policy Objects, GPOs), um die richtigen Server Werte zu füllen.
    
    <div>
    

    > [!NOTE]  
    > Mit dieser Option wird die automatische Konfiguration nicht aktiviert, die manuelle Konfiguration wird jedoch automatisiert, sodass bei Verwendung dieses Ansatzes keine SRV-Einträge erforderlich sind, die der automatischen Konfiguration zugeordnet sind.

    
    </div>

  - **Übereinstimmende interne Zone**   erstellen Sie eine Zone im internen DNS, die der externen DNS-Zone entspricht (beispielsweise contoso.com), und erstellen Sie DNS a und AAAA (wenn Sie IPv6-Adressierung verwenden) Datensätze, die dem für die automatische Konfiguration verwendeten lync Server 2013-Pool entsprechen. Wenn sich ein Benutzer beispielsweise in pool01.contoso.Net befindet, sich aber als Bob@contoso.com in lync befindet, erstellen Sie eine interne DNS-Zone namens Contoso.com, und erstellen Sie darin eine DNS-a-und AAAA-Aufzeichnung (wenn IPv6-Adressierung verwendet wird) für pool01.contoso.com.

  - **PIN-Punkt-interne Zone**   Wenn Sie eine gesamte Zone im internen DNS erstellen, ist keine Option, können Sie Pin-Point-(dedizierte) Zonen erstellen, die den SRV-Einträgen entsprechen, die für die automatische Konfiguration erforderlich sind, und diese Zonen mit dnscmd. exe füllen. Dnscmd. exe ist erforderlich, da die DNS-Benutzeroberfläche das Erstellen von PIN-Punkt-Zonen nicht unterstützt. Wenn beispielsweise die SIP-Domäne contoso.com ist und Sie über einen Front-End-Pool mit dem Namen pool01 verfügen, der zwei Front-End-Server enthält, benötigen Sie die folgenden Pin-Punkt Zonen und eine Datensätze in Ihrem internen DNS:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Wenn Ihre Umgebung eine zweite SIP-Domäne (beispielsweise fabrikam.com) enthält, benötigen Sie die folgenden Pin-Punkt Zonen und Datensätze in Ihrem internen DNS:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> Der FQDN des Front-End-Pools wird zweimal angezeigt, jedoch mit zwei unterschiedlichen IP-Adressen. Dies liegt daran, dass der DNS-Lastenausgleich verwendet wird, aber wenn der Hardwarelastenausgleich verwendet wird, gibt es nur einen einzigen Front-End-Pool Eintrag. Außerdem ändern sich die FQDN-Werte des Front-End-Pools zwischen dem contoso.com-Beispiel und dem fabrikam.com-Beispiel, aber die IP-Adressen bleiben identisch. Dies liegt daran, dass Benutzer, die sich über eine der SIP-Domänen anmelden, denselben Front-End-Pool für die automatische Konfiguration verwenden.



</div>

Ausführliche Informationen finden Sie im DMTF-Blog Artikel "Automatische Communicator-Konfiguration und Split-Brain-DNS" [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)unter.

<div>


> [!NOTE]  
> Die Inhalte der Blogs und die zugehörige URL können ohne vorherige Ankündigung geändert werden.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Konfigurieren des DNS (Domain Name System) für die Disaster Recovery

Um DNS so zu konfigurieren, dass der Web-Traffic von lync Server 2013 auf Ihre Disaster Recovery-und Failover-Websites umgeleitet wird, müssen Sie einen DNS-Anbieter verwenden, der GeoDNS unterstützt. Sie können Ihre DNS-Einträge für Web so einrichten, dass die Disaster Recovery unterstützt wird, damit Features, die Webdienste verwenden, weiterhin verwendet werden, auch wenn ein ganzer Front-End-Pool ausfällt. Dieses Disaster Recovery-Feature unterstützt die AutoErmittlung (Lyncdiscover-URL), Besprechungen und Einwahl einfache URLs.

Sie definieren und konfigurieren zusätzliche DNS-Hosteinträge (A und AAAA bei Verwendung von IPv6) für die interne und externe Auflösung von Webdiensten bei Ihrem GeoDNS-Anbieter. Bei den folgenden Details wird davon ausgegangen, dass gepaarte Pools, geografisch verteilte und GeoDNS von Ihrem Anbieter entweder mit Round-Robin-DNS unterstützt oder für die Verwendung von pool1 als primäres Gerät konfiguriert sind, und ein Failover auf Pool2 bei einem Kommunikationsverlust oder einem Hardwarefehler durchführen.


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
<th>Pool Datensätze (Beispiel)</th>
<th>CNAME-Einträge (Beispiel)</th>
<th>DNS-Einstellungen (wählen Sie eine Option aus)</th>
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
<p>Verwenden von Primary, verbinden mit sekundärem, wenn Fehler</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Verwenden von Primary, verbinden mit sekundärem, wenn Fehler</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Verwenden von Primary, verbinden mit sekundärem, wenn Fehler</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Verwenden von Primary, verbinden mit sekundärem, wenn Fehler</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Verwenden von Primary, verbinden mit sekundärem, wenn Fehler</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Verwenden von Primary, verbinden mit sekundärem, wenn Fehler</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Verwenden von Primary, verbinden mit sekundärem, wenn Fehler</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Roundrobin zwischen Pools</p>
<p>Verwenden von Primary, verbinden mit sekundärem, wenn Fehler</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS Load Balancing

Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert. Die Anwendung (beispielsweise ein Client, auf dem lync ausgeführt wird) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem eine Verbindung mit einer der IP-Adressen hergestellt wird, die von der DNS a-und AAAA-Daten Satz Abfrage (wenn IPv6-Adressierung verwendet wird) für den vollqualifizierten Domänennamen (FQDN) des Pools zurückgegeben wird.

Wenn beispielsweise drei Front-End-Server in einem Pool mit dem Namen pool01.contoso.com vorhanden sind, geschieht Folgendes:

  - Clients, auf denen lync Query DNS für pool01.contoso.com ausgeführt wird. Die Abfrage gibt drei IP-Adressen zurück und speichert Sie wie folgt (nicht unbedingt in dieser Reihenfolge):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - Der Client versucht, eine TCP-Verbindung (Transmission Control Protocol) mit einer der IP-Adressen einzurichten. Wenn dies fehlschlägt, versucht der Client die nächste IP-Adresse im Cache.

  - Bei erfolgreicher TCP-Verbindung handelt der Client die Verwendung von TLS zur Verbindungsherstellung mit der primären Registrierung in „pool01.contoso.com“ aus.

  - Wenn der Client alle zwischengespeicherten Einträge ohne erfolgreiche Verbindung versucht, wird der Benutzer benachrichtigt, dass zurzeit keine Server mit lync Server 2013 zur Verfügung stehen.

<div>


> [!NOTE]  
> DNS-basierter Lastenausgleich unterscheidet sich von DNS-Round-Robin (DNS-RR), die sich normalerweise auf den Lastenausgleich bezieht, indem DNS eine andere Reihenfolge der IP-Adressen bereitstellt, die den Servern in einem Pool entsprechen. In der Regel aktiviert DNS-RR nur die Lastverteilung, aktiviert aber kein Failover. Wenn beispielsweise die Verbindung mit der einzigen IP-Adresse, die von der DNS-Abfrage a und AAAA zurückgegeben wird (wenn Sie eine IPv6-Adressierung verwenden) fehlschlägt, schlägt die Verbindung fehl. Aus diesem Grund ist DNS Round Robin selbst weniger zuverlässig als DNS-basierter Lastenausgleich. Sie können DNS Round Robin in Verbindung mit dem DNS-Lastenausgleich verwenden.



</div>

DNS-Lastenausgleich wird für Folgendes verwendet:

  - Lastenausgleich von Server-zu-Server-SIP auf die Edgeserver

  - Lastenausgleich für Unified Communications Application Services (UCAS)-Anwendungen wie automatische Konferenzzentrale, Reaktionsgruppe und Anruf Park

  - Verhindern neuer Verbindungen zu UCAS-Anwendungen (auch bekannt als "Draining")

  - Lastenausgleich für den gesamten Client-zu-Server-Datenverkehr zwischen Clients und Edgeserver

Der DNS-Lastenausgleich kann für Folgendes nicht verwendet werden:

  - Client-zu-Server-Webverkehr an Director-oder Front-End-Server

DNS-Load-Balancing und Federated-Traffic:

Wenn mehrere DNS-Einträge von einer DNS-SRV-Abfrage zurückgegeben werden, wählt der Access-Edgedienst immer den DNS-SRV-Eintrag mit der niedrigsten numerischen Priorität und dem höchsten numerischen Gewicht aus. Das Internet Engineering Task Force-Dokument "ein DNS-Eintrag für die Angabe des Standorts von Diensten ( <http://www.ietf.org/rfc/rfc2782.txt> DNS SRV)" gibt an, dass, wenn mehrere DNS-SRV-Einträge definiert sind, Priorität zuerst verwendet wird, und dann Gewicht. DNS-SRV-Eintrag a hat beispielsweise eine Gewichtung von 20 und eine Priorität von 40 und DNS-SRV-Eintrag B hat eine Gewichtung von 10 und eine Priorität von 50. DNS-SRV-Eintrag A mit Priorität 40 wird ausgewählt. Für die Auswahl des DNS-SRV-Eintrags gelten die folgenden Regeln:

  - Priorität wird zuerst berücksichtigt. Ein Client muss versuchen, den vom DNS-SRV-Eintrag definierten Ziel Host mit der niedrigsten nummerierten Priorität zu kontaktieren, die er erreichen kann. Ziele mit der gleichen Priorität sollten in einer Reihenfolge ausprobiert werden, die durch das gewichtungsfeld definiert ist.

  - Das Feld "Gewichtung" gibt eine relative Gewichtung für Einträge mit der gleichen Priorität an. Bei größeren gewichten sollte eine proportional höhere Wahrscheinlichkeit für die Auswahl angegeben werden. DNS-Administratoren sollten Weight 0 verwenden, wenn keine Serverauswahl vorhanden ist. In Anwesenheit von Datensätzen mit einer Gewichtung von mehr als 0 sollten Datensätze mit der Gewichtung 0 eine sehr geringe Wahrscheinlichkeit haben, ausgewählt zu werden.

Wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden, wählt der Access-Edgedienst den SRV-Eintrag aus, der zuerst vom DNS-Server empfangen wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

