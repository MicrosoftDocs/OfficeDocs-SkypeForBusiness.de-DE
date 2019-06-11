---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="dbeef-102">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbeef-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbeef-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="dbeef-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="dbeef-104">tblNode enthält die Objektstruktur (mit Kategorien-oder Chatroom-Knoten), wie Sie in der lync Server 2013-Systemsteuerung und den administrativen Cmdlets verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="dbeef-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="dbeef-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="dbeef-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbeef-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="dbeef-106">Column</span></span></th>
<th><span data-ttu-id="dbeef-107">Typ</span><span class="sxs-lookup"><span data-stu-id="dbeef-107">Type</span></span></th>
<th><span data-ttu-id="dbeef-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbeef-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="dbeef-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="dbeef-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-111">Knoten-ID (eindeutige Nummer).</span><span class="sxs-lookup"><span data-stu-id="dbeef-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="dbeef-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="dbeef-113">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-114">Knoten-GUID.</span><span class="sxs-lookup"><span data-stu-id="dbeef-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-115">parentID</span><span class="sxs-lookup"><span data-stu-id="dbeef-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="dbeef-116">int</span><span class="sxs-lookup"><span data-stu-id="dbeef-116">int</span></span></p></td>
<td><p><span data-ttu-id="dbeef-117">Knoten-ID des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="dbeef-117">Node ID of parent.</span></span> <span data-ttu-id="dbeef-118">Der Stammknoten (mit ID 1) schließt sich ebenfalls als übergeordnetes Element ein.</span><span class="sxs-lookup"><span data-stu-id="dbeef-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-119">NodeType</span><span class="sxs-lookup"><span data-stu-id="dbeef-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="dbeef-120">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-121">"True", wenn der Knoten eine Kategorie ist.</span><span class="sxs-lookup"><span data-stu-id="dbeef-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="dbeef-122">False, wenn es sich bei dem Knoten um einen Chatroom handelt.</span><span class="sxs-lookup"><span data-stu-id="dbeef-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="dbeef-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="dbeef-124">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-125">Knotenname</span><span class="sxs-lookup"><span data-stu-id="dbeef-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="dbeef-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="dbeef-127">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-128">Knotenbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="dbeef-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-129">einladen</span><span class="sxs-lookup"><span data-stu-id="dbeef-129">invite</span></span></p></td>
<td><p><span data-ttu-id="dbeef-130">bit</span><span class="sxs-lookup"><span data-stu-id="dbeef-130">bit</span></span></p></td>
<td><p><span data-ttu-id="dbeef-131">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="dbeef-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbeef-132">True, wenn Einladungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="dbeef-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="dbeef-133">False, wenn Einladungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="dbeef-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="dbeef-134">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="dbeef-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbeef-135">False, wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie).</span><span class="sxs-lookup"><span data-stu-id="dbeef-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="dbeef-136">NULL, wenn die invites-Einstellung von der übergeordneten Kategorie geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="dbeef-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-137">angemeldet</span><span class="sxs-lookup"><span data-stu-id="dbeef-137">logged</span></span></p></td>
<td><p><span data-ttu-id="dbeef-138">bit</span><span class="sxs-lookup"><span data-stu-id="dbeef-138">bit</span></span></p></td>
<td><p><span data-ttu-id="dbeef-139">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="dbeef-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbeef-140">"True", wenn das Chat-Protokoll aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dbeef-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="dbeef-141">Falsch, wenn das Chat-Protokoll deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dbeef-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="dbeef-142">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="dbeef-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbeef-143">NULL.</span><span class="sxs-lookup"><span data-stu-id="dbeef-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-144">filePost</span><span class="sxs-lookup"><span data-stu-id="dbeef-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="dbeef-145">bit</span><span class="sxs-lookup"><span data-stu-id="dbeef-145">bit</span></span></p></td>
<td><p><span data-ttu-id="dbeef-146">Für Kategorien:</span><span class="sxs-lookup"><span data-stu-id="dbeef-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbeef-147">"True", wenn Dateiuploads zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="dbeef-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="dbeef-148">False, wenn Dateiuploads nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="dbeef-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="dbeef-149">Für Räume:</span><span class="sxs-lookup"><span data-stu-id="dbeef-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbeef-150">NULL.</span><span class="sxs-lookup"><span data-stu-id="dbeef-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-151">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="dbeef-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="dbeef-152">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-153">"True", wenn der Chatroom deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dbeef-153">True if the chat room is disabled.</span></span> <span data-ttu-id="dbeef-154">Gilt nur für Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="dbeef-154">Applies only to chat rooms.</span></span> <span data-ttu-id="dbeef-155">(Falsch für Kategorien.)</span><span class="sxs-lookup"><span data-stu-id="dbeef-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-156">Verhalten</span><span class="sxs-lookup"><span data-stu-id="dbeef-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="dbeef-157">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-158">Verhalten (in der EnumValue-Tabelle nachgeschlagen):</span><span class="sxs-lookup"><span data-stu-id="dbeef-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="dbeef-159">4: Normal (normale Chatrooms).</span><span class="sxs-lookup"><span data-stu-id="dbeef-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="dbeef-160">5: Auditorium (Auditorium-Chatrooms, nur Referenten können dazu beitragen).</span><span class="sxs-lookup"><span data-stu-id="dbeef-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="dbeef-161">Gilt nur für Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="dbeef-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-162">Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="dbeef-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="dbeef-163">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-164">Sichtbarkeit (in der EnumValue-Tabelle nachgeschlagen):</span><span class="sxs-lookup"><span data-stu-id="dbeef-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="dbeef-165">2: privat</span><span class="sxs-lookup"><span data-stu-id="dbeef-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="dbeef-166">3: Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="dbeef-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="dbeef-167">6: Öffnen</span><span class="sxs-lookup"><span data-stu-id="dbeef-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="dbeef-168">Gilt nur für Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="dbeef-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-169">siopID</span><span class="sxs-lookup"><span data-stu-id="dbeef-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="dbeef-170">GUID</span><span class="sxs-lookup"><span data-stu-id="dbeef-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="dbeef-171">Add-in-GUID, wenn diesem Chatroom ein Add-in zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dbeef-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="dbeef-172">(Kategorien verfügen nicht über Add-Ins.)</span><span class="sxs-lookup"><span data-stu-id="dbeef-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="dbeef-173">Die Add-in-Informationen werden in der SiopWhiteList-Tabelle nachgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="dbeef-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="dbeef-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="dbeef-175">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-176">Die ID des Prinzipals, der diesen Knoten erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="dbeef-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="dbeef-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="dbeef-178">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-179">Zeitstempel der Knotenerstellung.</span><span class="sxs-lookup"><span data-stu-id="dbeef-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="dbeef-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="dbeef-181">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-182">Die ID des Prinzipals, der das neueste Update dieses Knotens durchführte.</span><span class="sxs-lookup"><span data-stu-id="dbeef-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="dbeef-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="dbeef-184">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="dbeef-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="dbeef-185">Zeitstempel der letzten Aktualisierung dieses Knotens.</span><span class="sxs-lookup"><span data-stu-id="dbeef-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="dbeef-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="dbeef-187">datetime</span><span class="sxs-lookup"><span data-stu-id="dbeef-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="dbeef-188">Zeitpunkt des letzten Aufräumvorgangs (Entfernen von Bereichen aus tblScopedPrincipal-Tabelle und Rollen aus der tblPrincipalRole-Tabelle), die diesen Knoten betroffen haben.</span><span class="sxs-lookup"><span data-stu-id="dbeef-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="dbeef-189">Dieser wird vom internen Cache Aktualisierungsmechanismus des Chat Diensts verwendet.</span><span class="sxs-lookup"><span data-stu-id="dbeef-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="dbeef-190">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="dbeef-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbeef-191">Spalte</span><span class="sxs-lookup"><span data-stu-id="dbeef-191">Column</span></span></th>
<th><span data-ttu-id="dbeef-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbeef-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="dbeef-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="dbeef-194">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="dbeef-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-195">Verhalten</span><span class="sxs-lookup"><span data-stu-id="dbeef-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="dbeef-196">Fremdschlüssel mit Lookup in der Tabelle "tblEnumValue. Wert".</span><span class="sxs-lookup"><span data-stu-id="dbeef-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-197">Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="dbeef-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="dbeef-198">Fremdschlüssel mit Lookup in der Tabelle "tblEnumValue. Wert".</span><span class="sxs-lookup"><span data-stu-id="dbeef-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbeef-199">parentID</span><span class="sxs-lookup"><span data-stu-id="dbeef-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="dbeef-200">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="dbeef-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbeef-201">siopID</span><span class="sxs-lookup"><span data-stu-id="dbeef-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="dbeef-202">Fremdschlüssel mit Lookup in der tblSiopWhiteList. siopId-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="dbeef-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

