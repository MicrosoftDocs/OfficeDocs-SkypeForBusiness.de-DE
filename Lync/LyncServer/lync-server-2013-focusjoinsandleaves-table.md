---
title: 'Lync Server 2013: FocusJoinsAndLeaves-Tabelle'
description: 'Lync Server 2013: FocusJoinsAndLeaves-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5796de16ed204ce4f33935d937cbaa425d63a67f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577441"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="232ce-103">FocusJoinsAndLeaves-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="232ce-103">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="232ce-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="232ce-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="232ce-105">Jeder Datensatz in dieser Tabelle enthält die KDS-Informationen zu den Join-und Leave-Informationen eines Benutzers für eine Konferenz.</span><span class="sxs-lookup"><span data-stu-id="232ce-105">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="232ce-106">Jede Konferenz wird in dieser Tabelle von einem Datensatz für jedes Mal dargestellt, wenn ein Benutzer einer Konferenz Beitritt und diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="232ce-106">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="232ce-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="232ce-107">Column</span></span></th>
<th><span data-ttu-id="232ce-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="232ce-108">Data Type</span></span></th>
<th><span data-ttu-id="232ce-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="232ce-109">Key/Index</span></span></th>
<th><span data-ttu-id="232ce-110">Details</span><span class="sxs-lookup"><span data-stu-id="232ce-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="232ce-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="232ce-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="232ce-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="232ce-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="232ce-114">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="232ce-114">Time of conference instance.</span></span> <span data-ttu-id="232ce-115">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="232ce-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="232ce-116">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="232ce-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="232ce-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-118">int</span><span class="sxs-lookup"><span data-stu-id="232ce-118">int</span></span></p></td>
<td><p><span data-ttu-id="232ce-119">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="232ce-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="232ce-120">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="232ce-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="232ce-121">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="232ce-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="232ce-122">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="232ce-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="232ce-123"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-123"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-124">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="232ce-124">datetime</span></span></p></td>
<td><p><span data-ttu-id="232ce-125">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="232ce-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="232ce-126">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="232ce-126">Time of session request.</span></span> <span data-ttu-id="232ce-127">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="232ce-127">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="232ce-128">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="232ce-128">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="232ce-129"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-129"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-130">int</span><span class="sxs-lookup"><span data-stu-id="232ce-130">int</span></span></p></td>
<td><p><span data-ttu-id="232ce-131">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="232ce-131">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="232ce-132">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="232ce-132">ID number to identify the session.</span></span> <span data-ttu-id="232ce-133">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="232ce-133">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="232ce-134">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="232ce-134">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="232ce-135"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-135"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-136">int</span><span class="sxs-lookup"><span data-stu-id="232ce-136">int</span></span></p></td>
<td><p><span data-ttu-id="232ce-137">Fremd</span><span class="sxs-lookup"><span data-stu-id="232ce-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="232ce-138">Eindeutige Zahl, die diesen Benutzer identifiziert, auf die <a href="lync-server-2013-users-table.md">in der Tabelle users in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="232ce-138">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="232ce-139"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-139"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-140">int</span><span class="sxs-lookup"><span data-stu-id="232ce-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="232ce-141">Wenn ein Benutzer gleichzeitig auf mehreren Computern oder Geräten angemeldet ist, wird <strong>UserInstance</strong> verwendet, um die Benutzer/Geräte-Kombination eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="232ce-141">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="232ce-142"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-142"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-143">Bit</span><span class="sxs-lookup"><span data-stu-id="232ce-143">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="232ce-144">Gibt an, ob sich der Benutzer intern angemeldet hat oder nicht.</span><span class="sxs-lookup"><span data-stu-id="232ce-144">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="232ce-145"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-145"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-146">int</span><span class="sxs-lookup"><span data-stu-id="232ce-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="232ce-147">Rolle dieses Benutzers in der Konferenz, beispielsweise Referent oder Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="232ce-147">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="232ce-148"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-148"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-149">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="232ce-149">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="232ce-150">Die Zeit, zu der dieser Benutzer der Konferenz Beitritt.</span><span class="sxs-lookup"><span data-stu-id="232ce-150">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="232ce-151"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-151"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-152">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="232ce-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="232ce-153">Die Zeit, zu der dieser Benutzer die Konferenz verlässt.</span><span class="sxs-lookup"><span data-stu-id="232ce-153">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="232ce-154"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-154"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-155">int</span><span class="sxs-lookup"><span data-stu-id="232ce-155">int</span></span></p></td>
<td><p><span data-ttu-id="232ce-156">Fremd</span><span class="sxs-lookup"><span data-stu-id="232ce-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="232ce-157">Version der Client Software des Benutzers, auf die in der <a href="lync-server-2013-clientversions-table.md">Client Versions-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="232ce-157">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="232ce-158"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="232ce-158"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="232ce-159">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="232ce-159">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="232ce-160">GUID (Globally Unique Identifier) des in der Konferenz verwendeten Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="232ce-160">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="232ce-161">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="232ce-161">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

