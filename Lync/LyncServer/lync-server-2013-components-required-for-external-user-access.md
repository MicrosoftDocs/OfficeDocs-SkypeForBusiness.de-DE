---
title: 'Lync Server 2013: Erforderliche Komponenten für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="81c24-102">Erforderliche Komponenten für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81c24-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81c24-103">_**Letztes Änderungsdatum des Themas:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="81c24-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="81c24-104">Die meisten Edgekomponenten werden in einem Umkreisnetzwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="81c24-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="81c24-105">Die folgenden Komponenten bilden die Edge-Topologie des Umkreisnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="81c24-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="81c24-106">Sofern nicht anders angegeben, sind die Komponenten Teil der [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und befinden sich im Umkreisnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="81c24-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="81c24-107">Zu den Edgekomponenten gehören:</span><span class="sxs-lookup"><span data-stu-id="81c24-107">Edge components include the following:</span></span>

  - <span data-ttu-id="81c24-108">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="81c24-108">Edge Servers</span></span>

  - <span data-ttu-id="81c24-109">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="81c24-109">Reverse proxies</span></span>

  - <span data-ttu-id="81c24-110">Firewalls</span><span class="sxs-lookup"><span data-stu-id="81c24-110">Firewalls</span></span>

  - <span data-ttu-id="81c24-111">Directors (optional und logisch im internen Netzwerk angeordnet)</span><span class="sxs-lookup"><span data-stu-id="81c24-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="81c24-112">Lastenausgleich für skalierte Edgetopologien (entweder DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="81c24-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="81c24-p102">Das Verfahren, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden, wird nicht unterstützt. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="81c24-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="81c24-115">Edgeservers</span><span class="sxs-lookup"><span data-stu-id="81c24-115">Edge Servers</span></span>

<span data-ttu-id="81c24-116">Die Edgeserver senden und empfangen Netzwerkdatenverkehr für die Dienste, die von externen Benutzern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="81c24-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="81c24-117">Der Edgeserver führt die folgenden Dienste aus:</span><span class="sxs-lookup"><span data-stu-id="81c24-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="81c24-118">**Access**   -Edgedienst der Access-Edgedienst stellt einen einzigen vertrauenswürdigen Verbindungspunkt für ausgehende und eingehende SIP-Datenverkehr (Session Initiation Protocol) bereit.</span><span class="sxs-lookup"><span data-stu-id="81c24-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="81c24-119">**Webkonferenz-Edgedienst**   der Webkonferenz-Edgedienst ermöglicht es externen Benutzern, an Besprechungen teilzunehmen, die auf Ihrer internen lync Server 2013-Bereitstellung gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="81c24-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="81c24-120">**A/v**   -Edgedienst der a/v-Edgedienst ermöglicht externen Benutzern die Bereitstellung von Audio, Video, Anwendungsfreigabe und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="81c24-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="81c24-121">Ihre Benutzer können Besprechungen mit externen Teilnehmern Audio und Video hinzufügen, und Sie können in Punkt-zu-Punkt-Sitzungen mithilfe von Audio und/oder Video direkt mit einem externen Benutzer kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="81c24-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="81c24-122">Der A/V-Edgedienst bietet auch Unterstützung für die Desktopfreigabe und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="81c24-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="81c24-123">**XMPP-Proxydienst**   der XMPP-Proxydienst akzeptiert und sendet Nachrichten zu und von konfigurierten XMPP-Verbundpartnern.</span><span class="sxs-lookup"><span data-stu-id="81c24-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="81c24-124">Autorisierte externe Benutzer können auf die Edgeserver zugreifen, um eine Verbindung mit ihrer internen lync Server 2013-Bereitstellung herzustellen, aber die Edgeserver bieten keine Möglichkeit für einen anderen Zugriff auf das interne Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="81c24-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81c24-125">Edgeserver werden für die Bereitstellung von Verbindungen für aktivierte lync-Clients und andere Microsoft Edge-Server bereitgestellt (wie in Verbundszenarien).</span><span class="sxs-lookup"><span data-stu-id="81c24-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="81c24-126">Sie sind nicht dafür vorgesehen, Verbindungen von anderen Endpunkt Client-oder Servertypen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="81c24-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="81c24-127">Der XMPP-Gatewayserver kann bereitgestellt werden, um Verbindungen mit konfigurierten XMPP-Partnern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="81c24-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="81c24-128">Der Edge-Server und das XMPP-Gateway können nur Endpunkt Verbindungen von diesen Client-und Verbundtypen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="81c24-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="81c24-129">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="81c24-129">Reverse Proxy</span></span>

