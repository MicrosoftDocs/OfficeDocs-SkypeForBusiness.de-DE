---
title: 'Lync Server 2013: Technische Anforderungen für die Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4eef2cb185653446627fe6ccec2d49538e1162b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Technische Anforderungen für die Mobilität in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Mobile Benutzer stoßen auf verschiedene Szenarien für mobile Anwendungen, die spezielle Planung erfordern. So kann beispielsweise jemand eine mobile Anwendung während einer Abwesenheitszeit verwenden, indem er über das 3G-Netzwerk eine Verbindung herstellt und dann bei der Arbeit zum Firmen-Wi-Fi-Netzwerk wechselt und dann zurück zum 3G wechselt, wenn man das Gebäude verlässt. Sie müssen Ihre Umgebung planen, um solche Netzwerk Übergänge zu unterstützen und eine konsistente Benutzererfahrung zu gewährleisten. In diesem Abschnitt werden die Infrastrukturanforderungen beschrieben, die Sie zur Unterstützung mobiler Anwendungen und zur automatischen Ermittlung von mobilitätsressourcen benötigen.

<div>


> [!NOTE]  
> Obwohl mobile Anwendungen auch eine Verbindung mit anderen lync Server 2013-Diensten herstellen können, gilt die Anforderung zum Senden aller Webanforderungen für mobile Anwendungen an denselben externen Web-vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) nur für den lync Server 2013-Mobilitätsdienst. Für andere Mobilitätsdienste ist diese Konfiguration nicht erforderlich.



</div>

Die Anforderung für die Cookie-Affinität in Hardwarelastenausgleichs wird drastisch reduziert, und Sie ersetzen die TCP-Affinität (Transmission Control Protocol), wenn Sie das mit lync Server 2013 gelieferte lync Mobile verwenden. Die Cookie-Affinität kann weiterhin verwendet werden, die Webdienste werden aber nicht mehr benötigt.

<div>


> [!IMPORTANT]  
> Der gesamte Mobilitätsdienst Verkehr durchläuft den Reverse-Proxy, unabhängig davon, wo sich der Ursprungspunkt befindet – intern oder extern. Im Fall eines einzelnen Reverse-Proxys oder einer Farm von Reverse-Proxies oder eines Geräts, das die Reverse-Proxy-Funktion bereitstellt, kann ein Problem auftreten, wenn der interne Datenverkehr über eine Schnittstelle egressing und versucht, sofort auf derselben Schnittstelle zu ingresen. Dies führt häufig zu einer Sicherheitsregel Verletzung, die als TCP-Paket-Spoofing oder nur Spoofing bezeichnet wird. Das <EM>Anheften von Haaren</EM> (das Ausstiegs-und das sofortige Eindringen eines Pakets oder einer Reihe von Paketen) muss zulässig sein, damit die Mobilität funktionieren kann. Eine Möglichkeit zur Behebung dieses Problems besteht in der Verwendung eines umgekehrten Proxys, der von der Firewall getrennt ist (die Spoofing-Präventions Regel sollte immer für Sicherheitszwecke in der Firewall erzwungen werden). Die Haarnadel kann an der externen Schnittstelle des Reverse-Proxy statt der externen Firewall-Schnittstelle erfolgen. Sie erkennen die Spoofing-Funktion bei der Firewall und entspannen die Regel beim Reverse-Proxy, wodurch die Haarnadel für Mobilität erforderlich ist.<BR>Verwenden Sie den DNS-Host (Domain Name System) oder CNAME-Einträge, um den Reverseproxy für das Haarnadel-Verhalten (nicht für die Firewall) zu definieren, wenn dies überhaupt möglich ist.



</div>

Lync Server 2013 unterstützt Mobilitätsdienste für Mobile lync 2010 Mobile-und lync 2013-Clients. Beide Clients verwenden den lync Server 2013-AutoErmittlungsdienst, um den Mobilitäts Einstiegspunkt zu finden, unterscheiden sich jedoch von dem von Ihnen verwendeten Mobilitätsdienst. Lync 2010 Mobile verwendet den Mobilitätsdienst, der als *MCX*bekannt ist und mit dem kumulativen Update für lync Server 2010: November 2011 eingeführt wurde. Mobile lync 2013-Clients verwenden die Unified Communications Web-API oder *UCWA*als Mobilitätsdienst Anbieter.

