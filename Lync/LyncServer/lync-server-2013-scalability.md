---
title: Lync Server 2013 Skalierbarkeit
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
ms.openlocfilehash: d2b26f8f7b7b254a8576a08e9b24fdeb2da633b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510959"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="ee27f-102">Skalierbarkeit mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee27f-102">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee27f-103">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="ee27f-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="ee27f-104">Lync Server wird in zwei Editionen, Enterprise Edition und Standard Edition angeboten.</span><span class="sxs-lookup"><span data-stu-id="ee27f-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="ee27f-105">Die verschiedenen Editionen sind vor allem auf Organisationen unterschiedlicher Größe ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="ee27f-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="ee27f-106">Der folgenden Tabelle können Sie entnehmen, dass beide Editionen mit Ausnahme der hohen Verfügbarkeit und der Notfallwiederherstellung die gesamte Funktionalität in allen Arbeitsauslastungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ee27f-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee27f-107">Feature</span><span class="sxs-lookup"><span data-stu-id="ee27f-107">Feature</span></span></th>
<th><span data-ttu-id="ee27f-108">Unterstützung in Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ee27f-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="ee27f-109">Unterstützung in Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ee27f-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee27f-110">Instant Messaging und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="ee27f-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="ee27f-111">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="ee27f-112">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee27f-113">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="ee27f-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="ee27f-114">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="ee27f-115">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee27f-116">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="ee27f-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="ee27f-117">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="ee27f-118">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee27f-119">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="ee27f-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="ee27f-120">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="ee27f-121">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee27f-122">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="ee27f-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="ee27f-123">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="ee27f-124">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee27f-125">Virtualisierung</span><span class="sxs-lookup"><span data-stu-id="ee27f-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="ee27f-126">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="ee27f-127">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee27f-128">Hochverfügbarkeit, Failover und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="ee27f-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="ee27f-129">Ja</span><span class="sxs-lookup"><span data-stu-id="ee27f-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="ee27f-130">Nein</span><span class="sxs-lookup"><span data-stu-id="ee27f-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

