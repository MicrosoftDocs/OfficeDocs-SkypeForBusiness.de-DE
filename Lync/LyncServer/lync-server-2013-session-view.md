---
title: 'Lync Server 2013: Sitzungsansicht'
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
ms.openlocfilehash: 80b9c7c9b54deb28b70c8ee2386359bec37d5a69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="c9d1c-102">Sitzungsansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9d1c-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9d1c-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c9d1c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c9d1c-104">In der Sitzungsansicht werden Informationen über die Sitzungen gespeichert, die über einen Datensatz in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="c9d1c-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9d1c-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="c9d1c-106">Column</span></span></th>
<th><span data-ttu-id="c9d1c-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c9d1c-107">Data Type</span></span></th>
<th><span data-ttu-id="c9d1c-108">Details</span><span class="sxs-lookup"><span data-stu-id="c9d1c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="c9d1c-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c9d1c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-111">Verweis von der MediaLine-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="c9d1c-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-114">Konferenz-URI bei einer Konferenz, DialogID bei einer Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="c9d1c-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-117">Korrelations-ID der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="c9d1c-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-119">Bit</span><span class="sxs-lookup"><span data-stu-id="c9d1c-119">bit</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-120">Dialog Feld Kategorie; 0 ist lync Server Vermittlungsserver Bein; 1 ist Vermittlungsserver auf das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="c9d1c-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-122">Bit</span><span class="sxs-lookup"><span data-stu-id="c9d1c-122">bit</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-123">Gibt an, ob der Anruf umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="c9d1c-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-125">int</span><span class="sxs-lookup"><span data-stu-id="c9d1c-125">int</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-126">Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs abgeglichen wurden.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="c9d1c-127">Für lync Server wird nur ein Wert definiert:</span><span class="sxs-lookup"><span data-stu-id="c9d1c-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="c9d1c-128">0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="c9d1c-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="c9d1c-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-130">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c9d1c-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-131">Die Startzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="c9d1c-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-133">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c9d1c-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-134">Die Endzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="c9d1c-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-137">FQDN des Anruferpools.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="c9d1c-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-140">FQDN des Angerufenen-Pools.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="c9d1c-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-143">P-Asserted-Identity-URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="c9d1c-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-146">P-Asserted-Identity-URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c9d1c-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-149">Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="c9d1c-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-152">Endpunktname des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="c9d1c-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-155">Zeichenfolge für den Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c9d1c-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-157">smallint</span><span class="sxs-lookup"><span data-stu-id="c9d1c-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-158">Typ des Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-158">Type of caller’s user agent.</span></span> <span data-ttu-id="c9d1c-159">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c9d1c-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c9d1c-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-162">Benutzeragentkategorie des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-162">Category of caller’s user agent.</span></span> <span data-ttu-id="c9d1c-163">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c9d1c-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="c9d1c-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-166">Zeichenfolge für den Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c9d1c-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-168">smallint</span><span class="sxs-lookup"><span data-stu-id="c9d1c-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-169">Benutzeragenttyp des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-169">Type of user agent for the callee.</span></span> <span data-ttu-id="c9d1c-170">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c9d1c-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c9d1c-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-173">Benutzeragentkategorie des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-173">User agent category for the callee.</span></span> <span data-ttu-id="c9d1c-174">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c9d1c-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="c9d1c-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-177">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9d1c-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="c9d1c-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c9d1c-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-180">URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9d1c-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="c9d1c-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-182">int</span><span class="sxs-lookup"><span data-stu-id="c9d1c-182">int</span></span></p></td>
<td><p><span data-ttu-id="c9d1c-183">Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="c9d1c-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

