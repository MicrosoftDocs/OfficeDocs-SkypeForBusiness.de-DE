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
ms.openlocfilehash: ece3601ad32181d0700adbf3eb0d81eca7541b45
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="d8587-102">tblPrincipalInvites in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8587-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8587-103">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="d8587-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="d8587-104">tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten, für die die Funktion der automatischen Einladung (Auto-Invite) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d8587-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="d8587-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="d8587-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8587-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="d8587-106">Column</span></span></th>
<th><span data-ttu-id="d8587-107">Typ</span><span class="sxs-lookup"><span data-stu-id="d8587-107">Type</span></span></th>
<th><span data-ttu-id="d8587-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8587-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8587-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d8587-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="d8587-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="d8587-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d8587-111">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="d8587-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8587-112">invID</span><span class="sxs-lookup"><span data-stu-id="d8587-112">invID</span></span></p></td>
<td><p><span data-ttu-id="d8587-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d8587-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d8587-114">Eindeutige fortlaufende Zahl (pro Prinzipal-ID), generiert von der tblLastInviteId-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d8587-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8587-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="d8587-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d8587-116">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d8587-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d8587-117">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="d8587-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8587-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="d8587-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="d8587-119">datetime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d8587-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="d8587-120">Zeitpunkt des Erstellens.</span><span class="sxs-lookup"><span data-stu-id="d8587-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d8587-121">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="d8587-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8587-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="d8587-122">Column</span></span></th>
<th><span data-ttu-id="d8587-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8587-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8587-124">&lt;prinID, Knoten-Nr&gt;</span><span class="sxs-lookup"><span data-stu-id="d8587-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d8587-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="d8587-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8587-126">prinID</span><span class="sxs-lookup"><span data-stu-id="d8587-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="d8587-127">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d8587-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8587-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="d8587-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d8587-129">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d8587-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

