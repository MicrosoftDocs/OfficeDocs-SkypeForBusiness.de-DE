---
title: 'Lync Server 2013: Anruf Detail Bericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ef309873ef51e06903123dfb5a1b6ecf68b4ea8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502752"
---
# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="0e3a3-102">Anruf Detail Bericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e3a3-102">Call Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e3a3-103">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="0e3a3-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="0e3a3-104">Der Anruf Detail Bericht bietet einen detaillierten Überblick über einen einzelnen Anruf; der Bericht enthält nahezu alle Metriken und Statistiken zur Qualität der Erfahrung, die von lync Server gesammelt wurden, aufgeteilt in Berichtsabschnitte wie:</span><span class="sxs-lookup"><span data-stu-id="0e3a3-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="0e3a3-105">Anrufinformationen</span><span class="sxs-lookup"><span data-stu-id="0e3a3-105">Call Information</span></span>

  - <span data-ttu-id="0e3a3-106">Gerät und Signalmetrik des Anrufers</span><span class="sxs-lookup"><span data-stu-id="0e3a3-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="0e3a3-107">Gerät und Signalmetrik des Angerufenen</span><span class="sxs-lookup"><span data-stu-id="0e3a3-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="0e3a3-108">Clientereignis des Anrufers</span><span class="sxs-lookup"><span data-stu-id="0e3a3-108">Caller Client Event</span></span>

  - <span data-ttu-id="0e3a3-109">Clientereignis des Angerufenen</span><span class="sxs-lookup"><span data-stu-id="0e3a3-109">Callee Client Event</span></span>

  - <span data-ttu-id="0e3a3-110">Audiodatenstrom (Anrufer zum Angerufenen)</span><span class="sxs-lookup"><span data-stu-id="0e3a3-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="0e3a3-111">Videodatenstrom (Anrufer zum Angerufenen)</span><span class="sxs-lookup"><span data-stu-id="0e3a3-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="0e3a3-112">Audiodatenstrom (Angerufener zum Anrufer)</span><span class="sxs-lookup"><span data-stu-id="0e3a3-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="0e3a3-113">Videodatenstrom (Angerufener zum Anrufer)</span><span class="sxs-lookup"><span data-stu-id="0e3a3-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="0e3a3-p101">Beachten Sie, dass die Kategorien und Metriken in einem bestimmten Bericht zum einen vom Typ der Sitzung und zum anderen vom Typ der Endpunkte abhängen, die in der Sitzung verwendet werden. Bei einem reinen Audioanruf werden keine Metriken für Videodatenströme gemeldet, da der Anruf keinen Videodatenstrom beinhaltete. Entsprechend werden in einem Bericht ggf. zwar Anruferstatistiken, aber keine Statistiken zum Angerufen angezeigt. Dies liegt normalerweise daran, dass der Angerufene kein SIP-kompatibles Gerät verwendet. Endpunkte sind für das Melden von Statistiken am Ende des Anrufs verantwortlich. Ein Mobiltelefon (das SIP oder SIP-Statistiken nicht unterstützt) kann diese Informationen jedoch nicht melden. Wenn Sie jemanden anrufen und diese Person den Anruf auf einem Mobiltelefon entgegennimmt, erhalten Sie keinen Bericht von diesem Mobiltelefon, wenn der Anruf beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="0e3a3-120">Der Anrufdetailbericht ist sehr nützlich, wenn Sie genau feststellen möchten, warum bei einem bestimmten Anruf Probleme in Bezug auf die Medienqualität aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="0e3a3-121">Zugreifen auf den Anrufdetailbericht</span><span class="sxs-lookup"><span data-stu-id="0e3a3-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="0e3a3-122">Auf den Anrufdetailbericht kann von einem der folgenden Berichte aus zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="0e3a3-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="0e3a3-123">Der [Standortbericht in lync Server 2013](lync-server-2013-location-report.md) (durch Klicken auf die Metrik Anruflautstärke oder Prozentsatz armer Anrufe)</span><span class="sxs-lookup"><span data-stu-id="0e3a3-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="0e3a3-124">Der [zusammenfassende Bericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="0e3a3-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="0e3a3-125">Der [Bericht zur Medien Qualitätsvergleiche in lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (durch Klicken auf den [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) und anschließend auf die Metrik Detail).</span><span class="sxs-lookup"><span data-stu-id="0e3a3-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="0e3a3-126">Der [Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf die Metrik Anruflautstärke oder Prozentsatz armer Anrufe)</span><span class="sxs-lookup"><span data-stu-id="0e3a3-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="0e3a3-127">Der [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) (durch Klicken auf die Metrik "Detail")</span><span class="sxs-lookup"><span data-stu-id="0e3a3-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="0e3a3-128">Im Anruf Detail Bericht können Sie auf den [gerätebericht in lync Server 2013](lync-server-2013-device-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="0e3a3-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0e3a3-129">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="0e3a3-129">Capture device</span></span>

  - <span data-ttu-id="0e3a3-130">Darstellungsgerät</span><span class="sxs-lookup"><span data-stu-id="0e3a3-130">Render device</span></span>

<span data-ttu-id="0e3a3-131">Sie können auch auf den Trendbericht über Medienqualität des Servers zugreifen, indem Sie auf die Metrik A/V-Edgeserver klicken.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="0e3a3-132">Optimale Verwendung des Anrufdetailberichts</span><span class="sxs-lookup"><span data-stu-id="0e3a3-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="0e3a3-p102">Der Anrufdetailbericht umfasst normalerweise 250 verschiedene Metriken. Hierzu gehören Zeitstempelabweichung des Mikrofons, Geringer Rauschabstand, Zeit und Nahes Ende zu Echo, Zeit. Wenn Sie nicht genau wissen, was mit diesen Metriken gemessen wird, können Sie mit der Maus auf die Bezeichnung der Metrik zeigen. In den meisten Fällen erscheint dann eine QuickInfo mit einer Metrikbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="0e3a3-p103">Wenn Sie eine Metrik nicht finden können, geben Sie einen Teil der Metrikbezeichnung in das Suchfeld ein, und klicken Sie dann auf Suchen. Wenn Sie beispielsweise die Metrik Geringer Rauschabstand, Zeit nicht finden können, geben Sie "SNR" in das Suchfeld ein, und klicken Sie dann auf Suchen.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="0e3a3-137">Beachten Sie, dass der Bericht nur Informationen zu einem Anruf nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="0e3a3-138">Der Anruf selbst wird nicht aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0e3a3-139">Filter</span><span class="sxs-lookup"><span data-stu-id="0e3a3-139">Filters</span></span>

<span data-ttu-id="0e3a3-p105">Keine. Der Anrufdetailbericht lässt sich nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0e3a3-142">Metriken</span><span class="sxs-lookup"><span data-stu-id="0e3a3-142">Metrics</span></span>

<span data-ttu-id="0e3a3-143">In der folgenden Tabelle werden die Metriken aufgelistet, die im Anrufdetailbericht für jeden Anruf angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="0e3a3-144">Metriken im Anrufdetailbericht</span><span class="sxs-lookup"><span data-stu-id="0e3a3-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e3a3-145">Name</span><span class="sxs-lookup"><span data-stu-id="0e3a3-145">Name</span></span></th>
<th><span data-ttu-id="0e3a3-146">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="0e3a3-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0e3a3-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e3a3-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-148"><strong>PAI des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-149">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-149">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-p106">Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der den Anruf initiiert hat. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-152"><strong>URI des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-153">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-153">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-154">Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-155"><strong>Endpunkt des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-156">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-156">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-157">Das Gerät, mit dem der Anruf ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-158"><strong>Benutzer-Agent des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-159">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-159">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-160">Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-161"><strong>Startzeit des Anrufs</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-162">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-162">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-163">Der Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf ursprünglich getätigt wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-164"><strong>Vermittlungsserver-Umgehungsanruf</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-165">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-165">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-166">Gibt an, ob der Anruf mit einem PSTN-VoIP-Gateway oder einer qualifizierten IP-Nebenstellenanlage verbunden wurde, ohne dass er über den Vermittlungsserver geleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-167"><strong>Betriebssystem des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-168">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-168">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-169">Das Betriebssystem auf dem Computer des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-170"><strong>CPU des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-171">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-171">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-172">Die CPU, die im Computer des Benutzers installiert ist, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-173"><strong>Nummer des CPU-Kerns des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-174">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-174">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-175">Die Nummer des Prozessors in dem Computer des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-176"><strong>CPU-Geschwindigkeit des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-177">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-177">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-178">Die Taktfrequenz der CPU des Computers des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-179"><strong>Virtualisierung der CPU des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-180">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-180">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-181">Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-182"><strong>PAI des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-183">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-183">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-p107">Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der zur Teilnahme an dem Anruf eingeladen wurde. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-186"><strong>URI des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-187">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-187">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-188">Die SIP-Adresse des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-189"><strong>Endpunkt des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-190">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-190">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-191">Das Gerät, mit dem der Anruf angenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-192"><strong>Benutzer-Agent des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-193">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-193">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-194">Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf angenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-195"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-196">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-196">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-197">Die Dauer des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-198"><strong>Vermittlungsserver-Warnungskennzeichen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-199">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-199">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-200">Eine Warnung, die ausgegeben wird, wenn der Vermittlungsserver umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-201"><strong>Betriebssystem des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-202">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-202">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-203">Das Betriebssystem auf dem Computer des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-204"><strong>CPU des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-205">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-205">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-206">Die CPU, die im Computer des Benutzers installiert ist, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-207"><strong>Nummer des CPU-Kerns des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-208">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-208">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-209">Die Nummer des Prozessors in dem Computer des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3a3-210"><strong>CPU-Geschwindigkeit des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-211">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-211">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-212">Die Taktfrequenz der CPU des Computers des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3a3-213"><strong>Virtualisierung der CPU des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="0e3a3-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3a3-214">Nein</span><span class="sxs-lookup"><span data-stu-id="0e3a3-214">No</span></span></p></td>
<td><p><span data-ttu-id="0e3a3-215">Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e3a3-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

