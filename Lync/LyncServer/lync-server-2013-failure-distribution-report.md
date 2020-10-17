---
title: 'Lync Server 2013: Bericht über Fehlerverteilung'
description: 'Lync Server 2013: Bericht über Fehlerverteilung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5a87f779f87d6b7002fa108f1969c33739eed9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564731"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="a9aae-103">Bericht über Fehlerverteilung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9aae-103">Failure Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9aae-104">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a9aae-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a9aae-105">Der Bericht über Fehlerverteilung ordnet Sitzungen, bei denen ein Fehler aufgetreten ist, in folgende Kategorien ein:</span><span class="sxs-lookup"><span data-stu-id="a9aae-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="a9aae-106">Häufigste Diagnosegründe</span><span class="sxs-lookup"><span data-stu-id="a9aae-106">Top diagnostic reasons</span></span>

  - <span data-ttu-id="a9aae-107">Häufigste Modalitäten</span><span class="sxs-lookup"><span data-stu-id="a9aae-107">Top modalities</span></span>

  - <span data-ttu-id="a9aae-108">Häufigste Pools</span><span class="sxs-lookup"><span data-stu-id="a9aae-108">Top pools</span></span>

  - <span data-ttu-id="a9aae-109">Häufigste Quellen</span><span class="sxs-lookup"><span data-stu-id="a9aae-109">Top sources</span></span>

  - <span data-ttu-id="a9aae-110">Häufigste Komponenten</span><span class="sxs-lookup"><span data-stu-id="a9aae-110">Top components</span></span>

  - <span data-ttu-id="a9aae-111">Häufigste Absenderbenutzer</span><span class="sxs-lookup"><span data-stu-id="a9aae-111">Top from users</span></span>

  - <span data-ttu-id="a9aae-112">Häufigste Empfängerbenutzer</span><span class="sxs-lookup"><span data-stu-id="a9aae-112">Top to users</span></span>

  - <span data-ttu-id="a9aae-113">Häufigste Absenderbenutzer-Agents</span><span class="sxs-lookup"><span data-stu-id="a9aae-113">Top from user agents</span></span>

