---
title: 'Lync Server 2013: Media-Tabelle'
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
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="d34bb-102">Media-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d34bb-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d34bb-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d34bb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d34bb-104">Jeder Datensatz steht für einen in einer Peer-to-Peer-Sitzung verwendeten Medientyp.</span><span class="sxs-lookup"><span data-stu-id="d34bb-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="d34bb-105">Eine Sitzung wird von mehreren Datensätzen in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d34bb-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d34bb-106">Die Medientabelle sollte nicht verwendet werden, um die Mediendauer einer Sitzung zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="d34bb-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="d34bb-107">Diese Tabelle enthält die Signalisierungs Details von Medienaustausch in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d34bb-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="d34bb-108">Der Medienaustausch erfolgt über die Einladungs Anfrage, und Startzeit gibt an, wie lange die Einladung gesendet wurde. Die Einladungs Zeit bedeutet nicht unbedingt die Startzeit des Mediums, da Medien erst gestartet werden, nachdem der Sitzungs nehmer die Sitzung akzeptiert hat.</span><span class="sxs-lookup"><span data-stu-id="d34bb-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="d34bb-109">Die EndTime bedeutet normalerweise die Endzeit dieser Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d34bb-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="d34bb-110">Spalte</span><span class="sxs-lookup"><span data-stu-id="d34bb-110">Column</span></span></th>
<th><span data-ttu-id="d34bb-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d34bb-111">Data Type</span></span></th>
<th><span data-ttu-id="d34bb-112">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="d34bb-112">Key/Index</span></span></th>
<th><span data-ttu-id="d34bb-113">Details</span><span class="sxs-lookup"><span data-stu-id="d34bb-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d34bb-114"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="d34bb-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d34bb-115">datetime</span><span class="sxs-lookup"><span data-stu-id="d34bb-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="d34bb-116">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="d34bb-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d34bb-117">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="d34bb-117">Time of session request.</span></span> <span data-ttu-id="d34bb-118">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d34bb-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d34bb-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d34bb-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d34bb-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d34bb-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d34bb-121">int</span><span class="sxs-lookup"><span data-stu-id="d34bb-121">int</span></span></p></td>
<td><p><span data-ttu-id="d34bb-122">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="d34bb-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d34bb-123">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d34bb-123">ID number to identify the session.</span></span> <span data-ttu-id="d34bb-124">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d34bb-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d34bb-125">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d34bb-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d34bb-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="d34bb-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="d34bb-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="d34bb-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d34bb-128">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="d34bb-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d34bb-129">Eindeutige Nummer, die diesen Medientyp kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d34bb-129">Unique number identifying this media type.</span></span> <span data-ttu-id="d34bb-130">Weitere Informationen finden Sie <a href="lync-server-2013-medialist-table.md">in der Tabelle medialist in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d34bb-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d34bb-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="d34bb-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d34bb-132">datetime</span><span class="sxs-lookup"><span data-stu-id="d34bb-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="d34bb-133">Primary</span><span class="sxs-lookup"><span data-stu-id="d34bb-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="d34bb-134">Dies ist der Zeitpunkt, zu dem eine Medienanfrage gesendet wurde, nicht die Startzeit des realen Mediums.</span><span class="sxs-lookup"><span data-stu-id="d34bb-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="d34bb-135"><strong>Startzeit</strong> umfasst die Rüstzeit für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d34bb-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d34bb-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d34bb-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d34bb-137">datetime</span><span class="sxs-lookup"><span data-stu-id="d34bb-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d34bb-138">Dies ist die Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d34bb-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

