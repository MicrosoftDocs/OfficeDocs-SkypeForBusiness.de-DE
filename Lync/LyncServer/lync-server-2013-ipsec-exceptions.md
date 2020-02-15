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
ms.openlocfilehash: db7291674485dec30211d88e2739b0da89fb334f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="39fa0-102">IPsec-Ausnahmen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39fa0-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39fa0-103">_**Letztes Änderungsstand des Themas:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="39fa0-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="39fa0-p101">Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.</span><span class="sxs-lookup"><span data-stu-id="39fa0-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="39fa0-106">In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.</span><span class="sxs-lookup"><span data-stu-id="39fa0-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="39fa0-107">Empfohlene IPsec-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="39fa0-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="39fa0-108">Regelname</span><span class="sxs-lookup"><span data-stu-id="39fa0-108">Rule name</span></span></th>
<th><span data-ttu-id="39fa0-109">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="39fa0-109">Source IP</span></span></th>
<th><span data-ttu-id="39fa0-110">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="39fa0-110">Destination IP</span></span></th>
<th><span data-ttu-id="39fa0-111">Protokoll</span><span class="sxs-lookup"><span data-stu-id="39fa0-111">Protocol</span></span></th>
<th><span data-ttu-id="39fa0-112">Quellport</span><span class="sxs-lookup"><span data-stu-id="39fa0-112">Source port</span></span></th>
<th><span data-ttu-id="39fa0-113">Zielport</span><span class="sxs-lookup"><span data-stu-id="39fa0-113">Destination port</span></span></th>
<th><span data-ttu-id="39fa0-114">Authentifizierungsanforderung</span><span class="sxs-lookup"><span data-stu-id="39fa0-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39fa0-115">A/V-Edgeserver, intern eingehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-116">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-116">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-117">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="39fa0-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="39fa0-118">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-119">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-119">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-120">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-120">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-121">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39fa0-122">A/V-Edgeserver, extern eingehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-123">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-123">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-124">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="39fa0-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="39fa0-125">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-126">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-126">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-127">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-127">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-128">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39fa0-129">A/V-Edgeserver, intern ausgehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-130">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="39fa0-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="39fa0-131">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-131">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-132">UDP &amp; -TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-133">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-133">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-134">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-134">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-135">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39fa0-136">A/V-Edgeserver, extern ausgehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-137">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="39fa0-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="39fa0-138">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-138">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-139">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-140">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-140">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-141">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-141">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-142">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39fa0-143">Vermittlungsserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-144">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-144">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-145">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="39fa0-145">Mediation</span></span></p>
<p><span data-ttu-id="39fa0-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="39fa0-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="39fa0-147">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-148">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-148">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-149">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-149">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-150">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39fa0-151">Vermittlungsserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-152">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="39fa0-152">Mediation</span></span></p>
<p><span data-ttu-id="39fa0-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="39fa0-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="39fa0-154">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-154">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-155">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-156">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-156">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-157">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-157">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-158">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39fa0-159">Konferenzzentrale, eingehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-160">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-160">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-161">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="39fa0-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="39fa0-162">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-163">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-163">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-164">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-164">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-165">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39fa0-166">Konferenzzentrale (ausgehend)</span><span class="sxs-lookup"><span data-stu-id="39fa0-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-167">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="39fa0-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="39fa0-168">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-168">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-169">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-170">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-170">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-171">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-171">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-172">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39fa0-173">A/V-Konferenzserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-174">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-174">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-175">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="39fa0-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="39fa0-176">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-177">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-177">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-178">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-178">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-179">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39fa0-180">A/V-Konferenzen, ausgehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-181">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="39fa0-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="39fa0-182">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-182">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-183">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-184">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-184">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-185">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-185">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-186">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39fa0-187">Exchange, eingehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-188">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-188">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-189">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="39fa0-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="39fa0-190">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-191">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-191">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-192">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-192">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-193">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39fa0-194">Anwendungsfreigabeserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-195">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-195">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-196">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="39fa0-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="39fa0-197">TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-198">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-198">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-199">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-199">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-200">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39fa0-201">Anwendungsfreigabeserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-202">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="39fa0-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="39fa0-203">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-203">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-204">TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-205">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-205">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-206">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-206">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-207">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39fa0-208">Exchange, ausgehend</span><span class="sxs-lookup"><span data-stu-id="39fa0-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="39fa0-209">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="39fa0-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="39fa0-210">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-210">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-211">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="39fa0-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-212">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-212">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-213">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-213">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-214">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39fa0-215">Clients</span><span class="sxs-lookup"><span data-stu-id="39fa0-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="39fa0-216">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-216">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-217">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-217">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-218">UDP</span><span class="sxs-lookup"><span data-stu-id="39fa0-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="39fa0-219">Angegebener Medienportbereich</span><span class="sxs-lookup"><span data-stu-id="39fa0-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="39fa0-220">Any</span><span class="sxs-lookup"><span data-stu-id="39fa0-220">Any</span></span></p></td>
<td><p><span data-ttu-id="39fa0-221">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="39fa0-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

