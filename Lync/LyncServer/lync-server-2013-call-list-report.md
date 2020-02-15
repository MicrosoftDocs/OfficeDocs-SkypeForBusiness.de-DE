---
title: 'Lync Server 2013: Anruflistenbericht'
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
ms.openlocfilehash: 53b462644e2334f428b8cd9a46c0ca07472f6ee2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="2020c-102">Anruflistenbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2020c-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2020c-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2020c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2020c-104">Der Anruflistenbericht enthält QoE-Metriken (Quality of Experience) für einzelne Anrufe, die in Ihrer Organisation getätigt und empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="2020c-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="2020c-105">Beachten Sie, dass die gemeldeten tatsächlichen Metriken davon abhängen, wie Sie auf den Anruflistenbericht zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="2020c-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="2020c-106">Wenn Sie beispielsweise den Bericht [im gerätebericht in lync Server 2013](lync-server-2013-device-report.md)öffnen, werden Metriken wie die folgenden Metriken angezeigt, die auch im gerätebericht angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="2020c-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="2020c-107">Mikrofon des Anrufers</span><span class="sxs-lookup"><span data-stu-id="2020c-107">Caller's microphone</span></span>

  - <span data-ttu-id="2020c-108">Sprecher des Anrufers</span><span class="sxs-lookup"><span data-stu-id="2020c-108">Caller's speaker</span></span>

  - <span data-ttu-id="2020c-109">Mikrofon des angerufenen</span><span class="sxs-lookup"><span data-stu-id="2020c-109">Callee's microphone</span></span>

  - <span data-ttu-id="2020c-110">Sprecher des angerufenen</span><span class="sxs-lookup"><span data-stu-id="2020c-110">Callee's speaker</span></span>

  - <span data-ttu-id="2020c-111">Verhältnis der Zeit für die Sprachumstellung</span><span class="sxs-lookup"><span data-stu-id="2020c-111">Ratio of voice switch time</span></span>

<span data-ttu-id="2020c-112">Wenn Sie den Anruflistenbericht jedoch über den [Standortbericht in lync Server 2013](lync-server-2013-location-report.md)öffnen, werden keine dieser Metriken angezeigt; Stattdessen werden Metriken wie die folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="2020c-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="2020c-113">Roundtrip (ms)</span><span class="sxs-lookup"><span data-stu-id="2020c-113">Round trip (ms)</span></span>

  - <span data-ttu-id="2020c-114">Beeinträchtigung (MOS)</span><span class="sxs-lookup"><span data-stu-id="2020c-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="2020c-115">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="2020c-115">Packet loss</span></span>

  - <span data-ttu-id="2020c-116">Jitter (ms)</span><span class="sxs-lookup"><span data-stu-id="2020c-116">Jitter (ms)</span></span>

<span data-ttu-id="2020c-117">Dies sind die Metriken, die im Standortbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2020c-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="2020c-118">Aus dem Anruflistenbericht können Sie jedoch jederzeit auf die Detail Metrik klicken, um vollständige QoE-Informationen für jeden Anruf bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2020c-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="2020c-119">Zugreifen auf den Anruflistenbericht</span><span class="sxs-lookup"><span data-stu-id="2020c-119">Accessing the Call List Report</span></span>

