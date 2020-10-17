---
title: 'Lync Server 2013: tblPrincipalInvites'
description: 'Lync Server 2013: tblPrincipalInvites.'
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
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564671"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="e3136-103">tblPrincipalInvites in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3136-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3136-104">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="e3136-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="e3136-105">tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten, für die die Funktion der automatischen Einladung (Auto-Invite) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e3136-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="e3136-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="e3136-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3136-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="e3136-107">Column</span></span></th>
<th><span data-ttu-id="e3136-108">Typ</span><span class="sxs-lookup"><span data-stu-id="e3136-108">Type</span></span></th>
<th><span data-ttu-id="e3136-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3136-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3136-110">prinID</span><span class="sxs-lookup"><span data-stu-id="e3136-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="e3136-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e3136-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e3136-112">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="e3136-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3136-113">invID</span><span class="sxs-lookup"><span data-stu-id="e3136-113">invID</span></span></p></td>
<td><p><span data-ttu-id="e3136-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e3136-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e3136-115">Eindeutige fortlaufende Zahl (pro Prinzipal-ID), generiert von der tblLastInviteId-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e3136-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3136-116">nodeID</span><span class="sxs-lookup"><span data-stu-id="e3136-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e3136-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e3136-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e3136-118">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="e3136-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3136-119">createdOn</span><span class="sxs-lookup"><span data-stu-id="e3136-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="e3136-120">datetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e3136-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="e3136-121">Zeitpunkt des Erstellens.</span><span class="sxs-lookup"><span data-stu-id="e3136-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e3136-122">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="e3136-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3136-123">Spalte</span><span class="sxs-lookup"><span data-stu-id="e3136-123">Column</span></span></th>
<th><span data-ttu-id="e3136-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3136-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3136-125">&lt;prinID, Knoten-Nr&gt;</span><span class="sxs-lookup"><span data-stu-id="e3136-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e3136-126">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="e3136-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3136-127">prinID</span><span class="sxs-lookup"><span data-stu-id="e3136-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="e3136-128">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e3136-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3136-129">nodeID</span><span class="sxs-lookup"><span data-stu-id="e3136-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e3136-130">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e3136-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

