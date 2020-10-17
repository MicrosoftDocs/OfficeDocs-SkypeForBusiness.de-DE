---
title: 'Lync Server 2013: McuJoinsAndLeaves-Ansicht'
description: 'Lync Server 2013: McuJoinsAndLeaves-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556491"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="c4e04-103">McuJoinsAndLeaves-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4e04-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4e04-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c4e04-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c4e04-105">Die McuJoinsAndLeaves-Ansicht speichert Informationen zum Beitreten und Verlassen von Benutzern für einen Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="c4e04-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="c4e04-106">Jeder Datensatz in dieser Ansicht enthält Anrufdetails über eine Kombination aus einem Benutzer, der einer Konferenz beitritt oder sie verlässt, und einem Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="c4e04-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="c4e04-107">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c4e04-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4e04-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="c4e04-108">Column</span></span></th>
<th><span data-ttu-id="c4e04-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c4e04-109">Data Type</span></span></th>
<th><span data-ttu-id="c4e04-110">Details</span><span class="sxs-lookup"><span data-stu-id="c4e04-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c4e04-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4e04-113">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="c4e04-113">Time of conference instance.</span></span> <span data-ttu-id="c4e04-114">Wird zusammen mit SessionIdSeq verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c4e04-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="c4e04-115">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4e04-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e04-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-117">int</span><span class="sxs-lookup"><span data-stu-id="c4e04-117">int</span></span></p></td>
<td><p><span data-ttu-id="c4e04-118">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="c4e04-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="c4e04-119">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c4e04-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="c4e04-120">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4e04-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4e04-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4e04-123">Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="c4e04-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e04-124"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4e04-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4e04-126">Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="c4e04-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="c4e04-127">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4e04-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-129">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c4e04-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c4e04-130">Der URI des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c4e04-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e04-131"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4e04-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4e04-133">Der Typ des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c4e04-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c4e04-134">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4e04-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-135"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4e04-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4e04-137">Der Mandant des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c4e04-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c4e04-138">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4e04-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e04-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4e04-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4e04-141">Die Version des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c4e04-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-142"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-143">int</span><span class="sxs-lookup"><span data-stu-id="c4e04-143">int</span></span></p></td>
<td><p><span data-ttu-id="c4e04-144">Der Client, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c4e04-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c4e04-145">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4e04-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e04-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-147">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c4e04-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c4e04-148">Der Name der Kategorie des Clients, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c4e04-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-150">int</span><span class="sxs-lookup"><span data-stu-id="c4e04-150">int</span></span></p></td>
<td><p><span data-ttu-id="c4e04-151">Identifiziert die Kombination aus Benutzer/Gerät für Benutzer, die gleichzeitig auf mehreren Geräten angemeldet sind, eindeutig.</span><span class="sxs-lookup"><span data-stu-id="c4e04-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e04-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-153">Bit</span><span class="sxs-lookup"><span data-stu-id="c4e04-153">bit</span></span></p></td>
<td><p><span data-ttu-id="c4e04-154">Bitwert, der angibt, ob ein Benutzer ein interner Benutzer ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c4e04-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-156">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c4e04-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4e04-157">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="c4e04-157">Time of session request.</span></span> <span data-ttu-id="c4e04-158">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="c4e04-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c4e04-159">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4e04-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e04-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-161">int</span><span class="sxs-lookup"><span data-stu-id="c4e04-161">int</span></span></p></td>
<td><p><span data-ttu-id="c4e04-162">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c4e04-162">ID number to identify the session.</span></span> <span data-ttu-id="c4e04-163">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c4e04-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c4e04-164">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4e04-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-165"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-166">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="c4e04-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c4e04-p110">SIP-DialogID der Sitzung. Das Format lautet: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="c4e04-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e04-169"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-170">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c4e04-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4e04-171">Zeitpunkt, zu dem der Benutzer dem Konferenzserver beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c4e04-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e04-172"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4e04-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e04-173">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c4e04-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4e04-174">Zeitpunkt, zu dem der Benutzer den Konferenzserver verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="c4e04-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

