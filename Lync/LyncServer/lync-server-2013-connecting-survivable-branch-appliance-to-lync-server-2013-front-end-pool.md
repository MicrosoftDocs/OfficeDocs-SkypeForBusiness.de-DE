---
title: Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d23b501738010a8e5e5ed1c5c2e9a8608b0709e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="89dad-102">Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="89dad-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89dad-103">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="89dad-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="89dad-104">Jede Survivable Branch Appliance (SBA) ist einer Front-End-Pool zugeordnet, die als Sicherungs Registrierungsstelle für die SBVg dient.</span><span class="sxs-lookup"><span data-stu-id="89dad-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="89dad-105">Wenn das Front-End-Pool auf lync Server 2013 aktualisiert wird, muss das SBA von der Front-End-Pool entfernt werden, während das Front-End-Pool aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="89dad-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="89dad-106">Nachdem die Front-End-Pool aktualisiert wurde, kann die SBVg der Front-End-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="89dad-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="89dad-107">Dazu muss die SBA aus der Topologie im Topologie-Generator gelöscht und anschließend erneut zum Topologie-Generator hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="89dad-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="89dad-108">Benutzer, die im SBA verwaltet werden, müssen in ein anderes Front-End-Pool verschoben werden, bevor Sie die SBVg aus der Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="89dad-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="89dad-109">Nach dem erneuten Hinzufügen der SBA zur Topologie können diese Benutzer auf die SBA zurückverschoben werden.</span><span class="sxs-lookup"><span data-stu-id="89dad-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="89dad-110">Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="89dad-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="89dad-111">Verlagerung von Zweigstellenbenutzern, die in SBA verwaltet werden, in eine andere Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="89dad-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="89dad-112">Entfernen Sie SBA aus Ihrer Topologie, um die vorhandene Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.</span><span class="sxs-lookup"><span data-stu-id="89dad-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="89dad-113">Aktualisieren Sie Front-End-Pool auf Microsoft lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89dad-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="89dad-114">Fügen Sie die SBA wieder Ihrer Topologie hinzu.</span><span class="sxs-lookup"><span data-stu-id="89dad-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="89dad-115">Ordnen Sie den neuen Front-End-Pool der SBVg als Sicherungs Registrierungsstelle zu.</span><span class="sxs-lookup"><span data-stu-id="89dad-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="89dad-116">Verschieben Sie die Zweigstellenbenutzer zurück auf die SBA.</span><span class="sxs-lookup"><span data-stu-id="89dad-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89dad-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="89dad-117">In This Section</span></span>

  - [<span data-ttu-id="89dad-118">Hinzufügen von lync Server 2013 Survivable Branch Appliance Zweigstellen Standorts zur Topologie</span><span class="sxs-lookup"><span data-stu-id="89dad-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="89dad-119">Hinzufügen von lync Server 2010 Survivable Branch Appliance Zweigstellen Standorts zur Topologie</span><span class="sxs-lookup"><span data-stu-id="89dad-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

