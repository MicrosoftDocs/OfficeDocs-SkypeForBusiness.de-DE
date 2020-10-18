---
title: 'Lync Server 2013: Konfigurieren von Video Beispielszenarien'
description: 'Lync Server 2013: Konfigurieren von Video Beispielszenarien.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625899887926de9afe2e6ff94df70ab725c0190a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575141"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="55117-103">Konfigurieren von Video Beispielszenarien für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55117-103">Configuring video example scenarios for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55117-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="55117-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="55117-105">Lync 2013 fügt neue Videofunktionen zur Unterstützung von 1920 x 1080 Full High Definition (HD) Video und Gallery View Video hinzu.</span><span class="sxs-lookup"><span data-stu-id="55117-105">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="55117-106">Messungen basierend auf Kundendaten zeigen, dass die typische Videobandbreite im Vergleich zu lync 2010 nur geringfügig zugenommen hat, die maximale Bandbreite an Videostreams jedoch aufgrund der vollständigen HD-Unterstützung zugenommen hat (Ausführliche Informationen finden Sie im Abschnitt "Verwendung des Medien Verkehrs Netzwerks" unter Anforderungen an die [Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="55117-106">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="55117-107">Deshalb sollten Administratoren die Videobandbreite für bestimmte Benutzer beschränken (z. B. Benutzer in einer Zweigniederlassung, die über weniger Netzwerkkapazität verfügen) und dadurch die bestmögliche Videoqualität für andere Benutzer (z. B. Führungskräfte) sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="55117-107">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="55117-p102">Die folgende Tabelle enthält eine Aufstellung der empfohlenen Einstellungen zum Konfigurieren von Video für verschiedene Netzwerkkapazitäten. Mit diesen Einstellungen wird für bestimmte Benutzerszenarien das Senden und Empfangen von Videos mit höherer Auflösung beschränkt (siehe die Spalte ganz rechts). Mit der Mindesteinstellung ist die Katalogansicht aufgrund der niedrigen maximalen Netzwerkbandbreite beim Empfangen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="55117-p102">The following table provides a list of recommended settings for configuring video for different network capacities. These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column). The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="55117-111">Empfohlene Videoeinstellungen</span><span class="sxs-lookup"><span data-stu-id="55117-111">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="55117-112">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="55117-112">AllowMultiView</span></span></th>
<th><span data-ttu-id="55117-113">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="55117-113">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="55117-114">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="55117-114">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="55117-115">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="55117-115">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="55117-116">Erwartete Videoauflösung für Video in guter Qualität</span><span class="sxs-lookup"><span data-stu-id="55117-116">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55117-117">Optimal</span><span class="sxs-lookup"><span data-stu-id="55117-117">Best</span></span></p></td>
<td><p><span data-ttu-id="55117-118">True</span><span class="sxs-lookup"><span data-stu-id="55117-118">True</span></span></p></td>
<td><p><span data-ttu-id="55117-119">True</span><span class="sxs-lookup"><span data-stu-id="55117-119">True</span></span></p></td>
<td><p><span data-ttu-id="55117-120">8000</span><span class="sxs-lookup"><span data-stu-id="55117-120">8000</span></span></p></td>
<td><p><span data-ttu-id="55117-121">8000</span><span class="sxs-lookup"><span data-stu-id="55117-121">8000</span></span></p></td>
<td><p><span data-ttu-id="55117-122">Peer-zu-Peer: Videoauflösung von bis zu 1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="55117-122">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="55117-123">Katalogansicht: Bis zu 2 Videos mit einer Auflösung von 1920 x 1080 oder mehrere Videos mit niedrigerer Auflösung</span><span class="sxs-lookup"><span data-stu-id="55117-123">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55117-124">Gut</span><span class="sxs-lookup"><span data-stu-id="55117-124">Good</span></span></p></td>
<td><p><span data-ttu-id="55117-125">True</span><span class="sxs-lookup"><span data-stu-id="55117-125">True</span></span></p></td>
<td><p><span data-ttu-id="55117-126">True</span><span class="sxs-lookup"><span data-stu-id="55117-126">True</span></span></p></td>
<td><p><span data-ttu-id="55117-127">2500</span><span class="sxs-lookup"><span data-stu-id="55117-127">2500</span></span></p></td>
<td><p><span data-ttu-id="55117-128">2500</span><span class="sxs-lookup"><span data-stu-id="55117-128">2500</span></span></p></td>
<td><p><span data-ttu-id="55117-129">Peer-zu-Peer: Videoauflösung von bis zu 1280 x 720</span><span class="sxs-lookup"><span data-stu-id="55117-129">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="55117-130">Katalogansicht: Bis zu fünf Videos mit einer Auflösung von 640 x 360</span><span class="sxs-lookup"><span data-stu-id="55117-130">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55117-131">Mittel</span><span class="sxs-lookup"><span data-stu-id="55117-131">Medium</span></span></p></td>
<td><p><span data-ttu-id="55117-132">True</span><span class="sxs-lookup"><span data-stu-id="55117-132">True</span></span></p></td>
<td><p><span data-ttu-id="55117-133">True</span><span class="sxs-lookup"><span data-stu-id="55117-133">True</span></span></p></td>
<td><p><span data-ttu-id="55117-134">1000</span><span class="sxs-lookup"><span data-stu-id="55117-134">1000</span></span></p></td>
<td><p><span data-ttu-id="55117-135">1000</span><span class="sxs-lookup"><span data-stu-id="55117-135">1000</span></span></p></td>
<td><p><span data-ttu-id="55117-136">Peer-zu-Peer: Videoauflösung von bis zu 960 x 540</span><span class="sxs-lookup"><span data-stu-id="55117-136">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="55117-137">Katalogansicht: Bis zu fünf Videos mit einer Auflösung von 424 x 240</span><span class="sxs-lookup"><span data-stu-id="55117-137">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55117-138">Minimum</span><span class="sxs-lookup"><span data-stu-id="55117-138">Minimum</span></span></p></td>
<td><p><span data-ttu-id="55117-139">Richtig</span><span class="sxs-lookup"><span data-stu-id="55117-139">True</span></span></p></td>
<td><p><span data-ttu-id="55117-140">False</span><span class="sxs-lookup"><span data-stu-id="55117-140">False</span></span></p></td>
<td><p><span data-ttu-id="55117-141">350</span><span class="sxs-lookup"><span data-stu-id="55117-141">350</span></span></p></td>
<td><p><span data-ttu-id="55117-142">350</span><span class="sxs-lookup"><span data-stu-id="55117-142">350</span></span></p></td>
<td><p><span data-ttu-id="55117-143">Peer-zu-Peer: Videoauflösung von bis zu 424 x 240</span><span class="sxs-lookup"><span data-stu-id="55117-143">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="55117-144">Katalogansicht: Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="55117-144">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="55117-145">Mithilfe der Informationen in der vorstehenden Tabelle können Sie die neuen HD-Video- und Katalogansicht-Videokonferenzfeatures für bestimmte Benutzer in Ihrer Organisation und andere Videoauflösungen für andere Benutzer verwenden.</span><span class="sxs-lookup"><span data-stu-id="55117-145">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="55117-p103">Im folgenden Beispiel führt der Administrator die neuen Videofeatures mit der höchsten Videoqualität nur für Führungskräfte ein. Für Mitarbeiter in einer Remotezweigniederlassung mit niedriger Netzwerkkapazität wird nur die Minimumeinstellung aus der vorstehenden Tabelle bereitgestellt. Für alle anderen Mitarbeiter wird die Einstellung "Gut" aus der vorstehenden Tabelle bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="55117-p103">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives. For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed. For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="55117-p104">Für das Rollout der neuen Features für die Führungskräfte erstellt der Administrator die Konferenzrichtlinie ExecutiveVideo. Diese Konferenzrichtlinie weist die folgenden Einstellungen auf:</span><span class="sxs-lookup"><span data-stu-id="55117-p104">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="55117-151">VideoBitRateKB ist auf 8000 KBit/s festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-151">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="55117-152">TotalReceiveVideoBitRateKB ist auf 8000 KBit/s festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-152">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="55117-153">AllowMultiview ist auf True festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-153">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="55117-154">EnableMultiviewJoin ist auf True festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-154">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="55117-p105">Für die Mitarbeiter in der Zweigniederlassung erstellt der Administrator die Konferenzrichtlinie BranchOfficeVideo. Diese Konferenzrichtlinie weist die folgenden Einstellungen auf:</span><span class="sxs-lookup"><span data-stu-id="55117-p105">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="55117-157">VideoBitRateKB ist auf 350 KBit/s festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-157">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="55117-158">TotalReceiveVideoBitRateKB ist auf 350 KBit/s festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-158">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="55117-159">AllowMultiview ist auf True festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-159">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="55117-160">EnableMultiviewJoin ist auf False festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-160">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="55117-p106">Für alle anderen Mitarbeiter erstellt der Administrator die Konferenzrichtlinie StandardVideo. Diese Konferenzrichtlinie weist die folgenden Einstellungen auf:</span><span class="sxs-lookup"><span data-stu-id="55117-p106">For all other employees, the administrator creates a conferencing policy named StandardVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="55117-163">VideoBitRateKB ist auf 2500 KBit/s festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-163">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="55117-164">TotalReceiveVideoBitRateKB ist auf 2500 KBit/s festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-164">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="55117-165">AllowMultiview ist auf True festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-165">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="55117-166">EnableMultiviewJoin ist auf True festgelegt</span><span class="sxs-lookup"><span data-stu-id="55117-166">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="55117-167">Der Administrator weist die Konferenzrichtlinie wie folgt den Benutzern zu:</span><span class="sxs-lookup"><span data-stu-id="55117-167">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="55117-168">Die Konferenzrichtlinie ExecutiveVideo wird den Führungskräften zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="55117-168">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="55117-169">Die Konferenzrichtlinie BranchOfficeVideo wird allen Mitarbeitern in der Zweigniederlassung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="55117-169">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="55117-170">Die Konferenzrichtlinie StandardVideo wird allen anderen Mitarbeitern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="55117-170">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="55117-171">Diese Zuweisungen von Konferenzrichtlinien ergeben für die Benutzer Folgendes:</span><span class="sxs-lookup"><span data-stu-id="55117-171">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="55117-172">Alle von einem beliebigen Benutzer organisierte Konferenzen unterstützen die Katalogansicht, aber Mitarbeiter in der Zweigniederlassung können die Katalogansicht nicht nutzen.</span><span class="sxs-lookup"><span data-stu-id="55117-172">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="55117-173">Für Konferenzen mit zwei oder mehreren Teilnehmern können die Führungskräfte Full-HD-Video mit einer Auflösung von 1920 x 1080 senden, falls dies von ihrer Hardware und Netzwerkverbindung unterstützt wird, und sie können Full-HD-Video mit einer Auflösung von 1920 x 1080 empfangen, soweit dies von den Clients der anderen Teilnehmer unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="55117-173">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="55117-174">Mitarbeiter, die keine Führungskräfte sind, können bei Konferenzen mit zwei oder mehreren Teilnehmern niedrigere Auflösungen als die Führungskräfte nutzen, erhalten aber immer noch eine gute Auflösung.</span><span class="sxs-lookup"><span data-stu-id="55117-174">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="55117-175">Mitarbeiter, die sich in der Zweigniederlassung befinden, erhalten bei Anrufen mit zwei Teilnehmern gute Videoqualität, wenn lync die Standardgröße des Videofensters anzeigt. Wenn das lync-Fenster jedoch auf den Vollbildmodus maximiert ist, wird die Videoauflösung nicht erhöht.</span><span class="sxs-lookup"><span data-stu-id="55117-175">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="55117-176">Bei Konferenzen mit mehreren Teilnehmer wird den Mitarbeitern in der Zweigstelle nur ein aktives Video angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55117-176">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

