---
title: 'Lync Server 2013: Bericht über die häufigsten Fehler'
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
ms.openlocfilehash: 7c24c8879f967553d5bb6449f9245781f2b56e46
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="b58b3-102">Bericht über die häufigsten Fehler in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b58b3-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b58b3-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b58b3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b58b3-p101">Der Bericht über häufigste Fehler bietet einen Überblick über die am häufigsten gemeldeten Fehler mit Trenddarstellung.</span><span class="sxs-lookup"><span data-stu-id="b58b3-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="b58b3-p102">**Diagnose-ID**. Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b58b3-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="b58b3-109">**Antwortcode**.</span><span class="sxs-lookup"><span data-stu-id="b58b3-109">**Response code**.</span></span> <span data-ttu-id="b58b3-110">In SIP-Kommunikationssitzungen werden Antwortcodes verwendet, um auf SIP-Anforderungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="b58b3-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="b58b3-111">Nehmen wir beispielsweise an, dass Ken die INVITE-Anforderung an Pilar Ackerman sendet (angenommen, Ken Myers ruft Pilar Ackerman an).</span><span class="sxs-lookup"><span data-stu-id="b58b3-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="b58b3-112">Wenn Pilar antwortet, sendet Ihr Telefon den Antwortcode 200 (OK) und lässt Ken Telefon wissen, dass Pilar geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="b58b3-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="b58b3-113">Der Bericht "Top Failures" enthält nur Antwortcodes, die als Reaktion auf einen Anruf Fehler gesendet wurden. In lync Server werden nicht alle im Verlauf eines Anrufs ausgestellten Antwortcodes protokolliert.</span><span class="sxs-lookup"><span data-stu-id="b58b3-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="b58b3-114">Informationen werden nicht nur für die Gesamtzahl an Sitzungen, in denen ein Fehler aufgetreten ist, gemeldet, sondern auch für die Gesamtzahl der Benutzer, die von den Fehlern betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="b58b3-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="b58b3-115">Zugriff auf den Bericht über häufigste Fehler</span><span class="sxs-lookup"><span data-stu-id="b58b3-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="b58b3-116">Der Zugriff auf den Bericht über häufigste Fehler erfolgt von der Überwachungsberichte-Startseite aus.</span><span class="sxs-lookup"><span data-stu-id="b58b3-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="b58b3-117">Durch Klicken auf die Metrik "gemeldete Sitzungen" gelangen Sie zum [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="b58b3-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="b58b3-118">Beste Nutzung des Berichts häufigster Fehler</span><span class="sxs-lookup"><span data-stu-id="b58b3-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="b58b3-p105">Der Bericht häufigster Fehler ist in einer Hinsicht ungewöhnlich: Er ermöglicht Ihnen gleichzeitig, nach bis zu 5 Diagnose-IDs zu filtern (normalerweise kann nur nach einem Element gleichzeitig gefiltert werden, z. B. nach der SIP-Adresse des Benutzers). Um nach mehreren Diagnose-IDs zu filtern, geben Sie einfach alle IDs durch Kommas getrennt in das Feld "Diagnose-IDs" ein (Sie können, müssen aber nicht nach jedem Komma ein Leerzeichen einfügen). Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="b58b3-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="b58b3-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="b58b3-123">Wenn Sie dies tun, werden nur fehlerhafte Anrufe, die mindestens eine dieser fünf Diagnose-IDs gemeldet haben, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b58b3-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="b58b3-p106">Wenn Sie Ihre Maus über einen Antwortcode bewegen, wird eine QuickInfo angezeigt, die Ihnen mitteilt, was der jeweilige Antwortcode bedeutet. Wenn Sie beispielsweise die Maus über den Antwortcode 486 bewegen, wird folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="b58b3-126">Ausgelastet.</span><span class="sxs-lookup"><span data-stu-id="b58b3-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b58b3-127">Filter</span><span class="sxs-lookup"><span data-stu-id="b58b3-127">Filters</span></span>

