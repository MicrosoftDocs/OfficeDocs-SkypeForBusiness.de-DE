---
title: 'Lync Server 2013: Ermitteln von DNS-Anforderungen'
TOCTitle: Ermitteln von DNS-Anforderungen
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398758(v=OCS.15)
ms:contentKeyID: 49294797
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ermitteln von DNS-Anforderungen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Anhand des folgenden Ablaufdiagramms können Sie die DNS-Anforderungen (Domain Name System) ermitteln.


> [!IMPORTANT]
> Microsoft Lync Server 2013 unterstützt die Verwendung von IPv6-Adressen. Damit Sie IPv6-Adressen verwenden können, müssen Sie auch IPv6-DNS unterstützen und DNS-Host-AAAA-Einträge konfigurieren. In Bereitstellungen, die sowohl IPv4 als auch IPv6 verwenden, konfigurieren Sie am besten Host-A-Einträge für IPv4 und Host-AAAA-Einträge für IPv6. Auch wenn Ihre Bereitstellung vollständig auf IPv6 umgestellt wurde, kann es vorkommen, dass IPv4-DNS-Host-Einträge weiterhin benötigt werden, wenn externe Benutzer IPv4 verwenden.



**Ablaufdiagramm zur Ermittlung der DNS-Anforderungen**

![Flussdiagramm zu DNS-Anforderungen](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "Flussdiagramm zu DNS-Anforderungen")


