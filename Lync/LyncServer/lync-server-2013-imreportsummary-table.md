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
ms.openlocfilehash: 619f502f3671d5f8bfe66af2b157a9729ab0e952
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="92faf-102">IMReportSummary-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92faf-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92faf-103">_**Letztes Änderungsstand des Themas:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="92faf-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="92faf-104">Das IMReportSummaryTable bietet einen Gesamtbericht zu den in einer Organisation gehaltenen Sofortnachrichtensitzungen.</span><span class="sxs-lookup"><span data-stu-id="92faf-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="92faf-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="92faf-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92faf-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="92faf-106">Column</span></span></th>
<th><span data-ttu-id="92faf-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="92faf-107">Data Type</span></span></th>
<th><span data-ttu-id="92faf-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="92faf-108">Key/Index</span></span></th>
<th><span data-ttu-id="92faf-109">Details</span><span class="sxs-lookup"><span data-stu-id="92faf-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92faf-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="92faf-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="92faf-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="92faf-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="92faf-112">Primary</span><span class="sxs-lookup"><span data-stu-id="92faf-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="92faf-113">Datum und Uhrzeit, an dem bzw. zu der die Chatsitzung begann.</span><span class="sxs-lookup"><span data-stu-id="92faf-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92faf-114"><strong>Zeitraum</strong></span><span class="sxs-lookup"><span data-stu-id="92faf-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="92faf-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="92faf-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="92faf-116">Primary</span><span class="sxs-lookup"><span data-stu-id="92faf-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92faf-117"><strong>Poolfqdn "</strong></span><span class="sxs-lookup"><span data-stu-id="92faf-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="92faf-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="92faf-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="92faf-119">Primary</span><span class="sxs-lookup"><span data-stu-id="92faf-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="92faf-120">Vollqualifizierter Domänenname des Pools, der die Sitzung hostet.</span><span class="sxs-lookup"><span data-stu-id="92faf-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92faf-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="92faf-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="92faf-122">int</span><span class="sxs-lookup"><span data-stu-id="92faf-122">int</span></span></p></td>
<td><p><span data-ttu-id="92faf-123">Primary</span><span class="sxs-lookup"><span data-stu-id="92faf-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="92faf-124">Priorität (z. B. dringend oder nicht dringend) des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="92faf-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="92faf-125">Prioritätsinformationen werden in der <a href="lync-server-2013-callpriorities-table.md">CallPriorities-Tabelle in lync Server 2013</a>gespeichert.</span><span class="sxs-lookup"><span data-stu-id="92faf-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92faf-126"><strong>SessionCount gespeichert</strong></span><span class="sxs-lookup"><span data-stu-id="92faf-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="92faf-127">bigint</span><span class="sxs-lookup"><span data-stu-id="92faf-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92faf-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="92faf-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="92faf-129">bigint</span><span class="sxs-lookup"><span data-stu-id="92faf-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92faf-130">Die Gesamtzahl der Chatnachrichten, die während der Sitzung ausgetauscht wurden.</span><span class="sxs-lookup"><span data-stu-id="92faf-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

