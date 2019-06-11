---
title: 'Lync Server 2013: Diagnosebericht zur Peer-to-Peer-Aktivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f435a4b0ff0ec42e8898260c3ada528963bbebb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="03f2d-102">Diagnosebericht zur Peer-to-Peer-Aktivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03f2d-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03f2d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="03f2d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="03f2d-104">Der Diagnosebericht über Peer-to-Peer-Aktivitäten enthält Informationen dazu, ob Ihre Peer-to-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="03f2d-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="03f2d-105">Beachten Sie, dass Microsoft lync Server 2013 zwischen verschiedenen Arten von Fehlern unterscheidet:</span><span class="sxs-lookup"><span data-stu-id="03f2d-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="03f2d-106">**Erwarteter Fehler**.</span><span class="sxs-lookup"><span data-stu-id="03f2d-106">**Expected failure**.</span></span> <span data-ttu-id="03f2d-107">Ein erwarteter Fehler ist in der Regel ein Fehler nur im technisch Sinn.</span><span class="sxs-lookup"><span data-stu-id="03f2d-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="03f2d-108">Nehmen Sie beispielsweise an, dass Sie jemanden anrufen, aber er oder Sie nicht im Büro ist und das Telefon nicht annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="03f2d-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="03f2d-109">Da der Anruf nicht beantwortet wurde, wird der Anruf technisch als fehlerhaft eingestuft.</span><span class="sxs-lookup"><span data-stu-id="03f2d-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="03f2d-110">Auf der anderen Seite war dies ein erwarteter Fehler: Microsoft lync Server 2013 erwartet nicht, dass Sie das Telefon annehmen, wenn Sie nicht zur Beantwortung des Telefons verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="03f2d-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="03f2d-111">Ebenso tritt ein erwarteter Fehler auf, wenn Sie versuchen, eine Sofortnachricht an einen Benutzer zu senden, der offline ist, oder nur an einem Telefon angemeldet ist, das keine Chatnachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="03f2d-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="03f2d-112">**Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der unter den gegebenen Umständen nicht zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="03f2d-112">**Unexpected failure**.</span></span> <span data-ttu-id="03f2d-113">Wie der Name schon sagt, ist ein unerwarteter Fehler ein Fehler, dessen Auftreten Sie unter gegebenen Umständen nicht erwarten würden.</span><span class="sxs-lookup"><span data-stu-id="03f2d-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="03f2d-114">Nehmen wir beispielsweise an, dass Sie jemanden anrufen und diese Person zur Beantwortung des Anrufs zur Verfügung steht. Wenn lync Server 2013 jedoch versucht, Ihren Anruf an Voicemail weiterzuleiten, schlägt der Anruf fehl, da die Konnektivität zu Exchange Unified Messaging verloren gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="03f2d-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="03f2d-115">Das ist ein unerwarteter Fehler: Sie erwarten, dass Anrufe immer an Voicemail weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="03f2d-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="03f2d-116">Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Nutzer oder ähnliche Maßnahmen wahrscheinlich nicht behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="03f2d-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="03f2d-p104">Beachten Sie, dass die Metriken für „Erfolg“, „Erwarteter Fehler“ und „Unerwarteter Fehler“ nicht zwangsläufig identisch mit der Metrik unter „Sitzungen insgesamt“ sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:</span><span class="sxs-lookup"><span data-stu-id="03f2d-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f2d-119">Erfolge</span><span class="sxs-lookup"><span data-stu-id="03f2d-119">Successes</span></span></th>
<th><span data-ttu-id="03f2d-120">Erwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="03f2d-120">Expected failures</span></span></th>
<th><span data-ttu-id="03f2d-121">Unerwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="03f2d-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="03f2d-122">Sitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="03f2d-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f2d-123">2024</span><span class="sxs-lookup"><span data-stu-id="03f2d-123">2024</span></span></p></td>
<td><p><span data-ttu-id="03f2d-124">469</span><span class="sxs-lookup"><span data-stu-id="03f2d-124">469</span></span></p></td>
<td><p><span data-ttu-id="03f2d-125">16</span><span class="sxs-lookup"><span data-stu-id="03f2d-125">16</span></span></p></td>
<td><p><span data-ttu-id="03f2d-126">2521</span><span class="sxs-lookup"><span data-stu-id="03f2d-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03f2d-127">Wenn Sie 2024 + 469 + 16 addieren, ergibt das insgesamt 2.509 Sitzungen, aber in der Spalte „Sitzungen insgesamt“ wird 2.521 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03f2d-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="03f2d-128">Die „fehlenden“ 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder fehlerhaft eingestuft werden konnten.</span><span class="sxs-lookup"><span data-stu-id="03f2d-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="03f2d-129">Dies ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der lync Server nicht vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="03f2d-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="03f2d-130">In einer solchen Situation können Aufrufe, die mit diesem Produkt ausgeführt werden und für die dieser Diagnosecode gemeldet wird, nicht immer eindeutig als Erfolg, erwarteter Fehler oder unerwarteter Fehler kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="03f2d-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="03f2d-131">Zugreifen auf den Diagnosebericht über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="03f2d-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="03f2d-132">Auf den Diagnosebericht über Peer-to-Peer-Aktivitäten greifen Sie über die Startseite für Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="03f2d-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="03f2d-133">Sie können auf den [Bericht Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="03f2d-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="03f2d-134">Anzahl der unerwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="03f2d-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="03f2d-135">Anzahl der erwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="03f2d-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="03f2d-136">Optimales Verwenden des Diagnoseberichts über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="03f2d-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="03f2d-p107">Es gibt mehrere Möglichkeiten, wie Sie den Diagnosebericht über Peer-to-Peer-Aktivitäten filtern können, aber die Filteroptionen sind standardmäßig ausgeblendet. Um die verfügbaren Filteroptionen anzuzeigen, klicken Sie im Berichtfenster oben rechts auf die Schaltfläche zum Ein- und Ausblenden der Parameter. Danach können Sie die Filteroptionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="03f2d-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="03f2d-140">Filter</span><span class="sxs-lookup"><span data-stu-id="03f2d-140">Filters</span></span>

