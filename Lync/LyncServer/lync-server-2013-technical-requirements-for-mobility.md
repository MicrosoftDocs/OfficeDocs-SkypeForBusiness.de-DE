---
title: 'Lync Server 2013: technische Anforderungen für die Mobilität'
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
ms.openlocfilehash: fb4c1eacf48940822ddb26ac41f238ccdb4452dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Technische Anforderungen für die Mobilität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Mobile Benutzer stoßen auf verschiedene Szenarien für mobile Anwendungen, die eine spezielle Planung erfordern. Beispielsweise kann jemand eine mobile Anwendung während der Arbeit durch eine Verbindung über das 3G-Netzwerk verwenden, dann beim Verlassen des Gebäudes zum WLAN-Netzwerk des Unternehmens wechseln und dann wieder zu 3G wechseln. Sie müssen Ihre Umgebung so planen, dass solche Netzwerk Übergänge unterstützt werden, und Sie können eine konsistente Benutzeroberfläche gewährleisten. In diesem Abschnitt werden die Infrastrukturanforderungen beschrieben, die Sie für die Unterstützung mobiler Anwendungen und die automatische Ermittlung von mobilitätsressourcen haben müssen.

<div>


> [!NOTE]  
> Obwohl mobile Anwendungen auch eine Verbindung mit anderen lync Server 2013 Diensten herstellen können, gilt die Anforderung zum Senden aller Webanforderungen für mobile Anwendungen an denselben externen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) nur für den lync Server 2013-Mobilitätsdienst. Für andere Mobilitätsdienste ist diese Konfiguration nicht erforderlich.



</div>

Die Anforderung an die Affinität von Cookies in Hardwarelastenausgleichs wird drastisch reduziert, und Sie ersetzen die TCP-Affinität (Transmission Control Protocol), wenn Sie das mit lync Server 2013 bereitgestellte lync Mobile verwenden. Die Cookie-Affinität kann weiterhin verwendet werden, die Webdienste benötigen Sie jedoch nicht mehr.

<div>


> [!IMPORTANT]  
> Der gesamte Datenverkehr für Mobilitätsdienste geht über den Reverseproxy, unabhängig davon, wo sich der Ursprungspunkt befindet – intern oder extern. Im Fall eines einzelnen Reverseproxys oder einer Farm von Reverse-Proxies oder eines Geräts, das die Reverse-Proxyfunktion bereitstellt, kann ein Problem auftreten, wenn der interne Datenverkehr über eine Schnittstelle egressing und sofort auf dieselbe Schnittstelle eindringt. Dies führt häufig zu einer Sicherheitsregel Verletzung, die als TCP-Paket Spoofing oder nur Spoofing bezeichnet wird. Das <EM>Anheften von Haaren</EM> (der Austritt und das sofortige Eindringen eines Pakets oder einer Reihe von Paketen) muss zulässig sein, damit die Mobilität funktionieren kann. Eine Möglichkeit zum Beheben dieses Problems besteht in der Verwendung eines Reverseproxys, der von der Firewall getrennt ist (die Spoofing-Präventions Regel sollte aus Sicherheitsgründen immer an der Firewall erzwungen werden). Die Haarnadel kann an der externen Schnittstelle des Reverse-Proxys statt der externen Firewall-Schnittstelle auftreten. Sie erkennen die Spoofing-Vorgänge in der Firewall und entspannen die Regel auf dem Reverseproxy, wodurch die Haarnadel, die Mobilität erfordert.<BR>Verwenden Sie die Domain Name System (DNS) Host-oder CNAME-Einträge, um den Reverseproxy für das Haarnadel Verhalten (nicht für die Firewall) zu definieren, wenn dies möglich ist.



</div>

