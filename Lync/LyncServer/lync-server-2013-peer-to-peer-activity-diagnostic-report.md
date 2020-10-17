---
title: 'Lync Server 2013: Diagnosebericht über Peer-to-Peer-Aktivität'
description: 'Lync Server 2013: Diagnosebericht über Peer-to-Peer-Aktivitäten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80172c5e0f8b23bf05fad6ec300f0d1ffefb3327
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557351"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="7df79-103">Diagnosebericht über Peer-to-Peer-Aktivitäten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7df79-103">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7df79-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7df79-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7df79-105">Der Diagnosebericht über Peer-zu-Peer-Aktivitäten enthält Informationen dazu, ob die Peer-zu-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="7df79-105">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="7df79-106">Beachten Sie, dass Microsoft lync Server 2013 zwischen verschiedenen Arten von Fehlern unterscheidet:</span><span class="sxs-lookup"><span data-stu-id="7df79-106">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="7df79-107">**Erwarteter Fehler**.</span><span class="sxs-lookup"><span data-stu-id="7df79-107">**Expected failure**.</span></span> <span data-ttu-id="7df79-108">Ein erwarteter Fehler ist normalerweise nur im technischsten Sinn ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="7df79-108">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="7df79-109">Nehmen wir beispielsweise an, Sie rufen jemanden an, aber er ist nicht im Büro und kann das Telefon nicht beantworten.</span><span class="sxs-lookup"><span data-stu-id="7df79-109">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="7df79-110">Da der Anruf nicht beantwortet wurde, wird der Anruf technisch als Fehler betrachtet.</span><span class="sxs-lookup"><span data-stu-id="7df79-110">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="7df79-111">Auf der anderen Seite war dies ein erwarteter Fehler: Microsoft lync Server 2013 erwartet nicht, dass Sie das Telefon beantworten, wenn Sie nicht zur Verfügung stehen, um das Telefon zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="7df79-111">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="7df79-112">Ebenso tritt ein erwarteter Fehler auf, wenn Sie versuchen, eine Sofortnachricht an einen Benutzer zu senden, der offline ist, oder nur an einem Telefon angemeldet ist, das keine Chatnachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7df79-112">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="7df79-113">**Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der gemessen an den Umständen nicht zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="7df79-113">**Unexpected failure**.</span></span> <span data-ttu-id="7df79-114">Angenommen, Sie rufen eine Person an, und die Person kann den Anruf annehmen.</span><span class="sxs-lookup"><span data-stu-id="7df79-114">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="7df79-115">Nehmen wir beispielsweise an, Sie rufen jemanden an, und diese Person steht zur Verfügung, um den Anruf entgegenzunehmen. Wenn lync Server 2013 jedoch versucht, Ihren Anruf an Voicemail weiterzuleiten, schlägt der Anruf fehl, da die Konnektivität mit Exchange Unified Messaging verloren gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="7df79-115">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="7df79-116">Das ist ein unerwarteter Fehler: Es kann davon ausgegangen werden, dass Anrufe immer an die Voicemail weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="7df79-116">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="7df79-117">Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Benutzer oder ähnliche Maßnahmen nicht behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="7df79-117">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="7df79-p104">Beachten Sie, dass die Metriken für "Erfolg", "Erwarteter Fehler" und "Unerwarteter Fehler" nicht zwangsläufig identisch mit der Metrik unter "Sitzungen insgesamt" sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:</span><span class="sxs-lookup"><span data-stu-id="7df79-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7df79-120">Erfolge</span><span class="sxs-lookup"><span data-stu-id="7df79-120">Successes</span></span></th>
<th><span data-ttu-id="7df79-121">Erwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="7df79-121">Expected failures</span></span></th>
<th><span data-ttu-id="7df79-122">Unerwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="7df79-122">Unexpected failures</span></span></th>
<th><span data-ttu-id="7df79-123">Sitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="7df79-123">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7df79-124">2024</span><span class="sxs-lookup"><span data-stu-id="7df79-124">2024</span></span></p></td>
<td><p><span data-ttu-id="7df79-125">469</span><span class="sxs-lookup"><span data-stu-id="7df79-125">469</span></span></p></td>
<td><p><span data-ttu-id="7df79-126">16 </span><span class="sxs-lookup"><span data-stu-id="7df79-126">16</span></span></p></td>
<td><p><span data-ttu-id="7df79-127">2521</span><span class="sxs-lookup"><span data-stu-id="7df79-127">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7df79-128">Wenn Sie 2024 + 469 + 16 hinzufügen, erhalten Sie insgesamt 2.509 Sitzungen, doch in der Spalte Gesamt Sitzungen werden insgesamt 2.521 Sitzungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7df79-128">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="7df79-129">Die "fehlenden" 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder nicht erfolgreich kategorisiert werden konnten.</span><span class="sxs-lookup"><span data-stu-id="7df79-129">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="7df79-130">Dies ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der lync Server nicht vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="7df79-130">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="7df79-131">Wenn dies geschieht, können mit diesem Produkt erstellte Anrufe und das melden dieses Diagnosecodes nicht immer als ein Erfolg, ein erwarteter Fehler oder ein unerwarteter Fehler kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7df79-131">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="7df79-132">Zugreifen auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="7df79-132">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="7df79-133">Auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten greifen Sie über die Homepage für Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="7df79-133">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7df79-134">Sie können auf den [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="7df79-134">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7df79-135">Anzahl der unerwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="7df79-135">Unexpected failure volume</span></span>

  - <span data-ttu-id="7df79-136">Anzahl der erwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="7df79-136">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="7df79-137">Optimales Verwenden des Diagnoseberichts über Peer-zu-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="7df79-137">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="7df79-p107">Es gibt mehrere Möglichkeiten, wie Sie den Diagnosebericht über Peer-zu-Peer-Aktivitäten filtern können, aber die Filteroptionen sind standardmäßig ausgeblendet. Um die verfügbaren Filteroptionen anzuzeigen, klicken Sie im Berichtfenster oben rechts auf die Schaltfläche zum Ein- und Ausblenden der Parameter. Danach können Sie die Filteroptionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7df79-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7df79-141">Filter</span><span class="sxs-lookup"><span data-stu-id="7df79-141">Filters</span></span>

<span data-ttu-id="7df79-p108">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise ansehen. Beispielsweise können Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten nach Kriterien wie etwa Sitzungsmodalität (z. B. Sofortnachrichten, Dateiübertragung oder Anwendungsfreigabe) filtern. Sie können auch auswählen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="7df79-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7df79-146">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7df79-146">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="7df79-147">Filter im Diagnosebericht über Peer-zu-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="7df79-147">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7df79-148">Name</span><span class="sxs-lookup"><span data-stu-id="7df79-148">Name</span></span></th>
<th><span data-ttu-id="7df79-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7df79-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7df79-150"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-150"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-p109">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="7df79-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7df79-153">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="7df79-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7df79-p110">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="7df79-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7df79-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7df79-156">7/7/2012</span></span></p>
<p><span data-ttu-id="7df79-157">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="7df79-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7df79-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7df79-158">7/3/2012</span></span></p>
<p><span data-ttu-id="7df79-159">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="7df79-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df79-160"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-160"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-p111">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="7df79-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7df79-163">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="7df79-163">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7df79-p112">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="7df79-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7df79-166">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7df79-166">7/7/2012</span></span></p>
<p><span data-ttu-id="7df79-167">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="7df79-167">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7df79-168">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7df79-168">7/3/2012</span></span></p>
<p><span data-ttu-id="7df79-169">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="7df79-169">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7df79-170"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-170"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-p113">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7df79-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7df79-173">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="7df79-173">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7df79-174">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="7df79-174">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7df79-175">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="7df79-175">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7df79-176">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="7df79-176">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7df79-p114">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="7df79-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df79-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-p115">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7df79-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7df79-183"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-p116">Gibt den Typ der Kommunikationsaktivität an, die stattgefunden hat. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7df79-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7df79-186">Alle</span><span class="sxs-lookup"><span data-stu-id="7df79-186">[All]</span></span></p></li>
<li><p><span data-ttu-id="7df79-187">Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="7df79-187">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="7df79-188">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="7df79-188">File transfer</span></span></p></li>
<li><p><span data-ttu-id="7df79-189">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="7df79-189">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="7df79-190">Audio</span><span class="sxs-lookup"><span data-stu-id="7df79-190">Audio</span></span></p></li>
<li><p><span data-ttu-id="7df79-191">Video</span><span class="sxs-lookup"><span data-stu-id="7df79-191">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="7df79-192">Metrik (pro Modalität)</span><span class="sxs-lookup"><span data-stu-id="7df79-192">Metrics (per modality)</span></span>

<span data-ttu-id="7df79-193">In der folgenden Tabelle werden die Metriken aufgelistet, die im Diagnosebericht über Peer-zu-Peer-Aktivitäten für jede Modalität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7df79-193">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="7df79-194">Metrik (pro Modalität)</span><span class="sxs-lookup"><span data-stu-id="7df79-194">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7df79-195">Name</span><span class="sxs-lookup"><span data-stu-id="7df79-195">Name</span></span></th>
<th><span data-ttu-id="7df79-196">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="7df79-196">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7df79-197">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7df79-197">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7df79-198"><strong>Anzahl der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-198"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-199">Nein</span><span class="sxs-lookup"><span data-stu-id="7df79-199">No</span></span></p></td>
<td><p><span data-ttu-id="7df79-200">Die Gesamtzahl der erfolgreichen Peer-zu-Peer-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7df79-200">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df79-201"><strong>Prozentsatz der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-201"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-202">Nein</span><span class="sxs-lookup"><span data-stu-id="7df79-202">No</span></span></p></td>
<td><p><span data-ttu-id="7df79-p117">Der Prozentsatz der Peer-zu-Peer-Sitzungen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7df79-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7df79-205"><strong>Anzahl der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-205"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-206">Nein</span><span class="sxs-lookup"><span data-stu-id="7df79-206">No</span></span></p></td>
<td><p><span data-ttu-id="7df79-207">Die Gesamtzahl der Sitzungen, bei denen ein &quot; Erwarteter Fehler &quot; aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7df79-207">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="7df79-p118">Ein erwarteter Fehler ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf Nicht stören festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="7df79-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df79-210"><strong>Prozentsatz der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-210"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-211">Nein</span><span class="sxs-lookup"><span data-stu-id="7df79-211">No</span></span></p></td>
<td><p><span data-ttu-id="7df79-p119">Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7df79-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7df79-214"><strong>Anzahl der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-214"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-215">Nein</span><span class="sxs-lookup"><span data-stu-id="7df79-215">No</span></span></p></td>
<td><p><span data-ttu-id="7df79-216">Die Gesamtzahl der Sitzungen, bei denen ein &quot; unerwarteter Fehler &quot; aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7df79-216">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="7df79-p120">Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7df79-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df79-220"><strong>Prozentsatz der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-220"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-221">Nein</span><span class="sxs-lookup"><span data-stu-id="7df79-221">No</span></span></p></td>
<td><p><span data-ttu-id="7df79-p121">Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7df79-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7df79-224"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="7df79-224"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7df79-225">Nein</span><span class="sxs-lookup"><span data-stu-id="7df79-225">No</span></span></p></td>
<td><p><span data-ttu-id="7df79-226">Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7df79-226">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

