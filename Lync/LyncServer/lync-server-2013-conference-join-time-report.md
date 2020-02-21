---
title: 'Lync Server 2013: Bericht zur Konferenzbeitritts Zeit'
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
ms.openlocfilehash: 76388655fc8ed893e09b192ae24c7807b46f9f6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="36564-102">Bericht zur Konferenzbeitritts Zeit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36564-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36564-103">_**Letztes Änderungsstand des Themas:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="36564-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="36564-p101">Mit dem Bericht über Zeitpunkt des Konferenzbeitritts können Sie bestimmen, wie lange die Benutzer benötigen, um einer Konferenz beizutreten. Dieser Bericht enthält die durchschnittliche Zeit für den Beitritt (in Millisekunden) sowie eine Übersicht darüber, wie viele Benutzer in maximal 2 Sekunden einer Konferenz beitreten konnten, wie viele Benutzer zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten usw.</span><span class="sxs-lookup"><span data-stu-id="36564-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="36564-106">Zugriff auf den Bericht über Zeitpunkt des Konferenzbeitritts</span><span class="sxs-lookup"><span data-stu-id="36564-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="36564-107">Auf den Bericht über Zeitpunkt des Konferenzbeitritts greifen Sie auf der Startseite Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="36564-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="36564-108">Filter</span><span class="sxs-lookup"><span data-stu-id="36564-108">Filters</span></span>

<span data-ttu-id="36564-p102">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Zeitpunkt des Konferenzbeitritts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="36564-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="36564-111">Filter im Bericht über Zeitpunkt des Konferenzbeitritts</span><span class="sxs-lookup"><span data-stu-id="36564-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36564-112">Name</span><span class="sxs-lookup"><span data-stu-id="36564-112">Name</span></span></th>
<th><span data-ttu-id="36564-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36564-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36564-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="36564-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-p103">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="36564-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="36564-117">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="36564-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="36564-p104">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="36564-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="36564-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="36564-120">7/7/2012</span></span></p>
<p><span data-ttu-id="36564-121">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="36564-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="36564-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="36564-122">7/3/2012</span></span></p>
<p><span data-ttu-id="36564-123">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="36564-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36564-124"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="36564-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-p105">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="36564-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="36564-127">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="36564-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="36564-p106">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="36564-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="36564-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="36564-130">7/7/2012</span></span></p>
<p><span data-ttu-id="36564-131">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="36564-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="36564-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="36564-132">7/3/2012</span></span></p>
<p><span data-ttu-id="36564-133">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="36564-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36564-134"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="36564-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-p107">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="36564-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="36564-137">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="36564-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="36564-138">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="36564-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="36564-139">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="36564-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="36564-140">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="36564-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="36564-p108">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="36564-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36564-143"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="36564-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-p109">Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="36564-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36564-147"><strong>Konferenzsitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="36564-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-p110">Der Sitzungstyp. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="36564-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="36564-150">Alle</span><span class="sxs-lookup"><span data-stu-id="36564-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="36564-151">Fokussitzungen (der Schwerpunkt liegt auf der zentralen Richtlinie und dem Status-Manager für Onlinebesprechungen und koordiniert alle Aspekte einer Konferenz.</span><span class="sxs-lookup"><span data-stu-id="36564-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="36564-152">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="36564-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="36564-153">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="36564-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="36564-p111">Wenn Sie [Alle] auswählen, wird die Gesamtzeit für den Konferenzbeitritt oben im Bericht angezeigt. Beachten Sie, dass diese Gesamtwerte nur für Konferenzen sind, die mit Microsoft Exchange oder Microsoft Outlook geplant wurden.</span><span class="sxs-lookup"><span data-stu-id="36564-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="36564-156">Metriken</span><span class="sxs-lookup"><span data-stu-id="36564-156">Metrics</span></span>