Lync Server 2013 unterstützt Mobilitätsdienste für lync 2010 Mobile und lync 2013 Mobile Clients. Beide Clients verwenden den lync Server 2013 AutoErmittlungsdienst, um seinen Mobilitäts Einstiegspfad zu finden, unterscheiden sich jedoch in dem von Ihnen verwendeten Mobilitätsdienst. Lync 2010 Mobile verwendet den als *MCX*bekannten Mobilitätsdienst, der mit dem kumulativen Update für lync Server 2010: November 2011 eingeführt wurde. Lync 2013 Mobile Clients verwenden die Unified Communications-WebAPI oder *UCWA*als Mobilitätsdienst Anbieter.

<div>

## <a name="internal-and-external-dns-configuration"></a>Interne und externe DNS-Konfiguration

Die Mobilitätsdienste MCX (eingeführt mit dem kumulativen Update für lync Server 2010: November 2011) und UCWA (eingeführt in den kumulativen Updates für lync Server 2013: Februar 2013) verwenden DNS auf die gleiche Weise.

Wenn Sie die automatische Ermittlung verwenden, verwenden mobile Geräte DNS zum Auffinden von Ressourcen. Während der DNS-Suche versucht eine Verbindung zuerst den FQDN, der dem internen DNS-Eintrag zugeordnet ist ("lyncdiscoverinternal".\< Interner Domänenname\>). Wenn mit dem internen DNS-Eintrag keine Verbindung hergestellt werden kann, wird versucht, eine Verbindung mit dem externen DNS-Eintrag herzustellen (\< lyncdiscover. sipdomain "\>). Ein mobiles Gerät, das sich innerhalb des Netzwerks befindet, stellt eine Verbindung mit der internen AutoErmittlungsdienst-URL her, und ein mobiles Gerät, das sich außerhalb des Netzwerks befindet, stellt eine Verbindung mit der externen AutoErmittlungsdienst-URL her. Externe Auto Ermittlungsanforderungen gehen über den Reverseproxy. Der lync Server 2013 AutoErmittlungsdienst gibt alle Webdienste-URLs für den Home-Pool des Benutzers zurück, einschließlich der Mobilitätsdienst-URLs (MCX und UCWA). Jedoch ist sowohl die interne Mobilitätsdienst-URL als auch die externe Mobilitätsdienst-URL mit dem externen Webdienste-FQDN verbunden. Unabhängig davon, ob ein mobiles Gerät intern oder extern für das Netzwerk ist, stellt das Gerät daher immer extern über den Reverseproxy eine Verbindung mit dem lync Server 2013 Mobilitätsdienst her.

<div>


> [!NOTE]  
> Es ist wichtig zu wissen, dass Ihre Bereitstellung aus mehreren unterschiedlichen Namespaces für die interne und externe Verwendung bestehen kann. Der SIP-Domänenname kann sich von dem Namen der internen Bereitstellungsdomäne unterscheiden. Beispielsweise kann Ihre SIP-Domäne <STRONG>contoso.com</STRONG>sein, während die interne Bereitstellung möglicherweise <STRONG>contoso.net</STRONG>ist. Für Benutzer, die sich bei lync Server anmelden, wird der SIP-Domänenname wie <STRONG>John@contoso.com</STRONG>verwendet. Wenn Sie die externen Webdienste (im Topologie-Generator als <STRONG>externe Webdienste</STRONG>definiert) adressieren, sind der Domänenname und der SIP-Domänenname gemäß der Definition in DNS konsistent. Bei der Adressierung der internen Webdienste (definiert im Topologie-Generator als <STRONG>interne Webdienste</STRONG>) ist der Standardname der internen Webdienste der FQDN des Front-End-Server, Front-End-Pool, Directors oder Directorpool. Sie haben die Option, den internen Webdienste-Namen außer Kraft zu setzen. Sie sollten den internen Domänennamen (und nicht den SIP-Domänennamen) für interne Webdienste verwenden und den DNS-Hosteintrag a (oder, für IPv6, AAAA) definieren, um den überschriebenen Namen widerzuspiegeln. Beispielsweise kann der interne Standard-Webdienste-FQDN <STRONG>pool01.contoso.net</STRONG>sein. Ein überschriebene FQDN für interne Webdienste kann <STRONG>webpool.contoso.net</STRONG>sein. Wenn Sie die Webdienste auf diese Weise definieren, wird sichergestellt, dass die interne und externe Lokalität der Dienste – und nicht die Lokalität des Benutzers, der Sie verwendet – eingehaltenwerden.<BR>Da die Webdienste jedoch im Topologie-Generator definiert sind und der Name der internen Webdienste überschrieben werden kann, solange der resultierende Name der Webdienste, das Zertifikat, das es überprüft, und die DNS-Einträge, die es definieren, konsistent sind, können Sie die interne Webdienste mit einem beliebigen Domänennamen, einschließlich des gewünschten SIP-Domänennamens. Letztlich wird die Auflösung für den Namen der IP-Adresse durch DNS-Hosteinträge und einen konsistenten Namespace bestimmt.<BR>Für die Zwecke dieses Themas und der Beispiele wird der Name der internen Domäne verwendet, um die Topologie und die DNS-Definitionen zu veranschaulichen.



</div>

Das folgende Diagramm veranschaulicht den Fluss von Webanforderungen für mobile Anwendungen für den Mobilitätsdienst und den AutoErmittlungsdienst bei Verwendung einer internen und externen DNS-Konfiguration.

**Mobilitätsdienst Ablauf mithilfe der AutoErmittlung**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> Das Diagramm veranschaulicht generische Webdienste. Ein virtuelles Verzeichnis mit dem Namen Mobility zeigt die Mobilitätsdienste MCX und/oder UCWA. Wenn Sie die kumulativen Updates für lync Server 2013:2013 Februar nicht angewendet haben, ist das virtuelle Verzeichnis Ucwa möglicherweise nicht für Ihre internen und externen Webdienste definiert. Sie verfügen über ein virtuelles Verzeichnis AutoErmittlung, und Sie haben möglicherweise ein virtuelles Verzeichnis MCX.<BR>Die AutoErmittlung und die Ermittlung von Diensten funktionieren auf die gleiche Weise, unabhängig von der von Ihnen bereitgestellten Mobilitätsdienste-Technologie.



</div>

Die internen und externen Web-FQDNs müssen einige Voraussetzungen erfüllen, um mobile Benutzer sowohl von innerhalb als auch außerhalb des Firmennetzwerks zu unterstützen. Zudem müssen möglicherweise andere Anforderungen erfüllt werden, je nachdem, welche Features implementiert werden sollen:

  - Neue DNS-, CNAME-oder a-Einträge (Host, if IPv6, AAAA) für die automatische Ermittlung.

  - Neue Firewallregel, wenn Sie Push-Benachrichtigungen über Ihr WLAN-Netzwerk unterstützen möchten.

  - Alternative Antragstellernamen auf internen Serverzertifikaten und Reverse-Proxy Zertifikaten für die automatische Ermittlung.

  - Front-End-Server Hardware Lastenausgleichskonfiguration die Quell Affinität ändert.

Die Topologie muss die folgenden Anforderungen erfüllen, um den Mobilitätsdienst und den AutoErmittlungsdienst zu unterstützen:

  - Der Front-End-Pool Interner FQDN des Webparts muss sich vom Front-End-Pool externen webfqdn des Webparts unterscheiden.

  - Auf den internen Web-FQDN darf nur von innerhalb des Firmennetzwerks zugegriffen werden. Zudem darf der interne Web-FQDN nur in eine Firmennetzwerkadresse aufgelöst werden.

  - Der externe Web-FQDN darf nur im Internet aufgelöst und zugänglich sein.

  - Für Benutzer, die sich innerhalb des Firmennetzwerks befinden, muss die Mobilitätsdienst-URL an den externen Web-FQDN adressiert werden. Diese Anforderung gilt für den Mobilitätsdienst und betrifft nur diese URL.

  - Für einen Benutzer, der sich außerhalb des Unternehmensnetzwerks befindet, muss die Anforderung an den externen webfqdn des Front-End-Pool oder Directors gehen.

Zur Unterstützung der AutoErmittlung müssen Sie für jede SIP-Domäne die folgenden DNS-Einträge erstellen:

  - Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die im Netzwerk Ihrer Organisation eine Verbindung herstellen.

  - Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen.

Die interne AutoErmittlung-URL sollte nicht von außerhalb des Netzwerks adressierbar sein. Die externe AutoErmittlung-URL sollte nicht von innerhalb des Netzwerks adressierbar sein. Wenn Sie diese Anforderung für die externe URL jedoch nicht erfüllen können, ist der Mobile Client möglicherweise nicht betroffen, da die interne URL stets zuerst ausprobiert wird.

Die DNS-Einträge können entweder CNAME-Einträge oder a-Einträge (Host, if IPv6, AAAA) sein.

<div>


> [!NOTE]  
> Clients mobiler Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) von verschiedenen Domänen. Daher wird die CNAME-Umleitung an verschiedene Domänen nicht über HTTPS unterstützt. Beispielsweise wird ein DNS-CNAME-Eintrag für "lyncdiscover.contoso.com", der eine Weiterleitung an eine Adresse von "director.contoso.net" vornimmt, nicht über HTTPS unterstützt. In einer solchen Topologie muss ein Client für ein mobiles Gerät HTTP für die erste Anforderung verwenden, sodass die CNAME-Umleitung über HTTP aufgelöst wird. Für die nachfolgenden Anforderungen wird dann HTTPS verwendet. Um dieses Szenario zu unterstützen, müssen Sie den Reverseproxy mit einer Webveröffentlichungsregel für Port 80 (HTTP) konfigurieren. Ausführliche Informationen finden Sie unter "So erstellen Sie eine Webveröffentlichungsregel für Port 80" unter <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in lync Server 2013</A>.<BR>Die CNAME-Umleitung an dieselbe Domäne wird über HTTPS unterstützt. In diesem Fall deckt das Zertifikat der Zieldomäne die ursprüngliche Domäne ab.