<div>

## <a name="internal-and-external-dns-configuration"></a>Interne und externe DNS-Konfiguration

Die Mobilitätsdienste MCX (mit dem kumulativen Update für lync Server 2010: November 2011) und UCWA (eingeführt in den kumulativen Updates für lync Server 2013: Februar 2013) verwenden DNS auf die gleiche Weise.

Wenn Sie die automatische Ermittlung verwenden, verwenden mobile Geräte DNS zum Auffinden von Ressourcen. Während des DNS-Lookups wird zuerst eine Verbindung mit dem FQDN versucht, der dem internen DNS-Eintrag zugeordnet ist (\< lyncdiscoverinternal. Interner Domänenname\>). Wenn eine Verbindung nicht mithilfe des internen DNS-Eintrags hergestellt werden kann, wird eine Verbindung mithilfe des externen DNS-Eintrags versucht\< (lyncdiscover. sipdomain\>). Ein mobiles Gerät, das für das Netzwerk intern ist, stellt eine Verbindung mit der internen AutoErmittlungsdienst-URL her, und ein mobiles Gerät, das sich außerhalb des Netzwerks befindet, stellt eine Verbindung mit der URL des externen AutoErmittlungsdiensts her. Externe Auto Ermittlungsanforderungen durchlaufen den Reverse-Proxy. Der lync Server 2013-AutoErmittlungsdienst gibt alle Webdienste-URLs für den privaten Pool des Benutzers zurück, einschließlich der Mobility Service-URLs (MCX und UCWA). Die URL für den internen Mobilitätsdienst und die URL für den externen Mobilitätsdienst sind jedoch mit dem FQDN der externen Webdienste verbunden. Unabhängig davon, ob ein mobiles Gerät intern oder extern für das Netzwerk ist, stellt das Gerät daher immer extern über den Reverse-Proxy eine Verbindung mit dem lync Server 2013-Mobilitätsdienst her.

<div>


> [!NOTE]  
> Es ist wichtig zu wissen, dass Ihre Bereitstellung aus mehreren unterschiedlichen Namespaces für die interne und externe Verwendung bestehen kann. Ihr SIP-Domänenname kann sich vom internen Bereitstellungs Domänennamen unterscheiden. Beispielsweise kann Ihre SIP-Domäne <STRONG>contoso.com</STRONG>sein, während ihre interne Bereitstellung möglicherweise <STRONG>contoso.net</STRONG>ist. Für Benutzer, die sich bei lync Server anmelden, wird der SIP-Domänenname verwendet, beispielsweise <STRONG>John@contoso.com</STRONG>. Bei der Adressierung der externen Webdienste (definiert im Topologie-Generator als <STRONG>externe Webdienste</STRONG>) sind der Domänenname und der SIP-Domänenname konsistent, wie in DNS definiert. Beim Adressieren der internen Webdienste (definiert im Topologie-Generator als <STRONG>interne Webdienste</STRONG>) ist der Standardname der internen Webdienste der FQDN des Front-End-Servers, des Front-End-Pools, des Directors oder des Director-Pools. Sie haben die Möglichkeit, den internen Webdienste-Namen zu überschreiben. Sie sollten den internen Domänennamen (und nicht den SIP-Domänennamen) für interne Webdienste verwenden und den DNS-Host a (oder, für IPv6, AAAA)-Eintrag definieren, um den überschriebenen Namen wiederzugeben. So kann beispielsweise der standardmäßige interne Webdienste-FQDN <STRONG>pool01.contoso.net</STRONG>sein. Ein überschriebner Interner FQDN für Webdienste kann <STRONG>webpool.contoso.net</STRONG>sein. Wenn Sie die Webdienste auf diese Weise definieren, wird sichergestellt, dass die interne und externe Lokalität der Dienste – und nicht die Lokalität des Benutzers, der Sie verwendet – beobachtet wird.<BR>Da die Webdienste jedoch im Topologie-Generator definiert sind und der interne Webdienste-Name überschrieben werden kann, solange der resultierende Webdienste-Name, das Zertifikat, das ihn überprüft, und die DNS-Einträge, die ihn definieren, konsistent sind, können Sie die interne Webdienste mit einem beliebigen Domänennamen, einschließlich des SIP-Domänennamens, den Sie wünschen. Letztendlich wird die Auflösung für den Namen der IP-Adresse von DNS-Hosteinträgen und einem konsistenten Namespace bestimmt.<BR>Für die Zwecke dieses Themas und der Beispiele wird der interne Domänenname verwendet, um die Topologie und die DNS-Definitionen zu veranschaulichen.



