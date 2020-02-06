---
title: SIP-Trunking in der Zweigstelle in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Informieren Sie sich über SIP-Trunking an Zweigstellen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 158c1cff28ba0c21f5c995a1fe5b7dfdf2f9f150
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803255"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="25411-103">SIP-Trunking in der Zweigstelle in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="25411-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="25411-104">Informieren Sie sich über SIP-Trunking an Zweigstellen in Skype for Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="25411-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="25411-105">In einigen Fällen müssen Sie möglicherweise verteilte SIP-Trunking an ausgewählten Zweigstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="25411-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="25411-106">Wenn Sie feststellen möchten, ob ein SIP-Trunk für eine Zweigstelle benötigt wird, und Details zu den unterstützten Topologie-Optionen für die Bereitstellung von SIP-Stämmen in Zweigstellen finden Sie unter [SIP-Trunking in Skype for Business Server](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="25411-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="25411-107">Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung</span><span class="sxs-lookup"><span data-stu-id="25411-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="25411-108">Wenn Sie sich für die Bereitstellung einer Zweigstelle SIP Trunk entscheiden, müssen Sie eine Website spezifische Kostenanalyse durchführen.</span><span class="sxs-lookup"><span data-stu-id="25411-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="25411-109">Beispielsweise sollte ein Unternehmen mit einem zentralen Standort in Redmond, Washington und einer Zweigstelle in New York eine Analyse durchführen, um zu ermitteln, ob ein SIP-Trunk vom Standort New York zu einem lokalen Dienstanbieter implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="25411-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="25411-110">Wenn Sie feststellen möchten, ob ein verteilter SIP-Trunk in New York kostengünstig ist, ermitteln Sie, welche Direktwahlnummern (DID) den SIP-Stamm verwenden, und analysieren Sie die Anzahl der Anrufe, die in New York an andere Bereiche als Redmond (425) vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="25411-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="25411-111">Sie können für die Verzweigungs Website am zentralen Standort beendet haben.</span><span class="sxs-lookup"><span data-stu-id="25411-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="25411-112">So kann beispielsweise auf der zentralen Website von Redmond die Nummer für die Niederlassung in der New York Branch-Website gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="25411-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="25411-113">Wenn die Kosten für die Implementierung eines verteilten SIP-Trunks kleiner als die Kosten dieser Anrufe sind, sollten Sie einen SIP-Trunk an der New York Branch-Website implementieren.</span><span class="sxs-lookup"><span data-stu-id="25411-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="25411-114">Weitere SIP-Trunkanforderungen für Zweigniederlassungen</span><span class="sxs-lookup"><span data-stu-id="25411-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="25411-115">Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="25411-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="25411-116">Wenn Sie eine Verzweigungs Website SIP-Trunk bereitstellen, müssen Sie auch ihre Stabilitäts-und Bandbreitenanforderungen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="25411-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="25411-117">Wenn der Link zwischen Ihrer Zweigstelle und dem zentralen Standort widerstandsfähig ist und über genügend Bandbreite verfügt, können Sie einen SIP-Trunk oder ein Gateway bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="25411-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="25411-118">Sie müssen keine Survivable Branch-Appliance an der Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="25411-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="25411-119">Wenn der Link zwischen Ihrer Verzweigungs Website und dem zentralen Standort nicht belastbar ist, stellen Sie eine Survivable Branch-Appliance bereit, oder stellen Sie einen überlebensfähigen Verzweigungs Server mit einem Gateway oder SIP-Trunk an der Zweigstelle bereit.</span><span class="sxs-lookup"><span data-stu-id="25411-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

