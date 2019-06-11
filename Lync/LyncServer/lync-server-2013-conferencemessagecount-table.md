---
title: 'Lync Server 2013: ConferenceMessageCount-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2994f02bf087ef55edff6b2153e7504f881b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="9b05b-102">ConferenceMessageCount-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b05b-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b05b-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9b05b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9b05b-104">Jeder Datensatz in dieser Tabelle steht für einen Benutzer in einer Chat Konferenz und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9b05b-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="9b05b-105">Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9b05b-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b05b-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="9b05b-106">Column</span></span></th>
<th><span data-ttu-id="9b05b-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9b05b-107">Data Type</span></span></th>
<th><span data-ttu-id="9b05b-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="9b05b-108">Key/Index</span></span></th>
<th><span data-ttu-id="9b05b-109">Details</span><span class="sxs-lookup"><span data-stu-id="9b05b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b05b-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="9b05b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9b05b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9b05b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9b05b-112">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="9b05b-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9b05b-113">Uhrzeit der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="9b05b-113">Time of conference instance.</span></span> <span data-ttu-id="9b05b-114">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9b05b-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="9b05b-115">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9b05b-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b05b-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9b05b-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9b05b-117">int</span><span class="sxs-lookup"><span data-stu-id="9b05b-117">int</span></span></p></td>
<td><p><span data-ttu-id="9b05b-118">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="9b05b-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9b05b-119">Die ID-Nummer zum Identifizieren der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="9b05b-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="9b05b-120">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9b05b-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="9b05b-121">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9b05b-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b05b-122"><strong>UserID</strong></span><span class="sxs-lookup"><span data-stu-id="9b05b-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9b05b-123">int</span><span class="sxs-lookup"><span data-stu-id="9b05b-123">int</span></span></p></td>
<td><p><span data-ttu-id="9b05b-124">Fremd</span><span class="sxs-lookup"><span data-stu-id="9b05b-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9b05b-125">Eindeutige Nummer, die diesen Benutzer identifiziert, auf die <a href="lync-server-2013-users-table.md">in der Tabelle "Benutzer" in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9b05b-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b05b-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9b05b-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9b05b-127">smallint</span><span class="sxs-lookup"><span data-stu-id="9b05b-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b05b-128">Die Anzahl der Nachrichten, die dieser Benutzer während dieser Konferenz gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="9b05b-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

