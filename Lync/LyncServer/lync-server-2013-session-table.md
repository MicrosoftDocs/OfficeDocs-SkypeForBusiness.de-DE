---
title: 'Lync Server 2013: Session-Tabelle'
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
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="6fd9c-102">Session-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fd9c-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fd9c-103">_**Letztes Änderungsdatum des Themas:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="6fd9c-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="6fd9c-104">Jeder Eintrag stellt eine Sitzung dar, die Audio-oder Audio-und Videodaten beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="6fd9c-105">Sie enthält allgemeine Informationen zur Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-105">It contains overall information about the session.</span></span> <span data-ttu-id="6fd9c-106">Eine Sitzung ist als SIP-Dialog (Audio-oder Video Session Initiation Protocol) zwischen zwei Endpunkten definiert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd9c-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6fd9c-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6fd9c-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6fd9c-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6fd9c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6fd9c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-114">Wird in der <a href="lync-server-2013-dialog-table.md">Dialog Feld Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-116">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-116">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-117">Primary</span><span class="sxs-lookup"><span data-stu-id="6fd9c-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-118">Wird in der <a href="lync-server-2013-dialog-table.md">Dialog Feld Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-120">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-120">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-122">Konferenz Taste.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-122">Conference key.</span></span> <span data-ttu-id="6fd9c-123">Wird aus der <a href="lync-server-2013-conference-table.md">Konferenz Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-125">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-125">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-126">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-127">Korrelationsschlüssel</span><span class="sxs-lookup"><span data-stu-id="6fd9c-127">Correlation key.</span></span> <span data-ttu-id="6fd9c-128">Wird in der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-130">bit</span><span class="sxs-lookup"><span data-stu-id="6fd9c-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6fd9c-131">Dialog Feld Kategorie; 0 ist lync Server to Mediation Server Leg; 1 ist Vermittlungs Server für das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-133">bit</span><span class="sxs-lookup"><span data-stu-id="6fd9c-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fd9c-134">Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-136">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fd9c-137">Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs übereinstimmten.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="6fd9c-138">Bei lync Server ist nur ein Wert definiert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="6fd9c-139">0x0001 – unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-141">datetime</span><span class="sxs-lookup"><span data-stu-id="6fd9c-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6fd9c-142">Startzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-144">datetime</span><span class="sxs-lookup"><span data-stu-id="6fd9c-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6fd9c-145">Endzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-147">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-147">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-148">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-149">Der Pool des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-149">The pool of the caller.</span></span> <span data-ttu-id="6fd9c-150">Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6fd9c-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-152">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-152">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-153">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-154">Der Pool des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-154">The pool of the call receiver.</span></span> <span data-ttu-id="6fd9c-155">Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6fd9c-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-157">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-157">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-158">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-159">SIP-URI in der SIP p-asserted Identity (Pai) des empfangenden Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="6fd9c-160">Wird in der <a href="lync-server-2013-user-table.md">Tabelle "Benutzer" in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-162">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-162">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-163">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-164">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-164">Caller’s URI.</span></span> <span data-ttu-id="6fd9c-165">Wird in der <a href="lync-server-2013-user-table.md">Tabelle "Benutzer" in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-167">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-167">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-168">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-169">Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-169">Caller’s endpoint.</span></span> <span data-ttu-id="6fd9c-170">Wird von der <a href="lync-server-2013-endpoint-table.md">Endpunkt Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-172">bit</span><span class="sxs-lookup"><span data-stu-id="6fd9c-172">bit</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-173">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-174">Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-174">Caller’s user agent.</span></span> <span data-ttu-id="6fd9c-175">Wird in der <a href="lync-server-2013-useragent-table.md">userAgent-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-177">smallint</span><span class="sxs-lookup"><span data-stu-id="6fd9c-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fd9c-178">Die Priorität dieses Anrufs.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-180">bit</span><span class="sxs-lookup"><span data-stu-id="6fd9c-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fd9c-181">Diese Spalte wurde als veraltet markiert und wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6fd9c-182">Stattdessen werden diese Informationen auf Basis einer einzelnen medienzeile gemeldet.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="6fd9c-183">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6fd9c-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-185">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-185">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-186">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-187">P-bestätigt – Identität des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="6fd9c-188">Die P-Asserted-Identity (Pai) wird verwendet, um die wahre Identität des Benutzers zu vermitteln, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-190">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-190">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-192">Endpunkt, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd9c-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-194">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-194">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-195">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-196">Benutzer-Agent des Benutzers, der den Anruf erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="6fd9c-197">Benutzer-Agents stellen das Clientendpunkt Gerät dar.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd9c-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="6fd9c-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd9c-199">int</span><span class="sxs-lookup"><span data-stu-id="6fd9c-199">int</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-200">Fremd</span><span class="sxs-lookup"><span data-stu-id="6fd9c-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6fd9c-201">SIP-URI des Benutzers, der den Anruf erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="6fd9c-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

