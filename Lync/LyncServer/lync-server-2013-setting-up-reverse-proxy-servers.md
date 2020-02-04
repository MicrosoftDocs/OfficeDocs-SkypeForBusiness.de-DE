---
title: 'Lync Server 2013: Einrichten von Reverseproxyservern'
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
ms.openlocfilehash: fbc6e0aee918d08f47c6df88f91493cd62ae6a3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="58abe-102">Einrichten von Reverseproxyservern für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58abe-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58abe-103">_**Letztes Änderungsdatum des Themas:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="58abe-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="58abe-104">Für Microsoft lync Server 2013-Edgeserver-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk für externe Clients erforderlich, um auf die lync Server 2013-Webdienste (so genannte *Webkomponenten* in Office Communications Server) auf dem Director und dem privaten Pool des Benutzers zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="58abe-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="58abe-105">Zu den Features, die einen externen Zugriff über einen Reverseproxy erfordern, gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="58abe-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="58abe-106">Aktivieren von externen Benutzern zum Herunterladen von Besprechungsinhalten für Ihre Besprechungen</span><span class="sxs-lookup"><span data-stu-id="58abe-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="58abe-107">Aktivieren von externen Benutzern zum Erweitern von Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="58abe-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="58abe-108">Aktivieren von Remotebenutzern zum Herunterladen von Dateien aus dem Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="58abe-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="58abe-109">Zugriff auf den lync Web App-Client</span><span class="sxs-lookup"><span data-stu-id="58abe-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="58abe-110">Zugreifen auf die Webseite "Einstellungen für Einwahlkonferenzen"</span><span class="sxs-lookup"><span data-stu-id="58abe-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="58abe-111">Aktivieren externer Geräte zum Herstellen einer Verbindung mit dem Geräte Update-Webdienst und Abrufen von Updates</span><span class="sxs-lookup"><span data-stu-id="58abe-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="58abe-112">Aktivieren von mobilen Anwendungen zum automatischen Auffinden und Verwenden der Mobilitäts-URLs (MCX) aus dem Internet.</span><span class="sxs-lookup"><span data-stu-id="58abe-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="58abe-113">Aktivieren des lync 2013-Clients, der lync Windows Store-App und des lync 2013 Mobile-Clients zum Auffinden der URLs von lync Discover (autodiscover) und Verwenden der Unified Communications Web-API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="58abe-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="58abe-114">Wir empfehlen, den HTTP-Reverseproxy so zu konfigurieren, dass alle Webdienste in allen Pools veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="58abe-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="58abe-115">Publishing https://ExternalFQDN/\* veröffentlicht alle virtuellen IIS-Verzeichnisse für einen Pool.</span><span class="sxs-lookup"><span data-stu-id="58abe-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="58abe-116">Sie benötigen eine Veröffentlichungsregel für jeden Standard Edition-Server, Front-End-Pool oder Director-oder Director-Pool in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="58abe-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="58abe-117">Darüber hinaus müssen Sie die einfachen URLs veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="58abe-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="58abe-118">Wenn die Organisation über einen Director-oder Director-Pool verfügt, lauscht der HTTP-Reverseproxy auf HTTP/HTTPS-Anforderungen an die einfachen URLs und stellt Sie dem virtuellen Verzeichnis der externen Webdienste im Director-oder Director-Pool zur Ver, Proxys.</span><span class="sxs-lookup"><span data-stu-id="58abe-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="58abe-119">Wenn Sie keinen Director bereitgestellt haben, müssen Sie einen Pool angeben, um Anforderungen an einfache URLs zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="58abe-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="58abe-120">(Wenn es sich nicht um den Home-Pool des Benutzers handelt, wird er an die Webdienste im Home-Pool des Benutzers weitergeleitet).</span><span class="sxs-lookup"><span data-stu-id="58abe-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="58abe-121">Die einfachen URLs können von einer dedizierten Webveröffentlichungsregel verarbeitet werden, oder Sie können Sie den öffentlichen Namen der Webveröffentlichungsregel für den Director hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="58abe-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="58abe-122">Außerdem müssen Sie die URL des externen AutoErmittlungsdiensts veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="58abe-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="58abe-123">Sie können Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 oder Internet Information Server 7,0, 7,5 oder 8,0 mit Application Request Routing (IIS arr) als Reverse-Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="58abe-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="58abe-124">In den detaillierten Schritten in diesem Abschnitt wird beschrieben, wie Sie das Forefront Threat Management Gateway 2010 konfigurieren, und die Schritte zum Konfigurieren von ISA Server 2006 sind nahezu identisch.</span><span class="sxs-lookup"><span data-stu-id="58abe-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="58abe-125">Es werden auch Anleitungen für IIS arr bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="58abe-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="58abe-126">Wenn Sie einen anderen Reverseproxy verwenden, konsultieren Sie die Dokumentation für dieses Produkt, und ordnen Sie die hier definierten Anforderungen den zugehörigen Features in anderen Reverse-Proxys zu.</span><span class="sxs-lookup"><span data-stu-id="58abe-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="58abe-127">Internet Information Server Application Request Routing (IIS arr) ist eine vollständig getestete und unterstützte Option für die Implementierung eines Reverse-Proxys für lync Server 2010 und lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58abe-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="58abe-128">Im November 2012 hat Microsoft den Lizenzverkauf von Forefront Threat Management Gateway 2010 oder TMG eingestellt.</span><span class="sxs-lookup"><span data-stu-id="58abe-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="58abe-129">TMG ist nach wie vor ein vollständig unterstütztes Produkt und steht weiterhin für Verkauf von Geräten zur Verfügung, die von Drittanbietern verkauft werden.</span><span class="sxs-lookup"><span data-stu-id="58abe-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="58abe-130">Darüber hinaus bieten viele Hardware-Load-Balancer und Firewalls von Drittanbietern Reverse-Proxy-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="58abe-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="58abe-131">Bei Hardwarelastenausgleichs und Firewalls, die Reverse-Proxyfunktionen bereitstellen, erkundigen Sie sich bei Ihrem Anbieter nach spezifischen Anweisungen zum Konfigurieren des Produkts, um die Unterstützung für den Reverse-Proxy für lync Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="58abe-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="58abe-132">Sie können auch Drittanbieteranzeigen, die die Dokumentation für Ihr Produkt an Microsoft übermittelt haben.</span><span class="sxs-lookup"><span data-stu-id="58abe-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="58abe-133">Der Support wird von der Drittpartei für Ihre Lösung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="58abe-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="58abe-134">Informationen zu Drittanbietern, die bei der Bereitstellung von Lösungen aktiv sind, finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=268730">für Microsoft lync qualifizierte Infrastruktur</A>.</span><span class="sxs-lookup"><span data-stu-id="58abe-134">To see third parties that are active in providing solutions, see <A href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="58abe-135">Die folgenden Themen und Verfahren verwenden Forefront Threat Management Gateway 2010 und IIS arr als Grundlage für die Bereitstellungs-und Konfigurationsverfahren.</span><span class="sxs-lookup"><span data-stu-id="58abe-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="58abe-136">Konfigurieren von Webfarm-FQDNs für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58abe-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="58abe-137">Konfigurieren von Netzwerkadaptern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58abe-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="58abe-138">Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58abe-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="58abe-139">Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58abe-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="58abe-140">Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58abe-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="58abe-141">Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58abe-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="58abe-142">Überprüfen des Zugriffs über den Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58abe-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="58abe-143">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="58abe-143">Before You Begin</span></span>

