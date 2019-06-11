---
title: Lync Server 2013 IPsec-Ausnahmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="e368c-102">IPsec-Ausnahmen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e368c-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e368c-103">_**Letztes Änderungsdatum des Themas:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="e368c-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="e368c-104">Für Unternehmensnetzwerke, in denen IPSec (Internet Protocol Security) (siehe IETF-RFC 4301-4309) bereitgestellt wurde, muss IPsec über den Portbereich deaktiviert werden, der für die Bereitstellung von Audio-, Video-und Panorama Video verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e368c-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="e368c-105">Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.</span><span class="sxs-lookup"><span data-stu-id="e368c-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="e368c-106">In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.</span><span class="sxs-lookup"><span data-stu-id="e368c-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="e368c-107">Empfohlene IPsec-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="e368c-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="e368c-108">Regelname</span><span class="sxs-lookup"><span data-stu-id="e368c-108">Rule name</span></span></th>
<th><span data-ttu-id="e368c-109">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="e368c-109">Source IP</span></span></th>
<th><span data-ttu-id="e368c-110">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="e368c-110">Destination IP</span></span></th>
<th><span data-ttu-id="e368c-111">Protokoll</span><span class="sxs-lookup"><span data-stu-id="e368c-111">Protocol</span></span></th>
<th><span data-ttu-id="e368c-112">Quellport</span><span class="sxs-lookup"><span data-stu-id="e368c-112">Source port</span></span></th>
<th><span data-ttu-id="e368c-113">Zielport</span><span class="sxs-lookup"><span data-stu-id="e368c-113">Destination port</span></span></th>
<th><span data-ttu-id="e368c-114">Authentifizierungsanforderung</span><span class="sxs-lookup"><span data-stu-id="e368c-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e368c-115">A/V-Edgeserver, intern eingehend</span><span class="sxs-lookup"><span data-stu-id="e368c-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-116">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-116">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-117">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="e368c-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="e368c-118">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-119">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-119">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-120">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-120">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-121">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e368c-122">A/V-Edgeserver, extern eingehend</span><span class="sxs-lookup"><span data-stu-id="e368c-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-123">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-123">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-124">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="e368c-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="e368c-125">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-126">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-126">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-127">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-127">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-128">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e368c-129">A/V-Edgeserver, intern ausgehend</span><span class="sxs-lookup"><span data-stu-id="e368c-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-130">A/V-Edgeserver, intern</span><span class="sxs-lookup"><span data-stu-id="e368c-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="e368c-131">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-131">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-132">UDP &amp; -TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-133">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-133">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-134">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-134">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-135">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e368c-136">A/V-Edgeserver, extern ausgehend</span><span class="sxs-lookup"><span data-stu-id="e368c-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-137">A/V-Edgeserver, extern</span><span class="sxs-lookup"><span data-stu-id="e368c-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="e368c-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-138">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-139">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-140">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-140">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-141">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-141">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-142">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e368c-143">Vermittlungsserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="e368c-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-144">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-144">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-145">Vermittlungs-</span><span class="sxs-lookup"><span data-stu-id="e368c-145">Mediation</span></span></p>
<p><span data-ttu-id="e368c-146">server</span><span class="sxs-lookup"><span data-stu-id="e368c-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="e368c-147">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-148">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-148">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-149">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-149">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-150">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e368c-151">Vermittlungsserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="e368c-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-152">Vermittlungs-</span><span class="sxs-lookup"><span data-stu-id="e368c-152">Mediation</span></span></p>
<p><span data-ttu-id="e368c-153">server</span><span class="sxs-lookup"><span data-stu-id="e368c-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="e368c-154">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-154">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-155">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-156">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-156">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-157">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-157">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-158">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e368c-159">Konferenzzentrale, eingehend</span><span class="sxs-lookup"><span data-stu-id="e368c-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-160">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-160">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-161">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="e368c-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="e368c-162">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-163">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-163">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-164">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-164">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-165">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e368c-166">Konferenzzentrale (ausgehend)</span><span class="sxs-lookup"><span data-stu-id="e368c-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-167">Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="e368c-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="e368c-168">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-168">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-169">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-170">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-170">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-171">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-171">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-172">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e368c-173">A/V-Konferenzserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="e368c-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-174">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-174">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-175">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="e368c-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e368c-176">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-177">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-177">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-178">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-178">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-179">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e368c-180">A/V-Konferenzen, ausgehend</span><span class="sxs-lookup"><span data-stu-id="e368c-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-181">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="e368c-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e368c-182">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-182">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-183">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-184">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-184">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-185">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-185">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-186">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e368c-187">Exchange, eingehend</span><span class="sxs-lookup"><span data-stu-id="e368c-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-188">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-188">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-189">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="e368c-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="e368c-190">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-191">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-191">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-192">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-192">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-193">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e368c-194">Anwendungsfreigabeserver, eingehend</span><span class="sxs-lookup"><span data-stu-id="e368c-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-195">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-195">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-196">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="e368c-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="e368c-197">TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-198">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-198">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-199">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-199">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-200">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e368c-201">Anwendungsfreigabeserver, ausgehend</span><span class="sxs-lookup"><span data-stu-id="e368c-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-202">Anwendungsfreigabeserver</span><span class="sxs-lookup"><span data-stu-id="e368c-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="e368c-203">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-203">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-204">TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-205">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-205">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-206">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-206">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-207">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e368c-208">Exchange, ausgehend</span><span class="sxs-lookup"><span data-stu-id="e368c-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="e368c-209">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="e368c-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="e368c-210">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-210">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-211">UDP und TCP</span><span class="sxs-lookup"><span data-stu-id="e368c-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="e368c-212">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-212">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-213">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-213">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-214">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e368c-215">Clients</span><span class="sxs-lookup"><span data-stu-id="e368c-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="e368c-216">Beliebig </span><span class="sxs-lookup"><span data-stu-id="e368c-216">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-217">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-217">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-218">UDP</span><span class="sxs-lookup"><span data-stu-id="e368c-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="e368c-219">Angegebener Medienportbereich</span><span class="sxs-lookup"><span data-stu-id="e368c-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="e368c-220">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e368c-220">Any</span></span></p></td>
<td><p><span data-ttu-id="e368c-221">Nicht authentifizieren</span><span class="sxs-lookup"><span data-stu-id="e368c-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

