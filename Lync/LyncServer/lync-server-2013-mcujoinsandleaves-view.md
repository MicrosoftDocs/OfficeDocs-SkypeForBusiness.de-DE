---
title: 'Lync Server 2013: McuJoinsAndLeaves-Ansicht'
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
ms.openlocfilehash: c4f3f73606cfd05df17022770da7dcd1f5266b21
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="4ae2b-102">McuJoinsAndLeaves-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ae2b-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ae2b-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4ae2b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4ae2b-104">Die McuJoinsAndLeaves-Ansicht speichert Informationen zum Beitreten und Verlassen von Benutzern für einen Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="4ae2b-105">Jeder Datensatz in dieser Ansicht enthält Anrufdetails über eine Kombination aus einem Benutzer, der einer Konferenz beitritt oder sie verlässt, und einem Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="4ae2b-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ae2b-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="4ae2b-107">Column</span></span></th>
<th><span data-ttu-id="4ae2b-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4ae2b-108">Data Type</span></span></th>
<th><span data-ttu-id="4ae2b-109">Details</span><span class="sxs-lookup"><span data-stu-id="4ae2b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4ae2b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-112">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-112">Time of conference instance.</span></span> <span data-ttu-id="4ae2b-113">Wird zusammen mit SessionIdSeq verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="4ae2b-114">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ae2b-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ae2b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-116">int</span><span class="sxs-lookup"><span data-stu-id="4ae2b-116">int</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-117">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="4ae2b-118">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="4ae2b-119">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ae2b-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ae2b-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-122">Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ae2b-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ae2b-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-125">Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="4ae2b-126">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ae2b-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4ae2b-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-129">Der URI des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ae2b-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ae2b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-132">Der Typ des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="4ae2b-133">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ae2b-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ae2b-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-136">Der Mandant des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="4ae2b-137">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ae2b-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ae2b-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ae2b-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-140">Die Version des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-142">int</span><span class="sxs-lookup"><span data-stu-id="4ae2b-142">int</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-143">Der Client, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="4ae2b-144">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ae2b-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ae2b-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4ae2b-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-147">Der Name der Kategorie des Clients, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-149">int</span><span class="sxs-lookup"><span data-stu-id="4ae2b-149">int</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-150">Identifiziert die Kombination aus Benutzer/Gerät für Benutzer, die gleichzeitig auf mehreren Geräten angemeldet sind, eindeutig.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ae2b-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-152">Bit</span><span class="sxs-lookup"><span data-stu-id="4ae2b-152">bit</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-153">Bitwert, der angibt, ob ein Benutzer ein interner Benutzer ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-155">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4ae2b-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-156">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-156">Time of session request.</span></span> <span data-ttu-id="4ae2b-157">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="4ae2b-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="4ae2b-158">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ae2b-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ae2b-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-160">int</span><span class="sxs-lookup"><span data-stu-id="4ae2b-160">int</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-161">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-161">ID number to identify the session.</span></span> <span data-ttu-id="4ae2b-162">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="4ae2b-163">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4ae2b-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-164"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="4ae2b-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-p110">SIP-DialogID der Sitzung. Das Format lautet: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ae2b-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-169">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4ae2b-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-170">Zeitpunkt, zu dem der Benutzer dem Konferenzserver beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ae2b-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ae2b-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ae2b-172">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4ae2b-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ae2b-173">Zeitpunkt, zu dem der Benutzer den Konferenzserver verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="4ae2b-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

