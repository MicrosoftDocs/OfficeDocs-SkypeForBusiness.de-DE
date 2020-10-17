---
title: 'Lync Server 2013: tblPrincipalAffiliations'
description: 'Lync Server 2013: tblPrincipalAffiliations.'
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
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547481"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="5efbc-103">tblPrincipalAffiliations in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5efbc-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5efbc-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5efbc-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5efbc-105">tblPrincipalAffiliations enthält die Haupt Zuordnungen, in denen Mitgliedschaften an Standorten, einschließlich Active Directory-Domänendienste Sicherheitsgruppen, in Active Directory Containern in Domänen beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="5efbc-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="5efbc-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="5efbc-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5efbc-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="5efbc-107">Column</span></span></th>
<th><span data-ttu-id="5efbc-108">Typ</span><span class="sxs-lookup"><span data-stu-id="5efbc-108">Type</span></span></th>
<th><span data-ttu-id="5efbc-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5efbc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5efbc-110">principalID</span><span class="sxs-lookup"><span data-stu-id="5efbc-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="5efbc-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5efbc-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5efbc-112">ID des zugeordneten Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="5efbc-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5efbc-113">affiliationID</span><span class="sxs-lookup"><span data-stu-id="5efbc-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="5efbc-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5efbc-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5efbc-p101">ID des Prinzipals, die für die Zuordnung steht. Jeder Prinzipal (ausgenommen system-user-types) verfügt auch über eine Selbstzuordnung.</span><span class="sxs-lookup"><span data-stu-id="5efbc-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5efbc-117">Index</span><span class="sxs-lookup"><span data-stu-id="5efbc-117">index</span></span></p></td>
<td><p><span data-ttu-id="5efbc-118">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5efbc-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5efbc-119">Index.</span><span class="sxs-lookup"><span data-stu-id="5efbc-119">Index.</span></span> <span data-ttu-id="5efbc-120">Der Wert für Self-Affiliations ist-1, und bei den anderen Zuordnungen steigt er nacheinander von 1 innerhalb der einzelnen &lt; affiliationId- &gt; Buckets an.</span><span class="sxs-lookup"><span data-stu-id="5efbc-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5efbc-121">updatedBy</span><span class="sxs-lookup"><span data-stu-id="5efbc-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="5efbc-122">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5efbc-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5efbc-p103">Prinzipal, der die letzte Aktualisierung durchführte. Der Wert ist in der Regel 1, was der Active Directory-Synchronisierung entspricht.</span><span class="sxs-lookup"><span data-stu-id="5efbc-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5efbc-125">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="5efbc-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5efbc-126">Spalten</span><span class="sxs-lookup"><span data-stu-id="5efbc-126">Columns</span></span></th>
<th><span data-ttu-id="5efbc-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5efbc-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5efbc-128">&lt;Prinzipal-, Index-, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="5efbc-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="5efbc-129">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="5efbc-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5efbc-130">principalID</span><span class="sxs-lookup"><span data-stu-id="5efbc-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="5efbc-131">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle</span><span class="sxs-lookup"><span data-stu-id="5efbc-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5efbc-132">affiliationID</span><span class="sxs-lookup"><span data-stu-id="5efbc-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="5efbc-133">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle</span><span class="sxs-lookup"><span data-stu-id="5efbc-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

