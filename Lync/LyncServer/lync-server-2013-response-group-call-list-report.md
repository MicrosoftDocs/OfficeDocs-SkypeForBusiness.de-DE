---
title: 'Lync Server 2013: Anruflistenbericht für Reaktionsgruppen'
description: 'Lync Server 2013: Anruflistenbericht für Reaktionsgruppen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ffe4b62534d4849b4f0cdade9aeef8be5d69178
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560881"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="e1515-103">Anruflistenbericht der Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1515-103">Response Group Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1515-104">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e1515-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e1515-105">Das Reaktionsgruppenanwendung bietet eine Möglichkeit für Microsoft lync Server 2013, Telefonanrufe basierend auf der gewählten Nummer und optional bei den Antworten des Anrufers auf eine Reihe von Fragen zu beantworten und weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e1515-105">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="e1515-106">Reaktionsgruppenanrufe werden normalerweise nicht an eine Einzelperson weitergeleitet, sondern stattdessen an ein Team von Personen, die als eine Agentgruppe bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="e1515-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="e1515-107">Wenn ein Benutzer beispielsweise die Telefonnummer für Ihr Helpdesk anruft, kann lync Server 2013 diesen Anruf automatisch an den ersten verfügbaren Helpdesk-Agent weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="e1515-107">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="e1515-108">Alternativ können lync Server eine Reihe von Fragen stellen ("drücken Sie 1, wenn Sie Hardwareprobleme haben.</span><span class="sxs-lookup"><span data-stu-id="e1515-108">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="e1515-109">Drücken Sie 2, wenn Sie Softwareprobleme haben.</span><span class="sxs-lookup"><span data-stu-id="e1515-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="e1515-110">Drücken Sie 3, wenn Netzwerkprobleme auftreten. ") und leiten Sie den Anruf dann basierend auf der Antwort auf diese Fragen an den am besten geeigneten Helpdesk-Agent weiter.</span><span class="sxs-lookup"><span data-stu-id="e1515-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="e1515-p102">Der  Anruflistenbericht für Reaktionsgruppen stellt eine Sammlung von Anrufen dar, die über einen bestimmten Zeitraum und für einen bestimmten Anruftyp getätigt wurden. Im Reaktionsgruppen-Verwendungsbericht (der zuerst geöffnet werden muss, bevor Sie den Anruflistenbericht für Reaktionsgruppen öffnen können) werden die folgenden Anruftypen erkannt:</span><span class="sxs-lookup"><span data-stu-id="e1515-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="e1515-p103">**Empfangene Anrufe**. Gesamtzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="e1515-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="e1515-115">**Erfolgreiche Anrufe**.</span><span class="sxs-lookup"><span data-stu-id="e1515-115">**Successful calls**.</span></span> <span data-ttu-id="e1515-116">Die Gesamtzahl der Anrufe, die von der Reaktionsgruppenanwendung übernommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e1515-116">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="e1515-p105">**Angebotene Anrufe**. Gesamtanzahl der Anrufe, die an einen Reaktionsgruppen-Agenten weitergeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="e1515-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="e1515-p106">**Angenommene Anrufe**. Gesamtanzahl der Anrufe, die von einem Reaktionsgruppen-Agenten tatsächlich angenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e1515-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="e1515-121">Prozentsatz abgebrochener Anrufe.</span><span class="sxs-lookup"><span data-stu-id="e1515-121">Percentage of abandoned calls.</span></span> <span data-ttu-id="e1515-122">Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agenten angenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e1515-122">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="e1515-123">Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="e1515-123">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="e1515-124">Wenn Sie beispielsweise 10 Anrufe empfangen haben und 7 davon beantwortet wurden, ziehen Sie 7 von 10 ab, wonach drei unbeantwortete Anrufe übrig bleiben.</span><span class="sxs-lookup"><span data-stu-id="e1515-124">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="e1515-125">Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt..</span><span class="sxs-lookup"><span data-stu-id="e1515-125">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="e1515-p108">**Durchgestellte Anrufe**. Gesamtzahl der Reaktionsgruppenanrufe, die aufgrund eines Timeouts oder Überlaufs der Warteschleife durchgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e1515-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="e1515-128">Zugreifen auf den Anruflistenbericht für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="e1515-128">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="e1515-129">Auf den Anruflistenbericht für Reaktionsgruppen kann nur zugegriffen werden, indem Sie auf eine der folgenden Metriken klicken, die im Bericht über die [Reaktionsgruppen Verwendung in lync Server 2013](lync-server-2013-response-group-usage-report.md)gefunden werden:</span><span class="sxs-lookup"><span data-stu-id="e1515-129">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="e1515-130">Empfangene Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-130">Received calls</span></span>

  - <span data-ttu-id="e1515-131">Erfolgreiche Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-131">Successful calls</span></span>

  - <span data-ttu-id="e1515-132">Angebotene Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-132">Offered calls</span></span>

  - <span data-ttu-id="e1515-133">Angenommene Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-133">Answered calls</span></span>

  - <span data-ttu-id="e1515-134">Durchgestellte Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-134">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="e1515-135">Optimale Nutzung des Anruflistenberichts für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="e1515-135">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="e1515-p109">Mithilfe des Anruflistenberichts für Reaktionsgruppen können Sie die angezeigten Daten auf Anfrufe mit einem bestimmten Reaktionsgruppenworkflow beschränken. Dazu müssen Sie im Feld "Workflow-URI" den Workflow-URI (die SIP-Adresse des Workflows) eingeben. Bevor Sie dies tun können, muss das Feld "Workflow-URI" tatsächlich angezeigt werden. Wenn Sie die Filteroptionen für den Anruflistenbericht für Reaktionsgruppen anzeigen möchten, klicken Sie im oberen linken Teil des Berichtsfensters auf die Schaltfläche "Parameter ein-/ausblenden".</span><span class="sxs-lookup"><span data-stu-id="e1515-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="e1515-140">Beachten Sie, dass im Anruflistenbericht für Reaktionsgruppen keine Informationen zum Antwortcode oder zur Diagnose-ID angezeigt werden, wenn Sie die Maus über eine dieser Metriken halten.</span><span class="sxs-lookup"><span data-stu-id="e1515-140">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="e1515-141">Wenn Sie weitere Informationen benötigen, können Sie den Antwortcode und/oder die Diagnose-ID notieren und dann im Bericht " [Top Failures" in lync Server 2013](lync-server-2013-top-failures-report.md)nach diesen Werten suchen.</span><span class="sxs-lookup"><span data-stu-id="e1515-141">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="e1515-142">Bei einer Frage wie "Welcher Einzelworkflow hat die meisten Anrufe empfangen?" können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e1515-142">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="e1515-p111">Legen Sie im Reaktionsgruppen-Verwendungsbericht den gewünschten Zeitraum fest, und klicken Sie dann auf die Metrik "Empfangene Anrufe". Daraufhin wird der Anruflistenbericht für Reaktionsgruppen geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e1515-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="e1515-p112">Exportieren Sie die im Anruflistenbericht für Reaktionsgruppen angezeigten Daten. Sie können beispielsweise die Daten im Microsoft Excel-Format exportieren und diese Daten dann mit Excel in eine Datei mit durch Komma getrennten Werten konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e1515-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="e1515-147">Führen Sie Ihre Analysen mit Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="e1515-147">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="e1515-148">Wenn Sie beispielsweise die Daten in einer Datei namens C: \\ Data \\ Response \_ Group \_ Call \_ ListReport.csv gespeichert haben \_ , können Sie den folgenden Befehl verwenden, um die Gesamtzahl der empfangenen Anrufe für jeden im Bericht aufgeführten Workflow zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="e1515-148">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="e1515-149">Dadurch werden Informationen bereitgestellt, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="e1515-149">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e1515-150">Filter</span><span class="sxs-lookup"><span data-stu-id="e1515-150">Filters</span></span>

