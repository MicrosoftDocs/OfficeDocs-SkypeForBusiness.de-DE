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
ms.openlocfilehash: 2b1eea02c41acf748674cdd7976028a51fdb367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529502"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="2e843-102">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="2e843-102">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e843-103">_**Letztes Änderungsstand des Themas:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="2e843-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="2e843-p101">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="2e843-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="2e843-106">Zum Domänenstamm hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="2e843-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="2e843-107">ACE</span><span class="sxs-lookup"><span data-stu-id="2e843-107">ACE</span></span></th>
<th><span data-ttu-id="2e843-108">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2e843-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="2e843-109">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2e843-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="2e843-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="2e843-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="2e843-111">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="2e843-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="2e843-112">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="2e843-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e843-113">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="2e843-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="2e843-114"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-115"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-116">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-116">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-117">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-117">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-118">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e843-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="2e843-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="2e843-120"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-121">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-121">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-122">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-122">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-123">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-123">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-124">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e843-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="2e843-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="2e843-126"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-127">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-127">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-128">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-128">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-129">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-129">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-130">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e843-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="2e843-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="2e843-132"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-133">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-133">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-134">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-134">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-135">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-135">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-136">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e843-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="2e843-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="2e843-138"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-139">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-139">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-140">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-140">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-141">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-141">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-142">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e843-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="2e843-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="2e843-144"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-145">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-145">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-146">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-146">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-147">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-147">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-148"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e843-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2e843-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="2e843-150"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-151">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-151">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-152">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-152">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-153">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-153">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-154">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e843-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="2e843-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="2e843-156">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-156">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-157">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-157">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-158"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-159">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-159">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-160">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e843-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="2e843-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="2e843-162">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-162">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-163">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-163">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-164"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-165">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-165">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-166">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e843-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2e843-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="2e843-168">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-168">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-169">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-169">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-170"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-171">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-171">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-172">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e843-173">Read PropertySet DS-Replication-Get-Changes für alle Active Directory-Objekte</span><span class="sxs-lookup"><span data-stu-id="2e843-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="2e843-174">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-174">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-175">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-175">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-176">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-176">No</span></span></p></td>
<td><p><span data-ttu-id="2e843-177"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-178">Nein</span><span class="sxs-lookup"><span data-stu-id="2e843-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2e843-p102">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung in den drei integrierten Containern erstellt werden: für Benutzer, Computer und Domänencontroller. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="2e843-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="2e843-181">Zu integrierten Containern hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="2e843-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e843-182">ACE</span><span class="sxs-lookup"><span data-stu-id="2e843-182">ACE</span></span></th>
<th><span data-ttu-id="2e843-183">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2e843-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="2e843-184">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2e843-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e843-185">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="2e843-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="2e843-186"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2e843-187"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2e843-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

