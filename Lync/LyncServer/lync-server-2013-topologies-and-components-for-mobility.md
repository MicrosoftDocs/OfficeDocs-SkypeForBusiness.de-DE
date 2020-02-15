---
title: 'Lync Server 2013: Topologien und Komponenten für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac03d6b98b0b209a50f08e660fe6665b975d2ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="86372-102">Topologien und Komponenten für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86372-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86372-103">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="86372-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="86372-104">Zur Unterstützung von mobilen lync-Anwendungen auf mobilen Geräten bietet lync Server 2013 drei Dienste an: lync Server 2013 MCX-Mobilitätsdienst, lync Server 2013 AutoErmittlungsdienst und lync Server 2013 Push-Benachrichtigungsdienst.</span><span class="sxs-lookup"><span data-stu-id="86372-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="86372-105">Die kumulativen Updates für lync Server 2013: Februar 2013 fügt einen kostenlosen, aber erweiterten Dienst für lync 2013 Mobile Clients hinzu – Mobilitätsunterstützung durch die Verwendung der Unified Communications-WebAPI oder UCWA.</span><span class="sxs-lookup"><span data-stu-id="86372-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="86372-106">In diesem Abschnitt werden diese Komponenten kurz beschrieben und die lync Server 2013 Topologien identifiziert, die die Mobilität unterstützen.</span><span class="sxs-lookup"><span data-stu-id="86372-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86372-107">Mobilitätsdienste sind auch in hybriden Bereitstellungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="86372-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="86372-108">Sie müssen keine Dienste zur Unterstützung der Mobilität bereitstellen, falls die Benutzer online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="86372-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="86372-109">Sie müssen eine Einstellung für den AutoErmittlungsdienst definieren, damit Mobile Benutzer ihre Online Identität finden können.</span><span class="sxs-lookup"><span data-stu-id="86372-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86372-110">Wenn Sie eine externe Benutzerkonnektivität planen (beispielsweise Partnerverbund, externer Benutzer Zugriff oder Mobilitätsfunktionen), müssen Sie Edgeserver mit Standard Edition-Server und dem Front-End-Server oder Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="86372-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="86372-111">Die Standard Edition-Server und die Front-End-Server oder Front-End-Pool verfügen nicht über die erforderlichen Komponenten, um externen Benutzern den Zugriff auf Ihre interne Bereitstellung zu ermöglichen, oder um die interne Bereitstellung für die Kommunikation mit Ihren externen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="86372-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="86372-112">Für alle Szenarien, die externe Benutzer einschließen, die mit internen Benutzern zusammenarbeiten oder kommunizieren, einschließlich Mobilität, müssen Sie mindestens eine Edgeserver und einen Reverseproxy bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="86372-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="86372-113"><EM>Push Notification</EM> verwendet einen Typ von Verbund für die lync Online Dienste, die das Push Notification Clearing House (PNCH) hosten.</span><span class="sxs-lookup"><span data-stu-id="86372-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="86372-114">Push Notification bezieht sich auf die Sound Warnungen, Warnungen auf dem Bildschirm (Text) und Abzeichen, die von Anwendungen auf das Apple iPhone, iPad und Windows Phone geschoben werden, wenn das Mobile Gerät inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="86372-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="86372-115">PNCH empfängt Push-Benachrichtigungen von lync Server.</span><span class="sxs-lookup"><span data-stu-id="86372-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="86372-116">Wenn PNCH eine Benachrichtigung über eine Nachricht erhält, leitet PNCH eine Benachrichtigung an mobile Clients über den Apple Push Notification Services oder lync Server 2013 Push Notification Service weiter, basierend auf dem mobilen Client, für den die Nachricht bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="86372-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="86372-117">PNCH ist ein erforderlicher Dienst für diese mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="86372-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="86372-118">Um eine Föderation mit lync online zu erhalten, verwendet PNCH Edgeserver und Zertifikate, um Vertraulichkeit und Authentifizierung, Richtlinien und ordnungsgemäß konfigurierte DNS-Einträge (Domain Name System) sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="86372-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="86372-119">Nokia Symbian und Android-basierte lync Mobile-Clients verwenden nicht PNCH.</span><span class="sxs-lookup"><span data-stu-id="86372-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="86372-120">Ausführliche Informationen zum Planen und Bereitstellen von Edgeserver finden Sie unter <A href="lync-server-2013-planning-for-external-user-access.md">Planen des Zugriffs durch externe Benutzer in lync Server 2013</A> und <A href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="86372-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="86372-121">Die lync 2013 Mobile Clients für Apple-Geräte, die mit den kumulativen Updates für lync Server 2013 eingeführt wurden: Februar 2013 nicht mehr die Push-Benachrichtigung oder das Push Notification Clearing House (PNCH) verwenden.</span><span class="sxs-lookup"><span data-stu-id="86372-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="86372-122">Lync 2013 Mobile Clients auf Windows Phone weiterhin Push-Benachrichtigung und die (PNCH) verwenden.</span><span class="sxs-lookup"><span data-stu-id="86372-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="86372-123">Mobilitätskomponenten</span><span class="sxs-lookup"><span data-stu-id="86372-123">Mobility Components</span></span>