<span data-ttu-id="e1515-p113">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anruflistenbericht für Reaktionsgruppen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e1515-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="e1515-153">Filter für den Anruflistenbericht für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="e1515-153">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1515-154">Name</span><span class="sxs-lookup"><span data-stu-id="e1515-154">Name</span></span></th>
<th><span data-ttu-id="e1515-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1515-155">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1515-156"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-156"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-p114">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="e1515-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e1515-159">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="e1515-159">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e1515-p115">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="e1515-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e1515-162">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e1515-162">7/7/2012</span></span></p>
<p><span data-ttu-id="e1515-163">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="e1515-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e1515-164">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e1515-164">7/3/2012</span></span></p>
<p><span data-ttu-id="e1515-165">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="e1515-165">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1515-166"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-166"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-p116">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="e1515-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e1515-169">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="e1515-169">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e1515-p117">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="e1515-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e1515-172">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e1515-172">7/7/2012</span></span></p>
<p><span data-ttu-id="e1515-173">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="e1515-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e1515-174">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e1515-174">7/3/2012</span></span></p>
<p><span data-ttu-id="e1515-175">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="e1515-175">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1515-176"><strong>Workflow-URI</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-176"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-p118">Damit können Sie die zurückgegebenen Daten auf den angegebenen Reaktionsgruppen-Workflow beschränken. Geben Sie zur Verwendung dieses Filters die SIP-Adresse des Workflows ein. Beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="e1515-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="e1515-180">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e1515-180">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1515-181"><strong>Aufrufe</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-181"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-182">Sie können die folgenden Anruftypen auswählen:</span><span class="sxs-lookup"><span data-stu-id="e1515-182">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="e1515-183">Empfangene Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-183">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="e1515-184">Erfolgreiche Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-184">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="e1515-185">Angebotene Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-185">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="e1515-186">Angenommene Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-186">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="e1515-187">Durchgestellte Anrufe</span><span class="sxs-lookup"><span data-stu-id="e1515-187">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e1515-188">Metriken</span><span class="sxs-lookup"><span data-stu-id="e1515-188">Metrics</span></span>

