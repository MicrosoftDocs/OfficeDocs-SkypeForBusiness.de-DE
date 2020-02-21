---
title: 'Lync Server 2013: zusammenfassender Anruf Diagnosebericht'
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
ms.openlocfilehash: c055a48684716ce64428615759b023242b9e4ff5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="b2b66-102">Zusammenfassender Anruf Diagnosebericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2b66-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2b66-103">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="b2b66-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="b2b66-p101">Der zusammenfassende Anrufdiagnosebericht bietet eine Gesamtübersicht zu fehlgeschlagenen Peer-zu-Peer- und Konferenzsitzungen. Der Bericht zeigt die Gesamtfehlerrate für beide Sitzungstypen und detaillierte Fehlerinformationen nach Sitzungsmodalitätstyp:</span><span class="sxs-lookup"><span data-stu-id="b2b66-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="b2b66-106">Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="b2b66-106">Instant messaging</span></span>

  - <span data-ttu-id="b2b66-107">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="b2b66-107">Application sharing</span></span>

  - <span data-ttu-id="b2b66-108">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="b2b66-108">File transfer</span></span>

  - <span data-ttu-id="b2b66-109">Audio</span><span class="sxs-lookup"><span data-stu-id="b2b66-109">Audio</span></span>

  - <span data-ttu-id="b2b66-110">Video</span><span class="sxs-lookup"><span data-stu-id="b2b66-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="b2b66-111">Zugriff auf den zusammenfassenden Anrufdiagnosebericht</span><span class="sxs-lookup"><span data-stu-id="b2b66-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="b2b66-112">Der Zugriff auf den zusammenfassenden Anrufdiagnosebericht erfolgt auf der Startseite für Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="b2b66-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="b2b66-113">Im zusammenfassenden Bericht "Anruf Diagnose" können Sie auf den [Diagnosebericht über Peer-to-Peer-Aktivitäten in lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) zugreifen, indem Sie im Abschnitt Peer-to-Peer-Sitzungszusammenfassung des Berichts auf die Metrik für Fehlerrate klicken.</span><span class="sxs-lookup"><span data-stu-id="b2b66-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="b2b66-114">Sie können auch auf den [Konferenz Diagnosebericht in lync Server 2013](lync-server-2013-conference-diagnostic-report.md) zugreifen, indem Sie auf eine der folgenden Konferenz Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="b2b66-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="b2b66-115">Sitzungsfehlerrate insgesamt</span><span class="sxs-lookup"><span data-stu-id="b2b66-115">Overall session failure rate</span></span>

  - <span data-ttu-id="b2b66-116">Fehlerrate für Konferenzzustandsobjekt</span><span class="sxs-lookup"><span data-stu-id="b2b66-116">Focus failure rate</span></span>

  - <span data-ttu-id="b2b66-117">MCU-Fehlerrate</span><span class="sxs-lookup"><span data-stu-id="b2b66-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="b2b66-118">Optimale Verwendung des zusammenfassenden Anrufdiagnoseberichts</span><span class="sxs-lookup"><span data-stu-id="b2b66-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="b2b66-119">Der zusammenfassende Anruf Diagnosebericht enthält Diagramme, die Fehlerraten für die verschiedenen in Microsoft lync Server 2013 verwendeten Modalitäten vergleichen.</span><span class="sxs-lookup"><span data-stu-id="b2b66-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b2b66-120">Die Spalten in diesen Diagrammen sind tatsächlich Hotlinks; Wenn Sie beispielsweise auf die Instant Messaging-Spalte für Peer-to-Peer-Sitzungen klicken, wird ein Drilldown zu einer Instanz des [Diagnoseberichts über Peer-to-Peer-Aktivitäten in lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)durchführt, ein Bericht mit zusätzlichen Details zu allen Chatnachrichten, die im zusammenfassenden Anruf Diagnosebericht enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b2b66-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b2b66-121">Filter</span><span class="sxs-lookup"><span data-stu-id="b2b66-121">Filters</span></span>

