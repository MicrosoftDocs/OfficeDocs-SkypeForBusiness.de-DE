---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="59bb6-102">tblComplianceParticipant in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59bb6-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59bb6-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="59bb6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="59bb6-104">tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.</span><span class="sxs-lookup"><span data-stu-id="59bb6-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="59bb6-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="59bb6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59bb6-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="59bb6-106">Column</span></span></th>
<th><span data-ttu-id="59bb6-107">Typ</span><span class="sxs-lookup"><span data-stu-id="59bb6-107">Type</span></span></th>
<th><span data-ttu-id="59bb6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59bb6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="59bb6-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="59bb6-110">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="59bb6-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="59bb6-111">Kanal Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="59bb6-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-112">UserID</span><span class="sxs-lookup"><span data-stu-id="59bb6-112">userId</span></span></p></td>
<td><p><span data-ttu-id="59bb6-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="59bb6-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="59bb6-114">Prinzipal-ID des Teilnehmers (entsprechend der Tabelle tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="59bb6-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="59bb6-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="59bb6-116">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="59bb6-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="59bb6-117">Zeitstempel des Joining-Ereignisses</span><span class="sxs-lookup"><span data-stu-id="59bb6-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="59bb6-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="59bb6-119">bigint</span><span class="sxs-lookup"><span data-stu-id="59bb6-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="59bb6-120">NULL, wenn der Teilnehmer noch verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="59bb6-120">Null if participant is still joined.</span></span> <span data-ttu-id="59bb6-121">Der Zeitstempel des Kanals, der das Ereignis verlässt, wenn nicht NULL.</span><span class="sxs-lookup"><span data-stu-id="59bb6-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="59bb6-122">Diese Einträge werden schließlich entfernt, wenn alle Übersetzer das Ereignis verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="59bb6-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-123">userUri</span><span class="sxs-lookup"><span data-stu-id="59bb6-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="59bb6-124">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="59bb6-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="59bb6-125">Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="59bb6-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-126">ServerID</span><span class="sxs-lookup"><span data-stu-id="59bb6-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="59bb6-127">int</span><span class="sxs-lookup"><span data-stu-id="59bb6-127">int</span></span></p></td>
<td><p><span data-ttu-id="59bb6-128">Serveridentität (wie in der Tabelle tblServerIdentity. Server-ID).</span><span class="sxs-lookup"><span data-stu-id="59bb6-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-129">SessionID</span><span class="sxs-lookup"><span data-stu-id="59bb6-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="59bb6-130">bigint</span><span class="sxs-lookup"><span data-stu-id="59bb6-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="59bb6-131">Server Sitzung.</span><span class="sxs-lookup"><span data-stu-id="59bb6-131">Server session.</span></span> <span data-ttu-id="59bb6-132">Hierbei handelt es sich um eine Zufallszahl, die bei jedem Start eines Chat-Diensts generiert wird.</span><span class="sxs-lookup"><span data-stu-id="59bb6-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="59bb6-133">Sie wird zur Unterscheidung von Sitzungen zum Zweck der Identifizierung verwaister Teilnehmer verwendet.</span><span class="sxs-lookup"><span data-stu-id="59bb6-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="59bb6-134">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="59bb6-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59bb6-135">Spalte</span><span class="sxs-lookup"><span data-stu-id="59bb6-135">Column</span></span></th>
<th><span data-ttu-id="59bb6-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59bb6-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-137">&lt;channelUri, UserID, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="59bb6-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="59bb6-138">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="59bb6-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

