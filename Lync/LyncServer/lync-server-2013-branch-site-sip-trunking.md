---
title: 'Lync Server 2013: SIP-Trunking für Zweigstellenstandorte'
description: 'Lync Server 2013: SIP-Trunking für Zweigstellenstandorte.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33e408a462c21ffa6df6e6a2aee50d7b87dca1f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569321"
---
# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="9c322-103">SIP-Trunking für Zweigstellenstandorte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c322-103">Branch site SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c322-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9c322-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9c322-105">In einigen Fällen müssen Sie möglicherweise verteiltes SIP-Trunking an ausgewählten Zweigstellenstandorten implementieren.</span><span class="sxs-lookup"><span data-stu-id="9c322-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="9c322-106">Um zu ermitteln, ob ein SIP-Trunk für einen Zweigstellenstandort erforderlich ist, lesen Sie die Informationen unter [How do I implement SIP Trunking in lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="9c322-106">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="9c322-107">Ausführliche Informationen zu den unterstützten Topologie-Optionen für die Bereitstellung von SIP-Trunks an Zweigstellenstandorten finden Sie unter [Branch-Site Resilienz Solutions in lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="9c322-107">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="9c322-108">Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung</span><span class="sxs-lookup"><span data-stu-id="9c322-108">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="9c322-109">Wenn Sie sich für die Bereitstellungeines Zweigstellenstandort-SIP-Trunks entscheiden, müssen Sie eine standortspezifische Kostenanalyse durchführen.</span><span class="sxs-lookup"><span data-stu-id="9c322-109">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="9c322-110">Beispielsweise sollte ein Unternehmen mit einem zentralen Standort in Redmond, Washington und einem Zweigstellenstandort in New York eine Analyse durchführen, um zu bestimmen, ob ein SIP-Trunk vom Standort New York an einen lokalen Dienstanbieter implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c322-110">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="9c322-111">Um zu ermitteln, ob ein verteilter SIP-Trunk in New York kostengünstig ist, ermitteln Sie, welche DID-Nummern (Direct Inward Dialing) den SIP-Trunk verwenden sollen, und analysieren Sie die Anzahl der Anrufe, die New York in andere Bereiche als Redmond (425) vornimmt.</span><span class="sxs-lookup"><span data-stu-id="9c322-111">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="9c322-112">Sie können die Beendigung für den Zweigstellenstandort am zentralen Standort haben.</span><span class="sxs-lookup"><span data-stu-id="9c322-112">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="9c322-113">Beispielsweise kann der zentrale Standort in Redmond die Nummern für den Zweigstellenstandort in New York hosten.</span><span class="sxs-lookup"><span data-stu-id="9c322-113">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="9c322-114">Wenn die Kosten für die Implementierung eines verteilten SIP-Trunks niedriger sind als die Kosten für diese Anrufe, sollten Sie einen SIP-Trunk am Zweigstellenstandort in New York implementieren.</span><span class="sxs-lookup"><span data-stu-id="9c322-114">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="9c322-115">Weitere SIP-Trunkanforderungen für Zweigniederlassungen</span><span class="sxs-lookup"><span data-stu-id="9c322-115">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="9c322-116">Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="9c322-116">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="9c322-117">Wenn Sie einen SIP-Trunk für eine Zweigstelle bereitstellen, müssen Sie auch die Ausfallsicherheit und die Bandbreitenanforderungen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="9c322-117">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="9c322-118">Wenn die Verbindung zwischen dem Zweigstellenstandort und dem zentralen Standort widerstandsfähig ist und über ausreichende Bandbreite verfügt, können Sie einen SIP-Trunk oder ein Gateway bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9c322-118">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="9c322-119">Sie müssen keine Survivable Branch Appliance an der Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9c322-119">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="9c322-120">Wenn die Verknüpfung zwischen dem Zweigstellenstandort und dem zentralen Standort nicht belastbar ist, stellen Sie eine Survivable Branch Appliance bereit, oder stellen Sie eine Survivable Branch Server mit einem Gateway oder einem SIP-Trunk am Zweigstellenstandort bereit.</span><span class="sxs-lookup"><span data-stu-id="9c322-120">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

