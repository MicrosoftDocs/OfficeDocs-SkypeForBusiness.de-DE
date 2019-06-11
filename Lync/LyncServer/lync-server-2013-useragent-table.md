---
title: 'Lync Server 2013: UserAgent-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09bb2e3a71f81014bcb08952c03b59c93ac6a62f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="d7f41-102">UserAgent-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7f41-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7f41-103">_**Letztes Änderungsdatum des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="d7f41-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="d7f41-104">Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="d7f41-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d7f41-105">Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent</span><span class="sxs-lookup"><span data-stu-id="d7f41-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7f41-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="d7f41-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d7f41-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="d7f41-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d7f41-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="d7f41-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d7f41-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d7f41-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7f41-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="d7f41-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f41-111">int</span><span class="sxs-lookup"><span data-stu-id="d7f41-111">int</span></span></p></td>
<td><p><span data-ttu-id="d7f41-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d7f41-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d7f41-113">Eindeutige Nummer, die diesen Benutzer-Agent kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d7f41-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f41-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="d7f41-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f41-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7f41-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7f41-116">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="d7f41-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="d7f41-117">Benutzer-Agent-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d7f41-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f41-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="d7f41-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f41-119">smallint</span><span class="sxs-lookup"><span data-stu-id="d7f41-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f41-120">1 ist ein Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="d7f41-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="d7f41-121">2 ist ein/V-Konferenz Server.</span><span class="sxs-lookup"><span data-stu-id="d7f41-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="d7f41-122">4 ist lync.</span><span class="sxs-lookup"><span data-stu-id="d7f41-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="d7f41-123">8 ist IP Phone.</span><span class="sxs-lookup"><span data-stu-id="d7f41-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="d7f41-124">16 ist eine Live Meeting-Konsole.</span><span class="sxs-lookup"><span data-stu-id="d7f41-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="d7f41-125">32 ist ein Bereitstellungs Überprüfungs Tool (Thrombose).</span><span class="sxs-lookup"><span data-stu-id="d7f41-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="d7f41-126">64 ist lync auf Macintosh-Computern.</span><span class="sxs-lookup"><span data-stu-id="d7f41-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="d7f41-127">128 ist Office Communications Server 2007 R2 Attendant.</span><span class="sxs-lookup"><span data-stu-id="d7f41-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="d7f41-128">256 ist ein Konferenzankündigungsdienst.</span><span class="sxs-lookup"><span data-stu-id="d7f41-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="d7f41-129">512 ist eine automatische Konferenzzentrale.</span><span class="sxs-lookup"><span data-stu-id="d7f41-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="d7f41-130">1024 ist eine reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="d7f41-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="d7f41-131">2048 ist außerhalb der Sprachsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d7f41-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

