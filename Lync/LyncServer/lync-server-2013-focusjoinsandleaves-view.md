---
title: 'Lync Server 2013: FocusJoinsAndLeaves-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="c1db9-102">FocusJoinsAndLeaves-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1db9-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1db9-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c1db9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c1db9-104">In der FocusJoinsAndLeaves-Ansicht werden Informationen zu Join-und Leave-Informationen für eine Konferenz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c1db9-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="c1db9-105">Jede Konferenz wird in dieser Ansicht durch einen Datensatz dargestellt, der jedes Mal geschrieben wird, wenn ein Benutzer eine Konferenz anschließt und verlässt.</span><span class="sxs-lookup"><span data-stu-id="c1db9-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="c1db9-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c1db9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1db9-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="c1db9-107">Column</span></span></th>
<th><span data-ttu-id="c1db9-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c1db9-108">Data Type</span></span></th>
<th><span data-ttu-id="c1db9-109">Details</span><span class="sxs-lookup"><span data-stu-id="c1db9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c1db9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c1db9-112">Uhrzeit der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="c1db9-112">Time of conference instance.</span></span> <span data-ttu-id="c1db9-113">Wird in Verbindung mit SessionIdSeq verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c1db9-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="c1db9-114">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c1db9-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1db9-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-116">int</span><span class="sxs-lookup"><span data-stu-id="c1db9-116">int</span></span></p></td>
<td><p><span data-ttu-id="c1db9-117">Die ID-Nummer zum Identifizieren der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="c1db9-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="c1db9-118">Wird in Verbindung mit SessionID-Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c1db9-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="c1db9-119">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c1db9-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c1db9-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c1db9-122">Der URI des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c1db9-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1db9-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1db9-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1db9-125">Der Typ des URIs des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c1db9-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="c1db9-126">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c1db9-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1db9-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1db9-129">Der Mandant des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="c1db9-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="c1db9-130">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c1db9-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1db9-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c1db9-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c1db9-133">Eindeutiger Bezeichner des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c1db9-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1db9-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1db9-136">Die Version des Clients, die von dem Benutzer verwendet wurde, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c1db9-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1db9-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-138">int</span><span class="sxs-lookup"><span data-stu-id="c1db9-138">int</span></span></p></td>
<td><p><span data-ttu-id="c1db9-139">Der Client, der von dem Benutzer verwendet wird, dessen Konferenz beitreten/Leave-Informationen erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="c1db9-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="c1db9-140">Weitere Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c1db9-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c1db9-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c1db9-143">Name der Kategorie des Clients, die von dem Benutzer verwendet wird, dessen Konferenz teilnehmen/-Abwesenheitsinformationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c1db9-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1db9-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-145">int</span><span class="sxs-lookup"><span data-stu-id="c1db9-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-147">bit</span><span class="sxs-lookup"><span data-stu-id="c1db9-147">bit</span></span></p></td>
<td><p><span data-ttu-id="c1db9-148">Bit, das darstellt, ob der Benutzer ein interner Benutzer ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c1db9-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1db9-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-150">datetime</span><span class="sxs-lookup"><span data-stu-id="c1db9-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="c1db9-151">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="c1db9-151">Time of session request.</span></span> <span data-ttu-id="c1db9-152">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c1db9-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c1db9-153">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c1db9-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-155">int</span><span class="sxs-lookup"><span data-stu-id="c1db9-155">int</span></span></p></td>
<td><p><span data-ttu-id="c1db9-156">Wenn ein Benutzer gleichzeitig an mehreren Computern oder Geräten angemeldet ist, wird UserInstance verwendet, um die Kombination aus Benutzer und Gerät eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c1db9-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1db9-157"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="c1db9-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c1db9-159">SIP-Dialogfeld-ID der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c1db9-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="c1db9-160">Das Format lautet: Dialogfeld; from-Tag; to-Tag.</span><span class="sxs-lookup"><span data-stu-id="c1db9-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-162">datetime</span><span class="sxs-lookup"><span data-stu-id="c1db9-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="c1db9-163">Uhrzeit, zu der der Benutzer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c1db9-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1db9-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-165">datetime</span><span class="sxs-lookup"><span data-stu-id="c1db9-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="c1db9-166">Der Zeitpunkt, zu dem der Benutzer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="c1db9-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1db9-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="c1db9-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="c1db9-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1db9-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1db9-169">Rolle des Benutzers in der Konferenz, beispielsweise Referent oder Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="c1db9-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

