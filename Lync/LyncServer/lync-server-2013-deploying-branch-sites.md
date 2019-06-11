---
title: 'Lync Server 2013: Bereitstellen von Zweigstellen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="9e9f4-102">Bereitstellen von Zweigstellen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e9f4-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e9f4-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9e9f4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9e9f4-104">Zweigstellenbenutzer erhalten die meisten ihrer lync Server 2013-Funktionen von dem Server am zentralen Standort, dem die Zweigstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="9e9f4-105">Jede Verzweigungs Website ist genau einem zentralen Standort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="9e9f4-106">Zum Bereitstellen von Anrufen in das und aus dem PSTN (Public Switched Telephone Network) kann eine Verzweigungs Website eine der folgenden Aktionen enthalten:</span><span class="sxs-lookup"><span data-stu-id="9e9f4-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="9e9f4-107">Ein PSTN-Gateway und möglicherweise ein Meditations Server</span><span class="sxs-lookup"><span data-stu-id="9e9f4-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="9e9f4-108">Ein SIP-Trunk</span><span class="sxs-lookup"><span data-stu-id="9e9f4-108">A SIP trunk</span></span>

  - <span data-ttu-id="9e9f4-109">Eine vorhandene VoIP-Infrastruktur mit einer PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="9e9f4-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="9e9f4-110">Eine Survivable-Branch-Appliance</span><span class="sxs-lookup"><span data-stu-id="9e9f4-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="9e9f4-111">Ein Survivable-Branch-Server</span><span class="sxs-lookup"><span data-stu-id="9e9f4-111">A Survivable Branch Server</span></span>

<span data-ttu-id="9e9f4-112">Zweigstellen mit einer überlebensfähigen Branch-Appliance oder einem Survivable Branch-Server sind in Zeiten von Wide-Area-Netzwerk-oder zentralen Standortausfällen widerstandsfähiger als Zweigstellen ohne eine dieser Lösungen.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="9e9f4-113">Beispielsweise können Benutzer in einer Website mit einer überlebensfähigen Branch-Appliance oder einem Überlebenden Branch-Server weiterhin PSTN-Anrufe tätigen und empfangen, wenn das Netzwerk, das die Verzweigungs Website mit dem zentralen Standort verbindet, ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="9e9f4-114">Eine weitere Möglichkeit zum Erreichen einer Ausfallsicherheit für Zweigstellen ist die Verwendung eines PSTN-Gateways oder eines SIP-Trunks mit einer vollständigen lync Server-Bereitstellung auf der Zweigstelle.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="9e9f4-115">Details dazu, welche Verzweigungs Website Bereitstellung für Ihre Organisation richtig ist, einschließlich Voraussetzungen und andere Planungsüberlegungen, finden Sie unter [Planen der PSTN-Konnektivität in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) und [Planen der sprach Sicherheit in der Zweigstelle in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e9f4-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9e9f4-116">In This Section</span></span>

  - [<span data-ttu-id="9e9f4-117">Bereitstellen der PSTN-Konnektivität an einem Zweigstellenstandort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e9f4-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="9e9f4-118">Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e9f4-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

