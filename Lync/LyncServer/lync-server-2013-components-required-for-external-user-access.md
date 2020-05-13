---
title: 'Lync Server 2013: erforderliche Komponenten für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05c4b2845f4146c6394712951089750299ce60b7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="0640f-102">Erforderliche Komponenten für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0640f-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0640f-103">_**Letztes Änderungsstand des Themas:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="0640f-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="0640f-104">Die meisten Edge-Komponenten werden in einem Umkreisnetzwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0640f-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="0640f-105">Die folgenden Komponenten bilden die Edge-Topologie des Umkreisnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="0640f-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="0640f-106">Sofern nicht anders angegeben, sind die Komponenten Teil der [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und befinden sich im Umkreisnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="0640f-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="0640f-107">Zu den Edge-Komponenten zählen folgende:</span><span class="sxs-lookup"><span data-stu-id="0640f-107">Edge components include the following:</span></span>

  - <span data-ttu-id="0640f-108">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="0640f-108">Edge Servers</span></span>

  - <span data-ttu-id="0640f-109">Reverse-Proxies</span><span class="sxs-lookup"><span data-stu-id="0640f-109">Reverse proxies</span></span>

  - <span data-ttu-id="0640f-110">Firewalls</span><span class="sxs-lookup"><span data-stu-id="0640f-110">Firewalls</span></span>

  - <span data-ttu-id="0640f-111">Directors (optional und logisch im internen Netzwerk gespeichert)</span><span class="sxs-lookup"><span data-stu-id="0640f-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="0640f-112">Lastenausgleich für skalierte Edge-Topologien (entweder DNS-Lastenausgleich oder ein Hardwaregerät zum Lastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="0640f-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0640f-p102">Es wird nicht unterstützt, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="0640f-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="0640f-115">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="0640f-115">Edge Servers</span></span>

<span data-ttu-id="0640f-116">Die Edgeserver senden und empfangen Netzwerkdatenverkehr für die Dienste, die von externen Benutzern von der internen Bereitstellung angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="0640f-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="0640f-117">Im Edgeserver werden die folgenden Dienste ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="0640f-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="0640f-118">**Zugriffs-Edgedienst**     Das Zugriffs-Edgedienst stellt einen einzelnen vertrauenswürdigen Verbindungspfad für ausgehenden und eingehenden SIP-Datenverkehr (Session Initiation Protocol) bereit.</span><span class="sxs-lookup"><span data-stu-id="0640f-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="0640f-119">**Webkonferenz-Edgedienst**     Mit dem Webkonferenz-Edgedienst können externe Benutzer an Besprechungen teilnehmen, die in ihrer internen lync Server 2013-Bereitstellung gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="0640f-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="0640f-120">**A/V-Edgedienst**     In der A/V-Edgedienst werden Audio-, Video-, Anwendungsfreigabe und Dateiübertragung für externe Benutzer verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="0640f-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="0640f-121">Ihre Benutzer können Besprechungen, die externe Teilnehmer einschließen, Audio und Video hinzufügen, und Sie können über Audio und/oder Video direkt mit einem externen Benutzer in den "Points-to-Points"-Sitzungen kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="0640f-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="0640f-122">Die A/V-Edgedienst bietet auch Unterstützung für Desktopfreigabe und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="0640f-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="0640f-123">**XMPP-Proxy Dienst**     Der XMPP-Proxy Dienst akzeptiert und sendet XMPP-Nachrichten (Extensible Messaging and Presence Protocol) an und von konfigurierten XMPP-Verbundpartnern.</span><span class="sxs-lookup"><span data-stu-id="0640f-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="0640f-124">Autorisierte externe Benutzer können auf die Edgeserver zugreifen, um eine Verbindung mit ihrer internen lync Server 2013-Bereitstellung herzustellen, aber die Edgeserver bieten keine Möglichkeit für einen anderen Zugriff auf das interne Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="0640f-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0640f-125">Edgeserver werden bereitgestellt, um Verbindungen für aktivierte lync-Clients und andere Microsoft-Edgeserver (wie in Verbundszenarien) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0640f-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="0640f-126">Sie sind nicht für Verbindungen von anderen Endpunkt Client-oder Servertypen ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="0640f-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="0640f-127">Der XMPP-Gatewayserver kann bereitgestellt werden, um Verbindungen mit konfigurierten XMPP-Partnern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0640f-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="0640f-128">Der Edgeserver und das XMPP-Gateway können nur Endpunkt Verbindungen von diesen Client-und Verbundtypen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0640f-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="0640f-129">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="0640f-129">Reverse Proxy</span></span>

