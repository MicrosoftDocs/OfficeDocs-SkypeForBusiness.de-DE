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
ms.openlocfilehash: b68c50fc17199c68a69c5a7c6dd6abc8a5bd1dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="66bc9-102">SessionDetails-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66bc9-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66bc9-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="66bc9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="66bc9-104">Jeder Datensatz stellt eine Peer-to-Peer-Sitzung dar, bei der es sich um einen VoIP-VoIP-Telefonanruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann.</span><span class="sxs-lookup"><span data-stu-id="66bc9-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="66bc9-105">Sie können eine Tabellen Verknüpfung mit der [Medientabelle in lync Server 2013](lync-server-2013-media-table.md) ausführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="66bc9-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="66bc9-106">Beachten Sie, dass die IsUser1IntegratedWithDeskPhone-und IsUser2IntegratedWithDeskPhone-Felder aus der SessionDetails-Tabelle gelöscht wurden, die in Microsoft lync Server 2013 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="66bc9-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66bc9-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="66bc9-107">Column</span></span></th>
<th><span data-ttu-id="66bc9-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="66bc9-108">Data Type</span></span></th>
<th><span data-ttu-id="66bc9-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="66bc9-109">Key/Index</span></span></th>
<th><span data-ttu-id="66bc9-110">Details</span><span class="sxs-lookup"><span data-stu-id="66bc9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-112">datetime</span><span class="sxs-lookup"><span data-stu-id="66bc9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="66bc9-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-114">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="66bc9-114">Time of session request.</span></span> <span data-ttu-id="66bc9-115">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="66bc9-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="66bc9-116">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-118">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-118">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-119">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-120">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="66bc9-120">ID number to identify the session.</span></span> <span data-ttu-id="66bc9-121">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. \* Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="66bc9-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-124">Eine GUID zum Korrelieren mehrerer Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="66bc9-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-126">datetime</span><span class="sxs-lookup"><span data-stu-id="66bc9-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="66bc9-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-128">Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="66bc9-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="66bc9-129">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-131">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-131">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-132">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-133">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="66bc9-133">ID number to identify the session.</span></span> <span data-ttu-id="66bc9-134">Wird in Verbindung mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="66bc9-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="66bc9-135">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-136"><strong>Benutzer1</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-137">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-137">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-138">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-139">Die ID eines Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="66bc9-139">ID of one user in the session.</span></span> <span data-ttu-id="66bc9-140">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-142">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-142">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-143">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-144">Die ID des anderen Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="66bc9-144">ID of the other user in the session.</span></span> <span data-ttu-id="66bc9-145">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="66bc9-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-148">GUID, die den vom ersten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="66bc9-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="66bc9-149">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66bc9-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="66bc9-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-152">GUID, die den vom zweiten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="66bc9-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="66bc9-153">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66bc9-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-155">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-155">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-156">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-157">Das Original für Benutzer-URI in der SIP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="66bc9-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="66bc9-158">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-160">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-160">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-162">Die ID des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="66bc9-162">ID of the user who started the session.</span></span> <span data-ttu-id="66bc9-163">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-165">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-165">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-166">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-167">Gibt die ID des Benutzers an, der der Anrufer im Auftrag ist.</span><span class="sxs-lookup"><span data-stu-id="66bc9-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="66bc9-168">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-170">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-170">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-171">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-172">Die ID des Benutzers, auf den der Anruf verweist.</span><span class="sxs-lookup"><span data-stu-id="66bc9-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="66bc9-173">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-174"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-175">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-175">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-176">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-177">Die ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="66bc9-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="66bc9-178">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-179"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-180">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-180">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-181">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-182">Die ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="66bc9-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="66bc9-183">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-185">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-185">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-186">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-187">Inhaltstyp, der in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66bc9-187">Content type used in the session.</span></span> <span data-ttu-id="66bc9-188">Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der Tabelle "ContentTypes" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-190">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-190">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-192">Von Benutzer1 verwendete Client Version.</span><span class="sxs-lookup"><span data-stu-id="66bc9-192">Client version used by User1.</span></span> <span data-ttu-id="66bc9-193">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-195">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-195">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-196">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-197">Von User2 verwendete Client Version.</span><span class="sxs-lookup"><span data-stu-id="66bc9-197">Client version used by User2.</span></span> <span data-ttu-id="66bc9-198">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-200">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-200">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-201">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-202">Von Benutzer1 verwendeter Edgeserver</span><span class="sxs-lookup"><span data-stu-id="66bc9-202">Edge Server used by User1.</span></span> <span data-ttu-id="66bc9-203">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-205">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-205">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-206">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-207">Von User2 verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="66bc9-207">Edge Server used by User2.</span></span> <span data-ttu-id="66bc9-208">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-210">bit</span><span class="sxs-lookup"><span data-stu-id="66bc9-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-211">Gibt an, ob Benutzer1 intern angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="66bc9-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-213">bit</span><span class="sxs-lookup"><span data-stu-id="66bc9-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-214">Gibt an, ob User2 intern angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="66bc9-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-215"><strong>Einladen</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-216">datetime</span><span class="sxs-lookup"><span data-stu-id="66bc9-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-217">Der Zeitpunkt der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="66bc9-217">The time of the first INVITE request.</span></span> <span data-ttu-id="66bc9-218">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="66bc9-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="66bc9-219">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="66bc9-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="66bc9-220">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="66bc9-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="66bc9-221">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="66bc9-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-222"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-223">datetime</span><span class="sxs-lookup"><span data-stu-id="66bc9-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-224">Der Zeitpunkt der Antwort auf die erste Einladungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="66bc9-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="66bc9-225">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="66bc9-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="66bc9-226">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="66bc9-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-227"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-228">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-229">SIP-Antwortcode für die Sitzungseinladung</span><span class="sxs-lookup"><span data-stu-id="66bc9-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="66bc9-230">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="66bc9-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="66bc9-231">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="66bc9-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-232"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-233">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-234">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="66bc9-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-236">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-236">int</span></span></p></td>
<td><p><span data-ttu-id="66bc9-237">Fremd</span><span class="sxs-lookup"><span data-stu-id="66bc9-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66bc9-238">Anrufpriorität.</span><span class="sxs-lookup"><span data-stu-id="66bc9-238">Call priority.</span></span> <span data-ttu-id="66bc9-239">Weitere Informationen finden Sie <a href="lync-server-2013-callpriorities-table.md">in der CallPriorities-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66bc9-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-241">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-242">Die Anzahl der Nachrichten, die von Benutzer1 während der Sitzung gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="66bc9-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-244">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-245">Die Anzahl der Nachrichten, die von User2 während der Sitzung gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="66bc9-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-247">datetime</span><span class="sxs-lookup"><span data-stu-id="66bc9-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-248">Uhrzeit am Ende der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="66bc9-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-250">int</span><span class="sxs-lookup"><span data-stu-id="66bc9-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-251">Ein Bit-Satz, der den Medientyp dieser Sitzung angibt.</span><span class="sxs-lookup"><span data-stu-id="66bc9-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="66bc9-252">Aufgelistet sind die Definitionen der Typen:</span><span class="sxs-lookup"><span data-stu-id="66bc9-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-253">Chat</span><span class="sxs-lookup"><span data-stu-id="66bc9-253">IM</span></span></p></td>
<td><p><span data-ttu-id="66bc9-254">1</span><span class="sxs-lookup"><span data-stu-id="66bc9-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="66bc9-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="66bc9-256">2</span><span class="sxs-lookup"><span data-stu-id="66bc9-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="66bc9-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="66bc9-258">4</span><span class="sxs-lookup"><span data-stu-id="66bc9-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="66bc9-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="66bc9-260">8</span><span class="sxs-lookup"><span data-stu-id="66bc9-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-261">Audio</span><span class="sxs-lookup"><span data-stu-id="66bc9-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="66bc9-262">16</span><span class="sxs-lookup"><span data-stu-id="66bc9-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-263">Video</span><span class="sxs-lookup"><span data-stu-id="66bc9-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="66bc9-264">32</span><span class="sxs-lookup"><span data-stu-id="66bc9-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="66bc9-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="66bc9-266">64</span><span class="sxs-lookup"><span data-stu-id="66bc9-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-268">smallint</span><span class="sxs-lookup"><span data-stu-id="66bc9-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-269">Ein Bit-Satz, der die Benutzer1-Attribute angibt.</span><span class="sxs-lookup"><span data-stu-id="66bc9-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="66bc9-270">Die folgenden Attributdefinitionen werden aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="66bc9-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="66bc9-271">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="66bc9-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-273">smallint</span><span class="sxs-lookup"><span data-stu-id="66bc9-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-274">Ein Bit-Satz, der die User2-Attribute angibt.</span><span class="sxs-lookup"><span data-stu-id="66bc9-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="66bc9-275">Die folgenden Attributdefinitionen werden aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="66bc9-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="66bc9-276">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="66bc9-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bc9-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-278">smallint</span><span class="sxs-lookup"><span data-stu-id="66bc9-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-279">Ein Bit-Satz, der die anrufattribute angibt.</span><span class="sxs-lookup"><span data-stu-id="66bc9-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="66bc9-280">Die folgenden Attributdefinitionen werden aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="66bc9-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="66bc9-281">0x01-wiederholte Sitzung</span><span class="sxs-lookup"><span data-stu-id="66bc9-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="66bc9-282">0x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="66bc9-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bc9-283"><strong>Verarbeitet</strong></span><span class="sxs-lookup"><span data-stu-id="66bc9-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="66bc9-284">bit</span><span class="sxs-lookup"><span data-stu-id="66bc9-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66bc9-285">Für die interne Verwendung durch den Überwachungsdienst.</span><span class="sxs-lookup"><span data-stu-id="66bc9-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="66bc9-286">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66bc9-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="66bc9-287">\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1.</span><span class="sxs-lookup"><span data-stu-id="66bc9-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="66bc9-288">Wenn mehrere Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, für einen anderen wird 2 usw.</span><span class="sxs-lookup"><span data-stu-id="66bc9-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

