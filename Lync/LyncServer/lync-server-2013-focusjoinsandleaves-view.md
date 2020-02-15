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
ms.openlocfilehash: 8c5c10cc90064e9ed3237dcd4cd4cbed1021d1b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="b96c4-102">FocusJoinsAndLeaves-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b96c4-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b96c4-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b96c4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b96c4-104">In der FocusJoinsAndLeaves-Ansicht werden Informationen zu Join-und Leave-Informationen für eine Konferenz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b96c4-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="b96c4-105">Jede Konferenz wird in dieser Ansicht durch einen Datensatz dargestellt, der jedes Mal geschrieben wird, wenn ein Benutzer einer Konferenz Beitritt und diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="b96c4-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="b96c4-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b96c4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b96c4-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="b96c4-107">Column</span></span></th>
<th><span data-ttu-id="b96c4-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b96c4-108">Data Type</span></span></th>
<th><span data-ttu-id="b96c4-109">Details</span><span class="sxs-lookup"><span data-stu-id="b96c4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b96c4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b96c4-112">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="b96c4-112">Time of conference instance.</span></span> <span data-ttu-id="b96c4-113">Wird zusammen mit SessionIdSeq verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b96c4-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="b96c4-114">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b96c4-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c4-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-116">int</span><span class="sxs-lookup"><span data-stu-id="b96c4-116">int</span></span></p></td>
<td><p><span data-ttu-id="b96c4-117">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="b96c4-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="b96c4-118">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b96c4-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="b96c4-119">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b96c4-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b96c4-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b96c4-122">URI des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="b96c4-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c4-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b96c4-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b96c4-125">Typ des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="b96c4-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b96c4-126">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b96c4-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b96c4-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b96c4-129">Mandant des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="b96c4-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b96c4-130">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b96c4-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c4-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b96c4-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b96c4-133">Eindeutiger Bezeichner des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="b96c4-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b96c4-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b96c4-136">Version des Client des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="b96c4-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c4-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-138">int</span><span class="sxs-lookup"><span data-stu-id="b96c4-138">int</span></span></p></td>
<td><p><span data-ttu-id="b96c4-139">Client, der vom Benutzer verwendet wurde, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="b96c4-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b96c4-140">Weitere Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b96c4-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b96c4-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b96c4-143">Name der Kategorie des Clients des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="b96c4-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c4-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-145">int</span><span class="sxs-lookup"><span data-stu-id="b96c4-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-147">Bit</span><span class="sxs-lookup"><span data-stu-id="b96c4-147">bit</span></span></p></td>
<td><p><span data-ttu-id="b96c4-148">Bitwert, der angibt, ob ein Benutzer ein interner Benutzer ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="b96c4-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c4-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-150">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b96c4-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="b96c4-151">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="b96c4-151">Time of session request.</span></span> <span data-ttu-id="b96c4-152">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="b96c4-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b96c4-153">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b96c4-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-155">int</span><span class="sxs-lookup"><span data-stu-id="b96c4-155">int</span></span></p></td>
<td><p><span data-ttu-id="b96c4-156">Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, wird UserInstance verwendet, um die Benutzer/Geräte-Kombination eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b96c4-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c4-157"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b96c4-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b96c4-p108">SIP-DialogID der Sitzung. Das Format lautet: dialog;from-tag;to-tag.</span><span class="sxs-lookup"><span data-stu-id="b96c4-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-162">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b96c4-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="b96c4-163">Zeitpunkt, zu dem dieser Benutzer der Konferenz beitrat.</span><span class="sxs-lookup"><span data-stu-id="b96c4-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c4-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-165">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b96c4-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="b96c4-166">Zeitpunkt, zu dem dieser Benutzer die Konferenz verließ.</span><span class="sxs-lookup"><span data-stu-id="b96c4-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c4-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="b96c4-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="b96c4-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b96c4-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b96c4-169">Die Rolle des Benutzers bei der Konferenz, wie etwa Referent oder Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="b96c4-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

