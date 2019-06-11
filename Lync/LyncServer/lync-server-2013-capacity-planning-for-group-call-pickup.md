---
title: 'Lync Server 2013: Kapazitätsplanung für die Gruppenanruf Abholung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="e2554-102">Kapazitätsplanung für die Gruppenanruf Abholung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2554-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2554-103">_**Letztes Änderungsdatum des Themas:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="e2554-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="e2554-104">In der folgenden Tabelle wird das Benutzermodell für die Gruppenanruf Abholung beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e2554-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e2554-105">Die Abholung von Gruppen anrufen basiert auf der Anwendung "Parken".</span><span class="sxs-lookup"><span data-stu-id="e2554-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="e2554-106">Beachten Sie, dass für die Planung von Disaster Recovery-Kapazität jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitsauslastungen für die Anruf Park Dienste, einschließlich der Gruppenanruf Abholung, in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e2554-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="e2554-107">Gruppenanruf-Pickup-Benutzermodell</span><span class="sxs-lookup"><span data-stu-id="e2554-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2554-108">Metrik</span><span class="sxs-lookup"><span data-stu-id="e2554-108">Metric</span></span></th>
<th><span data-ttu-id="e2554-109">Pro Front-End-Pool (mit 8 Front-End-Servern)</span><span class="sxs-lookup"><span data-stu-id="e2554-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="e2554-110">Pro Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="e2554-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2554-111">Empfohlene Benutzeranzahl pro Gruppe</span><span class="sxs-lookup"><span data-stu-id="e2554-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="e2554-112">50</span><span class="sxs-lookup"><span data-stu-id="e2554-112">50</span></span></p></td>
<td><p><span data-ttu-id="e2554-113">50</span><span class="sxs-lookup"><span data-stu-id="e2554-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2554-114">Empfohlene Gruppenanzahl</span><span class="sxs-lookup"><span data-stu-id="e2554-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="e2554-115">500</span><span class="sxs-lookup"><span data-stu-id="e2554-115">500</span></span></p></td>
<td><p><span data-ttu-id="e2554-116">60</span><span class="sxs-lookup"><span data-stu-id="e2554-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2554-117">Maximale Anzahl der für die Gruppenanrufannahme aktivierten Benutzer pro Pool</span><span class="sxs-lookup"><span data-stu-id="e2554-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="e2554-118">25.000</span><span class="sxs-lookup"><span data-stu-id="e2554-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="e2554-119">3.000</span><span class="sxs-lookup"><span data-stu-id="e2554-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2554-120">Maximale Rate an eingehenden Anrufen pro Pool und Minute an alle Benutzer, die für die Gruppenanrufannahme aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="e2554-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="e2554-121">500</span><span class="sxs-lookup"><span data-stu-id="e2554-121">500</span></span></p></td>
<td><p><span data-ttu-id="e2554-122">60</span><span class="sxs-lookup"><span data-stu-id="e2554-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2554-123">Maximale Rate an von Benutzern mit Gruppenanrufannahme wieder aufgenommenen Anrufen pro Pool und Minute</span><span class="sxs-lookup"><span data-stu-id="e2554-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="e2554-124">200</span><span class="sxs-lookup"><span data-stu-id="e2554-124">200</span></span></p></td>
<td><p><span data-ttu-id="e2554-125">25</span><span class="sxs-lookup"><span data-stu-id="e2554-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="e2554-126">Für Front-End-Pools mit weniger als acht Front-End-Servern berechnen Sie die Metriken linear.</span><span class="sxs-lookup"><span data-stu-id="e2554-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="e2554-127">Wenn der Front-End-Pool beispielsweise über einen Front-End-Server verfügt, berechnen Sie die maximale Auslastung als 1/8 der in der Tabelle angegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="e2554-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="e2554-128">Sie können die empfohlene Anzahl von Benutzern pro Gruppe erhöhen oder reduzieren, solange die maximale Anzahl von Benutzern pro Pool nicht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="e2554-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="e2554-129">Beispielsweise kann Ihr Standard Edition-Server 120-Gruppen mit 25 Benutzern pro Gruppe haben, da die Anzahl der Benutzer, die für die Gruppenanruf-Abholung aktiviert sind, sich noch innerhalb des maximal zulässigen Benutzermodells befindet (das heißt, 120 Gruppen mal 25 Benutzer sind 3.000 Benutzer, die für Gruppenanruf-Pickups aktiviert sind).</span><span class="sxs-lookup"><span data-stu-id="e2554-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

