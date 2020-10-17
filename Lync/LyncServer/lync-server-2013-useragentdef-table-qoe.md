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
ms.openlocfilehash: 7294c70a0ebfd49f954bbe911d2fccb81d79fa54
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530102"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="d8201-102">UserAgentDef-Tabelle (QoE) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8201-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8201-103">_**Letztes Änderungsstand des Themas:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="d8201-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="d8201-104">Die Tabelle "UserAgentDef" ordnet Benutzer-Agent-IDs den aussagekräftigen Namen der Agents zu.</span><span class="sxs-lookup"><span data-stu-id="d8201-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="d8201-105">Benutzer-Agents sind Software Clients, die zum Herstellen einer Verbindung mit Microsoft lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8201-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8201-106">UAType</span><span class="sxs-lookup"><span data-stu-id="d8201-106">UAType</span></span></th>
<th><span data-ttu-id="d8201-107">UAName</span><span class="sxs-lookup"><span data-stu-id="d8201-107">UAName</span></span></th>
<th><span data-ttu-id="d8201-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="d8201-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8201-109">1</span><span class="sxs-lookup"><span data-stu-id="d8201-109">1</span></span></p></td>
<td><p><span data-ttu-id="d8201-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="d8201-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="d8201-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="d8201-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-112">2</span><span class="sxs-lookup"><span data-stu-id="d8201-112">2</span></span></p></td>
<td><p><span data-ttu-id="d8201-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="d8201-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="d8201-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="d8201-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-115">4 </span><span class="sxs-lookup"><span data-stu-id="d8201-115">4</span></span></p></td>
<td><p><span data-ttu-id="d8201-116">OC</span><span class="sxs-lookup"><span data-stu-id="d8201-116">OC</span></span></p></td>
<td><p><span data-ttu-id="d8201-117">OC</span><span class="sxs-lookup"><span data-stu-id="d8201-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-118">8 </span><span class="sxs-lookup"><span data-stu-id="d8201-118">8</span></span></p></td>
<td><p><span data-ttu-id="d8201-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="d8201-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="d8201-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="d8201-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-121">16 </span><span class="sxs-lookup"><span data-stu-id="d8201-121">16</span></span></p></td>
<td><p><span data-ttu-id="d8201-122">LMC</span><span class="sxs-lookup"><span data-stu-id="d8201-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="d8201-123">LMC</span><span class="sxs-lookup"><span data-stu-id="d8201-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-124">32</span><span class="sxs-lookup"><span data-stu-id="d8201-124">32</span></span></p></td>
<td><p><span data-ttu-id="d8201-125">DVT</span><span class="sxs-lookup"><span data-stu-id="d8201-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="d8201-126">DVT</span><span class="sxs-lookup"><span data-stu-id="d8201-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-127">64</span><span class="sxs-lookup"><span data-stu-id="d8201-127">64</span></span></p></td>
<td><p><span data-ttu-id="d8201-128">MM</span><span class="sxs-lookup"><span data-stu-id="d8201-128">MM</span></span></p></td>
<td><p><span data-ttu-id="d8201-129">MM</span><span class="sxs-lookup"><span data-stu-id="d8201-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-130">64</span><span class="sxs-lookup"><span data-stu-id="d8201-130">64</span></span></p></td>
<td><p><span data-ttu-id="d8201-131">Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="d8201-131">MC</span></span></p></td>
<td><p><span data-ttu-id="d8201-132">MM</span><span class="sxs-lookup"><span data-stu-id="d8201-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-133">128</span><span class="sxs-lookup"><span data-stu-id="d8201-133">128</span></span></p></td>
<td><p><span data-ttu-id="d8201-134">Attendant</span><span class="sxs-lookup"><span data-stu-id="d8201-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="d8201-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="d8201-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-136">256</span><span class="sxs-lookup"><span data-stu-id="d8201-136">256</span></span></p></td>
<td><p><span data-ttu-id="d8201-137">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="d8201-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="d8201-138">CAS</span><span class="sxs-lookup"><span data-stu-id="d8201-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-139">512</span><span class="sxs-lookup"><span data-stu-id="d8201-139">512</span></span></p></td>
<td><p><span data-ttu-id="d8201-140">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="d8201-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="d8201-141">CAA</span><span class="sxs-lookup"><span data-stu-id="d8201-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-142">512</span><span class="sxs-lookup"><span data-stu-id="d8201-142">512</span></span></p></td>
<td><p><span data-ttu-id="d8201-143">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="d8201-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="d8201-144">CAA</span><span class="sxs-lookup"><span data-stu-id="d8201-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-145">1024</span><span class="sxs-lookup"><span data-stu-id="d8201-145">1024</span></span></p></td>
<td><p><span data-ttu-id="d8201-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="d8201-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="d8201-147">RGS</span><span class="sxs-lookup"><span data-stu-id="d8201-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-148">1032</span><span class="sxs-lookup"><span data-stu-id="d8201-148">1032</span></span></p></td>
<td><p><span data-ttu-id="d8201-149">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="d8201-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="d8201-150">CPS</span><span class="sxs-lookup"><span data-stu-id="d8201-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-151">1040</span><span class="sxs-lookup"><span data-stu-id="d8201-151">1040</span></span></p></td>
<td><p><span data-ttu-id="d8201-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="d8201-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="d8201-153">AS</span><span class="sxs-lookup"><span data-stu-id="d8201-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-154">2048</span><span class="sxs-lookup"><span data-stu-id="d8201-154">2048</span></span></p></td>
<td><p><span data-ttu-id="d8201-155">Microsoft. RTC. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="d8201-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="d8201-156">CCS</span><span class="sxs-lookup"><span data-stu-id="d8201-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-157">16386</span><span class="sxs-lookup"><span data-stu-id="d8201-157">16386</span></span></p></td>
<td><p><span data-ttu-id="d8201-158">Como</span><span class="sxs-lookup"><span data-stu-id="d8201-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="d8201-159">Como</span><span class="sxs-lookup"><span data-stu-id="d8201-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-160">16387</span><span class="sxs-lookup"><span data-stu-id="d8201-160">16387</span></span></p></td>
<td><p><span data-ttu-id="d8201-161">CWA</span><span class="sxs-lookup"><span data-stu-id="d8201-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="d8201-162">CWA</span><span class="sxs-lookup"><span data-stu-id="d8201-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-163">16388</span><span class="sxs-lookup"><span data-stu-id="d8201-163">16388</span></span></p></td>
<td><p><span data-ttu-id="d8201-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="d8201-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="d8201-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="d8201-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-166">16389</span><span class="sxs-lookup"><span data-stu-id="d8201-166">16389</span></span></p></td>
<td><p><span data-ttu-id="d8201-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="d8201-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="d8201-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="d8201-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-169">16393</span><span class="sxs-lookup"><span data-stu-id="d8201-169">16393</span></span></p></td>
<td><p><span data-ttu-id="d8201-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="d8201-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="d8201-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="d8201-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-172">16395</span><span class="sxs-lookup"><span data-stu-id="d8201-172">16395</span></span></p></td>
<td><p><span data-ttu-id="d8201-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="d8201-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="d8201-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="d8201-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-175">16396</span><span class="sxs-lookup"><span data-stu-id="d8201-175">16396</span></span></p></td>
<td><p><span data-ttu-id="d8201-176">St</span><span class="sxs-lookup"><span data-stu-id="d8201-176">ST</span></span></p></td>
<td><p><span data-ttu-id="d8201-177">St</span><span class="sxs-lookup"><span data-stu-id="d8201-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-178">16397</span><span class="sxs-lookup"><span data-stu-id="d8201-178">16397</span></span></p></td>
<td><p><span data-ttu-id="d8201-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="d8201-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="d8201-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="d8201-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-181">16398</span><span class="sxs-lookup"><span data-stu-id="d8201-181">16398</span></span></p></td>
<td><p><span data-ttu-id="d8201-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="d8201-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="d8201-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="d8201-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-184">16399</span><span class="sxs-lookup"><span data-stu-id="d8201-184">16399</span></span></p></td>
<td><p><span data-ttu-id="d8201-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="d8201-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="d8201-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="d8201-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-187">16400</span><span class="sxs-lookup"><span data-stu-id="d8201-187">16400</span></span></p></td>
<td><p><span data-ttu-id="d8201-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="d8201-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="d8201-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="d8201-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-190">16401</span><span class="sxs-lookup"><span data-stu-id="d8201-190">16401</span></span></p></td>
<td><p><span data-ttu-id="d8201-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="d8201-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="d8201-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="d8201-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-193">16402</span><span class="sxs-lookup"><span data-stu-id="d8201-193">16402</span></span></p></td>
<td><p><span data-ttu-id="d8201-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="d8201-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="d8201-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="d8201-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-196">16403</span><span class="sxs-lookup"><span data-stu-id="d8201-196">16403</span></span></p></td>
<td><p><span data-ttu-id="d8201-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="d8201-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="d8201-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="d8201-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-199">16404</span><span class="sxs-lookup"><span data-stu-id="d8201-199">16404</span></span></p></td>
<td><p><span data-ttu-id="d8201-200">PCs</span><span class="sxs-lookup"><span data-stu-id="d8201-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="d8201-201">PCs</span><span class="sxs-lookup"><span data-stu-id="d8201-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-202">16405</span><span class="sxs-lookup"><span data-stu-id="d8201-202">16405</span></span></p></td>
<td><p><span data-ttu-id="d8201-203">LWA</span><span class="sxs-lookup"><span data-stu-id="d8201-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="d8201-204">LWA</span><span class="sxs-lookup"><span data-stu-id="d8201-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-205">16406</span><span class="sxs-lookup"><span data-stu-id="d8201-205">16406</span></span></p></td>
<td><p><span data-ttu-id="d8201-206">OWA</span><span class="sxs-lookup"><span data-stu-id="d8201-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="d8201-207">OWA</span><span class="sxs-lookup"><span data-stu-id="d8201-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-208">16407</span><span class="sxs-lookup"><span data-stu-id="d8201-208">16407</span></span></p></td>
<td><p><span data-ttu-id="d8201-209">AOC</span><span class="sxs-lookup"><span data-stu-id="d8201-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="d8201-210">AOC</span><span class="sxs-lookup"><span data-stu-id="d8201-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-211">16408</span><span class="sxs-lookup"><span data-stu-id="d8201-211">16408</span></span></p></td>
<td><p><span data-ttu-id="d8201-212">GCC</span><span class="sxs-lookup"><span data-stu-id="d8201-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="d8201-213">GCC</span><span class="sxs-lookup"><span data-stu-id="d8201-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-214">16409</span><span class="sxs-lookup"><span data-stu-id="d8201-214">16409</span></span></p></td>
<td><p><span data-ttu-id="d8201-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="d8201-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="d8201-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="d8201-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-217">16410</span><span class="sxs-lookup"><span data-stu-id="d8201-217">16410</span></span></p></td>
<td><p><span data-ttu-id="d8201-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="d8201-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="d8201-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="d8201-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8201-220">32769</span><span class="sxs-lookup"><span data-stu-id="d8201-220">32769</span></span></p></td>
<td><p><span data-ttu-id="d8201-221">Gateway</span><span class="sxs-lookup"><span data-stu-id="d8201-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="d8201-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="d8201-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8201-223">32770</span><span class="sxs-lookup"><span data-stu-id="d8201-223">32770</span></span></p></td>
<td><p><span data-ttu-id="d8201-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="d8201-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="d8201-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="d8201-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

