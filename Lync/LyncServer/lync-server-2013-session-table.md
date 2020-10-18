---
title: 'Lync Server 2013: Session-Tabelle'
description: 'Lync Server 2013: Sitzungstabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576451"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="28e90-103">Sitzungstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28e90-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28e90-104">_**Letztes Änderungsstand des Themas:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="28e90-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="28e90-105">Jeder Datensatz stellt eine Sitzung dar, die Audio-oder Audio-und Videodaten umfasst.</span><span class="sxs-lookup"><span data-stu-id="28e90-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="28e90-106">Sie enthält allgemeine Informationen zur Sitzung.</span><span class="sxs-lookup"><span data-stu-id="28e90-106">It contains overall information about the session.</span></span> <span data-ttu-id="28e90-107">Eine Sitzung ist als SIP-Dialog (Audio oder Video Session Initiation Protocol) zwischen zwei Endpunkten definiert.</span><span class="sxs-lookup"><span data-stu-id="28e90-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28e90-108"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="28e90-109"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="28e90-110"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="28e90-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28e90-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="28e90-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="28e90-114">Primary</span><span class="sxs-lookup"><span data-stu-id="28e90-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="28e90-115"><a href="lync-server-2013-dialog-table.md">In lync Server 2013 auf die in der Dialog Tabelle</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="28e90-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-117">int</span><span class="sxs-lookup"><span data-stu-id="28e90-117">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-118">Primary</span><span class="sxs-lookup"><span data-stu-id="28e90-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="28e90-119"><a href="lync-server-2013-dialog-table.md">In lync Server 2013 auf die in der Dialog Tabelle</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="28e90-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-121">int</span><span class="sxs-lookup"><span data-stu-id="28e90-121">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-123">Konferenzschlüssel.</span><span class="sxs-lookup"><span data-stu-id="28e90-123">Conference key.</span></span> <span data-ttu-id="28e90-124">Referenziert aus dem <a href="lync-server-2013-conference-table.md">Konferenztisch in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28e90-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-126">int</span><span class="sxs-lookup"><span data-stu-id="28e90-126">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-128">Korrelationsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="28e90-128">Correlation key.</span></span> <span data-ttu-id="28e90-129">Referenziert aus der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28e90-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-130"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-131">Bit</span><span class="sxs-lookup"><span data-stu-id="28e90-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="28e90-132">Dialog Feld Kategorie; 0 ist lync Server Vermittlungsserver Bein; 1 ist Vermittlungsserver auf das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="28e90-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-134">Bit</span><span class="sxs-lookup"><span data-stu-id="28e90-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="28e90-135">Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="28e90-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-136"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-137">int</span><span class="sxs-lookup"><span data-stu-id="28e90-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="28e90-138">Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs abgeglichen wurden.</span><span class="sxs-lookup"><span data-stu-id="28e90-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="28e90-139">Für lync Server ist nur ein Wert definiert.</span><span class="sxs-lookup"><span data-stu-id="28e90-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="28e90-140">0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="28e90-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-142">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="28e90-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="28e90-143">Die Startzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="28e90-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-145">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="28e90-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="28e90-146">Die Endzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="28e90-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-148">int</span><span class="sxs-lookup"><span data-stu-id="28e90-148">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-149">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-150">Der Pool des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="28e90-150">The pool of the caller.</span></span> <span data-ttu-id="28e90-151">Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28e90-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-153">int</span><span class="sxs-lookup"><span data-stu-id="28e90-153">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-154">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-155">Der Pool des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="28e90-155">The pool of the call receiver.</span></span> <span data-ttu-id="28e90-156">Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28e90-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-158">int</span><span class="sxs-lookup"><span data-stu-id="28e90-158">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-159">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-160">SIP-URI in der vom SIP p-asserted Identity (Pai) des empfangenden Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="28e90-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="28e90-161">Wird aus der <a href="lync-server-2013-user-table.md">Benutzertabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="28e90-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-163">int</span><span class="sxs-lookup"><span data-stu-id="28e90-163">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-164">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-165">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="28e90-165">Caller’s URI.</span></span> <span data-ttu-id="28e90-166">Wird aus der <a href="lync-server-2013-user-table.md">Benutzertabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="28e90-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-168">int</span><span class="sxs-lookup"><span data-stu-id="28e90-168">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-169">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-170">Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="28e90-170">Caller’s endpoint.</span></span> <span data-ttu-id="28e90-171">Referenziert von der <a href="lync-server-2013-endpoint-table.md">Endpunkt Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28e90-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-173">Bit</span><span class="sxs-lookup"><span data-stu-id="28e90-173">bit</span></span></p></td>
<td><p><span data-ttu-id="28e90-174">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-175">Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="28e90-175">Caller’s user agent.</span></span> <span data-ttu-id="28e90-176">Verweist auf die <a href="lync-server-2013-useragent-table.md">userAgent-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28e90-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-178">smallint</span><span class="sxs-lookup"><span data-stu-id="28e90-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="28e90-179">Die Priorität dieses Anrufs.</span><span class="sxs-lookup"><span data-stu-id="28e90-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-181">Bit</span><span class="sxs-lookup"><span data-stu-id="28e90-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="28e90-182">Diese Spalte ist veraltet und wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="28e90-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="28e90-183">Stattdessen werden diese Informationen auf einer pro-Medien-Basis angegeben.</span><span class="sxs-lookup"><span data-stu-id="28e90-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="28e90-184">Weitere Informationen hierzu erhalten Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle "medialinie" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="28e90-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-186">int</span><span class="sxs-lookup"><span data-stu-id="28e90-186">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-187">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-188">P-Asserted-Identity des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="28e90-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="28e90-189">Die P-Asserted-Identity (Pai) wird verwendet, um die wahre Identität des Benutzers zu vermitteln, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="28e90-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-191">int</span><span class="sxs-lookup"><span data-stu-id="28e90-191">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-192">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-193">Endpunkt, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="28e90-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28e90-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-195">int</span><span class="sxs-lookup"><span data-stu-id="28e90-195">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-196">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-197">Benutzer-Agent, der von dem Benutzer, der den Anruf empfangen hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="28e90-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="28e90-198">Benutzer-Agents stellen das Clientendpunkt Gerät dar.</span><span class="sxs-lookup"><span data-stu-id="28e90-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28e90-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="28e90-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="28e90-200">int</span><span class="sxs-lookup"><span data-stu-id="28e90-200">int</span></span></p></td>
<td><p><span data-ttu-id="28e90-201">Fremd</span><span class="sxs-lookup"><span data-stu-id="28e90-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28e90-202">SIP-URI des Benutzers, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="28e90-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

