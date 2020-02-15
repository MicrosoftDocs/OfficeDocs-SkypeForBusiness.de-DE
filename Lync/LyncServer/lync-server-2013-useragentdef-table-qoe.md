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
ms.openlocfilehash: ebddb1e0313d0c47acb4171929d12d352f69c260
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="bff72-102">UserAgentDef-Tabelle (QoE) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bff72-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bff72-103">_**Letztes Änderungsstand des Themas:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="bff72-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="bff72-104">Die Tabelle "UserAgentDef" ordnet Benutzer-Agent-IDs den aussagekräftigen Namen der Agents zu.</span><span class="sxs-lookup"><span data-stu-id="bff72-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="bff72-105">Benutzer-Agents sind Software Clients, die zum Herstellen einer Verbindung mit Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bff72-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bff72-106">UAType</span><span class="sxs-lookup"><span data-stu-id="bff72-106">UAType</span></span></th>
<th><span data-ttu-id="bff72-107">UAName</span><span class="sxs-lookup"><span data-stu-id="bff72-107">UAName</span></span></th>
<th><span data-ttu-id="bff72-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="bff72-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bff72-109">1 </span><span class="sxs-lookup"><span data-stu-id="bff72-109">1</span></span></p></td>
<td><p><span data-ttu-id="bff72-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="bff72-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="bff72-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="bff72-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-112">2 </span><span class="sxs-lookup"><span data-stu-id="bff72-112">2</span></span></p></td>
<td><p><span data-ttu-id="bff72-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="bff72-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="bff72-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="bff72-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-115">4 </span><span class="sxs-lookup"><span data-stu-id="bff72-115">4</span></span></p></td>
<td><p><span data-ttu-id="bff72-116">OC</span><span class="sxs-lookup"><span data-stu-id="bff72-116">OC</span></span></p></td>
<td><p><span data-ttu-id="bff72-117">OC</span><span class="sxs-lookup"><span data-stu-id="bff72-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-118">8 </span><span class="sxs-lookup"><span data-stu-id="bff72-118">8</span></span></p></td>
<td><p><span data-ttu-id="bff72-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="bff72-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="bff72-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="bff72-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-121">16 </span><span class="sxs-lookup"><span data-stu-id="bff72-121">16</span></span></p></td>
<td><p><span data-ttu-id="bff72-122">LMC</span><span class="sxs-lookup"><span data-stu-id="bff72-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="bff72-123">LMC</span><span class="sxs-lookup"><span data-stu-id="bff72-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-124">32</span><span class="sxs-lookup"><span data-stu-id="bff72-124">32</span></span></p></td>
<td><p><span data-ttu-id="bff72-125">DVT</span><span class="sxs-lookup"><span data-stu-id="bff72-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="bff72-126">DVT</span><span class="sxs-lookup"><span data-stu-id="bff72-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-127">64</span><span class="sxs-lookup"><span data-stu-id="bff72-127">64</span></span></p></td>
<td><p><span data-ttu-id="bff72-128">MM</span><span class="sxs-lookup"><span data-stu-id="bff72-128">MM</span></span></p></td>
<td><p><span data-ttu-id="bff72-129">MM</span><span class="sxs-lookup"><span data-stu-id="bff72-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-130">64</span><span class="sxs-lookup"><span data-stu-id="bff72-130">64</span></span></p></td>
<td><p><span data-ttu-id="bff72-131">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="bff72-131">MC</span></span></p></td>
<td><p><span data-ttu-id="bff72-132">MM</span><span class="sxs-lookup"><span data-stu-id="bff72-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-133">128</span><span class="sxs-lookup"><span data-stu-id="bff72-133">128</span></span></p></td>
<td><p><span data-ttu-id="bff72-134">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="bff72-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="bff72-135">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="bff72-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-136">256</span><span class="sxs-lookup"><span data-stu-id="bff72-136">256</span></span></p></td>
<td><p><span data-ttu-id="bff72-137">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="bff72-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="bff72-138">CAS</span><span class="sxs-lookup"><span data-stu-id="bff72-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-139">512</span><span class="sxs-lookup"><span data-stu-id="bff72-139">512</span></span></p></td>
<td><p><span data-ttu-id="bff72-140">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="bff72-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="bff72-141">CAA</span><span class="sxs-lookup"><span data-stu-id="bff72-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-142">512</span><span class="sxs-lookup"><span data-stu-id="bff72-142">512</span></span></p></td>
<td><p><span data-ttu-id="bff72-143">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="bff72-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="bff72-144">CAA</span><span class="sxs-lookup"><span data-stu-id="bff72-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-145">1024</span><span class="sxs-lookup"><span data-stu-id="bff72-145">1024</span></span></p></td>
<td><p><span data-ttu-id="bff72-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="bff72-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="bff72-147">RGS</span><span class="sxs-lookup"><span data-stu-id="bff72-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-148">1032</span><span class="sxs-lookup"><span data-stu-id="bff72-148">1032</span></span></p></td>
<td><p><span data-ttu-id="bff72-149">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="bff72-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="bff72-150">CPS</span><span class="sxs-lookup"><span data-stu-id="bff72-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-151">1040</span><span class="sxs-lookup"><span data-stu-id="bff72-151">1040</span></span></p></td>
<td><p><span data-ttu-id="bff72-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="bff72-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="bff72-153">AS</span><span class="sxs-lookup"><span data-stu-id="bff72-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-154">2048</span><span class="sxs-lookup"><span data-stu-id="bff72-154">2048</span></span></p></td>
<td><p><span data-ttu-id="bff72-155">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="bff72-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="bff72-156">CCS</span><span class="sxs-lookup"><span data-stu-id="bff72-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-157">16386</span><span class="sxs-lookup"><span data-stu-id="bff72-157">16386</span></span></p></td>
<td><p><span data-ttu-id="bff72-158">Como</span><span class="sxs-lookup"><span data-stu-id="bff72-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="bff72-159">Como</span><span class="sxs-lookup"><span data-stu-id="bff72-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-160">16387</span><span class="sxs-lookup"><span data-stu-id="bff72-160">16387</span></span></p></td>
<td><p><span data-ttu-id="bff72-161">CWA</span><span class="sxs-lookup"><span data-stu-id="bff72-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="bff72-162">CWA</span><span class="sxs-lookup"><span data-stu-id="bff72-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-163">16388</span><span class="sxs-lookup"><span data-stu-id="bff72-163">16388</span></span></p></td>
<td><p><span data-ttu-id="bff72-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="bff72-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="bff72-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="bff72-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-166">16389</span><span class="sxs-lookup"><span data-stu-id="bff72-166">16389</span></span></p></td>
<td><p><span data-ttu-id="bff72-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="bff72-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="bff72-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="bff72-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-169">16393</span><span class="sxs-lookup"><span data-stu-id="bff72-169">16393</span></span></p></td>
<td><p><span data-ttu-id="bff72-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="bff72-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="bff72-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="bff72-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-172">16395</span><span class="sxs-lookup"><span data-stu-id="bff72-172">16395</span></span></p></td>
<td><p><span data-ttu-id="bff72-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="bff72-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="bff72-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="bff72-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-175">16396</span><span class="sxs-lookup"><span data-stu-id="bff72-175">16396</span></span></p></td>
<td><p><span data-ttu-id="bff72-176">St</span><span class="sxs-lookup"><span data-stu-id="bff72-176">ST</span></span></p></td>
<td><p><span data-ttu-id="bff72-177">St</span><span class="sxs-lookup"><span data-stu-id="bff72-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-178">16397</span><span class="sxs-lookup"><span data-stu-id="bff72-178">16397</span></span></p></td>
<td><p><span data-ttu-id="bff72-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="bff72-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="bff72-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="bff72-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-181">16398</span><span class="sxs-lookup"><span data-stu-id="bff72-181">16398</span></span></p></td>
<td><p><span data-ttu-id="bff72-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="bff72-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="bff72-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="bff72-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-184">16399</span><span class="sxs-lookup"><span data-stu-id="bff72-184">16399</span></span></p></td>
<td><p><span data-ttu-id="bff72-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="bff72-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="bff72-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="bff72-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-187">16400</span><span class="sxs-lookup"><span data-stu-id="bff72-187">16400</span></span></p></td>
<td><p><span data-ttu-id="bff72-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="bff72-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="bff72-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="bff72-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-190">16401</span><span class="sxs-lookup"><span data-stu-id="bff72-190">16401</span></span></p></td>
<td><p><span data-ttu-id="bff72-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="bff72-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="bff72-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="bff72-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-193">16402</span><span class="sxs-lookup"><span data-stu-id="bff72-193">16402</span></span></p></td>
<td><p><span data-ttu-id="bff72-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="bff72-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="bff72-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="bff72-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-196">16403</span><span class="sxs-lookup"><span data-stu-id="bff72-196">16403</span></span></p></td>
<td><p><span data-ttu-id="bff72-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="bff72-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="bff72-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="bff72-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-199">16404</span><span class="sxs-lookup"><span data-stu-id="bff72-199">16404</span></span></p></td>
<td><p><span data-ttu-id="bff72-200">PCs</span><span class="sxs-lookup"><span data-stu-id="bff72-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="bff72-201">PCs</span><span class="sxs-lookup"><span data-stu-id="bff72-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-202">16405</span><span class="sxs-lookup"><span data-stu-id="bff72-202">16405</span></span></p></td>
<td><p><span data-ttu-id="bff72-203">LWA</span><span class="sxs-lookup"><span data-stu-id="bff72-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="bff72-204">LWA</span><span class="sxs-lookup"><span data-stu-id="bff72-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-205">16406</span><span class="sxs-lookup"><span data-stu-id="bff72-205">16406</span></span></p></td>
<td><p><span data-ttu-id="bff72-206">OWA</span><span class="sxs-lookup"><span data-stu-id="bff72-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="bff72-207">OWA</span><span class="sxs-lookup"><span data-stu-id="bff72-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-208">16407</span><span class="sxs-lookup"><span data-stu-id="bff72-208">16407</span></span></p></td>
<td><p><span data-ttu-id="bff72-209">AOC</span><span class="sxs-lookup"><span data-stu-id="bff72-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="bff72-210">AOC</span><span class="sxs-lookup"><span data-stu-id="bff72-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-211">16408</span><span class="sxs-lookup"><span data-stu-id="bff72-211">16408</span></span></p></td>
<td><p><span data-ttu-id="bff72-212">GCC</span><span class="sxs-lookup"><span data-stu-id="bff72-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="bff72-213">GCC</span><span class="sxs-lookup"><span data-stu-id="bff72-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-214">16409</span><span class="sxs-lookup"><span data-stu-id="bff72-214">16409</span></span></p></td>
<td><p><span data-ttu-id="bff72-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="bff72-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="bff72-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="bff72-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-217">16410</span><span class="sxs-lookup"><span data-stu-id="bff72-217">16410</span></span></p></td>
<td><p><span data-ttu-id="bff72-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="bff72-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="bff72-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="bff72-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff72-220">32769</span><span class="sxs-lookup"><span data-stu-id="bff72-220">32769</span></span></p></td>
<td><p><span data-ttu-id="bff72-221">Gateway</span><span class="sxs-lookup"><span data-stu-id="bff72-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="bff72-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="bff72-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff72-223">32770</span><span class="sxs-lookup"><span data-stu-id="bff72-223">32770</span></span></p></td>
<td><p><span data-ttu-id="bff72-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="bff72-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="bff72-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="bff72-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