<span data-ttu-id="2020c-120">Auf den Anruflistenbericht kann über einen der folgenden Berichte zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="2020c-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="2020c-121">Der [Standortbericht in lync Server 2013](lync-server-2013-location-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="2020c-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="2020c-122">Der [gerätebericht in lync Server 2013](lync-server-2013-device-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="2020c-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="2020c-123">Der [zusammenfassende Bericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="2020c-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="2020c-124">Der [Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="2020c-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="2020c-125">Im Anruflistenbericht können Sie auf den [Anruf Detailbericht in lync Server 2013](lync-server-2013-call-detail-report.md) zugreifen, indem Sie auf die Metrik Detail klicken.</span><span class="sxs-lookup"><span data-stu-id="2020c-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="2020c-126">Optimale Verwendung des Anruflisten Berichts</span><span class="sxs-lookup"><span data-stu-id="2020c-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="2020c-127">Wenn Sie nicht mehr wissen, welche Metriken für den Anruflistenbericht (beispielsweise die Zeit für das Verhältnis von VoIP-Umschaltungen) tatsächlich gemessen werden, halten Sie die Maus über dem metrischen Etikett; eine QuickInfo wird dann angezeigt, die Ihnen eine kurze Beschreibung der Metrik gibt.</span><span class="sxs-lookup"><span data-stu-id="2020c-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2020c-128">Filter</span><span class="sxs-lookup"><span data-stu-id="2020c-128">Filters</span></span>

<span data-ttu-id="2020c-129">Keine.</span><span class="sxs-lookup"><span data-stu-id="2020c-129">None.</span></span> <span data-ttu-id="2020c-130">Der Anruflistenbericht kann nicht gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="2020c-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2020c-131">Metriken</span><span class="sxs-lookup"><span data-stu-id="2020c-131">Metrics</span></span>

<span data-ttu-id="2020c-132">In der folgenden Tabelle sind die Informationen aufgeführt, die im Anruflistenbericht für jeden Anruf angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2020c-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="2020c-133">Metriken für den Anruflistenbericht</span><span class="sxs-lookup"><span data-stu-id="2020c-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2020c-134">Name</span><span class="sxs-lookup"><span data-stu-id="2020c-134">Name</span></span></th>
<th><span data-ttu-id="2020c-135">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="2020c-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2020c-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2020c-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2020c-137"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-138">Nein</span><span class="sxs-lookup"><span data-stu-id="2020c-138">No</span></span></p></td>
<td><p><span data-ttu-id="2020c-139">Wenn Sie auf dieses Element klicken, zeigt der Bericht zusätzliche Informationen über den Anruf an.</span><span class="sxs-lookup"><span data-stu-id="2020c-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2020c-140"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-141">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-142">SIP-Adresse der Person, die den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="2020c-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2020c-143"><strong>Aufgerufene</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-144">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-145">SIP-Adresse der Person, die aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="2020c-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2020c-146"><strong>Start time</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-147">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-148">Datum und Uhrzeit des Beginns des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="2020c-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2020c-149"><strong>Endzeit</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-150">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-151">Datum und Uhrzeit des Endes des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="2020c-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2020c-152"><strong>Benutzer-Agent des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-153">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-154">Software, die vom Endpunkt der Person, die den Anruf initiiert hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2020c-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2020c-155"><strong>Benutzer-Agent des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-156">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-157">Software, die vom Endpunkt der Person verwendet wurde, die aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="2020c-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2020c-158"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-159">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-p104">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="2020c-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2020c-p105">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="2020c-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2020c-164"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-165">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-166">Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat.</span><span class="sxs-lookup"><span data-stu-id="2020c-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="2020c-167">Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut).</span><span class="sxs-lookup"><span data-stu-id="2020c-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="2020c-168">Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung.</span><span class="sxs-lookup"><span data-stu-id="2020c-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="2020c-169">Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ.</span><span class="sxs-lookup"><span data-stu-id="2020c-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="2020c-170">In lync Server verwendet lync Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="2020c-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="2020c-p107">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="2020c-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2020c-173"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-174">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-p108">Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="2020c-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2020c-178"><strong>Jitter</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-179">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-180">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="2020c-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2020c-181">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="2020c-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2020c-182"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-183">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-p110">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="2020c-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2020c-186"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-187">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-p111">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="2020c-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2020c-190"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-191">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-p112">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="2020c-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2020c-194"><strong>Konnektivität</strong></span><span class="sxs-lookup"><span data-stu-id="2020c-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="2020c-195">Ja</span><span class="sxs-lookup"><span data-stu-id="2020c-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="2020c-196">Typ der drahtlosen Kommunikationsverbindung.</span><span class="sxs-lookup"><span data-stu-id="2020c-196">Type of wireless communication link.</span></span> <span data-ttu-id="2020c-197">In der Regel ist dies einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="2020c-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2020c-198">Relay</span><span class="sxs-lookup"><span data-stu-id="2020c-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="2020c-199">Direkte</span><span class="sxs-lookup"><span data-stu-id="2020c-199">Direct</span></span></p></li>
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

