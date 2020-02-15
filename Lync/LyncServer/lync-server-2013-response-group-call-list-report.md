---
title: 'Lync Server 2013: Anruflistenbericht für Reaktionsgruppen'
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
ms.openlocfilehash: fb6b35d3c76d8cf625d6d7317c89658223aada9c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Anruflistenbericht der Reaktionsgruppe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Das Reaktionsgruppenanwendung bietet eine Möglichkeit für Microsoft lync Server 2013, Telefonanrufe basierend auf der gewählten Nummer und optional bei den Antworten des Anrufers auf eine Reihe von Fragen zu beantworten und weiterzuleiten. Reaktionsgruppenanrufe werden normalerweise nicht an eine Einzelperson weitergeleitet, sondern stattdessen an ein Team von Personen, die als eine Agentgruppe bezeichnet wird. Wenn ein Benutzer beispielsweise die Telefonnummer für Ihr Helpdesk anruft, kann lync Server 2013 diesen Anruf automatisch an den ersten verfügbaren Helpdesk-Agent weiterleiten. Alternativ können lync Server eine Reihe von Fragen stellen ("drücken Sie 1, wenn Sie Hardwareprobleme haben. Drücken Sie 2, wenn Sie Softwareprobleme haben. Drücken Sie 3, wenn Netzwerkprobleme auftreten. ") und leiten Sie den Anruf dann basierend auf der Antwort auf diese Fragen an den am besten geeigneten Helpdesk-Agent weiter.

Der  Anruflistenbericht für Reaktionsgruppen stellt eine Sammlung von Anrufen dar, die über einen bestimmten Zeitraum und für einen bestimmten Anruftyp getätigt wurden. Im Reaktionsgruppen-Verwendungsbericht (der zuerst geöffnet werden muss, bevor Sie den Anruflistenbericht für Reaktionsgruppen öffnen können) werden die folgenden Anruftypen erkannt:

  - **Empfangene Anrufe**. Gesamtzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.

  - **Erfolgreiche Anrufe**. Die Gesamtzahl der Anrufe, die von der Reaktionsgruppenanwendung übernommen wurden.

  - **Angebotene Anrufe**. Gesamtanzahl der Anrufe, die an einen Reaktionsgruppen-Agenten weitergeleitet wurden.

  - **Angenommene Anrufe**. Gesamtanzahl der Anrufe, die von einem Reaktionsgruppen-Agenten tatsächlich angenommen wurden.

  - Prozentsatz abgebrochener Anrufe. Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agenten angenommen wurden. Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und 7 davon beantwortet wurden, ziehen Sie 7 von 10 ab, wonach drei unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt..

  - **Durchgestellte Anrufe**. Gesamtzahl der Reaktionsgruppenanrufe, die aufgrund eines Timeouts oder Überlaufs der Warteschleife durchgestellt wurden.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>Zugreifen auf den Anruflistenbericht für Reaktionsgruppen

Auf den Anruflistenbericht für Reaktionsgruppen kann nur zugegriffen werden, indem Sie auf eine der folgenden Metriken klicken, die im Bericht über die [Reaktionsgruppen Verwendung in lync Server 2013](lync-server-2013-response-group-usage-report.md)gefunden werden:

  - Empfangene Anrufe

  - Erfolgreiche Anrufe

  - Angebotene Anrufe

  - Angenommene Anrufe

  - Durchgestellte Anrufe

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Optimale Nutzung des Anruflistenberichts für Reaktionsgruppen

Mithilfe des Anruflistenberichts für Reaktionsgruppen können Sie die angezeigten Daten auf Anfrufe mit einem bestimmten Reaktionsgruppenworkflow beschränken. Dazu müssen Sie im Feld "Workflow-URI" den Workflow-URI (die SIP-Adresse des Workflows) eingeben. Bevor Sie dies tun können, muss das Feld "Workflow-URI" tatsächlich angezeigt werden. Wenn Sie die Filteroptionen für den Anruflistenbericht für Reaktionsgruppen anzeigen möchten, klicken Sie im oberen linken Teil des Berichtsfensters auf die Schaltfläche "Parameter ein-/ausblenden".

Beachten Sie, dass im Anruflistenbericht für Reaktionsgruppen keine Informationen zum Antwortcode oder zur Diagnose-ID angezeigt werden, wenn Sie die Maus über eine dieser Metriken halten. Wenn Sie weitere Informationen benötigen, können Sie den Antwortcode und/oder die Diagnose-ID notieren und dann im Bericht " [Top Failures" in lync Server 2013](lync-server-2013-top-failures-report.md)nach diesen Werten suchen.

Bei einer Frage wie "Welcher Einzelworkflow hat die meisten Anrufe empfangen?" können Sie die folgenden Aktionen ausführen:

1.  Legen Sie im Reaktionsgruppen-Verwendungsbericht den gewünschten Zeitraum fest, und klicken Sie dann auf die Metrik "Empfangene Anrufe". Daraufhin wird der Anruflistenbericht für Reaktionsgruppen geöffnet.

2.  Exportieren Sie die im Anruflistenbericht für Reaktionsgruppen angezeigten Daten. Sie können beispielsweise die Daten im Microsoft Excel-Format exportieren und diese Daten dann mit Excel in eine Datei mit durch Komma getrennten Werten konvertieren.

3.  Führen Sie Ihre Analysen mit Windows PowerShell aus.

Wenn Sie beispielsweise die Daten in einer Datei namens C\\: Data\\Response\_Group\_Call\_List\_Report. csv gespeichert haben, können Sie den folgenden Befehl verwenden, um die Gesamtzahl der empfangenen Anrufe für jeden im Bericht aufgeführten Workflow zurückzugeben:

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

Dadurch werden Informationen bereitgestellt, die den Folgenden ähneln:

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anruflistenbericht für Reaktionsgruppen verwenden können.

### <a name="response-group-call-list-report-filters"></a>Filter für den Anruflistenbericht für Reaktionsgruppen

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
<td><p><strong>From</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ziel</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Workflow-URI</strong></p></td>
<td><p>Damit können Sie die zurückgegebenen Daten auf den angegebenen Reaktionsgruppen-Workflow beschränken. Geben Sie zur Verwendung dieses Filters die SIP-Adresse des Workflows ein. Beispielsweise:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufe</strong></p></td>
<td><p>Sie können die folgenden Anruftypen auswählen:</p>
<ul>
<li><p>Empfangene Anrufe</p></li>
<li><p>Erfolgreiche Anrufe</p></li>
<li><p>Angebotene Anrufe</p></li>
<li><p>Angenommene Anrufe</p></li>
<li><p>Durchgestellte Anrufe</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Anruflistenbericht für Reaktionsgruppen für jeden Anruf, der von der Reaktionsgruppenanwendung empfangen wurde, bereitgestellten Informationen aufgelistet.

### <a name="response-group-call-list-report-metrics"></a>Metriken für den Anruflistenbericht für Reaktionsgruppen

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
<td><p><strong>Caller</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Workflow</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Reaktionsgruppenworkflows.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Startzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit des Beginns des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit des Endes des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in Form eines Headers vom Typ "ms-diagnostics"), die einer SIP-Nachricht angefügt ist, die häufig nützliche Informationen für die Problembehandlung von Fehlern bereitstellt.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

