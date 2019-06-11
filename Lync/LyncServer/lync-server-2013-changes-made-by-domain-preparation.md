---
title: 'Lync Server 2013: von der Domänenvorbereitung vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="407a6-102">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="407a6-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="407a6-103">_**Letztes Änderungsdatum des Themas:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="407a6-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="407a6-104">In der folgenden Tabelle sind die Zugriffssteuerungseinträge (ACEs) aufgeführt, die von der Domänenvorbereitung für den Domänenstamm erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="407a6-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="407a6-105">Alle ACEs werden geerbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="407a6-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="407a6-106">ACEs, die dem Domänenstamm hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="407a6-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="407a6-107">ACE</span><span class="sxs-lookup"><span data-stu-id="407a6-107">ACE</span></span></th>
<th><span data-ttu-id="407a6-108">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="407a6-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="407a6-109">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="407a6-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="407a6-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="407a6-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="407a6-111">RTCHSUniversal-Dienste</span><span class="sxs-lookup"><span data-stu-id="407a6-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="407a6-112">Authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="407a6-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="407a6-113">Read-Container (nicht geerbt)</span><span class="sxs-lookup"><span data-stu-id="407a6-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="407a6-114"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-115"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-116">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-116">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-117">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-117">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-118">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407a6-119">Lesen der Benutzer-PropertySet-Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="407a6-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="407a6-120"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-121">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-121">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-122">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-122">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-123">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-123">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-124">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407a6-125">Lesen der Benutzer-PropertySet Personal-Informationen</span><span class="sxs-lookup"><span data-stu-id="407a6-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="407a6-126"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-127">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-127">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-128">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-128">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-129">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-129">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-130">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407a6-131">Lesen der Benutzer-PropertySet-allgemeine Informationen</span><span class="sxs-lookup"><span data-stu-id="407a6-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="407a6-132"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-133">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-133">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-134">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-134">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-135">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-135">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-136">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407a6-137">Lesen der Benutzer-PropertySet-öffentlichen Informationen</span><span class="sxs-lookup"><span data-stu-id="407a6-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="407a6-138"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-139">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-139">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-140">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-140">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-141">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-141">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-142">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407a6-143">Read User PropertySet RTCUserSearchProperty-Satz</span><span class="sxs-lookup"><span data-stu-id="407a6-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="407a6-144"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-145">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-145">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-146">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-146">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-147">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-147">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-148"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407a6-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="407a6-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="407a6-150"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-151">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-151">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-152">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-152">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-153">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-153">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-154">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407a6-155">Schreiben von Benutzer Eigenschafts Proxy-Adressen</span><span class="sxs-lookup"><span data-stu-id="407a6-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="407a6-156">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-156">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-157">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-157">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-158"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-159">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-159">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-160">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407a6-161">Schreiben von Benutzer-Eigenschaftssatz-RTCUserSearchProperty</span><span class="sxs-lookup"><span data-stu-id="407a6-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="407a6-162">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-162">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-163">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-163">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-164"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-165">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-165">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-166">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407a6-167">Schreiben von Benutzer-PropertySet-RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="407a6-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="407a6-168">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-168">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-169">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-169">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-170"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-171">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-171">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-172">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407a6-173">Lesen von PropertySet DS-Replikation-abrufen – Änderungen aller Active Directory-Objekte</span><span class="sxs-lookup"><span data-stu-id="407a6-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="407a6-174">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-174">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-175">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-175">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-176">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-176">No</span></span></p></td>
<td><p><span data-ttu-id="407a6-177"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-178">Nein</span><span class="sxs-lookup"><span data-stu-id="407a6-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="407a6-179">In der folgenden Tabelle sind die ACEs aufgeführt, die von der Domänenvorbereitung in den drei integrierten Containern erstellt werden: Benutzer, Computer und Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="407a6-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="407a6-180">Alle ACEs werden geerbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="407a6-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="407a6-181">ACEs, die zu integrierten Containern hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="407a6-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="407a6-182">ACE</span><span class="sxs-lookup"><span data-stu-id="407a6-182">ACE</span></span></th>
<th><span data-ttu-id="407a6-183">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="407a6-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="407a6-184">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="407a6-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="407a6-185">Read-Container (nicht geerbt)</span><span class="sxs-lookup"><span data-stu-id="407a6-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="407a6-186"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="407a6-187"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="407a6-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

