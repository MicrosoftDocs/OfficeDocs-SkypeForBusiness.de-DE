---
title: 'Lync Server 2013: Diagnosebericht zur Peer-to-Peer-Aktivität'
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
ms.openlocfilehash: dc98f1c81f79605da2de2b06397d8a23d8086861
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="4097b-102">Diagnosebericht zur Peer-to-Peer-Aktivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4097b-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4097b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4097b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4097b-104">Der Diagnosebericht über Peer-to-Peer-Aktivitäten enthält Informationen dazu, ob Ihre Peer-to-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="4097b-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="4097b-105">Beachten Sie, dass Microsoft lync Server 2013 zwischen verschiedenen Arten von Fehlern unterscheidet:</span><span class="sxs-lookup"><span data-stu-id="4097b-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="4097b-106">**Erwarteter Fehler**.</span><span class="sxs-lookup"><span data-stu-id="4097b-106">**Expected failure**.</span></span> <span data-ttu-id="4097b-107">Ein erwarteter Fehler ist in der Regel ein Fehler nur im technisch Sinn.</span><span class="sxs-lookup"><span data-stu-id="4097b-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="4097b-108">Nehmen Sie beispielsweise an, dass Sie jemanden anrufen, aber er oder Sie nicht im Büro ist und das Telefon nicht annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="4097b-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="4097b-109">Da der Anruf nicht beantwortet wurde, wird der Anruf technisch als fehlerhaft eingestuft.</span><span class="sxs-lookup"><span data-stu-id="4097b-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="4097b-110">Auf der anderen Seite war dies ein erwarteter Fehler: Microsoft lync Server 2013 erwartet nicht, dass Sie das Telefon annehmen, wenn Sie nicht zur Beantwortung des Telefons verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4097b-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="4097b-111">Ebenso tritt ein erwarteter Fehler auf, wenn Sie versuchen, eine Sofortnachricht an einen Benutzer zu senden, der offline ist, oder nur an einem Telefon angemeldet ist, das keine Chatnachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4097b-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="4097b-112">**Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der unter den gegebenen Umständen nicht zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="4097b-112">**Unexpected failure**.</span></span> <span data-ttu-id="4097b-113">Wie der Name schon sagt, ist ein unerwarteter Fehler ein Fehler, dessen Auftreten Sie unter gegebenen Umständen nicht erwarten würden.</span><span class="sxs-lookup"><span data-stu-id="4097b-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="4097b-114">Nehmen wir beispielsweise an, dass Sie jemanden anrufen und diese Person zur Beantwortung des Anrufs zur Verfügung steht. Wenn lync Server 2013 jedoch versucht, Ihren Anruf an Voicemail weiterzuleiten, schlägt der Anruf fehl, da die Konnektivität zu Exchange Unified Messaging verloren gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="4097b-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="4097b-115">Das ist ein unerwarteter Fehler: Sie erwarten, dass Anrufe immer an Voicemail weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="4097b-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="4097b-116">Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Nutzer oder ähnliche Maßnahmen wahrscheinlich nicht behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="4097b-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="4097b-p104">Beachten Sie, dass die Metriken für „Erfolg“, „Erwarteter Fehler“ und „Unerwarteter Fehler“ nicht zwangsläufig identisch mit der Metrik unter „Sitzungen insgesamt“ sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:</span><span class="sxs-lookup"><span data-stu-id="4097b-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4097b-119">Erfolge</span><span class="sxs-lookup"><span data-stu-id="4097b-119">Successes</span></span></th>
<th><span data-ttu-id="4097b-120">Erwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="4097b-120">Expected failures</span></span></th>
<th><span data-ttu-id="4097b-121">Unerwartete Fehler</span><span class="sxs-lookup"><span data-stu-id="4097b-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="4097b-122">Sitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="4097b-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4097b-123">2024</span><span class="sxs-lookup"><span data-stu-id="4097b-123">2024</span></span></p></td>
<td><p><span data-ttu-id="4097b-124">469</span><span class="sxs-lookup"><span data-stu-id="4097b-124">469</span></span></p></td>
<td><p><span data-ttu-id="4097b-125">16</span><span class="sxs-lookup"><span data-stu-id="4097b-125">16</span></span></p></td>
<td><p><span data-ttu-id="4097b-126">2521</span><span class="sxs-lookup"><span data-stu-id="4097b-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4097b-127">Wenn Sie 2024 + 469 + 16 addieren, ergibt das insgesamt 2.509 Sitzungen, aber in der Spalte „Sitzungen insgesamt“ wird 2.521 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4097b-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="4097b-128">Die „fehlenden“ 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder fehlerhaft eingestuft werden konnten.</span><span class="sxs-lookup"><span data-stu-id="4097b-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="4097b-129">Dies ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der lync Server nicht vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="4097b-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="4097b-130">In einer solchen Situation können Aufrufe, die mit diesem Produkt ausgeführt werden und für die dieser Diagnosecode gemeldet wird, nicht immer eindeutig als Erfolg, erwarteter Fehler oder unerwarteter Fehler kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="4097b-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="4097b-131">Zugreifen auf den Diagnosebericht über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="4097b-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="4097b-132">Auf den Diagnosebericht über Peer-to-Peer-Aktivitäten greifen Sie über die Startseite für Überwachungsberichte zu.</span><span class="sxs-lookup"><span data-stu-id="4097b-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4097b-133">Sie können auf den [Bericht Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="4097b-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4097b-134">Anzahl der unerwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="4097b-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="4097b-135">Anzahl der erwarteten Fehler</span><span class="sxs-lookup"><span data-stu-id="4097b-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="4097b-136">Optimales Verwenden des Diagnoseberichts über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="4097b-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="4097b-p107">Es gibt mehrere Möglichkeiten, wie Sie den Diagnosebericht über Peer-to-Peer-Aktivitäten filtern können, aber die Filteroptionen sind standardmäßig ausgeblendet. Um die verfügbaren Filteroptionen anzuzeigen, klicken Sie im Berichtfenster oben rechts auf die Schaltfläche zum Ein- und Ausblenden der Parameter. Danach können Sie die Filteroptionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4097b-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4097b-140">Filter</span><span class="sxs-lookup"><span data-stu-id="4097b-140">Filters</span></span>

<span data-ttu-id="4097b-p108">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise ansehen. Beispielsweise können Sie im Diagnosebericht über Peer-to-Peer-Aktivitäten nach Kriterien wie etwa Sitzungsmodalität (z. B. Sofortnachrichten, Dateiübertragung oder Anwendungsfreigabe) filtern. Sie können auch auswählen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4097b-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4097b-145">In der folgenden Tabelle sind die Filter aufgelistet, die Sie im Diagnosebericht über Peer-to-Peer-Aktivitäten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4097b-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="4097b-146">Filter im Diagnosebericht über Peer-to-Peer-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="4097b-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4097b-147">Name</span><span class="sxs-lookup"><span data-stu-id="4097b-147">Name</span></span></th>
<th><span data-ttu-id="4097b-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4097b-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4097b-149"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-p109">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="4097b-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4097b-152">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="4097b-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4097b-p110">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="4097b-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4097b-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4097b-155">7/7/2012</span></span></p>
<p><span data-ttu-id="4097b-156">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="4097b-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4097b-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4097b-157">7/3/2012</span></span></p>
<p><span data-ttu-id="4097b-158">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="4097b-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4097b-159"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-p111">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="4097b-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4097b-162">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="4097b-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4097b-p112">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="4097b-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4097b-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4097b-165">7/7/2012</span></span></p>
<p><span data-ttu-id="4097b-166">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="4097b-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4097b-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4097b-167">7/3/2012</span></span></p>
<p><span data-ttu-id="4097b-168">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="4097b-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4097b-169"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-p113">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="4097b-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4097b-172">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4097b-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4097b-173">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4097b-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4097b-174">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4097b-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4097b-175">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="4097b-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4097b-176">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4097b-176">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="4097b-177">Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="4097b-177">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4097b-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-p115">Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4097b-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4097b-182"><strong>Modalität</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-p116">Gibt den Typ der Kommunikationsaktivität an, die stattgefunden hat. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="4097b-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4097b-185">[Alle]</span><span class="sxs-lookup"><span data-stu-id="4097b-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="4097b-186">Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="4097b-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="4097b-187">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="4097b-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="4097b-188">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="4097b-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="4097b-189">Audio</span><span class="sxs-lookup"><span data-stu-id="4097b-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="4097b-190">Video</span><span class="sxs-lookup"><span data-stu-id="4097b-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="4097b-191">Metrik (pro Modalität)</span><span class="sxs-lookup"><span data-stu-id="4097b-191">Metrics (per modality)</span></span>

<span data-ttu-id="4097b-192">In der folgenden Tabelle sind die Metriken aufgelistet, die im Diagnosebericht über Peer-to-Peer-Aktivitäten für jede Modalität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4097b-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="4097b-193">Metrik (pro Modalität)</span><span class="sxs-lookup"><span data-stu-id="4097b-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4097b-194">Name</span><span class="sxs-lookup"><span data-stu-id="4097b-194">Name</span></span></th>
<th><span data-ttu-id="4097b-195">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="4097b-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4097b-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4097b-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4097b-197"><strong>Anzahl der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-198">Nein</span><span class="sxs-lookup"><span data-stu-id="4097b-198">No</span></span></p></td>
<td><p><span data-ttu-id="4097b-199">Die Gesamtzahl der erfolgreichen Peer-to-Peer-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4097b-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4097b-200"><strong>Prozentsatz der erfolgreichen Sitzungen</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-201">Nein</span><span class="sxs-lookup"><span data-stu-id="4097b-201">No</span></span></p></td>
<td><p><span data-ttu-id="4097b-p117">Der Prozentsatz der Peer-to-Peer-Sitzungen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4097b-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4097b-204"><strong>Anzahl der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-205">Nein</span><span class="sxs-lookup"><span data-stu-id="4097b-205">No</span></span></p></td>
<td><p><span data-ttu-id="4097b-206">Die Gesamtzahl der Sitzungen, &quot;bei denen&quot; ein erwarteter Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4097b-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="4097b-p118">Ein erwarteter Fehler ist ein Fehler, der zu erwarten ist. Wenn beispielsweise ein Benutzer seinen Status auf „Nicht stören“ festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="4097b-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4097b-209"><strong>Prozentsatz der erwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-210">Nein</span><span class="sxs-lookup"><span data-stu-id="4097b-210">No</span></span></p></td>
<td><p><span data-ttu-id="4097b-p119">Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4097b-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4097b-213"><strong>Anzahl der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-214">Nein</span><span class="sxs-lookup"><span data-stu-id="4097b-214">No</span></span></p></td>
<td><p><span data-ttu-id="4097b-215">Die Gesamtzahl der Sitzungen, &quot;bei denen&quot; ein unerwarteter Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4097b-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="4097b-p120">Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4097b-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4097b-219"><strong>Prozentsatz der unerwarteten Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-220">Nein</span><span class="sxs-lookup"><span data-stu-id="4097b-220">No</span></span></p></td>
<td><p><span data-ttu-id="4097b-p121">Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4097b-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4097b-223"><strong>Sitzungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="4097b-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4097b-224">Nein</span><span class="sxs-lookup"><span data-stu-id="4097b-224">No</span></span></p></td>
<td><p><span data-ttu-id="4097b-225">Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4097b-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

