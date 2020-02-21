---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 459b5393f255ade4e510f17c11beccf2f38f7cfc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="90d3a-102">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90d3a-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90d3a-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="90d3a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="90d3a-104">tblNode enthält die Objektstruktur (mit Knoten der Kategorie oder des Chatrooms), die in der lync Server 2013-Systemsteuerung und administrativen Cmdlets verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="90d3a-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="90d3a-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="90d3a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d3a-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="90d3a-106">Column</span></span></th>
<th><span data-ttu-id="90d3a-107">Typ</span><span class="sxs-lookup"><span data-stu-id="90d3a-107">Type</span></span></th>
<th><span data-ttu-id="90d3a-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d3a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="90d3a-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="90d3a-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="90d3a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-111">Knoten-ID (eindeutige Nummer).</span><span class="sxs-lookup"><span data-stu-id="90d3a-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="90d3a-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="90d3a-113">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="90d3a-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-114">Knoten-GUID.</span><span class="sxs-lookup"><span data-stu-id="90d3a-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-115">parentID</span><span class="sxs-lookup"><span data-stu-id="90d3a-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="90d3a-116">int</span><span class="sxs-lookup"><span data-stu-id="90d3a-116">int</span></span></p></td>
<td><p><span data-ttu-id="90d3a-p101">Knoten-ID des übergeordneten Elements. Der Stammknoten (mit ID 1) gilt selbst als übergeordnetes Element.</span><span class="sxs-lookup"><span data-stu-id="90d3a-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-119">NodeType</span><span class="sxs-lookup"><span data-stu-id="90d3a-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="90d3a-120">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="90d3a-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-121">"True" wenn der Knoten eine Kategorie ist.</span><span class="sxs-lookup"><span data-stu-id="90d3a-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="90d3a-122">"False" wenn der Knoten ein Chatroom ist.</span><span class="sxs-lookup"><span data-stu-id="90d3a-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="90d3a-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="90d3a-124">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="90d3a-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-125">Knotenname</span><span class="sxs-lookup"><span data-stu-id="90d3a-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="90d3a-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="90d3a-127">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="90d3a-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-128">Knotenbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="90d3a-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-129">invite</span><span class="sxs-lookup"><span data-stu-id="90d3a-129">invite</span></span></p></td>
<td><p><span data-ttu-id="90d3a-130">Bit</span><span class="sxs-lookup"><span data-stu-id="90d3a-130">bit</span></span></p></td>
<td><p><span data-ttu-id="90d3a-131">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="90d3a-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="90d3a-132">"True" wenn Einladungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="90d3a-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="90d3a-133">"False" wenn Einladungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="90d3a-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="90d3a-134">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="90d3a-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="90d3a-135">"False", wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie).</span><span class="sxs-lookup"><span data-stu-id="90d3a-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="90d3a-136">"Null" wenn die Einstellung zum Einladen von der übergeordneten Kategorie geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="90d3a-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-137">angemeldet</span><span class="sxs-lookup"><span data-stu-id="90d3a-137">logged</span></span></p></td>
<td><p><span data-ttu-id="90d3a-138">Bit</span><span class="sxs-lookup"><span data-stu-id="90d3a-138">bit</span></span></p></td>
<td><p><span data-ttu-id="90d3a-139">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="90d3a-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="90d3a-140">"True" wenn der Chatverlauf aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="90d3a-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="90d3a-141">"False" wenn der Chatverlauf deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="90d3a-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="90d3a-142">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="90d3a-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="90d3a-143">NULL.</span><span class="sxs-lookup"><span data-stu-id="90d3a-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-144">filePost</span><span class="sxs-lookup"><span data-stu-id="90d3a-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="90d3a-145">Bit</span><span class="sxs-lookup"><span data-stu-id="90d3a-145">bit</span></span></p></td>
<td><p><span data-ttu-id="90d3a-146">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="90d3a-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="90d3a-147">"True" wenn Dateiuploads zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="90d3a-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="90d3a-148">"False" wenn Dateiuploads nicht zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="90d3a-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="90d3a-149">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="90d3a-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="90d3a-150">NULL.</span><span class="sxs-lookup"><span data-stu-id="90d3a-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-151">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="90d3a-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="90d3a-152">bit, not null</span><span class="sxs-lookup"><span data-stu-id="90d3a-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-p102">"True" wenn der Chatroom deaktiviert ist. Trifft nur auf Chatrooms zu. ("False" für Kategorien.)</span><span class="sxs-lookup"><span data-stu-id="90d3a-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-156">Verhalten</span><span class="sxs-lookup"><span data-stu-id="90d3a-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="90d3a-157">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="90d3a-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-158">Verhalten (in der Tabelle "EnumValue" ermittelt):</span><span class="sxs-lookup"><span data-stu-id="90d3a-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="90d3a-159">4: Normal (normale Chatrooms)</span><span class="sxs-lookup"><span data-stu-id="90d3a-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="90d3a-160">5: Auditorium (Auditoriumchatrooms, nur Referenten können Beiträge veröffentlichen).</span><span class="sxs-lookup"><span data-stu-id="90d3a-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="90d3a-161">Trifft nur auf Chatrooms zu.</span><span class="sxs-lookup"><span data-stu-id="90d3a-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-162">visibility</span><span class="sxs-lookup"><span data-stu-id="90d3a-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="90d3a-163">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="90d3a-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-164">Sichtbarkeit (in der Tabelle "EnumValue" ermittelt):</span><span class="sxs-lookup"><span data-stu-id="90d3a-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="90d3a-165">2: Privat</span><span class="sxs-lookup"><span data-stu-id="90d3a-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="90d3a-166">3: Bereich</span><span class="sxs-lookup"><span data-stu-id="90d3a-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="90d3a-167">6: Offen</span><span class="sxs-lookup"><span data-stu-id="90d3a-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="90d3a-168">Trifft nur auf Chatrooms zu.</span><span class="sxs-lookup"><span data-stu-id="90d3a-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-169">siopID</span><span class="sxs-lookup"><span data-stu-id="90d3a-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="90d3a-170">GUID</span><span class="sxs-lookup"><span data-stu-id="90d3a-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="90d3a-p103">Add-In-GUID, falls diesem Chatroom ein Add-In zugeordnet ist. (Kategorien sind keine Add-Ins zugeordnet.)</span><span class="sxs-lookup"><span data-stu-id="90d3a-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="90d3a-173">Die Add-In-Informationen werden in der Tabelle "SiopWhiteList" gesucht.</span><span class="sxs-lookup"><span data-stu-id="90d3a-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="90d3a-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="90d3a-175">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="90d3a-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-176">ID des Prinzipals, der diesen Knoten erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="90d3a-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="90d3a-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="90d3a-178">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="90d3a-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-179">Zeitstempel der Knotenerstellung.</span><span class="sxs-lookup"><span data-stu-id="90d3a-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="90d3a-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="90d3a-181">int, not null</span><span class="sxs-lookup"><span data-stu-id="90d3a-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-182">ID des Prinzipals, der die letzte Aktualisierung dieses Knotens vorgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="90d3a-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="90d3a-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="90d3a-184">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="90d3a-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="90d3a-185">Zeitstempel der letzten Aktualisierung dieses Knotens.</span><span class="sxs-lookup"><span data-stu-id="90d3a-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="90d3a-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="90d3a-187">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="90d3a-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="90d3a-p104">Zeitpunkt des letzten Löschvorgangs (Entfernung von Bereichen aus der Tabelle "tblScopedPrincipal" und Rollen aus der Tabelle "tblPrincipalRole"), der Auswirkungen auf diesen Knoten hatte. Wird von der internen Cache-Aktualisierung des Chatdiensts verwendet.</span><span class="sxs-lookup"><span data-stu-id="90d3a-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="90d3a-190">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="90d3a-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d3a-191">Spalte</span><span class="sxs-lookup"><span data-stu-id="90d3a-191">Column</span></span></th>
<th><span data-ttu-id="90d3a-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d3a-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="90d3a-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="90d3a-194">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="90d3a-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-195">Verhalten</span><span class="sxs-lookup"><span data-stu-id="90d3a-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="90d3a-196">Fremdschlüssel mit Suche in der Tabelle "tblEnumValue.valueID".</span><span class="sxs-lookup"><span data-stu-id="90d3a-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-197">visibility</span><span class="sxs-lookup"><span data-stu-id="90d3a-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="90d3a-198">Fremdschlüssel mit Suche in der Tabelle "tblEnumValue.valueID".</span><span class="sxs-lookup"><span data-stu-id="90d3a-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d3a-199">parentID</span><span class="sxs-lookup"><span data-stu-id="90d3a-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="90d3a-200">Fremdschlüssel mit Suche in der Tabelle "tblNode.nodeID".</span><span class="sxs-lookup"><span data-stu-id="90d3a-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d3a-201">siopID</span><span class="sxs-lookup"><span data-stu-id="90d3a-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="90d3a-202">Fremdschlüssel mit Suche in der Tabelle "tblSiopWhiteList.siopId".</span><span class="sxs-lookup"><span data-stu-id="90d3a-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

