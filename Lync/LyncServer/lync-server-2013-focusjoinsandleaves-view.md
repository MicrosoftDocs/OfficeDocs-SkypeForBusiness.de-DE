---
title: 'Lync Server 2013: FocusJoinsAndLeaves-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7cc1da4f5923a7c42e74c9069054863f1d99a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="cab74-102">FocusJoinsAndLeaves-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cab74-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cab74-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cab74-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cab74-104">In der FocusJoinsAndLeaves-Ansicht werden Informationen zu Join-und Leave-Informationen für eine Konferenz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cab74-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="cab74-105">Jede Konferenz wird in dieser Ansicht durch einen Datensatz dargestellt, der jedes Mal geschrieben wird, wenn ein Benutzer eine Konferenz anschließt und verlässt.</span><span class="sxs-lookup"><span data-stu-id="cab74-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="cab74-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cab74-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cab74-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="cab74-107">Column</span></span></th>
<th><span data-ttu-id="cab74-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="cab74-108">Data Type</span></span></th>
<th><span data-ttu-id="cab74-109">Details</span><span class="sxs-lookup"><span data-stu-id="cab74-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cab74-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-111">datetime</span><span class="sxs-lookup"><span data-stu-id="cab74-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="cab74-112">Uhrzeit der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="cab74-112">Time of conference instance.</span></span> <span data-ttu-id="cab74-113">Wird in Verbindung mit SessionIdSeq verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cab74-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="cab74-114">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cab74-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cab74-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-116">int</span><span class="sxs-lookup"><span data-stu-id="cab74-116">int</span></span></p></td>
<td><p><span data-ttu-id="cab74-117">Die ID-Nummer zum Identifizieren der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="cab74-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="cab74-118">Wird in Verbindung mit SessionID-Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cab74-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="cab74-119">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cab74-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cab74-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cab74-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cab74-122">Der URI des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="cab74-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cab74-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cab74-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cab74-125">Der Typ des URIs des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="cab74-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="cab74-126">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cab74-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cab74-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cab74-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cab74-129">Der Mandant des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="cab74-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="cab74-130">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cab74-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cab74-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="cab74-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="cab74-133">Eindeutiger Bezeichner des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="cab74-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cab74-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cab74-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cab74-136">Die Version des Clients, die von dem Benutzer verwendet wurde, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="cab74-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cab74-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-138">int</span><span class="sxs-lookup"><span data-stu-id="cab74-138">int</span></span></p></td>
<td><p><span data-ttu-id="cab74-139">Der Client, der von dem Benutzer verwendet wird, dessen Konferenz beitreten/Leave-Informationen erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="cab74-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="cab74-140">Weitere Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cab74-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cab74-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="cab74-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="cab74-143">Name der Kategorie des Clients, die von dem Benutzer verwendet wird, dessen Konferenz teilnehmen/-Abwesenheitsinformationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="cab74-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cab74-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-145">int</span><span class="sxs-lookup"><span data-stu-id="cab74-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cab74-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-147">bit</span><span class="sxs-lookup"><span data-stu-id="cab74-147">bit</span></span></p></td>
<td><p><span data-ttu-id="cab74-148">Bit, das darstellt, ob der Benutzer ein interner Benutzer ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="cab74-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cab74-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-150">datetime</span><span class="sxs-lookup"><span data-stu-id="cab74-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="cab74-151">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="cab74-151">Time of session request.</span></span> <span data-ttu-id="cab74-152">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cab74-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="cab74-153">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cab74-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cab74-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-155">int</span><span class="sxs-lookup"><span data-stu-id="cab74-155">int</span></span></p></td>
<td><p><span data-ttu-id="cab74-156">Wenn ein Benutzer gleichzeitig an mehreren Computern oder Geräten angemeldet ist, wird UserInstance verwendet, um die Kombination aus Benutzer und Gerät eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cab74-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cab74-157"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="cab74-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="cab74-159">SIP-Dialogfeld-ID der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cab74-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="cab74-160">Das Format lautet: Dialogfeld; from-Tag; to-Tag.</span><span class="sxs-lookup"><span data-stu-id="cab74-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cab74-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-162">datetime</span><span class="sxs-lookup"><span data-stu-id="cab74-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="cab74-163">Uhrzeit, zu der der Benutzer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cab74-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cab74-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-165">datetime</span><span class="sxs-lookup"><span data-stu-id="cab74-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="cab74-166">Der Zeitpunkt, zu dem der Benutzer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="cab74-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cab74-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="cab74-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="cab74-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cab74-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cab74-169">Rolle des Benutzers in der Konferenz, beispielsweise Referent oder Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="cab74-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

