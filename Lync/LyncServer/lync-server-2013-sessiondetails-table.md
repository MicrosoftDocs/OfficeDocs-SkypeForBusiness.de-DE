---
title: 'Lync Server 2013: SessionDetails-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="05ed8-102">SessionDetails-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05ed8-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05ed8-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="05ed8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="05ed8-104">Jeder Datensatz stellt eine Peer-to-Peer-Sitzung dar, bei der es sich um einen VoIP-VoIP-Telefonanruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann.</span><span class="sxs-lookup"><span data-stu-id="05ed8-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="05ed8-105">Sie können eine Tabellen Verknüpfung mit der [Medientabelle in lync Server 2013](lync-server-2013-media-table.md) ausführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="05ed8-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="05ed8-106">Beachten Sie, dass die IsUser1IntegratedWithDeskPhone-und IsUser2IntegratedWithDeskPhone-Felder aus der SessionDetails-Tabelle gelöscht wurden, die in Microsoft lync Server 2013 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="05ed8-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05ed8-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="05ed8-107">Column</span></span></th>
<th><span data-ttu-id="05ed8-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="05ed8-108">Data Type</span></span></th>
<th><span data-ttu-id="05ed8-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="05ed8-109">Key/Index</span></span></th>
<th><span data-ttu-id="05ed8-110">Details</span><span class="sxs-lookup"><span data-stu-id="05ed8-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-111"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-112">datetime</span><span class="sxs-lookup"><span data-stu-id="05ed8-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="05ed8-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-114">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="05ed8-114">Time of session request.</span></span> <span data-ttu-id="05ed8-115">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="05ed8-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="05ed8-116">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-118">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-118">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-119">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-120">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="05ed8-120">ID number to identify the session.</span></span> <span data-ttu-id="05ed8-121">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. \* Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="05ed8-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-124">Eine GUID zum Korrelieren mehrerer Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="05ed8-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-126">datetime</span><span class="sxs-lookup"><span data-stu-id="05ed8-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="05ed8-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-128">Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="05ed8-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="05ed8-129">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-131">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-131">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-132">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-133">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="05ed8-133">ID number to identify the session.</span></span> <span data-ttu-id="05ed8-134">Wird in Verbindung mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="05ed8-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="05ed8-135">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-136"><strong>Benutzer1</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-137">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-137">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-138">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-139">Die ID eines Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="05ed8-139">ID of one user in the session.</span></span> <span data-ttu-id="05ed8-140">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-142">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-142">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-143">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-144">Die ID des anderen Benutzers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="05ed8-144">ID of the other user in the session.</span></span> <span data-ttu-id="05ed8-145">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="05ed8-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-148">GUID, die den vom ersten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="05ed8-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="05ed8-149">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="05ed8-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="05ed8-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-152">GUID, die den vom zweiten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="05ed8-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="05ed8-153">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="05ed8-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-155">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-155">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-156">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-157">Das Original für Benutzer-URI in der SIP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="05ed8-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="05ed8-158">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-160">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-160">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-162">Die ID des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="05ed8-162">ID of the user who started the session.</span></span> <span data-ttu-id="05ed8-163">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-165">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-165">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-166">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-167">Gibt die ID des Benutzers an, der der Anrufer im Auftrag ist.</span><span class="sxs-lookup"><span data-stu-id="05ed8-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="05ed8-168">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-170">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-170">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-171">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-172">Die ID des Benutzers, auf den der Anruf verweist.</span><span class="sxs-lookup"><span data-stu-id="05ed8-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="05ed8-173">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-174"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-175">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-175">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-176">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-177">Die ID des für diese Sitzung verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="05ed8-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="05ed8-178">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-179"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-180">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-180">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-181">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-182">Die ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="05ed8-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="05ed8-183">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-185">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-185">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-186">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-187">Inhaltstyp, der in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05ed8-187">Content type used in the session.</span></span> <span data-ttu-id="05ed8-188">Weitere Informationen finden Sie in der Tabelle "ContentTypes" <a href="lync-server-2013-contenttypes-table.md">in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-190">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-190">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-192">Von Benutzer1 verwendete Client Version.</span><span class="sxs-lookup"><span data-stu-id="05ed8-192">Client version used by User1.</span></span> <span data-ttu-id="05ed8-193">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-195">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-195">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-196">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-197">Von User2 verwendete Client Version.</span><span class="sxs-lookup"><span data-stu-id="05ed8-197">Client version used by User2.</span></span> <span data-ttu-id="05ed8-198">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-200">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-200">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-201">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-202">Von Benutzer1 verwendeter Edgeserver</span><span class="sxs-lookup"><span data-stu-id="05ed8-202">Edge Server used by User1.</span></span> <span data-ttu-id="05ed8-203">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-205">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-205">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-206">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-207">Von User2 verwendeter Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="05ed8-207">Edge Server used by User2.</span></span> <span data-ttu-id="05ed8-208">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-210">bit</span><span class="sxs-lookup"><span data-stu-id="05ed8-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-211">Gibt an, ob Benutzer1 intern angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="05ed8-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-213">bit</span><span class="sxs-lookup"><span data-stu-id="05ed8-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-214">Gibt an, ob User2 intern angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="05ed8-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-215"><strong>Einladen</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-216">datetime</span><span class="sxs-lookup"><span data-stu-id="05ed8-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-217">Der Zeitpunkt der ersten INVITE-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="05ed8-217">The time of the first INVITE request.</span></span> <span data-ttu-id="05ed8-218">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="05ed8-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="05ed8-219">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="05ed8-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="05ed8-220">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="05ed8-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="05ed8-221">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="05ed8-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-222"><strong>Webantworten</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-223">datetime</span><span class="sxs-lookup"><span data-stu-id="05ed8-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-224">Der Zeitpunkt der Antwort auf die erste Einladungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="05ed8-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="05ed8-225">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="05ed8-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="05ed8-226">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="05ed8-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-227"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-228">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-229">SIP-Antwortcode für die Sitzungseinladung</span><span class="sxs-lookup"><span data-stu-id="05ed8-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="05ed8-230">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="05ed8-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="05ed8-231">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="05ed8-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-232"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-233">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-234">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="05ed8-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-236">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-236">int</span></span></p></td>
<td><p><span data-ttu-id="05ed8-237">Fremd</span><span class="sxs-lookup"><span data-stu-id="05ed8-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ed8-238">Anrufpriorität.</span><span class="sxs-lookup"><span data-stu-id="05ed8-238">Call priority.</span></span> <span data-ttu-id="05ed8-239">Weitere Informationen finden Sie <a href="lync-server-2013-callpriorities-table.md">in der CallPriorities-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="05ed8-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-241">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-242">Die Anzahl der Nachrichten, die von Benutzer1 während der Sitzung gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="05ed8-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-244">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-245">Die Anzahl der Nachrichten, die von User2 während der Sitzung gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="05ed8-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-247">datetime</span><span class="sxs-lookup"><span data-stu-id="05ed8-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-248">Uhrzeit am Ende der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="05ed8-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-250">int</span><span class="sxs-lookup"><span data-stu-id="05ed8-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-251">Ein Bit-Satz, der den Medientyp dieser Sitzung angibt.</span><span class="sxs-lookup"><span data-stu-id="05ed8-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="05ed8-252">Aufgelistet sind die Definitionen der Typen:</span><span class="sxs-lookup"><span data-stu-id="05ed8-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-253">Chat</span><span class="sxs-lookup"><span data-stu-id="05ed8-253">IM</span></span></p></td>
<td><p><span data-ttu-id="05ed8-254">1</span><span class="sxs-lookup"><span data-stu-id="05ed8-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="05ed8-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="05ed8-256">2</span><span class="sxs-lookup"><span data-stu-id="05ed8-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="05ed8-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="05ed8-258">4</span><span class="sxs-lookup"><span data-stu-id="05ed8-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="05ed8-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="05ed8-260">8</span><span class="sxs-lookup"><span data-stu-id="05ed8-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-261">Audio</span><span class="sxs-lookup"><span data-stu-id="05ed8-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="05ed8-262">16</span><span class="sxs-lookup"><span data-stu-id="05ed8-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-263">Video</span><span class="sxs-lookup"><span data-stu-id="05ed8-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="05ed8-264">32</span><span class="sxs-lookup"><span data-stu-id="05ed8-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="05ed8-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="05ed8-266">64</span><span class="sxs-lookup"><span data-stu-id="05ed8-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-268">smallint</span><span class="sxs-lookup"><span data-stu-id="05ed8-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-269">Ein Bit-Satz, der die Benutzer1-Attribute angibt.</span><span class="sxs-lookup"><span data-stu-id="05ed8-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="05ed8-270">Die folgenden Attributdefinitionen werden aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="05ed8-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="05ed8-271">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="05ed8-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-273">smallint</span><span class="sxs-lookup"><span data-stu-id="05ed8-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-274">Ein Bit-Satz, der die User2-Attribute angibt.</span><span class="sxs-lookup"><span data-stu-id="05ed8-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="05ed8-275">Die folgenden Attributdefinitionen werden aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="05ed8-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="05ed8-276">0x01-integriert mit dem Desktoptelefon</span><span class="sxs-lookup"><span data-stu-id="05ed8-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ed8-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-278">smallint</span><span class="sxs-lookup"><span data-stu-id="05ed8-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-279">Ein Bit-Satz, der die anrufattribute angibt.</span><span class="sxs-lookup"><span data-stu-id="05ed8-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="05ed8-280">Die folgenden Attributdefinitionen werden aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="05ed8-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="05ed8-281">0x01-wiederholte Sitzung</span><span class="sxs-lookup"><span data-stu-id="05ed8-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="05ed8-282">0x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="05ed8-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ed8-283"><strong>Verarbeitet</strong></span><span class="sxs-lookup"><span data-stu-id="05ed8-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="05ed8-284">bit</span><span class="sxs-lookup"><span data-stu-id="05ed8-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ed8-285">Für die interne Verwendung durch den Überwachungsdienst.</span><span class="sxs-lookup"><span data-stu-id="05ed8-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="05ed8-286">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="05ed8-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="05ed8-287">\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1.</span><span class="sxs-lookup"><span data-stu-id="05ed8-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="05ed8-288">Wenn mehrere Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, für einen anderen wird 2 usw.</span><span class="sxs-lookup"><span data-stu-id="05ed8-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

