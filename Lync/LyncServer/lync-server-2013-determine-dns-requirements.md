---
title: 'Lync Server 2013: Bestimmen der DNS-Anforderungen'
description: 'Lync Server 2013: Bestimmen der DNS-Anforderungen.'
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
ms.openlocfilehash: 0a4bfe682314fa4f91826f4bf85f8eac36ea91d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550911"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="63f80-103">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63f80-103">Determine DNS requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63f80-104">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="63f80-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="63f80-105">Anhand des folgenden Ablaufdiagramms können Sie die DNS-Anforderungen (Domain Name System) ermitteln.</span><span class="sxs-lookup"><span data-stu-id="63f80-105">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="63f80-106">Änderungen für die kumulativen Updates für lync Server 2013: Februar 2013 werden notiert, wo Sie zutreffen.</span><span class="sxs-lookup"><span data-stu-id="63f80-106">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63f80-107">Microsoft lync Server 2013 unterstützt die Verwendung der IPv6-Adressierung.</span><span class="sxs-lookup"><span data-stu-id="63f80-107">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="63f80-108">Um IPv6-Adressen verwenden zu können, müssen Sie auch Unterstützung für IPv6-DNS bereitstellen und DNS-Host-AAAA-Einträge ("Quad-A" bezeichnet) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="63f80-108">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="63f80-109">In Bereitstellungen, in denen sowohl IPv4 als auch IPv6 verwendet werden, empfiehlt es sich, sowohl Host A-Einträge für IPv4 als auch Host-AAAA für IPv6 zu konfigurieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="63f80-109">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="63f80-110">Auch wenn Ihre Bereitstellung vollständig auf IPv6 umgestellt ist, sind IPv4-DNS-Hosteinträge möglicherweise noch erforderlich, wenn externe Benutzer weiterhin IPv4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="63f80-110">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="63f80-111">**Ablaufdiagramm zur Ermittlung der DNS-Anforderungen**</span><span class="sxs-lookup"><span data-stu-id="63f80-111">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="63f80-112">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="63f80-112">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63f80-113">Standardmäßig ist der Computername eines Computers, der nicht einer Domäne angehört, ein Hostname, kein vollqualifizierter Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="63f80-113">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="63f80-114">Der Topologie-Generator verwendet FQDNs und keine Hostnamen.</span><span class="sxs-lookup"><span data-stu-id="63f80-114">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="63f80-115">Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="63f80-115">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="63f80-116"><STRONG>Verwenden Sie nur Standardzeichen</STRONG> (also A–Z, a–z, 0–9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="63f80-116"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="63f80-117">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="63f80-117">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="63f80-118">Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63f80-118">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="63f80-119">Weitere Informationen finden Sie unter <A href="lync-server-2013-configure-dns-host-records.md">Konfigurieren von DNS-Host Einträgen für lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="63f80-119">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="63f80-120">So finden lync-Clients Dienste</span><span class="sxs-lookup"><span data-stu-id="63f80-120">How Lync Clients Locate Services</span></span>

<span data-ttu-id="63f80-121">Microsoft lync 2010, lync 2013 und lync Mobile ähneln der Art und Weise, in der der Clientdienste in lync Server 2013 findet und zugreift.</span><span class="sxs-lookup"><span data-stu-id="63f80-121">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="63f80-122">Die wichtigste Ausnahme ist die lync Windows Store-App, die einen anderen Dienststandort Prozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="63f80-122">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="63f80-123">In diesem Abschnitt werden zwei Szenarien beschrieben, wie die Clients Dienste suchen, zunächst die herkömmliche Methode, die eine Reihe von SRV-und Hosteinträgen verwendet, und zweitens nur die Datensätze des AutoErmittlungsdiensts.</span><span class="sxs-lookup"><span data-stu-id="63f80-123">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="63f80-124">Kumulierte Aktualisierungen der Desktop Clients ändern den DNS-Standort Prozess von lync Server 2010 für alle Clients, der DNS-Abfrageprozess wird fortgesetzt, bis eine erfolgreiche Abfrage zurückgegeben wird, oder die Liste der möglichen DNS-Einträge ist erschöpft, und der letzte Fehler wird an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63f80-124">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="63f80-125">Für alle Clients **mit Ausnahme** der lync Windows Store-App während der DNS-Suche werden SRV-Einträge abgefragt und in der folgenden Reihenfolge an den Client zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="63f80-125">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="63f80-126">"lyncdiscoverinternal". \<domain\>     Ein (Host)-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten</span><span class="sxs-lookup"><span data-stu-id="63f80-126">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="63f80-127">lyncdiscover. \<domain\>     Ein (Host)-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten</span><span class="sxs-lookup"><span data-stu-id="63f80-127">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="63f80-128">\_sipinternaltls. \_ TCP. \<domain\>     SRV (Service Locator)-Eintrag für interne TLS-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="63f80-128">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="63f80-129">\_sipinternal. \_ TCP. \<domain\>     SRV (Service Locator)-Eintrag für interne TCP-Verbindungen (nur ausgeführt, wenn TCP zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="63f80-129">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="63f80-130">\_SIP. \_ TLS. \<domain\>     SRV (Service Locator)-Eintrag für externe TLS-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="63f80-130">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="63f80-131">sipinternal. \<domain\>     Ein (Host-) Eintrag für den Front-End-Pool oder Director, der nur im internen Netzwerk aufgelöst werden kann</span><span class="sxs-lookup"><span data-stu-id="63f80-131">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="63f80-132">SIP. \<domain\>     Ein (Host-) Eintrag für den Front-End-Pool oder Director im internen Netzwerk oder die Zugriffs-Edgedienst, wenn der Client extern ist</span><span class="sxs-lookup"><span data-stu-id="63f80-132">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="63f80-133">sipexternal. \<domain\>     Ein (Host-) Eintrag für den Zugriffs-Edgedienst, wenn der Client extern ist</span><span class="sxs-lookup"><span data-stu-id="63f80-133">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="63f80-134">Die lync Windows Store-App ändert den Prozess vollständig, da zwei Datensätze verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="63f80-134">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="63f80-135">"lyncdiscoverinternal". \<domain\>     Ein (Host)-Eintrag für den AutoErmittlungsdienst in den internen Webdiensten</span><span class="sxs-lookup"><span data-stu-id="63f80-135">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="63f80-136">lyncdiscover. \<domain\>     Ein (Host)-Eintrag für den AutoErmittlungsdienst in den externen Webdiensten</span><span class="sxs-lookup"><span data-stu-id="63f80-136">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="63f80-137">Es gibt kein Fallback auf die anderen Datensatztypen.</span><span class="sxs-lookup"><span data-stu-id="63f80-137">There is no fallback to the other record types.</span></span>

<span data-ttu-id="63f80-138">Der Unterschied zwischen den Methoden, die für neuere Clients im Vergleich zu älteren Clients verwendet werden, besteht darin, dass der AutoErmittlungsdienst die bevorzugte Methode zum Auffinden aller Dienste wird.</span><span class="sxs-lookup"><span data-stu-id="63f80-138">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="63f80-139">Wenn eine Verbindung erfolgreich hergestellt wurde, gibt der AutoErmittlungsdienst alle Webdienste-URLs für den privaten Pool des Benutzers zurück, einschließlich des mobilitätsdiensts (bekannt als MCX durch das virtuelle Verzeichnis, das in IIS für den Dienst erstellt wurde), Microsoft lync Web App-und Webplaner-URLs.</span><span class="sxs-lookup"><span data-stu-id="63f80-139">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="63f80-140">Jedoch ist sowohl die interne als auch die externe URL des Mobilitätsdiensts dem externen Webdienste-FQDN zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="63f80-140">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="63f80-141">Daher stellt das mobile Gerät (egal, ob es sich innerhalb oder außerhalb des Netzwerks befindet) immer extern über den Reverseproxy eine Verbindung mit dem Mobilitätsdienst her.</span><span class="sxs-lookup"><span data-stu-id="63f80-141">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="63f80-142">Wenn die kumulativen Updates für lync Server 2013:2013 Februar installiert wurde, gibt der AutoErmittlungsdienst auch Verweise auf Internal/UCWA, External/UCWA und UCWA zurück.</span><span class="sxs-lookup"><span data-stu-id="63f80-142">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="63f80-143">Diese Einträge verweisen auf die Unified Communications Web API (UCWA)-Webkomponente.</span><span class="sxs-lookup"><span data-stu-id="63f80-143">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="63f80-144">Derzeit wird nur der Eintrag UCWA verwendet, und es wird ein Verweis auf eine URL für die Webkomponente bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="63f80-144">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="63f80-145">UCWA wird von lync 2013 mobilen Clients anstelle des MCX-mobilitätsdiensts verwendet, der von den lync 2010 Mobile Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="63f80-145">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63f80-146">Beim Erstellen von SRV-Einträgen ist es wichtig, sich daran zu erinnern, dass Sie auf einen DNS-Eintrag (wenn Sie IPv6-Adressierung verwenden) in derselben Domäne, in der der DNS-SRV-Eintrag erstellt wird, hinweisen müssen.</span><span class="sxs-lookup"><span data-stu-id="63f80-146">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="63f80-147">Wenn sich der SRV-Eintrag beispielsweise in contoso.com befindet, zeigt der Eintrag A und AAAA (wenn Sie IPv6-Adressierung verwenden) auf nicht in fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="63f80-147">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="63f80-148">Die Standardkonfiguration besteht darin, den gesamten mobilen Client Datenverkehr über den externen Standort zu leiten.</span><span class="sxs-lookup"><span data-stu-id="63f80-148">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="63f80-149">Sie können Einstellungen so ändern, dass nur die interne URL zurückgegeben wird, wenn dies für Ihre Anforderungen vorzuziehen ist.</span><span class="sxs-lookup"><span data-stu-id="63f80-149">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="63f80-150">Bei dieser Konfiguration können Benutzer auf ihren mobilen Geräten mobile Lync-Anwendungen nur verwenden, wenn sie sich im Firmennetzwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="63f80-150">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="63f80-151">Um diese Konfiguration zu definieren, verwenden Sie das Cmdlet " <STRONG>CsMcxConfiguration</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="63f80-151">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="63f80-152">Obwohl mobile Anwendungen auch eine Verbindung mit anderen lync Server 2013 Diensten wie dem Adressbuchdienst herstellen können, werden Webanforderungen für interne Mobile Webanwendungen nur für den Mobilitätsdienst an den externen webfqdn des Webs weitergeben.</span><span class="sxs-lookup"><span data-stu-id="63f80-152">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="63f80-153">Für andere Dienstanforderungen, beispielsweise Adressbuchanforderungen, ist diese Konfiguration nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="63f80-153">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="63f80-154">Mobile Geräte unterstützen die manuelle Ermittlung von Diensten.</span><span class="sxs-lookup"><span data-stu-id="63f80-154">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="63f80-155">In diesem Fall muss jeder Benutzer in den Einstellungen des mobilen Geräts wie folgt die vollständigen internen und externen AutoErmittlungsdienst-URIs konfigurieren, einschließlich Protokoll und Pfad:</span><span class="sxs-lookup"><span data-stu-id="63f80-155">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="63f80-156">https://- \<ExtPoolFQDN\> /autodiscover/autodiscoverservice.svc/root für externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="63f80-156">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="63f80-157">https://- \<IntPoolFQDN\> /autodiscover/autodiscover.svc/root für internen Zugriff</span><span class="sxs-lookup"><span data-stu-id="63f80-157">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="63f80-158">Es wird empfohlen, die automatische Ermittlung anstelle von manueller Ermittlung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="63f80-158">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="63f80-159">Manuelle Einstellungen können jedoch bei der Behandlung von Problemen mit der Konnektivität mobiler Geräte hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="63f80-159">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="63f80-160">Konfigurieren Split-Brain DNS mit lync Server</span><span class="sxs-lookup"><span data-stu-id="63f80-160">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="63f80-161">Split-Brain-DNS ist durch eine Reihe von Namen bekannt, beispielsweise geteilte DNS oder Split-Horizon-DNS.</span><span class="sxs-lookup"><span data-stu-id="63f80-161">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="63f80-162">Es wird lediglich eine DNS-Konfiguration beschrieben, in der zwei DNS-Zonen mit dem gleichen Namespace vorhanden sind – nur interne Anforderungen für DNS-Zonen Dienste und die anderen DNS-Zonen Dienste, die nur extern angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="63f80-162">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="63f80-163">Eine Vielzahl der DNS-SRV- und DNS-A-Einträge in der internen DNS-Konfiguration sind jedoch nicht in der externen DNS-Konfiguration enthalten und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="63f80-163">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="63f80-164">In Fällen, in denen derselbe DNS-Eintrag sowohl im internen als auch im externen DNS vorhanden ist (beispielsweise www.contoso.com), unterscheidet sich die zurückgegebene IP-Adresse je nachdem, wo (intern oder extern) die Abfrage initiiert wurde.</span><span class="sxs-lookup"><span data-stu-id="63f80-164">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63f80-165">Derzeit wird Split-Brain DNS für die Mobilität oder genauer gesagt für die LyncDiscover-und "lyncdiscoverinternal"-DNS-Einträge nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63f80-165">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="63f80-166">LyncDiscover muss auf einem externen DNS-Server definiert sein, und "lyncdiscoverinternal" muss auf einem internen DNS-Server definiert sein.</span><span class="sxs-lookup"><span data-stu-id="63f80-166">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="63f80-167">Im Rahmen dieser Themen wird der Begriff Split-Brain-DNS verwendet.</span><span class="sxs-lookup"><span data-stu-id="63f80-167">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="63f80-168">Wenn Sie Split-Brain-DNS konfigurieren, umfassen die folgenden internen und externen Zonen eine Übersicht über die Typen von DNS-Einträgen, die in jeder Zone erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="63f80-168">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="63f80-169">Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="63f80-169">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="63f80-170">**Interne DNS-Konfiguration:**</span><span class="sxs-lookup"><span data-stu-id="63f80-170">**Internal DNS:**</span></span>

  - <span data-ttu-id="63f80-171">Enthält eine DNS-Zone "contoso.com", für die die DNS-Konfiguration autoritativ ist</span><span class="sxs-lookup"><span data-stu-id="63f80-171">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="63f80-172">Die interne Zone "contoso.com" umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="63f80-172">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="63f80-173">DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) und SRV-Einträge für die interne lync Server 2013 Client-Autokonfiguration (optional)</span><span class="sxs-lookup"><span data-stu-id="63f80-173">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="63f80-174">DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Ermittlung von lync Server 2013 Webdienste (optional)</span><span class="sxs-lookup"><span data-stu-id="63f80-174">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="63f80-175">DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für Front-End-Pool Namen, den Director oder den Directorpool Namen sowie alle internen Server mit lync Server 2013 im Unternehmensnetzwerk</span><span class="sxs-lookup"><span data-stu-id="63f80-175">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="63f80-176">DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für die interne Edge-Schnittstelle jedes lync Server 2013 Edgeserver im Umkreisnetzwerk</span><span class="sxs-lookup"><span data-stu-id="63f80-176">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="63f80-177">DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für die interne Schnittstelle jedes Reverse-Proxyservers im Umkreisnetzwerk (optional für die Verwaltung des Reverseproxys)</span><span class="sxs-lookup"><span data-stu-id="63f80-177">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="63f80-178">Alle lync Server 2013 Edgeserver internen Edge-Schnittstellen im Umkreisnetzwerk verwenden die interne DNS-Zone zum Auflösen von Abfragen in contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-178">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="63f80-179">Alle Server mit lync Server 2013 und Clients, auf denen lync 2013 im Unternehmensnetzwerk läuft, weisen auf die internen DNS-Server hin, um Abfragen an contoso.com zu lösen, oder Sie können die Hosts-Datei auf jedem Edgeserver und Listen A und AAAA (wenn Sie IPv6-Adressierung verwenden) für den nächsten Hop-Server, insbesondere den Director oder Director VIP, Front-End-Pool VIP oder Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="63f80-179">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="63f80-180">**Externe DNS-Konfiguration:**</span><span class="sxs-lookup"><span data-stu-id="63f80-180">**External DNS:**</span></span>

  - <span data-ttu-id="63f80-181">Enthält eine DNS-Zone "contoso.com", für die die DNS-Konfiguration autoritativ ist</span><span class="sxs-lookup"><span data-stu-id="63f80-181">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="63f80-182">Die externe Zone "contoso.com" umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="63f80-182">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="63f80-183">DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) und SRV-Einträge für lync Server 2013 Client-Autokonfiguration (optional)</span><span class="sxs-lookup"><span data-stu-id="63f80-183">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="63f80-184">DNS A und AAAA (wenn Sie IPv6-Adressierung verwenden) oder CNAME-Einträge für die automatische Ermittlung von lync Server 2013 Webdienste für die Verwendung mit Mobility</span><span class="sxs-lookup"><span data-stu-id="63f80-184">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="63f80-185">DNS A und AAAA (wenn Sie die IPv6-Adressierung verwenden) und SRV-Einträge für die externe Edge-Schnittstelle jedes lync Server 2013, Edgeserver oder die virtuelle IP des Hardware Lastenausgleichs im Umkreisnetzwerk</span><span class="sxs-lookup"><span data-stu-id="63f80-185">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="63f80-186">DNS-A-und-AAAA-Einträge (wenn Sie IPv6-Adressierung verwenden) für die externe Schnittstelle des Reverseproxy-Servers oder VIP für einen Pool von Reverse-Proxyservern im Umkreisnetzwerk</span><span class="sxs-lookup"><span data-stu-id="63f80-186">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="63f80-187">Automatische Konfiguration ohne Split-Brain-DNS</span><span class="sxs-lookup"><span data-stu-id="63f80-187">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="63f80-188">Bei Verwendung von Split-Brain-DNS kann ein lync Server 2013 Benutzer, der sich intern anmeldet, die automatische Konfiguration nutzen, wenn die interne DNS-Zone eine \_ sipinternaltls enthält. \_ TCP-SRV-Eintrag für jede verwendete SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="63f80-188">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="63f80-189">Wenn Sie jedoch nicht Split-Brain-DNS verwenden, funktioniert die interne automatische Konfiguration von Clients, auf denen lync ausgeführt wird, nur, wenn eine der in diesem Abschnitt weiter unten beschriebenen Problemumgehungen implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="63f80-189">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="63f80-190">Dies liegt daran, dass lync Server 2013 erfordert, dass der SIP-URI des Benutzers mit der Domäne der Front-End-Pool übereinstimmt, die für die automatische Konfiguration festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="63f80-190">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="63f80-191">Dies war auch bei früheren Versionen von Communicator der Fall.</span><span class="sxs-lookup"><span data-stu-id="63f80-191">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="63f80-192">Wenn Sie z. B. zwei SIP-Domänen verwenden, sind die zwei folgenden DNS-SRV-Einträge erforderlich:</span><span class="sxs-lookup"><span data-stu-id="63f80-192">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="63f80-193">Wenn sich ein Benutzer als Bob@contoso.com anmeldet, funktioniert der folgende SRV-Eintrag für die automatische Konfiguration, da die SIP-Domäne (contoso.com) des Benutzers mit der Domäne der automatischen Konfigurations Front-End-Pool) übereinstimmt:</span><span class="sxs-lookup"><span data-stu-id="63f80-193">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="63f80-194">\_sipinternaltls. \_ TCP.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="63f80-194">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="63f80-195">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-195">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="63f80-196">Wenn sich ein Benutzer als Alice@fabrikam.com anmeldet, funktioniert der folgende DNS-SRV-Eintrag für die automatische Konfiguration der zweiten SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="63f80-196">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="63f80-197">\_sipinternaltls. \_ TCP.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="63f80-197">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="63f80-198">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="63f80-198">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="63f80-199">Wenn sich ein Benutzer als Tim@litwareinc.com anmeldet, kann der folgende DNS-SRV-Eintrag zum Vergleich nicht für die automatische Konfiguration verwendet werden, da die SIP-Domäne (litwareinc.com) des Clients nicht mit der Domäne übereinstimmt, in der sich der Pool befindet (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="63f80-199">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="63f80-200">\_sipinternaltls. \_ TCP.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="63f80-200">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="63f80-201">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="63f80-201">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="63f80-202">Wenn für Clients, die lync ausführen, die automatische Konfiguration erforderlich ist, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="63f80-202">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="63f80-203">**Gruppenrichtlinienobjekte**     Verwenden Sie Gruppenrichtlinienobjekte (Group Policy Objects, GPOs), um die richtigen Server Werte aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="63f80-203">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63f80-204">Mit dieser Option wird die automatische Konfiguration nicht aktiviert, der Prozess der manuellen Konfiguration wird jedoch automatisiert. Daher werden die SRV-Einträge für die automatische Konfiguration bei Verwendung dieses Ansatzes nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="63f80-204">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="63f80-205">**Übereinstimmende interne Zone**     Erstellen Sie eine Zone im internen DNS, die mit der externen DNS-Zone übereinstimmt (beispielsweise contoso.com), und erstellen Sie DNS a und AAAA (wenn Sie IPv6-Adressierung verwenden), die dem lync Server 2013 Pool entsprechen, der für die automatische Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="63f80-205">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="63f80-206">Wenn ein Benutzer beispielsweise in pool01.contoso.NET verwaltet wird, sich jedoch als Bob@contoso.com in lync befindet, erstellen Sie eine interne DNS-Zone namens Contoso.com, und erstellen Sie in dieser einen DNS-Eintrag a und AAAA (falls IPv6-Adressierung verwendet wird) für pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="63f80-206">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="63f80-207">**Interne Pin-Punkt Zone**     Wenn Sie eine gesamte Zone im internen DNS erstellen, ist keine Option, sondern Sie können PIN-Punkt-(dedizierte) Zonen erstellen, die den SRV-Einträgen entsprechen, die für die automatische Konfiguration erforderlich sind, und diese Zonen mit dnscmd.exe auffüllen.</span><span class="sxs-lookup"><span data-stu-id="63f80-207">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="63f80-208">Dnscmd.exe ist erforderlich, da die DNS-Benutzeroberfläche die Erstellung von PIN-Punkt-Zonen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63f80-208">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="63f80-209">Wenn die SIP-Domäne beispielsweise contoso.com ist und Sie über eine Front-End-Pool namens pool01 verfügen, die zwei Front-End-Server enthält, benötigen Sie die folgenden Pin-Punkt-Zonen und einen Eintrag in Ihrem internen DNS:</span><span class="sxs-lookup"><span data-stu-id="63f80-209">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="63f80-210">Wenn Ihre Umgebung eine zweite SIP-Domäne (z. B. "fabrikam.com") umfasst, benötigen Sie die folgenden dedizierten Zonen und DNS-A-Einträge in Ihrem internen DNS:</span><span class="sxs-lookup"><span data-stu-id="63f80-210">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="63f80-p121">Der FQDN des Front-End-Pools wird zweimal aufgeführt, jedoch mit unterschiedlichen IP-Adressen. Der Grund dafür ist, dass ein DNS-Lastenausgleich verwendet wird. Bei Verwendung von Hardwarelastenausgleich wäre nur ein einzelner Front-End-Pool-Eintrag vorhanden. Zudem weisen die Beispiele "contoso.com" und "fabrikam.com" unterschiedliche FQDN-Werte des Front-End-Pools auf, die IP-Adressen sind jedoch gleich. Der Grund dafür ist, dass Benutzer, die sich über eine der SIP-Domänen anmelden, denselben Front-End-Pool für die automatische Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="63f80-p121">The Front End pool FQDN appears twice, but with two different IP addresses. This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry. Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same. This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="63f80-215">Ausführliche Informationen finden Sie im DMTF-Blog Artikel "Communicator Automatic Configuration and Split-Brain DNS" unter [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) .</span><span class="sxs-lookup"><span data-stu-id="63f80-215">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63f80-216">Der Inhalt jedes Blogs und die dazugehörige URL kann ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="63f80-216">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="63f80-217">Konfigurieren des DNS (Domain Name System) für die Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="63f80-217">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="63f80-218">Sie müssen einen DNS-Anbieter verwenden, der GeoDNS unterstützt, um DNS so zu konfigurieren, dass lync Server 2013 Webdatenverkehr auf Ihre Notfallwiederherstellung und Failover-Websites umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="63f80-218">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="63f80-219">Sie können Ihre DNS-Einträge für das Internet so einrichten, dass die Notfallwiederherstellung unterstützt wird, sodass Features, die Webdienste verwenden, auch dann fortgesetzt werden, wenn ein ganzer Front-End-Pool ausfällt.</span><span class="sxs-lookup"><span data-stu-id="63f80-219">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="63f80-220">Diese Notfallwiederherstellungsfunktion unterstützt die AutoErmittlung (Lyncdiscover-URL), Meet and Dial-in Simple URLs.</span><span class="sxs-lookup"><span data-stu-id="63f80-220">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="63f80-221">Sie definieren und konfigurieren zusätzliche DNS-Hosteinträge (A und AAAA bei Verwendung von IPv6) für die interne und externe Auflösung von Webdiensten bei Ihrem GeoDNS-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="63f80-221">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="63f80-222">Die folgenden Details setzen voraus, dass gekoppelte Pools, geografisch verteilte und GeoDNS, die von Ihrem Anbieter entweder mit Round-Robin-DNS unterstützt oder für die Verwendung von pool1 als Primary konfiguriert sind, und führen ein Failover auf Pool2 im Falle eines Kommunikations Verlusts oder eines Hardwarefehlers durch.</span><span class="sxs-lookup"><span data-stu-id="63f80-222">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63f80-223">GeoDNS-Eintrag (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="63f80-223">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="63f80-224">Pool Einträge (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="63f80-224">Pool records (example)</span></span></th>