<span data-ttu-id="36564-157">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Zeitpunkt des Konferenzbeitritts angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36564-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="36564-158">Metriken im Bericht über Zeitpunkt des Konferenzbeitritts</span><span class="sxs-lookup"><span data-stu-id="36564-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36564-159">Name</span><span class="sxs-lookup"><span data-stu-id="36564-159">Name</span></span></th>
<th><span data-ttu-id="36564-160">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="36564-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="36564-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36564-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36564-162"><strong>Date</strong></span><span class="sxs-lookup"><span data-stu-id="36564-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="36564-163">Der eigentliche Name dieser Metrik hängt vom ausgewählten Intervall ab.</span><span class="sxs-lookup"><span data-stu-id="36564-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="36564-164">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-164">No</span></span></p></td>
<td><p><span data-ttu-id="36564-165">Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</span><span class="sxs-lookup"><span data-stu-id="36564-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36564-166"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="36564-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-167">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-167">No</span></span></p></td>
<td><p><span data-ttu-id="36564-168">Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="36564-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36564-169"><strong>Mittelwert (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="36564-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-170">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-170">No</span></span></p></td>
<td><p><span data-ttu-id="36564-171">Die durchschnittliche Zeit (in Millisekunden), die die Teilnehmer für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="36564-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36564-172"><strong>Sitzungen &lt; 2 Sekunden, Volumen</strong></span><span class="sxs-lookup"><span data-stu-id="36564-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-173">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-173">No</span></span></p></td>
<td><p><span data-ttu-id="36564-174">Die Anzahl der Teilnehmer, die der Konferenz in weniger als 2 Sekunden beitreten konnten.</span><span class="sxs-lookup"><span data-stu-id="36564-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36564-175"><strong>Sitzungen &lt; 2 Sekunden, Prozentsatz</strong></span><span class="sxs-lookup"><span data-stu-id="36564-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-176">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36564-177"><strong>Sitzungen < 2-5 Sekunden, Anzahl</strong></span><span class="sxs-lookup"><span data-stu-id="36564-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-178">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-178">No</span></span></p></td>
<td><p><span data-ttu-id="36564-179">Die Anzahl der Teilnehmer, die zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="36564-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36564-180"><strong>Sitzungen < 2-5 Sekunden, Prozentsatz</strong></span><span class="sxs-lookup"><span data-stu-id="36564-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-181">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-181">No</span></span></p></td>
<td><p><span data-ttu-id="36564-182">Der Prozentsatz der Gesamtteilnehmer, die zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="36564-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36564-183"><strong>Sitzungen < 5-10 Sekunden, Anzahl</strong></span><span class="sxs-lookup"><span data-stu-id="36564-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-184">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-184">No</span></span></p></td>
<td><p><span data-ttu-id="36564-185">Die Anzahl der Teilnehmer, die zwischen 5 und 10 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="36564-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36564-186"><strong>Sitzungen < 5-10 Sekunden, Prozentsatz</strong></span><span class="sxs-lookup"><span data-stu-id="36564-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-187">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-187">No</span></span></p></td>
<td><p><span data-ttu-id="36564-188">Der Prozentsatz der Gesamtteilnehmer, die zwischen 5 und 10 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="36564-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36564-189"><strong>Sitzungen &gt; 10 Sekunden, Volumen</strong></span><span class="sxs-lookup"><span data-stu-id="36564-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-190">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-190">No</span></span></p></td>
<td><p><span data-ttu-id="36564-191">Die Anzahl der Teilnehmer, die mehr als 10 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="36564-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36564-192"><strong>Sitzungen &gt; 10 Sekunden, Prozentsatz</strong></span><span class="sxs-lookup"><span data-stu-id="36564-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="36564-193">Nein</span><span class="sxs-lookup"><span data-stu-id="36564-193">No</span></span></p></td>
<td><p><span data-ttu-id="36564-194">Der Prozentsatz der Gesamtteilnehmer, die mehr als 10 Sekunden für den Konferenzbeitritt benötigten.</span><span class="sxs-lookup"><span data-stu-id="36564-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

