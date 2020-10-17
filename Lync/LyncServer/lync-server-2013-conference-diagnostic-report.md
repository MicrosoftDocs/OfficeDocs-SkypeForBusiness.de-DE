---
title: 'Lync Server 2013: Konferenz Diagnosebericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c4489e13f794a924e1512a1e6ed7b32f73da8f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525992"
---
# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="4751a-102">Konferenz Diagnosebericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4751a-102">Conference Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4751a-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4751a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4751a-104">Der Konferenz Diagnosebericht enthält Informationen über den Erfolg und das Scheitern aller Konferenzsitzungen.</span><span class="sxs-lookup"><span data-stu-id="4751a-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="4751a-105">Beachten Sie, dass Microsoft lync Server zwischen verschiedenen Arten von Fehlern unterscheidet:</span><span class="sxs-lookup"><span data-stu-id="4751a-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="4751a-106">**Erwarteter Fehler**.</span><span class="sxs-lookup"><span data-stu-id="4751a-106">**Expected failure**.</span></span> <span data-ttu-id="4751a-107">Ein erwarteter Fehler ist normalerweise nur im technischsten Sinn ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="4751a-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="4751a-108">Nehmen wir beispielsweise an, dass jemand eine Konferenz startet, aber auflegt, bevor jeder beitreten kann.</span><span class="sxs-lookup"><span data-stu-id="4751a-108">For example, suppose someone starts a conference but hangs up before anyone can join.</span></span> <span data-ttu-id="4751a-109">Technisch gesehen ist das ein Fehler: die Konferenz wurde initiiert, aber nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4751a-109">Technically that's a failure: the conference was initiated, but not completed.</span></span> <span data-ttu-id="4751a-110">Dies ist jedoch ein Fehler, den Sie erwarten würden: Wenn der Organisator die Konferenz abbricht, bevor jemand beitreten kann, wird die Konferenz nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4751a-110">However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="4751a-111">**Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der gemessen an den Umständen nicht zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="4751a-111">**Unexpected failure**.</span></span> <span data-ttu-id="4751a-112">Angenommen, Sie rufen eine Person an, und die Person kann den Anruf annehmen.</span><span class="sxs-lookup"><span data-stu-id="4751a-112">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="4751a-113">Angenommen, eine Konferenz konnte nicht abgehalten werden, da die Besprechungsrichtlinie des Organisators nicht abgerufen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="4751a-113">For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved.</span></span> <span data-ttu-id="4751a-114">Das ist ein unerwarteter Fehler: Schließlich sollten Sie immer in der Lage sein, die Besprechungsrichtlinie eines Benutzers abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4751a-114">That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="4751a-115">Beachten Sie, dass die Metriken für "Erfolg", "Erwarteter Fehler" und "Unerwarteter Fehler" nicht zwangsläufig identisch mit der Metrik unter "Sitzungen insgesamt" sind.</span><span class="sxs-lookup"><span data-stu-id="4751a-115">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="4751a-116">Im Bericht werden beispielsweise die folgenden Werte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4751a-116">For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4751a-117">Erfolge</span><span class="sxs-lookup"><span data-stu-id="4751a-117">Successes</span></span></th>
<th><span data-ttu-id="4751a-118">Erwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="4751a-118">Expected failures</span></span></th>
<th><span data-ttu-id="4751a-119">Unerwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="4751a-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="4751a-120">Sitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="4751a-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4751a-121">2024</span><span class="sxs-lookup"><span data-stu-id="4751a-121">2024</span></span></p></td>
<td><p><span data-ttu-id="4751a-122">469</span><span class="sxs-lookup"><span data-stu-id="4751a-122">469</span></span></p></td>
<td><p><span data-ttu-id="4751a-123">16 </span><span class="sxs-lookup"><span data-stu-id="4751a-123">16</span></span></p></td>
<td><p><span data-ttu-id="4751a-124">2521</span><span class="sxs-lookup"><span data-stu-id="4751a-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4751a-125">Wenn Sie 2024 + 469 + 16 hinzufügen, erhalten Sie insgesamt 2.509 Sitzungen, in der Spalte Gesamt Sitzungen werden jedoch insgesamt 2.521 Sitzungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4751a-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="4751a-126">Die "fehlenden" 12 Sitzungen für sind Sitzungen, die vom System nicht als erfolgreich oder nicht erfolgreich kategorisiert werden konnten.</span><span class="sxs-lookup"><span data-stu-id="4751a-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="4751a-127">Dies ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der Monitoring Server nicht vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="4751a-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="4751a-128">Wenn dies geschieht, können mit diesem Produkt erstellte Anrufe und das melden dieses Diagnosecodes nicht immer als ein Erfolg, ein erwarteter Fehler oder ein unerwarteter Fehler kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="4751a-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="4751a-129">Zugreifen auf den Konferenz Diagnosebericht</span><span class="sxs-lookup"><span data-stu-id="4751a-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="4751a-130">Der Zugriff auf den Konferenz Diagnosebericht erfolgt über die Startseite für Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="4751a-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4751a-131">Sie können auf den [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="4751a-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4751a-132">Anzahl der unerwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="4751a-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="4751a-133">Anzahl der erwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="4751a-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="4751a-134">Optimale Nutzung des Konferenz Diagnoseberichts</span><span class="sxs-lookup"><span data-stu-id="4751a-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="4751a-135">Der Konferenz Diagnosebericht enthält eine Reihe von Diagrammen.</span><span class="sxs-lookup"><span data-stu-id="4751a-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="4751a-136">Jede der im Diagramm gezeigten Spalten ist eigentlich ein Hyperlink.</span><span class="sxs-lookup"><span data-stu-id="4751a-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="4751a-137">Wenn Sie auf eine Spalte klicken, führen Sie einen Drilldown zum [Fehler Verteilungs Bericht in lync Server 2013](lync-server-2013-failure-distribution-report.md) für diesen Zeitraum und diesen Konferenztyp aus.</span><span class="sxs-lookup"><span data-stu-id="4751a-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4751a-138">Filter</span><span class="sxs-lookup"><span data-stu-id="4751a-138">Filters</span></span>

<span data-ttu-id="4751a-139">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4751a-139">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="4751a-140">Beispielsweise können Sie mit dem Konferenz Diagnosebericht nach Dingen suchen, die den Typ der Konferenz (beispielsweise eine Fokus basierte Konferenz) oder den in der Konferenz verwendeten Edgeserver filtern.</span><span class="sxs-lookup"><span data-stu-id="4751a-140">For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference.</span></span> <span data-ttu-id="4751a-141">Sie können außerdem festlegen, wie Daten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4751a-141">You can also choose how data should be grouped.</span></span> <span data-ttu-id="4751a-142">In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4751a-142">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4751a-143">In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Konferenz Diagnosebericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4751a-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="4751a-144">Filter für Konferenz Diagnoseberichte</span><span class="sxs-lookup"><span data-stu-id="4751a-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4751a-145">Name</span><span class="sxs-lookup"><span data-stu-id="4751a-145">Name</span></span></th>
<th><span data-ttu-id="4751a-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4751a-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4751a-147"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-p109">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="4751a-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4751a-150">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4751a-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4751a-p110">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="4751a-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4751a-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4751a-153">7/7/2012</span></span></p>
<p><span data-ttu-id="4751a-154">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="4751a-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4751a-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4751a-155">7/3/2012</span></span></p>
<p><span data-ttu-id="4751a-156">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="4751a-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4751a-157"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-p111">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="4751a-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4751a-160">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4751a-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4751a-p112">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="4751a-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4751a-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4751a-163">7/7/2012</span></span></p>
<p><span data-ttu-id="4751a-164">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="4751a-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4751a-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4751a-165">7/3/2012</span></span></p>
<p><span data-ttu-id="4751a-166">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="4751a-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4751a-167"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-p113">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="4751a-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4751a-170">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4751a-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4751a-171">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4751a-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4751a-172">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4751a-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4751a-173">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="4751a-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4751a-p114">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="4751a-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4751a-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-p115">Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4751a-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4751a-180"><strong>Konferenzsitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-181">Gibt den Typ der Konferenzsitzung an.</span><span class="sxs-lookup"><span data-stu-id="4751a-181">Indicates the type of conferencing session.</span></span> <span data-ttu-id="4751a-182">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="4751a-182">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4751a-183">Alle</span><span class="sxs-lookup"><span data-stu-id="4751a-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="4751a-184">Konferenzzustandsobjekt-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4751a-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="4751a-185">Alle MCU-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4751a-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="4751a-186">Sofortnachrichtenkonferenzen</span><span class="sxs-lookup"><span data-stu-id="4751a-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="4751a-187">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="4751a-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="4751a-188">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="4751a-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4751a-189">Metriken</span><span class="sxs-lookup"><span data-stu-id="4751a-189">Metrics</span></span>

<span data-ttu-id="4751a-190">In der folgenden Tabelle sind die Informationen aufgeführt, die im Diagnosebericht über die Konferenz für jeden Typ von Konferenzsitzung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4751a-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="4751a-191">Metriken für den Konferenz Diagnosebericht</span><span class="sxs-lookup"><span data-stu-id="4751a-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4751a-192">Name</span><span class="sxs-lookup"><span data-stu-id="4751a-192">Name</span></span></th>
<th><span data-ttu-id="4751a-193">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="4751a-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4751a-194">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4751a-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4751a-195"><strong>Anzahl der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-196">Nein</span><span class="sxs-lookup"><span data-stu-id="4751a-196">No</span></span></p></td>
<td><p><span data-ttu-id="4751a-197">Die Gesamtzahl der erfolgreichen Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="4751a-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4751a-198"><strong>Prozentsatz der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-199">Nein</span><span class="sxs-lookup"><span data-stu-id="4751a-199">No</span></span></p></td>
<td><p><span data-ttu-id="4751a-200">Prozentsatz der Konferenzen, die mit erheblichen Problemen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="4751a-200">Percentage of conferences that completed with significant problems.</span></span> <span data-ttu-id="4751a-201">Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4751a-201">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4751a-202"><strong>Anzahl der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-203">Nein</span><span class="sxs-lookup"><span data-stu-id="4751a-203">No</span></span></p></td>
<td><p><span data-ttu-id="4751a-204">Die Gesamtzahl der Konferenzen, bei denen ein &quot; Erwarteter Fehler &quot; aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4751a-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="4751a-p118">Ein erwarteter Fehler ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf Nicht stören festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="4751a-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4751a-207"><strong>Prozentsatz der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-208">Nein</span><span class="sxs-lookup"><span data-stu-id="4751a-208">No</span></span></p></td>
<td><p><span data-ttu-id="4751a-209">Prozentsatz der Konferenzen, bei denen ein erwarteter Fehler auftrat.</span><span class="sxs-lookup"><span data-stu-id="4751a-209">Percentage of conferences that experienced an expected error.</span></span> <span data-ttu-id="4751a-210">Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4751a-210">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4751a-211"><strong>Anzahl der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-212">Nein</span><span class="sxs-lookup"><span data-stu-id="4751a-212">No</span></span></p></td>
<td><p><span data-ttu-id="4751a-213">Die Gesamtzahl der Konferenzen, bei denen ein &quot; unerwarteter Fehler &quot; aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4751a-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="4751a-p120">Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4751a-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4751a-217"><strong>Prozentsatz der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-218">Nein</span><span class="sxs-lookup"><span data-stu-id="4751a-218">No</span></span></p></td>
<td><p><span data-ttu-id="4751a-219">Prozentsatz der Konferenzen, bei denen ein unerwarteter Fehler auftrat</span><span class="sxs-lookup"><span data-stu-id="4751a-219">Percentage of conferences that experienced an unexpected error.</span></span> <span data-ttu-id="4751a-220">Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4751a-220">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4751a-221"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4751a-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4751a-222">Nein</span><span class="sxs-lookup"><span data-stu-id="4751a-222">No</span></span></p></td>
<td><p><span data-ttu-id="4751a-223">Gesamtzahl der Konferenzen, einschließlich erfolgreicher Konferenzen, fehlgeschlagener Konferenzen (sowohl erwartete Fehler als auch unerwartete Fehler) und nicht kategorisierter Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="4751a-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

