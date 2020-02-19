---
title: 'Lync Server 2013: konferenzaktivitätsbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93113f3167cf16733f5c7ab51247dcb57f1a118c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="7f95e-102">Konferenzaktivitätsbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f95e-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f95e-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7f95e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7f95e-104">Mit dem Konferenzaktivitätsbericht können Fragen wie diese leicht beantwortet werden: Wie viele Konferenzen werden täglich gehalten, und wann werden diese Konferenzen gehalten?</span><span class="sxs-lookup"><span data-stu-id="7f95e-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="7f95e-105">Derartige Informationen sind an sich nützlich und können außerdem für die Problembehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f95e-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="7f95e-106">Nehmen wir z. B. an, dass sich Benutzer darüber beschweren, dass das Netzwerk mittags besonders langsam zu sein scheint.</span><span class="sxs-lookup"><span data-stu-id="7f95e-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="7f95e-107">Ein kurzer Blick auf die Aktivitätsberichte der Konferenz kann einen möglichen Grund vorschlagen: in den Stunden 10:00 Uhr und 2:00 Uhr und dann zu jeder anderen Zeit werden weit mehr Konferenzen geplant.</span><span class="sxs-lookup"><span data-stu-id="7f95e-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="7f95e-108">Verursacht das langsame Netzwerk Probleme, können Sie Benutzern empfehlen, Konferenzen zu Tageszeiten mit weniger Datenauslastung abzuhalten.</span><span class="sxs-lookup"><span data-stu-id="7f95e-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="7f95e-109">Zugreifen auf den Konferenzaktivitätsbericht</span><span class="sxs-lookup"><span data-stu-id="7f95e-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="7f95e-110">Der Zugriff auf den Bericht über die Konferenz Aktivität erfolgt über den [Konferenz Zusammenfassungsbericht in lync Server 2013](lync-server-2013-conference-summary-report.md) , indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="7f95e-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="7f95e-111">Konferenzen insgesamt</span><span class="sxs-lookup"><span data-stu-id="7f95e-111">Total conferences</span></span>

  - <span data-ttu-id="7f95e-112">Teilnehmer insgesamt</span><span class="sxs-lookup"><span data-stu-id="7f95e-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="7f95e-113">Optimales Verwenden des Konferenzaktivitätsberichts</span><span class="sxs-lookup"><span data-stu-id="7f95e-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="7f95e-p102">Standardmäßig wird im Konferenzaktivitätsbericht die Gesamtanzahl der Konferenzen für den angegebenen Zeitraum (z. B. die Gesamtanzahl der Konferenzen pro Tag oder die Gesamtanzahl der Konferenzen pro Stunde eines Tages). Sie können jedoch auch die Gesamtanzahl der Teilnehmer für den Zeitraum oder die Gesamtanzahl der Teilnehmerminuten anzeigen. Klicken Sie dazu auf die Schaltfläche zum Ein- und Ausblenden der Parameter, um die Filteroptionen anzuzeigen, und wählen Sie dann eine der folgenden Optionen aus der Dropdownliste "Bericht nach" aus:</span><span class="sxs-lookup"><span data-stu-id="7f95e-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="7f95e-117">Teilnehmeranzahl</span><span class="sxs-lookup"><span data-stu-id="7f95e-117">Participant count</span></span>

  - <span data-ttu-id="7f95e-118">Teilnehmerminuten</span><span class="sxs-lookup"><span data-stu-id="7f95e-118">Participant minutes</span></span>

  - <span data-ttu-id="7f95e-119">Konferenzanzahl</span><span class="sxs-lookup"><span data-stu-id="7f95e-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7f95e-120">Filter</span><span class="sxs-lookup"><span data-stu-id="7f95e-120">Filters</span></span>

