---
title: Lync Server 2013 von IPsec-Ausnahmen
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
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514152"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="1feb5-102">IPsec-Ausnahmen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1feb5-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1feb5-103">_**Letztes Änderungsstand des Themas:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="1feb5-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="1feb5-p101">Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.</span><span class="sxs-lookup"><span data-stu-id="1feb5-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="1feb5-106">In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.</span><span class="sxs-lookup"><span data-stu-id="1feb5-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="1feb5-107">Empfohlene IPsec-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="1feb5-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="1feb5-108">Regelname</span><span class="sxs-lookup"><span data-stu-id="1feb5-108">Rule name</span></span></th>
<th><span data-ttu-id="1feb5-109">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="1feb5-109">Source IP</span></span></th>
<th><span data-ttu-id="1feb5-110">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="1feb5-110">Destination IP</span></span></th>
<th><span data-ttu-id="1feb5-111">Protokoll</span><span class="sxs-lookup"><span data-stu-id="1feb5-111">Protocol</span></span></th>
<th><span data-ttu-id="1feb5-112">Quellport</span><span class="sxs-lookup"><span data-stu-id="1feb5-112">Source port</span></span></th>
<th><span data-ttu-id="1feb5-113">Zielport</span><span class="sxs-lookup"><span data-stu-id="1feb5-113">Destination port</span></span></th>
<th><span data-ttu-id="1feb5-114">Authentifizierungsanforderung</span><span class="sxs-lookup"><span data-stu-id="1feb5-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1feb5-115">A/V-Edgeserver, intern eingehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-116">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-116">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-117">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="1feb5-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="1feb5-118">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-119">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-119">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-120">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-120">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-121">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1feb5-122">A/V-Edgeserver, extern eingehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-123">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-123">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-124">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="1feb5-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="1feb5-125">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-126">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-126">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-127">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-127">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-128">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1feb5-129">A/V-Edgeserver, intern ausgehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-130">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="1feb5-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="1feb5-131">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-131">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-132">UDP- &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-133">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-133">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-134">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-134">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-135">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1feb5-136">A/V-Edgeserver, extern ausgehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-137">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="1feb5-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="1feb5-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-138">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-139">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-140">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-140">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-141">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-141">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-142">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1feb5-143">Vermittlungsserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-144">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-144">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-145">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="1feb5-145">Mediation</span></span></p>
<p><span data-ttu-id="1feb5-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="1feb5-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="1feb5-147">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-148">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-148">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-149">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-149">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-150">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1feb5-151">Vermittlungsserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-152">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="1feb5-152">Mediation</span></span></p>
<p><span data-ttu-id="1feb5-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="1feb5-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="1feb5-154">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-154">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-155">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-156">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-156">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-157">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-157">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-158">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1feb5-159">Konferenzzentrale, eingehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-160">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-160">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-161">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="1feb5-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="1feb5-162">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-163">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-163">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-164">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-164">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-165">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1feb5-166">Konferenzzentrale (ausgehend)</span><span class="sxs-lookup"><span data-stu-id="1feb5-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-167">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="1feb5-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="1feb5-168">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-168">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-169">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-170">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-170">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-171">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-171">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-172">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1feb5-173">A/V-Konferenzserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-174">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-174">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-175">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="1feb5-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1feb5-176">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-177">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-177">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-178">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-178">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-179">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1feb5-180">A/V-Konferenzen, ausgehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-181">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="1feb5-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="1feb5-182">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-182">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-183">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-184">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-184">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-185">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-185">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-186">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1feb5-187">Exchange, eingehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-188">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-188">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-189">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="1feb5-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="1feb5-190">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-191">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-191">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-192">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-192">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-193">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1feb5-194">Anwendungsfreigabeserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-195">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-195">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-196">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="1feb5-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="1feb5-197">TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-198">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-198">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-199">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-199">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-200">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1feb5-201">Anwendungsfreigabeserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-202">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="1feb5-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="1feb5-203">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-203">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-204">TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-205">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-205">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-206">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-206">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-207">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1feb5-208">Exchange, ausgehend</span><span class="sxs-lookup"><span data-stu-id="1feb5-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="1feb5-209">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="1feb5-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="1feb5-210">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-210">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-211">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="1feb5-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-212">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-212">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-213">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-213">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-214">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1feb5-215">Clients</span><span class="sxs-lookup"><span data-stu-id="1feb5-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="1feb5-216">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-216">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-217">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-217">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-218">UDP</span><span class="sxs-lookup"><span data-stu-id="1feb5-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="1feb5-219">Angegebener Medienportbereich</span><span class="sxs-lookup"><span data-stu-id="1feb5-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="1feb5-220">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1feb5-220">Any</span></span></p></td>
<td><p><span data-ttu-id="1feb5-221">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="1feb5-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