<th><span data-ttu-id="63f80-225">CNAME-Einträge (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="63f80-225">CNAME records (example)</span></span></th>
<th><span data-ttu-id="63f80-226">DNS-Einstellungen (Wählen Sie eine Option aus)</span><span class="sxs-lookup"><span data-stu-id="63f80-226">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63f80-227">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-227">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-228">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-228">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-229">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-229">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-230">Meet.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-230">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-231">Meet.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-231">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-232">Roundrobin zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="63f80-232">Round Robin between pools</span></span></p>
<p><span data-ttu-id="63f80-233">Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</span><span class="sxs-lookup"><span data-stu-id="63f80-233">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f80-234">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-234">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-235">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-235">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-236">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-236">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-237">Meet.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-237">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-238">Meet.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-238">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-239">Roundrobin zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="63f80-239">Round Robin between pools</span></span></p>
<p><span data-ttu-id="63f80-240">Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</span><span class="sxs-lookup"><span data-stu-id="63f80-240">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f80-241">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-241">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-242">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-242">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-243">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-243">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-244">Dialin.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-244">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-245">Dialin.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-245">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-246">Roundrobin zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="63f80-246">Round Robin between pools</span></span></p>
<p><span data-ttu-id="63f80-247">Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</span><span class="sxs-lookup"><span data-stu-id="63f80-247">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f80-248">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-248">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-249">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-249">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-250">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-250">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-251">Dialin.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-251">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-252">Dialin.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-252">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-253">Roundrobin zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="63f80-253">Round Robin between pools</span></span></p>
<p><span data-ttu-id="63f80-254">Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</span><span class="sxs-lookup"><span data-stu-id="63f80-254">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f80-255">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-255">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-256">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-256">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-257">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-257">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-258">Lyncdiscoverinternal.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-258">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-259">Lyncdiscoverinternal.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-259">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-260">Roundrobin zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="63f80-260">Round Robin between pools</span></span></p>
<p><span data-ttu-id="63f80-261">Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</span><span class="sxs-lookup"><span data-stu-id="63f80-261">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f80-262">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-262">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-263">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-263">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-264">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-264">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-265">Lyncdiscover.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-265">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-266">Lyncdiscover.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-266">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-267">Roundrobin zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="63f80-267">Round Robin between pools</span></span></p>
<p><span data-ttu-id="63f80-268">Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</span><span class="sxs-lookup"><span data-stu-id="63f80-268">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f80-269">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-269">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-270">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-270">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-271">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-271">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-272">Scheduler.contoso.com-Alias für Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-272">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-273">Scheduler.contoso.com-Alias für Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-273">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-274">Roundrobin zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="63f80-274">Round Robin between pools</span></span></p>
<p><span data-ttu-id="63f80-275">Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</span><span class="sxs-lookup"><span data-stu-id="63f80-275">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f80-276">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-276">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-277">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-277">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-278">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-278">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-279">Scheduler.contoso.com-Alias für Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-279">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="63f80-280">Scheduler.contoso.com-Alias für Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="63f80-280">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="63f80-281">Roundrobin zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="63f80-281">Round Robin between pools</span></span></p>
<p><span data-ttu-id="63f80-282">Primäre verwenden, bei Ausfall eine Verbindung mit Sekundär herstellen</span><span class="sxs-lookup"><span data-stu-id="63f80-282">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="63f80-283">DNS-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="63f80-283">DNS Load Balancing</span></span>

<span data-ttu-id="63f80-284">Der DNS-Lastenausgleich wird in der Regel auf Anwendungsebene implementiert.</span><span class="sxs-lookup"><span data-stu-id="63f80-284">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="63f80-285">Die Anwendung (beispielsweise ein Client, der lync ausführt) versucht, eine Verbindung mit einem Server in einem Pool herzustellen, indem eine Verbindung mit einer der IP-Adressen hergestellt wird, die von der DNS-Adresse "a" und "AAAA (falls IPv6-Adressierung verwendet)" für den vollqualifizierten Domänennamen (FQDN) des Pools zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="63f80-285">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="63f80-286">Wenn z. B. drei Front-End-Server im Pool "pool01.contoso.com" vorhanden sind, werden folgende Schritte ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="63f80-286">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="63f80-287">Clients, auf denen lync Query DNS für pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="63f80-287">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="63f80-288">Die Abfrage gibt drei IP-Adressen zurück und speichert diese wie folgt (nicht notwendigerweise in dieser Reihenfolge) zwischen:</span><span class="sxs-lookup"><span data-stu-id="63f80-288">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="63f80-289">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="63f80-289">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="63f80-290">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="63f80-290">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="63f80-291">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="63f80-291">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="63f80-292">Der Client versucht, eine TCP-Verbindung (Transmission Control Protocol) mit einer der IP-Adressen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="63f80-292">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="63f80-293">Ist dies nicht möglich, versucht der Client, eine Verbindung mit der nächsten IP-Adresse im Zwischenspeicher herzustellen.</span><span class="sxs-lookup"><span data-stu-id="63f80-293">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="63f80-294">Wenn die TCP-Verbindung erfolgreich ist, verhandelt der Client TLS, um eine Verbindung mit der primären Registrierungsstelle in pool01.contoso.com herzustellen.</span><span class="sxs-lookup"><span data-stu-id="63f80-294">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="63f80-295">Wenn der Client alle zwischengespeicherten Einträge ohne erfolgreiche Verbindung versucht, wird der Benutzer benachrichtigt, dass derzeit keine Server mit lync Server 2013 zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="63f80-295">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63f80-296">DNS-basierter Lastenausgleich unterscheidet sich von DNS-Round Robin (DNS-Ressourceneintrag), der in der Regel auf Lastenausgleich verweist, indem DNS eine andere Reihenfolge von IP-Adressen bereitstellt, die den Servern in einem Pool entsprechen.</span><span class="sxs-lookup"><span data-stu-id="63f80-296">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="63f80-297">Normalerweise aktiviert DNS-RR nur die Lastenverteilung, aktiviert jedoch kein Failover.</span><span class="sxs-lookup"><span data-stu-id="63f80-297">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="63f80-298">Wenn beispielsweise die Verbindung mit der einzigen IP-Adresse, die von der DNS-A-und der AAAA-Abfrage (wenn Sie IPv6-Adressierung verwenden) zurückgegeben wird, schlägt die Verbindung fehl.</span><span class="sxs-lookup"><span data-stu-id="63f80-298">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="63f80-299">Daher ist DNS Round Robin selbst weniger zuverlässig als DNS-basierter Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="63f80-299">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="63f80-300">Sie können DNS-Roundrobin in Verbindung mit dem DNS-Lastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="63f80-300">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="63f80-301">DNS-Lastenausgleich wird für folgende Szenarien eingesetzt:</span><span class="sxs-lookup"><span data-stu-id="63f80-301">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="63f80-302">Lastenausgleich zwischen Server-zu-Server-SIP-Servern und Edgeserver</span><span class="sxs-lookup"><span data-stu-id="63f80-302">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="63f80-303">Lastenausgleich für Anwendungen der Unified Communications-Anwendungsdienste, z. B. automatische Konferenzzentrale, Reaktionsgruppen und die Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="63f80-303">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="63f80-304">Verhindern neuer Verbindungen mit Anwendungen der Unified Communications-Anwendungsdienste (auch als "Serverausgleich" bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="63f80-304">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="63f80-305">Lastenausgleich für den gesamten Datenverkehr zwischen Clients und Edgeservern</span><span class="sxs-lookup"><span data-stu-id="63f80-305">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="63f80-306">DNS-Lastenausgleich kann für folgende Szenarien nicht eingesetzt werden:</span><span class="sxs-lookup"><span data-stu-id="63f80-306">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="63f80-307">Client-zu-Server-Webdatenverkehr für Director-oder Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="63f80-307">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="63f80-308">DNS-Lastenausgleich und Datenverkehr im Partnerverbund:</span><span class="sxs-lookup"><span data-stu-id="63f80-308">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="63f80-309">Wenn mehrere DNS-Einträge von einer DNS-SRV-Abfrage zurückgegeben werden, wählt der Zugriffs-Edgedienst immer den DNS-SRV-Eintrag mit der niedrigsten numerischen Priorität und der höchsten numerischen Gewichtung aus.</span><span class="sxs-lookup"><span data-stu-id="63f80-309">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="63f80-310">Das Internet Engineering Task Force-Dokument "ein DNS-Ressourceneintrag für die Angabe des Speicherorts von Diensten (DNS-SRV)" <http://www.ietf.org/rfc/rfc2782.txt> gibt an, dass wenn mehrere DNS-SRV-Einträge definiert sind, Priorität zuerst verwendet wird, dann die Gewichtung.</span><span class="sxs-lookup"><span data-stu-id="63f80-310">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="63f80-311">Beispielsweise hat DNS-SRV-Eintrag a eine Gewichtung von 20 und eine Priorität von 40 und DNS-SRV-Eintrag B eine Gewichtung von 10 und eine Priorität von 50.</span><span class="sxs-lookup"><span data-stu-id="63f80-311">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="63f80-312">DNS-SRV-Eintrag A mit Priorität 40 wird ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="63f80-312">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="63f80-313">Die folgenden Regeln gelten für die Auswahl des DNS-SRV-Eintrags:</span><span class="sxs-lookup"><span data-stu-id="63f80-313">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="63f80-314">Priorität wird als erstes betrachtet.</span><span class="sxs-lookup"><span data-stu-id="63f80-314">Priority is considered first.</span></span> <span data-ttu-id="63f80-315">Ein Client muss versuchen, den vom DNS-SRV-Eintrag definierten Ziel Host mit der niedrigsten nummerierten Priorität zu kontaktieren, die er erreichen kann.</span><span class="sxs-lookup"><span data-stu-id="63f80-315">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="63f80-316">Ziele mit derselben Priorität sollten in einer durch das gewichtungsfeld definierten Reihenfolge ausprobiert werden.</span><span class="sxs-lookup"><span data-stu-id="63f80-316">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="63f80-317">Das Feld Gewichtung gibt eine relative Gewichtung für Einträge mit derselben Priorität an.</span><span class="sxs-lookup"><span data-stu-id="63f80-317">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="63f80-318">Größere Gewichtungen sollten eine proportional höhere Wahrscheinlichkeit für die Auswahl erhalten.</span><span class="sxs-lookup"><span data-stu-id="63f80-318">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="63f80-319">DNS-Administratoren sollten die Gewichtung 0 verwenden, wenn keine Serverauswahl erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="63f80-319">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="63f80-320">Bei vorhanden sein von Datensätzen, die die Gewichtung größer als 0 enthalten, sollten Datensätze mit einer Gewichtung von 0 eine sehr geringe Chance haben, ausgewählt zu werden.</span><span class="sxs-lookup"><span data-stu-id="63f80-320">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="63f80-321">Wenn mehrere DNS-SRV-Einträge mit gleicher Priorität und Gewichtung zurückgegeben werden, wählt der Zugriffs-Edgedienst den SRV-Eintrag aus, der zuerst vom DNS-Server empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="63f80-321">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

