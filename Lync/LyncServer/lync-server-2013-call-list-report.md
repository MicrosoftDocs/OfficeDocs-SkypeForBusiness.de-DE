---
title: 'Lync Server 2013: Anruflistenbericht'
description: 'Lync Server 2013: Anruflistenbericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561691"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="dc929-103">Anruflistenbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc929-103">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc929-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dc929-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dc929-105">Der Anruflistenbericht enthält QoE-Metriken (Quality of Experience) für einzelne Anrufe, die in Ihrer Organisation getätigt und empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="dc929-105">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="dc929-106">Beachten Sie, dass die gemeldeten tatsächlichen Metriken davon abhängen, wie Sie auf den Anruflistenbericht zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="dc929-106">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="dc929-107">Wenn Sie beispielsweise den Bericht [im gerätebericht in lync Server 2013](lync-server-2013-device-report.md)öffnen, werden Metriken wie die folgenden Metriken angezeigt, die auch im gerätebericht angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="dc929-107">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="dc929-108">Mikrofon des Anrufers</span><span class="sxs-lookup"><span data-stu-id="dc929-108">Caller's microphone</span></span>

  - <span data-ttu-id="dc929-109">Sprecher des Anrufers</span><span class="sxs-lookup"><span data-stu-id="dc929-109">Caller's speaker</span></span>

  - <span data-ttu-id="dc929-110">Mikrofon des angerufenen</span><span class="sxs-lookup"><span data-stu-id="dc929-110">Callee's microphone</span></span>

  - <span data-ttu-id="dc929-111">Sprecher des angerufenen</span><span class="sxs-lookup"><span data-stu-id="dc929-111">Callee's speaker</span></span>

  - <span data-ttu-id="dc929-112">Verhältnis der Zeit für die Sprachumstellung</span><span class="sxs-lookup"><span data-stu-id="dc929-112">Ratio of voice switch time</span></span>

<span data-ttu-id="dc929-113">Wenn Sie den Anruflistenbericht jedoch über den [Standortbericht in lync Server 2013](lync-server-2013-location-report.md)öffnen, werden keine dieser Metriken angezeigt; Stattdessen werden Metriken wie die folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dc929-113">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="dc929-114">Roundtrip (ms)</span><span class="sxs-lookup"><span data-stu-id="dc929-114">Round trip (ms)</span></span>

  - <span data-ttu-id="dc929-115">Beeinträchtigung (MOS)</span><span class="sxs-lookup"><span data-stu-id="dc929-115">Degradation (MOS)</span></span>

  - <span data-ttu-id="dc929-116">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="dc929-116">Packet loss</span></span>

  - <span data-ttu-id="dc929-117">Jitter (ms)</span><span class="sxs-lookup"><span data-stu-id="dc929-117">Jitter (ms)</span></span>

<span data-ttu-id="dc929-118">Dies sind die Metriken, die im Standortbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dc929-118">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="dc929-119">Aus dem Anruflistenbericht können Sie jedoch jederzeit auf die Detail Metrik klicken, um vollständige QoE-Informationen für jeden Anruf bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="dc929-119">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="dc929-120">Zugreifen auf den Anruflistenbericht</span><span class="sxs-lookup"><span data-stu-id="dc929-120">Accessing the Call List Report</span></span>

