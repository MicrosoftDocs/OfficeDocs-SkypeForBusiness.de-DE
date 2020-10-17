---
title: 'Lync Server 2013: Anruf Detail Bericht'
description: 'Lync Server 2013: Anruf Detail Bericht.'
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
ms.openlocfilehash: d72ae6c1c1ec869041eee5b0dc35941c33609710
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561771"
---
# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="d0065-103">Anruf Detail Bericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0065-103">Call Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0065-104">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d0065-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d0065-105">Der Anruf Detail Bericht bietet einen detaillierten Überblick über einen einzelnen Anruf; der Bericht enthält nahezu alle Metriken und Statistiken zur Qualität der Erfahrung, die von lync Server gesammelt wurden, aufgeteilt in Berichtsabschnitte wie:</span><span class="sxs-lookup"><span data-stu-id="d0065-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="d0065-106">Anrufinformationen</span><span class="sxs-lookup"><span data-stu-id="d0065-106">Call Information</span></span>

  - <span data-ttu-id="d0065-107">Gerät und Signalmetrik des Anrufers</span><span class="sxs-lookup"><span data-stu-id="d0065-107">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="d0065-108">Gerät und Signalmetrik des Angerufenen</span><span class="sxs-lookup"><span data-stu-id="d0065-108">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="d0065-109">Clientereignis des Anrufers</span><span class="sxs-lookup"><span data-stu-id="d0065-109">Caller Client Event</span></span>

  - <span data-ttu-id="d0065-110">Clientereignis des Angerufenen</span><span class="sxs-lookup"><span data-stu-id="d0065-110">Callee Client Event</span></span>

  - <span data-ttu-id="d0065-111">Audiodatenstrom (Anrufer zum Angerufenen)</span><span class="sxs-lookup"><span data-stu-id="d0065-111">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="d0065-112">Videodatenstrom (Anrufer zum Angerufenen)</span><span class="sxs-lookup"><span data-stu-id="d0065-112">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="d0065-113">Audiodatenstrom (Angerufener zum Anrufer)</span><span class="sxs-lookup"><span data-stu-id="d0065-113">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="d0065-114">Videodatenstrom (Angerufener zum Anrufer)</span><span class="sxs-lookup"><span data-stu-id="d0065-114">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="d0065-p101">Beachten Sie, dass die Kategorien und Metriken in einem bestimmten Bericht zum einen vom Typ der Sitzung und zum anderen vom Typ der Endpunkte abhängen, die in der Sitzung verwendet werden. Bei einem reinen Audioanruf werden keine Metriken für Videodatenströme gemeldet, da der Anruf keinen Videodatenstrom beinhaltete. Entsprechend werden in einem Bericht ggf. zwar Anruferstatistiken, aber keine Statistiken zum Angerufen angezeigt. Dies liegt normalerweise daran, dass der Angerufene kein SIP-kompatibles Gerät verwendet. Endpunkte sind für das Melden von Statistiken am Ende des Anrufs verantwortlich. Ein Mobiltelefon (das SIP oder SIP-Statistiken nicht unterstützt) kann diese Informationen jedoch nicht melden. Wenn Sie jemanden anrufen und diese Person den Anruf auf einem Mobiltelefon entgegennimmt, erhalten Sie keinen Bericht von diesem Mobiltelefon, wenn der Anruf beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0065-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="d0065-121">Der Anrufdetailbericht ist sehr nützlich, wenn Sie genau feststellen möchten, warum bei einem bestimmten Anruf Probleme in Bezug auf die Medienqualität aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="d0065-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="d0065-122">Zugreifen auf den Anrufdetailbericht</span><span class="sxs-lookup"><span data-stu-id="d0065-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="d0065-123">Auf den Anrufdetailbericht kann von einem der folgenden Berichte aus zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="d0065-123">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="d0065-124">Der [Standortbericht in lync Server 2013](lync-server-2013-location-report.md) (durch Klicken auf die Metrik Anruflautstärke oder Prozentsatz armer Anrufe)</span><span class="sxs-lookup"><span data-stu-id="d0065-124">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="d0065-125">Der [zusammenfassende Bericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")</span><span class="sxs-lookup"><span data-stu-id="d0065-125">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="d0065-126">Der [Bericht zur Medien Qualitätsvergleiche in lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (durch Klicken auf den [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) und anschließend auf die Metrik Detail).</span><span class="sxs-lookup"><span data-stu-id="d0065-126">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="d0065-127">Der [Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf die Metrik Anruflautstärke oder Prozentsatz armer Anrufe)</span><span class="sxs-lookup"><span data-stu-id="d0065-127">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="d0065-128">Der [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) (durch Klicken auf die Metrik "Detail")</span><span class="sxs-lookup"><span data-stu-id="d0065-128">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="d0065-129">Im Anruf Detail Bericht können Sie auf den [gerätebericht in lync Server 2013](lync-server-2013-device-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="d0065-129">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d0065-130">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="d0065-130">Capture device</span></span>

  - <span data-ttu-id="d0065-131">Darstellungsgerät</span><span class="sxs-lookup"><span data-stu-id="d0065-131">Render device</span></span>

<span data-ttu-id="d0065-132">Sie können auch auf den Trendbericht über Medienqualität des Servers zugreifen, indem Sie auf die Metrik A/V-Edgeserver klicken.</span><span class="sxs-lookup"><span data-stu-id="d0065-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="d0065-133">Optimale Verwendung des Anrufdetailberichts</span><span class="sxs-lookup"><span data-stu-id="d0065-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="d0065-p102">Der Anrufdetailbericht umfasst normalerweise 250 verschiedene Metriken. Hierzu gehören Zeitstempelabweichung des Mikrofons, Geringer Rauschabstand, Zeit und Nahes Ende zu Echo, Zeit. Wenn Sie nicht genau wissen, was mit diesen Metriken gemessen wird, können Sie mit der Maus auf die Bezeichnung der Metrik zeigen. In den meisten Fällen erscheint dann eine QuickInfo mit einer Metrikbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="d0065-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="d0065-p103">Wenn Sie eine Metrik nicht finden können, geben Sie einen Teil der Metrikbezeichnung in das Suchfeld ein, und klicken Sie dann auf Suchen. Wenn Sie beispielsweise die Metrik Geringer Rauschabstand, Zeit nicht finden können, geben Sie "SNR" in das Suchfeld ein, und klicken Sie dann auf Suchen.</span><span class="sxs-lookup"><span data-stu-id="d0065-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="d0065-138">Beachten Sie, dass der Bericht nur Informationen zu einem Anruf nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="d0065-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="d0065-139">Der Anruf selbst wird nicht aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d0065-139">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d0065-140">Filter</span><span class="sxs-lookup"><span data-stu-id="d0065-140">Filters</span></span>

<span data-ttu-id="d0065-p105">Keine. Der Anrufdetailbericht lässt sich nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="d0065-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d0065-143">Metriken</span><span class="sxs-lookup"><span data-stu-id="d0065-143">Metrics</span></span>

<span data-ttu-id="d0065-144">In der folgenden Tabelle werden die Metriken aufgelistet, die im Anrufdetailbericht für jeden Anruf angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d0065-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="d0065-145">Metriken im Anrufdetailbericht</span><span class="sxs-lookup"><span data-stu-id="d0065-145">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0065-146">Name</span><span class="sxs-lookup"><span data-stu-id="d0065-146">Name</span></span></th>
<th><span data-ttu-id="d0065-147">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="d0065-147">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d0065-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0065-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0065-149"><strong>PAI des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-149"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-150">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-150">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-p106">Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der den Anruf initiiert hat. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="d0065-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-153"><strong>URI des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-153"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-154">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-154">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-155">Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="d0065-155">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-156"><strong>Endpunkt des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-156"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-157">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-157">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-158">Das Gerät, mit dem der Anruf ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-158">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-159"><strong>Benutzer-Agent des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-159"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-160">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-160">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-161">Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-161">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-162"><strong>Startzeit des Anrufs</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-162"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-163">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-163">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-164">Der Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf ursprünglich getätigt wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-164">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-165"><strong>Vermittlungsserver-Umgehungsanruf</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-165"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-166">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-166">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-167">Gibt an, ob der Anruf mit einem PSTN-VoIP-Gateway oder einer qualifizierten IP-Nebenstellenanlage verbunden wurde, ohne dass er über den Vermittlungsserver geleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-168"><strong>Betriebssystem des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-168"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-169">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-169">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-170">Das Betriebssystem auf dem Computer des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d0065-170">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-171"><strong>CPU des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-171"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-172">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-172">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-173">Die CPU, die im Computer des Benutzers installiert ist, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="d0065-173">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-174"><strong>Nummer des CPU-Kerns des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-174"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-175">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-175">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-176">Die Nummer des Prozessors in dem Computer des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="d0065-176">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-177"><strong>CPU-Geschwindigkeit des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-177"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-178">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-178">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-179">Die Taktfrequenz der CPU des Computers des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="d0065-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-180"><strong>Virtualisierung der CPU des Anrufers</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-180"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-181">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-181">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-182">Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="d0065-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-183"><strong>PAI des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-183"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-184">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-184">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-p107">Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der zur Teilnahme an dem Anruf eingeladen wurde. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="d0065-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-187"><strong>URI des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-187"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-188">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-188">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-189">Die SIP-Adresse des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-189">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-190"><strong>Endpunkt des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-190"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-191">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-191">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-192">Das Gerät, mit dem der Anruf angenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-192">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-193"><strong>Benutzer-Agent des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-193"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-194">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-194">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-195">Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf angenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-195">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-196"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-196"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-197">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-197">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-198">Die Dauer des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d0065-198">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-199"><strong>Vermittlungsserver-Warnungskennzeichen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-199"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-200">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-200">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-201">Eine Warnung, die ausgegeben wird, wenn der Vermittlungsserver umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-201">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-202"><strong>Betriebssystem des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-202"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-203">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-203">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-204">Das Betriebssystem auf dem Computer des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-204">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-205"><strong>CPU des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-205"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-206">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-206">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-207">Die CPU, die im Computer des Benutzers installiert ist, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-207">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-208"><strong>Nummer des CPU-Kerns des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-208"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-209">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-209">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-210">Die Nummer des Prozessors in dem Computer des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-210">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0065-211"><strong>CPU-Geschwindigkeit des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-211"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-212">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-212">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-213">Die Taktfrequenz der CPU des Computers des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-213">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0065-214"><strong>Virtualisierung der CPU des Angerufenen</strong></span><span class="sxs-lookup"><span data-stu-id="d0065-214"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="d0065-215">Nein</span><span class="sxs-lookup"><span data-stu-id="d0065-215">No</span></span></p></td>
<td><p><span data-ttu-id="d0065-216">Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0065-216">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

