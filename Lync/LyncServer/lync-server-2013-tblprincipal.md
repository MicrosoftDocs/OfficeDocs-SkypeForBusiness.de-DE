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
ms.openlocfilehash: 5e4b0c8154429fa68bc05e757130e0b92a47e65c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523762"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="4a69f-102">tblPrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a69f-102">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a69f-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4a69f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4a69f-104">Die Tabelle „tblPrincipal“ enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="4a69f-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="4a69f-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="4a69f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a69f-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="4a69f-106">Column</span></span></th>
<th><span data-ttu-id="4a69f-107">Typ</span><span class="sxs-lookup"><span data-stu-id="4a69f-107">Type</span></span></th>
<th><span data-ttu-id="4a69f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a69f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="4a69f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="4a69f-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4a69f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4a69f-111">Die Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="4a69f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="4a69f-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="4a69f-113">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4a69f-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="4a69f-114">Die GUID des Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="4a69f-114">Principal GUID.</span></span> <span data-ttu-id="4a69f-115">Dies wird weitgehend als alternativer Primärschlüssel verwendet, da die Bedeutung in den Active Directory-Domänendienste Raum überschreitet.</span><span class="sxs-lookup"><span data-stu-id="4a69f-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="4a69f-116">(Die GUID für einen zwischengespeicherten Prinzipal ist mit der entsprechenden Objekt-GUID in Active Directory identisch.)</span><span class="sxs-lookup"><span data-stu-id="4a69f-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="4a69f-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="4a69f-118">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="4a69f-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4a69f-p102">Der URI des Prinzipals. Für Benutzer wird das SIP-Schema verwendet, für fast alles andere das ma-grp-Schema.</span><span class="sxs-lookup"><span data-stu-id="4a69f-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-121">prinName</span><span class="sxs-lookup"><span data-stu-id="4a69f-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="4a69f-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4a69f-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4a69f-p103">Der allgemeine Name. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a69f-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="4a69f-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="4a69f-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4a69f-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4a69f-p104">Der Anzeigename. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a69f-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="4a69f-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="4a69f-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4a69f-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4a69f-p105">Der Firmenname. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a69f-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="4a69f-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="4a69f-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4a69f-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4a69f-p106">Die E-Mail-Adresse. Wird nur von Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a69f-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="4a69f-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="4a69f-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="4a69f-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="4a69f-p107">Der Domänenname des Active Directory-Objekts, von dem der Prinzipal eine zwischengespeicherte Version ist. Kann für Typen, die keine Active Directory-Objekte sind (z. B. Systembenutzer), null sein.</span><span class="sxs-lookup"><span data-stu-id="4a69f-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="4a69f-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="4a69f-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4a69f-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="4a69f-p108">Der Benutzerprinzipalname (User Principal Name, UPN) des Benutzers. Wird nur von regulären Benutzertypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a69f-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="4a69f-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="4a69f-146">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="4a69f-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4a69f-147">0: Der Prinzipal ist aktiv.</span><span class="sxs-lookup"><span data-stu-id="4a69f-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="4a69f-148">1: Der Prinzipal ist deaktiviert, weil die SIP-Funktionen für den Benutzer deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4a69f-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="4a69f-149">2: Der Prinzipal wird gelöscht, da das zugehörige AD-Objekt gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="4a69f-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="4a69f-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="4a69f-151">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4a69f-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4a69f-152">Der Prinzipaltyp (aus der Tabelle „tblPrincipalType“).</span><span class="sxs-lookup"><span data-stu-id="4a69f-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="4a69f-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="4a69f-154">Int</span><span class="sxs-lookup"><span data-stu-id="4a69f-154">Int</span></span></p></td>
<td><p><span data-ttu-id="4a69f-155">Lync-Poolzuweisung für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="4a69f-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="4a69f-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="4a69f-157">Int</span><span class="sxs-lookup"><span data-stu-id="4a69f-157">Int</span></span></p></td>
<td><p><span data-ttu-id="4a69f-158">Server Richtlinienwert für beständigen Chat für Benutzer, wenn die Transpondertyp Richtlinie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4a69f-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="4a69f-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="4a69f-160">int</span><span class="sxs-lookup"><span data-stu-id="4a69f-160">int</span></span></p></td>
<td><p><span data-ttu-id="4a69f-161">Die Prinzipal-ID des Erstellers.</span><span class="sxs-lookup"><span data-stu-id="4a69f-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="4a69f-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="4a69f-163">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="4a69f-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4a69f-164">Der Zeitstempel für den Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="4a69f-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="4a69f-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="4a69f-166">int</span><span class="sxs-lookup"><span data-stu-id="4a69f-166">int</span></span></p></td>
<td><p><span data-ttu-id="4a69f-167">Die ID des Prinzipals, der dieses Element zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="4a69f-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="4a69f-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="4a69f-169">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="4a69f-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4a69f-170">Der Zeitstempel für die letzte Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="4a69f-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="4a69f-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="4a69f-172">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="4a69f-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="4a69f-173">Datum und Uhrzeit der letzten Aktualisierung der Active Directory-Synchronisierung für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="4a69f-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4a69f-174">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="4a69f-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a69f-175">Spalte</span><span class="sxs-lookup"><span data-stu-id="4a69f-175">Column</span></span></th>
<th><span data-ttu-id="4a69f-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a69f-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a69f-177">prinID</span><span class="sxs-lookup"><span data-stu-id="4a69f-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="4a69f-178">Der Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="4a69f-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a69f-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="4a69f-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="4a69f-180">Fremdschlüssel mit Suche in der Tabelle „ tblPrincipalType.ptypeID“.</span><span class="sxs-lookup"><span data-stu-id="4a69f-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

