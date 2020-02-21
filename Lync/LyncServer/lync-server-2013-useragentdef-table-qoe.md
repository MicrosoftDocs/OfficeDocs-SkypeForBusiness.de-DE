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
ms.openlocfilehash: d2daba0f4e37a07065edf6a9c80955047a7d26b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="50c7b-102">UserAgentDef-Tabelle (QoE) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50c7b-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50c7b-103">_**Letztes Änderungsstand des Themas:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="50c7b-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="50c7b-104">Die Tabelle "UserAgentDef" ordnet Benutzer-Agent-IDs den aussagekräftigen Namen der Agents zu.</span><span class="sxs-lookup"><span data-stu-id="50c7b-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="50c7b-105">Benutzer-Agents sind Software Clients, die zum Herstellen einer Verbindung mit Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50c7b-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50c7b-106">UAType</span><span class="sxs-lookup"><span data-stu-id="50c7b-106">UAType</span></span></th>
<th><span data-ttu-id="50c7b-107">UAName</span><span class="sxs-lookup"><span data-stu-id="50c7b-107">UAName</span></span></th>
<th><span data-ttu-id="50c7b-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="50c7b-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-109">1</span><span class="sxs-lookup"><span data-stu-id="50c7b-109">1</span></span></p></td>
<td><p><span data-ttu-id="50c7b-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="50c7b-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="50c7b-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="50c7b-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-112">2</span><span class="sxs-lookup"><span data-stu-id="50c7b-112">2</span></span></p></td>
<td><p><span data-ttu-id="50c7b-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="50c7b-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="50c7b-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="50c7b-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-115">4</span><span class="sxs-lookup"><span data-stu-id="50c7b-115">4</span></span></p></td>
<td><p><span data-ttu-id="50c7b-116">OC</span><span class="sxs-lookup"><span data-stu-id="50c7b-116">OC</span></span></p></td>
<td><p><span data-ttu-id="50c7b-117">OC</span><span class="sxs-lookup"><span data-stu-id="50c7b-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-118">8 </span><span class="sxs-lookup"><span data-stu-id="50c7b-118">8</span></span></p></td>
<td><p><span data-ttu-id="50c7b-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="50c7b-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="50c7b-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="50c7b-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-121">16 </span><span class="sxs-lookup"><span data-stu-id="50c7b-121">16</span></span></p></td>
<td><p><span data-ttu-id="50c7b-122">LMC</span><span class="sxs-lookup"><span data-stu-id="50c7b-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="50c7b-123">LMC</span><span class="sxs-lookup"><span data-stu-id="50c7b-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-124">32</span><span class="sxs-lookup"><span data-stu-id="50c7b-124">32</span></span></p></td>
<td><p><span data-ttu-id="50c7b-125">DVT</span><span class="sxs-lookup"><span data-stu-id="50c7b-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="50c7b-126">DVT</span><span class="sxs-lookup"><span data-stu-id="50c7b-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-127">64</span><span class="sxs-lookup"><span data-stu-id="50c7b-127">64</span></span></p></td>
<td><p><span data-ttu-id="50c7b-128">MM</span><span class="sxs-lookup"><span data-stu-id="50c7b-128">MM</span></span></p></td>
<td><p><span data-ttu-id="50c7b-129">MM</span><span class="sxs-lookup"><span data-stu-id="50c7b-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-130">64</span><span class="sxs-lookup"><span data-stu-id="50c7b-130">64</span></span></p></td>
<td><p><span data-ttu-id="50c7b-131">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="50c7b-131">MC</span></span></p></td>
<td><p><span data-ttu-id="50c7b-132">MM</span><span class="sxs-lookup"><span data-stu-id="50c7b-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-133">128</span><span class="sxs-lookup"><span data-stu-id="50c7b-133">128</span></span></p></td>
<td><p><span data-ttu-id="50c7b-134">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="50c7b-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="50c7b-135">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="50c7b-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-136">256</span><span class="sxs-lookup"><span data-stu-id="50c7b-136">256</span></span></p></td>
<td><p><span data-ttu-id="50c7b-137">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="50c7b-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="50c7b-138">CAS</span><span class="sxs-lookup"><span data-stu-id="50c7b-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-139">512</span><span class="sxs-lookup"><span data-stu-id="50c7b-139">512</span></span></p></td>
<td><p><span data-ttu-id="50c7b-140">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="50c7b-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="50c7b-141">CAA</span><span class="sxs-lookup"><span data-stu-id="50c7b-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-142">512</span><span class="sxs-lookup"><span data-stu-id="50c7b-142">512</span></span></p></td>
<td><p><span data-ttu-id="50c7b-143">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="50c7b-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="50c7b-144">CAA</span><span class="sxs-lookup"><span data-stu-id="50c7b-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-145">1024</span><span class="sxs-lookup"><span data-stu-id="50c7b-145">1024</span></span></p></td>
<td><p><span data-ttu-id="50c7b-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="50c7b-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="50c7b-147">RGS</span><span class="sxs-lookup"><span data-stu-id="50c7b-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-148">1032</span><span class="sxs-lookup"><span data-stu-id="50c7b-148">1032</span></span></p></td>
<td><p><span data-ttu-id="50c7b-149">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="50c7b-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="50c7b-150">CPS</span><span class="sxs-lookup"><span data-stu-id="50c7b-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-151">1040</span><span class="sxs-lookup"><span data-stu-id="50c7b-151">1040</span></span></p></td>
<td><p><span data-ttu-id="50c7b-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="50c7b-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="50c7b-153">AS</span><span class="sxs-lookup"><span data-stu-id="50c7b-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-154">2048</span><span class="sxs-lookup"><span data-stu-id="50c7b-154">2048</span></span></p></td>
<td><p><span data-ttu-id="50c7b-155">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="50c7b-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="50c7b-156">CCS</span><span class="sxs-lookup"><span data-stu-id="50c7b-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-157">16386</span><span class="sxs-lookup"><span data-stu-id="50c7b-157">16386</span></span></p></td>
<td><p><span data-ttu-id="50c7b-158">Como</span><span class="sxs-lookup"><span data-stu-id="50c7b-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="50c7b-159">Como</span><span class="sxs-lookup"><span data-stu-id="50c7b-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-160">16387</span><span class="sxs-lookup"><span data-stu-id="50c7b-160">16387</span></span></p></td>
<td><p><span data-ttu-id="50c7b-161">CWA</span><span class="sxs-lookup"><span data-stu-id="50c7b-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="50c7b-162">CWA</span><span class="sxs-lookup"><span data-stu-id="50c7b-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-163">16388</span><span class="sxs-lookup"><span data-stu-id="50c7b-163">16388</span></span></p></td>
<td><p><span data-ttu-id="50c7b-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="50c7b-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="50c7b-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="50c7b-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-166">16389</span><span class="sxs-lookup"><span data-stu-id="50c7b-166">16389</span></span></p></td>
<td><p><span data-ttu-id="50c7b-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="50c7b-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="50c7b-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="50c7b-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-169">16393</span><span class="sxs-lookup"><span data-stu-id="50c7b-169">16393</span></span></p></td>
<td><p><span data-ttu-id="50c7b-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="50c7b-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="50c7b-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="50c7b-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-172">16395</span><span class="sxs-lookup"><span data-stu-id="50c7b-172">16395</span></span></p></td>
<td><p><span data-ttu-id="50c7b-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="50c7b-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="50c7b-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="50c7b-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-175">16396</span><span class="sxs-lookup"><span data-stu-id="50c7b-175">16396</span></span></p></td>
<td><p><span data-ttu-id="50c7b-176">St</span><span class="sxs-lookup"><span data-stu-id="50c7b-176">ST</span></span></p></td>
<td><p><span data-ttu-id="50c7b-177">St</span><span class="sxs-lookup"><span data-stu-id="50c7b-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-178">16397</span><span class="sxs-lookup"><span data-stu-id="50c7b-178">16397</span></span></p></td>
<td><p><span data-ttu-id="50c7b-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="50c7b-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="50c7b-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="50c7b-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-181">16398</span><span class="sxs-lookup"><span data-stu-id="50c7b-181">16398</span></span></p></td>
<td><p><span data-ttu-id="50c7b-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="50c7b-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-184">16399</span><span class="sxs-lookup"><span data-stu-id="50c7b-184">16399</span></span></p></td>
<td><p><span data-ttu-id="50c7b-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="50c7b-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-187">16400</span><span class="sxs-lookup"><span data-stu-id="50c7b-187">16400</span></span></p></td>
<td><p><span data-ttu-id="50c7b-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="50c7b-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-190">16401</span><span class="sxs-lookup"><span data-stu-id="50c7b-190">16401</span></span></p></td>
<td><p><span data-ttu-id="50c7b-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="50c7b-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-193">16402</span><span class="sxs-lookup"><span data-stu-id="50c7b-193">16402</span></span></p></td>
<td><p><span data-ttu-id="50c7b-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="50c7b-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="50c7b-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-196">16403</span><span class="sxs-lookup"><span data-stu-id="50c7b-196">16403</span></span></p></td>
<td><p><span data-ttu-id="50c7b-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="50c7b-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="50c7b-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="50c7b-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-199">16404</span><span class="sxs-lookup"><span data-stu-id="50c7b-199">16404</span></span></p></td>
<td><p><span data-ttu-id="50c7b-200">PCs</span><span class="sxs-lookup"><span data-stu-id="50c7b-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="50c7b-201">PCs</span><span class="sxs-lookup"><span data-stu-id="50c7b-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-202">16405</span><span class="sxs-lookup"><span data-stu-id="50c7b-202">16405</span></span></p></td>
<td><p><span data-ttu-id="50c7b-203">LWA</span><span class="sxs-lookup"><span data-stu-id="50c7b-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="50c7b-204">LWA</span><span class="sxs-lookup"><span data-stu-id="50c7b-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-205">16406</span><span class="sxs-lookup"><span data-stu-id="50c7b-205">16406</span></span></p></td>
<td><p><span data-ttu-id="50c7b-206">OWA</span><span class="sxs-lookup"><span data-stu-id="50c7b-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="50c7b-207">OWA</span><span class="sxs-lookup"><span data-stu-id="50c7b-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-208">16407</span><span class="sxs-lookup"><span data-stu-id="50c7b-208">16407</span></span></p></td>
<td><p><span data-ttu-id="50c7b-209">AOC</span><span class="sxs-lookup"><span data-stu-id="50c7b-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="50c7b-210">AOC</span><span class="sxs-lookup"><span data-stu-id="50c7b-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-211">16408</span><span class="sxs-lookup"><span data-stu-id="50c7b-211">16408</span></span></p></td>
<td><p><span data-ttu-id="50c7b-212">GCC</span><span class="sxs-lookup"><span data-stu-id="50c7b-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="50c7b-213">GCC</span><span class="sxs-lookup"><span data-stu-id="50c7b-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-214">16409</span><span class="sxs-lookup"><span data-stu-id="50c7b-214">16409</span></span></p></td>
<td><p><span data-ttu-id="50c7b-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="50c7b-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="50c7b-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="50c7b-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-217">16410</span><span class="sxs-lookup"><span data-stu-id="50c7b-217">16410</span></span></p></td>
<td><p><span data-ttu-id="50c7b-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="50c7b-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="50c7b-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="50c7b-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50c7b-220">32769</span><span class="sxs-lookup"><span data-stu-id="50c7b-220">32769</span></span></p></td>
<td><p><span data-ttu-id="50c7b-221">Gateway</span><span class="sxs-lookup"><span data-stu-id="50c7b-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="50c7b-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="50c7b-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50c7b-223">32770</span><span class="sxs-lookup"><span data-stu-id="50c7b-223">32770</span></span></p></td>
<td><p><span data-ttu-id="50c7b-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="50c7b-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="50c7b-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="50c7b-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