> [!IMPORTANT]
> Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Hostname. Der Topologie-Generator verwendet FQDNs und keine Hostnamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (also A-Z, a-z, 0-9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync&nbsp;Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS-Einträgen und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-dns-host-records.md">Konfigurieren von DNS-Hosteinträgen für Lync Server 2013</A>



## Ermittlung von Diensten durch Lync-Clients

Das Identifizieren von und der Zugriff auf Dienste in Lync Server 2013 durch Clients erfolgt in Microsoft Lync 2010, Lync 2013 und Lync Mobile auf ähnliche Weise. Eine deutliche Ausnahme bildet die Windows Store-App für Lync, für die ein Dienstidentifizierungsprozess verwendet wird. In diesem Abschnitt werden zwei Szenarien der Identifizierung von Diensten durch Clients erläutert; zunächst die herkömmliche Methode mit einer Reihe von SRV- und A-Host-Einträgen und dann die Methode, bei der nur die Einträge des AutoErmittlungsdiensts verwendet werden. Kumulative Updates für Desktopclients ändern den DNS-Identifikationsprozess in Lync Server 2010. Der DNS-Abfrageprozess wird für alle Clients fortgesetzt, bis eine erfolgreiche Abfrage zurückgegeben wird oder die Liste mit möglichen DNS-Einträgen vollständig überprüft wurde. Der endgültige Fehler wird dann an den Client zurückgegeben.

Für alle Clients **außer** die Windows Store-App für Lync werden beim DNS-Lookup werden SRV-Einträge abgefragt und in der folgenden Reihenfolge an den Client zurückgegeben:

1.  lyncdiscoverinternal. *\<domain\>*    Ein (Host)Eintrag für den AutoErmittlungsdienst in den internen Webdiensten

2.  lyncdiscover. *\<domain\>*    Ein (Host)Eintrag für den AutoErmittlungsdienst in den externen Webdiensten

3.  \_sipinternaltls.\_tcp. *\<domain\>*    SRV (Service Locator)-Eintrag für interne TLS-Verbindungen

4.  \_sipinternal.\_tcp. *\<domain\>*    SRV (Service Locator)-Eintrag für interne TCP-Verbindungen (sofern TCP zulässig ist)

5.  \_sip.\_tls. *\<domain\>*    SRV (Service Locator)-Eintrag für externe TLS-Verbindungen

6.  sipinternal. *\<domain\>*    Ein (Host)-Eintrag für den Front-End-Pool oder den Director, der nur im internen Netzwerk aufgelöst werden kann.

7.  sip. *\<domain\>*    Ein (Host)-Eintrag für den Front-End-Pool oder den Director im internen Netzwerk oder für den Zugriffs-Edgedienst bei externem Client

8.  sipexternal. *\<domain\>*    Ein (Host)-Eintrag für den Zugriffs-Edgedienst bei externem Client

Bei der Windows Store-App für Lync ist das Verfahren vollständig anders, da zwei Einträge verwendet werden:

1.  lyncdiscoverinternal. *\<domain\>*    Ein (Host)Eintrag für den AutoErmittlungsdienst in den internen Webdiensten

2.  lyncdiscover. *\<domain\>*    Ein (Host)Eintrag für den AutoErmittlungsdienst in den externen Webdiensten

Ein Ausweichen auf die anderen Eintragstypen ist nicht möglich.

Der Unterschied zwischen den Methoden für neuere Clients im Vergleich zu älteren besteht darin, dass der AutoErmittlungsdienst als bevorzugte Methode zum Identifizieren aller Dienste verwendet wird.

Ist eine Verbindung erfolgreich, gibt der AutoErmittlungsdienst alle Webdienste-URLs für den Home-Pool des Benutzers zurück, einschließlich der URLs für den Mobilitätsdienst (Mcx im virtuellen Verzeichnis, das in IIS für den Dienst erstellt wurde) und Microsoft Lync Web App-Webplaner. Jedoch ist sowohl die interne Mobilitätsdienst-URL als auch die externe Mobilitätsdienst-URL mit dem externen Webdienste-FQDN verbunden. Daher stellt das mobile Gerät (egal, ob es sich innerhalb oder außerhalb des Netzwerks befindet) immer extern über den Reverseproxy eine Verbindung mit dem Mobilitätsdienst her.

Wenn die kumulativen Updates für Lync Server 2013: Februar 2013 installiert wurden, gibt er AutoErmittlungsdienst auch Verweise auf Intern/UCWA, Extern/UCWA und UCWA zurück. Diese Einträge verweisen auf die Unified Communications Web API (UCWA)-Webkomponente. Derzeit wird nur der Eintrag "UCWA" verwendet und bietet einen Verweis auf eine URL für die Webkomponente. UCWA wird von Lync 2013 Mobile-Clients anstatt des von den Lync 2010 Mobile-Clients verwendeten Mobilitätsdiensts (Mcx) verwendet.


> [!NOTE]
> Beim Erstellen von SRV-Einträgen muss berücksichtigt werden, dass die Einträge auf einen DNS-A- oder DNS-AAAA-Eintrag (wenn Sie IPv6-Adressen nutzen) in derselben Domäne zeigen, in welcher der DNS-SRV-Eintrag erstellt wird. Wenn sich der SRV-Eintrag z.&nbsp;B. in der Domäne "contoso.com" befindet, kann sich der DNS-A- oder und DNS-AAAA-Eintrag (wenn Sie IPv6-Adressen nutzen), auf den er zeigt, nicht in der Domäne "fabrikam.com" befinden.




> [!TIP]
> Die Standardkonfiguration ermöglicht es, dass der Datenverkehr des mobilen Clients über die externe Website erfolgt. Sie können Einstellungen ändern, damit nur die interne URL zurückgegeben wird, wenn Sie dies bevorzugen. Bei dieser Konfiguration können Benutzer auf ihren mobilen Geräten mobile Lync-Anwendungen nur verwenden, wenn sie sich im Firmennetzwerk befinden. Zur Definition dieser Konfiguration müssen Sie das Cmdlet <STRONG>Set-CsMcxConfiguration</STRONG> ausführen.




> [!NOTE]
> Obwohl mobile Anwendungen auch eine Verbindung mit anderen Lync Server 2013-Diensten wie dem Adressbuchdienst herstellen können, werden interne Webanforderungen mobiler Anwendungen nur an den externen Web-FQDN für den Mobilitätsdienst geleitet. Für andere Dienstanforderungen, beispielsweise Adressbuchanforderungen, ist diese Konfiguration nicht erforderlich.



Mobile Geräte unterstützen die manuelle Ermittlung von Diensten. In diesem Fall muss jeder Benutzer in den Einstellungen des mobilen Geräts wie folgt die vollständigen internen und externen AutoErmittlungsdienst-URIs konfigurieren, einschließlich Protokoll und Pfad:

  - https:// *\<ExtPoolFQDN\>* /Autodiscover/autodiscoverservice.svc/Stamm für externen Zugriff

  - https:// *\<IntPoolFQDN\>* /AutoDiscover/AutoDiscover.svc/Stamm für internen Zugriff

Es wird empfohlen, die automatische Ermittlung anstelle der manuellen Ermittlung zu verwenden. Bei der Behandlung von Konnektivitätsproblemen mobiler Geräte sind manuelle Einstellungen jedoch gegebenenfalls nützlich.

## Konfigurieren von Split-Brain-DNS mit Lync Server

Für den Begriff Split-Brain-DNS gibt es verschiedene Namen, wie Split-DNS oder Split-Horizont-DNS. Es geht dabei einfach um eine DNS-Konfiguration mit zwei DNS-Zonen mit demselben Namespace, von denen eine jedoch nur interne Anforderungen bearbeitet und die andere nur externe. Eine Vielzahl der DNS-SRV- und DNS-A-Einträge in der internen DNS-Konfiguration sind jedoch nicht in der externen DNS-Konfiguration enthalten und umgekehrt. In Fällen, in denen ein DNS-Eintrag sowohl in der internen als auch in der externen DNS-Konfiguration vorhanden ist (z. B. "www.contoso.com"), werden abhängig vom Ursprung der DNS-Abfrage unterschiedliche IP-Adressen zurückgegeben.


> [!IMPORTANT]
> Split-Brain-DNS wird zurzeit für Mobilität, genauer gesagt für die LyncDiscover- und LyncDiscoverInternal-DNS-Einträge nicht unterstützt. "LyncDiscover" muss auf einem externen DNS-Server und "LyncDiscoverInternal" muss auf einem internen DNS-Server definiert werden.



Im Rahmen dieser Themen wird der Begriff Split-Brain-DNS verwendet.

Wenn Sie Split-Brain-DNS konfigurieren, umfassen die folgenden internen und externen Zonen eine Übersicht über die Typen von DNS-Einträgen, die in jeder Zone erforderlich sind. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Interne DNS-Konfiguration:**

  - Enthält eine DNS-Zone "contoso.com", für die die DNS-Konfiguration autoritativ ist

  - Die interne Zone "contoso.com" umfasst Folgendes:
    
      - DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) und SRV-Einträge für die automatische interne Lync Server 2013-Clientkonfiguration (optional)
    
      - DNS-A- und DNS-AAAA- (wenn Sie IPv6-Adressen nutzen) oder DNS-CNAME-Einträge für die automatische Ermittlung von Lync Server 2013-Webdiensten (optional)
    
      - DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) für Front-End-Pool-Name, Director oder Director-Pool-Name und alle internen Server mit Lync Server 2013 im Unternehmensnetzwerk
    
      - DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) für die interne Edgeschnittstelle der einzelnen Lync Server 2013-Edgeserver im Umkreisnetzwerk
    
      - DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) für die interne Schnittstelle der einzelnen Reverseproxyserver im Umkreisnetzwerk (optional für die Reverseproxyverwaltung)
    
      - Sämtliche internen Edgeschnittstellen der Lync Server 2013- Edgeserver im Umkreisnetzwerk verwenden die interne DNS-Zone, um die Abfragen an "contoso.com" aufzulösen
    
      - Alle Server und Clients im Unternehmensnetzwerk, auf denen Lync Server 2013 bzw. Lync 2013 ausgeführt wird, zeigen auf die internen DNS-Server, um Anfragen an contoso.com aufzulösen oder die HOSTS-Datei der einzelnen Edgeserver zu nutzen und A- und AAAA-Einträge (sofern Sie IPv6-Adressen verwenden) für den nächsten Hopserver aufzulisten - insbesondere den Director- oder Director VIP-, Front End Pool VIP- oder Standard Edition-Server

