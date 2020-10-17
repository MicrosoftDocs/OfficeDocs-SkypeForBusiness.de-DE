---
title: 'Lync Server 2013: tblNode'
description: 'Lync Server 2013: tblNode.'
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
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547551"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="7ce90-103">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ce90-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ce90-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7ce90-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7ce90-105">tblNode enthält die Objektstruktur (mit Knoten der Kategorie oder des Chatrooms), die in der lync Server 2013-Systemsteuerung und administrativen Cmdlets verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="7ce90-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="7ce90-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="7ce90-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ce90-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="7ce90-107">Column</span></span></th>
<th><span data-ttu-id="7ce90-108">Typ</span><span class="sxs-lookup"><span data-stu-id="7ce90-108">Type</span></span></th>
<th><span data-ttu-id="7ce90-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ce90-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="7ce90-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="7ce90-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-112">Knoten-ID (eindeutige Nummer).</span><span class="sxs-lookup"><span data-stu-id="7ce90-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-113">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="7ce90-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="7ce90-114">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7ce90-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-115">Knoten-GUID.</span><span class="sxs-lookup"><span data-stu-id="7ce90-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-116">parentID</span><span class="sxs-lookup"><span data-stu-id="7ce90-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="7ce90-117">int</span><span class="sxs-lookup"><span data-stu-id="7ce90-117">int</span></span></p></td>
<td><p><span data-ttu-id="7ce90-p101">Knoten-ID des übergeordneten Elements. Der Stammknoten (mit ID 1) gilt selbst als übergeordnetes Element.</span><span class="sxs-lookup"><span data-stu-id="7ce90-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-120">NodeType</span><span class="sxs-lookup"><span data-stu-id="7ce90-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="7ce90-121">bit, not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-122">"True" wenn der Knoten eine Kategorie ist.</span><span class="sxs-lookup"><span data-stu-id="7ce90-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="7ce90-123">"False" wenn der Knoten ein Chatroom ist.</span><span class="sxs-lookup"><span data-stu-id="7ce90-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-124">nodeName</span><span class="sxs-lookup"><span data-stu-id="7ce90-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="7ce90-125">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-126">Knotenname</span><span class="sxs-lookup"><span data-stu-id="7ce90-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="7ce90-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="7ce90-128">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-129">Knotenbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="7ce90-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-130">invite</span><span class="sxs-lookup"><span data-stu-id="7ce90-130">invite</span></span></p></td>
<td><p><span data-ttu-id="7ce90-131">Bit</span><span class="sxs-lookup"><span data-stu-id="7ce90-131">bit</span></span></p></td>
<td><p><span data-ttu-id="7ce90-132">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="7ce90-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ce90-133">"True" wenn Einladungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7ce90-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="7ce90-134">"False" wenn Einladungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7ce90-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="7ce90-135">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="7ce90-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ce90-136">"False", wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie).</span><span class="sxs-lookup"><span data-stu-id="7ce90-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="7ce90-137">"Null" wenn die Einstellung zum Einladen von der übergeordneten Kategorie geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="7ce90-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-138">angemeldet</span><span class="sxs-lookup"><span data-stu-id="7ce90-138">logged</span></span></p></td>
<td><p><span data-ttu-id="7ce90-139">Bit</span><span class="sxs-lookup"><span data-stu-id="7ce90-139">bit</span></span></p></td>
<td><p><span data-ttu-id="7ce90-140">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="7ce90-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ce90-141">"True" wenn der Chatverlauf aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7ce90-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="7ce90-142">"False" wenn der Chatverlauf deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7ce90-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="7ce90-143">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="7ce90-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ce90-144">NULL.</span><span class="sxs-lookup"><span data-stu-id="7ce90-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-145">filePost</span><span class="sxs-lookup"><span data-stu-id="7ce90-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="7ce90-146">Bit</span><span class="sxs-lookup"><span data-stu-id="7ce90-146">bit</span></span></p></td>
<td><p><span data-ttu-id="7ce90-147">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="7ce90-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ce90-148">"True" wenn Dateiuploads zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="7ce90-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="7ce90-149">"False" wenn Dateiuploads nicht zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="7ce90-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="7ce90-150">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="7ce90-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ce90-151">NULL.</span><span class="sxs-lookup"><span data-stu-id="7ce90-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-152">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="7ce90-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="7ce90-153">bit, not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-p102">"True" wenn der Chatroom deaktiviert ist. Trifft nur auf Chatrooms zu. ("False" für Kategorien.)</span><span class="sxs-lookup"><span data-stu-id="7ce90-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-157">Verhalten</span><span class="sxs-lookup"><span data-stu-id="7ce90-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="7ce90-158">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-159">Verhalten (in der Tabelle "EnumValue" ermittelt):</span><span class="sxs-lookup"><span data-stu-id="7ce90-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="7ce90-160">4: Normal (normale Chatrooms)</span><span class="sxs-lookup"><span data-stu-id="7ce90-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="7ce90-161">5: Auditorium (Auditoriumchatrooms, nur Referenten können Beiträge veröffentlichen).</span><span class="sxs-lookup"><span data-stu-id="7ce90-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="7ce90-162">Trifft nur auf Chatrooms zu.</span><span class="sxs-lookup"><span data-stu-id="7ce90-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-163">visibility</span><span class="sxs-lookup"><span data-stu-id="7ce90-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="7ce90-164">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7ce90-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-165">Sichtbarkeit (in der Tabelle "EnumValue" ermittelt):</span><span class="sxs-lookup"><span data-stu-id="7ce90-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="7ce90-166">2: Privat</span><span class="sxs-lookup"><span data-stu-id="7ce90-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="7ce90-167">3: Bereich</span><span class="sxs-lookup"><span data-stu-id="7ce90-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="7ce90-168">6: Offen</span><span class="sxs-lookup"><span data-stu-id="7ce90-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="7ce90-169">Trifft nur auf Chatrooms zu.</span><span class="sxs-lookup"><span data-stu-id="7ce90-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-170">siopID</span><span class="sxs-lookup"><span data-stu-id="7ce90-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="7ce90-171">GUID</span><span class="sxs-lookup"><span data-stu-id="7ce90-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="7ce90-p103">Add-In-GUID, falls diesem Chatroom ein Add-In zugeordnet ist. (Kategorien sind keine Add-Ins zugeordnet.)</span><span class="sxs-lookup"><span data-stu-id="7ce90-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="7ce90-174">Die Add-In-Informationen werden in der Tabelle "SiopWhiteList" gesucht.</span><span class="sxs-lookup"><span data-stu-id="7ce90-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="7ce90-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="7ce90-176">int, not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-177">ID des Prinzipals, der diesen Knoten erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="7ce90-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="7ce90-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="7ce90-179">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-180">Zeitstempel der Knotenerstellung.</span><span class="sxs-lookup"><span data-stu-id="7ce90-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="7ce90-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="7ce90-182">int, not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-183">ID des Prinzipals, der die letzte Aktualisierung dieses Knotens vorgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="7ce90-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="7ce90-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="7ce90-185">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="7ce90-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="7ce90-186">Zeitstempel der letzten Aktualisierung dieses Knotens.</span><span class="sxs-lookup"><span data-stu-id="7ce90-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="7ce90-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="7ce90-188">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="7ce90-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="7ce90-p104">Zeitpunkt des letzten Löschvorgangs (Entfernung von Bereichen aus der Tabelle "tblScopedPrincipal" und Rollen aus der Tabelle "tblPrincipalRole"), der Auswirkungen auf diesen Knoten hatte. Wird von der internen Cache-Aktualisierung des Chatdiensts verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ce90-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7ce90-191">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="7ce90-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ce90-192">Spalte</span><span class="sxs-lookup"><span data-stu-id="7ce90-192">Column</span></span></th>
<th><span data-ttu-id="7ce90-193">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ce90-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-194">nodeID</span><span class="sxs-lookup"><span data-stu-id="7ce90-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="7ce90-195">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="7ce90-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-196">Verhalten</span><span class="sxs-lookup"><span data-stu-id="7ce90-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="7ce90-197">Fremdschlüssel mit Suche in der Tabelle "tblEnumValue.valueID".</span><span class="sxs-lookup"><span data-stu-id="7ce90-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-198">visibility</span><span class="sxs-lookup"><span data-stu-id="7ce90-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="7ce90-199">Fremdschlüssel mit Suche in der Tabelle "tblEnumValue.valueID".</span><span class="sxs-lookup"><span data-stu-id="7ce90-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ce90-200">parentID</span><span class="sxs-lookup"><span data-stu-id="7ce90-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="7ce90-201">Fremdschlüssel mit Suche in der Tabelle "tblNode.nodeID".</span><span class="sxs-lookup"><span data-stu-id="7ce90-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ce90-202">siopID</span><span class="sxs-lookup"><span data-stu-id="7ce90-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="7ce90-203">Fremdschlüssel mit Suche in der Tabelle "tblSiopWhiteList.siopId".</span><span class="sxs-lookup"><span data-stu-id="7ce90-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