<span data-ttu-id="86372-124">Die folgenden Dienste unterstützen Mobilität:</span><span class="sxs-lookup"><span data-stu-id="86372-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="86372-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   bietet Dienste für die Echtzeitkommunikation mit mobilen und Webclients in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86372-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="86372-126">Wenn Sie die kumulativen Updates für lync Server 2013 bereitstellen: 2013 Februar bis zum Front-End-Server und Director erstellt die Installation ein virtuelles Verzeichnis in den internen und externen Webdiensten (Ucwa).</span><span class="sxs-lookup"><span data-stu-id="86372-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="86372-127">Eine Webkomponente, die Teil des virtuellen Ucwa-Verzeichnisses ist, akzeptiert Anrufe von Ucwa-aktivierten Clients.</span><span class="sxs-lookup"><span data-stu-id="86372-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="86372-128">Die Client-apps kommunizieren über eine Rest-Schnittstelle für Anwesenheit, Kontakte, Instant Messaging, VoIP, Videokonferenzen und Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="86372-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="86372-129">UCWA verwendet einen P-get-basierten Kanal, um Ereignisse wie einen eingehenden Anruf, eine eingehende Sofortnachricht oder eine Nachricht an die Client-App zu senden.</span><span class="sxs-lookup"><span data-stu-id="86372-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86372-130"><EM>Rest</EM> -oder Darstellungs Zustands Übertragung ist ein Softwarearchitekturstil für verteilte Systeme, der in vielen Formen weit verbreitet ist und für die Anforderungen von Webdiensten allgemein geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="86372-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="86372-131">**Lync Server 2013 Mobilitätsdienst (MCX)**   dieser Dienst unterstützt lync-Funktionen wie Instant Messaging (Sofortnachrichten), Anwesenheitsinformationen und Kontakte auf mobilen Geräten.</span><span class="sxs-lookup"><span data-stu-id="86372-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="86372-132">Der Mobilitätsdienst wird auf jedem Front-End-Server in jedem Pool installiert, der lync-Funktionen auf mobilen Geräten unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="86372-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="86372-133">Wenn Sie lync Server 2013 installieren, wird ein neues virtuelles Verzeichnis (MCX) sowohl unter der internen Website als auch auf der externen Website auf Ihren Front-End-Servern erstellt.</span><span class="sxs-lookup"><span data-stu-id="86372-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="86372-134">Lync Server 2013 mit den kumulativen Updates für lync Server 2013: Februar 2013 unterstützt sowohl den Mobilitätsdienst, der im kumulativen Update für lync Server 2010 eingeführt wurde: November 2011, allgemein bekannt als MCX, und die UCWA-Webkomponente.</span><span class="sxs-lookup"><span data-stu-id="86372-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="86372-135">Die Kombination dieser beiden Mobilitätsdienste bietet Interoperabilität und die Verwendung von Benutzern mit lync 2010 Mobile und lync 2013 mobilen Clients auf lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86372-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="86372-136">**Lync Server 2013 AutoErmittlungsdienst**   dieser Dienst identifiziert den Speicherort des Benutzers und ermöglicht es mobilen Geräten und anderen lync-Clients, Ressourcen wie die internen und externen URLs für lync Server 2013 Webdienste und die URL für die MCX oder UCWA unabhängig vom Netzwerkstandort zu finden.</span><span class="sxs-lookup"><span data-stu-id="86372-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="86372-137">Bei der automatischen Ermittlung werden hart codierte Hostnamen ("lyncdiscoverinternal" für Benutzer innerhalb des Netzwerks; lyncdiscover für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="86372-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="86372-138">Es unterstützt Clientverbindungen, die entweder http oder HTTPS verwenden.</span><span class="sxs-lookup"><span data-stu-id="86372-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="86372-139">Der AutoErmittlungsdienst wird auf jedem Front-End-Server und jedem Director in jedem Pool installiert, der lync-Funktionen auf mobilen Geräten unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="86372-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="86372-140">Wenn Sie den AutoErmittlungsdienst installieren, wird ein neues virtuelles Verzeichnis (AutoErmittlung) sowohl unter der internen Website als auch auf der externen Website sowohl auf Front-End-Servern als auch in Directors erstellt.</span><span class="sxs-lookup"><span data-stu-id="86372-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86372-141">Der AutoErmittlungsdienst wird hier aufgelistet, da er bei der Bereitstellung von mobilen Clientdiensten eine wichtige Komponente bleibt.</span><span class="sxs-lookup"><span data-stu-id="86372-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="86372-142">Die Rolle der AutoErmittlung in lync Server 2013 wurde erweitert, um Dienste für alle Clients bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="86372-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="86372-143">Ausführliche Informationen zur Planung für den AutoErmittlungsdienst finden Sie unter <A href="lync-server-2013-planning-for-autodiscover.md">Planning for AutoErmittlung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="86372-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="86372-144">**Push-Benachrichtigungsdienst**   dieser Dienst ist ein Cloud-basierter Dienst, der sich im Rechenzentrum lync Online befindet.</span><span class="sxs-lookup"><span data-stu-id="86372-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="86372-145">Wenn die Mobile lync-Anwendung auf einem unterstützten Apple IOS-Gerät oder Windows Phone inaktiv ist, kann Sie nicht auf neue Ereignisse reagieren, beispielsweise auf eine neue sofortnachrichteneinladung, eine verpasste Sofortnachricht, einen verpassten Anruf oder eine Voicemail, da diese Geräte keine Unterstützung für Mobile Anwendungen, die im Hintergrund ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="86372-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="86372-146">In diesen Fällen wird eine Benachrichtigung des neuen Ereignisses, das als *Push-Benachrichtigung*bezeichnet wird, an das Mobile Gerät gesendet.</span><span class="sxs-lookup"><span data-stu-id="86372-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="86372-147">Der Mobilitätsdienst sendet die Benachrichtigung an den cloudbasierten Push-Benachrichtigungsdienst, der die Benachrichtigung dann entweder an den Apple Push Notification Service (APNS) (für unterstützte Apple IOS-Geräte) oder an den Microsoft Push Notification Service sendet (MPNS ) (für Windows Phone), der Sie dann an das Mobile Gerät sendet.</span><span class="sxs-lookup"><span data-stu-id="86372-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="86372-148">Der Benutzer kann dann auf dem mobilen Gerät auf die Benachrichtigung Antworten, um die Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="86372-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="86372-149">Die lync 2010 Mobile auf Apple-und Windows Phone-Geräten verwenden Push-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="86372-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="86372-150">Der lync 2013 Mobile Client für Apple-Geräte, die mit den kumulativen Updates für lync Server 2013 eingeführt wurden: Februar 2013 verwendet keine Push-Benachrichtigung mehr oder das Push Notification Clearing House (PNCH).</span><span class="sxs-lookup"><span data-stu-id="86372-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="86372-151">Das folgende Diagramm zeigt, wie der Push-Benachrichtigungsdienst in eine lync Server 2013 Topologie passt, in der UCWA und lync 2013 Mobile Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86372-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="86372-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="86372-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="86372-153">Eingeführt im kumulativen Update für lync Server 2010: November 2011 stellt der MCX-Dienst Dienste für lync 2010 Mobile-Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="86372-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="86372-154">Das folgende Diagramm veranschaulicht den Push-Benachrichtigungsdienst, der für eine Topologie mithilfe von MCX und lync 2010 Mobile Clients gilt.</span><span class="sxs-lookup"><span data-stu-id="86372-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="86372-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="86372-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="86372-156">Unterstützte Topologien</span><span class="sxs-lookup"><span data-stu-id="86372-156">Supported Topologies</span></span>