</div>

Das folgende Diagramm veranschaulicht den Fluss von Webanforderungen für mobile Webanwendungen für den Mobilitätsdienst und für den AutoErmittlungsdienst, wenn eine interne und externe DNS-Konfiguration verwendet wird.

**Mobilitätsdienst Fluss mithilfe der AutoErmittlung**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> Das Diagramm veranschaulicht generische Webdienste. Ein virtuelles Verzeichnis mit dem Namen Mobility zeigt die Mobilitätsdienste MCX und/oder UCWA. Wenn Sie die kumulierten Updates für lync Server 2013: Februar 2013 nicht angewendet haben, ist es möglich, dass Sie das virtuelle Verzeichnis Ucwa in ihren internen und externen Webdiensten definiert haben. Sie verfügen über ein virtuelles Verzeichnis AutoErmittlung, und Sie haben möglicherweise ein virtuelles Verzeichnis MCX.<BR>AutoErmittlung und die Ermittlung von Diensten funktionieren auf die gleiche Weise, unabhängig von der von Ihnen bereitgestellten Mobilitätsdienst Technologie.



</div>

Um mobile Benutzer sowohl innerhalb als auch außerhalb des Unternehmensnetzwerks zu unterstützen, müssen Ihre internen und externen Web-FQDNs einige Voraussetzungen erfüllen. Darüber hinaus müssen Sie möglicherweise andere Anforderungen erfüllen, abhängig von den Features, die Sie implementieren möchten:

  - Neue DNS-, CNAME-oder a (Host-, wenn IPv6-, AAAA-) Einträge für die automatische Erkennung.

  - Neue Firewallregel, wenn Pushbenachrichtigungen über das WLAN-Netzwerk unterstützt werden sollen

  - Sie können alternative Namen für interne Serverzertifikate und Reverse-Proxy Zertifikate für die automatische Ermittlung untersuchen.

  - Die Konfiguration des Front-End-Server-Hardwarelastenausgleichs ändert die Quell Affinität.

Ihre Topologie muss die folgenden Voraussetzungen erfüllen, um den Mobilitätsdienst und den AutoErmittlungsdienst zu unterstützen:

  - Der interne Web-FQDN des Front-End-Pools muss sich vom externen Web-FQDN des Front-End-Pools unterscheiden.

  - Der interne Web-FQDN muss nur im Unternehmensnetzwerk aufgelöst werden und darauf zugreifen können.

  - Der FQDN des externen Webdiensts muss nur im Internet aufgelöst werden und darauf zugreifen können.

  - Für einen Benutzer, der sich im Unternehmensnetzwerk befindet, muss die URL des mobilitätsdiensts an den FQDN des externen Webdiensts adressiert sein. Diese Anforderung gilt für den Mobilitätsdienst und gilt nur für diese URL.

  - Für einen Benutzer, der sich außerhalb des Unternehmensnetzwerks befindet, muss die Anforderung zum externen Web-FQDN des Front-End-Pools oder Directors wechseln.

Wenn Sie die automatische Ermittlung unterstützen, müssen Sie die folgenden DNS-Einträge für jede SIP-Domäne erstellen:

  - Ein interner DNS-Eintrag zur Unterstützung von mobilen Benutzern, die im Netzwerk Ihrer Organisation eine Verbindung herstellen.

  - Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung von mobilen Benutzern, die eine Verbindung mit dem Internet herstellen.

