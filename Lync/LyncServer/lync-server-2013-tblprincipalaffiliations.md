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
ms.openlocfilehash: 0a57e4a3c7a5fdcc1825c140cb6e26f8cede8dc1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="b92f8-102">tblPrincipalAffiliations in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b92f8-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b92f8-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b92f8-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b92f8-104">tblPrincipalAffiliations enthält die Haupt Zuordnungen, in denen Mitgliedschaften an Standorten, einschließlich Active Directory-Domänendienste Sicherheitsgruppen, in Active Directory Containern in Domänen beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b92f8-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="b92f8-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="b92f8-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b92f8-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="b92f8-106">Column</span></span></th>
<th><span data-ttu-id="b92f8-107">Typ</span><span class="sxs-lookup"><span data-stu-id="b92f8-107">Type</span></span></th>
<th><span data-ttu-id="b92f8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b92f8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-109">principalID</span><span class="sxs-lookup"><span data-stu-id="b92f8-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="b92f8-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b92f8-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b92f8-111">ID des zugeordneten Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="b92f8-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="b92f8-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="b92f8-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b92f8-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p101">ID des Prinzipals, die für die Zuordnung steht. Jeder Prinzipal (ausgenommen system-user-types) verfügt auch über eine Selbstzuordnung.</span><span class="sxs-lookup"><span data-stu-id="b92f8-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-116">Index</span><span class="sxs-lookup"><span data-stu-id="b92f8-116">index</span></span></p></td>
<td><p><span data-ttu-id="b92f8-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b92f8-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b92f8-118">Index.</span><span class="sxs-lookup"><span data-stu-id="b92f8-118">Index.</span></span> <span data-ttu-id="b92f8-119">Der Wert für Self-Affiliations ist-1, und bei den anderen Zuordnungen steigt er nacheinander von 1 innerhalb der einzelnen &lt;affiliationId&gt; -Buckets an.</span><span class="sxs-lookup"><span data-stu-id="b92f8-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="b92f8-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="b92f8-121">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b92f8-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b92f8-p103">Prinzipal, der die letzte Aktualisierung durchführte. Der Wert ist in der Regel 1, was der Active Directory-Synchronisierung entspricht.</span><span class="sxs-lookup"><span data-stu-id="b92f8-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b92f8-124">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b92f8-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b92f8-125">Spalten</span><span class="sxs-lookup"><span data-stu-id="b92f8-125">Columns</span></span></th>
<th><span data-ttu-id="b92f8-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b92f8-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-127">&lt;Prinzipal-, Index-, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="b92f8-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b92f8-128">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="b92f8-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92f8-129">principalID</span><span class="sxs-lookup"><span data-stu-id="b92f8-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="b92f8-130">Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b92f8-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92f8-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="b92f8-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="b92f8-132">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle</span><span class="sxs-lookup"><span data-stu-id="b92f8-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

