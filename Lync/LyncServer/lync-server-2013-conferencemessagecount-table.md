---
title: 'Lync Server 2013: ConferenceMessageCount-Tabelle'
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
ms.openlocfilehash: e862209d384cd3927b6f8136b1a0d04b378e00c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="7cc01-102">ConferenceMessageCount-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cc01-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cc01-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7cc01-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7cc01-104">Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Chat Konferenz dar und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="7cc01-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="7cc01-105">Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7cc01-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cc01-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="7cc01-106">Column</span></span></th>
<th><span data-ttu-id="7cc01-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7cc01-107">Data Type</span></span></th>
<th><span data-ttu-id="7cc01-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="7cc01-108">Key/Index</span></span></th>
<th><span data-ttu-id="7cc01-109">Details</span><span class="sxs-lookup"><span data-stu-id="7cc01-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cc01-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="7cc01-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7cc01-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="7cc01-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7cc01-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="7cc01-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cc01-113">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="7cc01-113">Time of conference instance.</span></span> <span data-ttu-id="7cc01-114">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7cc01-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7cc01-115">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cc01-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cc01-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7cc01-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7cc01-117">int</span><span class="sxs-lookup"><span data-stu-id="7cc01-117">int</span></span></p></td>
<td><p><span data-ttu-id="7cc01-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="7cc01-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cc01-119">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="7cc01-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="7cc01-120">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7cc01-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7cc01-121">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cc01-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cc01-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="7cc01-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7cc01-123">int</span><span class="sxs-lookup"><span data-stu-id="7cc01-123">int</span></span></p></td>
<td><p><span data-ttu-id="7cc01-124">Fremd</span><span class="sxs-lookup"><span data-stu-id="7cc01-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cc01-125">Eindeutige Zahl, die diesen Benutzer identifiziert, auf die <a href="lync-server-2013-users-table.md">in der Tabelle users in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7cc01-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cc01-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7cc01-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7cc01-127">smallint</span><span class="sxs-lookup"><span data-stu-id="7cc01-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cc01-128">Die Anzahl der Nachrichten, die dieser Benutzer während dieser Konferenz gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="7cc01-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

