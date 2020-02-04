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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="09e72-102">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09e72-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09e72-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="09e72-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="09e72-104">tblNode enthält die Objektstruktur (mit Kategorien-oder Chatroom-Knoten), wie Sie in der lync Server 2013-Systemsteuerung und den administrativen Cmdlets verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="09e72-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="09e72-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="09e72-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09e72-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="09e72-106">Column</span></span></th>
<th><span data-ttu-id="09e72-107">Typ</span><span class="sxs-lookup"><span data-stu-id="09e72-107">Type</span></span></th>
<th><span data-ttu-id="09e72-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09e72-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09e72-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="09e72-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="09e72-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-111">Knoten-ID (eindeutige Nummer).</span><span class="sxs-lookup"><span data-stu-id="09e72-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="09e72-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="09e72-113">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-114">Knoten-GUID.</span><span class="sxs-lookup"><span data-stu-id="09e72-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-115">parentID</span><span class="sxs-lookup"><span data-stu-id="09e72-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="09e72-116">int</span><span class="sxs-lookup"><span data-stu-id="09e72-116">int</span></span></p></td>
<td><p><span data-ttu-id="09e72-117">Knoten-ID des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="09e72-117">Node ID of parent.</span></span> <span data-ttu-id="09e72-118">Der Stammknoten (mit ID 1) schließt sich ebenfalls als übergeordnetes Element ein.</span><span class="sxs-lookup"><span data-stu-id="09e72-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-119">NodeType</span><span class="sxs-lookup"><span data-stu-id="09e72-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="09e72-120">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-121">"True", wenn der Knoten eine Kategorie ist.</span><span class="sxs-lookup"><span data-stu-id="09e72-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="09e72-122">False, wenn es sich bei dem Knoten um einen Chatroom handelt.</span><span class="sxs-lookup"><span data-stu-id="09e72-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="09e72-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="09e72-124">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-125">Knotenname</span><span class="sxs-lookup"><span data-stu-id="09e72-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="09e72-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="09e72-127">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-128">Knotenbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="09e72-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-129">einladen</span><span class="sxs-lookup"><span data-stu-id="09e72-129">invite</span></span></p></td>
<td><p><span data-ttu-id="09e72-130">bit</span><span class="sxs-lookup"><span data-stu-id="09e72-130">bit</span></span></p></td>
<td><p><span data-ttu-id="09e72-131">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="09e72-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="09e72-132">True, wenn Einladungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="09e72-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="09e72-133">False, wenn Einladungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="09e72-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="09e72-134">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="09e72-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="09e72-135">False, wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie).</span><span class="sxs-lookup"><span data-stu-id="09e72-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="09e72-136">NULL, wenn die invites-Einstellung von der übergeordneten Kategorie geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="09e72-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-137">angemeldet</span><span class="sxs-lookup"><span data-stu-id="09e72-137">logged</span></span></p></td>
<td><p><span data-ttu-id="09e72-138">bit</span><span class="sxs-lookup"><span data-stu-id="09e72-138">bit</span></span></p></td>
<td><p><span data-ttu-id="09e72-139">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="09e72-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="09e72-140">"True", wenn das Chat-Protokoll aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="09e72-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="09e72-141">Falsch, wenn das Chat-Protokoll deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="09e72-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="09e72-142">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="09e72-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="09e72-143">NULL.</span><span class="sxs-lookup"><span data-stu-id="09e72-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-144">filePost</span><span class="sxs-lookup"><span data-stu-id="09e72-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="09e72-145">bit</span><span class="sxs-lookup"><span data-stu-id="09e72-145">bit</span></span></p></td>
<td><p><span data-ttu-id="09e72-146">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="09e72-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="09e72-147">"True", wenn Dateiuploads zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="09e72-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="09e72-148">False, wenn Dateiuploads nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="09e72-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="09e72-149">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="09e72-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="09e72-150">NULL.</span><span class="sxs-lookup"><span data-stu-id="09e72-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-151">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="09e72-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="09e72-152">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-153">"True", wenn der Chatroom deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="09e72-153">True if the chat room is disabled.</span></span> <span data-ttu-id="09e72-154">Gilt nur für Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="09e72-154">Applies only to chat rooms.</span></span> <span data-ttu-id="09e72-155">(Falsch für Kategorien.)</span><span class="sxs-lookup"><span data-stu-id="09e72-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-156">Verhalten</span><span class="sxs-lookup"><span data-stu-id="09e72-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="09e72-157">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-158">Verhalten (in der EnumValue-Tabelle nachgeschlagen):</span><span class="sxs-lookup"><span data-stu-id="09e72-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="09e72-159">4: Normal (normale Chatrooms).</span><span class="sxs-lookup"><span data-stu-id="09e72-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="09e72-160">5: Auditorium (Auditorium-Chatrooms, nur Referenten können dazu beitragen).</span><span class="sxs-lookup"><span data-stu-id="09e72-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="09e72-161">Gilt nur für Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="09e72-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-162">Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="09e72-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="09e72-163">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-164">Sichtbarkeit (in der EnumValue-Tabelle nachgeschlagen):</span><span class="sxs-lookup"><span data-stu-id="09e72-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="09e72-165">2: privat</span><span class="sxs-lookup"><span data-stu-id="09e72-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="09e72-166">3: Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="09e72-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="09e72-167">6: Öffnen</span><span class="sxs-lookup"><span data-stu-id="09e72-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="09e72-168">Gilt nur für Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="09e72-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-169">siopID</span><span class="sxs-lookup"><span data-stu-id="09e72-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="09e72-170">GUID</span><span class="sxs-lookup"><span data-stu-id="09e72-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="09e72-171">Add-in-GUID, wenn diesem Chatroom ein Add-in zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="09e72-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="09e72-172">(Kategorien verfügen nicht über Add-Ins.)</span><span class="sxs-lookup"><span data-stu-id="09e72-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="09e72-173">Die Add-in-Informationen werden in der SiopWhiteList-Tabelle nachgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="09e72-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="09e72-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="09e72-175">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-176">Die ID des Prinzipals, der diesen Knoten erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="09e72-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="09e72-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="09e72-178">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-179">Zeitstempel der Knotenerstellung.</span><span class="sxs-lookup"><span data-stu-id="09e72-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="09e72-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="09e72-181">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-182">Die ID des Prinzipals, der das neueste Update dieses Knotens durchführte.</span><span class="sxs-lookup"><span data-stu-id="09e72-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="09e72-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="09e72-184">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="09e72-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="09e72-185">Zeitstempel der letzten Aktualisierung dieses Knotens.</span><span class="sxs-lookup"><span data-stu-id="09e72-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="09e72-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="09e72-187">datetime</span><span class="sxs-lookup"><span data-stu-id="09e72-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="09e72-188">Zeitpunkt des letzten Aufräumvorgangs (Entfernen von Bereichen aus tblScopedPrincipal-Tabelle und Rollen aus der tblPrincipalRole-Tabelle), die diesen Knoten betroffen haben.</span><span class="sxs-lookup"><span data-stu-id="09e72-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="09e72-189">Dieser wird vom internen Cache Aktualisierungsmechanismus des Chat Diensts verwendet.</span><span class="sxs-lookup"><span data-stu-id="09e72-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="09e72-190">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="09e72-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09e72-191">Spalte</span><span class="sxs-lookup"><span data-stu-id="09e72-191">Column</span></span></th>
<th><span data-ttu-id="09e72-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09e72-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09e72-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="09e72-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="09e72-194">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="09e72-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-195">Verhalten</span><span class="sxs-lookup"><span data-stu-id="09e72-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="09e72-196">Fremdschlüssel mit Lookup in der Tabelle "tblEnumValue. Wert".</span><span class="sxs-lookup"><span data-stu-id="09e72-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-197">Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="09e72-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="09e72-198">Fremdschlüssel mit Lookup in der Tabelle "tblEnumValue. Wert".</span><span class="sxs-lookup"><span data-stu-id="09e72-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09e72-199">parentID</span><span class="sxs-lookup"><span data-stu-id="09e72-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="09e72-200">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="09e72-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09e72-201">siopID</span><span class="sxs-lookup"><span data-stu-id="09e72-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="09e72-202">Fremdschlüssel mit Lookup in der tblSiopWhiteList. siopId-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="09e72-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

