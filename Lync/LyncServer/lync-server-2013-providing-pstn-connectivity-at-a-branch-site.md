---
title: 'Lync Server 2013: Bereitstellen der PSTN-Konnektivität an einem Zweigstellenstandort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf4b0582de84fe8d2eff4b0026f27a7268af2a02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="3da83-102">Bereitstellen der PSTN-Konnektivität an einem Zweigstellenstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da83-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3da83-103">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3da83-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3da83-104">Wir empfehlen die Verwendung des Microsoft lync Server 2013, Planungstools zum Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie und zum Einrichten Ihrer VoIP-Infrastruktur an Zweigstellenstandorten.</span><span class="sxs-lookup"><span data-stu-id="3da83-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="3da83-105">Wenn Sie das Planungs Tool nicht verwenden, verwenden Sie die Verfahren in den Themen in diesem Abschnitt zuerst zum Hinzufügen der Zweigstellenstandorte und dann zum Einrichten Ihrer VoIP-Infrastruktur durch Definieren des IP/Public Switched Telephone Network (PSTN)-Gateways und/oder durch Konfigurieren des SIP-Trunks (mit oder ohne medienumgehung).</span><span class="sxs-lookup"><span data-stu-id="3da83-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="3da83-106">Eine weitere Option ist das Verbinden einer Nebenstellenanlage mit dem Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="3da83-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3da83-107">Wenn Sie Ausfallsicherheit für Zweigstellenstandorte bereitstellen möchten, müssen Sie eine Survivable Branch Appliance, eine Survivable Branch Server oder Standard Edition-Server am Zweigstellenstandort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3da83-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="3da83-108">Ausführliche Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013</A> oder <A href="lync-server-2013-deploying-lync-server.md">Bereitstellen lync Server 2013</A>entsprechend.</span><span class="sxs-lookup"><span data-stu-id="3da83-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3da83-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3da83-109">In This Section</span></span>

  - [<span data-ttu-id="3da83-110">Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da83-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="3da83-111">Definieren eines PSTN-Gateways für einen Zweigstellenstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da83-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="3da83-112">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da83-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="3da83-113">Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da83-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3da83-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3da83-114">See Also</span></span>


[<span data-ttu-id="3da83-115">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da83-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="3da83-116">Planen der PSTN-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da83-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