</div>

Ausführliche Informationen zu den für Ihr Szenario erforderlichen DNS-Einträgen finden Sie unter [DNS Summary-AutoErmittlung in lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Port- und Firewallanforderungen

Wenn Sie Push-Benachrichtigungen unterstützen und möchten, dass Apple Mobile Geräte Push-Benachrichtigungen über Ihr WLAN-Netzwerk erhalten, müssen Sie auch Port 5223 in Ihrem WLAN-Netzwerk in Ihrem Unternehmen öffnen. Bei Port 5223 handelt es sich um einen ausgehenden TCP-Port, der vom Apple Push Notification Service (APNS) verwendet wird. Das Mobile Gerät initiiert die Verbindung. Ausführliche Informationen finden Sie [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) unter.

<div>


> [!WARNING]  
> Ein Apple-Gerät, das den lync 2013 mobilen Client verwendet, erfordert keine Push-Benachrichtigungen.



</div>

Beachten Sie, dass die folgenden Ports erforderlich sind, wenn ein Benutzer in einem Survivable Branch Appliance (SBA) verwaltet wird:

  - UcwaSipExternalListeningPort erfordert Port 5088

  - UcwaSipPrimaryListeningPort erfordert Port 5089

Weitere Informationen und Anleitungen zu Port-und Protokollanforderungen für die AutoErmittlung finden Sie unter [Port Summary-AutoErmittlung in lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Zertifikatanforderungen

Wenn Sie die automatische Ermittlung für mobile Lync-Clients unterstützen, müssen Sie die Listen der alternativen Antragstellernamen für Zertifikate ändern, um sichere Verbindungen von mobilen Clients zu unterstützen. Sie müssen für jeden Front-End-Server und Director, der den AutoErmittlungsdienst ausführt, neue Zertifikate anfordern und zuweisen, indem Sie die in diesem Abschnitt beschriebenen alternativen Antragstellernamen hinzufügen. Es wird empfohlen, auch die Listen der alternativen Antragstellernamen für die Zertifikate der Reverseproxys zu ändern. Sie müssen die Einträge für den alternativen Antragstellernamen für jede SIP-Domäne in der Organisation hinzufügen.

Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist normalerweise ein einfacher Vorgang, aber das Hinzufügen von Einträgen für mehrere alternative Antragstellernamen zu öffentlichen Zertifikaten, die vom Reverseproxy verwendet werden, kann kostspielig sein. Wenn Sie über zahlreiche SIP-Domänen verfügen und das Hinzufügen von alternativen Antragstellernamen sehr kostspielig ist, können Sie den Reverseproxy so konfigurieren, dass er die anfängliche AutoErmittlungsdienst Anforderung über Port 80 mithilfe von http anstelle von Port 443 über HTTPS (Standardkonfiguration) abgibt. Die Anforderung wird dann auf dem Director oder Front-End-Pool an Port 8080 umgeleitet. Wenn Sie die anfängliche AutoErmittlungsdienst-Anforderung auf Port 80 veröffentlichen, müssen Sie keine Zertifikate für den Reverseproxy ändern, da die Anforderung http anstelle von HTTPS verwendet. Dieser Ansatz wird unterstützt, wird jedoch nicht empfohlen.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>IIS-Anforderungen (Internetinformationsdienste)

Es wird empfohlen, IIS 7,5, IIS 8,0 oder IIS 8,5 für Mobilität zu verwenden. Der Mobility Service Installer legt Flags in ASP.net fest, um die Leistung zu verbessern. IIS 7,5 wird standardmäßig auf Windows Server 2008 R2 installiert, IIS 8,0 ist auf Windows Server 2012 installiert, und IIS 8,5 wird auf Windows Server 2012 R2 installiert. Der Mobilitätsdienst-Installer ändert automatisch die ASP.NET-Einstellungen.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Anforderungen an das Hardwaregerät zum Lastenausgleich

Auf dem Hardwaregerät zum Lastenausgleich, das die Front-End-Pool unterstützt, muss der externe Webdienste virtuelle IPS (VIPs) für Webdienste-Datenverkehr für die Quelle konfiguriert werden. Die Quell Affinität hilft sicherzustellen, dass mehrere Verbindungen von einem einzelnen Client an einen Server gesendet werden, um den Sitzungsstatus beizubehalten. Ausführliche Informationen zu Affinitäts Anforderungen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Wenn Sie lync Mobile-Clients nur über das interne WLAN-Netzwerk unterstützen möchten, sollten Sie die internen Webdienste VIPs für die Quelle wie für externe Webdienste VIPs beschrieben konfigurieren. In diesem Fall sollten Sie die Quell\_-addr-(oder TCP-) Affinität für die interne Webdienste VIPs auf dem Hardwaregerät zum Lastenausgleich verwenden. Ausführliche Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Reverseproxyanforderungen

Wenn Sie die automatische Ermittlung für lync Mobile-Clients unterstützen, müssen Sie die aktuelle Veröffentlichungsregel wie folgt aktualisieren:

  - Wenn Sie die Listen alternativer Antragstellernamen in den Reverse-Proxy Zertifikaten aktualisieren und HTTPS für die anfängliche AutoErmittlungsdienst Anforderung verwenden, müssen Sie die Webveröffentlichungsregel für lyncdiscover aktualisieren. \<sipdomain "\>. In der Regel wird dies mit der Veröffentlichungsregel für die externe Webdienste-URL im Front-End-Pool kombiniert.

  - Wenn Sie http für die anfängliche AutoErmittlungsdienst-Anforderung verwenden, damit Sie die Liste der alternativen Antragstellernamen nicht in den Reverseproxy-Zertifikaten aktualisieren müssen, müssen Sie eine neue Webveröffentlichungsregel für Port http/TCP 80 erstellen, falls noch keine vorhanden ist. Wenn bereits eine Regel für http/TCP 80 vorhanden ist, können Sie diese Regel so aktualisieren, dass Sie die lyncdiscover enthält. \<sipdomain "\> -Eintrag.

</div>

</div>

<span> </span>

</div>

</div>

</div>

