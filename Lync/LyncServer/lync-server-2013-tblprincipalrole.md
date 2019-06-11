---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="6f1b0-102">tblPrincipalRole in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f1b0-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f1b0-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6f1b0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6f1b0-104">tblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="6f1b0-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="6f1b0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f1b0-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="6f1b0-106">Column</span></span></th>
<th><span data-ttu-id="6f1b0-107">Typ</span><span class="sxs-lookup"><span data-stu-id="6f1b0-107">Type</span></span></th>
<th><span data-ttu-id="6f1b0-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f1b0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f1b0-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="6f1b0-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="6f1b0-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-111">Die Knoten-ID, auf die sich die Rolle bezieht.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1b0-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="6f1b0-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="6f1b0-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-114">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1b0-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="6f1b0-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="6f1b0-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-117">Rollentyp-ID (aus tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="6f1b0-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1b0-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="6f1b0-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-119">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="6f1b0-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-120">Die ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6f1b0-121">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="6f1b0-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f1b0-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="6f1b0-122">Column</span></span></th>
<th><span data-ttu-id="6f1b0-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f1b0-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f1b0-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="6f1b0-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="6f1b0-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1b0-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="6f1b0-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-127">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="6f1b0-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1b0-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="6f1b0-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-129">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1b0-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="6f1b0-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="6f1b0-131">Fremdschlüssel mit Lookup in der tblRoleType. rtypeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

