---
title: 'Lync Server 2013: Überwachen des Gruppenchats'
description: 'Lync Server 2013: Überwachen des Gruppenchats.'
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
ms.openlocfilehash: 625e45f455e8dba50a5fa64240b62cb010623d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562031"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="79502-103">Überwachen des Gruppenchats in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79502-103">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79502-104">_**Letztes Änderungsstand des Themas:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="79502-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="79502-105">Es wird dringend empfohlen, das neueste [Installationsprogramm für kumulative Server Updates](https://support.microsoft.com/kb/968802) , das im Microsoft Download Center verfügbar ist, zur Verbesserung der Leistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="79502-105">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="79502-106">Unter der Voraussetzung, dass Sie das neueste kumulative Update ausführen, verwenden Sie die folgende Belastungstest Tabelle für Metriken, um zu verstehen, ob Ihre Gruppen Chat Server mit optimaler Integrität betrieben werden.</span><span class="sxs-lookup"><span data-stu-id="79502-106">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="79502-107">Test Umgebung und Benutzermodell</span><span class="sxs-lookup"><span data-stu-id="79502-107">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="79502-108">Drei Gruppenchatserver in einem Gruppenchat Pool mit jeweils 8 GB Arbeitsspeicher und 8 Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="79502-108">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79502-109">Zwei lync Server 2013-Front-Ends in Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="79502-109">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79502-110">60.000 gleichzeitige Benutzer auf drei Gruppen Chat Servern.</span><span class="sxs-lookup"><span data-stu-id="79502-110">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79502-111">25.000 Kanäle, die vom Gruppen Chat Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="79502-111">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79502-112">Kanalgröße:</span><span class="sxs-lookup"><span data-stu-id="79502-112">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="79502-113">Größe des kleinen Kanals: 30</span><span class="sxs-lookup"><span data-stu-id="79502-113">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="79502-114">Mittlere Kanalgröße: 150</span><span class="sxs-lookup"><span data-stu-id="79502-114">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="79502-115">Große Kanalgröße: 2500</span><span class="sxs-lookup"><span data-stu-id="79502-115">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79502-116">Kanalanzahl:</span><span class="sxs-lookup"><span data-stu-id="79502-116">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="79502-117">Zahl kleine Kanäle: 24.000</span><span class="sxs-lookup"><span data-stu-id="79502-117">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="79502-118">Zahlmittel große Kanäle 800</span><span class="sxs-lookup"><span data-stu-id="79502-118">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="79502-119">Zahl große Kanäle 24</span><span class="sxs-lookup"><span data-stu-id="79502-119">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="79502-120">Gesamt Kanäle 24.824</span><span class="sxs-lookup"><span data-stu-id="79502-120">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79502-121">Kanäle einladen:</span><span class="sxs-lookup"><span data-stu-id="79502-121">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="79502-122">Die Hälfte der Kanäle wurden einladen Kanäle</span><span class="sxs-lookup"><span data-stu-id="79502-122">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79502-123">Anzahl der Kanäle, die ein Benutzer anschließt:</span><span class="sxs-lookup"><span data-stu-id="79502-123">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="79502-124">Klein: 12</span><span class="sxs-lookup"><span data-stu-id="79502-124">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="79502-125">Mittel: 2</span><span class="sxs-lookup"><span data-stu-id="79502-125">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="79502-126">Groß: 1</span><span class="sxs-lookup"><span data-stu-id="79502-126">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79502-127">Verknüpfungs Rate:</span><span class="sxs-lookup"><span data-stu-id="79502-127">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="79502-128">10 Gesamt/Sekunde, 3.33/Sekunde pro Server</span><span class="sxs-lookup"><span data-stu-id="79502-128">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79502-129">Abmelde Rate:</span><span class="sxs-lookup"><span data-stu-id="79502-129">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="79502-130">10 Gesamt/Sekunde, 3.33/Sekunde pro Server</span><span class="sxs-lookup"><span data-stu-id="79502-130">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79502-131">Chat Rate:</span><span class="sxs-lookup"><span data-stu-id="79502-131">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="79502-132">20 gesamt/Sekunde, 6.66/Sekunde pro Server</span><span class="sxs-lookup"><span data-stu-id="79502-132">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="79502-133">Die folgenden Leistungsindikator Nummern werden wahrscheinlich variieren, wenn unterschiedliche Hardwarespezifikationen oder Benutzerprofile verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79502-133">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="79502-134">Zu überwachende Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="79502-134">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79502-135">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="79502-135">Performance Counter</span></span></th>
<th><span data-ttu-id="79502-136">Schwellen</span><span class="sxs-lookup"><span data-stu-id="79502-136">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79502-137">Prozess (Channelservice)- &gt; % Prozessorzeit</span><span class="sxs-lookup"><span data-stu-id="79502-137">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="79502-138">Min: 0</span><span class="sxs-lookup"><span data-stu-id="79502-138">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

