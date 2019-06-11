---
title: 'Lync Server 2013: Skalierbarkeit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dfdc96934871fd2e73af30507288c734e786cc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="471fc-102">Skalierbarkeit mit Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="471fc-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="471fc-103">_**Letztes Änderungsdatum des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="471fc-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="471fc-104">Lync Server wird in zwei Editionen, Enterprise Edition und Standard Edition angeboten.</span><span class="sxs-lookup"><span data-stu-id="471fc-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="471fc-105">Die verschiedenen Editionen sind in erster Linie für unterschiedliche Größen von Organisationen vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="471fc-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="471fc-106">Wie in der folgenden Tabelle dargestellt, unterstützen beide Editionen alle Funktionen in allen Arbeitsauslastungen, mit Ausnahme von höchst Verfügbarkeit und Disaster Recovery.</span><span class="sxs-lookup"><span data-stu-id="471fc-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="471fc-107">Feature</span><span class="sxs-lookup"><span data-stu-id="471fc-107">Feature</span></span></th>
<th><span data-ttu-id="471fc-108">In Enterprise Edition unterstützt?</span><span class="sxs-lookup"><span data-stu-id="471fc-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="471fc-109">In der Standard Edition unterstützt?</span><span class="sxs-lookup"><span data-stu-id="471fc-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="471fc-110">Instant Messaging (im) und Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="471fc-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="471fc-111">Ja </span><span class="sxs-lookup"><span data-stu-id="471fc-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="471fc-112">Ja</span><span class="sxs-lookup"><span data-stu-id="471fc-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471fc-113">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="471fc-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="471fc-114">Ja </span><span class="sxs-lookup"><span data-stu-id="471fc-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="471fc-115">Ja</span><span class="sxs-lookup"><span data-stu-id="471fc-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="471fc-116">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="471fc-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="471fc-117">Ja </span><span class="sxs-lookup"><span data-stu-id="471fc-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="471fc-118">Ja</span><span class="sxs-lookup"><span data-stu-id="471fc-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471fc-119">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="471fc-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="471fc-120">Ja </span><span class="sxs-lookup"><span data-stu-id="471fc-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="471fc-121">Ja</span><span class="sxs-lookup"><span data-stu-id="471fc-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="471fc-122">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="471fc-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="471fc-123">Ja </span><span class="sxs-lookup"><span data-stu-id="471fc-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="471fc-124">Ja</span><span class="sxs-lookup"><span data-stu-id="471fc-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471fc-125">Virtualisierung</span><span class="sxs-lookup"><span data-stu-id="471fc-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="471fc-126">Ja </span><span class="sxs-lookup"><span data-stu-id="471fc-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="471fc-127">Ja</span><span class="sxs-lookup"><span data-stu-id="471fc-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="471fc-128">Hochgradige Verfügbarkeit, Failover und Disaster Recovery</span><span class="sxs-lookup"><span data-stu-id="471fc-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="471fc-129">Ja</span><span class="sxs-lookup"><span data-stu-id="471fc-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="471fc-130">Nein</span><span class="sxs-lookup"><span data-stu-id="471fc-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

