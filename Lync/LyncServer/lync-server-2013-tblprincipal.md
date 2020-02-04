---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="09935-102">tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09935-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09935-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="09935-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="09935-104">tblPrincipal enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="09935-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="09935-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="09935-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09935-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="09935-106">Column</span></span></th>
<th><span data-ttu-id="09935-107">Typ</span><span class="sxs-lookup"><span data-stu-id="09935-107">Type</span></span></th>
<th><span data-ttu-id="09935-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09935-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09935-109">prinID</span><span class="sxs-lookup"><span data-stu-id="09935-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="09935-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09935-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="09935-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="09935-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="09935-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="09935-113">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09935-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="09935-114">Prinzipal-GUID.</span><span class="sxs-lookup"><span data-stu-id="09935-114">Principal GUID.</span></span> <span data-ttu-id="09935-115">Dies wird im Allgemeinen als alternativer Primärschlüssel verwendet, da dessen Bedeutung in den Bereich der Active Directory-Domänendienste überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="09935-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="09935-116">(Die GUID für einen zwischengespeicherten Prinzipal entspricht der entsprechenden GUID des Active Directory-Objekts.)</span><span class="sxs-lookup"><span data-stu-id="09935-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09935-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="09935-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="09935-118">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09935-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="09935-119">Prinzipal-URI.</span><span class="sxs-lookup"><span data-stu-id="09935-119">Principal URI.</span></span> <span data-ttu-id="09935-120">Das SIP-Schema wird für Benutzer verwendet, und MA-GRP wird für fast alles andere verwendet.</span><span class="sxs-lookup"><span data-stu-id="09935-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-121">prinName</span><span class="sxs-lookup"><span data-stu-id="09935-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="09935-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="09935-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="09935-123">Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="09935-123">Common name.</span></span> <span data-ttu-id="09935-124">Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="09935-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09935-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="09935-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="09935-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="09935-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="09935-127">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="09935-127">Display name.</span></span> <span data-ttu-id="09935-128">Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="09935-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="09935-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="09935-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="09935-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="09935-131">Name des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="09935-131">Company name.</span></span> <span data-ttu-id="09935-132">Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="09935-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09935-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="09935-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="09935-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="09935-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="09935-135">E-Mail.</span><span class="sxs-lookup"><span data-stu-id="09935-135">Email.</span></span> <span data-ttu-id="09935-136">Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="09935-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="09935-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="09935-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="09935-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="09935-139">Der Domänenname des Active Directory-Objekts, in dem der Prinzipal eine zwischengespeicherte Version von ist.</span><span class="sxs-lookup"><span data-stu-id="09935-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="09935-140">Kann NULL für Typen sein, die keine Active Directory-Objekte (wie Systembenutzer) sind.</span><span class="sxs-lookup"><span data-stu-id="09935-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09935-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="09935-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="09935-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="09935-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="09935-143">Benutzerprinzipalname (User Principal Name, UPN) des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="09935-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="09935-144">Wird nur von normalen Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="09935-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="09935-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="09935-146">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09935-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="09935-147">0: Principal ist aktiv.</span><span class="sxs-lookup"><span data-stu-id="09935-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="09935-148">1: Principal ist deaktiviert, da die SIP-Funktionen des Benutzers deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="09935-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="09935-149">2: Principal wird gelöscht, weil das zugeordnete anzeigen Objekt gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="09935-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09935-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="09935-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="09935-151">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09935-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="09935-152">Principal Type (aus tblPrincipalType-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="09935-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="09935-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="09935-154">Int</span><span class="sxs-lookup"><span data-stu-id="09935-154">Int</span></span></p></td>
<td><p><span data-ttu-id="09935-155">Lync-Pool Aufgabe für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="09935-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09935-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="09935-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="09935-157">Int</span><span class="sxs-lookup"><span data-stu-id="09935-157">Int</span></span></p></td>
<td><p><span data-ttu-id="09935-158">Server Richtlinienwert des beständigen Chats für Benutzer, wenn die Kategorie-typrichtlinie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="09935-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="09935-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="09935-160">int</span><span class="sxs-lookup"><span data-stu-id="09935-160">int</span></span></p></td>
<td><p><span data-ttu-id="09935-161">Prinzipal-ID des Erstellers.</span><span class="sxs-lookup"><span data-stu-id="09935-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09935-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="09935-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="09935-163">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09935-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="09935-164">Zeitstempel für die Erstellungszeit.</span><span class="sxs-lookup"><span data-stu-id="09935-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="09935-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="09935-166">int</span><span class="sxs-lookup"><span data-stu-id="09935-166">int</span></span></p></td>
<td><p><span data-ttu-id="09935-167">Die ID des Prinzipals, der diesen zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="09935-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09935-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="09935-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="09935-169">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09935-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="09935-170">Zeitstempel für das letzte Update.</span><span class="sxs-lookup"><span data-stu-id="09935-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="09935-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="09935-172">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09935-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="09935-173">Datum und Uhrzeit der letzten Aktualisierung der Active Directory-Synchronisierung für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="09935-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="09935-174">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="09935-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09935-175">Spalte</span><span class="sxs-lookup"><span data-stu-id="09935-175">Column</span></span></th>
<th><span data-ttu-id="09935-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09935-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09935-177">prinID</span><span class="sxs-lookup"><span data-stu-id="09935-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="09935-178">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="09935-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09935-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="09935-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="09935-180">Fremdschlüssel mit Lookup in der tblPrincipalType. ptypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="09935-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

