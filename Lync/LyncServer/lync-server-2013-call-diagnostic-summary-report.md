---
title: 'Lync Server 2013: zusammenfassender Anruf Diagnosebericht'
description: 'Lync Server 2013: zusammenfassender Anruf Diagnosebericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b444a176c06974a9eb9827006e078c17b54047a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561701"
---
# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="4701b-103">Zusammenfassender Anruf Diagnosebericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4701b-103">Call Diagnostic Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4701b-104">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="4701b-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="4701b-p101">Der zusammenfassende Anrufdiagnosebericht bietet eine Gesamtübersicht zu fehlgeschlagenen Peer-zu-Peer- und Konferenzsitzungen. Der Bericht zeigt die Gesamtfehlerrate für beide Sitzungstypen und detaillierte Fehlerinformationen nach Sitzungsmodalitätstyp:</span><span class="sxs-lookup"><span data-stu-id="4701b-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="4701b-107">Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="4701b-107">Instant messaging</span></span>

  - <span data-ttu-id="4701b-108">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="4701b-108">Application sharing</span></span>

  - <span data-ttu-id="4701b-109">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="4701b-109">File transfer</span></span>

  - <span data-ttu-id="4701b-110">Audio</span><span class="sxs-lookup"><span data-stu-id="4701b-110">Audio</span></span>

  - <span data-ttu-id="4701b-111">Video</span><span class="sxs-lookup"><span data-stu-id="4701b-111">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="4701b-112">Zugriff auf den zusammenfassenden Anrufdiagnosebericht</span><span class="sxs-lookup"><span data-stu-id="4701b-112">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="4701b-113">Der Zugriff auf den zusammenfassenden Anrufdiagnosebericht erfolgt auf der Startseite für Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="4701b-113">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="4701b-114">Im zusammenfassenden Bericht "Anruf Diagnose" können Sie auf den [Diagnosebericht über Peer-to-Peer-Aktivitäten in lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) zugreifen, indem Sie im Abschnitt Peer-to-Peer-Sitzungszusammenfassung des Berichts auf die Metrik für Fehlerrate klicken.</span><span class="sxs-lookup"><span data-stu-id="4701b-114">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="4701b-115">Sie können auch auf den [Konferenz Diagnosebericht in lync Server 2013](lync-server-2013-conference-diagnostic-report.md) zugreifen, indem Sie auf eine der folgenden Konferenz Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="4701b-115">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="4701b-116">Sitzungsfehlerrate insgesamt</span><span class="sxs-lookup"><span data-stu-id="4701b-116">Overall session failure rate</span></span>

  - <span data-ttu-id="4701b-117">Fehlerrate für Konferenzzustandsobjekt</span><span class="sxs-lookup"><span data-stu-id="4701b-117">Focus failure rate</span></span>

  - <span data-ttu-id="4701b-118">MCU-Fehlerrate</span><span class="sxs-lookup"><span data-stu-id="4701b-118">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="4701b-119">Optimale Verwendung des zusammenfassenden Anrufdiagnoseberichts</span><span class="sxs-lookup"><span data-stu-id="4701b-119">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="4701b-120">Der zusammenfassende Anruf Diagnosebericht enthält Diagramme, die Fehlerraten für die verschiedenen in Microsoft lync Server 2013 verwendeten Modalitäten vergleichen.</span><span class="sxs-lookup"><span data-stu-id="4701b-120">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4701b-121">Die Spalten in diesen Diagrammen sind tatsächlich Hotlinks; Wenn Sie beispielsweise auf die Instant Messaging-Spalte für Peer-to-Peer-Sitzungen klicken, wird ein Drilldown zu einer Instanz des [Diagnoseberichts über Peer-to-Peer-Aktivitäten in lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)durchführt, ein Bericht mit zusätzlichen Details zu allen Chatnachrichten, die im zusammenfassenden Anruf Diagnosebericht enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4701b-121">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4701b-122">Filter</span><span class="sxs-lookup"><span data-stu-id="4701b-122">Filters</span></span>

