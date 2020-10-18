---
title: 'Lync Server 2013: Bereitstellungsrichtlinien für Vermittlungsserver'
description: 'Lync Server 2013: Bereitstellungsrichtlinien für Vermittlungsserver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8198431b24714666c9411029aecd12835014fef4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575771"
---
# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="20fbb-103">Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20fbb-103">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20fbb-104">_**Letztes Änderungsstand des Themas:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="20fbb-104">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="20fbb-105">In diesem Thema werden Planungsrichtlinien für Vermittlungsserver Bereitstellung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="20fbb-105">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="20fbb-106">Nachdem Sie diese Richtlinien überprüft haben, empfehlen wir Ihnen, das Planungs Tool zum Erstellen und anzeigen möglicher alternativer Topologien zu verwenden, die als Modelle für die endgültige, von Ihnen bereitzustellende Topologie fungieren können.</span><span class="sxs-lookup"><span data-stu-id="20fbb-106">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="20fbb-107">Verbundenes oder eigenständiges Vermittlungsserver?</span><span class="sxs-lookup"><span data-stu-id="20fbb-107">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="20fbb-108">Der Vermittlungsserver ist standardmäßig mit anderen Servern auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten verbunden.</span><span class="sxs-lookup"><span data-stu-id="20fbb-108">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="20fbb-109">Die Anzahl der PSTN-Anrufe (Public Switched Telephone Network), die verarbeitet werden können, und die Anzahl der im Pool erforderlichen Computer hängen von folgenden Anforderungen ab:</span><span class="sxs-lookup"><span data-stu-id="20fbb-109">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="20fbb-110">Die Anzahl der Gateway-Peers, die vom Vermittlungsserver Pool gesteuert werden</span><span class="sxs-lookup"><span data-stu-id="20fbb-110">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="20fbb-111">Die großen Datenverkehrs Zeiträume über diese Gateways</span><span class="sxs-lookup"><span data-stu-id="20fbb-111">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="20fbb-112">Der Prozentsatz der Anrufe, bei denen es sich um Anrufe handelt, deren Medien die Vermittlungsserver umgehen</span><span class="sxs-lookup"><span data-stu-id="20fbb-112">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="20fbb-113">Achten Sie bei der Planung darauf, die Anforderungen an die Medienverarbeitung für PSTN-Anrufe und A/V-Konferenzen, die nicht für die medienumgehung konfiguriert sind, sowie die Verarbeitung zur Behandlung von Signalisierungs Interaktionen für die Anzahl der Anrufe, die unterstützt werden müssen, zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="20fbb-113">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="20fbb-114">Wenn nicht genügend CPU vorhanden ist, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. und PSTN-Gateways, IP-Nebenstellenanlagen und SBCS müssen in Untergruppen unterteilt werden, die von den verbundenen Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="20fbb-114">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="20fbb-115">Wenn Sie PSTN-Gateways, IP-Nebenstellenanlagen oder Session Border Controller (SBCS) bereitgestellt haben, die nicht die richtigen Funktionen für die Interaktion mit einem Pool von Vermittlungsservern unterstützen, einschließlich der folgenden, müssen Sie einem eigenständigen Pool zugeordnet sein, der aus einem einzigen Vermittlungsserver besteht:</span><span class="sxs-lookup"><span data-stu-id="20fbb-115">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="20fbb-116">Ausführen von Netzwerkschicht Domain Name System (DNS) Lastenausgleich über Vermittlungsserver in einem Pool (oder anderweitige gleichmäßige Weiterleitung des Datenverkehrs an alle Vermittlungsserver in einem Pool)</span><span class="sxs-lookup"><span data-stu-id="20fbb-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="20fbb-117">Akzeptieren von Datenverkehr von jedem Vermittlungsserver in einem Pool</span><span class="sxs-lookup"><span data-stu-id="20fbb-117">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="20fbb-118">Mit dem Microsoft lync Server 2013 Planungs Tool können Sie auswerten, ob abstimmen die Vermittlungsserver mit Ihrem Front-End-Pool die Last verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="20fbb-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="20fbb-119">Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="20fbb-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="20fbb-120">Überlegungen zum zentralen Standort und Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="20fbb-120">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="20fbb-p105">Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Bei Bereitstellung von SIP-Trunks müssen Sie jedoch einen Vermittlungsserver an dem Standort bereitstellen, der als Endpunkt für die einzelnen Trunks dient. Bei Einsatz eines Vermittlungsservers am zentralen Standort zum Weiterleiten von Anrufen für eine IP-Nebenstellenanlage oder ein PSTN-Gateway an einem Zweigstellenstandort ist keine Medienumgehung erforderlich. Wenn Sie die Medienumgehung jedoch aktivieren können, wird die Latenz für den Medienpfad reduziert und somit eine bessere Medienqualität erreicht, da der Medienpfad nicht länger dem Signalpfad folgen muss. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.</span><span class="sxs-lookup"><span data-stu-id="20fbb-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20fbb-126">Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren.</span><span class="sxs-lookup"><span data-stu-id="20fbb-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="20fbb-127">Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="20fbb-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="20fbb-128">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – lync Server unter aufgeführt sind <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A> .</span><span class="sxs-lookup"><span data-stu-id="20fbb-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="20fbb-129">Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="20fbb-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="20fbb-130">(Die Annahme mit Ausfallsicherheit für Zweigstellenstandorte besteht darin, dass Anwesenheit und Konferenzen am Standort nicht belastbar sind.) Anleitungen zur Planung von Zweigstellenstandorten für VoIP finden Sie unter [Planning for Branch-Site Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="20fbb-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="20fbb-131">Wenn die IP-Nebenstellenanlage für Interaktionen mit einer IP-Nebenstellenanlage nicht ordnungsgemäß unterstützt frühe Medien Interaktionen mit mehreren frühen Dialogen und RFC 3960-Interaktionen, kann es sein, Clipping der ersten Worte der Begrüßung für eingehende Anrufe von der IP-Nebenstellenanlage zu lync-Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="20fbb-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="20fbb-132">Dieses Verhalten kann gravierender sein, wenn eine Vermittlungsserver an einem zentralen Standort Routing Anrufe für eine IP-Nebenstellenanlage ist, bei der die Route an einem Zweigstellenstandort beendet wird, da mehr Zeit erforderlich ist, um die Signalisierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="20fbb-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="20fbb-133">Wenn dieses Verhalten auftritt, ist die Bereitstellungeines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit, das Clipping der ersten Wörter zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="20fbb-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="20fbb-134">Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="20fbb-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20fbb-135">Um die Medien Leistung eigenständiger Vermittlungsserver zu verbessern, sollten Sie die Receive-Side Scaling (RSS) auf den Netzwerkadaptern auf diesen Servern aktivieren.</span><span class="sxs-lookup"><span data-stu-id="20fbb-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="20fbb-136">Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="20fbb-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="20fbb-137">Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="20fbb-137">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="20fbb-138">Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="20fbb-138">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