**Externe DNS-Konfiguration:**

  - Enthält eine DNS-Zone "contoso.com", für die die DNS-Konfiguration autoritativ ist

  - Die externe Zone "contoso.com" umfasst Folgendes:
    
      - DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) und SRV-Einträge für die automatische Lync Server 2013-Clientkonfiguration (optional)
    
      - DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) oder DNS-CNAME-Einträge für die automatische Ermittlung von Lync Server 2013-Webdiensten für die Mobilität
    
      - DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) sowie SRV-Einträge für die externe Edgeschnittstelle der einzelnen Lync Server 2013-Edgeserver oder die virtuelle IP (VIP) des Hardwaregeräts zum Lastenausgleich im Umkreisnetzwerk
    
      - DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) für die externe Schnittstelle der einzelnen Reverseproxyserver oder die VIP für einen Pool von Reverseproxyservern im Umkreisnetzwerk

## Automatische Konfiguration ohne Split-Brain-DNS

Bei Verwendung von Split-Brain-DNS kann ein Lync Server 2013-Benutzer, der sich intern anmeldet, die automatische Konfiguration nutzen, wenn die interne DNS-Zone einen SRV-Eintrag "\_sipinternaltls.\_tcp" für jede verwendete SIP-Domäne umfasst. Wenn Sie jedoch kein Split-Brain-DNS verwenden, ist die interne automatische Konfiguration von Clients, auf denen Lync ausgeführt wird, nur funktionsfähig, wenn Sie eine der weiter unten in diesem Abschnitt beschriebenen Problemumgehungen implementieren. Der Grund dafür ist, dass Lync Server 2013 den SIP-URI des Benutzers für den Abgleich der Domäne des Front-End-Pools benötigt, der für die automatische Konfiguration vorgesehen ist. Diese Anforderung muss auch in früheren Versionen von Communicator erfüllt werden.