<span data-ttu-id="81c24-130">Der Reverseproxy ist für Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="81c24-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="81c24-131">So ermöglichen Sie Benutzern das Herstellen einer Verbindung mit Besprechungen oder Einwahlkonferenzen mithilfe einfacher URLs</span><span class="sxs-lookup"><span data-stu-id="81c24-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="81c24-132">So aktivieren Sie externe Benutzer zum Herunterladen von Besprechungsinhalten</span><span class="sxs-lookup"><span data-stu-id="81c24-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="81c24-133">So aktivieren Sie externe Benutzer zum Erweitern von Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="81c24-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="81c24-134">So ermöglichen Sie Benutzern das Abrufen eines benutzerbasierten Zertifikats für die Clientzertifikat basierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="81c24-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="81c24-135">So aktivieren Sie Remotebenutzer zum Herunterladen von Dateien vom Adressbuch Server oder zum Übermitteln von Abfragen an den Adressbuch-Webabfrage Dienst</span><span class="sxs-lookup"><span data-stu-id="81c24-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="81c24-136">So ermöglichen Sie es Remotebenutzern, Updates für Client-und Geräte Software zu erhalten</span><span class="sxs-lookup"><span data-stu-id="81c24-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="81c24-137">So aktivieren Sie mobile Geräte, um Front-End-Server, die Mobilitätsdienste anbieten, automatisch zu erkennen</span><span class="sxs-lookup"><span data-stu-id="81c24-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="81c24-138">So aktivieren Sie Push-Benachrichtigungen auf mobilen Geräten über die Office 365-oder Apple Push Notification Services</span><span class="sxs-lookup"><span data-stu-id="81c24-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="81c24-139">Weitere Informationen zu Reverse-Proxys und den Anforderungen, die umgekehrte Proxys erfüllen müssen, finden Sie in den Details unter [Konfigurationsanforderungen für Reverse Proxy in lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="81c24-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81c24-140">Externe Benutzer benötigen keine VPN-Verbindung (virtuelles privates Netzwerk) mit Ihrer Organisation, um an der Kommunikation mit lync Server 2013 teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="81c24-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="81c24-141">Wenn Sie in Ihrer Organisation VPN-Technologie implementiert haben und Ihre Benutzer das VPN für lync verwenden, können Mediendatenverkehr (wie Videokonferenzen) beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="81c24-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="81c24-142">Sie sollten die Bereitstellungeines Mediums für Mediendatenverkehr in Frage stellen, um die Verbindung mit dem AV Edge-Dienst direkt herzustellen und das VPN zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="81c24-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="81c24-143">Ausführliche Informationen finden Sie im NextHop-Blog Artikel "Aktivieren von <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>lync Media zur Umgehung eines VPN-Tunnels" unter.</span><span class="sxs-lookup"><span data-stu-id="81c24-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="81c24-144">Firewall</span><span class="sxs-lookup"><span data-stu-id="81c24-144">Firewall</span></span>

<span data-ttu-id="81c24-145">Sie können Ihre Edge-Topologie nur mit einer externen Firewall oder mit externen und internen Firewalls bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="81c24-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="81c24-146">Zu den Szenarien-Architekturen gehören zwei Firewalls.</span><span class="sxs-lookup"><span data-stu-id="81c24-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="81c24-147">Die Verwendung von zwei Firewalls ist die empfohlene Vorgehensweise, da Sie ein striktes Routing von einem Netzwerkrand zum anderen gewährleistet und ihre interne Bereitstellung hinter zwei Firewall-Ebenen schützt.</span><span class="sxs-lookup"><span data-stu-id="81c24-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="81c24-148">Director</span><span class="sxs-lookup"><span data-stu-id="81c24-148">Director</span></span>

<span data-ttu-id="81c24-149">Bei einem Director handelt es sich um eine separate, optionale Serverrolle in lync Server 2013, in der keine Benutzerkonten zu Hause sind, oder Anwesenheits-oder Konferenzdienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="81c24-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="81c24-150">Sie fungiert als interner Server für den nächsten Hop, auf dem ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="81c24-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="81c24-151">Der Director authentifiziert eingehende Anforderungen und leitet Sie an den privaten Pool oder Server des Benutzers weiter.</span><span class="sxs-lookup"><span data-stu-id="81c24-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="81c24-152">Durch die Vorauthentifizierung beim Director können Sie Anforderungen aus Benutzerkonten, die für die Bereitstellung unbekannt sind, ablegen.</span><span class="sxs-lookup"><span data-stu-id="81c24-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="81c24-153">Ein Director hilft beim Isolieren von Standard Edition-Servern und Front-End-Servern in Enterprise Edition-Front-End-Pools vor böswilligem Datenverkehr wie DOS-Attacken (Denial-of-Service).</span><span class="sxs-lookup"><span data-stu-id="81c24-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="81c24-154">Wenn das Netzwerk bei einem solchen Angriff mit einem ungültigen externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director.</span><span class="sxs-lookup"><span data-stu-id="81c24-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="81c24-155">Ausführliche Informationen zur Verwendung von Directors finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="81c24-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81c24-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81c24-156">See Also</span></span>


[<span data-ttu-id="81c24-157">Anforderungen an das Hardwaregerät zum Lastenausgleich für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81c24-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