<span data-ttu-id="58abe-144">Wenn Sie Forefront Threat Management Gateway 2010 als Reverse-Proxy erfolgreich bereitstellen möchten, müssen Sie einen Server einrichten und konfigurieren, indem Sie die Voraussetzungen und Hardwareanforderungen verwenden, die in der Forefront Threat Management Gateway 2010-Dokumentation definiert sind.</span><span class="sxs-lookup"><span data-stu-id="58abe-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="58abe-145">Lesen Sie das folgende Thema, das für die ordnungsgemäße Konfiguration der Hardware und die Installation von Forefront Threat Management Gateway 2010 auf dem Server festgesetzt ist, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="58abe-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="58abe-146">Forefront Threat Management-Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="58abe-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="58abe-147">Empfehlungen für Forefront TMG 2010-Hardware</span><span class="sxs-lookup"><span data-stu-id="58abe-147">Forefront TMG 2010 hardware recommendations</span></span>](http://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="58abe-148">Wenn Sie IIS arr erfolgreich als Reverse-Proxy bereitstellen möchten, lesen Sie die folgenden Themen, um die Hardware und die erforderliche Software zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="58abe-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="58abe-149">Informationen zum Installieren von IIS unter Windows Server 2008 oder Windows Server 2008 R2 finden Sie unter [Installieren von IIS 7 unter Windows Server 2008 oder Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296) .</span><span class="sxs-lookup"><span data-stu-id="58abe-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="58abe-150">Informationen zum Installieren von IIS unter Windows Server 2012 finden Sie unter [Installieren von IIS 8 unter Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="58abe-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="58abe-151">Informationen zum Installieren von IIS unter Windows Server 2012 R2 finden Sie unter [Installieren von IIS 8,5 unter Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687) .</span><span class="sxs-lookup"><span data-stu-id="58abe-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="58abe-152">Zum Herunterladen der Anwendungs Anforderungs-Routingerweiterung für IIS befolgen Sie die Anweisungen unter [Application Request Routing v 2.5 herunterladen](http://go.microsoft.com/fwlink/?linkid=291298) .</span><span class="sxs-lookup"><span data-stu-id="58abe-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](http://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="58abe-153">So installieren Sie arr für die Anweisungen unter [Installieren von Anwendungs Anforderungs Routing, Version 2](http://go.microsoft.com/fwlink/?linkid=291299)</span><span class="sxs-lookup"><span data-stu-id="58abe-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](http://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58abe-154">Die aktuell geposteten Anweisungen gelten für arr 2,0.</span><span class="sxs-lookup"><span data-stu-id="58abe-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="58abe-155">Für die Installation der Erweiterung gibt es keinen Unterschied zwischen den beiden Versionen.</span><span class="sxs-lookup"><span data-stu-id="58abe-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