Wenn Sie z. B. zwei SIP-Domänen verwenden, sind die zwei folgenden DNS-SRV-Einträge erforderlich:

  - Wenn sich ein Benutzer als "bob@contoso.com" anmeldet, kann der folgende SRV-Eintrag für die automatische Konfiguration verwendet werden, da die SIP-Domäne des Benutzers (contoso.com) mit der Domäne des Front-End-Pools für die automatische Konfiguration übereinstimmt:
    
     \_sipinternaltls.\_tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Wenn sich ein Benutzer als "alice@fabrikam.com" anmeldet, kann der folgende DNS-SRV-Eintrag für die automatische Konfiguration der zweiten SIP-Domäne verwendet werden.
    
     \_sipinternaltls.\_tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Zum Vergleich: wenn sich ein Benutzer als "tim@litwareinc.com" anmeldet, kann der folgende DNS-SRV-Eintrag nicht für die automatische Konfiguration verwendet werden, da die SIP-Domäne des Clients (litwareinc.com) nicht mit der Domäne des Pools (fabrikam.com) übereinstimmt:

 \_sipinternaltls.\_tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Wenn für Clients, auf denen Lync ausgeführt wird, die automatische Konfiguration erforderlich ist, wählen Sie eine der folgenden Optionen aus:

  - **Gruppenrichtlinienobjekte**   Verwenden Sie Gruppenrichtlinienobjekte zum Auffüllen der richtigen Serverwerte.
    

    > [!NOTE]
    > Mit dieser Option wird die automatische Konfiguration nicht aktiviert, der Prozess der manuellen Konfiguration wird jedoch automatisiert. Daher werden die SRV-Einträge für die automatische Konfiguration bei Verwendung dieses Ansatzes nicht benötigt.



  - **Übereinstimmende interne Zone**   Erstellen Sie eine interne DNS-Zone, die mit der externen DNS-Zone übereinstimmt (z. B. "contoso.com"), sowie DNS-A- und DNS-AAAA-Einträge (wenn Sie IPv6-Adressen nutzen) für den Lync Server 2013-Pool, der für die automatische Konfiguration verwendet wird. Beispiel: wenn ein Benutzer in "pool01.contoso.net" verwaltet wird, sich jedoch als "bob@contoso.com" bei Lync anmeldet, erstellen Sie eine interne DNS-Zone "contoso.com" und in dieser Zone einen DNS-A- und DNS-AAAA-Eintrag (wenn Sie IPv6-Adressen nutzen) für "pool01.contoso.com".

  - **Interne dedizierte Zone**   Wenn die Erstellung einer vollständigen internen DNS-Zone nicht möglich ist, können Sie dedizierte Zonen erstellen, die den für die automatische Konfiguration erforderlichen SRV-Einträgen entsprechen. Anschließend füllen Sie diese Zonen mithilfe von "dnscmd.exe" auf. "Dnscmd.exe" wird benötigt, da die Benutzeroberfläche für DNS das Erstellen von dedizierten Zonen nicht unterstützt. Beispiel: wenn die SIP-Domäne "contoso.com" lautet und Sie über einen Front-End-Pool "pool01" mit zwei Front-End-Servern verfügen, benötigen Sie die folgenden dedizierten Zonen und DNS-A-Einträge in Ihrem internen DNS:
    
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


