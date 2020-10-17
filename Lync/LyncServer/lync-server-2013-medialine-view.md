---
title: 'Lync Server 2013: medialinie-Ansicht'
description: 'Lync Server 2013: medialinie-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568681"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="159c4-103">Medienansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="159c4-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="159c4-104">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="159c4-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="159c4-105">Die MediaLine-Ansicht speichert Informationen zu jeder Medienzeile in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="159c4-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="159c4-106">Eine Audiositzung enthält in der Regel eine Audiomedienzeile.</span><span class="sxs-lookup"><span data-stu-id="159c4-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="159c4-107">Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="159c4-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="159c4-108">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="159c4-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="159c4-109">Spalte</span><span class="sxs-lookup"><span data-stu-id="159c4-109">Column</span></span></th>
<th><span data-ttu-id="159c4-110">Datentyp</span><span class="sxs-lookup"><span data-stu-id="159c4-110">Data Type</span></span></th>
<th><span data-ttu-id="159c4-111">Details</span><span class="sxs-lookup"><span data-stu-id="159c4-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="159c4-112">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="159c4-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="159c4-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="159c4-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="159c4-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="159c4-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="159c4-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="159c4-116">int</span><span class="sxs-lookup"><span data-stu-id="159c4-116">int</span></span></p></td>
<td><p><span data-ttu-id="159c4-117"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="159c4-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="159c4-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="159c4-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="159c4-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="159c4-120"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="159c4-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="159c4-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="159c4-122">int</span><span class="sxs-lookup"><span data-stu-id="159c4-122">int</span></span></p></td>
<td><p><span data-ttu-id="159c4-p102">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="159c4-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="159c4-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="159c4-126">int</span><span class="sxs-lookup"><span data-stu-id="159c4-126">int</span></span></p></td>
<td><p><span data-ttu-id="159c4-p103">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE), in Bitflags für den Angerufenen beschrieben. Ausführliche Informationen finden Sie im Artikel "Quality of Experience Monitoring Server Protocol Specification".</span><span class="sxs-lookup"><span data-stu-id="159c4-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="159c4-129">Security</span></span></p></td>
<td><p><span data-ttu-id="159c4-130">tinyint</span><span class="sxs-lookup"><span data-stu-id="159c4-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="159c4-p104">Verwendetes Sicherheitsprofil. 0 ist KEINES, 1 ist SRTP, 2 ist V1.</span><span class="sxs-lookup"><span data-stu-id="159c4-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-133">Transport</span><span class="sxs-lookup"><span data-stu-id="159c4-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="159c4-134">tinyint</span><span class="sxs-lookup"><span data-stu-id="159c4-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="159c4-p105">Transporttyp. 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="159c4-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="159c4-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="159c4-138">var (50)</span><span class="sxs-lookup"><span data-stu-id="159c4-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="159c4-p106">IP-Adresse des Anrufers. Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.</span><span class="sxs-lookup"><span data-stu-id="159c4-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="159c4-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="159c4-142">int</span><span class="sxs-lookup"><span data-stu-id="159c4-142">int</span></span></p></td>
<td><p><span data-ttu-id="159c4-143">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="159c4-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="159c4-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="159c4-145">Bit</span><span class="sxs-lookup"><span data-stu-id="159c4-145">bit</span></span></p></td>
<td><p><span data-ttu-id="159c4-p107">Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich innerhalb des Unternehmensnetzwerks. 0 bedeutet, der Anrufer befindet sich außerhalb des Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="159c4-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-149">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="159c4-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="159c4-150">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-151">MAC-Adresse der von Anrufer verwendeten Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="159c4-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="159c4-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="159c4-153">var (50)</span><span class="sxs-lookup"><span data-stu-id="159c4-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="159c4-154">IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="159c4-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="159c4-155">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="159c4-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="159c4-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="159c4-157">int</span><span class="sxs-lookup"><span data-stu-id="159c4-157">int</span></span></p></td>
<td><p><span data-ttu-id="159c4-158">Der vom Anrufer auf dem A/V-Edgedienst verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="159c4-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="159c4-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="159c4-160">var (50)</span><span class="sxs-lookup"><span data-stu-id="159c4-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="159c4-161">IP-Adresse des Anrufers, wie vom A/V-Edgedienst berichtet.</span><span class="sxs-lookup"><span data-stu-id="159c4-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="159c4-162">Diese Adresse kann sich von "CallerIPAddr" unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.</span><span class="sxs-lookup"><span data-stu-id="159c4-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="159c4-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="159c4-164">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-165">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="159c4-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="159c4-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="159c4-167">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-168">Name des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="159c4-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="159c4-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="159c4-170">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-171">Name des Gerätetreibers des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="159c4-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="159c4-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="159c4-173">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-174">Name des Treibers des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="159c4-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="159c4-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="159c4-176">varchar (256</span><span class="sxs-lookup"><span data-stu-id="159c4-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="159c4-177">Beschreibung des WLAN-Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="159c4-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="159c4-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="159c4-179">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-180">WLAN-Treiberversion des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="159c4-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="159c4-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="159c4-182">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-183">Details der Netzwerkverbindung des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="159c4-183">Details of caller’s network connection.</span></span> <span data-ttu-id="159c4-184">Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="159c4-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="159c4-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="159c4-186">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-187">Von der WLAN-Verbindung des Anrufers verwendete BSSID (Basic Service Set Identifier).</span><span class="sxs-lookup"><span data-stu-id="159c4-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="159c4-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="159c4-189">Bit</span><span class="sxs-lookup"><span data-stu-id="159c4-189">bit</span></span></p></td>
<td><p><span data-ttu-id="159c4-p111">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="159c4-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="159c4-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="159c4-193">var (50)</span><span class="sxs-lookup"><span data-stu-id="159c4-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="159c4-194">IP-Adresse des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="159c4-194">IP address of the callee.</span></span> <span data-ttu-id="159c4-195">Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.</span><span class="sxs-lookup"><span data-stu-id="159c4-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="159c4-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="159c4-197">int</span><span class="sxs-lookup"><span data-stu-id="159c4-197">int</span></span></p></td>
<td><p><span data-ttu-id="159c4-198">Vom Angerufenen verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="159c4-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="159c4-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="159c4-200">Bit</span><span class="sxs-lookup"><span data-stu-id="159c4-200">bit</span></span></p></td>
<td><p><span data-ttu-id="159c4-p113">Gibt an, ob sich der Angerufene innerhalb des Unternehmensnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb des Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="159c4-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="159c4-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="159c4-204">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-205">MAC-Adresse der von Angerufenen verwendeten Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="159c4-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="159c4-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="159c4-207">var (50)</span><span class="sxs-lookup"><span data-stu-id="159c4-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="159c4-208">IP-Adresse des vom Angerufenen verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="159c4-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="159c4-209">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="159c4-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="159c4-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="159c4-211">int</span><span class="sxs-lookup"><span data-stu-id="159c4-211">int</span></span></p></td>
<td><p><span data-ttu-id="159c4-212">Der vom Angerufenen auf dem A/V-Edgedienst verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="159c4-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-213">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="159c4-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="159c4-214">var (50)</span><span class="sxs-lookup"><span data-stu-id="159c4-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="159c4-215">IP-Adresse des Angerufenen, wie vom A/V-Edgedienst berichtet.</span><span class="sxs-lookup"><span data-stu-id="159c4-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="159c4-216">Diese Adresse kann sich von "CalleeIPAddr" unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.</span><span class="sxs-lookup"><span data-stu-id="159c4-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-217">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="159c4-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="159c4-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="159c4-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="159c4-219">Name des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="159c4-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="159c4-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="159c4-221">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-222">Name des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="159c4-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-223">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="159c4-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="159c4-224">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-225">Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="159c4-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="159c4-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="159c4-227">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-228">Name des Treibers des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="159c4-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="159c4-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="159c4-230">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-231">Beschreibung des WLAN-Treibers des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="159c4-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="159c4-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="159c4-233">varchar (256</span><span class="sxs-lookup"><span data-stu-id="159c4-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="159c4-234">WLAN-Treiberversion des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="159c4-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="159c4-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="159c4-236">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-237">Details der Netzwerkverbindung des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="159c4-237">Details of callee’s network connection.</span></span> <span data-ttu-id="159c4-238">Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="159c4-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="159c4-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="159c4-240">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-241">Von der WLAN-Verbindung des Angerufenen verwendete BSSID (Basic Service Set Identifier).</span><span class="sxs-lookup"><span data-stu-id="159c4-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="159c4-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="159c4-243">Bit</span><span class="sxs-lookup"><span data-stu-id="159c4-243">bit</span></span></p></td>
<td><p><span data-ttu-id="159c4-p117">Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="159c4-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="159c4-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="159c4-247">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="159c4-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="159c4-248">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="159c4-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="159c4-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="159c4-250">int</span><span class="sxs-lookup"><span data-stu-id="159c4-250">int</span></span></p></td>
<td><p><span data-ttu-id="159c4-p118">Hierbei handelt es sich um die genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</span><span class="sxs-lookup"><span data-stu-id="159c4-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="159c4-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="159c4-255">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="159c4-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="159c4-p119">Quelle der vorgegebenen Bandbreitenbeschränkung. Sie beschreibt den Ursprung der Bandbreitenbeschränkung (z. B."Policy Server", "TURN Server" oder "Modality").</span><span class="sxs-lookup"><span data-stu-id="159c4-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-258">Anrufer</span><span class="sxs-lookup"><span data-stu-id="159c4-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="159c4-259">Bit</span><span class="sxs-lookup"><span data-stu-id="159c4-259">bit</span></span></p></td>
<td><p><span data-ttu-id="159c4-260">Gibt an, ob die Metriken des Anrufers empfangen wurden; 1 ist ja, 0 ist nein.</span><span class="sxs-lookup"><span data-stu-id="159c4-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-261">Aufgerufene</span><span class="sxs-lookup"><span data-stu-id="159c4-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="159c4-262">Bit</span><span class="sxs-lookup"><span data-stu-id="159c4-262">bit</span></span></p></td>
<td><p><span data-ttu-id="159c4-263">Gibt an, ob die Metriken des Angerufenen empfangen wurden; 1 ist ja, 0 ist nein.</span><span class="sxs-lookup"><span data-stu-id="159c4-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="159c4-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="159c4-265">Bit</span><span class="sxs-lookup"><span data-stu-id="159c4-265">bit</span></span></p></td>
<td><p><span data-ttu-id="159c4-266">Gibt an, ob es sich um einen Bericht zu einem Teil des Anrufs oder zum gesamten Anruf handelt.</span><span class="sxs-lookup"><span data-stu-id="159c4-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="159c4-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="159c4-268">Bit</span><span class="sxs-lookup"><span data-stu-id="159c4-268">bit</span></span></p></td>
<td><p><span data-ttu-id="159c4-269">Gibt an, ob der Anruf als Anruf schlechter Qualität (1) oder als Anruf guter Qualität (0) klassifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="159c4-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="159c4-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="159c4-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="159c4-271">tinyint</span><span class="sxs-lookup"><span data-stu-id="159c4-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="159c4-272">Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="159c4-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="159c4-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="159c4-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="159c4-274">tinyint</span><span class="sxs-lookup"><span data-stu-id="159c4-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="159c4-275">Gibt an, ob sich der angerufene Benutzer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="159c4-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