Die interne automatische Erkennungs-URL sollte nicht von außerhalb Ihres Netzwerks adressierbar sein. Die URL für die externe automatische Suche sollte in Ihrem Netzwerk nicht adressierbar sein. Wenn Sie diese Anforderung für die externe URL jedoch nicht erfüllen können, ist der Mobile Client wahrscheinlich nicht betroffen, da die interne URL immer zuerst ausprobiert wird.

Bei den DNS-Einträgen kann es sich entweder um CNAME-Einträge oder um einen (Host-, wenn IPv6-, AAAA)-Eintrag handeln.

<div>


> [!NOTE]  
> Clients für mobile Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) aus verschiedenen Domänen. Daher wird die CNAME-Umleitung zu verschiedenen Domänen nicht über HTTPS unterstützt. Ein DNS-CNAME-Eintrag für lyncdiscover.contoso.com, der an eine Adresse von Director.contoso.net umgeleitet wird, wird beispielsweise nicht über HTTPS unterstützt. In einer solchen Topologie muss ein Client für mobile Geräte http für die erste Anforderung verwenden, damit die CNAME-Umleitung über HTTP aufgelöst wird. Nachfolgende Anforderungen verwenden dann HTTPS. Zur Unterstützung dieses Szenarios müssen Sie den Reverse-Proxy mit einer Webveröffentlichungsregel für Port 80 (http) konfigurieren. Ausführliche Informationen finden Sie unter "So erstellen Sie eine Webveröffentlichungsregel für Port 80" unter <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</A>.<BR>Die CNAME-Umleitung zur gleichen Domäne wird über HTTPS unterstützt. In diesem Fall umfasst das Zertifikat der Zieldomäne die ursprüngliche Domäne.



</div>

