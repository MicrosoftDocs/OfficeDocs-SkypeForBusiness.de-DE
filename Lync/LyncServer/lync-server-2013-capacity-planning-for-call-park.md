---
title: 'Lync Server 2013: Kapazitätsplanung für das Parken von Anrufen'
description: 'Lync Server 2013: Kapazitätsplanung für das Parken von anrufen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 053a6dabad9d10540e84e9e4f43de09057c295f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544541"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="981f5-103">Kapazitätsplanung für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="981f5-103">Capacity planning for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="981f5-104">_**Letztes Änderungsstand des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="981f5-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="981f5-105">In der folgenden Tabelle wird das Benutzermodell für das Parken von Anrufen beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="981f5-105">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="981f5-106">Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitslasten für die Dienste für den Parken von Anrufen in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="981f5-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="981f5-107">Benutzermodell der Funktion zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="981f5-107">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="981f5-108">Metrik</span><span class="sxs-lookup"><span data-stu-id="981f5-108">Metric</span></span></th>
<th><span data-ttu-id="981f5-109">Pro Front-End-Pool (mit 8 Front-End-Servern)</span><span class="sxs-lookup"><span data-stu-id="981f5-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="981f5-110">Pro Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="981f5-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="981f5-111">Rate für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="981f5-111">Park rate</span></span></p></td>
<td><p><span data-ttu-id="981f5-112">8 pro Minute</span><span class="sxs-lookup"><span data-stu-id="981f5-112">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="981f5-113">1 pro Minute</span><span class="sxs-lookup"><span data-stu-id="981f5-113">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="981f5-114">Rate für das Abrufen geparkter Anrufe</span><span class="sxs-lookup"><span data-stu-id="981f5-114">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="981f5-115">8 pro Minute</span><span class="sxs-lookup"><span data-stu-id="981f5-115">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="981f5-116">1 pro Minute</span><span class="sxs-lookup"><span data-stu-id="981f5-116">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="981f5-117">Durchschnittliche Parkdauer</span><span class="sxs-lookup"><span data-stu-id="981f5-117">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="981f5-118">60 Sekunden</span><span class="sxs-lookup"><span data-stu-id="981f5-118">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="981f5-119">60 Sekunden</span><span class="sxs-lookup"><span data-stu-id="981f5-119">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

