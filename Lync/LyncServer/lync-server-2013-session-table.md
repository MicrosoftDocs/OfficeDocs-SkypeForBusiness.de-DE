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
ms.openlocfilehash: f927957f21c67a8cfca6b169b99f7de9275740fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="d6152-102">Sitzungstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6152-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6152-103">_**Letztes Änderungsstand des Themas:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="d6152-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="d6152-104">Jeder Datensatz stellt eine Sitzung dar, die Audio-oder Audio-und Videodaten umfasst.</span><span class="sxs-lookup"><span data-stu-id="d6152-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="d6152-105">Sie enthält allgemeine Informationen zur Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d6152-105">It contains overall information about the session.</span></span> <span data-ttu-id="d6152-106">Eine Sitzung ist als SIP-Dialog (Audio oder Video Session Initiation Protocol) zwischen zwei Endpunkten definiert.</span><span class="sxs-lookup"><span data-stu-id="d6152-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6152-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d6152-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d6152-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d6152-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6152-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d6152-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d6152-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d6152-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d6152-114"><a href="lync-server-2013-dialog-table.md">In lync Server 2013 auf die in der Dialog Tabelle</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d6152-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-116">int</span><span class="sxs-lookup"><span data-stu-id="d6152-116">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d6152-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="d6152-118"><a href="lync-server-2013-dialog-table.md">In lync Server 2013 auf die in der Dialog Tabelle</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d6152-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-120">int</span><span class="sxs-lookup"><span data-stu-id="d6152-120">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-122">Konferenzschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d6152-122">Conference key.</span></span> <span data-ttu-id="d6152-123">Referenziert aus dem <a href="lync-server-2013-conference-table.md">Konferenztisch in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6152-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-125">int</span><span class="sxs-lookup"><span data-stu-id="d6152-125">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-126">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-127">Korrelationsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d6152-127">Correlation key.</span></span> <span data-ttu-id="d6152-128">Referenziert aus der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6152-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-130">Bit</span><span class="sxs-lookup"><span data-stu-id="d6152-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6152-131">Dialog Feld Kategorie; 0 ist lync Server Vermittlungsserver Bein; 1 ist Vermittlungsserver auf das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="d6152-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-133">Bit</span><span class="sxs-lookup"><span data-stu-id="d6152-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d6152-134">Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d6152-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-136">int</span><span class="sxs-lookup"><span data-stu-id="d6152-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d6152-137">Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs abgeglichen wurden.</span><span class="sxs-lookup"><span data-stu-id="d6152-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="d6152-138">Für lync Server ist nur ein Wert definiert.</span><span class="sxs-lookup"><span data-stu-id="d6152-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="d6152-139">0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="d6152-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-141">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d6152-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6152-142">Die Startzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d6152-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-144">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d6152-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6152-145">Die Endzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d6152-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-147">int</span><span class="sxs-lookup"><span data-stu-id="d6152-147">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-148">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-149">Der Pool des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d6152-149">The pool of the caller.</span></span> <span data-ttu-id="d6152-150">Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6152-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-152">int</span><span class="sxs-lookup"><span data-stu-id="d6152-152">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-153">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-154">Der Pool des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="d6152-154">The pool of the call receiver.</span></span> <span data-ttu-id="d6152-155">Referenziert aus der <a href="lync-server-2013-pool-table.md">Pool Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6152-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-157">int</span><span class="sxs-lookup"><span data-stu-id="d6152-157">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-158">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-159">SIP-URI in der vom SIP p-asserted Identity (Pai) des empfangenden Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="d6152-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="d6152-160">Wird aus der <a href="lync-server-2013-user-table.md">Benutzertabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="d6152-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-162">int</span><span class="sxs-lookup"><span data-stu-id="d6152-162">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-163">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-164">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d6152-164">Caller’s URI.</span></span> <span data-ttu-id="d6152-165">Wird aus der <a href="lync-server-2013-user-table.md">Benutzertabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="d6152-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-167">int</span><span class="sxs-lookup"><span data-stu-id="d6152-167">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-168">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-169">Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d6152-169">Caller’s endpoint.</span></span> <span data-ttu-id="d6152-170">Referenziert von der <a href="lync-server-2013-endpoint-table.md">Endpunkt Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6152-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-172">Bit</span><span class="sxs-lookup"><span data-stu-id="d6152-172">bit</span></span></p></td>
<td><p><span data-ttu-id="d6152-173">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-174">Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d6152-174">Caller’s user agent.</span></span> <span data-ttu-id="d6152-175">Verweist auf die <a href="lync-server-2013-useragent-table.md">userAgent-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6152-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-177">smallint</span><span class="sxs-lookup"><span data-stu-id="d6152-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d6152-178">Die Priorität dieses Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d6152-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-180">Bit</span><span class="sxs-lookup"><span data-stu-id="d6152-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d6152-181">Diese Spalte ist veraltet und wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6152-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d6152-182">Stattdessen werden diese Informationen auf einer pro-Medien-Basis angegeben.</span><span class="sxs-lookup"><span data-stu-id="d6152-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="d6152-183">Weitere Informationen hierzu erhalten Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle "medialinie" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d6152-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-185">int</span><span class="sxs-lookup"><span data-stu-id="d6152-185">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-186">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-187">P-Asserted-Identity des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="d6152-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="d6152-188">Die P-Asserted-Identity (Pai) wird verwendet, um die wahre Identität des Benutzers zu vermitteln, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="d6152-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-190">int</span><span class="sxs-lookup"><span data-stu-id="d6152-190">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-192">Endpunkt, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="d6152-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6152-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-194">int</span><span class="sxs-lookup"><span data-stu-id="d6152-194">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-195">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-196">Benutzer-Agent, der von dem Benutzer, der den Anruf empfangen hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d6152-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="d6152-197">Benutzer-Agents stellen das Clientendpunkt Gerät dar.</span><span class="sxs-lookup"><span data-stu-id="d6152-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6152-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="d6152-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d6152-199">int</span><span class="sxs-lookup"><span data-stu-id="d6152-199">int</span></span></p></td>
<td><p><span data-ttu-id="d6152-200">Fremd</span><span class="sxs-lookup"><span data-stu-id="d6152-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d6152-201">SIP-URI des Benutzers, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="d6152-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

