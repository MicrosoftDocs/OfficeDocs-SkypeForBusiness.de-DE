---
title: 'Lync Server 2013: tblPrincipal'
description: 'Lync Server 2013: tblPrincipal.'
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
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547491"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="05fc8-103">tblPrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05fc8-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05fc8-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="05fc8-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="05fc8-105">Die Tabelle „tblPrincipal“ enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="05fc8-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="05fc8-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="05fc8-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05fc8-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="05fc8-107">Column</span></span></th>
<th><span data-ttu-id="05fc8-108">Typ</span><span class="sxs-lookup"><span data-stu-id="05fc8-108">Type</span></span></th>
<th><span data-ttu-id="05fc8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05fc8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-110">prinID</span><span class="sxs-lookup"><span data-stu-id="05fc8-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="05fc8-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="05fc8-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="05fc8-112">Die Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="05fc8-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-113">prinGuid</span><span class="sxs-lookup"><span data-stu-id="05fc8-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="05fc8-114">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="05fc8-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="05fc8-115">Die GUID des Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="05fc8-115">Principal GUID.</span></span> <span data-ttu-id="05fc8-116">Dies wird weitgehend als alternativer Primärschlüssel verwendet, da die Bedeutung in den Active Directory-Domänendienste Raum überschreitet.</span><span class="sxs-lookup"><span data-stu-id="05fc8-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="05fc8-117">(Die GUID für einen zwischengespeicherten Prinzipal ist mit der entsprechenden Objekt-GUID in Active Directory identisch.)</span><span class="sxs-lookup"><span data-stu-id="05fc8-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-118">prinUri</span><span class="sxs-lookup"><span data-stu-id="05fc8-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="05fc8-119">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="05fc8-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="05fc8-p102">Der URI des Prinzipals. Für Benutzer wird das SIP-Schema verwendet, für fast alles andere das ma-grp-Schema.</span><span class="sxs-lookup"><span data-stu-id="05fc8-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-122">prinName</span><span class="sxs-lookup"><span data-stu-id="05fc8-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="05fc8-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="05fc8-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="05fc8-p103">Der allgemeine Name. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="05fc8-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-126">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="05fc8-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="05fc8-127">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="05fc8-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="05fc8-p104">Der Anzeigename. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="05fc8-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-130">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="05fc8-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="05fc8-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="05fc8-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="05fc8-p105">Der Firmenname. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="05fc8-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-134">prinEmail</span><span class="sxs-lookup"><span data-stu-id="05fc8-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="05fc8-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="05fc8-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="05fc8-p106">Die E-Mail-Adresse. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="05fc8-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-138">prinADPath</span><span class="sxs-lookup"><span data-stu-id="05fc8-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="05fc8-139">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="05fc8-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="05fc8-p107">Der Domänenname des Active Directory-Objekts, von dem der Prinzipal eine zwischengespeicherte Version ist. Kann für Typen, die keine Active Directory-Objekte sind (z. B. Systembenutzer), null sein.</span><span class="sxs-lookup"><span data-stu-id="05fc8-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-142">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="05fc8-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="05fc8-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="05fc8-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="05fc8-p108">Der Benutzerprinzipalname (User Principal Name, UPN) des Benutzers. Wird nur von regulären Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="05fc8-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-146">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="05fc8-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="05fc8-147">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="05fc8-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="05fc8-148">0: Der Prinzipal ist aktiv.</span><span class="sxs-lookup"><span data-stu-id="05fc8-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="05fc8-149">1: Der Prinzipal ist deaktiviert, weil die SIP-Funktionen für den Benutzer deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="05fc8-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="05fc8-150">2: Der Prinzipal wird gelöscht, da das zugehörige AD-Objekt gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="05fc8-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-151">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="05fc8-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="05fc8-152">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="05fc8-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="05fc8-153">Der Prinzipaltyp (aus der Tabelle „tblPrincipalType“).</span><span class="sxs-lookup"><span data-stu-id="05fc8-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-154">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="05fc8-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="05fc8-155">Int</span><span class="sxs-lookup"><span data-stu-id="05fc8-155">Int</span></span></p></td>
<td><p><span data-ttu-id="05fc8-156">Lync-Poolzuweisung für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="05fc8-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-157">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="05fc8-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="05fc8-158">Int</span><span class="sxs-lookup"><span data-stu-id="05fc8-158">Int</span></span></p></td>
<td><p><span data-ttu-id="05fc8-159">Server Richtlinienwert für beständigen Chat für Benutzer, wenn die Transpondertyp Richtlinie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="05fc8-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-160">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="05fc8-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="05fc8-161">int</span><span class="sxs-lookup"><span data-stu-id="05fc8-161">int</span></span></p></td>
<td><p><span data-ttu-id="05fc8-162">Die Prinzipal-ID des Erstellers.</span><span class="sxs-lookup"><span data-stu-id="05fc8-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-163">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="05fc8-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="05fc8-164">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="05fc8-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="05fc8-165">Der Zeitstempel für den Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="05fc8-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-166">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="05fc8-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="05fc8-167">int</span><span class="sxs-lookup"><span data-stu-id="05fc8-167">int</span></span></p></td>
<td><p><span data-ttu-id="05fc8-168">Die ID des Prinzipals, der dieses Element zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="05fc8-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-169">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="05fc8-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="05fc8-170">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="05fc8-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="05fc8-171">Der Zeitstempel für die letzte Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="05fc8-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-172">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="05fc8-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="05fc8-173">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="05fc8-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="05fc8-174">Datum und Uhrzeit der letzten Aktualisierung der Active Directory-Synchronisierung für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="05fc8-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="05fc8-175">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="05fc8-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05fc8-176">Spalte</span><span class="sxs-lookup"><span data-stu-id="05fc8-176">Column</span></span></th>
<th><span data-ttu-id="05fc8-177">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05fc8-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05fc8-178">prinID</span><span class="sxs-lookup"><span data-stu-id="05fc8-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="05fc8-179">Der Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="05fc8-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fc8-180">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="05fc8-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="05fc8-181">Fremdschlüssel mit Suche in der Tabelle „ tblPrincipalType.ptypeID“.</span><span class="sxs-lookup"><span data-stu-id="05fc8-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

