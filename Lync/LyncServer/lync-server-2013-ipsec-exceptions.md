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
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="20bbd-102">IPsec-Ausnahmen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20bbd-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20bbd-103">_**Letztes Änderungsstand des Themas:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="20bbd-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="20bbd-p101">Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.</span><span class="sxs-lookup"><span data-stu-id="20bbd-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="20bbd-106">In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.</span><span class="sxs-lookup"><span data-stu-id="20bbd-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="20bbd-107">Empfohlene IPsec-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="20bbd-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="20bbd-108">Regelname</span><span class="sxs-lookup"><span data-stu-id="20bbd-108">Rule name</span></span></th>
<th><span data-ttu-id="20bbd-109">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="20bbd-109">Source IP</span></span></th>
<th><span data-ttu-id="20bbd-110">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="20bbd-110">Destination IP</span></span></th>
<th><span data-ttu-id="20bbd-111">Protokoll</span><span class="sxs-lookup"><span data-stu-id="20bbd-111">Protocol</span></span></th>
<th><span data-ttu-id="20bbd-112">Quellport</span><span class="sxs-lookup"><span data-stu-id="20bbd-112">Source port</span></span></th>
<th><span data-ttu-id="20bbd-113">Zielport</span><span class="sxs-lookup"><span data-stu-id="20bbd-113">Destination port</span></span></th>
<th><span data-ttu-id="20bbd-114">Authentifizierungsanforderung</span><span class="sxs-lookup"><span data-stu-id="20bbd-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20bbd-115">A/V-Edgeserver, intern eingehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-116">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-116">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-117">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="20bbd-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="20bbd-118">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-119">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-119">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-120">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-120">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-121">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bbd-122">A/V-Edgeserver, extern eingehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-123">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-123">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-124">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="20bbd-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="20bbd-125">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-126">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-126">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-127">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-127">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-128">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bbd-129">A/V-Edgeserver, intern ausgehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-130">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="20bbd-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="20bbd-131">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-131">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-132">UDP &amp; -TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-133">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-133">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-134">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-134">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-135">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bbd-136">A/V-Edgeserver, extern ausgehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-137">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="20bbd-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="20bbd-138">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-138">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-139">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-140">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-140">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-141">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-141">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-142">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bbd-143">Vermittlungsserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-144">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-144">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-145">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="20bbd-145">Mediation</span></span></p>
<p><span data-ttu-id="20bbd-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="20bbd-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="20bbd-147">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-148">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-148">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-149">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-149">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-150">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bbd-151">Vermittlungsserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-152">Vermittlungs</span><span class="sxs-lookup"><span data-stu-id="20bbd-152">Mediation</span></span></p>
<p><span data-ttu-id="20bbd-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="20bbd-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="20bbd-154">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-154">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-155">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-156">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-156">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-157">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-157">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-158">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bbd-159">Konferenzzentrale, eingehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-160">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-160">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-161">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="20bbd-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="20bbd-162">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-163">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-163">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-164">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-164">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-165">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bbd-166">Konferenzzentrale (ausgehend)</span><span class="sxs-lookup"><span data-stu-id="20bbd-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-167">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="20bbd-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="20bbd-168">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-168">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-169">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-170">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-170">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-171">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-171">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-172">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bbd-173">A/V-Konferenzserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-174">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-174">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-175">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="20bbd-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="20bbd-176">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-177">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-177">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-178">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-178">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-179">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bbd-180">A/V-Konferenzen, ausgehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-181">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="20bbd-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="20bbd-182">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-182">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-183">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-184">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-184">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-185">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-185">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-186">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bbd-187">Exchange, eingehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-188">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-188">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-189">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="20bbd-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="20bbd-190">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-191">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-191">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-192">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-192">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-193">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bbd-194">Anwendungsfreigabeserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-195">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-195">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-196">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="20bbd-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="20bbd-197">TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-198">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-198">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-199">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-199">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-200">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bbd-201">Anwendungsfreigabeserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-202">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="20bbd-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="20bbd-203">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-203">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-204">TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-205">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-205">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-206">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-206">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-207">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bbd-208">Exchange, ausgehend</span><span class="sxs-lookup"><span data-stu-id="20bbd-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="20bbd-209">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="20bbd-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="20bbd-210">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-210">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-211">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="20bbd-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-212">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-212">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-213">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-213">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-214">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bbd-215">Clients</span><span class="sxs-lookup"><span data-stu-id="20bbd-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="20bbd-216">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-216">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-217">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-217">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-218">UDP</span><span class="sxs-lookup"><span data-stu-id="20bbd-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="20bbd-219">Angegebener Medienportbereich</span><span class="sxs-lookup"><span data-stu-id="20bbd-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="20bbd-220">Any</span><span class="sxs-lookup"><span data-stu-id="20bbd-220">Any</span></span></p></td>
<td><p><span data-ttu-id="20bbd-221">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="20bbd-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

