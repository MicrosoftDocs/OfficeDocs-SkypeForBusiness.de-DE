---
title: 'Lync Server 2013: Überwachen des Gruppen-Chats'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="316a7-102">Überwachen des Gruppen-Chats in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="316a7-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="316a7-103">_**Letztes Änderungsdatum des Themas:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="316a7-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="316a7-104">Es wird dringend empfohlen, das neueste im Microsoft Download Center verfügbare [kumulative Server Update-Installationsprogramm](http://support.microsoft.com/kb/968802) zur Verbesserung der Leistung zu führen.</span><span class="sxs-lookup"><span data-stu-id="316a7-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="316a7-105">Unter der Voraussetzung, dass Sie das neueste kumulative Update ausführen, verwenden Sie die folgende Belastungstest Tabelle für Metriken, um zu verstehen, ob Ihre Gruppen-Chat Server mit optimaler Integrität ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="316a7-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="316a7-106">Test Umgebung und Benutzermodell</span><span class="sxs-lookup"><span data-stu-id="316a7-106">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="316a7-107">Drei Gruppen-Chat Server in einem Gruppen-Chat-Pool mit jeweils 8 GB Arbeitsspeicher und 8 Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="316a7-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="316a7-108">Zwei lync Server 2013-Front-Ends in Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="316a7-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="316a7-109">60.000 gleichzeitige Benutzer in drei Gruppen Chat Servern.</span><span class="sxs-lookup"><span data-stu-id="316a7-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="316a7-110">25.000-Kanäle, die vom Gruppen-Chat-Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="316a7-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="316a7-111">Kanalgröße:</span><span class="sxs-lookup"><span data-stu-id="316a7-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="316a7-112">Größe des kleinen Kanals: 30</span><span class="sxs-lookup"><span data-stu-id="316a7-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="316a7-113">Mittlere Kanalgröße: 150</span><span class="sxs-lookup"><span data-stu-id="316a7-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="316a7-114">Größe des großen Kanals: 2500</span><span class="sxs-lookup"><span data-stu-id="316a7-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="316a7-115">Kanalanzahl:</span><span class="sxs-lookup"><span data-stu-id="316a7-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="316a7-116">Zahl kleine Kanäle: 24.000</span><span class="sxs-lookup"><span data-stu-id="316a7-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="316a7-117">Zahl Medium Kanäle 800</span><span class="sxs-lookup"><span data-stu-id="316a7-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="316a7-118">Zahl große Kanäle 24</span><span class="sxs-lookup"><span data-stu-id="316a7-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="316a7-119">Gesamtzahl der Kanäle 24.824</span><span class="sxs-lookup"><span data-stu-id="316a7-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="316a7-120">Kanäle einladen:</span><span class="sxs-lookup"><span data-stu-id="316a7-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="316a7-121">Die Hälfte der Kanäle waren Einladungs Kanäle</span><span class="sxs-lookup"><span data-stu-id="316a7-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="316a7-122">Die Anzahl der Kanäle, die ein Benutzer verknüpft:</span><span class="sxs-lookup"><span data-stu-id="316a7-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="316a7-123">Klein: 12</span><span class="sxs-lookup"><span data-stu-id="316a7-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="316a7-124">Mittel: 2</span><span class="sxs-lookup"><span data-stu-id="316a7-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="316a7-125">Groß: 1</span><span class="sxs-lookup"><span data-stu-id="316a7-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="316a7-126">Teilnahmegebühr:</span><span class="sxs-lookup"><span data-stu-id="316a7-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="316a7-127">10 Gesamt/Sekunde, 3.33/Sekunde pro Server</span><span class="sxs-lookup"><span data-stu-id="316a7-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="316a7-128">Abmelde Rate:</span><span class="sxs-lookup"><span data-stu-id="316a7-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="316a7-129">10 Gesamt/Sekunde, 3.33/Sekunde pro Server</span><span class="sxs-lookup"><span data-stu-id="316a7-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="316a7-130">Chat-Gebühr:</span><span class="sxs-lookup"><span data-stu-id="316a7-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="316a7-131">20 gesamt/Sekunde, 6.66/Sekunde pro Server</span><span class="sxs-lookup"><span data-stu-id="316a7-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="316a7-132">Die folgenden Leistungsindikator Nummern variieren wahrscheinlich, wenn verschiedene Hardwarespezifikationen oder Benutzerprofile verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="316a7-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="316a7-133">Zu überwachenden Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="316a7-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="316a7-134">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="316a7-134">Performance Counter</span></span></th>
<th><span data-ttu-id="316a7-135">Schwellenwerte</span><span class="sxs-lookup"><span data-stu-id="316a7-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="316a7-136">Prozess (Channelservice)-&gt;% Prozessorzeit</span><span class="sxs-lookup"><span data-stu-id="316a7-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="316a7-137">Min: 0</span><span class="sxs-lookup"><span data-stu-id="316a7-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

