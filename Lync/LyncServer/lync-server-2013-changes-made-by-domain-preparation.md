---
title: 'Lync Server 2013: von der Domänenvorbereitung vorgenommene Änderungen'
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
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="74ff5-102">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="74ff5-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74ff5-103">_**Letztes Änderungsstand des Themas:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="74ff5-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="74ff5-p101">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="74ff5-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="74ff5-106">Zum Domänenstamm hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="74ff5-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="74ff5-107">ACE</span><span class="sxs-lookup"><span data-stu-id="74ff5-107">ACE</span></span></th>
<th><span data-ttu-id="74ff5-108">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="74ff5-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="74ff5-109">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="74ff5-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="74ff5-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="74ff5-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="74ff5-111">RTCHSUniversal-Dienste</span><span class="sxs-lookup"><span data-stu-id="74ff5-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="74ff5-112">Authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="74ff5-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ff5-113">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="74ff5-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="74ff5-114"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-115"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-116">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-116">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-117">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-117">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-118">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ff5-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="74ff5-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="74ff5-120"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-121">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-121">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-122">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-122">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-123">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-123">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-124">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ff5-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="74ff5-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="74ff5-126"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-127">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-127">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-128">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-128">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-129">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-129">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-130">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ff5-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="74ff5-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="74ff5-132"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-133">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-133">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-134">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-134">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-135">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-135">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-136">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ff5-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="74ff5-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="74ff5-138"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-139">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-139">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-140">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-140">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-141">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-141">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-142">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ff5-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="74ff5-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="74ff5-144"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-145">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-145">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-146">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-146">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-147">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-147">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-148"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ff5-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="74ff5-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="74ff5-150"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-151">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-151">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-152">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-152">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-153">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-153">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-154">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ff5-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="74ff5-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="74ff5-156">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-156">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-157">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-157">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-158"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-159">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-159">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-160">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ff5-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="74ff5-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="74ff5-162">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-162">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-163">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-163">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-164"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-165">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-165">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-166">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ff5-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="74ff5-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="74ff5-168">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-168">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-169">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-169">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-170"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-171">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-171">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-172">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ff5-173">Read PropertySet DS-Replication-Get-Changes für alle Active Directory-Objekte</span><span class="sxs-lookup"><span data-stu-id="74ff5-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="74ff5-174">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-174">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-175">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-175">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-176">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-176">No</span></span></p></td>
<td><p><span data-ttu-id="74ff5-177"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-178">Nein</span><span class="sxs-lookup"><span data-stu-id="74ff5-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74ff5-p102">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung in den drei integrierten Containern erstellt werden: für Benutzer, Computer und Domänencontroller. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="74ff5-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="74ff5-181">Zu integrierten Containern hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="74ff5-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ff5-182">ACE</span><span class="sxs-lookup"><span data-stu-id="74ff5-182">ACE</span></span></th>
<th><span data-ttu-id="74ff5-183">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="74ff5-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="74ff5-184">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="74ff5-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ff5-185">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="74ff5-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="74ff5-186"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74ff5-187"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="74ff5-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

