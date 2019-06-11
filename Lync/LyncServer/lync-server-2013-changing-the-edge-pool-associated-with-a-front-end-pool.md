---
title: 'Lync Server 2013: Ändern des einem Front-End-Pool zugeordneten Edgepools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="2ce66-102">Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ce66-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ce66-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2ce66-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2ce66-104">Wenn ein Edge-Pool ausfällt, der Front-End-Pool am gleichen Standort aber noch ausgeführt wird, müssen Sie den Front-End-Pool so einrichten, dass ein Edge-Pool an einer anderen Website verwendet wird, bis der fehlerhafte Edge-Pool wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2ce66-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="2ce66-105">Ändern des einem Front-End-Pool zugeordneten Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="2ce66-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="2ce66-106">Navigieren Sie im Topologie-Generator zu dem Namen des Front-End-Pools, den Sie ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="2ce66-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="2ce66-107">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2ce66-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="2ce66-108">Verwenden Sie im Abschnitt **Zuordnungen** unter **Edge-Pool zuordnen (für Medienkomponenten)** das Dropdownfeld, um den Edge-Pool auszuwählen, dem Sie diesen Front-End-Pool zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="2ce66-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="2ce66-109">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ce66-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ce66-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ce66-110">See Also</span></span>


[<span data-ttu-id="2ce66-111">Notfallwiederherstellung für Edgeserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ce66-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