<span data-ttu-id="86372-157">Bei der Anwendung der kumulativen Updates für lync Server 2013: Februar 2013 werden die UCWA-Webkomponenten hinzugefügt, um die Mobilität für lync 2013 Mobile Clientfeatures in den folgenden Topologien zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="86372-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="86372-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86372-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="86372-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86372-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="86372-160">Die Edgeserver kann eine lync Server 2010 Edgeserver sein.</span><span class="sxs-lookup"><span data-stu-id="86372-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="86372-161">Eine lync Server 2013-Bereitstellung ohne kumulative Updates für lync Server 2013: Februar 2013 verwendet den MCX-Mobilitätsdienst und kann nur für lync 2010 Mobile Dienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="86372-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86372-162">Der Mobilitätsdienst wird auf Front-End-Servern unterstützt, die mit der Vermittlungsserver Rolle mit zwei Netzwerkschnittstellen verbunden sind, Sie müssen jedoch geeignete Schritte ausführen, um die Schnittstellen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86372-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="86372-163">Sie müssen die IP-Adressen der spezifischen Schnittstelle zuweisen, die als Vermittlungsserver kommunizieren wird, und die Netzwerkschnittstellen-IP, die als Front-End-Server kommunizieren soll.</span><span class="sxs-lookup"><span data-stu-id="86372-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="86372-164">Dies können Sie im Topologie-Generator tun, indem Sie die richtige IP-Adresse für jeden Dienst auswählen, anstatt die standardmäßigen <STRONG>use all configured IP Addresss</STRONG>zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="86372-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86372-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86372-165">See Also</span></span>


[<span data-ttu-id="86372-166">Planen des Zugriffs durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86372-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="86372-167">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86372-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="86372-168">Planen der AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86372-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

