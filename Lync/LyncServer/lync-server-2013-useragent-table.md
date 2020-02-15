---
title: 'Lync Server 2013: UserAgent-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ba13a18436c7a55ca68931ff2794fd584be84f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="1ba32-102">UserAgent-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ba32-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ba32-103">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="1ba32-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="1ba32-104">Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert wird, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="1ba32-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="1ba32-105">Jeder Datensatz in der Tabelle stellt einen Benutzer-Agent dar.</span><span class="sxs-lookup"><span data-stu-id="1ba32-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ba32-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="1ba32-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1ba32-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="1ba32-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1ba32-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="1ba32-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1ba32-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="1ba32-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ba32-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="1ba32-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="1ba32-111">int</span><span class="sxs-lookup"><span data-stu-id="1ba32-111">int</span></span></p></td>
<td><p><span data-ttu-id="1ba32-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1ba32-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ba32-113">Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1ba32-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba32-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="1ba32-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="1ba32-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ba32-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ba32-116">Eigen</span><span class="sxs-lookup"><span data-stu-id="1ba32-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="1ba32-117">Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="1ba32-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba32-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="1ba32-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="1ba32-119">smallint</span><span class="sxs-lookup"><span data-stu-id="1ba32-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ba32-120">1 ist Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="1ba32-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="1ba32-121">2 ist A/V-Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="1ba32-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="1ba32-122">4 ist lync.</span><span class="sxs-lookup"><span data-stu-id="1ba32-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="1ba32-123">8 ist IP-Telefon.</span><span class="sxs-lookup"><span data-stu-id="1ba32-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="1ba32-124">16 ist Live Meeting Konsole.</span><span class="sxs-lookup"><span data-stu-id="1ba32-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="1ba32-125">32 ist das Bereitstellungs Überprüfungs Tool (Thrombose).</span><span class="sxs-lookup"><span data-stu-id="1ba32-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="1ba32-126">64 ist lync auf Macintosh-Computern.</span><span class="sxs-lookup"><span data-stu-id="1ba32-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="1ba32-127">128 ist Office Communications Server 2007 R2 Attendant.</span><span class="sxs-lookup"><span data-stu-id="1ba32-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="1ba32-128">256 ist der Konferenzankündigungsdienst.</span><span class="sxs-lookup"><span data-stu-id="1ba32-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="1ba32-129">512 ist eine automatische Telefonzentrale für Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="1ba32-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="1ba32-130">1024 ist Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="1ba32-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="1ba32-131">2048 ist außerhalb der Sprachsteuerung.</span><span class="sxs-lookup"><span data-stu-id="1ba32-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