<span data-ttu-id="b2b66-p104">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Anrufdiagnosebericht nach Kriterien wie dem Registrierungspool oder den in der Sitzung verwendeten Edgeserver filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b2b66-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b2b66-126">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Anrufdiagnosebericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b2b66-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="b2b66-127">Filter im Zusammenfassenden Anrufdiagnosebericht</span><span class="sxs-lookup"><span data-stu-id="b2b66-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2b66-128">Name</span><span class="sxs-lookup"><span data-stu-id="b2b66-128">Name</span></span></th>
<th><span data-ttu-id="b2b66-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2b66-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b66-130"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-p105">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="b2b66-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b2b66-133">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="b2b66-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b2b66-p106">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="b2b66-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b2b66-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b2b66-136">7/7/2012</span></span></p>
<p><span data-ttu-id="b2b66-137">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="b2b66-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b2b66-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b2b66-138">7/3/2012</span></span></p>
<p><span data-ttu-id="b2b66-139">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="b2b66-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b66-140"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-p107">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="b2b66-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b2b66-143">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="b2b66-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b2b66-p108">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="b2b66-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b2b66-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b2b66-146">7/7/2012</span></span></p>
<p><span data-ttu-id="b2b66-147">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="b2b66-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b2b66-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b2b66-148">7/3/2012</span></span></p>
<p><span data-ttu-id="b2b66-149">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="b2b66-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b66-150"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-p109">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b2b66-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2b66-153">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="b2b66-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b2b66-154">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="b2b66-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b2b66-155">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="b2b66-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b2b66-156">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="b2b66-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b2b66-p110">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="b2b66-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b66-159"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-p111">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b2b66-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="b2b66-163">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="b2b66-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="b2b66-164">In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Peer-zu-Peer-Sitzungen (d. h. für Sitzungen mit nur zwei Teilnehmern) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b2b66-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="b2b66-165">Metriken für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="b2b66-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2b66-166">Name</span><span class="sxs-lookup"><span data-stu-id="b2b66-166">Name</span></span></th>
<th><span data-ttu-id="b2b66-167">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="b2b66-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2b66-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2b66-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b66-169"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-170">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-170">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-171">Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="b2b66-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b66-172"><strong>Fehlerrate</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-173">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-173">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-p112">Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist. Wenn Sie auf dieses Element klicken, wird der Diagnosebericht über Peer-zu-Peer-Aktivitäten angezeigt, der detailliertere Angaben zu den fehlgeschlagenen Peer-zu-Peer-Sitzungen enthält.</span><span class="sxs-lookup"><span data-stu-id="b2b66-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="b2b66-176">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="b2b66-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="b2b66-177">In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Konferenzsitzungen (d. h. für Sitzungen mit mindestens drei Teilnehmern) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b2b66-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="b2b66-178">Metriken für Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="b2b66-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2b66-179">Name</span><span class="sxs-lookup"><span data-stu-id="b2b66-179">Name</span></span></th>
<th><span data-ttu-id="b2b66-180">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="b2b66-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2b66-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2b66-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b66-182"><strong>Konferenzen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-183">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-183">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-184">Die Gesamtzahl der Konferenzen, die stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="b2b66-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b66-185"><strong>Konferenzsitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-186">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-186">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-187">Die Gesamtzahl der Konferenzsitzungen, die durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="b2b66-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b66-188"><strong>Sitzungsfehlerrate insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-189">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-189">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-190">Der Prozentsatz der Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b2b66-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b66-191"><strong>Konferenzzustandsobjekt-Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-192">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-192">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-193">Die Anzahl der auf Konferenzzustandsobjekten basierenden Sitzungen, bei denen Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="b2b66-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b66-194"><strong>Fehlerrate für Konferenzzustandsobjekt</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-195">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-195">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-196">Der Prozentsatz der auf Konferenzzustandsobjekten basierenden Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b2b66-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b66-197"><strong>MCU-Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-198">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-198">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-199">Die Gesamtzahl der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b2b66-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b66-200"><strong>MCU-Fehlerrate</strong></span><span class="sxs-lookup"><span data-stu-id="b2b66-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b66-201">Nein</span><span class="sxs-lookup"><span data-stu-id="b2b66-201">No</span></span></p></td>
<td><p><span data-ttu-id="b2b66-202">Der Prozentsatz der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b2b66-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

