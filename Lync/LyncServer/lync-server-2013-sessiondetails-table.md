---
title: 'Lync Server 2013: SessionDetails-Tabelle'
description: 'Lync Server 2013: SessionDetails-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569931"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="ed01c-103">SessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed01c-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed01c-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ed01c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ed01c-105">Jeder Eintrag steht für eine Peer-zu-Peer-Sitzung, die ein Telefonanruf von VoIP zu VoIP, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung sein kann.</span><span class="sxs-lookup"><span data-stu-id="ed01c-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="ed01c-106">Sie können einen Tabellen Beitritt mit der [Medientabelle in lync Server 2013](lync-server-2013-media-table.md) durchführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="ed01c-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="ed01c-107">Beachten Sie, dass die Felder IsUser1IntegratedWithDeskPhone und IsUser2IntegratedWithDeskPhone aus der SessionDetails-Tabelle gelöscht wurden, die in Microsoft lync Server 2013 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ed01c-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed01c-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="ed01c-108">Column</span></span></th>
<th><span data-ttu-id="ed01c-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ed01c-109">Data Type</span></span></th>
<th><span data-ttu-id="ed01c-110">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="ed01c-110">Key/Index</span></span></th>
<th><span data-ttu-id="ed01c-111">Details</span><span class="sxs-lookup"><span data-stu-id="ed01c-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-112"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ed01c-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="ed01c-114">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-115">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-115">Time of session request.</span></span> <span data-ttu-id="ed01c-116">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ed01c-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ed01c-117">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-119">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-119">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-120">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-121">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-121">ID number to identify the session.</span></span> <span data-ttu-id="ed01c-122">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. \* Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-123"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-124">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ed01c-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-125">Ein GUID für die Korrelation mehrerer Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="ed01c-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-126"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-127">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ed01c-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="ed01c-128">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-129">ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed01c-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="ed01c-130">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-131"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-132">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-132">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-133">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-134">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-134">ID number to identify the session.</span></span> <span data-ttu-id="ed01c-135">Wird zusammen mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed01c-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="ed01c-136">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-137"><strong>User1</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-138">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-138">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-139">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-140">ID eines Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-140">ID of one user in the session.</span></span> <span data-ttu-id="ed01c-141">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-143">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-143">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-144">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-145">ID des anderen Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-145">ID of the other user in the session.</span></span> <span data-ttu-id="ed01c-146">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-148">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="ed01c-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-149">GUID, die den Endpunkt angibt, der vom ersten Benutzer in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ed01c-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="ed01c-150">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ed01c-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-152">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="ed01c-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-153">GUID, die den Endpunkt angibt, der vom zweiten Benutzer in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ed01c-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="ed01c-154">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ed01c-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-156">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-156">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-157">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-158">Der ursprüngliche „An Benutzer“-URI in der SIP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="ed01c-159">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-161">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-161">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-162">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-163">ID des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="ed01c-163">ID of the user who started the session.</span></span> <span data-ttu-id="ed01c-164">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-166">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-166">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-167">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-168">Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird.</span><span class="sxs-lookup"><span data-stu-id="ed01c-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="ed01c-169">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-171">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-171">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-172">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-173">ID des Benutzers, der den Anruf weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="ed01c-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="ed01c-174">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-175"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-176">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-176">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-177">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-178">ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="ed01c-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="ed01c-179">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-180"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-181">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-181">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-182">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-183">ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="ed01c-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="ed01c-184">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-186">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-186">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-187">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-188">In der Sitzung verwendeter Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="ed01c-188">Content type used in the session.</span></span> <span data-ttu-id="ed01c-189">Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der ContentTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-191">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-191">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-192">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-193">Von Benutzer1 verwendete Clientversion.</span><span class="sxs-lookup"><span data-stu-id="ed01c-193">Client version used by User1.</span></span> <span data-ttu-id="ed01c-194">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-196">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-196">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-197">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-198">Von Benutzer2 verwendete Clientversion.</span><span class="sxs-lookup"><span data-stu-id="ed01c-198">Client version used by User2.</span></span> <span data-ttu-id="ed01c-199">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-201">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-201">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-202">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-203">Von Benutzer1 verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="ed01c-203">Edge Server used by User1.</span></span> <span data-ttu-id="ed01c-204">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-206">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-206">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-207">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-208">Von Benutzer2 verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="ed01c-208">Edge Server used by User2.</span></span> <span data-ttu-id="ed01c-209">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-211">Bit</span><span class="sxs-lookup"><span data-stu-id="ed01c-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-212">Gibt an, ob Benutzer1 ein interner oder externer Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="ed01c-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-214">Bit</span><span class="sxs-lookup"><span data-stu-id="ed01c-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-215">Gibt an, ob Benutzer2 ein interner oder externer Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="ed01c-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-216"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-217">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ed01c-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-218">Die Uhrzeit der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-218">The time of the first INVITE request.</span></span> <span data-ttu-id="ed01c-219">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="ed01c-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ed01c-220">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ed01c-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="ed01c-221">Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ed01c-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ed01c-222">Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="ed01c-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-223"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-224">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ed01c-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-225">Die Zeit bis zur Antwort auf die erste INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="ed01c-226">Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ed01c-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ed01c-227">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ed01c-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-229">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-p121">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ed01c-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-233"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-234">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-235">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="ed01c-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-237">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-237">int</span></span></p></td>
<td><p><span data-ttu-id="ed01c-238">Fremd</span><span class="sxs-lookup"><span data-stu-id="ed01c-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed01c-239">Anrufpriorität.</span><span class="sxs-lookup"><span data-stu-id="ed01c-239">Call priority.</span></span> <span data-ttu-id="ed01c-240">Weitere Informationen finden Sie <a href="lync-server-2013-callpriorities-table.md">in der CallPriorities-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ed01c-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-242">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-243">Anzahl der von Benutzer1 während der Sitzung gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="ed01c-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-245">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-246">Anzahl der von Benutzer2 während der Sitzung gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="ed01c-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-248">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ed01c-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-249">Uhrzeit am Ende der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ed01c-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-250"><strong>Mediatypes zu bestimmen</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-251">int</span><span class="sxs-lookup"><span data-stu-id="ed01c-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-p123">Ein Bit-Satz, der den Medientyp dieser Sitzung angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ed01c-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-254">Chat</span><span class="sxs-lookup"><span data-stu-id="ed01c-254">IM</span></span></p></td>
<td><p><span data-ttu-id="ed01c-255">1</span><span class="sxs-lookup"><span data-stu-id="ed01c-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="ed01c-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="ed01c-257">2</span><span class="sxs-lookup"><span data-stu-id="ed01c-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="ed01c-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="ed01c-259">4 </span><span class="sxs-lookup"><span data-stu-id="ed01c-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="ed01c-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="ed01c-261">8 </span><span class="sxs-lookup"><span data-stu-id="ed01c-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-262">Audio</span><span class="sxs-lookup"><span data-stu-id="ed01c-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="ed01c-263">16 </span><span class="sxs-lookup"><span data-stu-id="ed01c-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-264">Video</span><span class="sxs-lookup"><span data-stu-id="ed01c-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="ed01c-265">32</span><span class="sxs-lookup"><span data-stu-id="ed01c-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="ed01c-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="ed01c-267">64</span><span class="sxs-lookup"><span data-stu-id="ed01c-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-269">smallint</span><span class="sxs-lookup"><span data-stu-id="ed01c-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-p124">Ein Bit-Satz, der die Attribute von Benutzer1 angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ed01c-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ed01c-272">0x01 – Mit Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="ed01c-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-274">smallint</span><span class="sxs-lookup"><span data-stu-id="ed01c-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-p125">Ein Bit-Satz, der die Attribute von Benutzer2 angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ed01c-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ed01c-277">0x01 – Mit Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="ed01c-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed01c-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-279">smallint</span><span class="sxs-lookup"><span data-stu-id="ed01c-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-p126">Ein Bit-Satz, der die Anrufattribute angibt. Die Definitionen folgender Attribute sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ed01c-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ed01c-282">0x01 – Wiederholungsversuch der Sitzung</span><span class="sxs-lookup"><span data-stu-id="ed01c-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="ed01c-283">0x02 – Von Agent getätigter Anruf im Namen einer Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="ed01c-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed01c-284"><strong>Verarbeitet</strong></span><span class="sxs-lookup"><span data-stu-id="ed01c-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="ed01c-285">Bit</span><span class="sxs-lookup"><span data-stu-id="ed01c-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed01c-286">Für die interne Verwendung durch den Überwachungsdienst.</span><span class="sxs-lookup"><span data-stu-id="ed01c-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="ed01c-287">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ed01c-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ed01c-288">\* Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="ed01c-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="ed01c-289">Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.</span><span class="sxs-lookup"><span data-stu-id="ed01c-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

