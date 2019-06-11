---
title: Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="b73de-102">Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="b73de-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b73de-103">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b73de-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b73de-104">Jede Survivable Branch Appliance (SBA) ist mit einem Front-End-Pool verknüpft, der als Sicherungs Registrierungsstelle für die SBA fungiert.</span><span class="sxs-lookup"><span data-stu-id="b73de-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="b73de-105">Wenn der Front-End-Pool auf lync Server 2013 aktualisiert wird, muss der SBA vom Front-End-Pool entfernt werden, während der Front-End-Pool aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b73de-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="b73de-106">Nach dem Upgrade des Front-End-Pools kann die SBA dem Front-End-Pool erneut zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b73de-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="b73de-107">Dies umfasst das Löschen des SBA aus der Topologie im Topologie-Generator und das anschließende erneute Hinzufügen des SBA zu Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="b73de-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="b73de-108">Benutzer, die in der SBA verwaltet werden, müssen in einen anderen Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="b73de-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="b73de-109">Nachdem die SBA wieder zur Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBA verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b73de-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="b73de-110">Nachfolgend werden die folgenden Schritte zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="b73de-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="b73de-111">Verschieben Sie Branch-Benutzer, die in SBA beheimatet sind, in einen anderen Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="b73de-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="b73de-112">Entfernen Sie SBA aus Ihrer Topologie, um den vorhandenen Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.</span><span class="sxs-lookup"><span data-stu-id="b73de-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="b73de-113">Aktualisieren des Front-End-Pools auf Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b73de-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="b73de-114">Fügen Sie SBA wieder in Ihre Topologie ein.</span><span class="sxs-lookup"><span data-stu-id="b73de-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="b73de-115">Ordnen Sie den neuen Front-End-Pool der SBA als Sicherungs Registrierungsstelle zu.</span><span class="sxs-lookup"><span data-stu-id="b73de-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="b73de-116">Verschieben Sie Branch-Benutzer zurück in die SBA.</span><span class="sxs-lookup"><span data-stu-id="b73de-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b73de-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b73de-117">In This Section</span></span>

  - [<span data-ttu-id="b73de-118">Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2013 Survivable Branch Appliance zu einer Topologie</span><span class="sxs-lookup"><span data-stu-id="b73de-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="b73de-119">Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2010 Survivable Branch Appliance zu einer Topologie</span><span class="sxs-lookup"><span data-stu-id="b73de-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

