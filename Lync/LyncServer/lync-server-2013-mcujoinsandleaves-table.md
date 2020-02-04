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
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="6d88c-102">McuJoinsAndLeaves-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d88c-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d88c-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6d88c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6d88c-104">Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder Leave-und Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="6d88c-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="6d88c-105">Wenn ein Benutzer beispielsweise an einer Konferenz teilnimmt, die Webkonferenzen und Audio/Video-Elemente umfasst, wird ein Datensatz für die Webkonferenz Verknüpfung dieses Benutzers erstellt, und es wird ein anderer Eintrag für die Audio-und Videokonferenz Teilnahme des Benutzers erstellt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d88c-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="6d88c-106">Column</span></span></th>
<th><span data-ttu-id="6d88c-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6d88c-107">Data Type</span></span></th>
<th><span data-ttu-id="6d88c-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="6d88c-108">Key/Index</span></span></th>
<th><span data-ttu-id="6d88c-109">Details</span><span class="sxs-lookup"><span data-stu-id="6d88c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d88c-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="6d88c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6d88c-112">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="6d88c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d88c-113">Uhrzeit der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-113">Time of conference instance.</span></span> <span data-ttu-id="6d88c-114">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d88c-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="6d88c-115">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6d88c-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d88c-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-117">int</span><span class="sxs-lookup"><span data-stu-id="6d88c-117">int</span></span></p></td>
<td><p><span data-ttu-id="6d88c-118">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="6d88c-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d88c-119">Die ID-Nummer zum Identifizieren der Konferenz Instanz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="6d88c-120">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d88c-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="6d88c-121">Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6d88c-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d88c-122"><strong>UserID</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-123">int</span><span class="sxs-lookup"><span data-stu-id="6d88c-123">int</span></span></p></td>
<td><p><span data-ttu-id="6d88c-124">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="6d88c-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d88c-125">Eindeutige Nummer, die diesen Benutzer kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="6d88c-125">Unique number identifying this user.</span></span> <span data-ttu-id="6d88c-126">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6d88c-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d88c-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-128">int</span><span class="sxs-lookup"><span data-stu-id="6d88c-128">int</span></span></p></td>
<td><p><span data-ttu-id="6d88c-129">Primary</span><span class="sxs-lookup"><span data-stu-id="6d88c-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="6d88c-130">Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, identifiziert McuUserInstance die Kombination aus Benutzer und Gerät eindeutig.</span><span class="sxs-lookup"><span data-stu-id="6d88c-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d88c-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-132">bit</span><span class="sxs-lookup"><span data-stu-id="6d88c-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d88c-133">Gibt an, ob der Benutzer ein PSTN hat oder nicht.</span><span class="sxs-lookup"><span data-stu-id="6d88c-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d88c-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-135">int</span><span class="sxs-lookup"><span data-stu-id="6d88c-135">int</span></span></p></td>
<td><p><span data-ttu-id="6d88c-136">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="6d88c-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d88c-137">Eindeutige Nummer, die diesen Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6d88c-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="6d88c-138">Weitere Informationen finden Sie <a href="lync-server-2013-mcus-table.md">in der Tabelle "Tabelle" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6d88c-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d88c-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-140">datetime</span><span class="sxs-lookup"><span data-stu-id="6d88c-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="6d88c-141">Fremd</span><span class="sxs-lookup"><span data-stu-id="6d88c-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d88c-142">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="6d88c-142">Time of session request.</span></span> <span data-ttu-id="6d88c-143">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d88c-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6d88c-144">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6d88c-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d88c-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-146">int</span><span class="sxs-lookup"><span data-stu-id="6d88c-146">int</span></span></p></td>
<td><p><span data-ttu-id="6d88c-147">Fremd</span><span class="sxs-lookup"><span data-stu-id="6d88c-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d88c-148">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d88c-148">ID number to identify the session.</span></span> <span data-ttu-id="6d88c-149">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d88c-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6d88c-150">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6d88c-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d88c-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-152">datetime</span><span class="sxs-lookup"><span data-stu-id="6d88c-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d88c-153">Der Zeitpunkt, zu dem dieser Benutzer diesem Konferenzserver Beitritt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d88c-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-155">datetime</span><span class="sxs-lookup"><span data-stu-id="6d88c-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d88c-156">Der Zeitpunkt, zu dem dieser Benutzer diesen Konferenzserver verlässt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d88c-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="6d88c-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6d88c-158">int</span><span class="sxs-lookup"><span data-stu-id="6d88c-158">int</span></span></p></td>
<td><p><span data-ttu-id="6d88c-159">Fremd</span><span class="sxs-lookup"><span data-stu-id="6d88c-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d88c-160">Bezeichner, der die Versionsnummer der Client Software in der Konferenz angibt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="6d88c-161">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6d88c-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="6d88c-162">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

