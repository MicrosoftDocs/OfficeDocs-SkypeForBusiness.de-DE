---
title: Lync Server 2013 Skalierbarkeit
description: Lync Server 2013 Skalierbarkeit.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543791"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="f61ad-103">Skalierbarkeit mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f61ad-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f61ad-104">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="f61ad-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f61ad-105">Lync Server wird in zwei Editionen, Enterprise Edition und Standard Edition angeboten.</span><span class="sxs-lookup"><span data-stu-id="f61ad-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="f61ad-106">Die verschiedenen Editionen sind vor allem auf Organisationen unterschiedlicher Größe ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="f61ad-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="f61ad-107">Der folgenden Tabelle können Sie entnehmen, dass beide Editionen mit Ausnahme der hohen Verfügbarkeit und der Notfallwiederherstellung die gesamte Funktionalität in allen Arbeitsauslastungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f61ad-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f61ad-108">Feature</span><span class="sxs-lookup"><span data-stu-id="f61ad-108">Feature</span></span></th>
<th><span data-ttu-id="f61ad-109">Unterstützung in Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f61ad-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="f61ad-110">Unterstützung in Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f61ad-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f61ad-111">Instant Messaging und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="f61ad-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="f61ad-112">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="f61ad-113">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ad-114">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="f61ad-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="f61ad-115">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="f61ad-116">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f61ad-117">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="f61ad-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="f61ad-118">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="f61ad-119">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ad-120">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="f61ad-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="f61ad-121">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="f61ad-122">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f61ad-123">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="f61ad-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="f61ad-124">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="f61ad-125">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ad-126">Virtualisierung</span><span class="sxs-lookup"><span data-stu-id="f61ad-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="f61ad-127">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="f61ad-128">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f61ad-129">Hochverfügbarkeit, Failover und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="f61ad-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="f61ad-130">Ja</span><span class="sxs-lookup"><span data-stu-id="f61ad-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="f61ad-131">Nein</span><span class="sxs-lookup"><span data-stu-id="f61ad-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

