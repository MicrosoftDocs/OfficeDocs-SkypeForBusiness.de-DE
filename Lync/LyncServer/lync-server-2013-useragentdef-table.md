---
title: 'Lync Server 2013: UserAgentDef-Tabelle'
description: 'Lync Server 2013: UserAgentDef-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table
ms:assetid: 96c49239-d999-4045-8b64-9d1940cce8ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205100(v=OCS.15)
ms:contentKeyID: 48184860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b12239d0d6ba6e04a708708a1740dbf02c0e07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548641"
---
# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="68ec7-103">UserAgentDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ec7-103">UserAgentDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ec7-104">_**Letztes Änderungsstand des Themas:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="68ec7-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="68ec7-105">Die Tabelle "UserAgentDef" ordnet Benutzer-Agent-IDs den aussagekräftigen Namen der Agents zu.</span><span class="sxs-lookup"><span data-stu-id="68ec7-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="68ec7-106">Benutzer-Agents sind Software Clients, die zum Herstellen einer Verbindung mit Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68ec7-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="68ec7-107">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="68ec7-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68ec7-108">UAType</span><span class="sxs-lookup"><span data-stu-id="68ec7-108">UAType</span></span></th>
<th><span data-ttu-id="68ec7-109">UAName</span><span class="sxs-lookup"><span data-stu-id="68ec7-109">UAName</span></span></th>
<th><span data-ttu-id="68ec7-110">UACategory</span><span class="sxs-lookup"><span data-stu-id="68ec7-110">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-111">1</span><span class="sxs-lookup"><span data-stu-id="68ec7-111">1</span></span></p></td>
<td><p><span data-ttu-id="68ec7-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="68ec7-112">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="68ec7-113">MediationServer</span><span class="sxs-lookup"><span data-stu-id="68ec7-113">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-114">2</span><span class="sxs-lookup"><span data-stu-id="68ec7-114">2</span></span></p></td>
<td><p><span data-ttu-id="68ec7-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="68ec7-115">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="68ec7-116">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="68ec7-116">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-117">4 </span><span class="sxs-lookup"><span data-stu-id="68ec7-117">4</span></span></p></td>
<td><p><span data-ttu-id="68ec7-118">OC</span><span class="sxs-lookup"><span data-stu-id="68ec7-118">OC</span></span></p></td>
<td><p><span data-ttu-id="68ec7-119">OC</span><span class="sxs-lookup"><span data-stu-id="68ec7-119">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-120">8 </span><span class="sxs-lookup"><span data-stu-id="68ec7-120">8</span></span></p></td>
<td><p><span data-ttu-id="68ec7-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="68ec7-121">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="68ec7-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="68ec7-122">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-123">16 </span><span class="sxs-lookup"><span data-stu-id="68ec7-123">16</span></span></p></td>
<td><p><span data-ttu-id="68ec7-124">LMC</span><span class="sxs-lookup"><span data-stu-id="68ec7-124">LMC</span></span></p></td>
<td><p><span data-ttu-id="68ec7-125">LMC</span><span class="sxs-lookup"><span data-stu-id="68ec7-125">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-126">32</span><span class="sxs-lookup"><span data-stu-id="68ec7-126">32</span></span></p></td>
<td><p><span data-ttu-id="68ec7-127">DVT</span><span class="sxs-lookup"><span data-stu-id="68ec7-127">DVT</span></span></p></td>
<td><p><span data-ttu-id="68ec7-128">DVT</span><span class="sxs-lookup"><span data-stu-id="68ec7-128">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-129">64</span><span class="sxs-lookup"><span data-stu-id="68ec7-129">64</span></span></p></td>
<td><p><span data-ttu-id="68ec7-130">MM</span><span class="sxs-lookup"><span data-stu-id="68ec7-130">MM</span></span></p></td>
<td><p><span data-ttu-id="68ec7-131">MM</span><span class="sxs-lookup"><span data-stu-id="68ec7-131">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-132">64</span><span class="sxs-lookup"><span data-stu-id="68ec7-132">64</span></span></p></td>
<td><p><span data-ttu-id="68ec7-133">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="68ec7-133">MC</span></span></p></td>
<td><p><span data-ttu-id="68ec7-134">MM</span><span class="sxs-lookup"><span data-stu-id="68ec7-134">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-135">128</span><span class="sxs-lookup"><span data-stu-id="68ec7-135">128</span></span></p></td>
<td><p><span data-ttu-id="68ec7-136">Attendant</span><span class="sxs-lookup"><span data-stu-id="68ec7-136">Attendant</span></span></p></td>
<td><p><span data-ttu-id="68ec7-137">Attendant</span><span class="sxs-lookup"><span data-stu-id="68ec7-137">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-138">256</span><span class="sxs-lookup"><span data-stu-id="68ec7-138">256</span></span></p></td>
<td><p><span data-ttu-id="68ec7-139">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="68ec7-139">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="68ec7-140">CAS</span><span class="sxs-lookup"><span data-stu-id="68ec7-140">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-141">512</span><span class="sxs-lookup"><span data-stu-id="68ec7-141">512</span></span></p></td>
<td><p><span data-ttu-id="68ec7-142">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="68ec7-142">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="68ec7-143">CAA</span><span class="sxs-lookup"><span data-stu-id="68ec7-143">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-144">512</span><span class="sxs-lookup"><span data-stu-id="68ec7-144">512</span></span></p></td>
<td><p><span data-ttu-id="68ec7-145">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="68ec7-145">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="68ec7-146">CAA</span><span class="sxs-lookup"><span data-stu-id="68ec7-146">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-147">1024</span><span class="sxs-lookup"><span data-stu-id="68ec7-147">1024</span></span></p></td>
<td><p><span data-ttu-id="68ec7-148">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="68ec7-148">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="68ec7-149">RGS</span><span class="sxs-lookup"><span data-stu-id="68ec7-149">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-150">1032</span><span class="sxs-lookup"><span data-stu-id="68ec7-150">1032</span></span></p></td>
<td><p><span data-ttu-id="68ec7-151">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="68ec7-151">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="68ec7-152">CPS</span><span class="sxs-lookup"><span data-stu-id="68ec7-152">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-153">1040</span><span class="sxs-lookup"><span data-stu-id="68ec7-153">1040</span></span></p></td>
<td><p><span data-ttu-id="68ec7-154">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="68ec7-154">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="68ec7-155">AS</span><span class="sxs-lookup"><span data-stu-id="68ec7-155">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-156">2048</span><span class="sxs-lookup"><span data-stu-id="68ec7-156">2048</span></span></p></td>
<td><p><span data-ttu-id="68ec7-157">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="68ec7-157">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="68ec7-158">CCS</span><span class="sxs-lookup"><span data-stu-id="68ec7-158">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-159">16386</span><span class="sxs-lookup"><span data-stu-id="68ec7-159">16386</span></span></p></td>
<td><p><span data-ttu-id="68ec7-160">Como</span><span class="sxs-lookup"><span data-stu-id="68ec7-160">CoMo</span></span></p></td>
<td><p><span data-ttu-id="68ec7-161">Como</span><span class="sxs-lookup"><span data-stu-id="68ec7-161">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-162">16387</span><span class="sxs-lookup"><span data-stu-id="68ec7-162">16387</span></span></p></td>
<td><p><span data-ttu-id="68ec7-163">CWA</span><span class="sxs-lookup"><span data-stu-id="68ec7-163">CWA</span></span></p></td>
<td><p><span data-ttu-id="68ec7-164">CWA</span><span class="sxs-lookup"><span data-stu-id="68ec7-164">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-165">16388</span><span class="sxs-lookup"><span data-stu-id="68ec7-165">16388</span></span></p></td>
<td><p><span data-ttu-id="68ec7-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="68ec7-166">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="68ec7-167">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="68ec7-167">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-168">16389</span><span class="sxs-lookup"><span data-stu-id="68ec7-168">16389</span></span></p></td>
<td><p><span data-ttu-id="68ec7-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="68ec7-169">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="68ec7-170">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="68ec7-170">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-171">16393</span><span class="sxs-lookup"><span data-stu-id="68ec7-171">16393</span></span></p></td>
<td><p><span data-ttu-id="68ec7-172">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="68ec7-172">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="68ec7-173">ExUM</span><span class="sxs-lookup"><span data-stu-id="68ec7-173">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-174">16395</span><span class="sxs-lookup"><span data-stu-id="68ec7-174">16395</span></span></p></td>
<td><p><span data-ttu-id="68ec7-175">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="68ec7-175">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="68ec7-176">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="68ec7-176">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-177">16396</span><span class="sxs-lookup"><span data-stu-id="68ec7-177">16396</span></span></p></td>
<td><p><span data-ttu-id="68ec7-178">St</span><span class="sxs-lookup"><span data-stu-id="68ec7-178">ST</span></span></p></td>
<td><p><span data-ttu-id="68ec7-179">St</span><span class="sxs-lookup"><span data-stu-id="68ec7-179">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-180">16397</span><span class="sxs-lookup"><span data-stu-id="68ec7-180">16397</span></span></p></td>
<td><p><span data-ttu-id="68ec7-181">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="68ec7-181">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="68ec7-182">ASMCU</span><span class="sxs-lookup"><span data-stu-id="68ec7-182">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-183">16398</span><span class="sxs-lookup"><span data-stu-id="68ec7-183">16398</span></span></p></td>
<td><p><span data-ttu-id="68ec7-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-184">WPLync</span></span></p></td>
<td><p><span data-ttu-id="68ec7-185">WPLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-185">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-186">16399</span><span class="sxs-lookup"><span data-stu-id="68ec7-186">16399</span></span></p></td>
<td><p><span data-ttu-id="68ec7-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-187">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="68ec7-188">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-188">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-189">16400</span><span class="sxs-lookup"><span data-stu-id="68ec7-189">16400</span></span></p></td>
<td><p><span data-ttu-id="68ec7-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-190">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="68ec7-191">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-191">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-192">16401</span><span class="sxs-lookup"><span data-stu-id="68ec7-192">16401</span></span></p></td>
<td><p><span data-ttu-id="68ec7-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-193">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="68ec7-194">iPadLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-194">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-195">16402</span><span class="sxs-lookup"><span data-stu-id="68ec7-195">16402</span></span></p></td>
<td><p><span data-ttu-id="68ec7-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-196">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="68ec7-197">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="68ec7-197">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-198">16403</span><span class="sxs-lookup"><span data-stu-id="68ec7-198">16403</span></span></p></td>
<td><p><span data-ttu-id="68ec7-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="68ec7-199">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="68ec7-200">LyncImm</span><span class="sxs-lookup"><span data-stu-id="68ec7-200">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-201">16404</span><span class="sxs-lookup"><span data-stu-id="68ec7-201">16404</span></span></p></td>
<td><p><span data-ttu-id="68ec7-202">PCs</span><span class="sxs-lookup"><span data-stu-id="68ec7-202">PCS</span></span></p></td>
<td><p><span data-ttu-id="68ec7-203">PCs</span><span class="sxs-lookup"><span data-stu-id="68ec7-203">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-204">16405</span><span class="sxs-lookup"><span data-stu-id="68ec7-204">16405</span></span></p></td>
<td><p><span data-ttu-id="68ec7-205">LWA</span><span class="sxs-lookup"><span data-stu-id="68ec7-205">LWA</span></span></p></td>
<td><p><span data-ttu-id="68ec7-206">LWA</span><span class="sxs-lookup"><span data-stu-id="68ec7-206">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-207">16406</span><span class="sxs-lookup"><span data-stu-id="68ec7-207">16406</span></span></p></td>
<td><p><span data-ttu-id="68ec7-208">OWA</span><span class="sxs-lookup"><span data-stu-id="68ec7-208">OWA</span></span></p></td>
<td><p><span data-ttu-id="68ec7-209">OWA</span><span class="sxs-lookup"><span data-stu-id="68ec7-209">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-210">16407</span><span class="sxs-lookup"><span data-stu-id="68ec7-210">16407</span></span></p></td>
<td><p><span data-ttu-id="68ec7-211">AOC</span><span class="sxs-lookup"><span data-stu-id="68ec7-211">AOC</span></span></p></td>
<td><p><span data-ttu-id="68ec7-212">AOC</span><span class="sxs-lookup"><span data-stu-id="68ec7-212">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-213">16408</span><span class="sxs-lookup"><span data-stu-id="68ec7-213">16408</span></span></p></td>
<td><p><span data-ttu-id="68ec7-214">GCC</span><span class="sxs-lookup"><span data-stu-id="68ec7-214">GCC</span></span></p></td>
<td><p><span data-ttu-id="68ec7-215">GCC</span><span class="sxs-lookup"><span data-stu-id="68ec7-215">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-216">16409</span><span class="sxs-lookup"><span data-stu-id="68ec7-216">16409</span></span></p></td>
<td><p><span data-ttu-id="68ec7-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="68ec7-217">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="68ec7-218">IMMCU</span><span class="sxs-lookup"><span data-stu-id="68ec7-218">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-219">16410</span><span class="sxs-lookup"><span data-stu-id="68ec7-219">16410</span></span></p></td>
<td><p><span data-ttu-id="68ec7-220">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="68ec7-220">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="68ec7-221">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="68ec7-221">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ec7-222">32769</span><span class="sxs-lookup"><span data-stu-id="68ec7-222">32769</span></span></p></td>
<td><p><span data-ttu-id="68ec7-223">Gateway</span><span class="sxs-lookup"><span data-stu-id="68ec7-223">Gateway</span></span></p></td>
<td><p><span data-ttu-id="68ec7-224">Gateway</span><span class="sxs-lookup"><span data-stu-id="68ec7-224">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ec7-225">32770</span><span class="sxs-lookup"><span data-stu-id="68ec7-225">32770</span></span></p></td>
<td><p><span data-ttu-id="68ec7-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="68ec7-226">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="68ec7-227">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="68ec7-227">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

