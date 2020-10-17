---
title: Lync Server 2013 Websites
description: Lync Server 2013 Websites.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59739c5a81fca1f1f3ab5c1b83a23f0be0a5ee2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558961"
---
# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="44058-103">Lync Server Websites für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44058-103">Lync Server sites for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44058-104">_**Letztes Änderungsstand des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="44058-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="44058-105">In lync Server definieren Sie *Websites* in Ihrem Netzwerk, die lync Server Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="44058-105">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="44058-106">Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="44058-106">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="44058-107">Beachten Sie, dass lync Server Websites ein separates Konzept von Active Directory-Domänendienste Websites und Exchange Server Websites sind.</span><span class="sxs-lookup"><span data-stu-id="44058-107">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="44058-108">Ihre lync Server Websites müssen nicht Ihren Active Directory Websites entsprechen.</span><span class="sxs-lookup"><span data-stu-id="44058-108">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="44058-109">Standorttypen</span><span class="sxs-lookup"><span data-stu-id="44058-109">Site Types</span></span>

<span data-ttu-id="44058-110">Jeder Standort ist entweder ein *zentraler Standort*, auf dem mindestens eine Front-End-Pool oder ein Standard Edition-Server oder ein Zweigstellen *Standort*vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="44058-110">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="44058-111">Jeder Zweigstellenstandort ist genau einem zentralen Standort zugeordnet, und die Benutzer am Zweigstellenstandort erhalten den Großteil ihrer lync Server Funktionalität von den Servern am zugeordneten zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="44058-111">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="44058-112">Jeder Zweigstellenstandort umfasst eine der folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="44058-112">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="44058-113">Ein *Survivable Branch Appliance (SBA)*, bei dem es sich um einen standardmäßigen Blade-Server mit einer lync Server Registrierungsstelle und einem Vermittlungsserver, der unter Windows Server läuft, handelt.</span><span class="sxs-lookup"><span data-stu-id="44058-113">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="44058-114">Das Survivable Branch Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="44058-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="44058-115">Das Survivable Branch Appliance wurde für Zweigstellen mit 25 bis 1000 Benutzern entwickelt.</span><span class="sxs-lookup"><span data-stu-id="44058-115">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="44058-116">Ein *Survivable Branch Server (SBS)*, bei dem es sich um einen Server mit Windows Server handelt, der die angegebenen Hardwareanforderungen erfüllt und auf dem lync Server Registrierungsstelle und Vermittlungsserver Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="44058-116">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="44058-117">Der Server muss entweder über ein PSTN-Gateway oder einen SIP-Trunk mit einem Telefoniedienstanbieter verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="44058-117">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="44058-118">Das Survivable Branch Server wurde für Zweigstellen mit 1000-und 5000-Benutzern entwickelt.</span><span class="sxs-lookup"><span data-stu-id="44058-118">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="44058-119">Ein PSTN-Gateway und optional ein *Vermittlungsserver*.</span><span class="sxs-lookup"><span data-stu-id="44058-119">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="44058-120">Ausführliche Informationen zu dieser und anderen Serverrollen finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="44058-120">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="44058-121">Ein Zweigstellenstandort mit einer ausfallsicheren WAN-Verbindung (Wide Area Network) zu einem zentralen Standort kann die dritte Option nutzen – ein PSTN-Gateway und optional einen Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="44058-121">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="44058-122">Zweigstellenstandorte mit eher unelastischen Links sollten eine Survivable Branch Appliance oder Survivable Branch Server verwenden, die in Zeiten von weit reichenden Netzwerkfehlern Ausfallsicherheit bieten.</span><span class="sxs-lookup"><span data-stu-id="44058-122">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="44058-123">Beispielsweise können Benutzer bei einer Website mit einer Survivable Branch Appliance oder bereitgestellten Survivable Branch Server weiterhin Enterprise-VoIP-Anrufe tätigen und empfangen, wenn das WAN, das den Zweigstellenstandort mit dem zentralen Standort verbindet, nicht aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="44058-123">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="44058-124">Ausführliche Informationen zu Survivable Branch Appliance, Survivable Branch Server und Ausfallsicherheit finden Sie in der Planungsdokumentation unter [Planning for Enterprise Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) .</span><span class="sxs-lookup"><span data-stu-id="44058-124">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="44058-125">Standorttopologien</span><span class="sxs-lookup"><span data-stu-id="44058-125">Site Topologies</span></span>

<span data-ttu-id="44058-126">Ihre Bereitstellung muss mindestens einen zentralen Standort enthalten und kann einen oder mehrere Zweigstellenstandorte umfassen.</span><span class="sxs-lookup"><span data-stu-id="44058-126">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="44058-127">Jeder Zweigstellenstandort ist mit einem zentralen Standort verbunden.</span><span class="sxs-lookup"><span data-stu-id="44058-127">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="44058-128">Der zentrale Standort stellt die lync Server Dienste für den Zweigstellenstandort bereit, die nicht lokal am Zweigstellenstandort gehostet werden, beispielsweise Anwesenheitsinformationen und Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="44058-128">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="44058-129">Wenn Sie über mehrere Standorte verfügen, können Sie die Front-End-Pools an unterschiedlichen Standorten zu Paaren verknüpfen, um die Notfallwiederherstellung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="44058-129">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="44058-130">Ausführliche Informationen finden Sie unter [Support für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="44058-130">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44058-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44058-131">See Also</span></span>


[<span data-ttu-id="44058-132">Server Rollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44058-132">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="44058-133">Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44058-133">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="44058-134">Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44058-134">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

