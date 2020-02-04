---
title: 'Lync Server 2013: Bericht zur Reaktionsgruppen Nutzung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 702ab291955ef7c8ec992e3607de581dff52b6a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="47596-102">Bericht zur Antwortgruppen Nutzung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47596-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47596-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="47596-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="47596-104">Die Anwendung Reaktionsgruppe bietet eine Möglichkeit für Microsoft lync Server 2013, Telefonanrufe auf der Grundlage der Nummer, die gewählt wurde, und – optional – für die Antworten des Anrufers auf eine Reihe von Fragen zu beantworten und weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="47596-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="47596-105">Normalerweise werden Reaktionsgruppenanrufe nicht an eine Einzelperson, sondern an ein Personenteam weitergeleitet, das als Agentgruppe bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="47596-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="47596-106">Wenn beispielsweise jemand die Telefonnummer Ihres Helpdesks anruft, kann lync Server 2013 diesen Anruf automatisch an den ersten verfügbaren Help Desk-Agenten weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="47596-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="47596-107">Alternativ kann lync Server eine Reihe von Fragen stellen ("drücken Sie 1, wenn Sie Hardwareprobleme haben.</span><span class="sxs-lookup"><span data-stu-id="47596-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="47596-108">Wenn Sie Softwareprobleme haben, drücken Sie die 2.</span><span class="sxs-lookup"><span data-stu-id="47596-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="47596-109">Drücken Sie 3, wenn Sie Netzwerkprobleme haben. ") und leiten Sie dann den Anruf an den am besten geeigneten Helpdesk-Agenten weiter, basierend auf der Antwort auf diese Fragen.</span><span class="sxs-lookup"><span data-stu-id="47596-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="47596-110">Der Nutzungsbericht über die Reaktionsgruppe gibt einen detaillierten Einblick in die Anzahl der Telefonanrufe, die von allen Reaktionsgruppen-Workflows empfangen wurden. Diese Anrufe werden dann in spezifischere Kategorien unterteilt, z. B. „Angebotene Anrufe“, „Angenommene Anrufe“ und „Abgebrochene Anrufe“.</span><span class="sxs-lookup"><span data-stu-id="47596-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="47596-111">Bei der Verwendung des Nutzungsberichts über die Reaktionsgruppe ist es wichtig, den Unterschied zwischen den gemeldeten Anruftypen zu verstehen:</span><span class="sxs-lookup"><span data-stu-id="47596-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="47596-p102">**Empfangene Anrufe**. Gesamtzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="47596-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="47596-p103">**Erfolgreiche Anrufe**. Gesamtzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="47596-p103">**Successful calls**. Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="47596-p104">**Angebotene Anrufe**. Gesamtzahl der Anrufe, die an einen Reaktionsgruppenagent weitergeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="47596-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="47596-p105">**Angenommene Anrufe**. Gesamtzahl der Anrufe, die tatsächlich von einem Reaktionsgruppenagent angenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="47596-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="47596-p106">**Prozentsatz abgebrochener Anrufe**. Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agenten angenommen wurden. Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und 7 davon beantwortet wurden, ziehen Sie 7 von 10 ab, wonach 3 unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt.</span><span class="sxs-lookup"><span data-stu-id="47596-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="47596-p107">**Durchgestellte Anrufe**. Gesamtzahl der Reaktionsgruppenanrufe, die aufgrund eines Timeouts oder eines Überlaufens der Warteschleife durchgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="47596-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="47596-p108">Wenn Sie sich den Nutzungsbericht über die Reaktionsgruppe ansehen und sich nicht mehr an die Definition eines Anruftyps erinnern können, halten Sie einfach die Maus über die Beschriftung des entsprechenden Anruftyps. Daraufhin wird eine QuickInfo mit einer kurzen Beschreibung des Anruftyps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47596-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="47596-p109">Mit einem Nutzungsbericht über Reaktionsgruppe können Sie nach einem Workflow-URI (die mit dem Workflow verknüpfte SIP-Adresse) filtern. Workflow-URIs werden nicht tatsächlich im Bericht angezeigt. Wenn Sie z. B. mehr darüber erfahren möchten, welche Workflows die meisten Anrufe entgegennehmen oder in welchen Workflows die meisten Anrufe durchgestellt werden, klicken Sie auf die entsprechende Metrik, um den Anruflistenbericht für Reaktionsgruppen für diesen bestimmten Zeitraum anzuzeigen. In diesem Bericht werden die Workflow-URIs aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="47596-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="47596-133">Zugreifen auf den Nutzungsbericht über die Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="47596-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="47596-134">Sie können über die Startseite für Überwachungsberichte auf den Nutzungsbericht über die Reaktionsgruppe zugreifen.</span><span class="sxs-lookup"><span data-stu-id="47596-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="47596-135">Sie können einen Drilldown zum [Bericht "Anrufliste der Reaktionsgruppe" in lync Server 2013](lync-server-2013-response-group-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="47596-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="47596-136">Empfangene Anrufe</span><span class="sxs-lookup"><span data-stu-id="47596-136">Received calls</span></span>

  - <span data-ttu-id="47596-137">Erfolgreiche Anrufe</span><span class="sxs-lookup"><span data-stu-id="47596-137">Successful calls</span></span>

  - <span data-ttu-id="47596-138">Angebotene Anrufe</span><span class="sxs-lookup"><span data-stu-id="47596-138">Offered calls</span></span>

  - <span data-ttu-id="47596-139">Angenommene Anrufe</span><span class="sxs-lookup"><span data-stu-id="47596-139">Answered calls</span></span>

  - <span data-ttu-id="47596-140">Durchgestellte Anrufe</span><span class="sxs-lookup"><span data-stu-id="47596-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="47596-141">Optimale Verwendung des Nutzungsberichts über die Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="47596-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="47596-142">Eine der interessantesten Verwendungen des Nutzungsberichts über die Reaktionsgruppe ist vielleicht nicht auf den ersten Blick erkennbar: die Möglichkeit zum Abrufen von Nutzungsinformationen für einen einzelnen Reaktionsgruppenworkflow.</span><span class="sxs-lookup"><span data-stu-id="47596-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="47596-143">Ein Workflow der Reaktionsgruppe ist im Grunde eine Reihe von Anweisungen, die bestimmt, was lync Server tut, wenn ein Benutzer eine bestimmte Telefonnummer wählt.</span><span class="sxs-lookup"><span data-stu-id="47596-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="47596-144">Dafür ist jeder Workflow eindeutig einer Telefonnummer zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="47596-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="47596-145">Wenn jemand diese Nummer anruft, wird durch den Workflow festgelegt, wie der Anruf verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="47596-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="47596-146">Beispielsweise kann der Anruf zur Beantwortung einer Reihe von Fragen an das interaktive Sprachantwortsystem (IVR, Interactive Voice Response) weitergeleitet werden, sodass der Anrufer zur Eingabe weiterer Informationen aufgefordert wird („Für Hardwaresupport, drücken Sie die 1.</span><span class="sxs-lookup"><span data-stu-id="47596-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="47596-147">Für Softwaresupport, drücken Sie die 2.“).</span><span class="sxs-lookup"><span data-stu-id="47596-147">Press 2 for software support.").</span></span> <span data-ttu-id="47596-148">Alternativ dazu kann der Anruf vom Workflow in eine Warteschleife gestellt und gehalten werden, bis ein Agent den Anruf entgegennehmen kann.</span><span class="sxs-lookup"><span data-stu-id="47596-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="47596-149">Auch die Verfügbarkeit von Agenten zur Anrufannahme wird vom Workflow vorgegeben: Mithilfe von Workflows werden sowohl Geschäftszeiten (die Wochentage und Tageszeiten, zu denen Agenten für die Annahme von Anrufen verfügbar sind) als auch Feiertage (Tage, an denen keine Agenten zur Anrufannahme bereitstehen) konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="47596-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="47596-150">Jedes Mal, wenn eine Telefonnummer gewählt wird, die zur Reaktionsgruppenanwendung gehört, wird eigentlich ein Reaktionsgruppenworkflow angerufen.</span><span class="sxs-lookup"><span data-stu-id="47596-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="47596-p112">Obwohl im Nutzungsbericht über Reaktionsgruppe keine Workflow-URIs angezeigt werden, kann dennoch die Nutzungsstatistik für einen einzelnen Workflow angezeigt werden, was oftmals sehr nützlich sein kann. Angenommen, Sie haben vor kurzem eine neue Anzeigenkampagne lanciert und möchten gern erfahren, ob interessierte Leute anrufen, um mehr über dieses Produkt zu erfahren. Wenn Sie mit der in der Anzeigenkampagne genannten Telefonnummer einen Reaktionsgruppenworkflow verknüpft haben, können Sie auf einfache Weise feststellen, wie viele Personen (wenn überhaupt) diese Nummer gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="47596-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="47596-154">Sie können auch einen ähnlichen Ansatz verwenden, um die Anzahl der Anrufe zu messen, die von Ihrem internen Helpdesk oder Ihrer Kundendienstabteilung behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="47596-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="47596-155">Wenn Sie die Nutzungsstatistik für einen bestimmten Workflow prüfen möchten, geben Sie den Workflow-URI in das Feld „Workflow-URI“ ein.</span><span class="sxs-lookup"><span data-stu-id="47596-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="47596-156">Wie oben erwähnt, erscheinen im Bericht keine Workflow-URIs (die mit einem Workflow verknüpfte SIP-Adresse).</span><span class="sxs-lookup"><span data-stu-id="47596-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="47596-157">Das bedeutet, Sie müssen den URI eines Workflows auf andere Weise herausfinden.</span><span class="sxs-lookup"><span data-stu-id="47596-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="47596-158">Eine Möglichkeit besteht darin, Windows PowerShell und die lync Server-Verwaltungsshell zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="47596-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="47596-159">Mit diesem Befehl werden beispielsweise die URIs für Ihre gesamten Reaktionsgruppenworkflows zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="47596-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="47596-160">Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:</span><span class="sxs-lookup"><span data-stu-id="47596-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="47596-161">Mit diesem Befehl werden Informationen für einen einzelnen Workflow mit dem Namen „New Ad Campaign“ zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="47596-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="47596-162">Filter</span><span class="sxs-lookup"><span data-stu-id="47596-162">Filters</span></span>

