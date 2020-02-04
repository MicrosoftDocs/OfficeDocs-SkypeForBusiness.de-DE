---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75d842772c8c0e02352eacf7f80711aa79c29461
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="c2248-102">tblPrincipalInvites in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2248-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2248-103">_**Letztes Änderungsdatum des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="c2248-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="c2248-104">tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer für alle Knoten, bei denen die automatische Einladung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c2248-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="c2248-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="c2248-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2248-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="c2248-106">Column</span></span></th>
<th><span data-ttu-id="c2248-107">Typ</span><span class="sxs-lookup"><span data-stu-id="c2248-107">Type</span></span></th>
<th><span data-ttu-id="c2248-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2248-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2248-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c2248-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="c2248-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c2248-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c2248-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="c2248-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2248-112">invID</span><span class="sxs-lookup"><span data-stu-id="c2248-112">invID</span></span></p></td>
<td><p><span data-ttu-id="c2248-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c2248-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c2248-114">Eindeutige sequenzielle Zahl (pro Prinzipal-ID), die aus der tblLastInviteId-Tabelle generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c2248-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2248-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="c2248-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="c2248-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c2248-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c2248-117">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="c2248-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2248-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="c2248-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="c2248-119">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c2248-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="c2248-120">Zeitpunkt der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="c2248-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="c2248-121">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c2248-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2248-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="c2248-122">Column</span></span></th>
<th><span data-ttu-id="c2248-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2248-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2248-124">&lt;prinID, Knoten-Nr.&gt;</span><span class="sxs-lookup"><span data-stu-id="c2248-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="c2248-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="c2248-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2248-126">prinID</span><span class="sxs-lookup"><span data-stu-id="c2248-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="c2248-127">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c2248-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2248-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="c2248-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="c2248-129">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="c2248-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

