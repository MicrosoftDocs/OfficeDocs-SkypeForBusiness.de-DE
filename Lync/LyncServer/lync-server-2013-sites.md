---
title: Lync Server 2013-Standorte
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="f1347-102">Lync Server-Standorte für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1347-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1347-103">_**Letztes Änderungsdatum des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f1347-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f1347-104">In lync Server definieren Sie *Websites* in Ihrem Netzwerk, die lync Server-Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1347-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="f1347-105">Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f1347-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="f1347-106">Beachten Sie, dass lync Server-Websites ein separates Konzept von Active Directory-Domänendienst Websites und Microsoft Exchange Server-Websites sind.</span><span class="sxs-lookup"><span data-stu-id="f1347-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="f1347-107">Ihre lync Server-Websites müssen Ihren Active Directory-Standorten nicht entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f1347-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="f1347-108">Websitetypen</span><span class="sxs-lookup"><span data-stu-id="f1347-108">Site Types</span></span>

<span data-ttu-id="f1347-109">Jede Website ist entweder ein *zentraler Standort*, der mindestens einen Front-End-Pool oder einen Standard Edition-Server oder eine *Verzweigungs Website*enthält.</span><span class="sxs-lookup"><span data-stu-id="f1347-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="f1347-110">Jede Verzweigungs Website ist genau einem zentralen Standort zugeordnet, und die Benutzer an der Zweigstelle erhalten den größten Teil ihrer lync-Server Funktionen von den Servern auf dem zugehörigen zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="f1347-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="f1347-111">Jede Verzweigungs Website enthält eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="f1347-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="f1347-112">Eine *Survivable Branch Appliance (SBA)*, die ein branchenüblicher Blade-Server mit einer lync Server-Registrierungsstelle und einem auf Windows Server ausgeführten Vermittlungsserver ist.</span><span class="sxs-lookup"><span data-stu-id="f1347-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="f1347-113">Die Survivable Branch-Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="f1347-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="f1347-114">Die Survivable Branch-Appliance ist für Zweigstellen mit 25 und 1000-Benutzern konzipiert.</span><span class="sxs-lookup"><span data-stu-id="f1347-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="f1347-115">Ein *Survivable Branch Server (SBS)*, ein Server, auf dem Windows Server ausgeführt wird, der die angegebenen Hardwareanforderungen erfüllt und auf dem die lync Server Registrar-und Mediation Server-Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f1347-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="f1347-116">Sie muss mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefondienstanbieter angeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f1347-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="f1347-117">Der Survivor-Branch-Server ist für Zweigstellen mit zwischen 1000 und 5000-Benutzern konzipiert.</span><span class="sxs-lookup"><span data-stu-id="f1347-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="f1347-118">Ein PSTN-Gateway und optional ein Vermittlungs *Server*.</span><span class="sxs-lookup"><span data-stu-id="f1347-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="f1347-119">Details zu dieser und anderen Serverrollen finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f1347-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="f1347-120">Eine Zweigstelle mit einer stabilen WAN-Verbindung (Wide Area Network) zu einem zentralen Standort kann die dritte Option (ein PSTN-Gateway) und optional einen Vermittlungs Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1347-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="f1347-121">Zweigstellenstandorte mit unelastischen Links sollten eine Survivable Branch-Appliance oder einen Survivable Branch-Server verwenden, der in Zeiten von Wide-Area-Netzwerkfehlern Ausfallsicherheit bietet.</span><span class="sxs-lookup"><span data-stu-id="f1347-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="f1347-122">Beispielsweise können Benutzer in einer Website mit einer überlebensfähigen Branch-Appliance oder einem Überlebenden Branch-Server weiterhin Enterprise-VoIP-Anrufe tätigen und empfangen, wenn das WAN, das die Verzweigungs Website mit dem zentralen Standort verbindet, ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="f1347-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="f1347-123">Ausführliche Informationen zur Survivable Branch-Appliance, dem Survivable Branch-Server und zur Widerstandsfähigkeit finden Sie unter [Planen der Enterprise-VoIP-Resilienz in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f1347-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="f1347-124">Website Topologien</span><span class="sxs-lookup"><span data-stu-id="f1347-124">Site Topologies</span></span>

<span data-ttu-id="f1347-125">Ihre Bereitstellung muss mindestens einen zentralen Standort umfassen und NULL für viele Verzweigungs Websites enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1347-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="f1347-126">Jede Verzweigungs Website ist mit einem zentralen Standort verbunden.</span><span class="sxs-lookup"><span data-stu-id="f1347-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="f1347-127">Der zentrale Standort stellt die lync-Server Dienste für die Zweigstelle bereit, die nicht lokal auf der Zweigstelle gehostet werden, beispielsweise Anwesenheitsinformationen und Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="f1347-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="f1347-128">Wenn Sie über mehrere Websites verfügen, können Sie die Front-End-Pools an verschiedenen Standorten kombinieren, um Disaster Recovery-Fähigkeiten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f1347-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="f1347-129">Ausführliche Informationen finden Sie unter [Support für höhere Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="f1347-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1347-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1347-130">See Also</span></span>


[<span data-ttu-id="f1347-131">Serverrollen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1347-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="f1347-132">Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1347-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="f1347-133">Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1347-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