<span data-ttu-id="47596-p114">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Reaktionsgruppen-Verwendungsbericht Daten für all Ihre Reaktionsgruppen-Workflows anzeigen oder für einen einzelnen Workflow. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="47596-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="47596-167">In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Reaktionsgruppen-Verwendungsbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="47596-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="47596-168">Reaktionsgruppen-Verwendungsbericht - Filter</span><span class="sxs-lookup"><span data-stu-id="47596-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47596-169">Name</span><span class="sxs-lookup"><span data-stu-id="47596-169">Name</span></span></th>
<th><span data-ttu-id="47596-170">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47596-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47596-171"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="47596-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-p115">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="47596-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="47596-174">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="47596-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="47596-p116">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="47596-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="47596-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="47596-177">7/7/2012</span></span></p>
<p><span data-ttu-id="47596-178">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="47596-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="47596-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="47596-179">7/3/2012</span></span></p>
<p><span data-ttu-id="47596-180">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="47596-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47596-181"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="47596-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-p117">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="47596-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="47596-184">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="47596-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="47596-p118">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="47596-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="47596-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="47596-187">7/7/2012</span></span></p>
<p><span data-ttu-id="47596-188">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="47596-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="47596-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="47596-189">7/3/2012</span></span></p>
<p><span data-ttu-id="47596-190">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="47596-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47596-191"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="47596-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-p119">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="47596-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="47596-194">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="47596-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="47596-195">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="47596-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="47596-196">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="47596-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="47596-197">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="47596-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="47596-198">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47596-198">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="47596-199">Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="47596-199">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47596-200"><strong>Workflow-URI</strong></span><span class="sxs-lookup"><span data-stu-id="47596-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-p121">Bietet Ihnen die Möglichkeit, die zurückgegebenen Daten auf den angegebenen Reaktionsgruppenworkflow zu beschränken. Geben Sie die Workflow-SIP-Adresse ein, um diesen Filter zu verwenden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47596-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="47596-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47596-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="47596-205">Metriken</span><span class="sxs-lookup"><span data-stu-id="47596-205">Metrics</span></span>