<span data-ttu-id="e1515-189">In der folgenden Tabelle sind die im Anruflistenbericht für Reaktionsgruppen für jeden Anruf, der von der Reaktionsgruppenanwendung empfangen wurde, bereitgestellten Informationen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e1515-189">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="e1515-190">Metriken für den Anruflistenbericht für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="e1515-190">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1515-191">Name</span><span class="sxs-lookup"><span data-stu-id="e1515-191">Name</span></span></th>
<th><span data-ttu-id="e1515-192">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="e1515-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e1515-193">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1515-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1515-194"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-194"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-195">Nein</span><span class="sxs-lookup"><span data-stu-id="e1515-195">No</span></span></p></td>
<td><p><span data-ttu-id="e1515-196">SIP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="e1515-196">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1515-197"><strong>Workflow</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-197"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-198">Nein</span><span class="sxs-lookup"><span data-stu-id="e1515-198">No</span></span></p></td>
<td><p><span data-ttu-id="e1515-199">SIP-Adresse des Reaktionsgruppenworkflows.</span><span class="sxs-lookup"><span data-stu-id="e1515-199">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1515-200"><strong>Startzeit</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-200"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-201">Nein</span><span class="sxs-lookup"><span data-stu-id="e1515-201">No</span></span></p></td>
<td><p><span data-ttu-id="e1515-202">Datum und Uhrzeit des Beginns des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e1515-202">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1515-203"><strong>Endzeit</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-203"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-204">Nein</span><span class="sxs-lookup"><span data-stu-id="e1515-204">No</span></span></p></td>
<td><p><span data-ttu-id="e1515-205">Datum und Uhrzeit des Endes des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e1515-205">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1515-206"><strong>Antwortcode</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-206"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-207">Nein</span><span class="sxs-lookup"><span data-stu-id="e1515-207">No</span></span></p></td>
<td><p><span data-ttu-id="e1515-208">SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e1515-208">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1515-209"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="e1515-209"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e1515-210">Nein</span><span class="sxs-lookup"><span data-stu-id="e1515-210">No</span></span></p></td>
<td><p><span data-ttu-id="e1515-211">Eindeutige ID (in Form eines Headers vom Typ "ms-diagnostics"), die einer SIP-Nachricht angefügt ist, die häufig nützliche Informationen für die Problembehandlung von Fehlern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e1515-211">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

