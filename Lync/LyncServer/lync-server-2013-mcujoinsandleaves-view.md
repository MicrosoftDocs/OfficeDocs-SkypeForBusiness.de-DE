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
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="0c786-102">McuJoinsAndLeaves-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c786-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c786-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0c786-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0c786-104">Die McuJoinsAndLeaves-Ansicht speichert Informationen zu Benutzern, die an einem Konferenzserver teilnehmen und Informationen hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="0c786-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="0c786-105">Jeder Datensatz in dieser Ansicht enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder Leave-und Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="0c786-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="0c786-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0c786-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c786-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="0c786-107">Column</span></span></th>
<th><span data-ttu-id="0c786-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0c786-108">Data Type</span></span></th>
<th><span data-ttu-id="0c786-109">Details</span><span class="sxs-lookup"><span data-stu-id="0c786-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c786-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-111">datetime</span><span class="sxs-lookup"><span data-stu-id="0c786-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0c786-112">Uhrzeit der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="0c786-112">Time of conference instance.</span></span> <span data-ttu-id="0c786-113">Wird in Verbindung mit SessionIdSeq verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0c786-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="0c786-114">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0c786-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c786-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-116">int</span><span class="sxs-lookup"><span data-stu-id="0c786-116">int</span></span></p></td>
<td><p><span data-ttu-id="0c786-117">Die ID-Nummer zum Identifizieren der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="0c786-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="0c786-118">Wird in Verbindung mit SessionID-Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0c786-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="0c786-119">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0c786-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c786-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c786-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c786-122">Der URI des Konferenzservers, mit dem der Benutzer eine Verbindung hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="0c786-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c786-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c786-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c786-125">Der URI des Konferenzservers, mit dem der Benutzer eine Verbindung hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="0c786-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="0c786-126">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0c786-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c786-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0c786-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0c786-129">Der URI des Benutzers, dessen Konferenzserver teilnehmen/Leave-Informationen erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="0c786-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c786-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c786-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c786-132">Der Typ des URIs des Benutzers, dessen Konferenzserver teilnehmen/Leave-Informationen erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="0c786-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="0c786-133">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0c786-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c786-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c786-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c786-136">Der Mandant des Benutzers, dessen Konferenzserver teilnehmen/Leave-Informationen erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="0c786-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="0c786-137">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0c786-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c786-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c786-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0c786-140">Die Version des Clients, die von dem Benutzer verwendet wird, dessen Konferenzserver-Informationen aufgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="0c786-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c786-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-142">int</span><span class="sxs-lookup"><span data-stu-id="0c786-142">int</span></span></p></td>
<td><p><span data-ttu-id="0c786-143">Der Client, der von dem Benutzer verwendet wird, dessen Konferenzserver an-und Abgangs Informationen erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="0c786-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="0c786-144">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0c786-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c786-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0c786-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0c786-147">Der Name der Kategorie des Clients, die von dem Benutzer verwendet wird, dessen Konferenzserver-Informationen aufgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="0c786-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c786-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-149">int</span><span class="sxs-lookup"><span data-stu-id="0c786-149">int</span></span></p></td>
<td><p><span data-ttu-id="0c786-150">Kennzeichnet die Kombination von Benutzern/Geräten für Benutzer, die gleichzeitig an mehreren Geräten angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="0c786-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c786-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-152">bit</span><span class="sxs-lookup"><span data-stu-id="0c786-152">bit</span></span></p></td>
<td><p><span data-ttu-id="0c786-153">Bit, das darstellt, ob der Benutzer ein interner Benutzer ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="0c786-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c786-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-155">datetime</span><span class="sxs-lookup"><span data-stu-id="0c786-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="0c786-156">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="0c786-156">Time of session request.</span></span> <span data-ttu-id="0c786-157">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0c786-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="0c786-158">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0c786-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c786-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-160">int</span><span class="sxs-lookup"><span data-stu-id="0c786-160">int</span></span></p></td>
<td><p><span data-ttu-id="0c786-161">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0c786-161">ID number to identify the session.</span></span> <span data-ttu-id="0c786-162">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0c786-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="0c786-163">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0c786-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c786-164"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="0c786-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="0c786-166">SIP-Dialogfeld-ID der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0c786-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="0c786-167">Das Format lautet: Dialogfeld; from-Tag; to-Tag.</span><span class="sxs-lookup"><span data-stu-id="0c786-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c786-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-169">datetime</span><span class="sxs-lookup"><span data-stu-id="0c786-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="0c786-170">Zeitpunkt, zu dem der Benutzer dem Konferenzserver beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0c786-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c786-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="0c786-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0c786-172">datetime</span><span class="sxs-lookup"><span data-stu-id="0c786-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="0c786-173">Zeitpunkt, zu dem der Benutzer den Konferenzserver verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="0c786-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

