---
title: 'Lync Server 2013: von der Domänenvorbereitung vorgenommene Änderungen'
description: 'Lync Server 2013: von der Domänenvorbereitung vorgenommene Änderungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543691"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="66c6a-103">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="66c6a-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66c6a-104">_**Letztes Änderungsstand des Themas:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="66c6a-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="66c6a-p101">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="66c6a-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="66c6a-107">Zum Domänenstamm hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="66c6a-107">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c6a-108">ACE</span><span class="sxs-lookup"><span data-stu-id="66c6a-108">ACE</span></span></th>
<th><span data-ttu-id="66c6a-109">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="66c6a-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="66c6a-110">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="66c6a-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="66c6a-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="66c6a-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="66c6a-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="66c6a-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="66c6a-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="66c6a-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c6a-114">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="66c6a-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="66c6a-115"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-116"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-117">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-117">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-118">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-118">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-119">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c6a-120">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="66c6a-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="66c6a-121"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-122">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-122">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-123">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-123">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-124">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-124">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-125">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c6a-126">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="66c6a-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="66c6a-127"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-128">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-128">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-129">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-129">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-130">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-130">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-131">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c6a-132">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="66c6a-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="66c6a-133"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-134">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-134">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-135">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-135">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-136">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-136">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-137">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c6a-138">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="66c6a-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="66c6a-139"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-140">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-140">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-141">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-141">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-142">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-142">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-143">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c6a-144">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="66c6a-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="66c6a-145"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-146">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-146">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-147">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-147">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-148">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-148">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-149"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c6a-150">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="66c6a-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="66c6a-151"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-152">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-152">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-153">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-153">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-154">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-154">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-155">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c6a-156">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="66c6a-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="66c6a-157">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-157">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-158">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-158">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-159"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-160">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-160">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-161">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c6a-162">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="66c6a-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="66c6a-163">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-163">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-164">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-164">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-165"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-166">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-166">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-167">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c6a-168">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="66c6a-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="66c6a-169">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-169">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-170">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-170">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-171"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-172">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-172">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-173">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c6a-174">Read PropertySet DS-Replication-Get-Changes für alle Active Directory-Objekte</span><span class="sxs-lookup"><span data-stu-id="66c6a-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="66c6a-175">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-175">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-176">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-176">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-177">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-177">No</span></span></p></td>
<td><p><span data-ttu-id="66c6a-178"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-179">Nein</span><span class="sxs-lookup"><span data-stu-id="66c6a-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="66c6a-p102">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung in den drei integrierten Containern erstellt werden: für Benutzer, Computer und Domänencontroller. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="66c6a-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="66c6a-182">Zu integrierten Containern hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="66c6a-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c6a-183">ACE</span><span class="sxs-lookup"><span data-stu-id="66c6a-183">ACE</span></span></th>
<th><span data-ttu-id="66c6a-184">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="66c6a-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="66c6a-185">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="66c6a-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c6a-186">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="66c6a-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="66c6a-187"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="66c6a-188"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="66c6a-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

