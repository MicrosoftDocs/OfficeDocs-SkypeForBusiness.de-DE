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
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="ae2c2-102">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="ae2c2-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae2c2-103">_**Letztes Änderungsstand des Themas:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="ae2c2-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="ae2c2-p101">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="ae2c2-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="ae2c2-106">Zum Domänenstamm hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="ae2c2-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="ae2c2-107">ACE</span><span class="sxs-lookup"><span data-stu-id="ae2c2-107">ACE</span></span></th>
<th><span data-ttu-id="ae2c2-108">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="ae2c2-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="ae2c2-109">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="ae2c2-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="ae2c2-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="ae2c2-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="ae2c2-111">RTCHSUniversal-Dienste</span><span class="sxs-lookup"><span data-stu-id="ae2c2-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="ae2c2-112">Authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="ae2c2-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae2c2-113">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="ae2c2-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-114"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-115"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-116">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-116">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-117">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-117">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-118">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae2c2-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="ae2c2-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-120"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-121">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-121">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-122">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-122">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-123">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-123">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-124">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae2c2-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="ae2c2-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-126"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-127">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-127">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-128">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-128">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-129">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-129">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-130">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae2c2-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="ae2c2-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-132"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-133">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-133">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-134">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-134">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-135">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-135">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-136">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae2c2-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="ae2c2-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-138"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-139">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-139">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-140">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-140">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-141">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-141">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-142">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae2c2-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="ae2c2-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-144"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-145">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-145">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-146">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-146">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-147">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-147">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-148"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae2c2-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ae2c2-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-150"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-151">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-151">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-152">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-152">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-153">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-153">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-154">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae2c2-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="ae2c2-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-156">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-156">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-157">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-157">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-158"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-159">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-159">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-160">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae2c2-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="ae2c2-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-162">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-162">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-163">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-163">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-164"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-165">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-165">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-166">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae2c2-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ae2c2-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-168">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-168">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-169">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-169">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-170"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-171">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-171">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-172">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae2c2-173">Read PropertySet DS-Replication-Get-Changes für alle Active Directory-Objekte</span><span class="sxs-lookup"><span data-stu-id="ae2c2-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-174">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-174">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-175">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-175">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-176">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-176">No</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-177"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-178">Nein</span><span class="sxs-lookup"><span data-stu-id="ae2c2-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ae2c2-p102">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung in den drei integrierten Containern erstellt werden: für Benutzer, Computer und Domänencontroller. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="ae2c2-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="ae2c2-181">Zu integrierten Containern hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="ae2c2-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae2c2-182">ACE</span><span class="sxs-lookup"><span data-stu-id="ae2c2-182">ACE</span></span></th>
<th><span data-ttu-id="ae2c2-183">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="ae2c2-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="ae2c2-184">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="ae2c2-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae2c2-185">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="ae2c2-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="ae2c2-186"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="ae2c2-187"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="ae2c2-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

