---
title: 'Lync Server 2013: Anforderungen für den AutoErmittlungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec6c3ada06312f816a75f5539593336addc8d2b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="f9530-102">Anforderungen für den AutoErmittlungsdienst für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9530-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9530-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="f9530-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="f9530-104">Der Microsoft lync Server 2013 AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool-Server ausgeführt und kann, wenn er in DNS veröffentlicht wird, von mobilen Geräten mit lync Mobile zum Auffinden von Mobilitätsdiensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9530-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="f9530-105">Bevor Mobile Geräte, auf denen lync Mobile ausgeführt wird, die automatische Ermittlung nutzen können, müssen Sie die Listen alternativer Zertifikatsantrags Teller Namen in allen Directors und Front-End-Server ändern, auf denen der AutoErmittlungsdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f9530-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="f9530-106">Darüber hinaus kann es erforderlich sein, die Listen Betreff alternativer Namen auf Zertifikaten zu ändern, die für externe Webdienst-Veröffentlichungsregeln für Reverse-Proxies verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9530-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="f9530-107">Ausführliche Informationen zu den Einträgen für alternative Antragstellernamen, die für Directors, Front-End-Server und Reverse-Proxies erforderlich sind, finden Sie unter [Technical Requirements for Mobility in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span><span class="sxs-lookup"><span data-stu-id="f9530-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="f9530-108">Die Entscheidung, ob auf Reverseproxys alternative Antragstellernamen verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst an Port 80 oder an Port 443 veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="f9530-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="f9530-109">**Veröffentlicht auf Port 80**   keine Zertifikat Änderungen sind erforderlich, wenn die erste Abfrage an den AutoErmittlungsdienst über Port 80 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f9530-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="f9530-110">Dies liegt daran, dass Mobile Geräte, auf denen lync läuft, extern auf den Reverseproxy auf Port 80 zugreifen und dann an Port 8080 intern an einen Director oder Front-End-Server weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="f9530-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="f9530-111">Detaillierte Informationen finden Sie im Abschnitt "Anfänglicher AutoErmittlungsprozess über Port 80" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="f9530-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="f9530-112">**Veröffentlicht am Port 443**   die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss ein \*lyncdiscover enthalten.\< sipdomain "\> \* -Eintrag für jede SIP-Domäne in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f9530-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="f9530-113">Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Prozess, für öffentliche Zertifikate, die in der Veröffentlichungsregel des Webdiensts verwendet werden, kann das Hinzufügen mehrerer alternativer alternativen Namen teuer werden.</span><span class="sxs-lookup"><span data-stu-id="f9530-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="f9530-114">Um dieses Problem zu umgehen, unterstützen wir die anfängliche automatische Ermittlungs Verbindung über Port 80, die dann an Port 8080 auf dem Director oder Front-End-Server umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f9530-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="f9530-115">Nehmen Sie beispielsweise an, dass ein mobiler Client, auf dem lync Mobile läuft, für die Anmeldung bei lync Server 2013 mit dem automatischen Ermittlungs Feature unter Verwendung von http für die anfängliche Anforderung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f9530-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="f9530-116">Anfänglicher Auto Ermittlungsprozess für mobile Geräte mit Port 80</span><span class="sxs-lookup"><span data-stu-id="f9530-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="f9530-117">Mobiles Gerät, auf dem lync Mobile läuft, sucht nach lyncdiscover.contoso.com mithilfe von DNS, wobei ein A-Eintrag vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f9530-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="f9530-118">Externe DNS gibt die IP-Adresse für die externen Webdienste an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="f9530-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="f9530-119">Mobiles Gerät, auf dem lync http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com Mobile läuft, sendet eine Anforderung an den Reverse-Proxy</span><span class="sxs-lookup"><span data-stu-id="f9530-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="f9530-120">Die Webveröffentlichungsregel wird die Anforderung von Port 80 extern an Port 8080 intern überbrücken, um Sie dann an einen Director oder Front-End-Server weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="f9530-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="f9530-121">Da es sich um eine HTTP- und keine HTTPS-Anforderung handelt, sind keine Änderungen am Zertifikat der Veröffentlichungsregel für externe Webdienste erforderlich, damit der AutoErmittlungsdienst unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f9530-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="f9530-122">Der AutoErmittlungsdienst gibt die externen Webdienst-URLs (im HTTPS-Format) zurück.</span><span class="sxs-lookup"><span data-stu-id="f9530-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="f9530-123">Das Mobile Gerät, auf dem lync Mobile läuft, kann dann erneut eine Verbindung mit dem Reverseproxy an Port 443 herstellen und wird über 4443 an den Mobilitätsdienst umgeleitet, der im Home-Pool des Benutzers läuft.</span><span class="sxs-lookup"><span data-stu-id="f9530-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="f9530-124">Da die HTTPS-Abfrage an die externe Webdienste-URL und nicht an die AutoErmittlungsdienst-URL gerichtet ist, ist sie erfolgreich, da das Zertifikat bereits Einträge für alternative Antragstellernamen der externen Webdienste-FQDNs enthält.</span><span class="sxs-lookup"><span data-stu-id="f9530-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="f9530-125">In diesem Szenario sind zur Unterstützung der Mobilität keine Zertifikatänderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f9530-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9530-126">Wenn der Zielwebserver über ein Zertifikat verfügt, das "lyncdiscover.contoso.com" als alternativen Antragstellernamen enthält:</span><span class="sxs-lookup"><span data-stu-id="f9530-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="f9530-127">a.&nbsp;&nbsp;&nbsp;der Webserver antwortet mit einem "Server Hello" und keinem Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="f9530-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="f9530-128">b.&nbsp;&nbsp;&nbsp;das Mobile Gerät, auf dem lync Mobile läuft, beendet die Sitzung sofort.</span><span class="sxs-lookup"><span data-stu-id="f9530-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="f9530-129">Wenn der Zielwebserver über ein Zertifikat verfügt, das "lyncdiscover.contoso.com" als alternativen Antragstellernamen enthält:</span><span class="sxs-lookup"><span data-stu-id="f9530-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="f9530-130">a.&nbsp;&nbsp;&nbsp;der Webserver antwortet mit einem "Server Hello" und einem Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="f9530-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="f9530-131">b.&nbsp;&nbsp;&nbsp;mobiles Gerät, auf dem lync Mobile ausgeführt wird, überprüft das Zertifikat und schließt den Hand Shake ab.</span><span class="sxs-lookup"><span data-stu-id="f9530-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="f9530-132">Zur Unterstützung einer anfänglichen Verbindung mit dem AutoErmittlungsdienst über Port 80 auf dem Reverseproxyserver können Sie eine HTTP-Veröffentlichungsregel erstellen, die dem folgenden Beispiel einer Webveröffentlichungsregel für einen Forefront Threat Management Gateway 2010-Reverseproxy ähnelt:</span><span class="sxs-lookup"><span data-stu-id="f9530-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="f9530-133">Erstellen Sie eine neue Webveröffentlichungsregel (beispielsweise **Lync Server-AutoErmittlung (HTTP)**).</span><span class="sxs-lookup"><span data-stu-id="f9530-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="f9530-134">Geben Sie in **Öffentlicher Name** "lyncdiscover.contoso.com" ein.</span><span class="sxs-lookup"><span data-stu-id="f9530-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="f9530-135">Wählen Sie auf der Registerkarte **Bridging** nur die Option zum Überbrücken von Anforderungen von Port 80 zu Port 8080 aus.</span><span class="sxs-lookup"><span data-stu-id="f9530-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="f9530-136">Wählen Sie auf der Registerkarte **Authentifizierung** die Option **Keine Authentifizierung** und **Keine direkte Authentifizierung des Clients** aus.</span><span class="sxs-lookup"><span data-stu-id="f9530-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="f9530-137">Commit ändert und verschiebt die Regel an den Anfang der Liste der lync-Regeln (zuerst in der Verarbeitungsreihenfolge).</span><span class="sxs-lookup"><span data-stu-id="f9530-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="f9530-138">Mobilität für die Bereitstellung geteilter Domänen</span><span class="sxs-lookup"><span data-stu-id="f9530-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="f9530-139">Ein freigegebener SIP-Adressraum, der auch als *geteilte Domäne*bezeichnet wird, oder eine *hybridbereitstellung* ist eine Konfiguration, in der Benutzer über eine lokale Bereitstellung und eine Online Umgebung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f9530-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="f9530-140">Das gewünschte Ergebnis besteht darin, dass ein Benutzer unabhängig davon, wo sich sein Heimatserver befindet (lokal oder Online), sich bei der Bereitstellung anmeldet und zu seinem Standort des Heimat Servers umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f9530-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="f9530-141">Um dies zu erreichen, wird das Auto Ermittlungs Feature von Microsoft lync Server 2013 verwendet, um den Online Benutzer zur Online Topologie umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="f9530-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="f9530-142">Konfigurieren Sie dazu die URL (Uniform Resource Locator) der AutoErmittlung mithilfe der lync Server-Verwaltungsshell und der Cmdlets **Get-CsHostingProvider** und **CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="f9530-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="f9530-143">Sie müssen folgende bereitgestellte Attribute erfassen und aufzeichnen:</span><span class="sxs-lookup"><span data-stu-id="f9530-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="f9530-144">Geben Sie im lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f9530-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="f9530-p105">Suchen Sie in den Ergebnissen nach dem Onlineanbieter mit dem Attribut**ProxyFQDN**, z. B. "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="f9530-p105">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="f9530-147">Zeichnen Sie den Wert von "ProxyFQDN" auf.</span><span class="sxs-lookup"><span data-stu-id="f9530-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="f9530-148">Aktivieren Sie den Partnerverbund in der lokalen lync Server-Systemsteuerung, sodass der Verbund mit dem Onlineanbieter zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="f9530-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="f9530-p106">Aktivieren Sie den Partnerverbund für den Onlineanbieter. Standardmäßig sind alle Onlinebenutzer für den Domänenverbund aktiviert und können mit allen Domänen kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="f9530-p106">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="f9530-151">Wenn Sie gesperrte und zulässige Domänen definieren, legen Sie die Domänen fest, die Sie explizit zulassen oder sperren möchten.</span><span class="sxs-lookup"><span data-stu-id="f9530-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="f9530-152">Für den Onlineverbund müssen Sie Firewallausnahmen, Zertifikate und den DNS-Hosteinträge (A oder AAAA bei Verwendung von IPv6) planen.</span><span class="sxs-lookup"><span data-stu-id="f9530-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="f9530-153">Außerdem müssen Sie Verbundrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f9530-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="f9530-154">Ausführliche Informationen finden Sie unter [Planung für lync Server 2013 und Office Communications Server Partnerverbund](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="f9530-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

