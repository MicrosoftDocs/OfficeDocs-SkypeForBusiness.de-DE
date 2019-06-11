---
title: 'Lync Server 2013: Szenarien für Reverseproxys'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1621e8bb0241e82f9f4678d4fe39a4f66f6bcf9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="658f2-102">Szenarien für Reverseproxys in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="658f2-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="658f2-103">_**Letztes Änderungsdatum des Themas:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="658f2-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="658f2-104">Umgekehrte Proxys sind in lync Server 2013 für den Zugriff auf Dienste und Ressourcen wie die Besprechungs-und Einwahl einfachen URLs, das Adressbuch, den Besprechungsinhalt, die Erweiterung der Verteilerliste, Mobilitätsdienste und andere erforderlich.</span><span class="sxs-lookup"><span data-stu-id="658f2-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="658f2-105">Das typische Reverse-Proxy-Szenario in lync Server 2013 ist es, externen Clients (beispielsweise dem Desktop Client oder lync Web App-Client) Zugriff auf externe Webdienste des Director-oder Front-End-Servers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="658f2-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="658f2-106">**Reverse-Proxy und externe Webdienste**</span><span class="sxs-lookup"><span data-stu-id="658f2-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="658f2-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="658f2-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="658f2-108">Während der Planungsphase definieren Sie die Anforderungen für den Reverse Proxy in einer lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="658f2-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="658f2-109">Der Reverse-Proxy ermöglicht den Zugriff auf Features für die folgenden externen Clients:</span><span class="sxs-lookup"><span data-stu-id="658f2-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="658f2-110">Microsoft lync 2013-Desktop Client</span><span class="sxs-lookup"><span data-stu-id="658f2-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="658f2-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="658f2-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="658f2-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="658f2-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="658f2-113">Windows Store-App für Lync</span><span class="sxs-lookup"><span data-stu-id="658f2-113">Lync Windows Store app</span></span>

