---
title: Lync Server 2013 von IPsec-Ausnahmen
description: IPsec-Ausnahmen lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575001"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="bc056-103">IPsec-Ausnahmen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc056-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc056-104">_**Letztes Änderungsstand des Themas:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="bc056-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="bc056-p101">Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.</span><span class="sxs-lookup"><span data-stu-id="bc056-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="bc056-107">In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.</span><span class="sxs-lookup"><span data-stu-id="bc056-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="bc056-108">Empfohlene IPsec-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="bc056-108">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc056-109">Regelname</span><span class="sxs-lookup"><span data-stu-id="bc056-109">Rule name</span></span></th>
<th><span data-ttu-id="bc056-110">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="bc056-110">Source IP</span></span></th>
<th><span data-ttu-id="bc056-111">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="bc056-111">Destination IP</span></span></th>
<th><span data-ttu-id="bc056-112">Protokoll</span><span class="sxs-lookup"><span data-stu-id="bc056-112">Protocol</span></span></th>
<th><span data-ttu-id="bc056-113">Quellport</span><span class="sxs-lookup"><span data-stu-id="bc056-113">Source port</span></span></th>
<th><span data-ttu-id="bc056-114">Zielport</span><span class="sxs-lookup"><span data-stu-id="bc056-114">Destination port</span></span></th>
<th><span data-ttu-id="bc056-115">Authentifizierungsanforderung</span><span class="sxs-lookup"><span data-stu-id="bc056-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc056-116">A/V-Edgeserver, intern eingehend</span><span class="sxs-lookup"><span data-stu-id="bc056-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-117">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-117">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-118">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="bc056-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="bc056-119">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-120">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-120">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-121">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-121">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-122">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc056-123">A/V-Edgeserver, extern eingehend</span><span class="sxs-lookup"><span data-stu-id="bc056-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-124">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-124">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-125">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="bc056-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="bc056-126">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-127">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-127">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-128">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-128">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-129">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc056-130">A/V-Edgeserver, intern ausgehend</span><span class="sxs-lookup"><span data-stu-id="bc056-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-131">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="bc056-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="bc056-132">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-132">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-133">UDP- &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-134">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-134">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-135">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-135">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-136">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc056-137">A/V-Edgeserver, extern ausgehend</span><span class="sxs-lookup"><span data-stu-id="bc056-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-138">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="bc056-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="bc056-139">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-139">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-140">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-141">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-141">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-142">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-142">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-143">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc056-144">Vermittlungsserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="bc056-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-145">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-145">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-146">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="bc056-146">Mediation</span></span></p>
<p><span data-ttu-id="bc056-147">Server (s)</span><span class="sxs-lookup"><span data-stu-id="bc056-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="bc056-148">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-149">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-149">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-150">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-150">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-151">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc056-152">Vermittlungsserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="bc056-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-153">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="bc056-153">Mediation</span></span></p>
<p><span data-ttu-id="bc056-154">Server (s)</span><span class="sxs-lookup"><span data-stu-id="bc056-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="bc056-155">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-155">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-156">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-157">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-157">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-158">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-158">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-159">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc056-160">Konferenzzentrale, eingehend</span><span class="sxs-lookup"><span data-stu-id="bc056-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-161">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-161">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-162">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="bc056-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="bc056-163">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-164">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-164">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-165">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-165">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-166">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc056-167">Konferenzzentrale (ausgehend)</span><span class="sxs-lookup"><span data-stu-id="bc056-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-168">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="bc056-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="bc056-169">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-169">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-170">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-171">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-171">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-172">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-172">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-173">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc056-174">A/V-Konferenzserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="bc056-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-175">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-175">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-176">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="bc056-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bc056-177">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-178">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-178">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-179">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-179">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-180">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc056-181">A/V-Konferenzen, ausgehend</span><span class="sxs-lookup"><span data-stu-id="bc056-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-182">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="bc056-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bc056-183">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-183">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-184">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-185">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-185">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-186">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-186">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-187">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc056-188">Exchange, eingehend</span><span class="sxs-lookup"><span data-stu-id="bc056-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-189">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-189">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-190">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="bc056-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="bc056-191">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-192">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-192">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-193">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-193">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-194">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc056-195">Anwendungsfreigabeserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="bc056-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-196">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-196">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-197">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="bc056-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="bc056-198">TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-199">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-199">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-200">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-200">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-201">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc056-202">Anwendungsfreigabeserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="bc056-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-203">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="bc056-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="bc056-204">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-204">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-205">TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-206">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-206">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-207">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-207">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-208">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc056-209">Exchange, ausgehend</span><span class="sxs-lookup"><span data-stu-id="bc056-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="bc056-210">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="bc056-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="bc056-211">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-211">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-212">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="bc056-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bc056-213">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-213">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-214">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-214">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-215">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc056-216">Clients</span><span class="sxs-lookup"><span data-stu-id="bc056-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="bc056-217">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-217">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-218">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-218">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-219">UDP</span><span class="sxs-lookup"><span data-stu-id="bc056-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="bc056-220">Angegebener Medienportbereich</span><span class="sxs-lookup"><span data-stu-id="bc056-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="bc056-221">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bc056-221">Any</span></span></p></td>
<td><p><span data-ttu-id="bc056-222">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="bc056-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

