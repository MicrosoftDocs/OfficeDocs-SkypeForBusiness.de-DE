---
title: 'Lync Server 2013: UserAgentDef-Tabelle'
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
ms.openlocfilehash: 2ef005350d5ed9a4dee3f108a4cf9e3349389d1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530072"
---
# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="b046c-102">UserAgentDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b046c-102">UserAgentDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b046c-103">_**Letztes Änderungsstand des Themas:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="b046c-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="b046c-104">Die Tabelle "UserAgentDef" ordnet Benutzer-Agent-IDs den aussagekräftigen Namen der Agents zu.</span><span class="sxs-lookup"><span data-stu-id="b046c-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="b046c-105">Benutzer-Agents sind Software Clients, die zum Herstellen einer Verbindung mit Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b046c-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b046c-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b046c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b046c-107">UAType</span><span class="sxs-lookup"><span data-stu-id="b046c-107">UAType</span></span></th>
<th><span data-ttu-id="b046c-108">UAName</span><span class="sxs-lookup"><span data-stu-id="b046c-108">UAName</span></span></th>
<th><span data-ttu-id="b046c-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="b046c-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b046c-110">1</span><span class="sxs-lookup"><span data-stu-id="b046c-110">1</span></span></p></td>
<td><p><span data-ttu-id="b046c-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="b046c-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="b046c-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="b046c-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-113">2</span><span class="sxs-lookup"><span data-stu-id="b046c-113">2</span></span></p></td>
<td><p><span data-ttu-id="b046c-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="b046c-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="b046c-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="b046c-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-116">4 </span><span class="sxs-lookup"><span data-stu-id="b046c-116">4</span></span></p></td>
<td><p><span data-ttu-id="b046c-117">OC</span><span class="sxs-lookup"><span data-stu-id="b046c-117">OC</span></span></p></td>
<td><p><span data-ttu-id="b046c-118">OC</span><span class="sxs-lookup"><span data-stu-id="b046c-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-119">8 </span><span class="sxs-lookup"><span data-stu-id="b046c-119">8</span></span></p></td>
<td><p><span data-ttu-id="b046c-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="b046c-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="b046c-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="b046c-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-122">16 </span><span class="sxs-lookup"><span data-stu-id="b046c-122">16</span></span></p></td>
<td><p><span data-ttu-id="b046c-123">LMC</span><span class="sxs-lookup"><span data-stu-id="b046c-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="b046c-124">LMC</span><span class="sxs-lookup"><span data-stu-id="b046c-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-125">32</span><span class="sxs-lookup"><span data-stu-id="b046c-125">32</span></span></p></td>
<td><p><span data-ttu-id="b046c-126">DVT</span><span class="sxs-lookup"><span data-stu-id="b046c-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="b046c-127">DVT</span><span class="sxs-lookup"><span data-stu-id="b046c-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-128">64</span><span class="sxs-lookup"><span data-stu-id="b046c-128">64</span></span></p></td>
<td><p><span data-ttu-id="b046c-129">MM</span><span class="sxs-lookup"><span data-stu-id="b046c-129">MM</span></span></p></td>
<td><p><span data-ttu-id="b046c-130">MM</span><span class="sxs-lookup"><span data-stu-id="b046c-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-131">64</span><span class="sxs-lookup"><span data-stu-id="b046c-131">64</span></span></p></td>
<td><p><span data-ttu-id="b046c-132">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="b046c-132">MC</span></span></p></td>
<td><p><span data-ttu-id="b046c-133">MM</span><span class="sxs-lookup"><span data-stu-id="b046c-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-134">128</span><span class="sxs-lookup"><span data-stu-id="b046c-134">128</span></span></p></td>
<td><p><span data-ttu-id="b046c-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="b046c-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="b046c-136">Attendant</span><span class="sxs-lookup"><span data-stu-id="b046c-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-137">256</span><span class="sxs-lookup"><span data-stu-id="b046c-137">256</span></span></p></td>
<td><p><span data-ttu-id="b046c-138">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="b046c-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="b046c-139">CAS</span><span class="sxs-lookup"><span data-stu-id="b046c-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-140">512</span><span class="sxs-lookup"><span data-stu-id="b046c-140">512</span></span></p></td>
<td><p><span data-ttu-id="b046c-141">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="b046c-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="b046c-142">CAA</span><span class="sxs-lookup"><span data-stu-id="b046c-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-143">512</span><span class="sxs-lookup"><span data-stu-id="b046c-143">512</span></span></p></td>
<td><p><span data-ttu-id="b046c-144">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="b046c-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="b046c-145">CAA</span><span class="sxs-lookup"><span data-stu-id="b046c-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-146">1024</span><span class="sxs-lookup"><span data-stu-id="b046c-146">1024</span></span></p></td>
<td><p><span data-ttu-id="b046c-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="b046c-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="b046c-148">RGS</span><span class="sxs-lookup"><span data-stu-id="b046c-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-149">1032</span><span class="sxs-lookup"><span data-stu-id="b046c-149">1032</span></span></p></td>
<td><p><span data-ttu-id="b046c-150">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="b046c-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="b046c-151">CPS</span><span class="sxs-lookup"><span data-stu-id="b046c-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-152">1040</span><span class="sxs-lookup"><span data-stu-id="b046c-152">1040</span></span></p></td>
<td><p><span data-ttu-id="b046c-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="b046c-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="b046c-154">AS</span><span class="sxs-lookup"><span data-stu-id="b046c-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-155">2048</span><span class="sxs-lookup"><span data-stu-id="b046c-155">2048</span></span></p></td>
<td><p><span data-ttu-id="b046c-156">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="b046c-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="b046c-157">CCS</span><span class="sxs-lookup"><span data-stu-id="b046c-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-158">16386</span><span class="sxs-lookup"><span data-stu-id="b046c-158">16386</span></span></p></td>
<td><p><span data-ttu-id="b046c-159">Como</span><span class="sxs-lookup"><span data-stu-id="b046c-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="b046c-160">Como</span><span class="sxs-lookup"><span data-stu-id="b046c-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-161">16387</span><span class="sxs-lookup"><span data-stu-id="b046c-161">16387</span></span></p></td>
<td><p><span data-ttu-id="b046c-162">CWA</span><span class="sxs-lookup"><span data-stu-id="b046c-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="b046c-163">CWA</span><span class="sxs-lookup"><span data-stu-id="b046c-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-164">16388</span><span class="sxs-lookup"><span data-stu-id="b046c-164">16388</span></span></p></td>
<td><p><span data-ttu-id="b046c-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="b046c-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="b046c-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="b046c-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-167">16389</span><span class="sxs-lookup"><span data-stu-id="b046c-167">16389</span></span></p></td>
<td><p><span data-ttu-id="b046c-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="b046c-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="b046c-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="b046c-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-170">16393</span><span class="sxs-lookup"><span data-stu-id="b046c-170">16393</span></span></p></td>
<td><p><span data-ttu-id="b046c-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="b046c-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="b046c-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="b046c-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-173">16395</span><span class="sxs-lookup"><span data-stu-id="b046c-173">16395</span></span></p></td>
<td><p><span data-ttu-id="b046c-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="b046c-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="b046c-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="b046c-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-176">16396</span><span class="sxs-lookup"><span data-stu-id="b046c-176">16396</span></span></p></td>
<td><p><span data-ttu-id="b046c-177">St</span><span class="sxs-lookup"><span data-stu-id="b046c-177">ST</span></span></p></td>
<td><p><span data-ttu-id="b046c-178">St</span><span class="sxs-lookup"><span data-stu-id="b046c-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-179">16397</span><span class="sxs-lookup"><span data-stu-id="b046c-179">16397</span></span></p></td>
<td><p><span data-ttu-id="b046c-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="b046c-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="b046c-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="b046c-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-182">16398</span><span class="sxs-lookup"><span data-stu-id="b046c-182">16398</span></span></p></td>
<td><p><span data-ttu-id="b046c-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="b046c-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="b046c-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="b046c-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-185">16399</span><span class="sxs-lookup"><span data-stu-id="b046c-185">16399</span></span></p></td>
<td><p><span data-ttu-id="b046c-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="b046c-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="b046c-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="b046c-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-188">16400</span><span class="sxs-lookup"><span data-stu-id="b046c-188">16400</span></span></p></td>
<td><p><span data-ttu-id="b046c-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="b046c-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="b046c-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="b046c-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-191">16401</span><span class="sxs-lookup"><span data-stu-id="b046c-191">16401</span></span></p></td>
<td><p><span data-ttu-id="b046c-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="b046c-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="b046c-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="b046c-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-194">16402</span><span class="sxs-lookup"><span data-stu-id="b046c-194">16402</span></span></p></td>
<td><p><span data-ttu-id="b046c-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="b046c-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="b046c-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="b046c-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-197">16403</span><span class="sxs-lookup"><span data-stu-id="b046c-197">16403</span></span></p></td>
<td><p><span data-ttu-id="b046c-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="b046c-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="b046c-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="b046c-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-200">16404</span><span class="sxs-lookup"><span data-stu-id="b046c-200">16404</span></span></p></td>
<td><p><span data-ttu-id="b046c-201">PCs</span><span class="sxs-lookup"><span data-stu-id="b046c-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="b046c-202">PCs</span><span class="sxs-lookup"><span data-stu-id="b046c-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-203">16405</span><span class="sxs-lookup"><span data-stu-id="b046c-203">16405</span></span></p></td>
<td><p><span data-ttu-id="b046c-204">LWA</span><span class="sxs-lookup"><span data-stu-id="b046c-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="b046c-205">LWA</span><span class="sxs-lookup"><span data-stu-id="b046c-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-206">16406</span><span class="sxs-lookup"><span data-stu-id="b046c-206">16406</span></span></p></td>
<td><p><span data-ttu-id="b046c-207">OWA</span><span class="sxs-lookup"><span data-stu-id="b046c-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="b046c-208">OWA</span><span class="sxs-lookup"><span data-stu-id="b046c-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-209">16407</span><span class="sxs-lookup"><span data-stu-id="b046c-209">16407</span></span></p></td>
<td><p><span data-ttu-id="b046c-210">AOC</span><span class="sxs-lookup"><span data-stu-id="b046c-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="b046c-211">AOC</span><span class="sxs-lookup"><span data-stu-id="b046c-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-212">16408</span><span class="sxs-lookup"><span data-stu-id="b046c-212">16408</span></span></p></td>
<td><p><span data-ttu-id="b046c-213">GCC</span><span class="sxs-lookup"><span data-stu-id="b046c-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="b046c-214">GCC</span><span class="sxs-lookup"><span data-stu-id="b046c-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-215">16409</span><span class="sxs-lookup"><span data-stu-id="b046c-215">16409</span></span></p></td>
<td><p><span data-ttu-id="b046c-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="b046c-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="b046c-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="b046c-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-218">16410</span><span class="sxs-lookup"><span data-stu-id="b046c-218">16410</span></span></p></td>
<td><p><span data-ttu-id="b046c-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="b046c-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="b046c-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="b046c-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b046c-221">32769</span><span class="sxs-lookup"><span data-stu-id="b046c-221">32769</span></span></p></td>
<td><p><span data-ttu-id="b046c-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="b046c-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="b046c-223">Gateway</span><span class="sxs-lookup"><span data-stu-id="b046c-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b046c-224">32770</span><span class="sxs-lookup"><span data-stu-id="b046c-224">32770</span></span></p></td>
<td><p><span data-ttu-id="b046c-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="b046c-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="b046c-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="b046c-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

