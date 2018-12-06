---
title: 'Lync Server 2013: Technische Anforderungen für die Mobilität'
TOCTitle: Technische Anforderungen für die Mobilität
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690030(v=OCS.15)
ms:contentKeyID: 49294593
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für die Mobilität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Für mobile Benutzer müssen in den mobilen Anwendungen verschiedene Szenarien unterstützt werden, die eine besondere Planung erfordern. Ein Benutzer kann beispielsweise eine mobile Anwendung von außerhalb des Arbeitsplatzes aufrufen, indem er über das 3G-Netzwerk eine Verbindung herstellt, und dann beim Eintreffen am Arbeitsplatz wieder zum WLAN-Netzwerk wechseln. Beim Verlassen des Gebäudes kehrt er dann wieder zum 3G-Netzwerk zurück. Sie müssen die Umgebung entsprechend planen, um solche Netzwerkübergänge zu unterstützen und ein konsistentes Benutzererlebnis zu ermöglichen. In diesem Abschnitt werden die Infrastrukturanforderungen beschrieben, die Sie erfüllen müssen, um mobile Anwendungen und die automatische Ermittlung von Mobilitätsressourcen zu unterstützen.


> [!NOTE]
> Obwohl mobile Anwendungen auch eine Verbindung mit anderen Lync Server 2013-Diensten herstellen können, gilt die Anforderung, alle Webanforderungen mobiler Anwendungen an denselben externen Web-FQDN (vollqualifizierten Domänennamen) zu senden, nur für den Lync Server 2013-Mobilitätsdienst. Für andere Mobilitätsdienste ist diese Konfiguration nicht erforderlich.



Die Anforderungen an die Cookieaffinität für Hardwaregeräte zum Lastenausgleich wurde erheblich reduziert. Außerdem ersetzen Sie die TCP (Transmission Control-Protokoll)-Affinität, wenn Sie die in Lync Server 2013 enthaltene Anwendung Lync Mobile nutzen. Die Cookieaffinität kann weiterhin verwendet werden, für den Webdienst ist sie allerdings nicht mehr erforderlich.


> [!IMPORTANT]
> Der gesamte Mobilitätsdienst-Datenverkehr wird durch den Reverseproxy geleitet. Hierbei spielt es keine Rolle, ob ein externer oder interner Ursprungspunkt vorliegt. Bei der Verwendung eines einzelnen oder einer Farm an Reverseproxys oder eines Geräts, das die Funktion eines Reverseproxys bereitstellt, kann ein Problem auftreten, bei dem der interne Datenverkehr eine Schnittstelle verlässt und unverzüglich versucht, an derselben Schnittstelle wieder einzugehen. Dies führt häufig zu einer Sicherheitsregelverletzung, die als "TCP-Paketspoofing" oder einfach als "Spoofing" bezeichnet wird. <EM>Hairpinning</EM> (das Verlassen und sofortige Wiedereingehen eines Pakets oder einer Paketserie) muss erlaubt sein, damit der Mobilitätsdienst funktioniert. Eine Lösung für dieses Problem besteht in der Verwendung eines Reverseproxys, der von der Firewall getrennt ist (die Regel zum Verhindern von Spoofing sollte an der Firewall immer erzwungen werden). Ein Hairpin kann dann problemlos an der externen Schnittstelle des Reverseproxys statt an der externen Schnittstelle der Firewall erfolgen. Sie erkennen das Spoofing an der Firewall und lockern die Regel am Reverseproxy; dadurch wird der von Mobilitätsdienst erforderte Hairpin zugelassen.<BR>Sie sollten demnach die DNS (Domain Name System)-Host- oder CNAME-Einträge verwenden, um den Reverseproxy für das Hairpin-Verhalten zu definieren (nicht die Firewall), sofern dies möglich ist.



