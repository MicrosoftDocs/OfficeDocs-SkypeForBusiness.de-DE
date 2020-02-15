---
title: 'Lync Server 2013: medialinie-Ansicht'
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
ms.openlocfilehash: 5c6e5fd3c1afe27bc1baa8790527ee239bdba990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="d7a4c-102">Medienansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7a4c-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7a4c-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d7a4c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d7a4c-104">Die MediaLine-Ansicht speichert Informationen zu jeder Medienzeile in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="d7a4c-105">Eine Audiositzung enthält in der Regel eine Audiomedienzeile.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="d7a4c-106">Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="d7a4c-107">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a4c-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="d7a4c-108">Column</span></span></th>
<th><span data-ttu-id="d7a4c-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d7a4c-109">Data Type</span></span></th>
<th><span data-ttu-id="d7a4c-110">Details</span><span class="sxs-lookup"><span data-stu-id="d7a4c-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="d7a4c-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="d7a4c-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-115">int</span><span class="sxs-lookup"><span data-stu-id="d7a4c-115">int</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-116"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="d7a4c-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7a4c-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-119"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d7a4c-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-121">int</span><span class="sxs-lookup"><span data-stu-id="d7a4c-121">int</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p102">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d7a4c-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-125">int</span><span class="sxs-lookup"><span data-stu-id="d7a4c-125">int</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p103">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE), in Bitflags für den Angerufenen beschrieben. Ausführliche Informationen finden Sie im Artikel "Quality of Experience Monitoring Server Protocol Specification".</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-128">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-128">Security</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7a4c-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p104">Verwendetes Sicherheitsprofil. 0 ist KEINES, 1 ist SRTP, 2 ist V1.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-132">Transport</span><span class="sxs-lookup"><span data-stu-id="d7a4c-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7a4c-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p105">Transporttyp. 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7a4c-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p106">IP-Adresse des Anrufers. Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="d7a4c-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-141">int</span><span class="sxs-lookup"><span data-stu-id="d7a4c-141">int</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-142">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="d7a4c-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-144">Bit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-144">bit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p107">Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich innerhalb des Unternehmensnetzwerks. 0 bedeutet, der Anrufer befindet sich außerhalb des Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="d7a4c-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-150">MAC-Adresse der von Anrufer verwendeten Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7a4c-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-153">IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="d7a4c-154">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7a4c-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d7a4c-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-156">int</span><span class="sxs-lookup"><span data-stu-id="d7a4c-156">int</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-157">Der vom Anrufer auf dem A/V-Edgedienst verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7a4c-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-160">IP-Adresse des Anrufers, wie vom A/V-Edgedienst berichtet.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="d7a4c-161">Diese Adresse kann sich von "CallerIPAddr" unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d7a4c-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-164">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="d7a4c-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-167">Name des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7a4c-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-170">Name des Gerätetreibers des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7a4c-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-173">Name des Treibers des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="d7a4c-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="d7a4c-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-176">Beschreibung des WLAN-Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="d7a4c-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-179">WLAN-Treiberversion des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d7a4c-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-182">Details der Netzwerkverbindung des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-182">Details of caller’s network connection.</span></span> <span data-ttu-id="d7a4c-183">Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7a4c-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="d7a4c-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-186">Von der WLAN-Verbindung des Anrufers verwendete BSSID (Basic Service Set Identifier).</span><span class="sxs-lookup"><span data-stu-id="d7a4c-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="d7a4c-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-188">Bit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-188">bit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p111">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7a4c-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-193">IP-Adresse des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-193">IP address of the callee.</span></span> <span data-ttu-id="d7a4c-194">Hierbei handelt es sich entweder um eine IPv4- oder eine IPv6-Adresse.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="d7a4c-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-196">int</span><span class="sxs-lookup"><span data-stu-id="d7a4c-196">int</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-197">Vom Angerufenen verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="d7a4c-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-199">Bit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-199">bit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p113">Gibt an, ob sich der Angerufene innerhalb des Unternehmensnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb des Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="d7a4c-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-204">MAC-Adresse der von Angerufenen verwendeten Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7a4c-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-207">IP-Adresse des vom Angerufenen verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="d7a4c-208">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7a4c-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d7a4c-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-210">int</span><span class="sxs-lookup"><span data-stu-id="d7a4c-210">int</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-211">Der vom Angerufenen auf dem A/V-Edgedienst verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7a4c-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-214">IP-Adresse des Angerufenen, wie vom A/V-Edgedienst berichtet.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="d7a4c-215">Diese Adresse kann sich von "CalleeIPAddr" unterscheiden, wenn sich der Client beispielsweise hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) befindet.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d7a4c-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-218">Name des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="d7a4c-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-221">Name des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7a4c-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-224">Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7a4c-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-227">Name des Treibers des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="d7a4c-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-230">Beschreibung des WLAN-Treibers des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="d7a4c-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="d7a4c-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-233">WLAN-Treiberversion des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d7a4c-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-236">Details der Netzwerkverbindung des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-236">Details of callee’s network connection.</span></span> <span data-ttu-id="d7a4c-237">Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7a4c-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="d7a4c-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-240">Von der WLAN-Verbindung des Angerufenen verwendete BSSID (Basic Service Set Identifier).</span><span class="sxs-lookup"><span data-stu-id="d7a4c-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="d7a4c-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-242">Bit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-242">bit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p117">Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk verbunden ist. 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="d7a4c-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-246">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-247">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="d7a4c-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-249">int</span><span class="sxs-lookup"><span data-stu-id="d7a4c-249">int</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p118">Hierbei handelt es sich um die genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="d7a4c-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7a4c-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-p119">Quelle der vorgegebenen Bandbreitenbeschränkung. Sie beschreibt den Ursprung der Bandbreitenbeschränkung (z. B."Policy Server", "TURN Server" oder "Modality").</span><span class="sxs-lookup"><span data-stu-id="d7a4c-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-257">Anrufer</span><span class="sxs-lookup"><span data-stu-id="d7a4c-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-258">Bit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-258">bit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-259">Gibt an, ob die Metriken des Anrufers empfangen wurden; 1 ist ja, 0 ist nein.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-260">Aufgerufene</span><span class="sxs-lookup"><span data-stu-id="d7a4c-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-261">Bit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-261">bit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-262">Gibt an, ob die Metriken des Angerufenen empfangen wurden; 1 ist ja, 0 ist nein.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="d7a4c-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-264">Bit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-264">bit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-265">Gibt an, ob es sich um einen Bericht zu einem Teil des Anrufs oder zum gesamten Anruf handelt.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="d7a4c-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-267">Bit</span><span class="sxs-lookup"><span data-stu-id="d7a4c-267">bit</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-268">Gibt an, ob der Anruf als Anruf schlechter Qualität (1) oder als Anruf guter Qualität (0) klassifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a4c-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="d7a4c-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7a4c-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-271">Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a4c-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="d7a4c-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7a4c-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7a4c-274">Gibt an, ob sich der angerufene Benutzer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="d7a4c-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

