---
title: 'Lync Server 2013: Konfigurieren von Video Beispielszenarien'
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
ms.openlocfilehash: cbdd47056b97da1ba3ac1bf884cc3e8bd9aaf43f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="95d73-102">Konfigurieren von Video Beispielszenarien für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95d73-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95d73-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="95d73-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="95d73-104">Lync 2013 fügt neue Videofeatures zur Unterstützung von 1920 x 1080 Full High Definition (HD) Video-und Galerieansicht-Video hinzu.</span><span class="sxs-lookup"><span data-stu-id="95d73-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="95d73-105">Maße, die auf Kundendaten basieren, zeigen, dass die typische Videobandbreite im Vergleich zu lync 2010 nur geringfügig zugenommen hat, die maximale Bandbreite des Videostreams jedoch aufgrund der Full-HD-Unterstützung zugenommen hat (Einzelheiten finden Sie im Abschnitt "Verwendung des Medien Verkehrsnetzwerk" unter [Netzwerkbandbreite für den Mediendatenverkehr in lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="95d73-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="95d73-106">Daher möchten Administratoren möglicherweise die Videobandbreite für bestimmte Benutzer (wie Benutzer in einer Zweigstelle, die eine geringere Netzwerkkapazität aufweisen) einschränken und dabei helfen, die bestmögliche Videoqualität für andere Benutzer (wie Führungskräfte) zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="95d73-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="95d73-107">Die folgende Tabelle enthält eine Liste der empfohlenen Einstellungen für die Konfiguration von Video für verschiedene Netzwerkkapazitäten.</span><span class="sxs-lookup"><span data-stu-id="95d73-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="95d73-108">Diese Einstellungen beschränken einige Benutzerszenarien auf das Senden und empfangen von Videos mit höherer Auflösung (siehe Spalte ganz rechts).</span><span class="sxs-lookup"><span data-stu-id="95d73-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="95d73-109">Die Mindesteinstellungen führen dazu, dass Gallery-Video aufgrund der geringen maximalen Netzwerkbandbreite für den Empfang nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="95d73-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="95d73-110">Empfohlene Video Einstellungen</span><span class="sxs-lookup"><span data-stu-id="95d73-110">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="95d73-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="95d73-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="95d73-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="95d73-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="95d73-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="95d73-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="95d73-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="95d73-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="95d73-115">Erwartete Videoauflösung für Video in guter Qualität</span><span class="sxs-lookup"><span data-stu-id="95d73-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95d73-116">Optimal</span><span class="sxs-lookup"><span data-stu-id="95d73-116">Best</span></span></p></td>
<td><p><span data-ttu-id="95d73-117">Wahr</span><span class="sxs-lookup"><span data-stu-id="95d73-117">True</span></span></p></td>
<td><p><span data-ttu-id="95d73-118">Wahr</span><span class="sxs-lookup"><span data-stu-id="95d73-118">True</span></span></p></td>
<td><p><span data-ttu-id="95d73-119">8000</span><span class="sxs-lookup"><span data-stu-id="95d73-119">8000</span></span></p></td>
<td><p><span data-ttu-id="95d73-120">8000</span><span class="sxs-lookup"><span data-stu-id="95d73-120">8000</span></span></p></td>
<td><p><span data-ttu-id="95d73-121">Peer-to-Peer: bis zu 1920 x 1080 Videoauflösung</span><span class="sxs-lookup"><span data-stu-id="95d73-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="95d73-122">Katalogansicht: bis zu 2 1920 x 1080 Videos oder Videos mit mehreren kleineren Auflösungen</span><span class="sxs-lookup"><span data-stu-id="95d73-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95d73-123">Good</span><span class="sxs-lookup"><span data-stu-id="95d73-123">Good</span></span></p></td>
<td><p><span data-ttu-id="95d73-124">Wahr</span><span class="sxs-lookup"><span data-stu-id="95d73-124">True</span></span></p></td>
<td><p><span data-ttu-id="95d73-125">Wahr</span><span class="sxs-lookup"><span data-stu-id="95d73-125">True</span></span></p></td>
<td><p><span data-ttu-id="95d73-126">2500</span><span class="sxs-lookup"><span data-stu-id="95d73-126">2500</span></span></p></td>
<td><p><span data-ttu-id="95d73-127">2500</span><span class="sxs-lookup"><span data-stu-id="95d73-127">2500</span></span></p></td>
<td><p><span data-ttu-id="95d73-128">Peer-to-Peer: bis zu 1280 x 720 Videoauflösung</span><span class="sxs-lookup"><span data-stu-id="95d73-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="95d73-129">Galerieansicht: Videos mit bis zu 5 640 x 360 Auflösung</span><span class="sxs-lookup"><span data-stu-id="95d73-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95d73-130">Mittel</span><span class="sxs-lookup"><span data-stu-id="95d73-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="95d73-131">Wahr</span><span class="sxs-lookup"><span data-stu-id="95d73-131">True</span></span></p></td>
<td><p><span data-ttu-id="95d73-132">Wahr</span><span class="sxs-lookup"><span data-stu-id="95d73-132">True</span></span></p></td>
<td><p><span data-ttu-id="95d73-133">1000</span><span class="sxs-lookup"><span data-stu-id="95d73-133">1000</span></span></p></td>
<td><p><span data-ttu-id="95d73-134">1000</span><span class="sxs-lookup"><span data-stu-id="95d73-134">1000</span></span></p></td>
<td><p><span data-ttu-id="95d73-135">Peer-to-Peer: bis zu 960 x 540 Videoauflösung</span><span class="sxs-lookup"><span data-stu-id="95d73-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="95d73-136">Galerieansicht: Videos mit bis zu 5 424 x 240 Auflösung</span><span class="sxs-lookup"><span data-stu-id="95d73-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95d73-137">Mindestens</span><span class="sxs-lookup"><span data-stu-id="95d73-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="95d73-138">Wahr</span><span class="sxs-lookup"><span data-stu-id="95d73-138">True</span></span></p></td>
<td><p><span data-ttu-id="95d73-139">Falsch</span><span class="sxs-lookup"><span data-stu-id="95d73-139">False</span></span></p></td>
<td><p><span data-ttu-id="95d73-140">350</span><span class="sxs-lookup"><span data-stu-id="95d73-140">350</span></span></p></td>
<td><p><span data-ttu-id="95d73-141">350</span><span class="sxs-lookup"><span data-stu-id="95d73-141">350</span></span></p></td>
<td><p><span data-ttu-id="95d73-142">Peer-to-Peer: bis zu 424 x 240 Videoauflösung</span><span class="sxs-lookup"><span data-stu-id="95d73-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="95d73-143">Katalogansicht: nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="95d73-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95d73-144">Sie können die Informationen aus der vorstehenden Tabelle verwenden, um die neuen HD-Video-und-Galerie-Videokonferenz Features für einige Benutzer in Ihrer Organisation bereitzustellen, während Sie anderen Videoauflösungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="95d73-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="95d73-145">Im folgenden Beispiel werden die neuen Videofeatures mit der höchsten Videoqualität, die nur Führungskräften zur Verfügung stehen, vom Administrator ausgerollt.</span><span class="sxs-lookup"><span data-stu-id="95d73-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="95d73-146">Für Mitarbeiter in einer Remote-Zweigstelle, die über eine niedrige Netzwerkkapazität verfügt, wird nur die Mindesteinstellung der vorhergehenden Tabelle bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="95d73-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="95d73-147">Für alle anderen Mitarbeiter wird die Einstellung "gut" aus der vorhergehenden Tabelle bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="95d73-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="95d73-148">Um die neuen Funktionen für die Führungskräfte bereitzustellen, erstellt der Administrator eine konferenzrichtlinie mit dem Namen ExecutiveVideo.</span><span class="sxs-lookup"><span data-stu-id="95d73-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="95d73-149">Diese konferenzrichtlinie weist die folgenden Einstellungen auf:</span><span class="sxs-lookup"><span data-stu-id="95d73-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="95d73-150">VideoBitRateKB ist auf 8000 kBit/s eingestellt</span><span class="sxs-lookup"><span data-stu-id="95d73-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="95d73-151">TotalReceiveVideoBitRateKB ist auf 8000 kBit/s eingestellt</span><span class="sxs-lookup"><span data-stu-id="95d73-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="95d73-152">AllowMultiview ist auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95d73-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="95d73-153">EnableMultiviewJoin ist auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95d73-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="95d73-154">Für Mitarbeiter in der Zweigstelle erstellt der Administrator eine konferenzrichtlinie mit dem Namen BranchOfficeVideo.</span><span class="sxs-lookup"><span data-stu-id="95d73-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="95d73-155">Diese konferenzrichtlinie weist die folgenden Einstellungen auf:</span><span class="sxs-lookup"><span data-stu-id="95d73-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="95d73-156">VideoBitRateKB ist auf 350 KBit/s eingestellt</span><span class="sxs-lookup"><span data-stu-id="95d73-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="95d73-157">TotalReceiveVideoBitRateKB ist auf 350 KBit/s eingestellt</span><span class="sxs-lookup"><span data-stu-id="95d73-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="95d73-158">AllowMultiview ist auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95d73-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="95d73-159">EnableMultiviewJoin ist auf "false" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95d73-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="95d73-160">Für alle anderen Mitarbeiter erstellt der Administrator eine konferenzrichtlinie mit dem Namen StandardVideo.</span><span class="sxs-lookup"><span data-stu-id="95d73-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="95d73-161">Diese konferenzrichtlinie weist die folgenden Einstellungen auf:</span><span class="sxs-lookup"><span data-stu-id="95d73-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="95d73-162">VideoBitRateKB ist auf 2500 Kbit/s eingestellt</span><span class="sxs-lookup"><span data-stu-id="95d73-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="95d73-163">TotalReceiveVideoBitRateKB ist auf 2500 Kbit/s eingestellt</span><span class="sxs-lookup"><span data-stu-id="95d73-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="95d73-164">AllowMultiview ist auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95d73-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="95d73-165">EnableMultiviewJoin ist auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95d73-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="95d73-166">Der Administrator weist Benutzer Konferenzrichtlinien wie folgt zu:</span><span class="sxs-lookup"><span data-stu-id="95d73-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="95d73-167">Die ExecutiveVideo-konferenzrichtlinie wird den Führungskräften zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="95d73-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="95d73-168">Die BranchOfficeVideo-konferenzrichtlinie wird allen Mitarbeitern in der Zweigstelle zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="95d73-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="95d73-169">Die StandardVideo-konferenzrichtlinie wird allen anderen Mitarbeitern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="95d73-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="95d73-170">Diese Konferenzrichtlinien Zuweisungen führen zu der folgenden Benutzeroberfläche:</span><span class="sxs-lookup"><span data-stu-id="95d73-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="95d73-171">Alle Konferenzen, die von einer beliebigen Benutzer-Galerieansicht unterstützt werden, aber die Mitarbeiter in der Zweigstelle können die Katalogansicht nicht finden.</span><span class="sxs-lookup"><span data-stu-id="95d73-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="95d73-172">Für zwei-oder Mehrparteienkonferenzen können Führungskräfte 1920 x 1080 Full-HD-Video senden, wenn deren Hardware-und Netzwerkverbindung dies unterstützt, und Sie können 1920 x 1080 Full-HD-Video empfangen, wenn die anderen Teilnehmer dies unterstützen.</span><span class="sxs-lookup"><span data-stu-id="95d73-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="95d73-173">Mitarbeiter, die keine Führungskräfte sind, erleben niedrigere Auflösungen als die Führungskräfte in ihren zwei-oder Mehrparteienkonferenzen, erhalten aber trotzdem eine gute Auflösung.</span><span class="sxs-lookup"><span data-stu-id="95d73-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="95d73-174">Mitarbeiter, die in der Zweigstelle sind, erhalten gute Videoqualität bei Anrufen mit zwei Teilnehmern, wenn lync die Standardgröße des Videofensters anzeigt. Wenn das lync-Fenster jedoch auf Vollbild maximiert ist, nimmt die Videoauflösung nicht zu.</span><span class="sxs-lookup"><span data-stu-id="95d73-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="95d73-175">Bei Konferenzen mit mehreren Teilnehmern werden die Mitarbeiter in der Zweigstelle nur ein aktives Video sehen.</span><span class="sxs-lookup"><span data-stu-id="95d73-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

