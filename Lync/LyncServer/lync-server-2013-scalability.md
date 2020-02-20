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
ms.openlocfilehash: 3bd340d46855f01e8ff43dc9f66b527e5df1967c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="8183b-102">Skalierbarkeit mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8183b-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8183b-103">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="8183b-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="8183b-104">Lync Server wird in zwei Editionen, Enterprise Edition und Standard Edition angeboten.</span><span class="sxs-lookup"><span data-stu-id="8183b-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="8183b-105">Die verschiedenen Editionen sind vor allem auf Organisationen unterschiedlicher Größe ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="8183b-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="8183b-106">Der folgenden Tabelle können Sie entnehmen, dass beide Editionen mit Ausnahme der hohen Verfügbarkeit und der Notfallwiederherstellung die gesamte Funktionalität in allen Arbeitsauslastungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8183b-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8183b-107">Feature</span><span class="sxs-lookup"><span data-stu-id="8183b-107">Feature</span></span></th>
<th><span data-ttu-id="8183b-108">Unterstützung in Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="8183b-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="8183b-109">Unterstützung in Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8183b-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8183b-110">Instant Messaging und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="8183b-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="8183b-111">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="8183b-112">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8183b-113">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="8183b-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="8183b-114">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="8183b-115">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8183b-116">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="8183b-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="8183b-117">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="8183b-118">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8183b-119">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="8183b-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="8183b-120">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="8183b-121">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8183b-122">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="8183b-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="8183b-123">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="8183b-124">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8183b-125">Virtualisierung</span><span class="sxs-lookup"><span data-stu-id="8183b-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="8183b-126">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="8183b-127">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8183b-128">Hochverfügbarkeit, Failover und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="8183b-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="8183b-129">Ja</span><span class="sxs-lookup"><span data-stu-id="8183b-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="8183b-130">Nein</span><span class="sxs-lookup"><span data-stu-id="8183b-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

