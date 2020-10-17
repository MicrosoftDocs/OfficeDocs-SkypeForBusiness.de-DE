---
title: 'Lync Server 2013: Diagnosebericht über Peer-to-Peer-Aktivität'
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
ms.openlocfilehash: 53e47232a6345749f78f6136929209722a83621e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524392"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="b2f14-102">Diagnosebericht über Peer-to-Peer-Aktivitäten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2f14-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2f14-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b2f14-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b2f14-104">Der Diagnosebericht über Peer-zu-Peer-Aktivitäten enthält Informationen dazu, ob die Peer-zu-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="b2f14-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="b2f14-105">Beachten Sie, dass Microsoft lync Server 2013 zwischen verschiedenen Arten von Fehlern unterscheidet:</span><span class="sxs-lookup"><span data-stu-id="b2f14-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="b2f14-106">**Erwarteter Fehler**.</span><span class="sxs-lookup"><span data-stu-id="b2f14-106">**Expected failure**.</span></span> <span data-ttu-id="b2f14-107">Ein erwarteter Fehler ist normalerweise nur im technischsten Sinn ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="b2f14-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="b2f14-108">Nehmen wir beispielsweise an, Sie rufen jemanden an, aber er ist nicht im Büro und kann das Telefon nicht beantworten.</span><span class="sxs-lookup"><span data-stu-id="b2f14-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="b2f14-109">Da der Anruf nicht beantwortet wurde, wird der Anruf technisch als Fehler betrachtet.</span><span class="sxs-lookup"><span data-stu-id="b2f14-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="b2f14-110">Auf der anderen Seite war dies ein erwarteter Fehler: Microsoft lync Server 2013 erwartet nicht, dass Sie das Telefon beantworten, wenn Sie nicht zur Verfügung stehen, um das Telefon zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="b2f14-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="b2f14-111">Ebenso tritt ein erwarteter Fehler auf, wenn Sie versuchen, eine Sofortnachricht an einen Benutzer zu senden, der offline ist, oder nur an einem Telefon angemeldet ist, das keine Chatnachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b2f14-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="b2f14-112">**Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der gemessen an den Umständen nicht zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="b2f14-112">**Unexpected failure**.</span></span> <span data-ttu-id="b2f14-113">Angenommen, Sie rufen eine Person an, und die Person kann den Anruf annehmen.</span><span class="sxs-lookup"><span data-stu-id="b2f14-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="b2f14-114">Nehmen wir beispielsweise an, Sie rufen jemanden an, und diese Person steht zur Verfügung, um den Anruf entgegenzunehmen. Wenn lync Server 2013 jedoch versucht, Ihren Anruf an Voicemail weiterzuleiten, schlägt der Anruf fehl, da die Konnektivität mit Exchange Unified Messaging verloren gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="b2f14-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="b2f14-115">Das ist ein unerwarteter Fehler: Es kann davon ausgegangen werden, dass Anrufe immer an die Voicemail weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="b2f14-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="b2f14-116">Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Benutzer oder ähnliche Maßnahmen nicht behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="b2f14-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="b2f14-p104">Beachten Sie, dass die Metriken für "Erfolg", "Erwarteter Fehler" und "Unerwarteter Fehler" nicht zwangsläufig identisch mit der Metrik unter "Sitzungen insgesamt" sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:</span><span class="sxs-lookup"><span data-stu-id="b2f14-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2f14-119">Erfolge</span><span class="sxs-lookup"><span data-stu-id="b2f14-119">Successes</span></span></th>
<th><span data-ttu-id="b2f14-120">Erwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="b2f14-120">Expected failures</span></span></th>
<th><span data-ttu-id="b2f14-121">Unerwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="b2f14-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="b2f14-122">Sitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="b2f14-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2f14-123">2024</span><span class="sxs-lookup"><span data-stu-id="b2f14-123">2024</span></span></p></td>
<td><p><span data-ttu-id="b2f14-124">469</span><span class="sxs-lookup"><span data-stu-id="b2f14-124">469</span></span></p></td>
<td><p><span data-ttu-id="b2f14-125">16 </span><span class="sxs-lookup"><span data-stu-id="b2f14-125">16</span></span></p></td>
<td><p><span data-ttu-id="b2f14-126">2521</span><span class="sxs-lookup"><span data-stu-id="b2f14-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b2f14-127">Wenn Sie 2024 + 469 + 16 hinzufügen, erhalten Sie insgesamt 2.509 Sitzungen, doch in der Spalte Gesamt Sitzungen werden insgesamt 2.521 Sitzungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2f14-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="b2f14-128">Die "fehlenden" 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder nicht erfolgreich kategorisiert werden konnten.</span><span class="sxs-lookup"><span data-stu-id="b2f14-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="b2f14-129">Dies ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der lync Server nicht vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="b2f14-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="b2f14-130">Wenn dies geschieht, können mit diesem Produkt erstellte Anrufe und das melden dieses Diagnosecodes nicht immer als ein Erfolg, ein erwarteter Fehler oder ein unerwarteter Fehler kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b2f14-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="b2f14-131">Zugreifen auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="b2f14-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="b2f14-132">Auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten greifen Sie über die Homepage für Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="b2f14-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="b2f14-133">Sie können auf den [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="b2f14-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b2f14-134">Anzahl der unerwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="b2f14-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="b2f14-135">Anzahl der erwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="b2f14-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="b2f14-136">Optimales Verwenden des Diagnoseberichts über Peer-zu-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="b2f14-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="b2f14-p107">Es gibt mehrere Möglichkeiten, wie Sie den Diagnosebericht über Peer-zu-Peer-Aktivitäten filtern können, aber die Filteroptionen sind standardmäßig ausgeblendet. Um die verfügbaren Filteroptionen anzuzeigen, klicken Sie im Berichtfenster oben rechts auf die Schaltfläche zum Ein- und Ausblenden der Parameter. Danach können Sie die Filteroptionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2f14-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b2f14-140">Filter</span><span class="sxs-lookup"><span data-stu-id="b2f14-140">Filters</span></span>

<span data-ttu-id="b2f14-p108">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise ansehen. Beispielsweise können Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten nach Kriterien wie etwa Sitzungsmodalität (z. B. Sofortnachrichten, Dateiübertragung oder Anwendungsfreigabe) filtern. Sie können auch auswählen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b2f14-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b2f14-145">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b2f14-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="b2f14-146">Filter im Diagnosebericht über Peer-zu-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="b2f14-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2f14-147">Name</span><span class="sxs-lookup"><span data-stu-id="b2f14-147">Name</span></span></th>
<th><span data-ttu-id="b2f14-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2f14-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2f14-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-p109">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="b2f14-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b2f14-152">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="b2f14-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b2f14-p110">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="b2f14-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b2f14-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b2f14-155">7/7/2012</span></span></p>
<p><span data-ttu-id="b2f14-156">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="b2f14-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b2f14-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b2f14-157">7/3/2012</span></span></p>
<p><span data-ttu-id="b2f14-158">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="b2f14-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2f14-159"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-p111">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="b2f14-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b2f14-162">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="b2f14-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b2f14-p112">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="b2f14-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b2f14-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b2f14-165">7/7/2012</span></span></p>
<p><span data-ttu-id="b2f14-166">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="b2f14-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b2f14-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b2f14-167">7/3/2012</span></span></p>
<p><span data-ttu-id="b2f14-168">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="b2f14-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2f14-169"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-p113">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b2f14-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2f14-172">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="b2f14-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b2f14-173">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="b2f14-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b2f14-174">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="b2f14-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b2f14-175">Monatlich (maximal 12 Monate werden angezeigt)</span><span class="sxs-lookup"><span data-stu-id="b2f14-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b2f14-p114">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="b2f14-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2f14-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-p115">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b2f14-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2f14-182"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-p116">Gibt den Typ der Kommunikationsaktivität an, die stattgefunden hat. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b2f14-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2f14-185">Alle</span><span class="sxs-lookup"><span data-stu-id="b2f14-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="b2f14-186">Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="b2f14-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="b2f14-187">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="b2f14-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="b2f14-188">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="b2f14-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="b2f14-189">Audio</span><span class="sxs-lookup"><span data-stu-id="b2f14-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="b2f14-190">Video</span><span class="sxs-lookup"><span data-stu-id="b2f14-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="b2f14-191">Metrik (pro Modalität)</span><span class="sxs-lookup"><span data-stu-id="b2f14-191">Metrics (per modality)</span></span>

<span data-ttu-id="b2f14-192">In der folgenden Tabelle werden die Metriken aufgelistet, die im Diagnosebericht über Peer-zu-Peer-Aktivitäten für jede Modalität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b2f14-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="b2f14-193">Metrik (pro Modalität)</span><span class="sxs-lookup"><span data-stu-id="b2f14-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2f14-194">Name</span><span class="sxs-lookup"><span data-stu-id="b2f14-194">Name</span></span></th>
<th><span data-ttu-id="b2f14-195">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="b2f14-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2f14-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2f14-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2f14-197"><strong>Anzahl der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-198">Nein</span><span class="sxs-lookup"><span data-stu-id="b2f14-198">No</span></span></p></td>
<td><p><span data-ttu-id="b2f14-199">Die Gesamtzahl der erfolgreichen Peer-zu-Peer-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b2f14-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2f14-200"><strong>Prozentsatz der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-201">Nein</span><span class="sxs-lookup"><span data-stu-id="b2f14-201">No</span></span></p></td>
<td><p><span data-ttu-id="b2f14-p117">Der Prozentsatz der Peer-zu-Peer-Sitzungen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b2f14-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2f14-204"><strong>Anzahl der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-205">Nein</span><span class="sxs-lookup"><span data-stu-id="b2f14-205">No</span></span></p></td>
<td><p><span data-ttu-id="b2f14-206">Die Gesamtzahl der Sitzungen, bei denen ein &quot; Erwarteter Fehler &quot; aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b2f14-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="b2f14-p118">Ein erwarteter Fehler ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf Nicht stören festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="b2f14-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2f14-209"><strong>Prozentsatz der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-210">Nein</span><span class="sxs-lookup"><span data-stu-id="b2f14-210">No</span></span></p></td>
<td><p><span data-ttu-id="b2f14-p119">Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b2f14-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2f14-213"><strong>Anzahl der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-214">Nein</span><span class="sxs-lookup"><span data-stu-id="b2f14-214">No</span></span></p></td>
<td><p><span data-ttu-id="b2f14-215">Die Gesamtzahl der Sitzungen, bei denen ein &quot; unerwarteter Fehler &quot; aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b2f14-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="b2f14-p120">Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b2f14-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2f14-219"><strong>Prozentsatz der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-220">Nein</span><span class="sxs-lookup"><span data-stu-id="b2f14-220">No</span></span></p></td>
<td><p><span data-ttu-id="b2f14-p121">Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b2f14-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2f14-223"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="b2f14-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2f14-224">Nein</span><span class="sxs-lookup"><span data-stu-id="b2f14-224">No</span></span></p></td>
<td><p><span data-ttu-id="b2f14-225">Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b2f14-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

