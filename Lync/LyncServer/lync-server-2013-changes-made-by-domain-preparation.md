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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="bd224-102">Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="bd224-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd224-103">_**Letztes Änderungsdatum des Themas:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="bd224-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="bd224-104">In der folgenden Tabelle sind die Zugriffssteuerungseinträge (ACEs) aufgeführt, die von der Domänenvorbereitung für den Domänenstamm erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bd224-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="bd224-105">Alle ACEs werden geerbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="bd224-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="bd224-106">ACEs, die dem Domänenstamm hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="bd224-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="bd224-107">ACE</span><span class="sxs-lookup"><span data-stu-id="bd224-107">ACE</span></span></th>
<th><span data-ttu-id="bd224-108">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="bd224-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="bd224-109">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="bd224-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="bd224-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="bd224-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="bd224-111">RTCHSUniversal-Dienste</span><span class="sxs-lookup"><span data-stu-id="bd224-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="bd224-112">Authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="bd224-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd224-113">Read-Container (nicht geerbt)</span><span class="sxs-lookup"><span data-stu-id="bd224-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="bd224-114"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-115"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-116">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-116">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-117">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-117">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-118">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd224-119">Lesen der Benutzer-PropertySet-Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bd224-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="bd224-120"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-121">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-121">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-122">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-122">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-123">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-123">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-124">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd224-125">Lesen der Benutzer-PropertySet Personal-Informationen</span><span class="sxs-lookup"><span data-stu-id="bd224-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="bd224-126"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-127">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-127">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-128">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-128">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-129">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-129">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-130">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd224-131">Lesen der Benutzer-PropertySet-allgemeine Informationen</span><span class="sxs-lookup"><span data-stu-id="bd224-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="bd224-132"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-133">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-133">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-134">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-134">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-135">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-135">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-136">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd224-137">Lesen der Benutzer-PropertySet-öffentlichen Informationen</span><span class="sxs-lookup"><span data-stu-id="bd224-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="bd224-138"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-139">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-139">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-140">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-140">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-141">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-141">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-142">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd224-143">Read User PropertySet RTCUserSearchProperty-Satz</span><span class="sxs-lookup"><span data-stu-id="bd224-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="bd224-144"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-145">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-145">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-146">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-146">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-147">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-147">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-148"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd224-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="bd224-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="bd224-150"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-151">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-151">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-152">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-152">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-153">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-153">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-154">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd224-155">Schreiben von Benutzer Eigenschafts Proxy-Adressen</span><span class="sxs-lookup"><span data-stu-id="bd224-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="bd224-156">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-156">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-157">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-157">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-158"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-159">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-159">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-160">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd224-161">Schreiben von Benutzer-Eigenschaftssatz-RTCUserSearchProperty</span><span class="sxs-lookup"><span data-stu-id="bd224-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="bd224-162">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-162">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-163">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-163">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-164"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-165">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-165">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-166">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd224-167">Schreiben von Benutzer-PropertySet-RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="bd224-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="bd224-168">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-168">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-169">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-169">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-170"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-171">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-171">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-172">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd224-173">Lesen von PropertySet DS-Replikation-abrufen – Änderungen aller Active Directory-Objekte</span><span class="sxs-lookup"><span data-stu-id="bd224-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="bd224-174">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-174">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-175">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-175">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-176">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-176">No</span></span></p></td>
<td><p><span data-ttu-id="bd224-177"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-178">Nein</span><span class="sxs-lookup"><span data-stu-id="bd224-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bd224-179">In der folgenden Tabelle sind die ACEs aufgeführt, die von der Domänenvorbereitung in den drei integrierten Containern erstellt werden: Benutzer, Computer und Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="bd224-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="bd224-180">Alle ACEs werden geerbt, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="bd224-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="bd224-181">ACEs, die zu integrierten Containern hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="bd224-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd224-182">ACE</span><span class="sxs-lookup"><span data-stu-id="bd224-182">ACE</span></span></th>
<th><span data-ttu-id="bd224-183">RTCUniversal-UserReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="bd224-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="bd224-184">RTCUniversal-ServerReadOnly-Gruppe</span><span class="sxs-lookup"><span data-stu-id="bd224-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd224-185">Read-Container (nicht geerbt)</span><span class="sxs-lookup"><span data-stu-id="bd224-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="bd224-186"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bd224-187"><strong>Ja</strong></span><span class="sxs-lookup"><span data-stu-id="bd224-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

