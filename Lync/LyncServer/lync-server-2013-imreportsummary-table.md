---
title: 'Lync Server 2013: IMReportSummary-Tabelle'
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
ms.openlocfilehash: a7a6be73d31892b5a0d5a3a5b10ad136f92afbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="02cf5-102">IMReportSummary-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02cf5-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02cf5-103">_**Letztes Änderungsdatum des Themas:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="02cf5-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="02cf5-104">Der IMReportSummaryTable stellt einen Gesamtbericht zu den Chat-Sitzungen bereit, die in einer Organisation abgehalten werden.</span><span class="sxs-lookup"><span data-stu-id="02cf5-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="02cf5-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="02cf5-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02cf5-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="02cf5-106">Column</span></span></th>
<th><span data-ttu-id="02cf5-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="02cf5-107">Data Type</span></span></th>
<th><span data-ttu-id="02cf5-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="02cf5-108">Key/Index</span></span></th>
<th><span data-ttu-id="02cf5-109">Details</span><span class="sxs-lookup"><span data-stu-id="02cf5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02cf5-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="02cf5-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="02cf5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="02cf5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="02cf5-112">Primary</span><span class="sxs-lookup"><span data-stu-id="02cf5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="02cf5-113">Das Datum und die Uhrzeit, zu der die Sofortnachrichtensitzung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="02cf5-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02cf5-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="02cf5-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="02cf5-115">Zeichen (1)</span><span class="sxs-lookup"><span data-stu-id="02cf5-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="02cf5-116">Primary</span><span class="sxs-lookup"><span data-stu-id="02cf5-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02cf5-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="02cf5-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="02cf5-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="02cf5-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="02cf5-119">Primary</span><span class="sxs-lookup"><span data-stu-id="02cf5-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="02cf5-120">Vollständig qualifizierter Domänenname des Pools, der die Sitzung hostet.</span><span class="sxs-lookup"><span data-stu-id="02cf5-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02cf5-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="02cf5-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="02cf5-122">int</span><span class="sxs-lookup"><span data-stu-id="02cf5-122">int</span></span></p></td>
<td><p><span data-ttu-id="02cf5-123">Primary</span><span class="sxs-lookup"><span data-stu-id="02cf5-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="02cf5-124">Priorität (beispielsweise dringende oder nicht dringende) des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="02cf5-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="02cf5-125">Prioritätsinformationen werden in der <a href="lync-server-2013-callpriorities-table.md">CallPriorities-Tabelle in lync Server 2013</a>gespeichert.</span><span class="sxs-lookup"><span data-stu-id="02cf5-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02cf5-126"><strong>SessionCount gespeichert</strong></span><span class="sxs-lookup"><span data-stu-id="02cf5-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="02cf5-127">bigint</span><span class="sxs-lookup"><span data-stu-id="02cf5-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02cf5-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="02cf5-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="02cf5-129">bigint</span><span class="sxs-lookup"><span data-stu-id="02cf5-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="02cf5-130">Die Gesamtzahl der während der Sitzung ausgetauschten Sofortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="02cf5-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