<span data-ttu-id="47596-206">In der folgenden Tabelle sind die Informationen aufgeführt, die im Reaktionsgruppen-Verwendungsbericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="47596-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="47596-207">Reaktionsgruppen-Verwendungsbericht - Metriken</span><span class="sxs-lookup"><span data-stu-id="47596-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47596-208">Name</span><span class="sxs-lookup"><span data-stu-id="47596-208">Name</span></span></th>
<th><span data-ttu-id="47596-209">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="47596-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="47596-210">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47596-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47596-211"><strong>Stündlich</strong></span><span class="sxs-lookup"><span data-stu-id="47596-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="47596-212"><strong>Täglich</strong></span><span class="sxs-lookup"><span data-stu-id="47596-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="47596-213"><strong>Wöchentlich</strong></span><span class="sxs-lookup"><span data-stu-id="47596-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="47596-214"><strong>Monatlich</strong></span><span class="sxs-lookup"><span data-stu-id="47596-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-215">Nein</span><span class="sxs-lookup"><span data-stu-id="47596-215">No</span></span></p></td>
<td><p><span data-ttu-id="47596-216">Gibt das ausgewählte Zeitintervall an.</span><span class="sxs-lookup"><span data-stu-id="47596-216">Indicates the selected time interval.</span></span> <span data-ttu-id="47596-217">Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen.</span><span class="sxs-lookup"><span data-stu-id="47596-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="47596-218">Wenn Sie beispielsweise das Tagesintervall verwenden und auf 7/7/2012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47596-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47596-219"><strong>Empfangene Anrufe</strong></span><span class="sxs-lookup"><span data-stu-id="47596-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-220">Nein</span><span class="sxs-lookup"><span data-stu-id="47596-220">No</span></span></p></td>
<td><p><span data-ttu-id="47596-p123">Gesamtanzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="47596-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47596-223"><strong>Erfolgreiche Anrufe</strong></span><span class="sxs-lookup"><span data-stu-id="47596-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-224">Nein</span><span class="sxs-lookup"><span data-stu-id="47596-224">No</span></span></p></td>
<td><p><span data-ttu-id="47596-p124">Gesamtanzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="47596-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47596-227"><strong>Angebotene Anrufe</strong></span><span class="sxs-lookup"><span data-stu-id="47596-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-228">Nein</span><span class="sxs-lookup"><span data-stu-id="47596-228">No</span></span></p></td>
<td><p><span data-ttu-id="47596-p125">Gesamtanzahl der Anrufe, die an einen Reaktionsgruppenvertreter weitergeleitet wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="47596-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47596-231"><strong>Angenommene Anrufe</strong></span><span class="sxs-lookup"><span data-stu-id="47596-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-232">Nein</span><span class="sxs-lookup"><span data-stu-id="47596-232">No</span></span></p></td>
<td><p><span data-ttu-id="47596-p126">Gesamtanzahl der Anrufe, die von einem Reaktionsgruppenvertreter tatsächlich angenommen wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="47596-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47596-235"><strong>Prozentsatz abgebrochener Anrufe</strong></span><span class="sxs-lookup"><span data-stu-id="47596-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-236">Nein</span><span class="sxs-lookup"><span data-stu-id="47596-236">No</span></span></p></td>
<td><p><span data-ttu-id="47596-p127">Gesamtanzahl der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Vertreter angenommen wurden. Dies wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und sieben davon beantwortet wurden, ziehen Sie sieben von 10 ab, wonach drei unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt.</span><span class="sxs-lookup"><span data-stu-id="47596-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47596-241"><strong>Durchschnittliche Anrufminuten pro Agent</strong></span><span class="sxs-lookup"><span data-stu-id="47596-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-242">Nein</span><span class="sxs-lookup"><span data-stu-id="47596-242">No</span></span></p></td>
<td><p><span data-ttu-id="47596-243">Durchschnittliche Dauer, die ein Reaktionsgruppenvertreter für einen Anruf aufgewendet hat.</span><span class="sxs-lookup"><span data-stu-id="47596-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47596-244"><strong>Durchgestellte Anrufe</strong></span><span class="sxs-lookup"><span data-stu-id="47596-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="47596-245">Nein</span><span class="sxs-lookup"><span data-stu-id="47596-245">No</span></span></p></td>
<td><p><span data-ttu-id="47596-p128">Gesamtanzahl der Reaktionsgruppenanrufe, die aufgrund einer Timeout- oder Überlaufwarteschleife durchgestellt wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="47596-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

