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

# <a name="response-group-usage-report-in-lync-server-2013"></a>Bericht zur Antwortgruppen Nutzung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die Anwendung Reaktionsgruppe bietet eine Möglichkeit für Microsoft lync Server 2013, Telefonanrufe auf der Grundlage der Nummer, die gewählt wurde, und – optional – für die Antworten des Anrufers auf eine Reihe von Fragen zu beantworten und weiterzuleiten. Normalerweise werden Reaktionsgruppenanrufe nicht an eine Einzelperson, sondern an ein Personenteam weitergeleitet, das als Agentgruppe bezeichnet wird. Wenn beispielsweise jemand die Telefonnummer Ihres Helpdesks anruft, kann lync Server 2013 diesen Anruf automatisch an den ersten verfügbaren Help Desk-Agenten weiterleiten. Alternativ kann lync Server eine Reihe von Fragen stellen ("drücken Sie 1, wenn Sie Hardwareprobleme haben. Wenn Sie Softwareprobleme haben, drücken Sie die 2. Drücken Sie 3, wenn Sie Netzwerkprobleme haben. ") und leiten Sie dann den Anruf an den am besten geeigneten Helpdesk-Agenten weiter, basierend auf der Antwort auf diese Fragen.

Der Nutzungsbericht über die Reaktionsgruppe gibt einen detaillierten Einblick in die Anzahl der Telefonanrufe, die von allen Reaktionsgruppen-Workflows empfangen wurden. Diese Anrufe werden dann in spezifischere Kategorien unterteilt, z. B. „Angebotene Anrufe“, „Angenommene Anrufe“ und „Abgebrochene Anrufe“.

Bei der Verwendung des Nutzungsberichts über die Reaktionsgruppe ist es wichtig, den Unterschied zwischen den gemeldeten Anruftypen zu verstehen:

  - **Empfangene Anrufe**. Gesamtzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.

  - **Erfolgreiche Anrufe**. Gesamtzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden.

  - **Angebotene Anrufe**. Gesamtzahl der Anrufe, die an einen Reaktionsgruppenagent weitergeleitet wurden.

  - **Angenommene Anrufe**. Gesamtzahl der Anrufe, die tatsächlich von einem Reaktionsgruppenagent angenommen wurden.

  - **Prozentsatz abgebrochener Anrufe**. Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agenten angenommen wurden. Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und 7 davon beantwortet wurden, ziehen Sie 7 von 10 ab, wonach 3 unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt.

  - **Durchgestellte Anrufe**. Gesamtzahl der Reaktionsgruppenanrufe, die aufgrund eines Timeouts oder eines Überlaufens der Warteschleife durchgestellt wurden.

Wenn Sie sich den Nutzungsbericht über die Reaktionsgruppe ansehen und sich nicht mehr an die Definition eines Anruftyps erinnern können, halten Sie einfach die Maus über die Beschriftung des entsprechenden Anruftyps. Daraufhin wird eine QuickInfo mit einer kurzen Beschreibung des Anruftyps angezeigt.

Mit einem Nutzungsbericht über Reaktionsgruppe können Sie nach einem Workflow-URI (die mit dem Workflow verknüpfte SIP-Adresse) filtern. Workflow-URIs werden nicht tatsächlich im Bericht angezeigt. Wenn Sie z. B. mehr darüber erfahren möchten, welche Workflows die meisten Anrufe entgegennehmen oder in welchen Workflows die meisten Anrufe durchgestellt werden, klicken Sie auf die entsprechende Metrik, um den Anruflistenbericht für Reaktionsgruppen für diesen bestimmten Zeitraum anzuzeigen. In diesem Bericht werden die Workflow-URIs aufgelistet.

<div>

## <a name="accessing-the-response-group-usage-report"></a>Zugreifen auf den Nutzungsbericht über die Reaktionsgruppe