<span data-ttu-id="7f95e-p103">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Konferenzaktivitätsbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7f95e-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="7f95e-123">Filter im Konferenzaktivitätsbericht</span><span class="sxs-lookup"><span data-stu-id="7f95e-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f95e-124">Name</span><span class="sxs-lookup"><span data-stu-id="7f95e-124">Name</span></span></th>
<th><span data-ttu-id="7f95e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f95e-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f95e-126"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-p104">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="7f95e-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7f95e-129">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="7f95e-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7f95e-p105">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="7f95e-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7f95e-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7f95e-132">7/7/2012</span></span></p>
<p><span data-ttu-id="7f95e-133">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="7f95e-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7f95e-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7f95e-134">7/3/2012</span></span></p>
<p><span data-ttu-id="7f95e-135">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="7f95e-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f95e-136"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-p106">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="7f95e-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7f95e-139">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="7f95e-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7f95e-p107">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="7f95e-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7f95e-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7f95e-142">7/7/2012</span></span></p>
<p><span data-ttu-id="7f95e-143">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="7f95e-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7f95e-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7f95e-144">7/3/2012</span></span></p>
<p><span data-ttu-id="7f95e-145">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="7f95e-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f95e-146"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-p108">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7f95e-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7f95e-149">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="7f95e-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7f95e-150">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="7f95e-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7f95e-151">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="7f95e-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7f95e-152">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="7f95e-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7f95e-p109">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall "Täglich" mit dem Startdatum 07.07.2012 und dem Enddatum 28.02.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="7f95e-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f95e-155"><strong>Bericht nach:</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-p110">Gibt die Werte an, die in dem Bericht verwendet werden sollen. Sie können einen der folgenden Werte auswählen:</span><span class="sxs-lookup"><span data-stu-id="7f95e-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7f95e-158">Teilnehmeranzahl</span><span class="sxs-lookup"><span data-stu-id="7f95e-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="7f95e-159">Teilnehmerminuten</span><span class="sxs-lookup"><span data-stu-id="7f95e-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="7f95e-160">Konferenzanzahl</span><span class="sxs-lookup"><span data-stu-id="7f95e-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="7f95e-161">Metriken für Konferenzen nach Pool</span><span class="sxs-lookup"><span data-stu-id="7f95e-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="7f95e-162">In der folgenden Tabelle werden die Metriken aufgelistet, die im Konferenzaktivitätsbericht für jeden Pool angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f95e-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="7f95e-163">Metriken für Konferenzen nach Pool</span><span class="sxs-lookup"><span data-stu-id="7f95e-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f95e-164">Name</span><span class="sxs-lookup"><span data-stu-id="7f95e-164">Name</span></span></th>
<th><span data-ttu-id="7f95e-165">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="7f95e-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f95e-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f95e-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f95e-167"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-168">Nein</span><span class="sxs-lookup"><span data-stu-id="7f95e-168">No</span></span></p></td>
<td><p><span data-ttu-id="7f95e-169">Name des in der Konferenz verwendeten Registrierungspools oder Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="7f95e-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f95e-170"><strong>Datum/Uhrzeit</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-171">Nein</span><span class="sxs-lookup"><span data-stu-id="7f95e-171">No</span></span></p></td>
<td><p><span data-ttu-id="7f95e-172">Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</span><span class="sxs-lookup"><span data-stu-id="7f95e-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f95e-173"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-174">Nein</span><span class="sxs-lookup"><span data-stu-id="7f95e-174">No</span></span></p></td>
<td><p><span data-ttu-id="7f95e-175">Gesamtzahl der Teilnehmer, der Teilnehmerminuten oder der Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="7f95e-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="7f95e-176">Metriken für Konferenzen nach Servertyp</span><span class="sxs-lookup"><span data-stu-id="7f95e-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="7f95e-177">In der folgenden Tabelle werden die Metriken aufgelistet, die im Konferenzaktivitätsbericht für jeden Servertyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f95e-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="7f95e-178">Metriken für Konferenzen nach Servertyp</span><span class="sxs-lookup"><span data-stu-id="7f95e-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f95e-179">Name</span><span class="sxs-lookup"><span data-stu-id="7f95e-179">Name</span></span></th>
<th><span data-ttu-id="7f95e-180">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="7f95e-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f95e-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f95e-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f95e-182"><strong>Konferenzservertyp</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-183">Nein</span><span class="sxs-lookup"><span data-stu-id="7f95e-183">No</span></span></p></td>
<td><p><span data-ttu-id="7f95e-184">Der Typ des Servers, der in der Konferenz verwendet wird, in der Regel einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="7f95e-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7f95e-185">Webkonferenzserver</span><span class="sxs-lookup"><span data-stu-id="7f95e-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="7f95e-186">Sofortnachrichten-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="7f95e-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="7f95e-187">Telefonkonferenzserver</span><span class="sxs-lookup"><span data-stu-id="7f95e-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="7f95e-188">A/V-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="7f95e-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="7f95e-189">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="7f95e-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f95e-190"><strong>Datum/Uhrzeit</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-191">Nein</span><span class="sxs-lookup"><span data-stu-id="7f95e-191">No</span></span></p></td>
<td><p><span data-ttu-id="7f95e-192">Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</span><span class="sxs-lookup"><span data-stu-id="7f95e-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f95e-193"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="7f95e-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="7f95e-194">Nein</span><span class="sxs-lookup"><span data-stu-id="7f95e-194">No</span></span></p></td>
<td><p><span data-ttu-id="7f95e-195">Gesamtzahl der Teilnehmer, der Teilnehmerminuten oder der Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="7f95e-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

