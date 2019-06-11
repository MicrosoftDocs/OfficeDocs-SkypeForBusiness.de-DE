---
title: 'Lync Server 2013: FocusJoinsAndLeaves-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ead6fc2ce79f7ab1206476ee420bd2ba5a7711f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="2b2eb-102">FocusJoinsAndLeaves-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2eb-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b2eb-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2b2eb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2b2eb-104">Jeder Datensatz in dieser Tabelle enthält die CDR-Informationen zu den Join-und Leave-Informationen eines Benutzers für eine Konferenz.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="2b2eb-105">Jede Konferenz wird in dieser Tabelle für jedes Mal, wenn ein Benutzer mit der Konferenz verbunden ist, mit einem Datensatz dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b2eb-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="2b2eb-106">Column</span></span></th>
<th><span data-ttu-id="2b2eb-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2b2eb-107">Data Type</span></span></th>
<th><span data-ttu-id="2b2eb-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="2b2eb-108">Key/Index</span></span></th>
<th><span data-ttu-id="2b2eb-109">Details</span><span class="sxs-lookup"><span data-stu-id="2b2eb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b2eb-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="2b2eb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-112">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="2b2eb-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-113">Uhrzeit der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-113">Time of conference instance.</span></span> <span data-ttu-id="2b2eb-114">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="2b2eb-115">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b2eb-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2eb-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-117">int</span><span class="sxs-lookup"><span data-stu-id="2b2eb-117">int</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-118">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="2b2eb-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-119">Die ID-Nummer zum Identifizieren der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="2b2eb-120">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="2b2eb-121">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b2eb-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2eb-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-123">datetime</span><span class="sxs-lookup"><span data-stu-id="2b2eb-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-124">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="2b2eb-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-125">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-125">Time of session request.</span></span> <span data-ttu-id="2b2eb-126">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2b2eb-127">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b2eb-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2eb-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-129">int</span><span class="sxs-lookup"><span data-stu-id="2b2eb-129">int</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-130">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="2b2eb-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-131">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-131">ID number to identify the session.</span></span> <span data-ttu-id="2b2eb-132">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2b2eb-133">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b2eb-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2eb-134"><strong>UserID</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-135">int</span><span class="sxs-lookup"><span data-stu-id="2b2eb-135">int</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-136">Fremd</span><span class="sxs-lookup"><span data-stu-id="2b2eb-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-137">Eindeutige Nummer, die diesen Benutzer identifiziert, auf die <a href="lync-server-2013-users-table.md">in der Tabelle "Benutzer" in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2eb-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-139">int</span><span class="sxs-lookup"><span data-stu-id="2b2eb-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2b2eb-140">Wenn ein Benutzer gleichzeitig an mehreren Computern oder Geräten angemeldet ist, wird <strong>UserInstance</strong> verwendet, um die Kombination aus Benutzer und Gerät eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2eb-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-142">bit</span><span class="sxs-lookup"><span data-stu-id="2b2eb-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2b2eb-143">Ob sich der Benutzer intern angemeldet hat oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2eb-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-145">int</span><span class="sxs-lookup"><span data-stu-id="2b2eb-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2b2eb-146">Die Rolle dieses Benutzers in der Konferenz, beispielsweise Referent oder Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2eb-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-148">datetime</span><span class="sxs-lookup"><span data-stu-id="2b2eb-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2b2eb-149">Der Zeitpunkt, zu dem dieser Benutzer der Konferenz Beitritt.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2eb-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-151">datetime</span><span class="sxs-lookup"><span data-stu-id="2b2eb-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2b2eb-152">Der Zeitpunkt, zu dem dieser Benutzer die Konferenz verlässt.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2eb-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-154">int</span><span class="sxs-lookup"><span data-stu-id="2b2eb-154">int</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-155">Fremd</span><span class="sxs-lookup"><span data-stu-id="2b2eb-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2b2eb-156">Die Version der Client Software des Benutzers, auf die die <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in lync Server 2013</a>verweist.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2eb-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2b2eb-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2eb-158">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="2b2eb-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2b2eb-159">GUID (Globally Unique Identifier) des in der Konferenz verwendeten Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="2b2eb-160">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

