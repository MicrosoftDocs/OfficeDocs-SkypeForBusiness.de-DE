---
title: 'Lync Server 2013: Zertifikatanforderungen für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7000456629a91742350b9866dc9e1441c18eee57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="682aa-102">Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="682aa-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="682aa-103">_**Letztes Änderungsstand des Themas:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="682aa-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="682aa-104">Microsoft lync Server 2013 Kommunikationssoftware unterstützt die Verwendung eines einzelnen öffentlichen Zertifikats für Access-und Webkonferenz-Edge-externe Schnittstellen sowie den a/V-Authentifizierungsdienst.</span><span class="sxs-lookup"><span data-stu-id="682aa-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="682aa-105">Die interne Edge-Schnittstelle verwendet in der Regel ein privates Zertifikat, das von einer internen Zertifizierungsstelle ausgestellt wurde, kann aber auch ein öffentliches Zertifikat verwenden, vorausgesetzt, es stammt von einer vertrauenswürdigen öffentlichen Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="682aa-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="682aa-106">Der Reverseproxy in Ihrer Bereitstellung verwendet ein öffentliches Zertifikat und verschlüsselt die Kommunikation vom Reverseproxy zu Clients und dem Reverseproxy mit internen Servern mithilfe von http (also Transport Layer Security over HTTP).</span><span class="sxs-lookup"><span data-stu-id="682aa-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="682aa-107">Im Folgenden finden Sie die Anforderungen für das öffentliche Zertifikat, das für die externen Edgeschnittstellen für Zugriff und Webkonferenzen sowie für den Audio-Video-Authentifizierungsdienst verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="682aa-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="682aa-108">Das Zertifikat muss von einer vertrauenswürdigen öffentlichen Zertifizierungsstelle ausgestellt werden, die alternative Antragstellernamen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="682aa-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="682aa-109">Ausführliche Informationen finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)Microsoft Knowledge Base-Artikel 929395, "Unified Communications Zertifikat Partner für Exchange Server und für Communications Server" unter.</span><span class="sxs-lookup"><span data-stu-id="682aa-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="682aa-p103">Wenn das Zertifikat in einem Edgepool verwendet werden soll, muss es als exportierbares Zertifikat erstellt werden, und es muss auf jedem Edgeserver im Edgepool das gleiche Zertifikat verwendet werden. Der private Schlüssel als exportierbarer Schlüssel ist für die Verwendung mit dem Audio-Video-Authentifizierungsdienst notwendig, der für alle Edgeserver des Pools den gleichen privaten Schlüssel verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="682aa-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="682aa-112">Wenn Sie die Verfügbarkeit Ihrer Audio/Video-Dienste maximieren möchten, überprüfen Sie die Zertifikatanforderungen für die Implementierung eines entkoppelten A/V-Edgedienst Zertifikats (ein separates A/V-Edgedienst Zertifikat aus dem anderen externen Edge-Zertifikat).</span><span class="sxs-lookup"><span data-stu-id="682aa-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="682aa-113">Ausführliche Informationen finden Sie unter [Änderungen in lync Server 2013, die sich auf die Edgeserver Planung auswirken](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Planen von Edgeserver Zertifikaten in lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) und [Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Roll in der Gruppe CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="682aa-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="682aa-114">Der Antragstellername des Zertifikats ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) der Zugriffs-Edgedienst externen Schnittstelle oder VIP des Hardwarelastenausgleichs (beispielsweise Access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="682aa-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="682aa-115">).</span><span class="sxs-lookup"><span data-stu-id="682aa-115">).</span></span> <span data-ttu-id="682aa-116">Der Antragstellername darf kein Platzhalterzeichen sein, er muss ein expliziter Name sein.</span><span class="sxs-lookup"><span data-stu-id="682aa-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="682aa-117">Für lync Server 2013 ist dies nicht mehr erforderlich, wird aber weiterhin für die Kompatibilität mit Office Communications Server empfohlen.</span><span class="sxs-lookup"><span data-stu-id="682aa-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="682aa-118">Die Liste der alternativen Antragstellernamen enthält folgende FQDNs:</span><span class="sxs-lookup"><span data-stu-id="682aa-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="682aa-119">Die Zugriffs-Edgedienst externe Schnittstelle oder Hardwaregerät zum Lastenausgleich (beispielsweise SIP.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="682aa-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="682aa-120">Auch wenn der Antragstellername des Zertifikats dem FQDN des Zugriffsedges entspricht, muss der alternative Antragstellername auch den FQDN des Zugriffs-Edgeservers enthalten, da TLS (Transport Layer Security) den Antragstellernamen ignoriert und zur Überprüfung die Einträge für alternative Antragstellernamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="682aa-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="682aa-121">Die externe Edgeschnittstelle für Webkonferenzen oder die VIP eines Hardwaregeräts zum Lastenausgleich (zum Beispiel "webcon.contoso.com").</span><span class="sxs-lookup"><span data-stu-id="682aa-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="682aa-122">Wenn Sie die automatische Clientkonfiguration oder Partnerverbundfunktionen nutzen, geben Sie auch alle in Ihrem Unternehmen verwendeten FQDNs der SIP-Domäne an (zum Beispiel "sip.contoso.com", "sip.fabrikam.com").</span><span class="sxs-lookup"><span data-stu-id="682aa-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="682aa-123">Der A/V-Edgedienst verwendet nicht den Antragstellernamen oder die Einträge für alternative Antragstellernamen.</span><span class="sxs-lookup"><span data-stu-id="682aa-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="682aa-124">Die Reihenfolge der FQDNs in den alternativen Antragstellernamen spielt keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="682aa-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="682aa-p106">Wenn Sie an einem Standort mehrere Edgeserver mit Lastenausgleich bereitstellen, müssen alle auf den Edgeservern installierten Zertifikate für den Audio-Video-Authentifizierungsdienst von der gleichen Zertifizierungsstelle stammen und den gleichen privaten Schlüssel verwenden. Beachten Sie, dass der private Schlüssel des Zertifikats exportierbar sein muss, unabhängig davon, ob das Zertifikat auf einem oder mehreren Edgeservern verwendet wird. Dies gilt auch, wenn Sie das Zertifikat von einem anderen Computer als dem Edgeserver anfordern.</span><span class="sxs-lookup"><span data-stu-id="682aa-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="682aa-129">Folgende Anforderungen gelten für das private (oder öffentliche) Zertifikat für die interne Edgeschnittstelle:</span><span class="sxs-lookup"><span data-stu-id="682aa-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="682aa-130">Das Zertifikat kann von einer internen Zertifizierungsstelle oder einer vertrauenswürdigen öffentlichen Zertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="682aa-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="682aa-p107">Beim Antragstellernamen des Zertifikats handelt es sich üblicherweise um den FQDN der internen Edgeschnittstelle oder um die VIP eines Hardwaregeräts zum Lastenausgleich (zum Beispiel "lsedge.contoso.com"). Für die interne Edgeschnittstelle können Sie jedoch auch ein Platzhalterzertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="682aa-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="682aa-133">Eine Liste mit alternativen Antragstellernamen ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="682aa-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="682aa-134">Der Reverseproxy Ihrer Bereitstellungsdienste erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="682aa-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="682aa-135">Zugriff externer Benutzer auf Besprechungsinhalte bei Besprechungen</span><span class="sxs-lookup"><span data-stu-id="682aa-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="682aa-136">Zugriff externer Benutzer für das Erweitern und Anzeigen von Mitgliedern von Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="682aa-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="682aa-137">Zugriff externer Benutzer auf herunterladbare Dateien vom Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="682aa-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="682aa-138">Zugriff externer Benutzer auf den lync Web App-Client</span><span class="sxs-lookup"><span data-stu-id="682aa-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="682aa-139">Zugriff externer Benutzer auf die Webseite für Einwahlkonferenzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="682aa-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="682aa-140">Zugriff externer Benutzer auf den Standortinformationsdienst</span><span class="sxs-lookup"><span data-stu-id="682aa-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="682aa-141">Zugriff durch externe Geräte auf den Geräteaktualisierungsdienst und die Berechtigung, Updates anzufordern</span><span class="sxs-lookup"><span data-stu-id="682aa-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="682aa-142">Der Reverseproxy veröffentlicht die URLs für die Webkomponenten auf internen Servern.</span><span class="sxs-lookup"><span data-stu-id="682aa-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="682aa-143">Die Webkomponenten-URLs werden auf dem Director, Front-End-Server oder Front-End-Pool als **externe Webdienste** im Topologie-Generator definiert.</span><span class="sxs-lookup"><span data-stu-id="682aa-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="682aa-144">Einträge mit Platzhalterzeichen werden im Feld für den alternativen Antragstellernamen des für den Reverseproxy zugewiesenen Zertifikats unterstützt.</span><span class="sxs-lookup"><span data-stu-id="682aa-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="682aa-145">Ausführliche Informationen dazu, wie Sie die Zertifikatanforderung für den Reverseproxy konfigurieren, finden Sie unter [Anforderung und Konfigurieren eines Zertifikats für den Reverse-http-Proxy in lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="682aa-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="682aa-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="682aa-146">See Also</span></span>


[<span data-ttu-id="682aa-147">Unterstützung von Platzhalterzertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="682aa-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

