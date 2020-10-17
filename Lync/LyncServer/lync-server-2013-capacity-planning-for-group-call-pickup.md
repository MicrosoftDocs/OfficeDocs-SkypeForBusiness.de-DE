---
title: 'Lync Server 2013: Kapazitätsplanung für die gruppenanrufannahme'
description: 'Lync Server 2013: Kapazitätsplanung für die Gruppenanruf Abholung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12648c57d1036a0ed27c60ef6399bf570c5dcd3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544531"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="7fe55-103">Kapazitätsplanung für die gruppenanrufannahme in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fe55-103">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe55-104">_**Letztes Änderungsstand des Themas:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="7fe55-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="7fe55-105">In der folgenden Tabelle wird das Benutzermodell für die gruppenanrufannahme beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7fe55-105">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7fe55-106">Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="7fe55-106">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="7fe55-107">Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitslasten für die Dienste für den Parken von anrufen, einschließlich der gruppenanrufannahme, in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7fe55-107">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="7fe55-108">Gruppenanruf-Pickup-Benutzermodell</span><span class="sxs-lookup"><span data-stu-id="7fe55-108">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe55-109">Metrik</span><span class="sxs-lookup"><span data-stu-id="7fe55-109">Metric</span></span></th>
<th><span data-ttu-id="7fe55-110">Pro Front-End-Pool (mit 8 Front-End-Servern)</span><span class="sxs-lookup"><span data-stu-id="7fe55-110">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="7fe55-111">Pro Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="7fe55-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe55-112">Empfohlene Anzahl von Benutzern pro Gruppe</span><span class="sxs-lookup"><span data-stu-id="7fe55-112">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="7fe55-113">50</span><span class="sxs-lookup"><span data-stu-id="7fe55-113">50</span></span></p></td>
<td><p><span data-ttu-id="7fe55-114">50</span><span class="sxs-lookup"><span data-stu-id="7fe55-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe55-115">Empfohlene Anzahl von Gruppen</span><span class="sxs-lookup"><span data-stu-id="7fe55-115">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="7fe55-116">500</span><span class="sxs-lookup"><span data-stu-id="7fe55-116">500</span></span></p></td>
<td><p><span data-ttu-id="7fe55-117">60</span><span class="sxs-lookup"><span data-stu-id="7fe55-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe55-118">Maximale Anzahl von Benutzern pro Pool, die für die gruppenanrufannahme aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="7fe55-118">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="7fe55-119">25.000</span><span class="sxs-lookup"><span data-stu-id="7fe55-119">25,000</span></span></p></td>
<td><p><span data-ttu-id="7fe55-120">3,000</span><span class="sxs-lookup"><span data-stu-id="7fe55-120">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe55-121">Maximale Anzahl eingehender Anrufe an Gesamtbenutzer, die für die gruppenanrufannahme pro Pool pro Minute aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="7fe55-121">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="7fe55-122">500</span><span class="sxs-lookup"><span data-stu-id="7fe55-122">500</span></span></p></td>
<td><p><span data-ttu-id="7fe55-123">60</span><span class="sxs-lookup"><span data-stu-id="7fe55-123">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fe55-124">Maximale Anzahl von anrufen, die von Benutzern mit der gruppenanrufannahme pro Pool pro Minute abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="7fe55-124">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="7fe55-125">200</span><span class="sxs-lookup"><span data-stu-id="7fe55-125">200</span></span></p></td>
<td><p><span data-ttu-id="7fe55-126">25</span><span class="sxs-lookup"><span data-stu-id="7fe55-126">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="7fe55-127">Für Front-End-Pools mit weniger als acht Front-End-Servern sollten Sie die Metriken linear berechnen.</span><span class="sxs-lookup"><span data-stu-id="7fe55-127">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="7fe55-128">Wenn Ihr Front-End-Pool beispielsweise über eine Front-End-Server verfügt, berechnen Sie die maximale Last als 1/8 der in der Tabelle gezeigten Werte.</span><span class="sxs-lookup"><span data-stu-id="7fe55-128">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="7fe55-129">Sie können die empfohlene Anzahl von Benutzern pro Gruppe und Anzahl von Gruppen erweitern oder verringern, solange Sie die maximale Anzahl von Benutzern pro Pool nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="7fe55-129">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="7fe55-130">Beispielsweise kann Ihre Standard Edition-Server 120 Gruppen mit 25 Benutzern pro Gruppe haben, da die Anzahl der Benutzer, die für die gruppenanrufannahme aktiviert sind, sich immer noch innerhalb des Benutzermodell Maximums befindet (120 Gruppen mal 25 Benutzer 3.000 Benutzer sind, die für die gruppenanrufannahme aktiviert sind).</span><span class="sxs-lookup"><span data-stu-id="7fe55-130">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

