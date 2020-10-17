---
title: 'Lync Server 2013: ConferenceMessageCount-Tabelle'
description: 'Lync Server 2013: ConferenceMessageCount-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561621"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="dd10b-103">ConferenceMessageCount-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd10b-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd10b-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="dd10b-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="dd10b-105">Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Chat Konferenz dar und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="dd10b-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="dd10b-106">Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dd10b-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd10b-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="dd10b-107">Column</span></span></th>
<th><span data-ttu-id="dd10b-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="dd10b-108">Data Type</span></span></th>
<th><span data-ttu-id="dd10b-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="dd10b-109">Key/Index</span></span></th>
<th><span data-ttu-id="dd10b-110">Details</span><span class="sxs-lookup"><span data-stu-id="dd10b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd10b-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="dd10b-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd10b-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="dd10b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="dd10b-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="dd10b-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd10b-114">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="dd10b-114">Time of conference instance.</span></span> <span data-ttu-id="dd10b-115">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="dd10b-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="dd10b-116">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dd10b-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd10b-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dd10b-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dd10b-118">int</span><span class="sxs-lookup"><span data-stu-id="dd10b-118">int</span></span></p></td>
<td><p><span data-ttu-id="dd10b-119">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="dd10b-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd10b-120">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="dd10b-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="dd10b-121">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="dd10b-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="dd10b-122">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dd10b-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd10b-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="dd10b-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd10b-124">int</span><span class="sxs-lookup"><span data-stu-id="dd10b-124">int</span></span></p></td>
<td><p><span data-ttu-id="dd10b-125">Fremd</span><span class="sxs-lookup"><span data-stu-id="dd10b-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd10b-126">Eindeutige Zahl, die diesen Benutzer identifiziert, auf die <a href="lync-server-2013-users-table.md">in der Tabelle users in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dd10b-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd10b-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="dd10b-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="dd10b-128">smallint</span><span class="sxs-lookup"><span data-stu-id="dd10b-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dd10b-129">Die Anzahl der Nachrichten, die dieser Benutzer während dieser Konferenz gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="dd10b-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

