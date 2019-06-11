---
title: 'Lync Server 2013: traceroute-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="5c5ac-102">TraceRoute-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c5ac-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c5ac-103">_**Letztes Änderungsdatum des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="5c5ac-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="5c5ac-104">Die traceroute-Tabelle enthält Routinginformationen aus anrufen.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="5c5ac-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c5ac-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5c5ac-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5c5ac-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5c5ac-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c5ac-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5ac-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5c5ac-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-112">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="5c5ac-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-113">Das Datum und die Uhrzeit, zu der der Anruf begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c5ac-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5ac-115">int</span><span class="sxs-lookup"><span data-stu-id="5c5ac-115">int</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-116">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="5c5ac-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-117">Eindeutiger Bezeichner, der verwendet wird, um zwischen mehreren Anrufen zu unterscheiden, die möglicherweise am gleichen Datum und zur gleichen Zeit begonnen haben.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c5ac-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5ac-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="5c5ac-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-120">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="5c5ac-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-121">Stellt den Typ der im Anruf verwendeten Videozeile dar.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="5c5ac-122">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5c5ac-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5c5ac-123">0 – Audio</span><span class="sxs-lookup"><span data-stu-id="5c5ac-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="5c5ac-124">1 – Video</span><span class="sxs-lookup"><span data-stu-id="5c5ac-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="5c5ac-125">2 – Panorama Video</span><span class="sxs-lookup"><span data-stu-id="5c5ac-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="5c5ac-126">3 – Anwendung/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="5c5ac-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c5ac-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5ac-128">bit</span><span class="sxs-lookup"><span data-stu-id="5c5ac-128">bit</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-129">Primary</span><span class="sxs-lookup"><span data-stu-id="5c5ac-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-130">Endpunkt, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c5ac-131"><strong>Hop</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5ac-132">int</span><span class="sxs-lookup"><span data-stu-id="5c5ac-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c5ac-133">Netzwerk-Hop/</span><span class="sxs-lookup"><span data-stu-id="5c5ac-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c5ac-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5ac-135">int</span><span class="sxs-lookup"><span data-stu-id="5c5ac-135">int</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-136">Fremd</span><span class="sxs-lookup"><span data-stu-id="5c5ac-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c5ac-137">Eindeutiger Bezeichner für die IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="5c5ac-138">IP-Adressinformationen werden in der <a href="lync-server-2013-ipaddress-table.md">Tabelle IPAddress in lync Server 2013</a>gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c5ac-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="5c5ac-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5ac-140">int</span><span class="sxs-lookup"><span data-stu-id="5c5ac-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c5ac-141">Roundtrip-Zeit.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-141">Roundtrip time.</span></span> <span data-ttu-id="5c5ac-142">Die Roundtrip-Zeit misst die Zeitdauer, die ein Sprachpaket benötigt, um sein Ziel zu erreichen, und sendet dann eine Benachrichtigung, dass es empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="5c5ac-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

