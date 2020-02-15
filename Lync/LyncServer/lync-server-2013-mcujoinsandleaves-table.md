---
title: 'Lync Server 2013: McuJoinsAndLeaves-Tabelle'
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
ms.openlocfilehash: a398c0b860cd5b4043ee766b702b1b7e8e904552
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="4eb2c-102">McuJoinsAndLeaves-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eb2c-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eb2c-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4eb2c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4eb2c-104">Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder-Leave und dem Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="4eb2c-105">Wenn ein Benutzer beispielsweise einer Konferenz beitreten, die Webkonferenzen und Audio/Video-Elemente umfasst, wird ein Datensatz für den Webkonferenz Beitritt dieses Benutzers erstellt, und es wird ein anderer Datensatz für die Teilnahme an Audio/Videokonferenzen des Benutzers erstellt.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eb2c-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="4eb2c-106">Column</span></span></th>
<th><span data-ttu-id="4eb2c-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4eb2c-107">Data Type</span></span></th>
<th><span data-ttu-id="4eb2c-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="4eb2c-108">Key/Index</span></span></th>
<th><span data-ttu-id="4eb2c-109">Details</span><span class="sxs-lookup"><span data-stu-id="4eb2c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eb2c-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4eb2c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="4eb2c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-113">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-113">Time of conference instance.</span></span> <span data-ttu-id="4eb2c-114">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="4eb2c-115">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4eb2c-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb2c-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-117">int</span><span class="sxs-lookup"><span data-stu-id="4eb2c-117">int</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="4eb2c-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-119">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="4eb2c-120">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="4eb2c-121">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4eb2c-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb2c-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-123">int</span><span class="sxs-lookup"><span data-stu-id="4eb2c-123">int</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-124">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="4eb2c-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-125">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-125">Unique number identifying this user.</span></span> <span data-ttu-id="4eb2c-126">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4eb2c-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb2c-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-128">int</span><span class="sxs-lookup"><span data-stu-id="4eb2c-128">int</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-129">Primary</span><span class="sxs-lookup"><span data-stu-id="4eb2c-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-130">Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, identifiziert McuUserInstance die Benutzer/Geräte-Kombination eindeutig.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb2c-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-132">Bit</span><span class="sxs-lookup"><span data-stu-id="4eb2c-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4eb2c-133">Gibt an, ob der Benutzer von einem PSTN Beitritt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb2c-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-135">int</span><span class="sxs-lookup"><span data-stu-id="4eb2c-135">int</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-136">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="4eb2c-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-137">Eindeutige Zahl, die diesen Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="4eb2c-138">Weitere Informationen finden Sie <a href="lync-server-2013-mcus-table.md">in der Tabelle "MCU" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4eb2c-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb2c-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-140">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4eb2c-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-141">Fremd</span><span class="sxs-lookup"><span data-stu-id="4eb2c-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-142">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-142">Time of session request.</span></span> <span data-ttu-id="4eb2c-143">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4eb2c-144">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4eb2c-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb2c-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-146">int</span><span class="sxs-lookup"><span data-stu-id="4eb2c-146">int</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-147">Fremd</span><span class="sxs-lookup"><span data-stu-id="4eb2c-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-148">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-148">ID number to identify the session.</span></span> <span data-ttu-id="4eb2c-149">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4eb2c-150">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4eb2c-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb2c-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-152">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4eb2c-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4eb2c-153">Die Zeit, zu der dieser Benutzer diesem Konferenzserver Beitritt.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb2c-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-155">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4eb2c-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4eb2c-156">Die Zeit, die dieser Benutzer diesen Konferenzserver verlässt.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb2c-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="4eb2c-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4eb2c-158">int</span><span class="sxs-lookup"><span data-stu-id="4eb2c-158">int</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-159">Fremd</span><span class="sxs-lookup"><span data-stu-id="4eb2c-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4eb2c-160">Bezeichner, der die Versionsnummer der Client Software angibt, die in der Konferenz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="4eb2c-161">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4eb2c-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4eb2c-162">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4eb2c-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

