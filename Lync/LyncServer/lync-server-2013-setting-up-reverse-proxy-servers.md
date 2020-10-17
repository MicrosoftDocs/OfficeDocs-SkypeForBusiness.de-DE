---
title: 'Lync Server 2013: Einrichten von Reverse-Proxyservern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 640d8e97cf8b7a31e11cb2dc8f1b1394e4b1aae3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521812"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="f072a-102">Einrichten von Reverse-Proxyservern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f072a-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f072a-103">_**Letztes Änderungsstand des Themas:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="f072a-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="f072a-104">Für Microsoft lync Server 2013 Edgeserver-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich, damit externe Clients auf den lync Server 2013-Webdienste (als *Webkomponenten* in Office Communications Server) auf dem Director und dem Home-Pool des Benutzers zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f072a-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="f072a-105">Beispielsweise ist für die folgenden Funktionen ein externer Zugriff über einen Reverseproxy erforderlich:</span><span class="sxs-lookup"><span data-stu-id="f072a-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="f072a-106">Herunterladen von Besprechungsinhalten durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="f072a-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="f072a-107">Erweitern von Verteilergruppen durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="f072a-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="f072a-108">Herunterladen von Dateien aus dem Adressbuchdienst durch Remotebenutzer</span><span class="sxs-lookup"><span data-stu-id="f072a-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="f072a-109">Zugriff auf den lync Web App-Client.</span><span class="sxs-lookup"><span data-stu-id="f072a-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="f072a-110">Zugriff auf die Webseite mit Einstellungen für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="f072a-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="f072a-111">Herstellen einer Verbindung mit dem Geräteaktualisierungswebdienst und Abrufen von Updates durch externe Geräte</span><span class="sxs-lookup"><span data-stu-id="f072a-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="f072a-112">Aktivieren von mobilen Anwendungen zum automatischen ermitteln und Verwenden von Mobility-URLs (MCX) aus dem Internet.</span><span class="sxs-lookup"><span data-stu-id="f072a-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="f072a-113">Aktivieren des lync 2013-Clients, der lync Windows Store-App und lync 2013 mobilen Clients zum Auffinden der lync Discover (autodiscover)-URLs und Verwenden von Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="f072a-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="f072a-114">Es wird empfohlen, den HTTP-Reverseproxy zum Veröffentlichen aller Webdienste in sämtlichen Pools zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f072a-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="f072a-115">Veröffentlichen https://ExternalFQDN/ \* veröffentlicht alle virtuellen IIS-Verzeichnisse für einen Pool.</span><span class="sxs-lookup"><span data-stu-id="f072a-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="f072a-116">Sie benötigen eine Veröffentlichungsregel für jeden Standard Edition-Server, Front-End-Pool oder Director oder Director-Pool in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f072a-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="f072a-117">Darüber hinaus müssen Sie die einfachen URLs veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f072a-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="f072a-118">Wenn die Organisation über einen Director oder einen Director-Pool verfügt, fängt der HTTP-Reverseproxy HTTP/HTTPS-Anforderungen an die einfachen URLs ab und leitet sie an das virtuelle Verzeichnis der externen Webdienste auf dem Director oder dem Director-Pool weiter.</span><span class="sxs-lookup"><span data-stu-id="f072a-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="f072a-119">Wenn Sie keinen Director bereitgestellt haben, müssen Sie einen Pool zur Verarbeitung von Anforderungen für einfache URLs festlegen.</span><span class="sxs-lookup"><span data-stu-id="f072a-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="f072a-120">(Wenn es sich hierbei nicht um den Homepool des Benutzers handelt, wird eine Weiterleitung an die Webdienste im Homepool des Benutzers durchgeführt.)</span><span class="sxs-lookup"><span data-stu-id="f072a-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="f072a-121">Die einfachen URLs können durch eine dedizierte Webveröffentlichungsregel verarbeitet werden, oder Sie können sie zu den öffentlichen Namen der Webveröffentlichungsregel für den Director hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f072a-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="f072a-122">Sie müssen auch die externe AutoErmittlungsdienst-URL veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f072a-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="f072a-123">Sie können Microsoft Forefront Threat Management Gateway 2010, ISA (Microsoft Internet Security and Acceleration Server) 2006 SP1 oder Internet Information Server 7,0, 7,5 oder 8,0 mit dem Application Request Routing (IIS arr) als Reverse-Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="f072a-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="f072a-124">In den detaillierten Schritten in diesem Abschnitt wird beschrieben, wie Sie Forefront Threat Management Gateway 2010 konfigurieren, und die Schritte zum Konfigurieren von ISA Server 2006 sind nahezu identisch.</span><span class="sxs-lookup"><span data-stu-id="f072a-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="f072a-125">Außerdem werden Anleitungen für IIS arr bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f072a-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="f072a-126">Wenn Sie einen anderen Reverseproxy verwenden, lesen Sie in der Dokumentation zu diesem Produkt nach, und ordnen Sie die hier definierten Anforderungen den zugehörigen Features in anderen Reverse-Proxys zu.</span><span class="sxs-lookup"><span data-stu-id="f072a-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f072a-127">IIS ARR (Internet Information Server Application Request Routing) ist eine vollständig getestete und unterstützte Option für die Implementierung eines Reverse-Proxys für lync Server 2010 und lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f072a-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="f072a-128">Im November 2012 haben Microsoft den Lizenzverkauf von Forefront Threat Management Gateway 2010 oder TMG eingestellt.</span><span class="sxs-lookup"><span data-stu-id="f072a-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="f072a-129">TMG ist weiterhin ein vollständig unterstütztes Produkt und steht weiterhin für Geräte zur Verfügung, die von Drittanbietern vertrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f072a-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="f072a-130">Außerdem bieten viele Hardware-Lastenausgleichsgeräte von Drittanbietern und Firewalls Unterstützung für Reverse-Proxys.</span><span class="sxs-lookup"><span data-stu-id="f072a-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="f072a-131">Für Hardwarelastenausgleichs und Firewalls, die Reverse-Proxyfunktionen bereitstellen, erkundigen Sie sich bei Ihrem Anbieter nach spezifischen Anweisungen zum Konfigurieren des Produkts für die Bereitstellung von Reverse-Proxy Unterstützung für lync Server.</span><span class="sxs-lookup"><span data-stu-id="f072a-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="f072a-132">Sie können auch Drittanbieteranzeigen, die die Dokumentation für Ihr Produkt an Microsoft übermittelt haben.</span><span class="sxs-lookup"><span data-stu-id="f072a-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="f072a-133">Die Unterstützung wird vom Drittanbieter für die Lösung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f072a-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="f072a-134">Informationen zu Drittanbietern, die bei der Bereitstellung von Lösungen aktiv sind, finden Sie unter <A href="https://go.microsoft.com/fwlink/?linkid=268730">für Microsoft lync qualifizierte Infrastruktur</A>.</span><span class="sxs-lookup"><span data-stu-id="f072a-134">To see third parties that are active in providing solutions, see <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="f072a-135">In den folgenden Themen und Verfahren werden Forefront Threat Management Gateway 2010 und IIS arr als Grundlage für die Bereitstellungs-und Konfigurationsverfahren verwendet.</span><span class="sxs-lookup"><span data-stu-id="f072a-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="f072a-136">Konfigurieren von Webfarm-FQDNs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f072a-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="f072a-137">Konfigurieren von Netzwerkadaptern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f072a-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="f072a-138">Anfordern und Konfigurieren eines Zertifikats für den Reverse-http-Proxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f072a-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="f072a-139">Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f072a-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="f072a-140">Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f072a-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="f072a-141">Erstellen von DNS-Einträgen für Reverse-Proxy Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f072a-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="f072a-142">Überprüfen des Zugriffs über den Reverseproxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f072a-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="f072a-143">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="f072a-143">Before You Begin</span></span>

