---
title: 'Lync Server 2013: IMReportSummary-Tabelle'
description: 'Lync Server 2013: IMReportSummary-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfafa81d1605845b29a3627321fcbc0f72ca7ac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547741"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="5ea5d-103">IMReportSummary-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea5d-103">IMReportSummary table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea5d-104">_**Letztes Änderungsstand des Themas:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="5ea5d-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="5ea5d-105">Das IMReportSummaryTable bietet einen Gesamtbericht zu den in einer Organisation gehaltenen Sofortnachrichtensitzungen.</span><span class="sxs-lookup"><span data-stu-id="5ea5d-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="5ea5d-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5ea5d-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea5d-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="5ea5d-107">Column</span></span></th>
<th><span data-ttu-id="5ea5d-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5ea5d-108">Data Type</span></span></th>
<th><span data-ttu-id="5ea5d-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="5ea5d-109">Key/Index</span></span></th>
<th><span data-ttu-id="5ea5d-110">Details</span><span class="sxs-lookup"><span data-stu-id="5ea5d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea5d-111"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ea5d-111"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea5d-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="5ea5d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5ea5d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea5d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ea5d-114">Datum und Uhrzeit, an dem bzw. zu der die Chatsitzung begann.</span><span class="sxs-lookup"><span data-stu-id="5ea5d-114">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea5d-115"><strong>Zeitraum</strong></span><span class="sxs-lookup"><span data-stu-id="5ea5d-115"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea5d-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="5ea5d-116">char(1)</span></span></p></td>
<td><p><span data-ttu-id="5ea5d-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea5d-117">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea5d-118"><strong>Poolfqdn "</strong></span><span class="sxs-lookup"><span data-stu-id="5ea5d-118"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea5d-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="5ea5d-119">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="5ea5d-120">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea5d-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ea5d-121">Vollqualifizierter Domänenname des Pools, der die Sitzung hostet.</span><span class="sxs-lookup"><span data-stu-id="5ea5d-121">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea5d-122"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="5ea5d-122"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea5d-123">int</span><span class="sxs-lookup"><span data-stu-id="5ea5d-123">int</span></span></p></td>
<td><p><span data-ttu-id="5ea5d-124">Primary</span><span class="sxs-lookup"><span data-stu-id="5ea5d-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ea5d-125">Priorität (z. B. dringend oder nicht dringend) des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="5ea5d-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="5ea5d-126">Prioritätsinformationen werden in der <a href="lync-server-2013-callpriorities-table.md">CallPriorities-Tabelle in lync Server 2013</a>gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5ea5d-126">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ea5d-127"><strong>SessionCount gespeichert</strong></span><span class="sxs-lookup"><span data-stu-id="5ea5d-127"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea5d-128">bigint</span><span class="sxs-lookup"><span data-stu-id="5ea5d-128">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea5d-129"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="5ea5d-129"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5ea5d-130">bigint</span><span class="sxs-lookup"><span data-stu-id="5ea5d-130">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ea5d-131">Die Gesamtzahl der Chatnachrichten, die während der Sitzung ausgetauscht wurden.</span><span class="sxs-lookup"><span data-stu-id="5ea5d-131">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

