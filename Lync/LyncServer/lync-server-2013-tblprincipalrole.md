---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddab28b269cf2b720d6935fa6d50f4bf9ea3084a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="5ba84-102">tblPrincipalRole in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba84-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ba84-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5ba84-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5ba84-104">tblPrincipalRole enthält explizite Rollen, die Knoten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5ba84-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="5ba84-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="5ba84-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ba84-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="5ba84-106">Column</span></span></th>
<th><span data-ttu-id="5ba84-107">Typ</span><span class="sxs-lookup"><span data-stu-id="5ba84-107">Type</span></span></th>
<th><span data-ttu-id="5ba84-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ba84-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ba84-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5ba84-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="5ba84-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5ba84-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5ba84-111">Knoten-ID, auf die sich die Rolle bezieht.</span><span class="sxs-lookup"><span data-stu-id="5ba84-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba84-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5ba84-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="5ba84-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="5ba84-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5ba84-114">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="5ba84-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ba84-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5ba84-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="5ba84-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5ba84-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5ba84-117">Rollentyp-ID (von tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="5ba84-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba84-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5ba84-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="5ba84-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5ba84-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5ba84-120">ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="5ba84-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5ba84-121">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="5ba84-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ba84-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="5ba84-122">Column</span></span></th>
<th><span data-ttu-id="5ba84-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ba84-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ba84-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="5ba84-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="5ba84-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="5ba84-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba84-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5ba84-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="5ba84-127">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5ba84-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ba84-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5ba84-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="5ba84-129">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5ba84-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba84-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5ba84-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="5ba84-131">Fremdschlüssel mit Abfrage der tblRoleType.rtypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5ba84-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