<span data-ttu-id="0640f-130">Für Folgendes ist der Reverseproxy erforderlich:</span><span class="sxs-lookup"><span data-stu-id="0640f-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="0640f-131">So ermöglichen Sie Benutzern das Herstellen einer Verbindung mit Besprechungen oder Einwahlkonferenzen mithilfe einfacher URLs</span><span class="sxs-lookup"><span data-stu-id="0640f-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="0640f-132">So ermöglichen Sie externen Benutzern das Herunterladen von Besprechungsinhalten</span><span class="sxs-lookup"><span data-stu-id="0640f-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="0640f-133">So aktivieren Sie externe Benutzer zum Erweitern von Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="0640f-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="0640f-134">So ermöglichen Sie dem Benutzer das Abrufen eines benutzerbasierten Zertifikats für die Clientzertifikat basierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0640f-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="0640f-135">So ermöglichen Sie Remotebenutzern das Herunterladen von Dateien vom Adressbuch Server oder das Übermitteln von Abfragen an die Adressbuch-Webabfragedienst</span><span class="sxs-lookup"><span data-stu-id="0640f-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="0640f-136">So ermöglichen Sie Remotebenutzern das Abrufen von Updates für Client-und Geräte Software</span><span class="sxs-lookup"><span data-stu-id="0640f-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="0640f-137">So aktivieren Sie mobile Geräte zum automatischen ermitteln von Front-End-Servern, die Mobilitätsdienste anbieten</span><span class="sxs-lookup"><span data-stu-id="0640f-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="0640f-138">So aktivieren Sie Push-Benachrichtigungen für mobile Geräte von Microsoft 365, Office 365 oder Apple Push Notification Services</span><span class="sxs-lookup"><span data-stu-id="0640f-138">To enable push notifications to mobile devices from the Microsoft 365, Office 365, or Apple push notification services</span></span>

<span data-ttu-id="0640f-139">Weitere Informationen zu Reverse-Proxies und den Anforderungen, die Reverse-Proxies erfüllen müssen, finden Sie in den Details unter [Konfigurationsanforderungen für Reverse Proxy in lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="0640f-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0640f-140">Externe Benutzer benötigen keine VPN-Verbindung (Virtual Private Network) zu Ihrer Organisation, um mit lync Server 2013 an einer Kommunikation teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="0640f-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="0640f-141">Wenn Sie VPN-Technologie in Ihrer Organisation implementiert haben und Ihre Benutzer das VPN für lync verwenden, kann der Mediendatenverkehr (beispielsweise Videokonferenzen) beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="0640f-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="0640f-142">Sie sollten einen Mittel für den Mediendatenverkehr bereitstellen, um eine Verbindung mit dem AV-Edgedienst direkt herzustellen und das VPN zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="0640f-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="0640f-143">Ausführliche Informationen finden Sie im NextHop-Blog-Artikel "Aktivieren von lync Media zur Umgehung eines VPN-Tunnels" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A> .</span><span class="sxs-lookup"><span data-stu-id="0640f-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="0640f-144">Firewall</span><span class="sxs-lookup"><span data-stu-id="0640f-144">Firewall</span></span>

<span data-ttu-id="0640f-145">Sie können Ihre Edge-Topologie nur mit einer externen Firewall oder sowohl mit externen als auch mit internen Firewalls bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0640f-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="0640f-146">Die Szenario-Architekturen umfassen zwei Firewalls.</span><span class="sxs-lookup"><span data-stu-id="0640f-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="0640f-147">Die Verwendung von zwei Firewalls ist die empfohlene Vorgehensweise, da Sie ein striktes Routing von einem Netzwerk-Edge zum anderen gewährleistet und ihre interne Bereitstellung hinter zwei Firewall-Ebenen schützt.</span><span class="sxs-lookup"><span data-stu-id="0640f-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="0640f-148">Director</span><span class="sxs-lookup"><span data-stu-id="0640f-148">Director</span></span>

<span data-ttu-id="0640f-149">Ein Director ist eine separate, optionale Serverrolle in lync Server 2013, die keine Benutzerkonten aufweist, oder Anwesenheits-oder Konferenzdienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0640f-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="0640f-150">Er dient als interner nächster Hop-Server, an den ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="0640f-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="0640f-151">Der Director authentifiziert eingehende Anforderungen und leitet Sie an den privaten Pool oder Server des Benutzers weiter.</span><span class="sxs-lookup"><span data-stu-id="0640f-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="0640f-152">Durch Vorauthentifizierung beim Director können Sie Anforderungen von Benutzerkonten ablegen, die der Bereitstellung unbekannt sind.</span><span class="sxs-lookup"><span data-stu-id="0640f-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="0640f-153">Ein Director hilft bei der Isolierung von Standard Edition-Servern und Front-End-Servern in Enterprise Edition-Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen (DOS).</span><span class="sxs-lookup"><span data-stu-id="0640f-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="0640f-154">Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externem Datenverkehr überflutet wird, endet der Datenverkehr beim Director.</span><span class="sxs-lookup"><span data-stu-id="0640f-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="0640f-155">Ausführliche Informationen zur Verwendung von Directors finden Sie unter [Scenarios for the Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="0640f-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0640f-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0640f-156">See Also</span></span>


[<span data-ttu-id="0640f-157">Anforderungen an das Hardware Gerät zum Lastenausgleich für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0640f-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