Details zu den für Ihr Szenario erforderlichen DNS-Einträgen finden Sie unter [DNS-Zusammenfassung – AutoErmittlung in lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Port-und Firewall-Anforderungen

Wenn Sie Push-Benachrichtigungen unterstützen und möchten, dass Apple Mobile-Geräte Push-Benachrichtigungen über Ihr WLAN-Netzwerk empfangen, müssen Sie auch Port 5223 in Ihrem WLAN-Netzwerk für Unternehmen öffnen. Port 5223 ist ein ausgehender TCP-Port, der vom Apple Push Notification Service (APNS) verwendet wird. Das Mobile Gerät initiiert die Verbindung. Ausführliche Informationen finden Sie [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) unter.

<div>


> [!WARNING]  
> Ein Apple-Gerät, das den lync 2013-Mobilclient verwendet, erfordert keine Push-Benachrichtigungen.



</div>

Beachten Sie, dass die folgenden Ports erforderlich sind, wenn ein Benutzer in einer Survivable Branch Appliance (SBA) beheimatet ist:

  - UcwaSipExternalListeningPort erfordert Port 5088

  - UcwaSipPrimaryListeningPort erfordert Port 5089

Weitere Informationen und Anleitungen zu Port-und Protokollanforderungen für die AutoErmittlung finden Sie unter [Port Zusammenfassung – AutoErmittlung in lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Zertifikatanforderungen

Wenn Sie die automatische Ermittlung für lync Mobile-Clients unterstützen, müssen Sie die Listen Betreff alternativer Name auf Zertifikaten ändern, um sichere Verbindungen von den mobilen Clients zu unterstützen. Sie müssen für jeden Front-End-Server und Director, der den AutoErmittlungsdienst ausführt, neue Zertifikate anfordern und zuweisen, indem Sie die in diesem Abschnitt beschriebenen Alternativen für den Antragstellernamen hinzufügen. Die empfohlene Vorgehensweise besteht darin, auch die Listen Betreff Alternative Namen auf Zertifikaten für Ihre umgekehrten Proxys zu ändern. Sie müssen für jede SIP-Domäne in Ihrer Organisation Alternative Namen Einträge für Subjekte hinzufügen.

Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Vorgang, aber das Hinzufügen von mehreren alternativen Subjektnamen Einträgen zu öffentlichen Zertifikaten, die vom Reverse-Proxy verwendet werden, kann kostspielig sein. Wenn Sie über zahlreiche SIP-Domänen verfügen, die das Hinzufügen von alternativen Subjektnamen sehr teuer machen, können Sie den Reverse-Proxy so konfigurieren, dass die ursprüngliche AutoErmittlungsdienst Anforderung über Port 80 mithilfe von http statt Port 443 mithilfe von HTTPS (der Standardkonfiguration) vorgenommen wird. Die Anforderung wird dann auf Port 8080 im Director-oder Front-End-Pool umgeleitet. Wenn Sie die ursprüngliche AutoErmittlungsdienst Anforderung auf Port 80 veröffentlichen, müssen Sie keine Zertifikate für den Reverseproxy ändern, da die Anforderung http anstatt HTTPS verwendet. Dieser Ansatz wird unterstützt, aber wir empfehlen ihn nicht.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Anforderungen für Internet Informationsdienste (IIS)

Es wird empfohlen, IIS 7,5, IIS 8,0 oder IIS 8,5 für Mobilität zu verwenden. Das Mobilitätsdienst-Installationsprogramm legt Flags in ASP.net fest, um die Leistung zu verbessern. IIS 7,5 wird standardmäßig unter Windows Server 2008 R2 installiert, IIS 8,0 wird unter Windows Server 2012 installiert, und IIS 8,5 wird unter Windows Server 2012 R2 installiert. Das Mobilitätsdienst-Installationsprogramm ändert automatisch die ASP.NET-Einstellungen.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Anforderungen an das Hardwaregerät zum Lastenausgleich

Auf dem Hardware-Lastenausgleichsmodul, das den Front-End-Pool unterstützt, müssen die externen Webdienste (Virtual IPS) für Webdienste-Datenverkehr für die Quelle konfiguriert sein. Mit der Quell Affinität können Sie sicherstellen, dass mehrere Verbindungen von einem einzelnen Client an einen Server gesendet werden, um den Sitzungszustand beizubehalten. Details zu den Affinitäts Anforderungen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Wenn Sie beabsichtigen, lync Mobile-Clients nur über Ihr internes WLAN-Netzwerk zu unterstützen, sollten Sie die internen Webdienste-VIPs für Source so konfigurieren, wie dies für externe Webdienste-VIPs beschrieben ist. In diesem Fall sollten Sie für die internen\_Webdienste-VIPs auf dem Hardware-Lastenausgleichsmodul die Quell-addr-(oder TCP-) Affinität verwenden. Ausführliche Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Reverse Proxy-Anforderungen

Wenn Sie die automatische Ermittlung für lync Mobile-Clients unterstützen, müssen Sie die aktuelle Veröffentlichungsregel wie folgt aktualisieren:

  - Wenn Sie sich entschließen, die Listen Betreff Alternative Namen auf den Reverse-Proxy Zertifikaten zu aktualisieren und HTTPS für die ursprüngliche AutoErmittlungsdienst Anforderung zu verwenden, müssen Sie die Webveröffentlichungsregel für lyncdiscover aktualisieren. \<sipdomain\>. In der Regel wird dies mit der Veröffentlichungsregel für die externe Webdienste-URL im Front-End-Pool kombiniert.

  - Wenn Sie sich entschließen, http für die anfängliche AutoErmittlungsdienst Anforderung zu verwenden, damit Sie die Liste der alternativen Betreff-Namen nicht auf den Reverse-Proxy Zertifikaten aktualisieren müssen, müssen Sie eine neue Webveröffentlichungsregel für Port http/TCP 80 erstellen, wenn Sie noch nicht vorhanden ist. Wenn eine Regel für http/TCP 80 bereits vorhanden ist, können Sie diese Regel aktualisieren, um die lyncdiscover einzubeziehen. \<sipdomain\> -Eintrag.

</div>

</div>

<span> </span>

</div>

</div>

</div>