<span data-ttu-id="dc929-121">Auf den Anruflistenbericht kann über einen der folgenden Berichte zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="dc929-121">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="dc929-122">Der [Standortbericht in lync Server 2013](lync-server-2013-location-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="dc929-122">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="dc929-123">Der [gerätebericht in lync Server 2013](lync-server-2013-device-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="dc929-123">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="dc929-124">Der [zusammenfassende Bericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="dc929-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="dc929-125">Der [Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="dc929-125">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="dc929-126">Im Anruflistenbericht können Sie auf den [Anruf Detailbericht in lync Server 2013](lync-server-2013-call-detail-report.md) zugreifen, indem Sie auf die Metrik Detail klicken.</span><span class="sxs-lookup"><span data-stu-id="dc929-126">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="dc929-127">Optimale Verwendung des Anruflisten Berichts</span><span class="sxs-lookup"><span data-stu-id="dc929-127">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="dc929-128">Wenn Sie nicht mehr wissen, welche Metriken für den Anruflistenbericht (beispielsweise die Zeit für das Verhältnis von VoIP-Umschaltungen) tatsächlich gemessen werden, halten Sie die Maus über dem metrischen Etikett; eine QuickInfo wird dann angezeigt, die Ihnen eine kurze Beschreibung der Metrik gibt.</span><span class="sxs-lookup"><span data-stu-id="dc929-128">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dc929-129">Filter</span><span class="sxs-lookup"><span data-stu-id="dc929-129">Filters</span></span>

<span data-ttu-id="dc929-130">Keine.</span><span class="sxs-lookup"><span data-stu-id="dc929-130">None.</span></span> <span data-ttu-id="dc929-131">Der Anruflistenbericht kann nicht gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="dc929-131">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="dc929-132">Metriken</span><span class="sxs-lookup"><span data-stu-id="dc929-132">Metrics</span></span>

<span data-ttu-id="dc929-133">In der folgenden Tabelle sind die Informationen aufgeführt, die im Anruflistenbericht für jeden Anruf angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dc929-133">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="dc929-134">Metriken für den Anruflistenbericht</span><span class="sxs-lookup"><span data-stu-id="dc929-134">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc929-135">Name</span><span class="sxs-lookup"><span data-stu-id="dc929-135">Name</span></span></th>
<th><span data-ttu-id="dc929-136">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="dc929-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dc929-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc929-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc929-138"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-138"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-139">Nein</span><span class="sxs-lookup"><span data-stu-id="dc929-139">No</span></span></p></td>
<td><p><span data-ttu-id="dc929-140">Wenn Sie auf dieses Element klicken, zeigt der Bericht zusätzliche Informationen über den Anruf an.</span><span class="sxs-lookup"><span data-stu-id="dc929-140">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc929-141"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-141"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-142">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-142">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-143">SIP-Adresse der Person, die den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="dc929-143">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc929-144"><strong>Aufgerufene</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-144"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-145">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-146">SIP-Adresse der Person, die aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="dc929-146">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc929-147"><strong>Start time</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-147"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-148">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-148">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-149">Datum und Uhrzeit des Beginns des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="dc929-149">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc929-150"><strong>Endzeit</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-150"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-151">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-152">Datum und Uhrzeit des Endes des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="dc929-152">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc929-153"><strong>Benutzer-Agent des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-153"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-154">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-154">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-155">Software, die vom Endpunkt der Person, die den Anruf initiiert hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="dc929-155">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc929-156"><strong>Benutzer-Agent des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-156"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-157">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-157">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-158">Software, die vom Endpunkt der Person verwendet wurde, die aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="dc929-158">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc929-159"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-159"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-160">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-160">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-p104">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="dc929-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="dc929-p105">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="dc929-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc929-165"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-165"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-166">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-166">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-167">Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat.</span><span class="sxs-lookup"><span data-stu-id="dc929-167">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="dc929-168">Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut).</span><span class="sxs-lookup"><span data-stu-id="dc929-168">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="dc929-169">Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung.</span><span class="sxs-lookup"><span data-stu-id="dc929-169">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="dc929-170">Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ.</span><span class="sxs-lookup"><span data-stu-id="dc929-170">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="dc929-171">In lync Server verwendet lync Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="dc929-171">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="dc929-p107">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="dc929-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc929-174"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-174"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-175">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-p108">Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="dc929-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc929-179"><strong>Jitter</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-179"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-180">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-181">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="dc929-181">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="dc929-182">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="dc929-182">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc929-183"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-183"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-184">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-p110">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="dc929-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc929-187"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-187"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-188">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-188">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-p111">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="dc929-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc929-191"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-191"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-192">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-p112">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="dc929-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc929-195"><strong>Konnektivität</strong></span><span class="sxs-lookup"><span data-stu-id="dc929-195"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="dc929-196">Ja</span><span class="sxs-lookup"><span data-stu-id="dc929-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="dc929-197">Typ der drahtlosen Kommunikationsverbindung.</span><span class="sxs-lookup"><span data-stu-id="dc929-197">Type of wireless communication link.</span></span> <span data-ttu-id="dc929-198">In der Regel ist dies einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="dc929-198">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc929-199">Relay</span><span class="sxs-lookup"><span data-stu-id="dc929-199">Relay</span></span></p></li>
<li><p><span data-ttu-id="dc929-200">Direkte</span><span class="sxs-lookup"><span data-stu-id="dc929-200">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