> [!NOTE]
> Der FQDN des Front-End-Pools wird zweimal aufgeführt, jedoch mit unterschiedlichen IP-Adressen. Der Grund dafür ist, dass ein DNS-Lastenausgleich verwendet wird. Bei Verwendung von Hardwarelastenausgleich wäre nur ein einzelner Front-End-Pool-Eintrag vorhanden. Zudem weisen die Beispiele "contoso.com" und "fabrikam.com" unterschiedliche FQDN-Werte des Front-End-Pools auf, die IP-Adressen sind jedoch gleich. Der Grund dafür ist, dass Benutzer, die sich über eine der SIP-Domänen anmelden, denselben Front-End-Pool für die automatische Konfiguration verwenden.



Ausführliche Informationen finden Sie im DMTF-Blog-Artikel "Communicator Automatic Configuration and Split-Brain DNS" unter [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).


> [!NOTE]
> Die Inhalte der Blogs und die zugehörige URL können ohne vorherige Ankündigung geändert werden.



## Konfiguration des Domain Name Systems (DNS) für die Notfallwiederherstellung

Um DNS für die Umleitung des Lync Server 2013-Webdatenverkehrs an Ihre Notfallwiederherstellungs- und Failover-Sites zu konfigurieren, müssen Sie einen DNS-Anbieter nutzen, der GeoDNS unterstützt. Sie können Ihre DNS-Einträge für die Unterstützung der Notfallwiederherstellung für Web einrichten, damit Funktionen, die Webdienste verwenden, auch dann fortgesetzt werden, wenn ein gesamter Front-End-Pool ausfällt. Diese Notfallwiederherstellungsfunktion unterstützt AutoErmittlung (Lyncdiscover-URL), einfache URLs für Besprechungen und Einwahl.

Sie definieren und konfigurieren zusätzliche DNS-Host-Einträge (A und AAAA, wenn Sie IPv6 verwenden) für die interne und externe Auflösung von Webdiensten bei Ihrem GeoDNS-Anbieter. Die folgenden Beispiele gehen von kombinierten Pools aus, die geografisch zerstreut sind, und dass Ihr Anbieter GeoDNS entweder mit Roundrobin-DNS unterstützt, oder dass es für die Verwendung von Pool1 als primären Pool und Failover nach Pool2 konfiguriert ist, falls die Kommunikation abbricht oder die Hardware ausfällt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>GeoDNS-Datensatz (Beispiel)</th>
<th>Pooldatensätze (Beispiel)</th>
<th>CNAME-Datensätze (Beispiel)</th>
<th>DNS-Einstellungen (wählen Sie eine Option aus)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin zwischen Pools</p>
<p>Primäre verwenden, bei Fehler mit der sekundären verbinden</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin zwischen Pools</p>
<p>Primäre verwenden, bei Fehler mit der sekundären verbinden</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin zwischen Pools</p>
<p>Primäre verwenden, bei Fehler mit der sekundären verbinden</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin zwischen Pools</p>
<p>Primäre verwenden, bei Fehler mit der sekundären verbinden</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin zwischen Pools</p>
<p>Primäre verwenden, bei Fehler mit der sekundären verbinden</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin zwischen Pools</p>
<p>Primäre verwenden, bei Fehler mit der sekundären verbinden</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com Alias für Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com Alias für Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin zwischen Pools</p>
<p>Primäre verwenden, bei Fehler mit der sekundären verbinden</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com Alias für Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com Alias für Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin zwischen Pools</p>
<p>Primäre verwenden, bei Fehler mit der sekundären verbinden</p></td>
</tr>
</tbody>
</table>


## DNS-Lastenausgleich

Der DNS-Lastenausgleich wird typischerweise auf Anwendungsebene implementiert. Die Anwendung (z. B. ein Client, auf dem Lync ausgeführt wird) versucht, eine Verbindung mit einem Poolserver herzustellen. Hierzu wird eine der IP-Adressen verwendet, die über die DNS-A- und DNS-AAAA-Abfrage (wenn Sie IPv6-Adressen nutzen) für den FQDN des Pools zurückgegeben wurden.

Wenn z. B. drei Front-End-Server im Pool "pool01.contoso.com" vorhanden sind, werden folgende Schritte ausgeführt:

  - Der Client, auf dem Lync ausgeführt wird, sendet eine DNS-Abfrage für "pool01.contoso.com". Die Anfrage gibt drei IP-Adressen zurück und speichert diese wie folgt im Zwischenspeicher (nicht unbedingt in dieser Reihenfolge):
    
    pool01.contoso.com      192.168.10.90
    
    pool01.contoso.com      192.168.10.91
    
    pool01.contoso.com      192.168.10.92

  - Der Client versucht, eine TCP-Verbindung (Transmission Control Protocol) mit einer der IP-Adressen herzustellen. Ist dies nicht möglich, versucht der Client, eine Verbindung mit der nächsten IP-Adresse im Zwischenspeicher herzustellen.

  - Bei erfolgreicher TCP-Verbindung handelt der Client die Verwendung von TLS zur Verbindungsherstellung mit der primären Registrierung in "pool01.contos.com" aus.

  - Wenn der Client mit keinem der zwischengespeicherten Einträge eine Verbindung herstellen kann, wird der Benutzer darüber informiert, dass gegenwärtig keine Server mit Lync Server 2013 verfügbar sind.


