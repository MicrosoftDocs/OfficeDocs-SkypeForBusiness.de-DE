---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 721932aa2929930b3da742355a46c5e2066c5c83
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="93baf-102">tblRoleType in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93baf-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93baf-103">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="93baf-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="93baf-104">tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und ihren zugeordneten Berechtigungssätzen.</span><span class="sxs-lookup"><span data-stu-id="93baf-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="93baf-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="93baf-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93baf-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="93baf-106">Column</span></span></th>
<th><span data-ttu-id="93baf-107">Typ</span><span class="sxs-lookup"><span data-stu-id="93baf-107">Type</span></span></th>
<th><span data-ttu-id="93baf-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93baf-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93baf-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="93baf-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="93baf-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="93baf-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="93baf-111">Role Type ID.</span><span class="sxs-lookup"><span data-stu-id="93baf-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93baf-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="93baf-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="93baf-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="93baf-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="93baf-114">Beschreibung des Rollentyps.</span><span class="sxs-lookup"><span data-stu-id="93baf-114">Role type description.</span></span> <span data-ttu-id="93baf-115">Es gibt vier verfügbare Rollen:</span><span class="sxs-lookup"><span data-stu-id="93baf-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="93baf-116">Mitglied: Chat Room Member</span><span class="sxs-lookup"><span data-stu-id="93baf-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="93baf-117">Manager: Chat Raum Manager</span><span class="sxs-lookup"><span data-stu-id="93baf-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="93baf-118">Voiced: Referent für einen Auditorium-Chatroom</span><span class="sxs-lookup"><span data-stu-id="93baf-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="93baf-119">Creator: kann Chatrooms erstellen</span><span class="sxs-lookup"><span data-stu-id="93baf-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93baf-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="93baf-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="93baf-121">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="93baf-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="93baf-122">Berechtigungssatzes für die Rolle.</span><span class="sxs-lookup"><span data-stu-id="93baf-122">Permission set for the role.</span></span> <span data-ttu-id="93baf-123">Die verwendeten Bits sind:</span><span class="sxs-lookup"><span data-stu-id="93baf-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="93baf-124">2: true, wenn die Rolle Knoten verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="93baf-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="93baf-125">4: true, wenn die Rolle untergeordnete Knoten erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="93baf-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="93baf-126">7: true, wenn die Rolle einem Chatroom (oder Chatrooms für Kinder einer Kategorie) beitreten kann.</span><span class="sxs-lookup"><span data-stu-id="93baf-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="93baf-127">8: true, wenn die Rolle in einem Chatroom (oder in Chatrooms für Kinder einer Kategorie) chatten kann.</span><span class="sxs-lookup"><span data-stu-id="93baf-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="93baf-128">10: true, wenn die Rolle den Chatverlauf lesen kann, auch wenn Sie keinem Chatroom beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="93baf-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="93baf-129">11: true, wenn die Rolle den Chatroom sehen kann.</span><span class="sxs-lookup"><span data-stu-id="93baf-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="93baf-130">(Dies wird durch Faktoren wie Bereich und Sichtbarkeit weiter verfeinert.)</span><span class="sxs-lookup"><span data-stu-id="93baf-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="93baf-131">12: true, wenn die Rolle in einem Auditorium-Chatroom chatten kann.</span><span class="sxs-lookup"><span data-stu-id="93baf-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="93baf-132">13: true, wenn die Rolle Sichtbarkeitsregeln beim Anzeigen von Knoten umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="93baf-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="93baf-133">Key</span><span class="sxs-lookup"><span data-stu-id="93baf-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93baf-134">Spalte</span><span class="sxs-lookup"><span data-stu-id="93baf-134">Column</span></span></th>
<th><span data-ttu-id="93baf-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93baf-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93baf-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="93baf-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="93baf-137">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="93baf-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