<span data-ttu-id="b58b3-p107">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie die zurückgegebenen Daten im Bericht über häufigste Fehler nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder dem SIP-Antwortcode für die fehlgeschlagene Sitzung filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Ereignisse nach Stunde, Tag, Woche oder Monat zusammengefasst</span><span class="sxs-lookup"><span data-stu-id="b58b3-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b58b3-132">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über häufigste Fehler verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b58b3-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="b58b3-133">Filter im Bericht über häufigste Fehler</span><span class="sxs-lookup"><span data-stu-id="b58b3-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b58b3-134">Name</span><span class="sxs-lookup"><span data-stu-id="b58b3-134">Name</span></span></th>
<th><span data-ttu-id="b58b3-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b58b3-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b58b3-136"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-p108">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b58b3-139">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="b58b3-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b58b3-p109">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b58b3-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b58b3-142">7/7/2012</span></span></p>
<p><span data-ttu-id="b58b3-143">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="b58b3-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b58b3-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b58b3-144">7/3/2012</span></span></p>
<p><span data-ttu-id="b58b3-145">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="b58b3-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58b3-146"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-p110">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b58b3-149">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="b58b3-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b58b3-p111">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b58b3-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b58b3-152">7/7/2012</span></span></p>
<p><span data-ttu-id="b58b3-153">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="b58b3-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b58b3-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b58b3-154">7/3/2012</span></span></p>
<p><span data-ttu-id="b58b3-155">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="b58b3-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58b3-156"><strong>Aktivitätstyp</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-p112">Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b58b3-159">Alle</span><span class="sxs-lookup"><span data-stu-id="b58b3-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="b58b3-160">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="b58b3-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="b58b3-161">Konferenz</span><span class="sxs-lookup"><span data-stu-id="b58b3-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58b3-162"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-163">Derzeit ist nur die Option <strong>[Alle]</strong> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b58b3-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58b3-164"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-p113">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b58b3-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58b3-168"><strong>Kategorie</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-p114">Der Typ des aufgetretenen Fehlers. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b58b3-171">Erwartete und unerwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="b58b3-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="b58b3-172">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="b58b3-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="b58b3-173">Ein &quot;erwarteter&quot; Fehler ist ein Fehler, der voraussichtlich eintreten wird.</span><span class="sxs-lookup"><span data-stu-id="b58b3-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="b58b3-174">Hat beispielsweise ein Benutzer seinen Status auf "Nicht stören" gesetzt, ist zu erwarten, dass alle Anrufe an diesen Benutzer fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="b58b3-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="b58b3-175">Ein &quot;unerwarteter Fehler&quot; ist ein Fehler, der in einem ansonsten fehlerhaften System auftritt.</span><span class="sxs-lookup"><span data-stu-id="b58b3-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="b58b3-176">Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet.</span><span class="sxs-lookup"><span data-stu-id="b58b3-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="b58b3-177">Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b58b3-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58b3-178"><strong>Antwortcode</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-p116">Der SIP-Antwortcode, der gesendet wird, wenn die Konferenz fehlschlägt. Geben Sie den vollständigen Antwortcode ein. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b58b3-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="b58b3-181">400</span><span class="sxs-lookup"><span data-stu-id="b58b3-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58b3-182"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-p117">Der eindeutige Bezeichner (im Format eines ms-diagnostics-Headers), der an eine SIP-Nachricht angehängt ist und häufig Informationen enthält, die bei der Problembehandlung hilfreich sind. Diagnoseheader sind optional (es gibt auch SIP-Sitzungen, die keinen solchen Header enthalten), und Diagnose-IDs werden nur für Sitzungen zurückgegeben, bei denen ein Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b58b3-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b58b3-185">Metriken</span><span class="sxs-lookup"><span data-stu-id="b58b3-185">Metrics</span></span>

<span data-ttu-id="b58b3-186">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über häufigste Fehler angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b58b3-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="b58b3-187">Metriken im Bericht über häufigste Fehler</span><span class="sxs-lookup"><span data-stu-id="b58b3-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b58b3-188">Name</span><span class="sxs-lookup"><span data-stu-id="b58b3-188">Name</span></span></th>
<th><span data-ttu-id="b58b3-189">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="b58b3-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b58b3-190">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b58b3-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b58b3-191"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-192">Ja</span><span class="sxs-lookup"><span data-stu-id="b58b3-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58b3-193">Der relative Rang basierend auf der Anzahl der gemeldeten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b58b3-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58b3-194"><strong>Gemeldete Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-195">Ja</span><span class="sxs-lookup"><span data-stu-id="b58b3-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58b3-196">Die Gesamtzahl der fehlerhaften Sitzungen basierend auf der Diagnose-ID und dem SIP-Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="b58b3-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58b3-197"><strong>Betroffene Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-198">Ja</span><span class="sxs-lookup"><span data-stu-id="b58b3-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58b3-199">Die Gesamtzahl der Benutzer, die von der fehlerhaften Sitzung betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="b58b3-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58b3-200"><strong>Fehlerinformationen</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-201">Nein</span><span class="sxs-lookup"><span data-stu-id="b58b3-201">No</span></span></p></td>
<td><p><span data-ttu-id="b58b3-202">Genaue Angaben zu dem Fehler, u. a. die Diagnose-ID, der SIP-Antwortcode und eine Beschreibung der Ursache des Sitzungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="b58b3-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58b3-203"><strong>Trend in der Vergangenheit</strong></span><span class="sxs-lookup"><span data-stu-id="b58b3-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="b58b3-204">Nein</span><span class="sxs-lookup"><span data-stu-id="b58b3-204">No</span></span></p></td>
<td><p><span data-ttu-id="b58b3-205">Eine grafische Darstellung der fehlerhaften Sitzungen über einen bestimmten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="b58b3-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