<span data-ttu-id="03f2d-p108">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise ansehen. Beispielsweise können Sie im Diagnosebericht über Peer-to-Peer-Aktivitäten nach Kriterien wie etwa Sitzungsmodalität (z. B. Sofortnachrichten, Dateiübertragung oder Anwendungsfreigabe) filtern. Sie können auch auswählen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="03f2d-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="03f2d-145">In der folgenden Tabelle sind die Filter aufgelistet, die Sie im Diagnosebericht über Peer-to-Peer-Aktivitäten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="03f2d-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="03f2d-146">Filter im Diagnosebericht über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="03f2d-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f2d-147">Name</span><span class="sxs-lookup"><span data-stu-id="03f2d-147">Name</span></span></th>
<th><span data-ttu-id="03f2d-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03f2d-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f2d-149"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-p109">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="03f2d-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="03f2d-152">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="03f2d-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="03f2d-p110">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="03f2d-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="03f2d-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="03f2d-155">7/7/2012</span></span></p>
<p><span data-ttu-id="03f2d-156">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="03f2d-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="03f2d-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="03f2d-157">7/3/2012</span></span></p>
<p><span data-ttu-id="03f2d-158">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="03f2d-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f2d-159"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-p111">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="03f2d-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="03f2d-162">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="03f2d-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="03f2d-p112">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="03f2d-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="03f2d-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="03f2d-165">7/7/2012</span></span></p>
<p><span data-ttu-id="03f2d-166">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="03f2d-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="03f2d-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="03f2d-167">7/3/2012</span></span></p>
<p><span data-ttu-id="03f2d-168">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="03f2d-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f2d-169"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-p113">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="03f2d-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="03f2d-172">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="03f2d-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="03f2d-173">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="03f2d-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="03f2d-174">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="03f2d-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="03f2d-175">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="03f2d-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="03f2d-176">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03f2d-176">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="03f2d-177">Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="03f2d-177">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f2d-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-p115">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="03f2d-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f2d-182"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-p116">Gibt den Typ der Kommunikationsaktivität an, die stattgefunden hat. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="03f2d-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="03f2d-185">[Alle]</span><span class="sxs-lookup"><span data-stu-id="03f2d-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="03f2d-186">Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="03f2d-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="03f2d-187">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="03f2d-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="03f2d-188">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="03f2d-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="03f2d-189">Audio</span><span class="sxs-lookup"><span data-stu-id="03f2d-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="03f2d-190">Video</span><span class="sxs-lookup"><span data-stu-id="03f2d-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="03f2d-191">Metrik (pro Modalität)</span><span class="sxs-lookup"><span data-stu-id="03f2d-191">Metrics (per modality)</span></span>

