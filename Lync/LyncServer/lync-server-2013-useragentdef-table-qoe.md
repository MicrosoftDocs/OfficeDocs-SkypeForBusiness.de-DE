---
title: 'Lync Server 2013: UserAgentDef-Tabelle (QoE)'
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
ms.openlocfilehash: a37ea828dfe633ca8a685feb61311d59f443ae14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="68072-102">UserAgentDef-Tabelle (QoE) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68072-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68072-103">_**Letztes Änderungsstand des Themas:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="68072-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="68072-104">Die Tabelle "UserAgentDef" ordnet Benutzer-Agent-IDs den aussagekräftigen Namen der Agents zu.</span><span class="sxs-lookup"><span data-stu-id="68072-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="68072-105">Benutzer-Agents sind Software Clients, die zum Herstellen einer Verbindung mit Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68072-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68072-106">UAType</span><span class="sxs-lookup"><span data-stu-id="68072-106">UAType</span></span></th>
<th><span data-ttu-id="68072-107">UAName</span><span class="sxs-lookup"><span data-stu-id="68072-107">UAName</span></span></th>
<th><span data-ttu-id="68072-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="68072-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68072-109">1</span><span class="sxs-lookup"><span data-stu-id="68072-109">1</span></span></p></td>
<td><p><span data-ttu-id="68072-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="68072-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="68072-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="68072-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-112">2</span><span class="sxs-lookup"><span data-stu-id="68072-112">2</span></span></p></td>
<td><p><span data-ttu-id="68072-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="68072-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="68072-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="68072-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-115">4</span><span class="sxs-lookup"><span data-stu-id="68072-115">4</span></span></p></td>
<td><p><span data-ttu-id="68072-116">OC</span><span class="sxs-lookup"><span data-stu-id="68072-116">OC</span></span></p></td>
<td><p><span data-ttu-id="68072-117">OC</span><span class="sxs-lookup"><span data-stu-id="68072-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-118">8 </span><span class="sxs-lookup"><span data-stu-id="68072-118">8</span></span></p></td>
<td><p><span data-ttu-id="68072-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="68072-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="68072-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="68072-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-121">16 </span><span class="sxs-lookup"><span data-stu-id="68072-121">16</span></span></p></td>
<td><p><span data-ttu-id="68072-122">LMC</span><span class="sxs-lookup"><span data-stu-id="68072-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="68072-123">LMC</span><span class="sxs-lookup"><span data-stu-id="68072-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-124">32</span><span class="sxs-lookup"><span data-stu-id="68072-124">32</span></span></p></td>
<td><p><span data-ttu-id="68072-125">DVT</span><span class="sxs-lookup"><span data-stu-id="68072-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="68072-126">DVT</span><span class="sxs-lookup"><span data-stu-id="68072-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-127">64</span><span class="sxs-lookup"><span data-stu-id="68072-127">64</span></span></p></td>
<td><p><span data-ttu-id="68072-128">MM</span><span class="sxs-lookup"><span data-stu-id="68072-128">MM</span></span></p></td>
<td><p><span data-ttu-id="68072-129">MM</span><span class="sxs-lookup"><span data-stu-id="68072-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-130">64</span><span class="sxs-lookup"><span data-stu-id="68072-130">64</span></span></p></td>
<td><p><span data-ttu-id="68072-131">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="68072-131">MC</span></span></p></td>
<td><p><span data-ttu-id="68072-132">MM</span><span class="sxs-lookup"><span data-stu-id="68072-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-133">128</span><span class="sxs-lookup"><span data-stu-id="68072-133">128</span></span></p></td>
<td><p><span data-ttu-id="68072-134">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="68072-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="68072-135">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="68072-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-136">256</span><span class="sxs-lookup"><span data-stu-id="68072-136">256</span></span></p></td>
<td><p><span data-ttu-id="68072-137">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="68072-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="68072-138">CAS</span><span class="sxs-lookup"><span data-stu-id="68072-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-139">512</span><span class="sxs-lookup"><span data-stu-id="68072-139">512</span></span></p></td>
<td><p><span data-ttu-id="68072-140">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="68072-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="68072-141">CAA</span><span class="sxs-lookup"><span data-stu-id="68072-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-142">512</span><span class="sxs-lookup"><span data-stu-id="68072-142">512</span></span></p></td>
<td><p><span data-ttu-id="68072-143">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="68072-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="68072-144">CAA</span><span class="sxs-lookup"><span data-stu-id="68072-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-145">1024</span><span class="sxs-lookup"><span data-stu-id="68072-145">1024</span></span></p></td>
<td><p><span data-ttu-id="68072-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="68072-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="68072-147">RGS</span><span class="sxs-lookup"><span data-stu-id="68072-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-148">1032</span><span class="sxs-lookup"><span data-stu-id="68072-148">1032</span></span></p></td>
<td><p><span data-ttu-id="68072-149">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="68072-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="68072-150">CPS</span><span class="sxs-lookup"><span data-stu-id="68072-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-151">1040</span><span class="sxs-lookup"><span data-stu-id="68072-151">1040</span></span></p></td>
<td><p><span data-ttu-id="68072-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="68072-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="68072-153">AS</span><span class="sxs-lookup"><span data-stu-id="68072-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-154">2048</span><span class="sxs-lookup"><span data-stu-id="68072-154">2048</span></span></p></td>
<td><p><span data-ttu-id="68072-155">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="68072-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="68072-156">CCS</span><span class="sxs-lookup"><span data-stu-id="68072-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-157">16386</span><span class="sxs-lookup"><span data-stu-id="68072-157">16386</span></span></p></td>
<td><p><span data-ttu-id="68072-158">Como</span><span class="sxs-lookup"><span data-stu-id="68072-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="68072-159">Como</span><span class="sxs-lookup"><span data-stu-id="68072-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-160">16387</span><span class="sxs-lookup"><span data-stu-id="68072-160">16387</span></span></p></td>
<td><p><span data-ttu-id="68072-161">CWA</span><span class="sxs-lookup"><span data-stu-id="68072-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="68072-162">CWA</span><span class="sxs-lookup"><span data-stu-id="68072-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-163">16388</span><span class="sxs-lookup"><span data-stu-id="68072-163">16388</span></span></p></td>
<td><p><span data-ttu-id="68072-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="68072-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="68072-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="68072-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-166">16389</span><span class="sxs-lookup"><span data-stu-id="68072-166">16389</span></span></p></td>
<td><p><span data-ttu-id="68072-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="68072-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="68072-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="68072-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-169">16393</span><span class="sxs-lookup"><span data-stu-id="68072-169">16393</span></span></p></td>
<td><p><span data-ttu-id="68072-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="68072-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="68072-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="68072-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-172">16395</span><span class="sxs-lookup"><span data-stu-id="68072-172">16395</span></span></p></td>
<td><p><span data-ttu-id="68072-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="68072-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="68072-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="68072-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-175">16396</span><span class="sxs-lookup"><span data-stu-id="68072-175">16396</span></span></p></td>
<td><p><span data-ttu-id="68072-176">St</span><span class="sxs-lookup"><span data-stu-id="68072-176">ST</span></span></p></td>
<td><p><span data-ttu-id="68072-177">St</span><span class="sxs-lookup"><span data-stu-id="68072-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-178">16397</span><span class="sxs-lookup"><span data-stu-id="68072-178">16397</span></span></p></td>
<td><p><span data-ttu-id="68072-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="68072-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="68072-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="68072-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-181">16398</span><span class="sxs-lookup"><span data-stu-id="68072-181">16398</span></span></p></td>
<td><p><span data-ttu-id="68072-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="68072-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="68072-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="68072-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-184">16399</span><span class="sxs-lookup"><span data-stu-id="68072-184">16399</span></span></p></td>
<td><p><span data-ttu-id="68072-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="68072-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="68072-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="68072-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-187">16400</span><span class="sxs-lookup"><span data-stu-id="68072-187">16400</span></span></p></td>
<td><p><span data-ttu-id="68072-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="68072-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="68072-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="68072-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-190">16401</span><span class="sxs-lookup"><span data-stu-id="68072-190">16401</span></span></p></td>
<td><p><span data-ttu-id="68072-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="68072-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="68072-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="68072-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-193">16402</span><span class="sxs-lookup"><span data-stu-id="68072-193">16402</span></span></p></td>
<td><p><span data-ttu-id="68072-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="68072-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="68072-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="68072-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-196">16403</span><span class="sxs-lookup"><span data-stu-id="68072-196">16403</span></span></p></td>
<td><p><span data-ttu-id="68072-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="68072-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="68072-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="68072-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-199">16404</span><span class="sxs-lookup"><span data-stu-id="68072-199">16404</span></span></p></td>
<td><p><span data-ttu-id="68072-200">PCs</span><span class="sxs-lookup"><span data-stu-id="68072-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="68072-201">PCs</span><span class="sxs-lookup"><span data-stu-id="68072-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-202">16405</span><span class="sxs-lookup"><span data-stu-id="68072-202">16405</span></span></p></td>
<td><p><span data-ttu-id="68072-203">LWA</span><span class="sxs-lookup"><span data-stu-id="68072-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="68072-204">LWA</span><span class="sxs-lookup"><span data-stu-id="68072-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-205">16406</span><span class="sxs-lookup"><span data-stu-id="68072-205">16406</span></span></p></td>
<td><p><span data-ttu-id="68072-206">OWA</span><span class="sxs-lookup"><span data-stu-id="68072-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="68072-207">OWA</span><span class="sxs-lookup"><span data-stu-id="68072-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-208">16407</span><span class="sxs-lookup"><span data-stu-id="68072-208">16407</span></span></p></td>
<td><p><span data-ttu-id="68072-209">AOC</span><span class="sxs-lookup"><span data-stu-id="68072-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="68072-210">AOC</span><span class="sxs-lookup"><span data-stu-id="68072-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-211">16408</span><span class="sxs-lookup"><span data-stu-id="68072-211">16408</span></span></p></td>
<td><p><span data-ttu-id="68072-212">GCC</span><span class="sxs-lookup"><span data-stu-id="68072-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="68072-213">GCC</span><span class="sxs-lookup"><span data-stu-id="68072-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-214">16409</span><span class="sxs-lookup"><span data-stu-id="68072-214">16409</span></span></p></td>
<td><p><span data-ttu-id="68072-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="68072-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="68072-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="68072-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-217">16410</span><span class="sxs-lookup"><span data-stu-id="68072-217">16410</span></span></p></td>
<td><p><span data-ttu-id="68072-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="68072-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="68072-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="68072-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68072-220">32769</span><span class="sxs-lookup"><span data-stu-id="68072-220">32769</span></span></p></td>
<td><p><span data-ttu-id="68072-221">Gateway</span><span class="sxs-lookup"><span data-stu-id="68072-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="68072-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="68072-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68072-223">32770</span><span class="sxs-lookup"><span data-stu-id="68072-223">32770</span></span></p></td>
<td><p><span data-ttu-id="68072-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="68072-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="68072-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="68072-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

