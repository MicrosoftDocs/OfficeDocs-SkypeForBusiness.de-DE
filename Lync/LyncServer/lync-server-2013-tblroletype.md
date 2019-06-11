---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="cceb0-102">tblRoleType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cceb0-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cceb0-103">_**Letztes Änderungsdatum des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="cceb0-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="cceb0-104">tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und zugehörigen Berechtigungssätzen.</span><span class="sxs-lookup"><span data-stu-id="cceb0-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="cceb0-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="cceb0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cceb0-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="cceb0-106">Column</span></span></th>
<th><span data-ttu-id="cceb0-107">Typ</span><span class="sxs-lookup"><span data-stu-id="cceb0-107">Type</span></span></th>
<th><span data-ttu-id="cceb0-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cceb0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cceb0-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="cceb0-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="cceb0-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cceb0-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cceb0-111">ID des Rollentyps.</span><span class="sxs-lookup"><span data-stu-id="cceb0-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cceb0-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="cceb0-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="cceb0-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cceb0-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="cceb0-114">Beschreibung des Rollentyps.</span><span class="sxs-lookup"><span data-stu-id="cceb0-114">Role type description.</span></span> <span data-ttu-id="cceb0-115">Es gibt vier verfügbare Rollen:</span><span class="sxs-lookup"><span data-stu-id="cceb0-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="cceb0-116">Mitglied: Chatroom-Mitglied</span><span class="sxs-lookup"><span data-stu-id="cceb0-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="cceb0-117">Manager: Chat Room Manager</span><span class="sxs-lookup"><span data-stu-id="cceb0-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="cceb0-118">Geäußert: Referent für einen Chatroom für Auditorium</span><span class="sxs-lookup"><span data-stu-id="cceb0-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="cceb0-119">Creator: kann Chatrooms erstellen</span><span class="sxs-lookup"><span data-stu-id="cceb0-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cceb0-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="cceb0-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="cceb0-121">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cceb0-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="cceb0-122">Der Berechtigungssatz für die Rolle.</span><span class="sxs-lookup"><span data-stu-id="cceb0-122">Permission set for the role.</span></span> <span data-ttu-id="cceb0-123">Die verwendeten Bits sind:</span><span class="sxs-lookup"><span data-stu-id="cceb0-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cceb0-124">2: true, wenn die Rolle Knoten verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="cceb0-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="cceb0-125">4: true, wenn die Rolle untergeordnete Knoten erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cceb0-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="cceb0-126">7: true, wenn die Rolle einem Chatroom (oder Chatrooms einer Kategorie) beitreten kann.</span><span class="sxs-lookup"><span data-stu-id="cceb0-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="cceb0-127">8: true, wenn die Rolle in einem Chatroom (oder in Chatrooms einer Kategorie) chatten kann.</span><span class="sxs-lookup"><span data-stu-id="cceb0-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="cceb0-128">10: true, wenn die Rolle das Chat-Protokoll lesen kann, selbst wenn Sie nicht zu einem Chatroom gehört.</span><span class="sxs-lookup"><span data-stu-id="cceb0-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="cceb0-129">11: true, wenn die Rolle den Chatroom sehen kann.</span><span class="sxs-lookup"><span data-stu-id="cceb0-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="cceb0-130">(Dies wird durch Faktoren wie Bereich und Sichtbarkeit weiter verfeinert.)</span><span class="sxs-lookup"><span data-stu-id="cceb0-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="cceb0-131">12: true, wenn die Rolle in einem Auditorium-Chatroom chatten kann.</span><span class="sxs-lookup"><span data-stu-id="cceb0-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="cceb0-132">13: true, wenn die Rolle Sichtbarkeitsregeln beim Anzeigen von Knoten umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="cceb0-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="cceb0-133">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="cceb0-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cceb0-134">Spalte</span><span class="sxs-lookup"><span data-stu-id="cceb0-134">Column</span></span></th>
<th><span data-ttu-id="cceb0-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cceb0-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cceb0-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="cceb0-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="cceb0-137">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="cceb0-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

