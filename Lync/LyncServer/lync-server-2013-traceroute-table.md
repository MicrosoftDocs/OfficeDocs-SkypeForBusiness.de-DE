---
title: 'Lync Server 2013: traceroute-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afb8cfb65fdf8fdbb4c281127caafd394cb878af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="693a7-102">TraceRoute-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="693a7-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="693a7-103">_**Letztes Änderungsstand des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="693a7-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="693a7-104">Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="693a7-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="693a7-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="693a7-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="693a7-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="693a7-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="693a7-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="693a7-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="693a7-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="693a7-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="693a7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="693a7-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="693a7-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="693a7-113">Datum und Uhrzeit des Beginns des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="693a7-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="693a7-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="693a7-115">int</span><span class="sxs-lookup"><span data-stu-id="693a7-115">int</span></span></p></td>
<td><p><span data-ttu-id="693a7-116">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="693a7-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="693a7-117">Eindeutige ID, die zur Unterscheidung zwischen mehreren Anrufen verwendet wird, die möglicherweise zum gleichen Datum und zur gleichen Uhrzeit  begonnen haben.</span><span class="sxs-lookup"><span data-stu-id="693a7-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="693a7-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="693a7-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="693a7-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="693a7-120">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="693a7-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="693a7-p102">Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="693a7-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="693a7-123">0 – Audio</span><span class="sxs-lookup"><span data-stu-id="693a7-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="693a7-124">1 – Video</span><span class="sxs-lookup"><span data-stu-id="693a7-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="693a7-125">2 -- Panoramavideo</span><span class="sxs-lookup"><span data-stu-id="693a7-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="693a7-126">3 – Anwendungs-/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="693a7-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="693a7-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="693a7-128">Bit</span><span class="sxs-lookup"><span data-stu-id="693a7-128">bit</span></span></p></td>
<td><p><span data-ttu-id="693a7-129">Primary</span><span class="sxs-lookup"><span data-stu-id="693a7-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="693a7-130">Endpunkt, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="693a7-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="693a7-131"><strong>Hop</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="693a7-132">int</span><span class="sxs-lookup"><span data-stu-id="693a7-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="693a7-133">Netzwerk-Hop/</span><span class="sxs-lookup"><span data-stu-id="693a7-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="693a7-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="693a7-135">int</span><span class="sxs-lookup"><span data-stu-id="693a7-135">int</span></span></p></td>
<td><p><span data-ttu-id="693a7-136">Fremd</span><span class="sxs-lookup"><span data-stu-id="693a7-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="693a7-137">Eindeutige ID für die IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="693a7-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="693a7-138">IP-Adressinformationen werden in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle in lync Server 2013</a>gespeichert.</span><span class="sxs-lookup"><span data-stu-id="693a7-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="693a7-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="693a7-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="693a7-140">int</span><span class="sxs-lookup"><span data-stu-id="693a7-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="693a7-p104">Paketumlaufzeit (Roundtrip time). Die Paketumlaufzeit misst die Zeit, die ein Sprachpaket benötigt, um zu seinem Ziel zu gelangen und eine Benachrichtigung über den Empfang zu senden.</span><span class="sxs-lookup"><span data-stu-id="693a7-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

