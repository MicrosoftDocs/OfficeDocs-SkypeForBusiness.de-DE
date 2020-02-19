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
ms.openlocfilehash: b7f63c9e5194c2b75ea6f637acec7201c86178e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="550c4-102">UserAgentDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="550c4-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="550c4-103">_**Letztes Änderungsstand des Themas:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="550c4-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="550c4-104">Die Tabelle "UserAgentDef" ordnet Benutzer-Agent-IDs den aussagekräftigen Namen der Agents zu.</span><span class="sxs-lookup"><span data-stu-id="550c4-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="550c4-105">Benutzer-Agents sind Software Clients, die zum Herstellen einer Verbindung mit Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="550c4-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="550c4-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="550c4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="550c4-107">UAType</span><span class="sxs-lookup"><span data-stu-id="550c4-107">UAType</span></span></th>
<th><span data-ttu-id="550c4-108">UAName</span><span class="sxs-lookup"><span data-stu-id="550c4-108">UAName</span></span></th>
<th><span data-ttu-id="550c4-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="550c4-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="550c4-110">1</span><span class="sxs-lookup"><span data-stu-id="550c4-110">1</span></span></p></td>
<td><p><span data-ttu-id="550c4-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="550c4-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="550c4-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="550c4-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-113">2</span><span class="sxs-lookup"><span data-stu-id="550c4-113">2</span></span></p></td>
<td><p><span data-ttu-id="550c4-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="550c4-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="550c4-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="550c4-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-116">4</span><span class="sxs-lookup"><span data-stu-id="550c4-116">4</span></span></p></td>
<td><p><span data-ttu-id="550c4-117">OC</span><span class="sxs-lookup"><span data-stu-id="550c4-117">OC</span></span></p></td>
<td><p><span data-ttu-id="550c4-118">OC</span><span class="sxs-lookup"><span data-stu-id="550c4-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-119">8 </span><span class="sxs-lookup"><span data-stu-id="550c4-119">8</span></span></p></td>
<td><p><span data-ttu-id="550c4-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="550c4-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="550c4-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="550c4-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-122">16 </span><span class="sxs-lookup"><span data-stu-id="550c4-122">16</span></span></p></td>
<td><p><span data-ttu-id="550c4-123">LMC</span><span class="sxs-lookup"><span data-stu-id="550c4-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="550c4-124">LMC</span><span class="sxs-lookup"><span data-stu-id="550c4-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-125">32</span><span class="sxs-lookup"><span data-stu-id="550c4-125">32</span></span></p></td>
<td><p><span data-ttu-id="550c4-126">DVT</span><span class="sxs-lookup"><span data-stu-id="550c4-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="550c4-127">DVT</span><span class="sxs-lookup"><span data-stu-id="550c4-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-128">64</span><span class="sxs-lookup"><span data-stu-id="550c4-128">64</span></span></p></td>
<td><p><span data-ttu-id="550c4-129">MM</span><span class="sxs-lookup"><span data-stu-id="550c4-129">MM</span></span></p></td>
<td><p><span data-ttu-id="550c4-130">MM</span><span class="sxs-lookup"><span data-stu-id="550c4-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-131">64</span><span class="sxs-lookup"><span data-stu-id="550c4-131">64</span></span></p></td>
<td><p><span data-ttu-id="550c4-132">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="550c4-132">MC</span></span></p></td>
<td><p><span data-ttu-id="550c4-133">MM</span><span class="sxs-lookup"><span data-stu-id="550c4-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-134">128</span><span class="sxs-lookup"><span data-stu-id="550c4-134">128</span></span></p></td>
<td><p><span data-ttu-id="550c4-135">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="550c4-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="550c4-136">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="550c4-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-137">256</span><span class="sxs-lookup"><span data-stu-id="550c4-137">256</span></span></p></td>
<td><p><span data-ttu-id="550c4-138">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="550c4-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="550c4-139">CAS</span><span class="sxs-lookup"><span data-stu-id="550c4-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-140">512</span><span class="sxs-lookup"><span data-stu-id="550c4-140">512</span></span></p></td>
<td><p><span data-ttu-id="550c4-141">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="550c4-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="550c4-142">CAA</span><span class="sxs-lookup"><span data-stu-id="550c4-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-143">512</span><span class="sxs-lookup"><span data-stu-id="550c4-143">512</span></span></p></td>
<td><p><span data-ttu-id="550c4-144">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="550c4-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="550c4-145">CAA</span><span class="sxs-lookup"><span data-stu-id="550c4-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-146">1024</span><span class="sxs-lookup"><span data-stu-id="550c4-146">1024</span></span></p></td>
<td><p><span data-ttu-id="550c4-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="550c4-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="550c4-148">RGS</span><span class="sxs-lookup"><span data-stu-id="550c4-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-149">1032</span><span class="sxs-lookup"><span data-stu-id="550c4-149">1032</span></span></p></td>
<td><p><span data-ttu-id="550c4-150">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="550c4-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="550c4-151">CPS</span><span class="sxs-lookup"><span data-stu-id="550c4-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-152">1040</span><span class="sxs-lookup"><span data-stu-id="550c4-152">1040</span></span></p></td>
<td><p><span data-ttu-id="550c4-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="550c4-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="550c4-154">AS</span><span class="sxs-lookup"><span data-stu-id="550c4-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-155">2048</span><span class="sxs-lookup"><span data-stu-id="550c4-155">2048</span></span></p></td>
<td><p><span data-ttu-id="550c4-156">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="550c4-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="550c4-157">CCS</span><span class="sxs-lookup"><span data-stu-id="550c4-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-158">16386</span><span class="sxs-lookup"><span data-stu-id="550c4-158">16386</span></span></p></td>
<td><p><span data-ttu-id="550c4-159">Como</span><span class="sxs-lookup"><span data-stu-id="550c4-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="550c4-160">Como</span><span class="sxs-lookup"><span data-stu-id="550c4-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-161">16387</span><span class="sxs-lookup"><span data-stu-id="550c4-161">16387</span></span></p></td>
<td><p><span data-ttu-id="550c4-162">CWA</span><span class="sxs-lookup"><span data-stu-id="550c4-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="550c4-163">CWA</span><span class="sxs-lookup"><span data-stu-id="550c4-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-164">16388</span><span class="sxs-lookup"><span data-stu-id="550c4-164">16388</span></span></p></td>
<td><p><span data-ttu-id="550c4-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="550c4-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="550c4-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="550c4-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-167">16389</span><span class="sxs-lookup"><span data-stu-id="550c4-167">16389</span></span></p></td>
<td><p><span data-ttu-id="550c4-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="550c4-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="550c4-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="550c4-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-170">16393</span><span class="sxs-lookup"><span data-stu-id="550c4-170">16393</span></span></p></td>
<td><p><span data-ttu-id="550c4-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="550c4-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="550c4-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="550c4-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-173">16395</span><span class="sxs-lookup"><span data-stu-id="550c4-173">16395</span></span></p></td>
<td><p><span data-ttu-id="550c4-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="550c4-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="550c4-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="550c4-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-176">16396</span><span class="sxs-lookup"><span data-stu-id="550c4-176">16396</span></span></p></td>
<td><p><span data-ttu-id="550c4-177">St</span><span class="sxs-lookup"><span data-stu-id="550c4-177">ST</span></span></p></td>
<td><p><span data-ttu-id="550c4-178">St</span><span class="sxs-lookup"><span data-stu-id="550c4-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-179">16397</span><span class="sxs-lookup"><span data-stu-id="550c4-179">16397</span></span></p></td>
<td><p><span data-ttu-id="550c4-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="550c4-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="550c4-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="550c4-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-182">16398</span><span class="sxs-lookup"><span data-stu-id="550c4-182">16398</span></span></p></td>
<td><p><span data-ttu-id="550c4-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="550c4-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="550c4-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="550c4-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-185">16399</span><span class="sxs-lookup"><span data-stu-id="550c4-185">16399</span></span></p></td>
<td><p><span data-ttu-id="550c4-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="550c4-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="550c4-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="550c4-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-188">16400</span><span class="sxs-lookup"><span data-stu-id="550c4-188">16400</span></span></p></td>
<td><p><span data-ttu-id="550c4-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="550c4-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="550c4-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="550c4-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-191">16401</span><span class="sxs-lookup"><span data-stu-id="550c4-191">16401</span></span></p></td>
<td><p><span data-ttu-id="550c4-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="550c4-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="550c4-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="550c4-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-194">16402</span><span class="sxs-lookup"><span data-stu-id="550c4-194">16402</span></span></p></td>
<td><p><span data-ttu-id="550c4-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="550c4-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="550c4-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="550c4-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-197">16403</span><span class="sxs-lookup"><span data-stu-id="550c4-197">16403</span></span></p></td>
<td><p><span data-ttu-id="550c4-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="550c4-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="550c4-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="550c4-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-200">16404</span><span class="sxs-lookup"><span data-stu-id="550c4-200">16404</span></span></p></td>
<td><p><span data-ttu-id="550c4-201">PCs</span><span class="sxs-lookup"><span data-stu-id="550c4-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="550c4-202">PCs</span><span class="sxs-lookup"><span data-stu-id="550c4-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-203">16405</span><span class="sxs-lookup"><span data-stu-id="550c4-203">16405</span></span></p></td>
<td><p><span data-ttu-id="550c4-204">LWA</span><span class="sxs-lookup"><span data-stu-id="550c4-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="550c4-205">LWA</span><span class="sxs-lookup"><span data-stu-id="550c4-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-206">16406</span><span class="sxs-lookup"><span data-stu-id="550c4-206">16406</span></span></p></td>
<td><p><span data-ttu-id="550c4-207">OWA</span><span class="sxs-lookup"><span data-stu-id="550c4-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="550c4-208">OWA</span><span class="sxs-lookup"><span data-stu-id="550c4-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-209">16407</span><span class="sxs-lookup"><span data-stu-id="550c4-209">16407</span></span></p></td>
<td><p><span data-ttu-id="550c4-210">AOC</span><span class="sxs-lookup"><span data-stu-id="550c4-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="550c4-211">AOC</span><span class="sxs-lookup"><span data-stu-id="550c4-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-212">16408</span><span class="sxs-lookup"><span data-stu-id="550c4-212">16408</span></span></p></td>
<td><p><span data-ttu-id="550c4-213">GCC</span><span class="sxs-lookup"><span data-stu-id="550c4-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="550c4-214">GCC</span><span class="sxs-lookup"><span data-stu-id="550c4-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-215">16409</span><span class="sxs-lookup"><span data-stu-id="550c4-215">16409</span></span></p></td>
<td><p><span data-ttu-id="550c4-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="550c4-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="550c4-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="550c4-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-218">16410</span><span class="sxs-lookup"><span data-stu-id="550c4-218">16410</span></span></p></td>
<td><p><span data-ttu-id="550c4-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="550c4-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="550c4-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="550c4-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="550c4-221">32769</span><span class="sxs-lookup"><span data-stu-id="550c4-221">32769</span></span></p></td>
<td><p><span data-ttu-id="550c4-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="550c4-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="550c4-223">Gateway</span><span class="sxs-lookup"><span data-stu-id="550c4-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="550c4-224">32770</span><span class="sxs-lookup"><span data-stu-id="550c4-224">32770</span></span></p></td>
<td><p><span data-ttu-id="550c4-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="550c4-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="550c4-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="550c4-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

