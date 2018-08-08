---
title: Branch Site SIP-Trunking in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Informationen Sie zu SIP-Trunking an Zweigniederlassungen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: e14d6ba3101c1981b719ea0f030d2e92fbd4ab7b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966271"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="ef873-103">Branch Site SIP-Trunking in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ef873-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="ef873-104">Informationen Sie zu SIP-Trunking an Zweigniederlassungen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="ef873-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ef873-105">In einigen Fällen müssen Sie möglicherweise verteilten SIP-Trunking am ausgewählten Zweigniederlassungen implementieren.</span><span class="sxs-lookup"><span data-stu-id="ef873-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="ef873-106">Um zu bestimmen, ob ein SIP Trunk erforderlich ist, für eine Zweigstelle und ausführliche Informationen zu den unterstützten Topologieoptionen für die Bereitstellung von SIP-Trunks in Zweigniederlassungen, finden Sie unter [SIP-Trunking in Skype für Business Server](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="ef873-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="ef873-107">Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung</span><span class="sxs-lookup"><span data-stu-id="ef873-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="ef873-108">Wenn Sie einen Branch Site SIP-Trunk bereitstellen möchten, müssen Sie eine standortspezifische Kostenanalyse ausführen.</span><span class="sxs-lookup"><span data-stu-id="ef873-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="ef873-109">Beispielsweise sollte ein Unternehmen, das einen zentralen Standort in Redmond, Washington, und eine Zweigniederlassung in New York hat eine Analyse, um festzustellen, ob einen SIP-Trunk von New York-Website mit einem lokalen Dienstanbieter implementieren bewirken.</span><span class="sxs-lookup"><span data-stu-id="ef873-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="ef873-110">Zu bestimmen, ob ein verteilter SIP-Trunk in New York kostengünstigen ist, bestimmt, die direkte Nummer (Inward DIALING) Zahlen werden verwenden Sie den SIP-Trunk und analysieren die Anzahl von Aufrufen von New York zu Bereichen als "Redmond" (425) durch.</span><span class="sxs-lookup"><span data-stu-id="ef873-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="ef873-111">Sie können DID-Beendigung für den Zweigstellenstandort am zentralen Standort verfügen.</span><span class="sxs-lookup"><span data-stu-id="ef873-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="ef873-112">Beispielsweise kann am zentrale Standort "Redmond" DID-Nummern für die Zweigniederlassung New York hosten.</span><span class="sxs-lookup"><span data-stu-id="ef873-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="ef873-113">Wenn die Kosten der Implementierung eines verteilten SIP-Trunks kleiner als die Kosten für diese Aufrufe ist, sollten Sie einen SIP-Trunk am Zweigstellenstandort New York implementieren.</span><span class="sxs-lookup"><span data-stu-id="ef873-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="ef873-114">Weitere SIP-Trunkanforderungen für Zweigniederlassungen</span><span class="sxs-lookup"><span data-stu-id="ef873-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="ef873-115">Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="ef873-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="ef873-116">Wenn Sie einen Branch Site SIP-Trunk bereitstellen, müssen Sie auch Ihre Anforderungen höhere Zuverlässigkeit und Bandbreite bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ef873-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="ef873-117">Wenn die Verknüpfung zwischen der Zweigstelle und dem zentralen Standort ausfallsichere ist und verfügt über genügend Bandbreite, können Sie einen SIP-Trunk oder ein Gateway bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ef873-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="ef873-118">Sie müssen keine Survivable Branch Appliance am Zweigstellenstandort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ef873-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="ef873-119">Wenn die Verknüpfung zwischen der Zweigstelle und dem zentralen Standort nicht ausfallsicher ist, Bereitstellen einer Survivable Branch Appliance oder einen Survivable Branch Server mit einem Gateway oder SIP-Trunk am Zweigstellenstandort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ef873-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