Lync Server 2013 unterstützt Mobilitätsdienste für Lync 2010 Mobile und Lync 2013 Mobile-Clients. Beide Clients verwenden den Lync Server 2013-AutoErmittlungsdienst, um den Mobilitätseinstiegspunkt zu finden; die verwendeten Mobilitätsdienste unterscheiden sich jedoch. Lync 2010 Mobile verwendet den Mobilitätsdienst *Mcx* , der mit dem kumulativen Update für Lync Server 2010: November 2011 eingeführt wurde. Lync 2013 Mobile-Clients verwenden die Unified Communications Web-API oder *UCWA* als Mobilitätsdienstanbieter.

## Interne und externe DNS-Konfiguration

Der Mcx-Mobilitätsdienst (eingeführt mit dem kumulativen Update für Lync Server 2010: November 2011) und UCWA (eingeführt mit den kumulativen Updates für Lync Server 2013: Februar 2013) verwenden DNS auf die gleiche Weise.

Wenn Sie die automatische Ermittlung verwenden, suchen mobile Geräte über das DNS nach Ressourcen. Bei der DNS-Suche wird zuerst versucht, eine Verbindung mit dem FQDN herzustellen, der mit dem internen DNS-Eintrag verknüpft ist (lyncdiscoverinternal.*\<internal domain name\>*). Wenn mit dem internen DNS-Eintrag keine Verbindung hergestellt werden kann, wird versucht, mit dem externen DNS-Eintrag (lyncdiscover.*\<sipdomain\>*) eine Verbindung herzustellen. Ein mobiles Gerät, das sich im Netzwerk befindet, stellt eine Verbindung mit der internen URL des AutoErmittlungsdiensts her. Ein mobiles Gerät, das sich außerhalb des Netzwerks befindet, stellt eine Verbindung mit der externen URL des AutoErmittlungsdiensts her. Externe AutoErmittlungsanforderungen werden über den Reverseproxy geleitet. Der Lync Server 2013-AutoErmittlungsdienst gibt alle Webdienste-URLs für den Home-Pool des Benutzers zurück, einschließlich der Mobilitätsdienst-URLs (Mcx und UCWA). Jedoch ist sowohl die interne Mobilitätsdienst-URL als auch die externe Mobilitätsdienst-URL dem externen Webdienste-FQDN zugeordnet. Daher stellt das mobile Gerät (egal, ob es sich innerhalb oder außerhalb des Netzwerks befindet) immer extern über den Reverseproxy eine Verbindung mit dem Lync Server 2013-Mobilitätsdienst her.


> [!NOTE]
> Es ist zu beachten, dass Ihre Bereitstellung aus mehreren unterschiedlichen Namespaces für die interne und externe Verwendung bestehen kann. Ihr SIP-Domänenname kann vom Domänennamen für die interne Bereitstellung abweichen. Beispielsweise kann Ihre SIP-Domäne <STRONG>contoso.com</STRONG> und Ihre interne Bereitstellung <STRONG>contoso.net</STRONG> lauten. Benutzer, die sich bei Lync Server anmelden, verwenden den SIP-Domänennamen, wie zum Beispiel <STRONG>john@contoso.com</STRONG>. Beim Zugriff auf externe Webdienste (im Topologie-Generator als <STRONG>Externe Webdienste</STRONG> definiert), stimmen Domänenname und SIP-Domänenname überein, wie im DNS definiert. Beim Zugriff auf interne Webdienste (in Topologie-Generator als <STRONG>interne Webdienste</STRONG> definiert) ist der Standardname des internen Webdiensts der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) eines Front-End-Servers, Front-End-Pools, Directors oder Directorpools. Sie haben die Möglichkeit, den Namen des internen Webdiensts außer Kraft zu setzen. Sie sollten den internen Domänennamen (und nicht den SIP-Domänennamen) für interne Webdienste verwenden und den außer Kraft gesetzten Namen im DNS-A-Eintrag (oder für IPv6 AAAA) für den Host reflektieren. Der standardmäßige FQDN für interne Webdienste lautet zum Beispiel <STRONG>pool01.contoso.net</STRONG> und der außer Kraft gesetzte FQDN für interne Webdienste <STRONG>webpool.contoso.net</STRONG>. Wenn Sie die Webdienste auf diese Weise definieren, können Sie sicherstellen, dass der interne und externe Ort der Dienste berücksichtigt wird und nicht der des Benutzers, der diese Dienste in Anspruch nimmt.<BR>Da die Webdienste jedoch im Topologie-Generator definiert sind und der Name der internen Webdienste außer Kraft gesetzt werden kann, können Sie die internen Webdienste mit jedem beliebigen Domänennamen (einschließlich des SIP-Domänennamens) definieren, sofern der resultierende Name des Webdiensts, das zur Validierung verwendete Zertifikat und die definierenden DNS-Einträge konsistent sind. Letztendlich wird die Auflösung des Namens in die IP-Adresse durch die DNS-Einträge und einen konsistenten Namespace bestimmt.<BR>Für dieses Thema und seine Beispiele wird der interne Domänenname verwendet, um die Topologie und die DNS-Definitionen zu illustrieren.