Sie können über die Startseite für Überwachungsberichte auf den Nutzungsbericht über die Reaktionsgruppe zugreifen. Sie können einen Drilldown zum [Bericht "Anrufliste der Reaktionsgruppe" in lync Server 2013](lync-server-2013-response-group-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:

  - Empfangene Anrufe

  - Erfolgreiche Anrufe

  - Angebotene Anrufe

  - Angenommene Anrufe

  - Durchgestellte Anrufe

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Optimale Verwendung des Nutzungsberichts über die Reaktionsgruppe

Eine der interessantesten Verwendungen des Nutzungsberichts über die Reaktionsgruppe ist vielleicht nicht auf den ersten Blick erkennbar: die Möglichkeit zum Abrufen von Nutzungsinformationen für einen einzelnen Reaktionsgruppenworkflow.

<div>


> [!WARNING]  
> Ein Workflow der Reaktionsgruppe ist im Grunde eine Reihe von Anweisungen, die bestimmt, was lync Server tut, wenn ein Benutzer eine bestimmte Telefonnummer wählt. Dafür ist jeder Workflow eindeutig einer Telefonnummer zugeordnet. Wenn jemand diese Nummer anruft, wird durch den Workflow festgelegt, wie der Anruf verarbeitet wird. Beispielsweise kann der Anruf zur Beantwortung einer Reihe von Fragen an das interaktive Sprachantwortsystem (IVR, Interactive Voice Response) weitergeleitet werden, sodass der Anrufer zur Eingabe weiterer Informationen aufgefordert wird („Für Hardwaresupport, drücken Sie die 1. Für Softwaresupport, drücken Sie die 2.“). Alternativ dazu kann der Anruf vom Workflow in eine Warteschleife gestellt und gehalten werden, bis ein Agent den Anruf entgegennehmen kann. Auch die Verfügbarkeit von Agenten zur Anrufannahme wird vom Workflow vorgegeben: Mithilfe von Workflows werden sowohl Geschäftszeiten (die Wochentage und Tageszeiten, zu denen Agenten für die Annahme von Anrufen verfügbar sind) als auch Feiertage (Tage, an denen keine Agenten zur Anrufannahme bereitstehen) konfiguriert. Jedes Mal, wenn eine Telefonnummer gewählt wird, die zur Reaktionsgruppenanwendung gehört, wird eigentlich ein Reaktionsgruppenworkflow angerufen.



</div>

Obwohl im Nutzungsbericht über Reaktionsgruppe keine Workflow-URIs angezeigt werden, kann dennoch die Nutzungsstatistik für einen einzelnen Workflow angezeigt werden, was oftmals sehr nützlich sein kann. Angenommen, Sie haben vor kurzem eine neue Anzeigenkampagne lanciert und möchten gern erfahren, ob interessierte Leute anrufen, um mehr über dieses Produkt zu erfahren. Wenn Sie mit der in der Anzeigenkampagne genannten Telefonnummer einen Reaktionsgruppenworkflow verknüpft haben, können Sie auf einfache Weise feststellen, wie viele Personen (wenn überhaupt) diese Nummer gewählt haben.

Sie können auch einen ähnlichen Ansatz verwenden, um die Anzahl der Anrufe zu messen, die von Ihrem internen Helpdesk oder Ihrer Kundendienstabteilung behandelt werden.

Wenn Sie die Nutzungsstatistik für einen bestimmten Workflow prüfen möchten, geben Sie den Workflow-URI in das Feld „Workflow-URI“ ein. Wie oben erwähnt, erscheinen im Bericht keine Workflow-URIs (die mit einem Workflow verknüpfte SIP-Adresse). Das bedeutet, Sie müssen den URI eines Workflows auf andere Weise herausfinden. Eine Möglichkeit besteht darin, Windows PowerShell und die lync Server-Verwaltungsshell zu verwenden. Mit diesem Befehl werden beispielsweise die URIs für Ihre gesamten Reaktionsgruppenworkflows zurückgegeben:

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

Mit diesem Befehl werden Informationen für einen einzelnen Workflow mit dem Namen „New Ad Campaign“ zurückgegeben:

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Reaktionsgruppen-Verwendungsbericht Daten für all Ihre Reaktionsgruppen-Workflows anzeigen oder für einen einzelnen Workflow. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Reaktionsgruppen-Verwendungsbericht verwenden können.

### <a name="response-group-usage-report-filters"></a>Reaktionsgruppen-Verwendungsbericht - Filter

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Von</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 Uhr</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p>Monatlich (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Workflow-URI</strong></p></td>
<td><p>Bietet Ihnen die Möglichkeit, die zurückgegebenen Daten auf den angegebenen Reaktionsgruppenworkflow zu beschränken. Geben Sie die Workflow-SIP-Adresse ein, um diesen Filter zu verwenden. Beispiel:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Reaktionsgruppen-Verwendungsbericht angegeben werden.

### <a name="response-group-usage-report-metrics"></a>Reaktionsgruppen-Verwendungsbericht - Metriken

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Kann nach dieser Metrik sortiert werden?</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Stündlich</strong></p>
<p><strong>Täglich</strong></p>
<p><strong>Wöchentlich</strong></p>
<p><strong>Monatlich</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt das ausgewählte Zeitintervall an. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Tagesintervall verwenden und auf 7/7/2012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Empfangene Anrufe</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Erfolgreiche Anrufe</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Angebotene Anrufe</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Anrufe, die an einen Reaktionsgruppenvertreter weitergeleitet wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Angenommene Anrufe</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Anrufe, die von einem Reaktionsgruppenvertreter tatsächlich angenommen wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz abgebrochener Anrufe</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Vertreter angenommen wurden. Dies wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und sieben davon beantwortet wurden, ziehen Sie sieben von 10 ab, wonach drei unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Durchschnittliche Anrufminuten pro Agent</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Dauer, die ein Reaktionsgruppenvertreter für einen Anruf aufgewendet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchgestellte Anrufe</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Reaktionsgruppenanrufe, die aufgrund einer Timeout- oder Überlaufwarteschleife durchgestellt wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

