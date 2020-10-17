---
title: 'Lync Server 2013: Ändern der einem Front-End-Pool zugeordneten Edgepool'
description: 'Lync Server 2013: Ändern der einem Front-End-Pool zugeordneten Edgepool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab22ba35420341e291d51a1ff012459840e63a56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543571"
---
# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="1e5df-103">Ändern des Edgepool, das einem Front-End-Pool in lync Server 2013 zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="1e5df-103">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e5df-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1e5df-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1e5df-105">Wenn ein Edgepool ausfällt, aber der Front-End-Pool an demselben Standort noch ausgeführt wird, müssen Sie den Front-End-Pool so konfigurieren, dass er einen Edgepool an einem anderen Standort verwendet, bis der ausgefallene Edgepool wiederhergestellt ist.</span><span class="sxs-lookup"><span data-stu-id="1e5df-105">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="1e5df-106">Ändern des Edgepools, der einem Front-End-Pool zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="1e5df-106">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="1e5df-107">Navigieren Sie im Topologie-Generator zum Namen des Front-End-Pools, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="1e5df-107">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="1e5df-108">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1e5df-108">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="1e5df-109">Wählen Sie im Abschnitt **Zuordnungen** unter **Edgepool zuordnen (für Medienkomponenten)** im Dropdownfeld den Edgepool aus, den Sie diesem Front-End-Pool zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="1e5df-109">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="1e5df-110">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e5df-110">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e5df-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e5df-111">See Also</span></span>


[<span data-ttu-id="1e5df-112">Edgeserver Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e5df-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

