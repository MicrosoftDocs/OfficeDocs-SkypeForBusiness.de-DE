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
ms.openlocfilehash: fee9a2f2b59fc523224a778004b5c0beb041a12d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="4c347-102">SessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c347-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c347-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4c347-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4c347-104">Jeder Eintrag steht für eine Peer-zu-Peer-Sitzung, die ein Telefonanruf von VoIP zu VoIP, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung sein kann.</span><span class="sxs-lookup"><span data-stu-id="4c347-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="4c347-105">Sie können einen Tabellen Beitritt mit der [Medientabelle in lync Server 2013](lync-server-2013-media-table.md) durchführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="4c347-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="4c347-106">Beachten Sie, dass die Felder IsUser1IntegratedWithDeskPhone und IsUser2IntegratedWithDeskPhone aus der SessionDetails-Tabelle gelöscht wurden, die in Microsoft lync Server 2013 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4c347-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c347-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="4c347-107">Column</span></span></th>
<th><span data-ttu-id="4c347-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c347-108">Data Type</span></span></th>
<th><span data-ttu-id="4c347-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="4c347-109">Key/Index</span></span></th>
<th><span data-ttu-id="4c347-110">Details</span><span class="sxs-lookup"><span data-stu-id="4c347-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c347-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4c347-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4c347-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-114">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="4c347-114">Time of session request.</span></span> <span data-ttu-id="4c347-115">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4c347-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4c347-116">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-118">int</span><span class="sxs-lookup"><span data-stu-id="4c347-118">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-119">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="4c347-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-120">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4c347-120">ID number to identify the session.</span></span> <span data-ttu-id="4c347-121">Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. \* Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="4c347-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-124">Ein GUID für die Korrelation mehrerer Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4c347-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-126">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4c347-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="4c347-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-128">ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="4c347-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="4c347-129">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-131">int</span><span class="sxs-lookup"><span data-stu-id="4c347-131">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-132">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-133">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4c347-133">ID number to identify the session.</span></span> <span data-ttu-id="4c347-134">Wird zusammen mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="4c347-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="4c347-135">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-136"><strong>User1</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-137">int</span><span class="sxs-lookup"><span data-stu-id="4c347-137">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-138">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-139">ID eines Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4c347-139">ID of one user in the session.</span></span> <span data-ttu-id="4c347-140">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-142">int</span><span class="sxs-lookup"><span data-stu-id="4c347-142">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-143">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-144">ID des anderen Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4c347-144">ID of the other user in the session.</span></span> <span data-ttu-id="4c347-145">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="4c347-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-148">GUID, die den Endpunkt angibt, der vom ersten Benutzer in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c347-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="4c347-149">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4c347-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="4c347-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-152">GUID, die den Endpunkt angibt, der vom zweiten Benutzer in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c347-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="4c347-153">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4c347-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-155">int</span><span class="sxs-lookup"><span data-stu-id="4c347-155">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-156">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-157">Der ursprüngliche „An Benutzer“-URI in der SIP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4c347-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="4c347-158">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-160">int</span><span class="sxs-lookup"><span data-stu-id="4c347-160">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-162">ID des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="4c347-162">ID of the user who started the session.</span></span> <span data-ttu-id="4c347-163">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-165">int</span><span class="sxs-lookup"><span data-stu-id="4c347-165">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-166">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-167">Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird.</span><span class="sxs-lookup"><span data-stu-id="4c347-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="4c347-168">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-170">int</span><span class="sxs-lookup"><span data-stu-id="4c347-170">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-171">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-172">ID des Benutzers, der den Anruf weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="4c347-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="4c347-173">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-174"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-175">int</span><span class="sxs-lookup"><span data-stu-id="4c347-175">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-176">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-177">ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="4c347-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="4c347-178">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-179"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-180">int</span><span class="sxs-lookup"><span data-stu-id="4c347-180">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-181">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-182">ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="4c347-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="4c347-183">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-185">int</span><span class="sxs-lookup"><span data-stu-id="4c347-185">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-186">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-187">In der Sitzung verwendeter Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="4c347-187">Content type used in the session.</span></span> <span data-ttu-id="4c347-188">Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der ContentTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-190">int</span><span class="sxs-lookup"><span data-stu-id="4c347-190">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-192">Von Benutzer1 verwendete Clientversion.</span><span class="sxs-lookup"><span data-stu-id="4c347-192">Client version used by User1.</span></span> <span data-ttu-id="4c347-193">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-195">int</span><span class="sxs-lookup"><span data-stu-id="4c347-195">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-196">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-197">Von Benutzer2 verwendete Clientversion.</span><span class="sxs-lookup"><span data-stu-id="4c347-197">Client version used by User2.</span></span> <span data-ttu-id="4c347-198">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-200">int</span><span class="sxs-lookup"><span data-stu-id="4c347-200">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-201">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-202">Von Benutzer1 verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="4c347-202">Edge Server used by User1.</span></span> <span data-ttu-id="4c347-203">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-205">int</span><span class="sxs-lookup"><span data-stu-id="4c347-205">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-206">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-207">Von Benutzer2 verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="4c347-207">Edge Server used by User2.</span></span> <span data-ttu-id="4c347-208">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-210">Bit</span><span class="sxs-lookup"><span data-stu-id="4c347-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-211">Gibt an, ob Benutzer1 ein interner oder externer Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="4c347-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-213">Bit</span><span class="sxs-lookup"><span data-stu-id="4c347-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-214">Gibt an, ob Benutzer2 ein interner oder externer Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="4c347-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-215"><strong>Invitezeit</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-216">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4c347-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-217">Die Uhrzeit der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4c347-217">The time of the first INVITE request.</span></span> <span data-ttu-id="4c347-218">Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="4c347-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4c347-219">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4c347-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="4c347-220">Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c347-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4c347-221">Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</span><span class="sxs-lookup"><span data-stu-id="4c347-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-222"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-223">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4c347-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-224">Die Zeit bis zur Antwort auf die erste INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4c347-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="4c347-225">Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c347-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4c347-226">Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4c347-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-228">int</span><span class="sxs-lookup"><span data-stu-id="4c347-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-p121">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4c347-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-232"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-233">int</span><span class="sxs-lookup"><span data-stu-id="4c347-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-234">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="4c347-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-236">int</span><span class="sxs-lookup"><span data-stu-id="4c347-236">int</span></span></p></td>
<td><p><span data-ttu-id="4c347-237">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c347-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c347-238">Anrufpriorität.</span><span class="sxs-lookup"><span data-stu-id="4c347-238">Call priority.</span></span> <span data-ttu-id="4c347-239">Weitere Informationen finden Sie <a href="lync-server-2013-callpriorities-table.md">in der CallPriorities-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c347-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-241">int</span><span class="sxs-lookup"><span data-stu-id="4c347-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-242">Anzahl der von Benutzer1 während der Sitzung gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="4c347-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-244">int</span><span class="sxs-lookup"><span data-stu-id="4c347-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-245">Anzahl der von Benutzer2 während der Sitzung gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="4c347-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-247">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4c347-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-248">Uhrzeit am Ende der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4c347-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-249"><strong>Mediatypes zu bestimmen</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-250">int</span><span class="sxs-lookup"><span data-stu-id="4c347-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-p123">Ein Bit-Satz, der den Medientyp dieser Sitzung angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4c347-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c347-253">Chat</span><span class="sxs-lookup"><span data-stu-id="4c347-253">IM</span></span></p></td>
<td><p><span data-ttu-id="4c347-254">1 </span><span class="sxs-lookup"><span data-stu-id="4c347-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="4c347-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="4c347-256">2 </span><span class="sxs-lookup"><span data-stu-id="4c347-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="4c347-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="4c347-258">4 </span><span class="sxs-lookup"><span data-stu-id="4c347-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="4c347-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="4c347-260">8 </span><span class="sxs-lookup"><span data-stu-id="4c347-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-261">Audio</span><span class="sxs-lookup"><span data-stu-id="4c347-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="4c347-262">16 </span><span class="sxs-lookup"><span data-stu-id="4c347-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-263">Video</span><span class="sxs-lookup"><span data-stu-id="4c347-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="4c347-264">32</span><span class="sxs-lookup"><span data-stu-id="4c347-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="4c347-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="4c347-266">64</span><span class="sxs-lookup"><span data-stu-id="4c347-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-268">smallint</span><span class="sxs-lookup"><span data-stu-id="4c347-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-p124">Ein Bit-Satz, der die Attribute von Benutzer1 angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4c347-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c347-271">0x01 – Mit Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="4c347-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-273">smallint</span><span class="sxs-lookup"><span data-stu-id="4c347-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-p125">Ein Bit-Satz, der die Attribute von Benutzer2 angibt. Die Definitionen folgender Typen sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4c347-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c347-276">0x01 – Mit Desktoptelefon integriert</span><span class="sxs-lookup"><span data-stu-id="4c347-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c347-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-278">smallint</span><span class="sxs-lookup"><span data-stu-id="4c347-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-p126">Ein Bit-Satz, der die Anrufattribute angibt. Die Definitionen folgender Attribute sind aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4c347-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c347-281">0x01 – Wiederholungsversuch der Sitzung</span><span class="sxs-lookup"><span data-stu-id="4c347-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="4c347-282">0x02 – Von Agent getätigter Anruf im Namen einer Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="4c347-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c347-283"><strong>Verarbeitet</strong></span><span class="sxs-lookup"><span data-stu-id="4c347-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="4c347-284">Bit</span><span class="sxs-lookup"><span data-stu-id="4c347-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c347-285">Für die interne Verwendung durch den Überwachungsdienst.</span><span class="sxs-lookup"><span data-stu-id="4c347-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="4c347-286">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4c347-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4c347-287">\*Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="4c347-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="4c347-288">Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.</span><span class="sxs-lookup"><span data-stu-id="4c347-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

