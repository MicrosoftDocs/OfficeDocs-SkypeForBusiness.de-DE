---
title: 'Lync Server 2013: Medientabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92bd1abb28b74fe7f2c46ad89d713a9b6244f4c3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="68026-102">Medientabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68026-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68026-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="68026-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="68026-p101">Jeder Datensatz steht für einen Medientyp, der in einer Peer-zu-Peer-Sitzung verwendet wird. Eine Sitzung wird durch mehrere Datensätze in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68026-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68026-p102">Die Media-Tabelle sollte nicht zur Berechnung der Mediendauer für eine Sitzung verwendet werden. Diese Tabelle enthält die Signaldetails für den Austausch von Mediendaten in einer Sitzung. Der Austausch von Mediendaten erfolgt durch die INVITE-Anforderung; "StartTime" gibt den Zeitpunkt an, zu dem die INVITE-Anforderung gesendet wurde. Der INVITE-Zeitpunkt gibt nicht notwendigerweise die Medienstartzeit an, da die Medien erst gestartet werden, nachdem der Sitzungsteilnehmer die Sitzung angenommen hat. "EndTime" bezeichnet in der Regel das Ende der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="68026-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68026-110">Spalte</span><span class="sxs-lookup"><span data-stu-id="68026-110">Column</span></span></th>
<th><span data-ttu-id="68026-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="68026-111">Data Type</span></span></th>
<th><span data-ttu-id="68026-112">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="68026-112">Key/Index</span></span></th>
<th><span data-ttu-id="68026-113">Details</span><span class="sxs-lookup"><span data-stu-id="68026-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68026-114"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="68026-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68026-115">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="68026-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="68026-116">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="68026-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="68026-117">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="68026-117">Time of session request.</span></span> <span data-ttu-id="68026-118">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="68026-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="68026-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68026-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68026-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="68026-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="68026-121">int</span><span class="sxs-lookup"><span data-stu-id="68026-121">int</span></span></p></td>
<td><p><span data-ttu-id="68026-122">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="68026-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="68026-123">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="68026-123">ID number to identify the session.</span></span> <span data-ttu-id="68026-124">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="68026-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="68026-125">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68026-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68026-126"><strong>Mediaid</strong></span><span class="sxs-lookup"><span data-stu-id="68026-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="68026-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="68026-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68026-128">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="68026-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="68026-129">Eindeutige Zahl, die diesen Medientyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="68026-129">Unique number identifying this media type.</span></span> <span data-ttu-id="68026-130">Weitere Informationen finden Sie <a href="lync-server-2013-medialist-table.md">in der medialist-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68026-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68026-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="68026-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68026-132">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="68026-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="68026-133">Primary</span><span class="sxs-lookup"><span data-stu-id="68026-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="68026-p106">Dies ist der Zeitpunkt, zu dem eine Medienanforderung gesendet wurde, jedoch nicht die tatsächliche Medienstartzeit. <strong>StartTime</strong> schließt die Sitzungseinrichtungszeit mit ein.</span><span class="sxs-lookup"><span data-stu-id="68026-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68026-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="68026-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68026-137">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="68026-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68026-138">Bezeichnet das Ende der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="68026-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

