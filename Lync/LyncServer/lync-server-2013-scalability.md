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
ms.openlocfilehash: 130b1958b418aa2b09e572f137598487dc2c3401
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="23a91-102">Skalierbarkeit mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23a91-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23a91-103">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="23a91-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="23a91-104">Lync Server wird in zwei Editionen, Enterprise Edition und Standard Edition angeboten.</span><span class="sxs-lookup"><span data-stu-id="23a91-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="23a91-105">Die verschiedenen Editionen sind vor allem auf Organisationen unterschiedlicher Größe ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="23a91-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="23a91-106">Der folgenden Tabelle können Sie entnehmen, dass beide Editionen mit Ausnahme der hohen Verfügbarkeit und der Notfallwiederherstellung die gesamte Funktionalität in allen Arbeitsauslastungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="23a91-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23a91-107">Feature</span><span class="sxs-lookup"><span data-stu-id="23a91-107">Feature</span></span></th>
<th><span data-ttu-id="23a91-108">Unterstützung in Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="23a91-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="23a91-109">Unterstützung in Standard Edition</span><span class="sxs-lookup"><span data-stu-id="23a91-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23a91-110">Instant Messaging und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="23a91-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="23a91-111">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="23a91-112">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23a91-113">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="23a91-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="23a91-114">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="23a91-115">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23a91-116">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="23a91-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="23a91-117">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="23a91-118">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23a91-119">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="23a91-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="23a91-120">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="23a91-121">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23a91-122">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="23a91-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="23a91-123">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="23a91-124">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23a91-125">Virtualisierung</span><span class="sxs-lookup"><span data-stu-id="23a91-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="23a91-126">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="23a91-127">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23a91-128">Hochverfügbarkeit, Failover und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="23a91-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="23a91-129">Ja</span><span class="sxs-lookup"><span data-stu-id="23a91-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="23a91-130">Nein</span><span class="sxs-lookup"><span data-stu-id="23a91-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

