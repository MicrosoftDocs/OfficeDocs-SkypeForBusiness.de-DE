---
title: 'Lync Server 2013: Bereitstellen von Zweigstellenstandorten'
description: 'Lync Server 2013: Bereitstellen von Zweigstellenstandorten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d653e3f06de832693d97bfb229f122a67c28640e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552641"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="6a0b9-103">Bereitstellen von Zweigstellenstandorten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a0b9-103">Deploying branch sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a0b9-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6a0b9-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6a0b9-105">Zweigstellenbenutzer erhalten den Großteil ihrer lync Server 2013 Funktionalität von dem Server am zentralen Standort, dem der Zweigstellenstandort zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6a0b9-105">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="6a0b9-106">Jede Zweigstelle ist mit genau einem zentralen Standort verbunden.</span><span class="sxs-lookup"><span data-stu-id="6a0b9-106">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="6a0b9-107">Zum Tätigen und Entgegennehmen von Anrufen aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) kann ein Zweigstellenstandort eine der folgenden Komponenten umfassen:</span><span class="sxs-lookup"><span data-stu-id="6a0b9-107">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="6a0b9-108">Ein PSTN-Gateway und optional einen Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="6a0b9-108">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="6a0b9-109">Einen SIP-Trunk</span><span class="sxs-lookup"><span data-stu-id="6a0b9-109">A SIP trunk</span></span>

  - <span data-ttu-id="6a0b9-110">Eine vorhandene VoIP-Infrastruktur mit einer Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="6a0b9-110">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="6a0b9-111">Ein Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="6a0b9-111">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="6a0b9-112">Ein Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="6a0b9-112">A Survivable Branch Server</span></span>

<span data-ttu-id="6a0b9-113">Zweigstellenstandorte mit einem Survivable Branch Appliance oder einem Survivable Branch Server sind in Zeiten größerer Netzwerk-oder zentraler Standortausfälle widerstandsfähiger als Zweigstellenstandorte ohne eine dieser Lösungen.</span><span class="sxs-lookup"><span data-stu-id="6a0b9-113">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="6a0b9-114">Beispielsweise können Benutzer bei einer Website mit einer Survivable Branch Appliance oder einer Survivable Branch Server, die bereitgestellt werden, weiterhin PSTN-Anrufe tätigen und empfangen, wenn das Netzwerk, das den Zweigstellenstandort mit dem zentralen Standort verbindet, nicht aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="6a0b9-114">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="6a0b9-115">Eine weitere Möglichkeit zum Erreichen von Ausfallsicherheit für Zweigstellenstandorte ist die Verwendung eines PSTN-Gateways oder eines SIP-Trunks mit einer vollständigen lync Server-Bereitstellung am Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="6a0b9-115">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="6a0b9-116">Ausführliche Informationen dazu, welche Zweigstellenbereitstellung für Ihre Organisation geeignet ist, einschließlich Voraussetzungen und anderen Planungsüberlegungen, finden Sie unter [Planning for PSTN Connectivity in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) und [Planning for Branch-Site Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6a0b9-116">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6a0b9-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6a0b9-117">In This Section</span></span>

  - [<span data-ttu-id="6a0b9-118">Bereitstellen der PSTN-Konnektivität an einem Zweigstellenstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a0b9-118">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="6a0b9-119">Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a0b9-119">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