<span data-ttu-id="03f2d-192">In der folgenden Tabelle sind die Metriken aufgelistet, die im Diagnosebericht über Peer-to-Peer-Aktivitäten für jede Modalität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="03f2d-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="03f2d-193">Metrik (pro Modalität)</span><span class="sxs-lookup"><span data-stu-id="03f2d-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f2d-194">Name</span><span class="sxs-lookup"><span data-stu-id="03f2d-194">Name</span></span></th>
<th><span data-ttu-id="03f2d-195">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="03f2d-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="03f2d-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03f2d-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f2d-197"><strong>Anzahl der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-198">Nein</span><span class="sxs-lookup"><span data-stu-id="03f2d-198">No</span></span></p></td>
<td><p><span data-ttu-id="03f2d-199">Die Gesamtzahl der erfolgreichen Peer-to-Peer-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="03f2d-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f2d-200"><strong>Prozentsatz der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-201">Nein</span><span class="sxs-lookup"><span data-stu-id="03f2d-201">No</span></span></p></td>
<td><p><span data-ttu-id="03f2d-p117">Der Prozentsatz der Peer-to-Peer-Sitzungen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="03f2d-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f2d-204"><strong>Anzahl der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-205">Nein</span><span class="sxs-lookup"><span data-stu-id="03f2d-205">No</span></span></p></td>
<td><p><span data-ttu-id="03f2d-206">Die Gesamtzahl der Sitzungen, &quot;bei denen&quot; ein erwarteter Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="03f2d-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="03f2d-p118">Ein erwarteter Fehler ist ein Fehler, der zu erwarten ist. Wenn beispielsweise ein Benutzer seinen Status auf „Nicht stören“ festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="03f2d-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f2d-209"><strong>Prozentsatz der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-210">Nein</span><span class="sxs-lookup"><span data-stu-id="03f2d-210">No</span></span></p></td>
<td><p><span data-ttu-id="03f2d-p119">Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="03f2d-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f2d-213"><strong>Anzahl der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-214">Nein</span><span class="sxs-lookup"><span data-stu-id="03f2d-214">No</span></span></p></td>
<td><p><span data-ttu-id="03f2d-215">Die Gesamtzahl der Sitzungen, &quot;bei denen&quot; ein unerwarteter Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="03f2d-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="03f2d-p120">Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="03f2d-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f2d-219"><strong>Prozentsatz der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-220">Nein</span><span class="sxs-lookup"><span data-stu-id="03f2d-220">No</span></span></p></td>
<td><p><span data-ttu-id="03f2d-p121">Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="03f2d-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f2d-223"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="03f2d-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="03f2d-224">Nein</span><span class="sxs-lookup"><span data-stu-id="03f2d-224">No</span></span></p></td>
<td><p><span data-ttu-id="03f2d-225">Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="03f2d-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

