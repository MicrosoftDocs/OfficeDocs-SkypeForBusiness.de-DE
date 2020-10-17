---
title: 'Lync Server 2013: SessionDetails-Tabelle'
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
ms.openlocfilehash: e49cb6a5715b95758a5e7520c69dd45b757b10c7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510052"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="61fd0-102">SessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61fd0-102">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61fd0-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="61fd0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="61fd0-104">Jeder Eintrag steht für eine Peer-zu-Peer-Sitzung, die ein Telefonanruf von VoIP zu VoIP, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung sein kann.</span><span class="sxs-lookup"><span data-stu-id="61fd0-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="61fd0-105">Sie können einen Tabellen Beitritt mit der [Medientabelle in lync Server 2013](lync-server-2013-media-table.md) durchführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="61fd0-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="61fd0-106">Beachten Sie, dass die Felder IsUser1IntegratedWithDeskPhone und IsUser2IntegratedWithDeskPhone aus der SessionDetails-Tabelle gelöscht wurden, die in Microsoft lync Server 2013 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="61fd0-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61fd0-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="61fd0-107">Column</span></span></th>
<th><span data-ttu-id="61fd0-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="61fd0-108">Data Type</span></span></th>
<th><span data-ttu-id="61fd0-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="61fd0-109">Key/Index</span></span></th>
<th><span data-ttu-id="61fd0-110">Details</span><span class="sxs-lookup"><span data-stu-id="61fd0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61fd0-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="61fd0-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-114">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-114">Time of session request.</span></span> <span data-ttu-id="61fd0-115">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="61fd0-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="61fd0-116">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-118">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-118">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-119">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-120">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-120">ID number to identify the session.</span></span> <span data-ttu-id="61fd0-121">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. \* Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="61fd0-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-124">Ein GUID für die Korrelation mehrerer Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="61fd0-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-126">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61fd0-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="61fd0-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-128">ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="61fd0-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="61fd0-129">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-131">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-131">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-132">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-133">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-133">ID number to identify the session.</span></span> <span data-ttu-id="61fd0-134">Wird zusammen mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="61fd0-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="61fd0-135">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-136"><strong>User1</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-137">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-137">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-138">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-139">ID eines Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-139">ID of one user in the session.</span></span> <span data-ttu-id="61fd0-140">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-142">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-142">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-143">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-144">ID des anderen Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-144">ID of the other user in the session.</span></span> <span data-ttu-id="61fd0-145">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="61fd0-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-148">GUID, die den Endpunkt angibt, der vom ersten Benutzer in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="61fd0-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="61fd0-149">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="61fd0-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="61fd0-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-152">GUID, die den Endpunkt angibt, der vom zweiten Benutzer in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="61fd0-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="61fd0-153">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="61fd0-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-155">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-155">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-156">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-157">Der ursprüngliche „An Benutzer“-URI in der SIP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="61fd0-158">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-160">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-160">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-162">ID des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="61fd0-162">ID of the user who started the session.</span></span> <span data-ttu-id="61fd0-163">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-165">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-165">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-166">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-167">Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird.</span><span class="sxs-lookup"><span data-stu-id="61fd0-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="61fd0-168">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-170">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-170">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-171">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-172">ID des Benutzers, der den Anruf weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="61fd0-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="61fd0-173">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-174"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-175">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-175">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-176">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-177">ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="61fd0-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="61fd0-178">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-179"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-180">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-180">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-181">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-182">ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="61fd0-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="61fd0-183">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-185">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-185">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-186">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-187">In der Sitzung verwendeter Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="61fd0-187">Content type used in the session.</span></span> <span data-ttu-id="61fd0-188">Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der ContentTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-190">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-190">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-192">Von Benutzer1 verwendete Clientversion.</span><span class="sxs-lookup"><span data-stu-id="61fd0-192">Client version used by User1.</span></span> <span data-ttu-id="61fd0-193">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-195">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-195">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-196">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-197">Von Benutzer2 verwendete Clientversion.</span><span class="sxs-lookup"><span data-stu-id="61fd0-197">Client version used by User2.</span></span> <span data-ttu-id="61fd0-198">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-200">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-200">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-201">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-202">Von Benutzer1 verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="61fd0-202">Edge Server used by User1.</span></span> <span data-ttu-id="61fd0-203">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-205">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-205">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-206">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-207">Von Benutzer2 verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="61fd0-207">Edge Server used by User2.</span></span> <span data-ttu-id="61fd0-208">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-210">Bit</span><span class="sxs-lookup"><span data-stu-id="61fd0-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-211">Gibt an, ob Benutzer1 ein interner oder externer Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="61fd0-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-213">Bit</span><span class="sxs-lookup"><span data-stu-id="61fd0-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-214">Gibt an, ob Benutzer2 ein interner oder externer Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="61fd0-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-215"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-216">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61fd0-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-217">Die Uhrzeit der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-217">The time of the first INVITE request.</span></span> <span data-ttu-id="61fd0-218">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="61fd0-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="61fd0-219">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="61fd0-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="61fd0-220">Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="61fd0-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="61fd0-221">Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="61fd0-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-222"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-223">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61fd0-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-224">Die Zeit bis zur Antwort auf die erste INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="61fd0-225">Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="61fd0-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="61fd0-226">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="61fd0-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-228">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-p121">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="61fd0-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-232"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-233">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-234">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="61fd0-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-236">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-236">int</span></span></p></td>
<td><p><span data-ttu-id="61fd0-237">Fremd</span><span class="sxs-lookup"><span data-stu-id="61fd0-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61fd0-238">Anrufpriorität.</span><span class="sxs-lookup"><span data-stu-id="61fd0-238">Call priority.</span></span> <span data-ttu-id="61fd0-239">Weitere Informationen finden Sie <a href="lync-server-2013-callpriorities-table.md">in der CallPriorities-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61fd0-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-241">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-242">Anzahl der von Benutzer1 während der Sitzung gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="61fd0-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-244">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-245">Anzahl der von Benutzer2 während der Sitzung gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="61fd0-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-247">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61fd0-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-248">Uhrzeit am Ende der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="61fd0-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-249"><strong>Mediatypes zu bestimmen</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-250">int</span><span class="sxs-lookup"><span data-stu-id="61fd0-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-p123">Ein Bit-Satz, der den Medientyp dieser Sitzung angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="61fd0-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-253">Chat</span><span class="sxs-lookup"><span data-stu-id="61fd0-253">IM</span></span></p></td>
<td><p><span data-ttu-id="61fd0-254">1</span><span class="sxs-lookup"><span data-stu-id="61fd0-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="61fd0-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="61fd0-256">2</span><span class="sxs-lookup"><span data-stu-id="61fd0-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="61fd0-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="61fd0-258">4 </span><span class="sxs-lookup"><span data-stu-id="61fd0-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="61fd0-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="61fd0-260">8 </span><span class="sxs-lookup"><span data-stu-id="61fd0-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-261">Audio</span><span class="sxs-lookup"><span data-stu-id="61fd0-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="61fd0-262">16 </span><span class="sxs-lookup"><span data-stu-id="61fd0-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-263">Video</span><span class="sxs-lookup"><span data-stu-id="61fd0-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="61fd0-264">32</span><span class="sxs-lookup"><span data-stu-id="61fd0-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="61fd0-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="61fd0-266">64</span><span class="sxs-lookup"><span data-stu-id="61fd0-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-268">smallint</span><span class="sxs-lookup"><span data-stu-id="61fd0-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-p124">Ein Bit-Satz, der die Attribute von Benutzer1 angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="61fd0-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="61fd0-271">0x01 – Mit Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="61fd0-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-273">smallint</span><span class="sxs-lookup"><span data-stu-id="61fd0-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-p125">Ein Bit-Satz, der die Attribute von Benutzer2 angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="61fd0-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="61fd0-276">0x01 – Mit Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="61fd0-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61fd0-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-278">smallint</span><span class="sxs-lookup"><span data-stu-id="61fd0-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-p126">Ein Bit-Satz, der die Anrufattribute angibt. Die Definitionen folgender Attribute sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="61fd0-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="61fd0-281">0x01 – Wiederholungsversuch der Sitzung</span><span class="sxs-lookup"><span data-stu-id="61fd0-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="61fd0-282">0x02 – Von Agent getätigter Anruf im Namen einer Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="61fd0-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61fd0-283"><strong>Verarbeitet</strong></span><span class="sxs-lookup"><span data-stu-id="61fd0-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="61fd0-284">Bit</span><span class="sxs-lookup"><span data-stu-id="61fd0-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61fd0-285">Für die interne Verwendung durch den Überwachungsdienst.</span><span class="sxs-lookup"><span data-stu-id="61fd0-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="61fd0-286">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="61fd0-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="61fd0-287">\* Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="61fd0-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="61fd0-288">Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.</span><span class="sxs-lookup"><span data-stu-id="61fd0-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

