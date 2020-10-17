---
title: 'Lync Server 2013: Bericht über die häufigsten Fehler'
description: 'Lync Server 2013: Bericht "Top Failures".'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 768c9a99916dece9eb76877b0cd65b057697ff95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561271"
---
# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="9c69c-103">Bericht über die häufigsten Fehler in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c69c-103">Top Failures Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c69c-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9c69c-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9c69c-p101">Der Bericht über häufigste Fehler bietet einen Überblick über die am häufigsten gemeldeten Fehler mit Trenddarstellung.</span><span class="sxs-lookup"><span data-stu-id="9c69c-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="9c69c-p102">**Diagnose-ID**. Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="9c69c-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="9c69c-110">**Antwortcode**.</span><span class="sxs-lookup"><span data-stu-id="9c69c-110">**Response code**.</span></span> <span data-ttu-id="9c69c-111">In SIP-Kommunikationssitzungen werden Antwortcodes verwendet, um auf SIP-Anforderungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="9c69c-111">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="9c69c-112">Nehmen wir beispielsweise an, dass Ken die INVITE-Anforderung an Pilar Ackerman sendet (angenommen, Ken Myers ruft Pilar Ackerman an).</span><span class="sxs-lookup"><span data-stu-id="9c69c-112">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="9c69c-113">Wenn Pilar antwortet, sendet Ihr Telefon den Antwortcode 200 (OK) und lässt Ken Telefon wissen, dass Pilar geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="9c69c-113">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="9c69c-114">Der Bericht "Top Failures" enthält nur Antwortcodes, die als Reaktion auf einen Anruf Fehler gesendet wurden. In lync Server werden nicht alle im Verlauf eines Anrufs ausgestellten Antwortcodes protokolliert.</span><span class="sxs-lookup"><span data-stu-id="9c69c-114">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="9c69c-115">Informationen werden nicht nur für die Gesamtzahl an Sitzungen, in denen ein Fehler aufgetreten ist, gemeldet, sondern auch für die Gesamtzahl der Benutzer, die von den Fehlern betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="9c69c-115">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="9c69c-116">Zugriff auf den Bericht über häufigste Fehler</span><span class="sxs-lookup"><span data-stu-id="9c69c-116">Accessing the Top Failures Report</span></span>

