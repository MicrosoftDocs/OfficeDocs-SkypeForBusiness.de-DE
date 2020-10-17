---
title: 'Lync Server 2013: UserAgentDef-Tabelle (QoE)'
description: 'Lync Server 2013: UserAgentDef-Tabelle (QoE).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8546a33e607524b23755e9abf3edb2d5e2e417d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547341"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="c7155-103">UserAgentDef-Tabelle (QoE) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7155-103">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7155-104">_**Letztes Änderungsstand des Themas:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="c7155-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="c7155-105">Die Tabelle "UserAgentDef" ordnet Benutzer-Agent-IDs den aussagekräftigen Namen der Agents zu.</span><span class="sxs-lookup"><span data-stu-id="c7155-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="c7155-106">Benutzer-Agents sind Software Clients, die zum Herstellen einer Verbindung mit Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7155-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7155-107">UAType</span><span class="sxs-lookup"><span data-stu-id="c7155-107">UAType</span></span></th>
<th><span data-ttu-id="c7155-108">UAName</span><span class="sxs-lookup"><span data-stu-id="c7155-108">UAName</span></span></th>
<th><span data-ttu-id="c7155-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="c7155-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7155-110">1</span><span class="sxs-lookup"><span data-stu-id="c7155-110">1</span></span></p></td>
<td><p><span data-ttu-id="c7155-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="c7155-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="c7155-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="c7155-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-113">2</span><span class="sxs-lookup"><span data-stu-id="c7155-113">2</span></span></p></td>
<td><p><span data-ttu-id="c7155-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="c7155-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="c7155-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="c7155-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-116">4 </span><span class="sxs-lookup"><span data-stu-id="c7155-116">4</span></span></p></td>
<td><p><span data-ttu-id="c7155-117">OC</span><span class="sxs-lookup"><span data-stu-id="c7155-117">OC</span></span></p></td>
<td><p><span data-ttu-id="c7155-118">OC</span><span class="sxs-lookup"><span data-stu-id="c7155-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-119">8 </span><span class="sxs-lookup"><span data-stu-id="c7155-119">8</span></span></p></td>
<td><p><span data-ttu-id="c7155-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="c7155-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="c7155-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="c7155-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-122">16 </span><span class="sxs-lookup"><span data-stu-id="c7155-122">16</span></span></p></td>
<td><p><span data-ttu-id="c7155-123">LMC</span><span class="sxs-lookup"><span data-stu-id="c7155-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="c7155-124">LMC</span><span class="sxs-lookup"><span data-stu-id="c7155-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-125">32</span><span class="sxs-lookup"><span data-stu-id="c7155-125">32</span></span></p></td>
<td><p><span data-ttu-id="c7155-126">DVT</span><span class="sxs-lookup"><span data-stu-id="c7155-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="c7155-127">DVT</span><span class="sxs-lookup"><span data-stu-id="c7155-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-128">64</span><span class="sxs-lookup"><span data-stu-id="c7155-128">64</span></span></p></td>
<td><p><span data-ttu-id="c7155-129">MM</span><span class="sxs-lookup"><span data-stu-id="c7155-129">MM</span></span></p></td>
<td><p><span data-ttu-id="c7155-130">MM</span><span class="sxs-lookup"><span data-stu-id="c7155-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-131">64</span><span class="sxs-lookup"><span data-stu-id="c7155-131">64</span></span></p></td>
<td><p><span data-ttu-id="c7155-132">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="c7155-132">MC</span></span></p></td>
<td><p><span data-ttu-id="c7155-133">MM</span><span class="sxs-lookup"><span data-stu-id="c7155-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-134">128</span><span class="sxs-lookup"><span data-stu-id="c7155-134">128</span></span></p></td>
<td><p><span data-ttu-id="c7155-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="c7155-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="c7155-136">Attendant</span><span class="sxs-lookup"><span data-stu-id="c7155-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-137">256</span><span class="sxs-lookup"><span data-stu-id="c7155-137">256</span></span></p></td>
<td><p><span data-ttu-id="c7155-138">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="c7155-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="c7155-139">CAS</span><span class="sxs-lookup"><span data-stu-id="c7155-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-140">512</span><span class="sxs-lookup"><span data-stu-id="c7155-140">512</span></span></p></td>
<td><p><span data-ttu-id="c7155-141">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="c7155-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="c7155-142">CAA</span><span class="sxs-lookup"><span data-stu-id="c7155-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-143">512</span><span class="sxs-lookup"><span data-stu-id="c7155-143">512</span></span></p></td>
<td><p><span data-ttu-id="c7155-144">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="c7155-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="c7155-145">CAA</span><span class="sxs-lookup"><span data-stu-id="c7155-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-146">1024</span><span class="sxs-lookup"><span data-stu-id="c7155-146">1024</span></span></p></td>
<td><p><span data-ttu-id="c7155-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="c7155-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="c7155-148">RGS</span><span class="sxs-lookup"><span data-stu-id="c7155-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-149">1032</span><span class="sxs-lookup"><span data-stu-id="c7155-149">1032</span></span></p></td>
<td><p><span data-ttu-id="c7155-150">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="c7155-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="c7155-151">CPS</span><span class="sxs-lookup"><span data-stu-id="c7155-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-152">1040</span><span class="sxs-lookup"><span data-stu-id="c7155-152">1040</span></span></p></td>
<td><p><span data-ttu-id="c7155-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="c7155-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="c7155-154">AS</span><span class="sxs-lookup"><span data-stu-id="c7155-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-155">2048</span><span class="sxs-lookup"><span data-stu-id="c7155-155">2048</span></span></p></td>
<td><p><span data-ttu-id="c7155-156">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="c7155-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="c7155-157">CCS</span><span class="sxs-lookup"><span data-stu-id="c7155-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-158">16386</span><span class="sxs-lookup"><span data-stu-id="c7155-158">16386</span></span></p></td>
<td><p><span data-ttu-id="c7155-159">Como</span><span class="sxs-lookup"><span data-stu-id="c7155-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="c7155-160">Como</span><span class="sxs-lookup"><span data-stu-id="c7155-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-161">16387</span><span class="sxs-lookup"><span data-stu-id="c7155-161">16387</span></span></p></td>
<td><p><span data-ttu-id="c7155-162">CWA</span><span class="sxs-lookup"><span data-stu-id="c7155-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="c7155-163">CWA</span><span class="sxs-lookup"><span data-stu-id="c7155-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-164">16388</span><span class="sxs-lookup"><span data-stu-id="c7155-164">16388</span></span></p></td>
<td><p><span data-ttu-id="c7155-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="c7155-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="c7155-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="c7155-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-167">16389</span><span class="sxs-lookup"><span data-stu-id="c7155-167">16389</span></span></p></td>
<td><p><span data-ttu-id="c7155-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="c7155-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="c7155-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="c7155-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-170">16393</span><span class="sxs-lookup"><span data-stu-id="c7155-170">16393</span></span></p></td>
<td><p><span data-ttu-id="c7155-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="c7155-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="c7155-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="c7155-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-173">16395</span><span class="sxs-lookup"><span data-stu-id="c7155-173">16395</span></span></p></td>
<td><p><span data-ttu-id="c7155-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="c7155-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="c7155-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="c7155-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-176">16396</span><span class="sxs-lookup"><span data-stu-id="c7155-176">16396</span></span></p></td>
<td><p><span data-ttu-id="c7155-177">St</span><span class="sxs-lookup"><span data-stu-id="c7155-177">ST</span></span></p></td>
<td><p><span data-ttu-id="c7155-178">St</span><span class="sxs-lookup"><span data-stu-id="c7155-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-179">16397</span><span class="sxs-lookup"><span data-stu-id="c7155-179">16397</span></span></p></td>
<td><p><span data-ttu-id="c7155-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="c7155-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="c7155-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="c7155-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-182">16398</span><span class="sxs-lookup"><span data-stu-id="c7155-182">16398</span></span></p></td>
<td><p><span data-ttu-id="c7155-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="c7155-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="c7155-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="c7155-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-185">16399</span><span class="sxs-lookup"><span data-stu-id="c7155-185">16399</span></span></p></td>
<td><p><span data-ttu-id="c7155-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="c7155-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="c7155-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="c7155-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-188">16400</span><span class="sxs-lookup"><span data-stu-id="c7155-188">16400</span></span></p></td>
<td><p><span data-ttu-id="c7155-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="c7155-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="c7155-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="c7155-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-191">16401</span><span class="sxs-lookup"><span data-stu-id="c7155-191">16401</span></span></p></td>
<td><p><span data-ttu-id="c7155-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="c7155-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="c7155-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="c7155-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-194">16402</span><span class="sxs-lookup"><span data-stu-id="c7155-194">16402</span></span></p></td>
<td><p><span data-ttu-id="c7155-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="c7155-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="c7155-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="c7155-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-197">16403</span><span class="sxs-lookup"><span data-stu-id="c7155-197">16403</span></span></p></td>
<td><p><span data-ttu-id="c7155-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="c7155-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="c7155-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="c7155-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-200">16404</span><span class="sxs-lookup"><span data-stu-id="c7155-200">16404</span></span></p></td>
<td><p><span data-ttu-id="c7155-201">PCs</span><span class="sxs-lookup"><span data-stu-id="c7155-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="c7155-202">PCs</span><span class="sxs-lookup"><span data-stu-id="c7155-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-203">16405</span><span class="sxs-lookup"><span data-stu-id="c7155-203">16405</span></span></p></td>
<td><p><span data-ttu-id="c7155-204">LWA</span><span class="sxs-lookup"><span data-stu-id="c7155-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="c7155-205">LWA</span><span class="sxs-lookup"><span data-stu-id="c7155-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-206">16406</span><span class="sxs-lookup"><span data-stu-id="c7155-206">16406</span></span></p></td>
<td><p><span data-ttu-id="c7155-207">OWA</span><span class="sxs-lookup"><span data-stu-id="c7155-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="c7155-208">OWA</span><span class="sxs-lookup"><span data-stu-id="c7155-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-209">16407</span><span class="sxs-lookup"><span data-stu-id="c7155-209">16407</span></span></p></td>
<td><p><span data-ttu-id="c7155-210">AOC</span><span class="sxs-lookup"><span data-stu-id="c7155-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="c7155-211">AOC</span><span class="sxs-lookup"><span data-stu-id="c7155-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-212">16408</span><span class="sxs-lookup"><span data-stu-id="c7155-212">16408</span></span></p></td>
<td><p><span data-ttu-id="c7155-213">GCC</span><span class="sxs-lookup"><span data-stu-id="c7155-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="c7155-214">GCC</span><span class="sxs-lookup"><span data-stu-id="c7155-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-215">16409</span><span class="sxs-lookup"><span data-stu-id="c7155-215">16409</span></span></p></td>
<td><p><span data-ttu-id="c7155-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="c7155-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="c7155-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="c7155-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-218">16410</span><span class="sxs-lookup"><span data-stu-id="c7155-218">16410</span></span></p></td>
<td><p><span data-ttu-id="c7155-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="c7155-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="c7155-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="c7155-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7155-221">32769</span><span class="sxs-lookup"><span data-stu-id="c7155-221">32769</span></span></p></td>
<td><p><span data-ttu-id="c7155-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="c7155-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="c7155-223">Gateway</span><span class="sxs-lookup"><span data-stu-id="c7155-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7155-224">32770</span><span class="sxs-lookup"><span data-stu-id="c7155-224">32770</span></span></p></td>
<td><p><span data-ttu-id="c7155-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="c7155-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="c7155-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="c7155-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

