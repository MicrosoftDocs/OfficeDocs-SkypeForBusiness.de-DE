---
title: 'Lync Server 2013: McuJoinsAndLeaves-Tabelle'
description: 'Lync Server 2013: McuJoinsAndLeaves-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556501"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="6759a-103">McuJoinsAndLeaves-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6759a-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6759a-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6759a-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6759a-105">Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder-Leave und dem Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="6759a-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="6759a-106">Wenn ein Benutzer beispielsweise einer Konferenz beitreten, die Webkonferenzen und Audio/Video-Elemente umfasst, wird ein Datensatz für den Webkonferenz Beitritt dieses Benutzers erstellt, und es wird ein anderer Datensatz für die Teilnahme an Audio/Videokonferenzen des Benutzers erstellt.</span><span class="sxs-lookup"><span data-stu-id="6759a-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6759a-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="6759a-107">Column</span></span></th>
<th><span data-ttu-id="6759a-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6759a-108">Data Type</span></span></th>
<th><span data-ttu-id="6759a-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="6759a-109">Key/Index</span></span></th>
<th><span data-ttu-id="6759a-110">Details</span><span class="sxs-lookup"><span data-stu-id="6759a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6759a-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="6759a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="6759a-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="6759a-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6759a-114">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="6759a-114">Time of conference instance.</span></span> <span data-ttu-id="6759a-115">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6759a-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="6759a-116">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6759a-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6759a-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-118">int</span><span class="sxs-lookup"><span data-stu-id="6759a-118">int</span></span></p></td>
<td><p><span data-ttu-id="6759a-119">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="6759a-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6759a-120">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="6759a-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="6759a-121">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6759a-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="6759a-122">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6759a-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6759a-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-124">int</span><span class="sxs-lookup"><span data-stu-id="6759a-124">int</span></span></p></td>
<td><p><span data-ttu-id="6759a-125">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="6759a-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6759a-126">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6759a-126">Unique number identifying this user.</span></span> <span data-ttu-id="6759a-127">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6759a-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6759a-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-129">int</span><span class="sxs-lookup"><span data-stu-id="6759a-129">int</span></span></p></td>
<td><p><span data-ttu-id="6759a-130">Primary</span><span class="sxs-lookup"><span data-stu-id="6759a-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="6759a-131">Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, identifiziert McuUserInstance die Benutzer/Geräte-Kombination eindeutig.</span><span class="sxs-lookup"><span data-stu-id="6759a-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6759a-132"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-133">Bit</span><span class="sxs-lookup"><span data-stu-id="6759a-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6759a-134">Gibt an, ob der Benutzer von einem PSTN Beitritt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="6759a-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6759a-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-136">int</span><span class="sxs-lookup"><span data-stu-id="6759a-136">int</span></span></p></td>
<td><p><span data-ttu-id="6759a-137">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="6759a-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6759a-138">Eindeutige Zahl, die diesen Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6759a-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="6759a-139">Weitere Informationen finden Sie <a href="lync-server-2013-mcus-table.md">in der Tabelle "MCU" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6759a-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6759a-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-141">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="6759a-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="6759a-142">Fremd</span><span class="sxs-lookup"><span data-stu-id="6759a-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6759a-143">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="6759a-143">Time of session request.</span></span> <span data-ttu-id="6759a-144">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6759a-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6759a-145">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6759a-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6759a-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-147">int</span><span class="sxs-lookup"><span data-stu-id="6759a-147">int</span></span></p></td>
<td><p><span data-ttu-id="6759a-148">Fremd</span><span class="sxs-lookup"><span data-stu-id="6759a-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6759a-149">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6759a-149">ID number to identify the session.</span></span> <span data-ttu-id="6759a-150">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6759a-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6759a-151">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6759a-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6759a-152"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-153">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="6759a-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6759a-154">Die Zeit, zu der dieser Benutzer diesem Konferenzserver Beitritt.</span><span class="sxs-lookup"><span data-stu-id="6759a-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6759a-155"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-156">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="6759a-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6759a-157">Die Zeit, die dieser Benutzer diesen Konferenzserver verlässt.</span><span class="sxs-lookup"><span data-stu-id="6759a-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6759a-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="6759a-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6759a-159">int</span><span class="sxs-lookup"><span data-stu-id="6759a-159">int</span></span></p></td>
<td><p><span data-ttu-id="6759a-160">Fremd</span><span class="sxs-lookup"><span data-stu-id="6759a-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6759a-161">Bezeichner, der die Versionsnummer der Client Software angibt, die in der Konferenz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6759a-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="6759a-162">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6759a-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="6759a-163">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6759a-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