<span data-ttu-id="a9aae-p101">Anhand dieser Kategorien können Sie genau bestimmen, wo ein Problem aufgetreten ist und in einigen Fällen auch die Ursache feststellen. Angenommen, an einem Tag sind bei 242 Audio- und Videositzungen Fehler aufgetreten. Wenn Sie sich den Bericht über Fehlerverteilung ansehen, stellen Sie möglicherweise fest, dass 237 dieser gescheiterten Sitzungen im Dublin-Pool aufgetreten sind. Dies gibt Ihnen einen guten Ausgangspunkt zum Einkreisen der Ursache und Diagnostizieren dieser Fehler. Wenn Sie in der Kategorie **Häufigste Pools** auf den Dublin-Pool klicken, sehen Sie einen Bericht über Fehlerverteilung nur für diesen Pool. Sie können dann mit der Analyse des Dublin-Pools beginnen, um herauszufinden, warum es so viele Schwierigkeiten gab.</span><span class="sxs-lookup"><span data-stu-id="a9aae-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="a9aae-120">Anzeigen des Berichts über Fehlerverteilung</span><span class="sxs-lookup"><span data-stu-id="a9aae-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="a9aae-121">Sie können auf den Bericht über Fehlerverteilung von einem beliebigen der folgenden Berichte zugreifen, indem Sie entweder auf die Metrik **Anzahl der erwarteten Fehler** oder **Anzahl der unerwarteten Fehler** klicken:</span><span class="sxs-lookup"><span data-stu-id="a9aae-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="a9aae-122">Bericht über die häufigsten Fehler in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9aae-122">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="a9aae-123">Konferenz Diagnosebericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9aae-123">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="a9aae-124">Diagnosebericht über Peer-to-Peer-Aktivitäten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9aae-124">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="a9aae-125">Im Bericht über Fehlerverteilung können Sie auf eine der folgenden Metriken klicken, um den [fehlerlistenbericht in lync Server 2013](lync-server-2013-failure-list-report.md)anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="a9aae-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="a9aae-126">Häufigste Diagnosegründe (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="a9aae-126">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="a9aae-127">Häufigste Modalitäten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="a9aae-127">Top modalities (sessions)</span></span>

  - <span data-ttu-id="a9aae-128">Häufigste Pools (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="a9aae-128">Top pools (sessions)</span></span>

  - <span data-ttu-id="a9aae-129">Häufigste Quellen (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="a9aae-129">Top sources (sessions)</span></span>

  - <span data-ttu-id="a9aae-130">Häufigste Komponenten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="a9aae-130">Top components (sessions)</span></span>

  - <span data-ttu-id="a9aae-131">Häufigste Absenderbenutzer (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="a9aae-131">Top from users (sessions)</span></span>

  - <span data-ttu-id="a9aae-132">Häufigste Empfängerbenutzer (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="a9aae-132">Top to users (sessions)</span></span>

  - <span data-ttu-id="a9aae-133">Häufigste Absenderbenutzer-Agents (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="a9aae-133">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="a9aae-134">Verwenden des Berichts über Fehlerverteilung</span><span class="sxs-lookup"><span data-stu-id="a9aae-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="a9aae-p102">Je nach Ihrer Monitorgröße und Bildschirmauflösung werden einige Daten im Bericht über Fehlerverteilung möglicherweise abgeschnitten, wenn Sie auf dem Bildschirm angezeigt werden. Dies ist insbesondere bei Agent-Benutzern der Fall, die sehr lange Bezeichnungen haben können. Auf dem Bildschirm wird ein Benutzer-Agent mit dem Namen "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" z. B. nur teilweise angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a9aae-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="a9aae-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="a9aae-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="a9aae-139">Sie können aber die gesamte Bezeichnung anzeigen, indem Sie die Maus über den gekürzten Wert halten.</span><span class="sxs-lookup"><span data-stu-id="a9aae-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="a9aae-p103">Eine interessante Metrik, nach der Sie im Bericht über Fehlerverteilung filtern können, ist die Diagnose-ID. Wenn Sie dieselbe Diagnose-ID auch in anderen Berichten sehen, können Sie nach dieser ID im Bericht über Fehlerverteilung filtern. Sie erhalten dann einen sehr detaillierten Einblick darüber, wo genau und wie oft diese ID in einer gescheiterten Sitzung gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="a9aae-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a9aae-142">Filter</span><span class="sxs-lookup"><span data-stu-id="a9aae-142">Filters</span></span>

<span data-ttu-id="a9aae-p104">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Bericht über Fehlerverteilung können Sie beispielsweise nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder nach der Diagnose-ID der jeweiligen fehlgeschlagenen Sitzung filtern.</span><span class="sxs-lookup"><span data-stu-id="a9aae-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="a9aae-145">In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Bericht über Fehlerverteilung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a9aae-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="a9aae-146">Bericht über Fehlerverteilung – Filter</span><span class="sxs-lookup"><span data-stu-id="a9aae-146">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-147">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-147">Name</span></span></th>
<th><span data-ttu-id="a9aae-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-p105">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="a9aae-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a9aae-152">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="a9aae-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a9aae-p106">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="a9aae-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a9aae-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a9aae-155">7/7/2012</span></span></p>
<p><span data-ttu-id="a9aae-156">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="a9aae-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a9aae-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a9aae-157">7/3/2012</span></span></p>
<p><span data-ttu-id="a9aae-158">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="a9aae-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-159"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-p107">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="a9aae-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a9aae-162">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="a9aae-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a9aae-p108">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="a9aae-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a9aae-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a9aae-165">7/7/2012</span></span></p>
<p><span data-ttu-id="a9aae-166">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="a9aae-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a9aae-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a9aae-167">7/3/2012</span></span></p>
<p><span data-ttu-id="a9aae-168">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="a9aae-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-169"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-169"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-p109">Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a9aae-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-173"><strong>Aktivitätstyp</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-173"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-p110">Aktivitätstyp, nach dem gefiltert wird. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a9aae-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a9aae-176">Alle</span><span class="sxs-lookup"><span data-stu-id="a9aae-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="a9aae-177">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="a9aae-177">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="a9aae-178">Konferenz</span><span class="sxs-lookup"><span data-stu-id="a9aae-178">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-179"><strong>Sitzungskategorie</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-179"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-p111">Gibt an, ob die betreffende Aktivität erfolgreich war oder nicht. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a9aae-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a9aae-182">Alle</span><span class="sxs-lookup"><span data-stu-id="a9aae-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="a9aae-183">Erfolg</span><span class="sxs-lookup"><span data-stu-id="a9aae-183">Success</span></span></p></li>
<li><p><span data-ttu-id="a9aae-184">Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="a9aae-184">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="a9aae-185">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="a9aae-185">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="a9aae-186">Ein &quot; Erwarteter Fehler &quot; ist ein Fehler, der voraussichtlich eintreten wird.</span><span class="sxs-lookup"><span data-stu-id="a9aae-186">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="a9aae-187">Hat beispielsweise ein Benutzer seinen Status auf "Nicht stören" gesetzt, ist zu erwarten, dass alle Anrufe an diesen Benutzer fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="a9aae-187">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="a9aae-188">Ein &quot; unerwarteter Fehler &quot; ist ein Fehler, der in einem ansonsten fehlerhaften System auftritt.</span><span class="sxs-lookup"><span data-stu-id="a9aae-188">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="a9aae-189">Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet.</span><span class="sxs-lookup"><span data-stu-id="a9aae-189">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="a9aae-190">In diesem Fall würde der Fehler als "unerwartet" gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a9aae-190">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-191"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-p113">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="a9aae-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="a9aae-194">Metriken für die wichtigsten Diagnosegründe</span><span class="sxs-lookup"><span data-stu-id="a9aae-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="a9aae-195">In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf der am häufigsten berichteten Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="a9aae-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="a9aae-196">Metriken für die wichtigsten Diagnosegründe</span><span class="sxs-lookup"><span data-stu-id="a9aae-196">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-197">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-197">Name</span></span></th>
<th><span data-ttu-id="a9aae-198">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="a9aae-198">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a9aae-199">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-200"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-200"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-201">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-201">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-p114">Relative Rangordnung der fehlgeschlagenen Sitzungen basierend auf Diagnose-IDs. Die Diagnose-ID ist eine eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a9aae-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-204"><strong>Wichtigste Diagnosegründe</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-204"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-205">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-205">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-206">In einer Sitzung generierte Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="a9aae-206">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-207"><strong>Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-207"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-208">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-208">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-209">Gesamtanzahl der fehlgeschlagenen Sitzungen, für die die angegebene Diagnose-ID generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a9aae-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="a9aae-210">Metriken für die wichtigsten Modalitäten</span><span class="sxs-lookup"><span data-stu-id="a9aae-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="a9aae-211">In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Sitzungsmodalitäten, bei denen die meisten Fehler auftraten.</span><span class="sxs-lookup"><span data-stu-id="a9aae-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="a9aae-212">Metriken für die wichtigsten Modalitäten</span><span class="sxs-lookup"><span data-stu-id="a9aae-212">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-213">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-213">Name</span></span></th>
<th><span data-ttu-id="a9aae-214">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="a9aae-214">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a9aae-215">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-216"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-216"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-217">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-217">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-218">Relative Rangordnung basierend auf der gescheiterten Sitzung und auf dem Sitzungstyp (z. B. Audio-/Video-Konferenz oder Peer-zu-Peer-Dateiübertragungssitzung).</span><span class="sxs-lookup"><span data-stu-id="a9aae-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-219"><strong>Wichtigste Modalitäten</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-219"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-220">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-220">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-221">Sitzungstyp</span><span class="sxs-lookup"><span data-stu-id="a9aae-221">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-222"><strong>Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-222"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-223">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-223">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-224">Gesamtanzahl der fehlgeschlagenen Sitzungen mit der angegebenen Modalität.</span><span class="sxs-lookup"><span data-stu-id="a9aae-224">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="a9aae-225">Metriken für die wichtigsten Pools</span><span class="sxs-lookup"><span data-stu-id="a9aae-225">Metrics for Top Pools</span></span>

<span data-ttu-id="a9aae-226">In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Pools, bei denen die meisten Fehler auftraten.</span><span class="sxs-lookup"><span data-stu-id="a9aae-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="a9aae-227">Metriken für die wichtigsten Pools</span><span class="sxs-lookup"><span data-stu-id="a9aae-227">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-228">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-228">Name</span></span></th>
<th><span data-ttu-id="a9aae-229">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="a9aae-229">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a9aae-230">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-230">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-231"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-231"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-232">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-232">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-233">Relative Rangfolge der fehlgeschlagenen Sitzungen basierend auf dem registrierungsstellenpool oder Edgeserver, in der die Sitzung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a9aae-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-234"><strong>Wichtigste Pools</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-234"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-235">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-235">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-236">Name des registrierungspools oder Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="a9aae-236">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-237"><strong>Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-237"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-238">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-238">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-239">Die Gesamtzahl der fehlgeschlagenen Sitzungen pro registrierungsstellenpool oder Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="a9aae-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="a9aae-240">Metriken für die wichtigsten Quellen</span><span class="sxs-lookup"><span data-stu-id="a9aae-240">Metrics for Top Sources</span></span>

<span data-ttu-id="a9aae-241">In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Computern, bei denen die meisten Fehler auftraten.</span><span class="sxs-lookup"><span data-stu-id="a9aae-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="a9aae-242">Metriken für die wichtigsten Quellen</span><span class="sxs-lookup"><span data-stu-id="a9aae-242">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-243">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-243">Name</span></span></th>
<th><span data-ttu-id="a9aae-244">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="a9aae-244">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a9aae-245">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-245">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-246"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-246"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-247">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-247">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-248">Relative Rangordnung der fehlgeschlagenen Sitzungen pro Computer.</span><span class="sxs-lookup"><span data-stu-id="a9aae-248">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-249"><strong>Wichtigste Quellen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-249"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-250">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-250">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-251">Name des Computers, auf dem die Sitzung fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="a9aae-251">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-252"><strong>Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-252"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-253">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-253">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-254">Gesamtanzahl der fehlgeschlagenen Sitzungen pro Computer.</span><span class="sxs-lookup"><span data-stu-id="a9aae-254">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="a9aae-255">Metriken für die wichtigsten Komponenten</span><span class="sxs-lookup"><span data-stu-id="a9aae-255">Metrics for Top Components</span></span>

<span data-ttu-id="a9aae-256">In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Microsoft lync Server 2010-Komponenten, bei denen die meisten Fehler auftraten.</span><span class="sxs-lookup"><span data-stu-id="a9aae-256">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="a9aae-257">Metriken für die wichtigsten Komponenten</span><span class="sxs-lookup"><span data-stu-id="a9aae-257">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-258">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-258">Name</span></span></th>
<th><span data-ttu-id="a9aae-259">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="a9aae-259">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a9aae-260">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-260">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-261"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-261"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-262">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-262">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-263">Relative Rangfolge der fehlgeschlagenen Sitzungen basierend auf lync Server 2010-Komponente (beispielsweise ExumRouting, GroupChat oder MediationServer).</span><span class="sxs-lookup"><span data-stu-id="a9aae-263">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-264"><strong>Wichtigste Komponenten</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-264"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-265">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-265">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-266">Name der für die fehlgeschlagene Sitzung verwendeten Komponente.</span><span class="sxs-lookup"><span data-stu-id="a9aae-266">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-267"><strong>Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-267"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-268">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-268">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-269">Gesamtanzahl der fehlgeschlagenen Sitzungen pro Komponente.</span><span class="sxs-lookup"><span data-stu-id="a9aae-269">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="a9aae-270">Metriken für die wichtigsten "Von Benutzer"</span><span class="sxs-lookup"><span data-stu-id="a9aae-270">Metrics for Top From Users</span></span>

<span data-ttu-id="a9aae-271">In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Benutzern, bei denen beim Versuch, jemanden anzurufen, die meisten Fehler auftraten (als "Von Benutzer" bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="a9aae-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="a9aae-272">Metriken für die wichtigsten "Von Benutzer"</span><span class="sxs-lookup"><span data-stu-id="a9aae-272">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-273">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-273">Name</span></span></th>
<th><span data-ttu-id="a9aae-274">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="a9aae-274">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a9aae-275">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-276"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-276"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-277">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-277">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-278">Relative Rangordnung der fehlgeschlagenen Sitzungen basierend auf dem Benutzer, der zur Teilnahme an der Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a9aae-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-279"><strong>Wichtigste "Von Benutzer"</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-279"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-280">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-280">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-281">SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a9aae-281">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-282"><strong>Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-282"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-283">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-283">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-284">Gesamtanzahl der fehlgeschlagenen Sitzungen pro Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a9aae-284">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="a9aae-285">Metriken für die wichtigsten "An Benutzer"</span><span class="sxs-lookup"><span data-stu-id="a9aae-285">Metrics for Top To Users</span></span>

<span data-ttu-id="a9aae-286">In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Benutzern, bei denen die meisten Fehler auftraten, wenn sie von einem anderen Benutzer angerufen wurden (als "An Benutzer" bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="a9aae-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-287">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-287">Name</span></span></th>
<th><span data-ttu-id="a9aae-288">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="a9aae-288">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a9aae-289">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-289">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-290"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-290"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-291">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-291">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-292">Relative Rangordnung der fehlgeschlagenen Sitzungen basierend auf dem Benutzer, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="a9aae-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-293"><strong>Wichtigste "An Benutzer"</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-293"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-294">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-294">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-295">SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="a9aae-295">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-296"><strong>Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-296"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-297">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-297">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-298">Gesamtanzahl der fehlgeschlagenen Sitzungen pro Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a9aae-298">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="a9aae-299">Metriken für die wichtigsten Benutzer-Agents</span><span class="sxs-lookup"><span data-stu-id="a9aae-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="a9aae-300">In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf der Endpunktsoftware, bei der die meisten Fehler auftraten.</span><span class="sxs-lookup"><span data-stu-id="a9aae-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="a9aae-301">Metriken für die wichtigsten Benutzer-Agents</span><span class="sxs-lookup"><span data-stu-id="a9aae-301">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9aae-302">Name</span><span class="sxs-lookup"><span data-stu-id="a9aae-302">Name</span></span></th>
<th><span data-ttu-id="a9aae-303">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="a9aae-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a9aae-304">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9aae-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-305"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-305"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-306">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-306">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-p115">Relative Rangordnung der fehlgeschlagenen Sitzungen basierend auf dem in der Sitzung verwendeten Benutzer-Agent (Software), z. B. RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="a9aae-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9aae-309"><strong>Wichtigste Benutzer-Agents</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-309"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-310">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-310">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-311">Name des in der fehlgeschlagenen Sitzung verwendeten Benutzer-Agent.</span><span class="sxs-lookup"><span data-stu-id="a9aae-311">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9aae-312"><strong>Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="a9aae-312"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a9aae-313">Nein</span><span class="sxs-lookup"><span data-stu-id="a9aae-313">No</span></span></p></td>
<td><p><span data-ttu-id="a9aae-314">Gesamtanzahl der fehlgeschlagenen Sitzungen pro Benutzer-Agent.</span><span class="sxs-lookup"><span data-stu-id="a9aae-314">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

