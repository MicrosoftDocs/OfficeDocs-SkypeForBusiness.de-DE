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
ms.openlocfilehash: b9d5122b375b4906320f254179ce101652ad6db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="4cb38-102">tblPrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cb38-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cb38-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4cb38-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4cb38-104">Die Tabelle „tblPrincipal“ enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="4cb38-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="4cb38-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="4cb38-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cb38-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="4cb38-106">Column</span></span></th>
<th><span data-ttu-id="4cb38-107">Typ</span><span class="sxs-lookup"><span data-stu-id="4cb38-107">Type</span></span></th>
<th><span data-ttu-id="4cb38-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cb38-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-109">prinID</span><span class="sxs-lookup"><span data-stu-id="4cb38-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="4cb38-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4cb38-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4cb38-111">Die Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="4cb38-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="4cb38-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="4cb38-113">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4cb38-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="4cb38-114">Die GUID des Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="4cb38-114">Principal GUID.</span></span> <span data-ttu-id="4cb38-115">Dies wird weitgehend als alternativer Primärschlüssel verwendet, da die Bedeutung in den Active Directory-Domänendienste Raum überschreitet.</span><span class="sxs-lookup"><span data-stu-id="4cb38-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="4cb38-116">(Die GUID für einen zwischengespeicherten Prinzipal ist mit der entsprechenden Objekt-GUID in Active Directory identisch.)</span><span class="sxs-lookup"><span data-stu-id="4cb38-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="4cb38-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="4cb38-118">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="4cb38-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4cb38-p102">Der URI des Prinzipals. Für Benutzer wird das SIP-Schema verwendet, für fast alles andere das ma-grp-Schema.</span><span class="sxs-lookup"><span data-stu-id="4cb38-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-121">prinName</span><span class="sxs-lookup"><span data-stu-id="4cb38-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="4cb38-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4cb38-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4cb38-p103">Der allgemeine Name. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cb38-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="4cb38-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="4cb38-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4cb38-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4cb38-p104">Der Anzeigename. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cb38-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="4cb38-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="4cb38-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4cb38-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4cb38-p105">Der Firmenname. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cb38-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="4cb38-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="4cb38-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4cb38-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4cb38-p106">Die E-Mail-Adresse. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cb38-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="4cb38-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="4cb38-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="4cb38-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="4cb38-p107">Der Domänenname des Active Directory-Objekts, von dem der Prinzipal eine zwischengespeicherte Version ist. Kann für Typen, die keine Active Directory-Objekte sind (z. B. Systembenutzer), null sein.</span><span class="sxs-lookup"><span data-stu-id="4cb38-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="4cb38-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="4cb38-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4cb38-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4cb38-p108">Der Benutzerprinzipalname (User Principal Name, UPN) des Benutzers. Wird nur von regulären Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cb38-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="4cb38-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="4cb38-146">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="4cb38-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4cb38-147">0: Der Prinzipal ist aktiv.</span><span class="sxs-lookup"><span data-stu-id="4cb38-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="4cb38-148">1: Der Prinzipal ist deaktiviert, weil die SIP-Funktionen für den Benutzer deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4cb38-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="4cb38-149">2: Der Prinzipal wird gelöscht, da das zugehörige AD-Objekt gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="4cb38-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="4cb38-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="4cb38-151">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4cb38-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4cb38-152">Der Prinzipaltyp (aus der Tabelle „tblPrincipalType“).</span><span class="sxs-lookup"><span data-stu-id="4cb38-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="4cb38-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="4cb38-154">Int</span><span class="sxs-lookup"><span data-stu-id="4cb38-154">Int</span></span></p></td>
<td><p><span data-ttu-id="4cb38-155">Lync-Poolzuweisung für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="4cb38-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="4cb38-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="4cb38-157">Int</span><span class="sxs-lookup"><span data-stu-id="4cb38-157">Int</span></span></p></td>
<td><p><span data-ttu-id="4cb38-158">Server Richtlinienwert für beständigen Chat für Benutzer, wenn die Transpondertyp Richtlinie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4cb38-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="4cb38-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="4cb38-160">int</span><span class="sxs-lookup"><span data-stu-id="4cb38-160">int</span></span></p></td>
<td><p><span data-ttu-id="4cb38-161">Die Prinzipal-ID des Erstellers.</span><span class="sxs-lookup"><span data-stu-id="4cb38-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="4cb38-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="4cb38-163">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4cb38-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4cb38-164">Der Zeitstempel für den Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="4cb38-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="4cb38-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="4cb38-166">int</span><span class="sxs-lookup"><span data-stu-id="4cb38-166">int</span></span></p></td>
<td><p><span data-ttu-id="4cb38-167">Die ID des Prinzipals, der dieses Element zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="4cb38-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="4cb38-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="4cb38-169">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="4cb38-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4cb38-170">Der Zeitstempel für die letzte Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="4cb38-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="4cb38-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="4cb38-172">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="4cb38-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="4cb38-173">Datum und Uhrzeit der letzten Aktualisierung der Active Directory-Synchronisierung für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="4cb38-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4cb38-174">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="4cb38-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cb38-175">Spalte</span><span class="sxs-lookup"><span data-stu-id="4cb38-175">Column</span></span></th>
<th><span data-ttu-id="4cb38-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cb38-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cb38-177">prinID</span><span class="sxs-lookup"><span data-stu-id="4cb38-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="4cb38-178">Der Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="4cb38-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cb38-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="4cb38-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="4cb38-180">Fremdschlüssel mit Suche in der Tabelle „ tblPrincipalType.ptypeID“.</span><span class="sxs-lookup"><span data-stu-id="4cb38-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