<span data-ttu-id="658f2-114">Bei der Planung Ihrer lync Server 2013-Bereitstellung ordnen Sie die tatsächlichen Anforderungen für lync Server 2013 den Reverse-Proxy Features zu.</span><span class="sxs-lookup"><span data-stu-id="658f2-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="658f2-115">Externe Clients stellen eine Verbindung mit dem Reverse Proxy auf Port TCP 443 her und verwenden Secure Socket Layer (SSL) oder Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="658f2-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="658f2-116">Microsoft lync Mobile-Clients können eine Verbindung mit Port TCP 80 herstellen, allerdings nur, wenn die anfängliche Verbindung mit den lync Discover-Diensten hergestellt wird und der Administrator die richtigen DNS-Einträge (Domain Name System) konfiguriert hat, und akzeptiert, dass diese die Kommunikation wird nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="658f2-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="658f2-117">Lync Server 2013-externe Webdienste (bereitgestellt auf dem Front-End-Server und/oder der Director) erwarten eine Verbindung von einem Reverseproxy auf Port TCP 4443, und es wird erwartet, dass die Verbindung SSL/TLS ist.</span><span class="sxs-lookup"><span data-stu-id="658f2-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="658f2-118">Die empfohlenen Standard Überwachungsanschlüsse für die externen Webdienste sind TCP 8080 für HTTP-Datenverkehr und TCP 4443 für HTTPS-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="658f2-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="658f2-119">Der Topologie-Generator bietet die Möglichkeit, die Standardeinstellungen zu überschreiben und ihre eigenen Überwachungsanschlüsse für die externen Webdienste zu definieren.</span><span class="sxs-lookup"><span data-stu-id="658f2-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="658f2-120">Beachten Sie, dass der Reverse-Proxy mit den externen Webdiensten kommuniziert und die externen Clients mit dem Reverse-Proxy kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="658f2-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="658f2-121">Der externe Client kommuniziert mit dem Reverseproxy auf Port TCP 443, aber Sie können neu definieren, welchen Port der Reverse-Proxy mit den externen Webdiensten kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="658f2-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="658f2-122">Mit den Optionen im Topologie-Generator können Sie die standardmäßigen Überwachungsanschlüsse für die Webdienste überschreiben, um die Überwachung von Port Konflikten zu beheben, die in Ihrer Infrastruktur auftreten können.</span><span class="sxs-lookup"><span data-stu-id="658f2-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="658f2-123">Lync Server 2013-externe Webdienste erwarten einen unveränderten Host Header vom Client, um zu ermitteln, welches Dienst-und Webserververzeichnis der Client verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="658f2-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="658f2-124">Anforderungen sollten so aussehen, als ob Sie vom Reverse-Proxy stammen</span><span class="sxs-lookup"><span data-stu-id="658f2-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="658f2-125">Die externen Webdienste verwenden definierte Webserver Virtual Directories (vDir), die die für Clients angebotenen Dienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="658f2-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="658f2-126">Bestimmte extern identifizierbare Webdienste sind:</span><span class="sxs-lookup"><span data-stu-id="658f2-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="658f2-127">Die "Besprechung"-vDir für Webkonferenzbesprechungen</span><span class="sxs-lookup"><span data-stu-id="658f2-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="658f2-128">"Dialin"-vDir für Telefon-und Telefonkonferenzen</span><span class="sxs-lookup"><span data-stu-id="658f2-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="658f2-129">Der "Auto Ermittlungs-vDir" für die lync Windows Store-App, lync Mobile und den Desktop Client lync 2013.</span><span class="sxs-lookup"><span data-stu-id="658f2-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="658f2-130">Die AutoErmittlung in lync Server 2013 ist unter dem DNS-Namen "lyncdiscover" bekannt.</span><span class="sxs-lookup"><span data-stu-id="658f2-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="658f2-131">Auf Dienste, die nicht definiert sind, wird vom externen Client durch direkte Anrufe an die externen Webdienste zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="658f2-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="658f2-132">So können Sie beispielsweisedurch direkte Anrufe an externe Webdienste und zugeordnete vDirs auf die Expansion von Verteilergruppen (dlx) und den Adressbuchdienst (ABS) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="658f2-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="658f2-133">Der Client kennt den tatsächlichen Pfad zum vDir und erstellt basierend auf diesen Informationen einen Uniform Record Locator (URL).</span><span class="sxs-lookup"><span data-stu-id="658f2-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="658f2-134">Der Clientzugriff auf den Adressbuchdienst mit einer URL ähnlich wie`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="658f2-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="658f2-135">Der Office Web Apps-Server, wenn Konferenzen als Teil der lync Server-Topologie definiert und konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="658f2-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="658f2-136">Der Office Web Apps-Server ist ein separater Rollen Server und nicht als Teil der externen Webdienste konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="658f2-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="658f2-137">Dieser Server wird separat für den Clientzugriff veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="658f2-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="658f2-138">Definieren Sie SSL-Bridging für jeden Dienst.</span><span class="sxs-lookup"><span data-stu-id="658f2-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="658f2-139">Der externe Port TCP 443 wird dem external Web Services-Port von TCP 4443 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="658f2-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="658f2-140">Für unverschlüsselte http wird Port TCP 80 dem externen Webdienste-Port TCP 8080 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="658f2-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="658f2-141">Planen von Reverse Proxy-Listenern zum Veröffentlichen von Webserverressourcen</span><span class="sxs-lookup"><span data-stu-id="658f2-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="658f2-142">Sie können das Zertifikat für den Reverse-Proxy basierend auf den angebotenen Diensten anfordern und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="658f2-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="658f2-143">Wenn dieses Zertifikat mit dem richtigen Alternativen Betreff-Namen konfiguriert wurde, kann es von allen konfigurierten Listener auf dem Reverse-Proxy Server freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="658f2-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="658f2-144">Ressourcen, die für die Planung der Reverse-Proxybereitstellung verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="658f2-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="658f2-145">Datenerfassung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="658f2-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="658f2-146">Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="658f2-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="658f2-147">Portzusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="658f2-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="658f2-148">DNS-Zusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="658f2-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

