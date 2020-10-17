---
title: 'Lync Server 2013: traceroute-Tabelle'
description: 'Lync Server 2013: traceroute-Tabelle.'
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
ms.openlocfilehash: 8af33e572065fbab1eaaaef684997e7f95edaed9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549061"
---
# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="23a73-103">TraceRoute-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23a73-103">TraceRoute table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23a73-104">_**Letztes Änderungsstand des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="23a73-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="23a73-105">Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="23a73-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="23a73-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23a73-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23a73-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="23a73-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="23a73-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="23a73-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23a73-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="23a73-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="23a73-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="23a73-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="23a73-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="23a73-114">Datum und Uhrzeit des Beginns des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="23a73-114">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23a73-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="23a73-116">int</span><span class="sxs-lookup"><span data-stu-id="23a73-116">int</span></span></p></td>
<td><p><span data-ttu-id="23a73-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="23a73-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="23a73-118">Eindeutige ID, die zur Unterscheidung zwischen mehreren Anrufen verwendet wird, die möglicherweise zum gleichen Datum und zur gleichen Uhrzeit  begonnen haben.</span><span class="sxs-lookup"><span data-stu-id="23a73-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23a73-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="23a73-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="23a73-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23a73-121">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="23a73-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="23a73-p102">Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="23a73-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="23a73-124">0 – Audio</span><span class="sxs-lookup"><span data-stu-id="23a73-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="23a73-125">1 – Video</span><span class="sxs-lookup"><span data-stu-id="23a73-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="23a73-126">2 -- Panoramavideo</span><span class="sxs-lookup"><span data-stu-id="23a73-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="23a73-127">3 – Anwendungs-/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="23a73-127">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23a73-128"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-128"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="23a73-129">Bit</span><span class="sxs-lookup"><span data-stu-id="23a73-129">bit</span></span></p></td>
<td><p><span data-ttu-id="23a73-130">Primary</span><span class="sxs-lookup"><span data-stu-id="23a73-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="23a73-131">Endpunkt, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="23a73-131">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23a73-132"><strong>Hop</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-132"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="23a73-133">int</span><span class="sxs-lookup"><span data-stu-id="23a73-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23a73-134">Netzwerk-Hop/</span><span class="sxs-lookup"><span data-stu-id="23a73-134">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23a73-135"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-135"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="23a73-136">int</span><span class="sxs-lookup"><span data-stu-id="23a73-136">int</span></span></p></td>
<td><p><span data-ttu-id="23a73-137">Fremd</span><span class="sxs-lookup"><span data-stu-id="23a73-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="23a73-138">Eindeutige ID für die IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="23a73-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="23a73-139">IP-Adressinformationen werden in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle in lync Server 2013</a>gespeichert.</span><span class="sxs-lookup"><span data-stu-id="23a73-139">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23a73-140"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="23a73-140"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="23a73-141">int</span><span class="sxs-lookup"><span data-stu-id="23a73-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23a73-p104">Paketumlaufzeit (Roundtrip time). Die Paketumlaufzeit misst die Zeit, die ein Sprachpaket benötigt, um zu seinem Ziel zu gelangen und eine Benachrichtigung über den Empfang zu senden.</span><span class="sxs-lookup"><span data-stu-id="23a73-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

