---
title: 'Lync Server 2013: FocusJoinsAndLeaves-Tabelle'
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
ms.openlocfilehash: 49021f6b03481ccb5661c85cec87e5786a8d83dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="e9e67-102">FocusJoinsAndLeaves-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9e67-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9e67-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e9e67-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e9e67-104">Jeder Datensatz in dieser Tabelle enthält die KDS-Informationen zu den Join-und Leave-Informationen eines Benutzers für eine Konferenz.</span><span class="sxs-lookup"><span data-stu-id="e9e67-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="e9e67-105">Jede Konferenz wird in dieser Tabelle von einem Datensatz für jedes Mal dargestellt, wenn ein Benutzer einer Konferenz Beitritt und diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="e9e67-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9e67-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="e9e67-106">Column</span></span></th>
<th><span data-ttu-id="e9e67-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e9e67-107">Data Type</span></span></th>
<th><span data-ttu-id="e9e67-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="e9e67-108">Key/Index</span></span></th>
<th><span data-ttu-id="e9e67-109">Details</span><span class="sxs-lookup"><span data-stu-id="e9e67-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9e67-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e9e67-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9e67-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e9e67-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9e67-113">Zeitpunkt der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="e9e67-113">Time of conference instance.</span></span> <span data-ttu-id="e9e67-114">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e9e67-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e9e67-115">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e9e67-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9e67-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-117">int</span><span class="sxs-lookup"><span data-stu-id="e9e67-117">int</span></span></p></td>
<td><p><span data-ttu-id="e9e67-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e9e67-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9e67-119">ID zur Identifikation der Konferenzinstanz.</span><span class="sxs-lookup"><span data-stu-id="e9e67-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="e9e67-120">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e9e67-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e9e67-121">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e9e67-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9e67-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-123">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e9e67-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9e67-124">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e9e67-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9e67-125">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e9e67-125">Time of session request.</span></span> <span data-ttu-id="e9e67-126">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e9e67-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e9e67-127">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e9e67-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9e67-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-129">int</span><span class="sxs-lookup"><span data-stu-id="e9e67-129">int</span></span></p></td>
<td><p><span data-ttu-id="e9e67-130">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e9e67-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9e67-131">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e9e67-131">ID number to identify the session.</span></span> <span data-ttu-id="e9e67-132">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e9e67-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e9e67-133">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e9e67-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9e67-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-135">int</span><span class="sxs-lookup"><span data-stu-id="e9e67-135">int</span></span></p></td>
<td><p><span data-ttu-id="e9e67-136">Fremd</span><span class="sxs-lookup"><span data-stu-id="e9e67-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9e67-137">Eindeutige Zahl, die diesen Benutzer identifiziert, auf die <a href="lync-server-2013-users-table.md">in der Tabelle users in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e9e67-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9e67-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-139">int</span><span class="sxs-lookup"><span data-stu-id="e9e67-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9e67-140">Wenn ein Benutzer gleichzeitig auf mehreren Computern oder Geräten angemeldet ist, wird <strong>UserInstance</strong> verwendet, um die Benutzer/Geräte-Kombination eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e9e67-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9e67-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-142">Bit</span><span class="sxs-lookup"><span data-stu-id="e9e67-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e9e67-143">Gibt an, ob sich der Benutzer intern angemeldet hat oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e9e67-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9e67-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-145">int</span><span class="sxs-lookup"><span data-stu-id="e9e67-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e9e67-146">Rolle dieses Benutzers in der Konferenz, beispielsweise Referent oder Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="e9e67-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9e67-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-148">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e9e67-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e9e67-149">Die Zeit, zu der dieser Benutzer der Konferenz Beitritt.</span><span class="sxs-lookup"><span data-stu-id="e9e67-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9e67-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-151">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e9e67-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e9e67-152">Die Zeit, zu der dieser Benutzer die Konferenz verlässt.</span><span class="sxs-lookup"><span data-stu-id="e9e67-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9e67-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-154">int</span><span class="sxs-lookup"><span data-stu-id="e9e67-154">int</span></span></p></td>
<td><p><span data-ttu-id="e9e67-155">Fremd</span><span class="sxs-lookup"><span data-stu-id="e9e67-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9e67-156">Version der Client Software des Benutzers, auf die in der <a href="lync-server-2013-clientversions-table.md">Client Versions-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e9e67-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9e67-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e9e67-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e67-158">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="e9e67-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9e67-159">GUID (Globally Unique Identifier) des in der Konferenz verwendeten Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="e9e67-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="e9e67-160">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e9e67-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