> [!NOTE]
> Der DNS-basierte Lastenausgleich unterscheidet sich von DNS-Roundrobin (DNS RR). Dieser letztgenannte Mechanismus bezieht sich typischerweise auf einen Lastenausgleich, bei dem DNS zur Bereitstellung einer anderen Reihenfolge von IP-Adressen für die Server in einem Pool eingesetzt wird. Mit DNS RR ist typischerweise nur ein Lastenausgleich, jedoch kein Failover möglich. Wenn die Verbindung mit der IP-Adresse, die über die DNS-A- und DNS-AAAA-Abfrage (wenn Sie IPv6-Adressen nutzen) zurückgegeben wurde, nicht hergestellt werden kann, tritt für die Verbindungsherstellung ein Fehler auf. Daher ist DNS-Roundrobin allein weniger zuverlässig als der DNS-basierte Lastenausgleich. Sie können DNS-Roundrobin gemeinsam mit dem DNS-Lastenausgleich verwenden.



DNS-Lastenausgleich wird für folgende Szenarien eingesetzt:

  - Lastenausgleich zwischen SIP- und Edgeservern

  - Lastenausgleich für Anwendungen der Unified Communications-Anwendungsdienste, z. B. automatische Konferenzzentrale, Reaktionsgruppen und die Anwendung zum Parken von Anrufen

  - Verhindern neuer Verbindungen mit Anwendungen der Unified Communications-Anwendungsdienste (auch als "Serverausgleich" bezeichnet)

  - Lastenausgleich für den gesamten Datenverkehr zwischen Clients und Edgeservern

DNS-Lastenausgleich kann für folgende Szenarien nicht eingesetzt werden:

  - Webdatenverkehr zu Director oder Front-End-Servern

DNS-Lastenausgleich und Datenverkehr im Partnerverbund:

Wenn eine DNS-SRV-Abfrage mehrere DNS-Einträge zurückgibt, wählt der Zugriffs-Edgedienst immer den DNS-SRV-Eintrag aus, dessen Priorität durch die kleinste Zahl und dessen Gewichtung durch die größte Zahl gekennzeichnet ist. Im Dokument "A DNS RR for specifying the location of services (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> der Internet Engineering Task Force ist angegeben, dass bei mehreren definierten DNS-SRV-Einträgen zuerst die Priorität und dann die Gewichtung verwendet wird. Angenommen, DNS-SRV-Eintrag A hat eine Gewichtung von 20 und eine Priorität von 40, und DNS-SRV-Eintrag B hat eine Gewichtung von 10 und eine Priorität von 50. DNS-SRV-Eintrag A mit Priorität 40 wird ausgewählt. Für die Auswahl von DNS-SRV-Einträgen gelten folgende Regeln:

  - Die Priorität wird zuerst berücksichtigt. Ein Client MUSS versuchen, den Zielhost zu kontaktieren, der vom DNS-SRV-Eintrag mit der niedrigsten Prioritätszahl definiert ist, der erreicht werden kann. Ziele mit derselben Priorität SOLLTEN in einer durch das Gewichtungsfeld definierten Reihenfolge zu kontaktieren versucht werden.

  - Das Gewichtungsfeld gibt eine relative Gewichtung für Einträge mit derselben Priorität an. Größere Gewichtungen SOLLTEN mit proportional höherer Wahrscheinlichkeit gewählt werden. DNS-Administratoren SOLLTEN eine Gewichtung von 0 verwenden, wenn keine Serverauswahl getroffen werden muss. Wenn Server mit größeren Gewichtungen als 0 vorhanden sind, werden Einträge mit der Gewichtung 0 höchstwahrscheinlich nicht ausgewählt.

Wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden, wählt der Zugriffs-Edgedienst den SRV-Eintrag aus, der zuerst vom DNS-Server empfangen wurde.

