---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="373f1-102">tblPrincipalAffiliations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="373f1-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="373f1-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="373f1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="373f1-104">tblPrincipalAffiliations enthält die Haupt Zuordnungen, die Mitgliedschaften an Speicherorten beschreiben, einschließlich Sicherheitsgruppen für Active Directory-Domänendienste, in Active Directory-Containern in Domänen.</span><span class="sxs-lookup"><span data-stu-id="373f1-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="373f1-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="373f1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="373f1-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="373f1-106">Column</span></span></th>
<th><span data-ttu-id="373f1-107">Typ</span><span class="sxs-lookup"><span data-stu-id="373f1-107">Type</span></span></th>
<th><span data-ttu-id="373f1-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="373f1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="373f1-109">Prinzipal-Nr</span><span class="sxs-lookup"><span data-stu-id="373f1-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="373f1-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="373f1-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="373f1-111">Die ID des verbundenen Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="373f1-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f1-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="373f1-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="373f1-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="373f1-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="373f1-114">Die ID des Prinzipals, der die Zuordnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="373f1-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="373f1-115">Jeder Prinzipal (mit Ausnahme von System-User-Typen) hat ebenfalls eine Selbstzuordnung.</span><span class="sxs-lookup"><span data-stu-id="373f1-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f1-116">Index</span><span class="sxs-lookup"><span data-stu-id="373f1-116">index</span></span></p></td>
<td><p><span data-ttu-id="373f1-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="373f1-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="373f1-118">Index.</span><span class="sxs-lookup"><span data-stu-id="373f1-118">Index.</span></span> <span data-ttu-id="373f1-119">Der Wert für Self-Affiliations ist-1, und für die anderen Zuordnungen wird er sequenziell von 1 innerhalb der einzelnen &lt;Prinzipal-affiliationId&gt; -Buckets erhöht.</span><span class="sxs-lookup"><span data-stu-id="373f1-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f1-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="373f1-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="373f1-121">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="373f1-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="373f1-122">Prinzipal, der das neueste Update durchführte.</span><span class="sxs-lookup"><span data-stu-id="373f1-122">Principal that did the latest update.</span></span> <span data-ttu-id="373f1-123">Dies ist normalerweise 1, was bedeutet, dass die Active Directory-Synchronisierung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="373f1-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="373f1-124">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="373f1-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="373f1-125">Spalten</span><span class="sxs-lookup"><span data-stu-id="373f1-125">Columns</span></span></th>
<th><span data-ttu-id="373f1-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="373f1-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="373f1-127">&lt;Prinzipal-, Index-, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="373f1-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="373f1-128">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="373f1-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f1-129">Prinzipal-Nr</span><span class="sxs-lookup"><span data-stu-id="373f1-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="373f1-130">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="373f1-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f1-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="373f1-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="373f1-132">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="373f1-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

