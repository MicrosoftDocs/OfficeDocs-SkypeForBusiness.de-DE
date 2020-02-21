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
ms.openlocfilehash: 74fe383cf773e1cdfa645a3f8513167fd7472958
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="2f1d7-102">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="2f1d7-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f1d7-103">_**Letztes Änderungsstand des Themas:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="2f1d7-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="2f1d7-p101">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="2f1d7-106">Zum Domänenstamm hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="2f1d7-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="2f1d7-107">ACE</span><span class="sxs-lookup"><span data-stu-id="2f1d7-107">ACE</span></span></th>
<th><span data-ttu-id="2f1d7-108">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2f1d7-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="2f1d7-109">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2f1d7-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="2f1d7-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="2f1d7-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="2f1d7-111">RTCHSUniversal-Dienste</span><span class="sxs-lookup"><span data-stu-id="2f1d7-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="2f1d7-112">Authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="2f1d7-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f1d7-113">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="2f1d7-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-114"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-115"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-116">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-116">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-117">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-117">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-118">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f1d7-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="2f1d7-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-120"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-121">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-121">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-122">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-122">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-123">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-123">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-124">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f1d7-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="2f1d7-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-126"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-127">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-127">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-128">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-128">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-129">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-129">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-130">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f1d7-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="2f1d7-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-132"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-133">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-133">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-134">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-134">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-135">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-135">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-136">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f1d7-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="2f1d7-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-138"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-139">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-139">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-140">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-140">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-141">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-141">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-142">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f1d7-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="2f1d7-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-144"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-145">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-145">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-146">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-146">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-147">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-147">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-148"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f1d7-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2f1d7-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-150"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-151">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-151">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-152">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-152">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-153">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-153">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-154">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f1d7-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="2f1d7-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-156">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-156">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-157">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-157">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-158"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-159">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-159">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-160">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f1d7-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="2f1d7-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-162">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-162">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-163">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-163">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-164"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-165">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-165">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-166">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f1d7-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2f1d7-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-168">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-168">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-169">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-169">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-170"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-171">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-171">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-172">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f1d7-173">Read PropertySet DS-Replication-Get-Changes für alle Active Directory-Objekte</span><span class="sxs-lookup"><span data-stu-id="2f1d7-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-174">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-174">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-175">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-175">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-176">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-176">No</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-177"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-178">Nein</span><span class="sxs-lookup"><span data-stu-id="2f1d7-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2f1d7-p102">In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung in den drei integrierten Containern erstellt werden: für Benutzer, Computer und Domänencontroller. Alle ACEs werden vererbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="2f1d7-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="2f1d7-181">Zu integrierten Containern hinzugefügte ACEs</span><span class="sxs-lookup"><span data-stu-id="2f1d7-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f1d7-182">ACE</span><span class="sxs-lookup"><span data-stu-id="2f1d7-182">ACE</span></span></th>
<th><span data-ttu-id="2f1d7-183">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2f1d7-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="2f1d7-184">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="2f1d7-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f1d7-185">Read Container (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="2f1d7-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="2f1d7-186"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="2f1d7-187"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="2f1d7-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