<span data-ttu-id="4701b-p104">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Anrufdiagnosebericht nach Kriterien wie dem Registrierungspool oder den in der Sitzung verwendeten Edgeserver filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4701b-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4701b-127">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Anrufdiagnosebericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4701b-127">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="4701b-128">Filter im Zusammenfassenden Anrufdiagnosebericht</span><span class="sxs-lookup"><span data-stu-id="4701b-128">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4701b-129">Name</span><span class="sxs-lookup"><span data-stu-id="4701b-129">Name</span></span></th>
<th><span data-ttu-id="4701b-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4701b-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4701b-131"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-131"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-p105">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="4701b-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4701b-134">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4701b-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4701b-p106">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="4701b-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4701b-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4701b-137">7/7/2012</span></span></p>
<p><span data-ttu-id="4701b-138">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="4701b-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4701b-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4701b-139">7/3/2012</span></span></p>
<p><span data-ttu-id="4701b-140">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="4701b-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4701b-141"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-141"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-p107">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="4701b-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4701b-144">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4701b-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4701b-p108">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="4701b-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4701b-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4701b-147">7/7/2012</span></span></p>
<p><span data-ttu-id="4701b-148">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="4701b-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4701b-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4701b-149">7/3/2012</span></span></p>
<p><span data-ttu-id="4701b-150">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="4701b-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4701b-151"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-151"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-p109">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="4701b-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4701b-154">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4701b-154">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4701b-155">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4701b-155">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4701b-156">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4701b-156">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4701b-157">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="4701b-157">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4701b-p110">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="4701b-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4701b-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-p111">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4701b-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="4701b-164">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4701b-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="4701b-165">In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Peer-zu-Peer-Sitzungen (d. h. für Sitzungen mit nur zwei Teilnehmern) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4701b-165">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="4701b-166">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4701b-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4701b-167">Name</span><span class="sxs-lookup"><span data-stu-id="4701b-167">Name</span></span></th>
<th><span data-ttu-id="4701b-168">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="4701b-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4701b-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4701b-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4701b-170"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-170"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-171">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-171">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-172">Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="4701b-172">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4701b-173"><strong>Fehlerrate</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-173"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-174">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-174">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-p112">Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist. Wenn Sie auf dieses Element klicken, wird der Diagnosebericht über Peer-zu-Peer-Aktivitäten angezeigt, der detailliertere Angaben zu den fehlgeschlagenen Peer-zu-Peer-Sitzungen enthält.</span><span class="sxs-lookup"><span data-stu-id="4701b-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="4701b-177">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="4701b-177">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="4701b-178">In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Konferenzsitzungen (d. h. für Sitzungen mit mindestens drei Teilnehmern) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4701b-178">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="4701b-179">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="4701b-179">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4701b-180">Name</span><span class="sxs-lookup"><span data-stu-id="4701b-180">Name</span></span></th>
<th><span data-ttu-id="4701b-181">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="4701b-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4701b-182">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4701b-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4701b-183"><strong>Konferenzen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-183"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-184">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-184">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-185">Die Gesamtzahl der Konferenzen, die stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="4701b-185">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4701b-186"><strong>Konferenzsitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-186"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-187">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-187">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-188">Die Gesamtzahl der Konferenzsitzungen, die durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="4701b-188">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4701b-189"><strong>Sitzungsfehlerrate insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-189"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-190">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-190">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-191">Der Prozentsatz der Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4701b-191">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4701b-192"><strong>Konferenzzustandsobjekt-Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-192"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-193">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-193">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-194">Die Anzahl der auf Konferenzzustandsobjekten basierenden Sitzungen, bei denen Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="4701b-194">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4701b-195"><strong>Fehlerrate für Konferenzzustandsobjekt</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-195"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-196">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-196">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-197">Der Prozentsatz der auf Konferenzzustandsobjekten basierenden Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4701b-197">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4701b-198"><strong>MCU-Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-198"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-199">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-199">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-200">Die Gesamtzahl der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4701b-200">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4701b-201"><strong>MCU-Fehlerrate</strong></span><span class="sxs-lookup"><span data-stu-id="4701b-201"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4701b-202">Nein</span><span class="sxs-lookup"><span data-stu-id="4701b-202">No</span></span></p></td>
<td><p><span data-ttu-id="4701b-203">Der Prozentsatz der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4701b-203">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

