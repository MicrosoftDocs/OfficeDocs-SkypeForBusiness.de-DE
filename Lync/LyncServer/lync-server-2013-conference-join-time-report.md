---
title: 'Lync Server 2013: Bericht zur Konferenzbeitritts Zeit'
description: 'Lync Server 2013: Bericht zur Konferenzbeitritts Zeit.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd4aa5d21a8109a323bb953c7196f43715d51413
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542791"
---
# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="fef93-103">Bericht zur Konferenzbeitritts Zeit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef93-103">Conference Join Time Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef93-104">_**Letztes Änderungsstand des Themas:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="fef93-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="fef93-p101">Mit dem Bericht über Zeitpunkt des Konferenzbeitritts können Sie bestimmen, wie lange die Benutzer benötigen, um einer Konferenz beizutreten. Dieser Bericht enthält die durchschnittliche Zeit für den Beitritt (in Millisekunden) sowie eine Übersicht darüber, wie viele Benutzer in maximal 2 Sekunden einer Konferenz beitreten konnten, wie viele Benutzer zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten usw.</span><span class="sxs-lookup"><span data-stu-id="fef93-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="fef93-107">Zugriff auf den Bericht über Zeitpunkt des Konferenzbeitritts</span><span class="sxs-lookup"><span data-stu-id="fef93-107">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="fef93-108">Auf den Bericht über Zeitpunkt des Konferenzbeitritts greifen Sie auf der Startseite Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="fef93-108">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fef93-109">Filter</span><span class="sxs-lookup"><span data-stu-id="fef93-109">Filters</span></span>

<span data-ttu-id="fef93-p102">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Zeitpunkt des Konferenzbeitritts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fef93-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="fef93-112">Filter im Bericht über Zeitpunkt des Konferenzbeitritts</span><span class="sxs-lookup"><span data-stu-id="fef93-112">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef93-113">Name</span><span class="sxs-lookup"><span data-stu-id="fef93-113">Name</span></span></th>
<th><span data-ttu-id="fef93-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fef93-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef93-115"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-115"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-p103">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="fef93-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fef93-118">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="fef93-118">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fef93-p104">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="fef93-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fef93-121">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fef93-121">7/7/2012</span></span></p>
<p><span data-ttu-id="fef93-122">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="fef93-122">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fef93-123">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fef93-123">7/3/2012</span></span></p>
<p><span data-ttu-id="fef93-124">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="fef93-124">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef93-125"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-125"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-p105">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="fef93-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fef93-128">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="fef93-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fef93-p106">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="fef93-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fef93-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fef93-131">7/7/2012</span></span></p>
<p><span data-ttu-id="fef93-132">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="fef93-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fef93-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fef93-133">7/3/2012</span></span></p>
<p><span data-ttu-id="fef93-134">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="fef93-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef93-135"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-135"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-p107">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="fef93-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fef93-138">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="fef93-138">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fef93-139">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="fef93-139">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fef93-140">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="fef93-140">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fef93-141">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="fef93-141">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="fef93-p108">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="fef93-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef93-144"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-144"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-p109">Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fef93-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef93-148"><strong>Konferenzsitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-148"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-p110">Der Sitzungstyp. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fef93-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="fef93-151">Alle</span><span class="sxs-lookup"><span data-stu-id="fef93-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="fef93-152">Fokussitzungen (der Schwerpunkt liegt auf der zentralen Richtlinie und dem Status-Manager für Onlinebesprechungen und koordiniert alle Aspekte einer Konferenz.</span><span class="sxs-lookup"><span data-stu-id="fef93-152">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="fef93-153">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="fef93-153">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="fef93-154">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="fef93-154">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="fef93-p111">Wenn Sie [Alle] auswählen, wird die Gesamtzeit für den Konferenzbeitritt oben im Bericht angezeigt. Beachten Sie, dass diese Gesamtwerte nur für Konferenzen sind, die mit Microsoft Exchange oder Microsoft Outlook geplant wurden.</span><span class="sxs-lookup"><span data-stu-id="fef93-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="fef93-157">Metriken</span><span class="sxs-lookup"><span data-stu-id="fef93-157">Metrics</span></span>

<span data-ttu-id="fef93-158">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Zeitpunkt des Konferenzbeitritts angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fef93-158">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="fef93-159">Metriken im Bericht über Zeitpunkt des Konferenzbeitritts</span><span class="sxs-lookup"><span data-stu-id="fef93-159">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef93-160">Name</span><span class="sxs-lookup"><span data-stu-id="fef93-160">Name</span></span></th>
<th><span data-ttu-id="fef93-161">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="fef93-161">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef93-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fef93-162">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef93-163"><strong>Date</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-163"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="fef93-164">Der eigentliche Name dieser Metrik hängt vom ausgewählten Intervall ab.</span><span class="sxs-lookup"><span data-stu-id="fef93-164">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="fef93-165">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-165">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-166">Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</span><span class="sxs-lookup"><span data-stu-id="fef93-166">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef93-167"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-167"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-168">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-168">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-169">Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="fef93-169">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef93-170"><strong>Mittelwert (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-170"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-171">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-171">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-172">Die durchschnittliche Zeit (in Millisekunden), die die Teilnehmer für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="fef93-172">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef93-173"><strong>Sitzungen &lt; 2 Sekunden, Volumen</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-173"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-174">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-174">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-175">Die Anzahl der Teilnehmer, die der Konferenz in weniger als 2 Sekunden beitreten konnten.</span><span class="sxs-lookup"><span data-stu-id="fef93-175">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef93-176"><strong>Sitzungen &lt; 2 Sekunden, Prozentsatz</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-176"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-177">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-177">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef93-178"><strong>Sitzungen < 2-5 Sekunden, Anzahl</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-178"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-179">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-179">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-180">Die Anzahl der Teilnehmer, die zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="fef93-180">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef93-181"><strong>Sitzungen < 2-5 Sekunden, Prozentsatz</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-181"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-182">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-182">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-183">Der Prozentsatz der Gesamtteilnehmer, die zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="fef93-183">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef93-184"><strong>Sitzungen < 5-10 Sekunden, Anzahl</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-184"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-185">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-185">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-186">Die Anzahl der Teilnehmer, die zwischen 5 und 10 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="fef93-186">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef93-187"><strong>Sitzungen < 5-10 Sekunden, Prozentsatz</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-187"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-188">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-188">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-189">Der Prozentsatz der Gesamtteilnehmer, die zwischen 5 und 10 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="fef93-189">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef93-190"><strong>Sitzungen &gt; 10 Sekunden, Volumen</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-190"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-191">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-191">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-192">Die Anzahl der Teilnehmer, die mehr als 10 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="fef93-192">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef93-193"><strong>Sitzungen &gt; 10 Sekunden, Prozentsatz</strong></span><span class="sxs-lookup"><span data-stu-id="fef93-193"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="fef93-194">Nein</span><span class="sxs-lookup"><span data-stu-id="fef93-194">No</span></span></p></td>
<td><p><span data-ttu-id="fef93-195">Der Prozentsatz der Gesamtteilnehmer, die mehr als 10 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="fef93-195">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