Das folgende Diagramm veranschaulicht den Ablauf der Webanforderungen mobiler Anwendungen für den Mobilitätsdienst und den AutoErmittlungsdienst bei der Verwendung einer internen und externen DNS-Konfiguration.

**Mobilitätsdienstablauf mit AutoErmittlung**

![Fluss der Mobilitätsanforderung](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "Fluss der Mobilitätsanforderung")


> [!NOTE]
> Das Diagram veranschaulicht generische Webdienste. Ein virtuelles Verzeichnis mit dem Namen "Mobility" zeigt die Mobilitätsdienste Mcx und/oder UCWA. Wenn Sie die kumulativen Updates für Lync Server&nbsp;2013: Februar&nbsp;2013 nicht installiert haben, ist das virtuelle Verzeichnis "Ucwa" in Ihren internen und externen Webdiensten möglicherweise nicht definiert. Das virtuelle Verzeichnis "Autodiscover" ist definitiv und das virtuelle Verzeichnis "Mcx" vielleicht vorhanden.<BR>Die Funktionsweise der AutoErmittlung und der Ermittlung von Diensten ist unabhängig von der bereitgestellten Mobilitätsdiensttechnologie gleich.



Die internen und externen Web-FQDNs müssen einige Voraussetzungen erfüllen, um mobile Benutzer sowohl von innerhalb als auch außerhalb des Firmennetzwerks zu unterstützen. Zudem müssen möglicherweise andere Anforderungen erfüllt werden, je nachdem, welche Features implementiert werden sollen:

  - Neue DNS-, CNAME- oder A-Einträge (Host für IPV6 AAAA) für die automatische Ermittlung

  - Neue Firewallregel, wenn Pushbenachrichtigungen über das WLAN-Netzwerk unterstützt werden sollen

  - Alternative Antragstellernamen für interne Serverzertifikate und Reverseproxyzertifikate für die automatische Ermittlung

  - Änderungen an der Konfiguration des Front-End-Server-Hardwaregeräts zum Lastenausgleich für die Quellaffinität

Die Topologie muss die folgenden Anforderungen erfüllen, um den Mobilitätsdienst und AutoErmittlungsdienst zu unterstützen:

  - Der interne Front-End-Pool-Web-FQDN muss sich vom externen Front-End-Pool-Web-FQDN unterscheiden.

  - Auf den internen Web-FQDN darf nur von innerhalb des Firmennetzwerks zugegriffen werden. Zudem darf der interne Web-FQDN nur in eine Firmennetzwerkadresse aufgelöst werden.

  - Auf den externen Web-FQDN darf nur vom Internet aus zugegriffen werden. Zudem darf der externe Web-FQDN nur in eine Internetadresse aufgelöst werden.

  - Für Benutzer, die sich innerhalb des Firmennetzwerks befinden, muss die Mobilitätsdienst-URL an den externen Web-FQDN adressiert werden. Diese Anforderung gilt für den Mobilitätsdienst und betrifft nur diese URL.

  - Für Benutzer, die sich außerhalb des Firmennetzwerks befinden, muss die Anforderung an den externen Web-FQDN des Front-End-Pools oder Directors gerichtet werden.

Zur Unterstützung der AutoErmittlung müssen Sie für jede SIP-Domäne die folgenden DNS-Einträge erstellen:

  - Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen

  - Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen

Die interne AutoErmittlung-URL sollte nicht von außerhalb des Netzwerks adressierbar sein. Die externe AutoErmittlung-URL sollte nicht von innerhalb des Netzwerks adressierbar sein. Wenn Sie diese Anforderung für die externe URL nicht erfüllen können, werden die Funktionen des mobilen Clients wahrscheinlich nicht dadurch beeinträchtigt, da immer zuerst versucht wird, eine Verbindung mit der internen URL herzustellen.

Bei den DNS-Einträgen kann es sich entweder um A-Einträge (Host für IPV6 AAAA) oder um CNAME-Einträge handeln.


> [!NOTE]
> Clients mobiler Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) von verschiedenen Domänen. Daher wird die CNAME-Umleitung an verschiedene Domänen nicht über HTTPS unterstützt. Beispielsweise wird ein DNS-CNAME-Eintrag für "lyncdiscover.contoso.com", der eine Weiterleitung an eine Adresse von "director.contoso.net" vornimmt, nicht über HTTPS unterstützt. In einer solchen Topologie muss ein Client für ein mobiles Gerät HTTP für die erste Anforderung verwenden, sodass die CNAME-Umleitung über HTTP aufgelöst wird. Für die nachfolgenden Anforderungen wird dann HTTPS verwendet. Um dieses Szenario zu unterstützen, müssen Sie den Reverseproxy mit einer Webveröffentlichungsregel für Port&nbsp;80 (HTTP) konfigurieren. Ausführliche Informationen finden Sie unter "So erstellen Sie eine Webveröffentlichungsregel für Port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013</A>.<BR>Die CNAME-Umleitung an dieselbe Domäne wird über HTTPS unterstützt. In diesem Fall deckt das Zertifikat der Zieldomäne die ursprüngliche Domäne ab.