<span data-ttu-id="f072a-144">Für die erfolgreiche Bereitstellung von Forefront Threat Management Gateway 2010 als Reverseproxy müssen Sie einen Server einrichten und konfigurieren, indem Sie die Voraussetzungen und Hardwareanforderungen beachten, die in der Forefront Threat Management Gateway 2010-Dokumentation angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="f072a-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="f072a-145">Lesen Sie das folgende Thema, das für eine ordnungsgemäße Konfiguration der Hardware und für die Installation von Forefront Threat Management Gateway 2010 auf dem Server festgelegt ist, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f072a-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="f072a-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="f072a-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="f072a-147">Hardwareempfehlungen für Forefront TMG 2010</span><span class="sxs-lookup"><span data-stu-id="f072a-147">Forefront TMG 2010 hardware recommendations</span></span>](https://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="f072a-148">Wenn Sie IIS arr erfolgreich als Reverse-Proxy bereitstellen möchten, lesen Sie die folgenden Themen, um die Hardware und die erforderliche Software zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f072a-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="f072a-149">Informationen zum Installieren von IIS auf Windows Server 2008 oder Windows Server 2008 R2 finden Sie unter [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="f072a-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="f072a-150">Informationen zum Installieren von IIS auf Windows Server 2012 finden Sie unter [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="f072a-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="f072a-151">Informationen zum Installieren von IIS auf Windows Server 2012 R2 finden Sie unter [Installing IIS 8,5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="f072a-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="f072a-152">Wenn Sie die Routingerweiterung für Anwendungsanforderungen für IIS herunterladen möchten, befolgen Sie die Anweisungen unter [Application Request Routing v 2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span><span class="sxs-lookup"><span data-stu-id="f072a-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="f072a-153">So installieren Sie arr für die Anweisungen unter [install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span><span class="sxs-lookup"><span data-stu-id="f072a-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f072a-154">Die derzeit veröffentlichten Anweisungen gelten für arr 2,0.</span><span class="sxs-lookup"><span data-stu-id="f072a-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="f072a-155">Für die Installation der Erweiterung gibt es keinen Unterschied zwischen den beiden Versionen.</span><span class="sxs-lookup"><span data-stu-id="f072a-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

