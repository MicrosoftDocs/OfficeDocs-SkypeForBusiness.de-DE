---
title: 'Lync Server 2013: Sitzungsansicht'
description: 'Lync Server 2013: Sitzungsansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545011"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="1ff52-103">Sitzungsansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff52-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ff52-104">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1ff52-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1ff52-105">In der Sitzungsansicht werden Informationen über die Sitzungen gespeichert, die über einen Datensatz in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="1ff52-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="1ff52-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1ff52-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ff52-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="1ff52-107">Column</span></span></th>
<th><span data-ttu-id="1ff52-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1ff52-108">Data Type</span></span></th>
<th><span data-ttu-id="1ff52-109">Details</span><span class="sxs-lookup"><span data-stu-id="1ff52-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-110">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="1ff52-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="1ff52-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1ff52-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ff52-112">Verweis von der MediaLine-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1ff52-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-113">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="1ff52-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="1ff52-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1ff52-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-115">Konferenz-URI bei einer Konferenz, DialogID bei einer Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1ff52-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-116">Correlation</span><span class="sxs-lookup"><span data-stu-id="1ff52-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="1ff52-117">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1ff52-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-118">Korrelations-ID der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1ff52-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-119">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="1ff52-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="1ff52-120">Bit</span><span class="sxs-lookup"><span data-stu-id="1ff52-120">bit</span></span></p></td>
<td><p><span data-ttu-id="1ff52-121">Dialog Feld Kategorie; 0 ist lync Server Vermittlungsserver Bein; 1 ist Vermittlungsserver auf das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="1ff52-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="1ff52-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="1ff52-123">Bit</span><span class="sxs-lookup"><span data-stu-id="1ff52-123">bit</span></span></p></td>
<td><p><span data-ttu-id="1ff52-124">Gibt an, ob der Anruf umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="1ff52-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-125">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="1ff52-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="1ff52-126">int</span><span class="sxs-lookup"><span data-stu-id="1ff52-126">int</span></span></p></td>
<td><p><span data-ttu-id="1ff52-127">Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs abgeglichen wurden.</span><span class="sxs-lookup"><span data-stu-id="1ff52-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="1ff52-128">Für lync Server wird nur ein Wert definiert:</span><span class="sxs-lookup"><span data-stu-id="1ff52-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="1ff52-129">0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="1ff52-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="1ff52-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="1ff52-131">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1ff52-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ff52-132">Die Startzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="1ff52-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="1ff52-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="1ff52-134">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1ff52-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ff52-135">Die Endzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="1ff52-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="1ff52-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="1ff52-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff52-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-138">FQDN des Anruferpools.</span><span class="sxs-lookup"><span data-stu-id="1ff52-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="1ff52-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="1ff52-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff52-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-141">FQDN des Angerufenen-Pools.</span><span class="sxs-lookup"><span data-stu-id="1ff52-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="1ff52-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="1ff52-143">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1ff52-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-144">P-Asserted-Identity-URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="1ff52-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="1ff52-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="1ff52-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1ff52-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-147">P-Asserted-Identity-URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="1ff52-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="1ff52-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="1ff52-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff52-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-150">Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="1ff52-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="1ff52-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="1ff52-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff52-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-153">Endpunktname des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="1ff52-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="1ff52-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="1ff52-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff52-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-156">Zeichenfolge für den Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="1ff52-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="1ff52-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="1ff52-158">smallint</span><span class="sxs-lookup"><span data-stu-id="1ff52-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="1ff52-159">Typ des Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="1ff52-159">Type of caller’s user agent.</span></span> <span data-ttu-id="1ff52-160">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ff52-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="1ff52-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="1ff52-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1ff52-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-163">Benutzeragentkategorie des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="1ff52-163">Category of caller’s user agent.</span></span> <span data-ttu-id="1ff52-164">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ff52-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="1ff52-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="1ff52-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff52-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-167">Zeichenfolge für den Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="1ff52-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="1ff52-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="1ff52-169">smallint</span><span class="sxs-lookup"><span data-stu-id="1ff52-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="1ff52-170">Benutzeragenttyp des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="1ff52-170">Type of user agent for the callee.</span></span> <span data-ttu-id="1ff52-171">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ff52-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="1ff52-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="1ff52-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1ff52-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-174">Benutzeragentkategorie des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="1ff52-174">User agent category for the callee.</span></span> <span data-ttu-id="1ff52-175">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ff52-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="1ff52-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="1ff52-177">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1ff52-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-178">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="1ff52-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff52-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="1ff52-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="1ff52-180">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1ff52-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1ff52-181">URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="1ff52-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff52-182">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="1ff52-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="1ff52-183">int</span><span class="sxs-lookup"><span data-stu-id="1ff52-183">int</span></span></p></td>
<td><p><span data-ttu-id="1ff52-184">Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="1ff52-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