<span data-ttu-id="9c69c-117">Der Zugriff auf den Bericht über häufigste Fehler erfolgt von der Überwachungsberichte-Startseite aus.</span><span class="sxs-lookup"><span data-stu-id="9c69c-117">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="9c69c-118">Durch Klicken auf die Metrik "gemeldete Sitzungen" gelangen Sie zum [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="9c69c-118">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="9c69c-119">Beste Nutzung des Berichts häufigster Fehler</span><span class="sxs-lookup"><span data-stu-id="9c69c-119">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="9c69c-p105">Der Bericht häufigster Fehler ist in einer Hinsicht ungewöhnlich: Er ermöglicht Ihnen gleichzeitig, nach bis zu 5 Diagnose-IDs zu filtern (normalerweise kann nur nach einem Element gleichzeitig gefiltert werden, z. B. nach der SIP-Adresse des Benutzers). Um nach mehreren Diagnose-IDs zu filtern, geben Sie einfach alle IDs durch Kommas getrennt in das Feld "Diagnose-IDs" ein (Sie können, müssen aber nicht nach jedem Komma ein Leerzeichen einfügen). Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="9c69c-123">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="9c69c-123">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="9c69c-124">Wenn Sie dies tun, werden nur fehlerhafte Anrufe, die mindestens eine dieser fünf Diagnose-IDs gemeldet haben, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c69c-124">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="9c69c-p106">Wenn Sie Ihre Maus über einen Antwortcode bewegen, wird eine QuickInfo angezeigt, die Ihnen mitteilt, was der jeweilige Antwortcode bedeutet. Wenn Sie beispielsweise die Maus über den Antwortcode 486 bewegen, wird folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="9c69c-127">Ausgelastet.</span><span class="sxs-lookup"><span data-stu-id="9c69c-127">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9c69c-128">Filter</span><span class="sxs-lookup"><span data-stu-id="9c69c-128">Filters</span></span>

<span data-ttu-id="9c69c-p107">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie die zurückgegebenen Daten im Bericht über häufigste Fehler nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder dem SIP-Antwortcode für die fehlgeschlagene Sitzung filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Ereignisse nach Stunde, Tag, Woche oder Monat zusammengefasst</span><span class="sxs-lookup"><span data-stu-id="9c69c-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="9c69c-133">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über häufigste Fehler verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9c69c-133">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="9c69c-134">Filter im Bericht über häufigste Fehler</span><span class="sxs-lookup"><span data-stu-id="9c69c-134">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c69c-135">Name</span><span class="sxs-lookup"><span data-stu-id="9c69c-135">Name</span></span></th>
<th><span data-ttu-id="9c69c-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c69c-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c69c-137"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-137"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-p108">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9c69c-140">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="9c69c-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9c69c-p109">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9c69c-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9c69c-143">7/7/2012</span></span></p>
<p><span data-ttu-id="9c69c-144">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="9c69c-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9c69c-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9c69c-145">7/3/2012</span></span></p>
<p><span data-ttu-id="9c69c-146">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="9c69c-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c69c-147"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-147"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-p110">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9c69c-150">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="9c69c-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9c69c-p111">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9c69c-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9c69c-153">7/7/2012</span></span></p>
<p><span data-ttu-id="9c69c-154">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="9c69c-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9c69c-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9c69c-155">7/3/2012</span></span></p>
<p><span data-ttu-id="9c69c-156">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="9c69c-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c69c-157"><strong>Aktivitätstyp</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-157"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-p112">Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9c69c-160">Alle</span><span class="sxs-lookup"><span data-stu-id="9c69c-160">[All]</span></span></p></li>
<li><p><span data-ttu-id="9c69c-161">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="9c69c-161">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="9c69c-162">Konferenz</span><span class="sxs-lookup"><span data-stu-id="9c69c-162">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c69c-163"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-163"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-164">Derzeit ist nur die Option <strong>[Alle]</strong> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9c69c-164">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c69c-165"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-165"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-p113">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9c69c-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c69c-169"><strong>Kategorie</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-169"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-p114">Der Typ des aufgetretenen Fehlers. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9c69c-172">Erwartete und unerwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="9c69c-172">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="9c69c-173">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="9c69c-173">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="9c69c-174">Ein &quot; Erwarteter Fehler &quot; ist ein Fehler, der voraussichtlich eintreten wird.</span><span class="sxs-lookup"><span data-stu-id="9c69c-174">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="9c69c-175">Hat beispielsweise ein Benutzer seinen Status auf "Nicht stören" gesetzt, ist zu erwarten, dass alle Anrufe an diesen Benutzer fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="9c69c-175">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="9c69c-176">Ein &quot; unerwarteter Fehler &quot; ist ein Fehler, der in einem ansonsten fehlerhaften System auftritt.</span><span class="sxs-lookup"><span data-stu-id="9c69c-176">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="9c69c-177">Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet.</span><span class="sxs-lookup"><span data-stu-id="9c69c-177">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="9c69c-178">Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="9c69c-178">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c69c-179"><strong>Antwortcode</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-179"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-p116">Der SIP-Antwortcode, der gesendet wird, wenn die Konferenz fehlschlägt. Geben Sie den vollständigen Antwortcode ein. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9c69c-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="9c69c-182">400</span><span class="sxs-lookup"><span data-stu-id="9c69c-182">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c69c-183"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-183"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-p117">Der eindeutige Bezeichner (im Format eines ms-diagnostics-Headers), der an eine SIP-Nachricht angehängt ist und häufig Informationen enthält, die bei der Problembehandlung hilfreich sind. Diagnoseheader sind optional (es gibt auch SIP-Sitzungen, die keinen solchen Header enthalten), und Diagnose-IDs werden nur für Sitzungen zurückgegeben, bei denen ein Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9c69c-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9c69c-186">Metriken</span><span class="sxs-lookup"><span data-stu-id="9c69c-186">Metrics</span></span>

<span data-ttu-id="9c69c-187">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über häufigste Fehler angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9c69c-187">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="9c69c-188">Metriken im Bericht über häufigste Fehler</span><span class="sxs-lookup"><span data-stu-id="9c69c-188">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c69c-189">Name</span><span class="sxs-lookup"><span data-stu-id="9c69c-189">Name</span></span></th>
<th><span data-ttu-id="9c69c-190">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="9c69c-190">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9c69c-191">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c69c-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c69c-192"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-192"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-193">Ja</span><span class="sxs-lookup"><span data-stu-id="9c69c-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="9c69c-194">Der relative Rang basierend auf der Anzahl der gemeldeten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9c69c-194">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c69c-195"><strong>Gemeldete Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-195"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-196">Ja</span><span class="sxs-lookup"><span data-stu-id="9c69c-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="9c69c-197">Die Gesamtzahl der fehlerhaften Sitzungen basierend auf der Diagnose-ID und dem SIP-Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="9c69c-197">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c69c-198"><strong>Betroffene Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-198"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-199">Ja</span><span class="sxs-lookup"><span data-stu-id="9c69c-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="9c69c-200">Die Gesamtzahl der Benutzer, die von der fehlerhaften Sitzung betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="9c69c-200">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c69c-201"><strong>Fehlerinformationen</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-201"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-202">Nein</span><span class="sxs-lookup"><span data-stu-id="9c69c-202">No</span></span></p></td>
<td><p><span data-ttu-id="9c69c-203">Genaue Angaben zu dem Fehler, u. a. die Diagnose-ID, der SIP-Antwortcode und eine Beschreibung der Ursache des Sitzungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="9c69c-203">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c69c-204"><strong>Trend in der Vergangenheit</strong></span><span class="sxs-lookup"><span data-stu-id="9c69c-204"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="9c69c-205">Nein</span><span class="sxs-lookup"><span data-stu-id="9c69c-205">No</span></span></p></td>
<td><p><span data-ttu-id="9c69c-206">Eine grafische Darstellung der fehlerhaften Sitzungen über einen bestimmten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="9c69c-206">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