Ausführliche Informationen zu den für Ihr Szenario erforderlichen DNS-Einträgen finden Sie unter [DNS-Zusammenfassung – AutoErmittlung in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

## Port- und Firewallanforderungen

Wenn Sie Pushbenachrichtigungen unterstützen und möchten, dass mobile Apple-Geräte Pushbenachrichtigungen über das WLAN-Netzwerk empfangen, müssen Sie auch Port 5223 im WLAN-Netzwerk des Unternehmens öffnen. Port 5223 ist ein ausgehender TCP-Port, der vom Apple Push Notification Service (APNS) verwendet wird. Das mobile Gerät initiiert die Verbindung. Ausführliche Informationen finden Sie unter [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629?viewlocale=de_de).


> [!WARNING]
> Ein Apple-Gerät, das den Lync 2013&nbsp;Mobile-Client verwendet, erfordert keine Pushbenachrichtigungen.



Beachten Sie: Wenn ein Benutzer sich in einer Survivable Branch Appliance (SBA) befindet, sind die folgenden Ports erforderlich:

  - UcwaSipExternalListeningPort erfordert Port 5088

  - UcwaSipPrimaryListeningPort erfordert Port 5089

Zusätzliche Informationen sowie Anweisungen zu Port- und Protokollanforderungen für die AutoErmittlung finden Sie unter [Portübersicht – AutoErmittlung in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

## Zertifikatanforderungen

Wenn Sie die automatische Ermittlung für mobile Lync-Clients unterstützen, müssen Sie die Listen der alternativen Antragstellernamen für Zertifikate ändern, um sichere Verbindungen von mobilen Clients zu unterstützen. Sie müssen neue Zertifikate anfordern und zuweisen und für jeden Front-End-Server und Director, auf dem der AutoErmittlungsdienst ausgeführt wird, die in diesem Abschnitt beschriebenen Einträge für alternative Antragstellernamen hinzufügen. Es wird empfohlen, auch die Listen der alternativen Antragstellernamen für die Zertifikate der Reverseproxys zu ändern. Sie müssen die Einträge für den alternativen Antragstellernamen für jede SIP-Domäne in der Organisation hinzufügen.

Das erneute Ausstellen von Zertifikaten durch eine interne Zertifizierungsstelle ist normalerweise ein einfacher Vorgang. Das Hinzufügen mehrerer Einträge für alternative Antragstellernamen zu öffentlichen Zertifikaten, die vom Reverseproxy verwendet werden, kann jedoch aufwendig sein. Wenn Sie über viele SIP-Domänen verfügen und das Hinzufügen alternativer Antragstellernamen daher sehr zeitaufwendig ist, können Sie den Reverseproxy so konfigurieren, dass die anfängliche AutoErmittlungsdienst-Anforderung über Port 80 mit HTTP erfolgt und nicht über 443 mit HTTPS (Standardkonfiguration). Die Anforderung wird dann an den Port 8080 auf dem Director oder Front-End-Pool umgeleitet. Wenn Sie die anfängliche AutoErmittlungsdienst-Anforderung an Port 80 veröffentlichen, müssen Sie die Zertifikate für den Reverseproxy nicht ändern, da die Anforderung HTTP anstatt HTTPS verwendet. Dieser Ansatz wird unterstützt, aber nicht empfohlen.

## IIS-Anforderungen (Internetinformationsdienste)

Für die Mobilität wird die Verwendung von IIS 7.5, IIS 8.0 oder IIS 8.5 empfohlen. Der Mobilitätsdienst-Installer legt zur Leistungsverbesserung einige ASP.NET-Kennzeichen fest. IIS 7.5 ist standardmäßig unter Windows Server 2008 R2, IIS 8.0 unter Windows Server 2012 und IIS 8.50 unter Windows Server 2012 R2 installiert. Der Mobilitätsdienst-Installer ändert die ASP.NET-Einstellungen automatisch.

## Anforderungen an das Hardwaregerät zum Lastenausgleich

Auf dem Hardwaregerät zum Lastenausgleich, das den Front-End-Pool unterstützt, müssen die virtuellen IPs (VIPs) der externen Webdienste für die Quelle konfiguriert werden. Die Quellaffinität stellt sicher, dass mehrere Verbindungen von einem einzelnen Client zur Beibehaltung des Sitzungsstatus an einen einzigen Server gesendet werden. Ausführliche Informationen zu den Affinitätsanforderungen finden Sie unter [Anforderungen an den Lastenausgleich für Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Wenn Sie mobile Lync-Clients nur über das interne WLAN-Netzwerk unterstützen möchten, sollten Sie die internen Webdienste-VIPs für die Quelle konfigurieren, so wie oben für externe Webdienste-VIPs beschrieben. In dieser Situation sollten Sie "source\_addr" (Quelladressenaffinität oder TCP-Affinität) für die internen Webdienste-VIPs auf dem Hardwaregerät zum Lastenausgleich verwenden. Ausführliche Informationen finden Sie unter [Anforderungen an den Lastenausgleich für Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

## Reverseproxyanforderungen

Wenn Sie die automatische Ermittlung für mobile Lync-Clients unterstützen, müssen Sie wie folgt eine neue Webveröffentlichungsregel erstellen:

  - Wenn Sie sich entscheiden, die Listen der alternativen Antragstellernamen in den Reverseproxyzertifikaten zu aktualisieren und HTTPS für die anfängliche AutoErmittlungsdienst-Anforderung zu verwenden, müssen Sie die Webveröffentlichungsregel für "lyncdiscover.*\<sipdomain\>*" aktualisieren. Typischerweise ist dies mit der Veröffentlichungsregel für die externe Webdienste-URL auf dem Front-End-Pool kombiniert.

  - Wenn Sie HTTP für die anfängliche AutoErmittlungsdienst-Anforderungen verwenden möchten, damit die Liste der alternativen Antragstellernamen in den Reverseproxyzertifikaten nicht aktualisiert werden muss, müssen Sie eine Webveröffentlichungsregel für Port HTTP/TCP 80 erstellen, sofern dieser noch nicht vorhanden ist. Wenn bereits eine Regel für HTTP/TCP 80 existiert, können Sie diese Regel so aktualisieren, dass der Eintrag "lyncdiscover.*\<sipdomain\>*" enthalten ist.

