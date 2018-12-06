---
title: 'Lync Server 2013: Anruflistenbericht für Reaktionsgruppen'
TOCTitle: Anruflistenbericht für Reaktionsgruppen
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615443(v=OCS.15)
ms:contentKeyID: 49294956
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anruflistenbericht für Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Reaktionsgruppenanwendung stellt eine Möglichkeit für Microsoft Lync Server 2013 dar, Anrufe basierend auf der gewählten Nummer und optional basierend auf den Antworten des Anrufers auf eine Reihe von Fragen entgegenzunehmen und weiterzuleiten. Normalerweise werden Reaktionsgruppenanrufe nicht an eine Einzelperson, sondern an ein Personenteam weitergeleitet, das als Agentgruppe bezeichnet wird. Wenn beispielsweise jemand die Telefonnummer für Ihren Helpdesk anruft, kann Lync Server 2013 diesen Anruf automatisch an den ersten freien Helpdeskmitarbeiter weiterleiten. Alternativ dazu kann Lync Server eine Reihe von Fragen stellen ("Wenn Sie Hardwareprobleme haben, drücken Sie die 1. Wenn Sie Softwareprobleme haben, drücken Sie die 2. Wenn Sie Netzwerkprobleme haben, drücken Sie die 3.") und den Anruf dann basierend auf der Antwort auf diese Fragen an den am besten geeigneten Helpdeskagent weiterleiten.

Der Anruflistenbericht für Reaktionsgruppen stellt eine Sammlung von Anrufen dar, die über einen bestimmten Zeitraum und für einen bestimmten Anruftyp getätigt wurden. Im Reaktionsgruppen-Verwendungsbericht (der zuerst geöffnet werden muss, bevor Sie den Anruflistenbericht für Reaktionsgruppen öffnen können) werden die folgenden Anruftypen erkannt:

  - **Empfangene Anrufe** . Gesamtzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.

  - **Erfolgreiche Anrufe** . Gesamtzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden.

  - **Angebotene Anrufe** . Gesamtzahl der Anrufe, die an einen Reaktionsgruppenagent weitergeleitet wurden.

  - **Angenommene Anrufe** . Gesamtzahl der Anrufe, die tatsächlich von einem Reaktionsgruppenagent angenommen wurden.

  - Prozentsatz der abgebrochenen Anrufe. Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agent angenommen wurden. Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise zehn Anrufe empfangen haben und sieben davon beantwortet wurden, ziehen Sie sieben von zehn ab, wonach drei unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch zehn geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt.

  - **Durchgestellte Anrufe** . Gesamtzahl der Reaktionsgruppenanrufe, die aufgrund eines Timeouts oder Überlaufs der Warteschleife durchgestellt wurden.

## Zugreifen auf den Anruflistenbericht für Reaktionsgruppen

Der Zugriff auf den Anruflistenbericht für Reaktionsgruppen ist nur durch Klicken auf eine der folgenden Metriken möglich, die im [Nutzungsbericht über die Reaktionsgruppe in Lync Server 2013](lync-server-2013-response-group-usage-report.md) enthalten sind:

  - Empfangene Anrufe

  - Erfolgreiche Anrufe

  - Angebotene Anrufe

  - Angenommene Anrufe

  - Durchgestellte Anrufe

## Optimale Nutzung des Anruflistenberichts für Reaktionsgruppen

Mithilfe des Anruflistenberichts für Reaktionsgruppen können Sie die angezeigten Daten auf Anfrufe mit einem bestimmten Reaktionsgruppenworkflow beschränken. Dazu müssen Sie im Feld "Workflow-URI" den Workflow-URI (die SIP-Adresse des Workflows) eingeben. Bevor Sie dies tun können, muss das Feld "Workflow-URI" tatsächlich angezeigt werden. Wenn Sie die Filteroptionen für den Anruflistenbericht für Reaktionsgruppen anzeigen möchten, klicken Sie im oberen linken Teil des Berichtsfensters auf die Schaltfläche "Parameter ein-/ausblenden".

Beachten Sie, dass im Anruflistenbericht für Reaktionsgruppen keine Informationen zum Antwortcode oder zur Diagnose-ID angezeigt werden, wenn Sie die Maus über eine dieser Metriken halten. Wenn Sie weitere Informationen benötigen, können Sie sich den Antwortcode und/oder die Diagnose-ID notieren und dann im [Bericht über häufigste Fehler in Lync Server 2013](lync-server-2013-top-failures-report.md) nach diesen Werten suchen.

Bei einer Frage wie "Welcher Einzelworkflow hat die meisten Anrufe empfangen?" können Sie die folgenden Aktionen ausführen:

1.  Legen Sie im Reaktionsgruppen-Verwendungsbericht den gewünschten Zeitraum fest, und klicken Sie dann auf die Metrik "Empfangene Anrufe". Daraufhin wird der Anruflistenbericht für Reaktionsgruppen geöffnet.

2.  Exportieren Sie die im Anruflistenbericht für Reaktionsgruppen angezeigten Daten. Sie können beispielsweise die Daten im Microsoft Excel-Format exportieren und diese Daten dann mit Excel in eine Datei mit durch Komma getrennten Werten konvertieren.

3.  Führen Sie Ihre Analysen mit Windows PowerShell aus.

Wenn Sie beispielsweise die Daten in einer Datei mit dem Namen "C:\\Data\\Response\_Group\_Call\_List\_Report.csv"gespeichert haben, können Sie anschließend mithilfe des folgenden Befehls die Gesamtzahl empfangener Anrufe für alle Workflows zurückgeben, die im Bericht aufgelistet sind:

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

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anruflistenbericht für Reaktionsgruppen verwenden können.

### Filter für den Anruflistenbericht für Reaktionsgruppen

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
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>07.07.12</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>03.07.12</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>07.07.12</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>03.07.12</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Workflow-URI</strong></p></td>
<td><p>Bietet Ihnen die Möglichkeit, die zurückgegebenen Daten auf den angegebenen Reaktionsgruppenworkflow zu beschränken. Geben Sie die Workflow-SIP-Adresse ein, um diesen Filter zu verwenden. Beispiel:</p>
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


## Metriken

In der folgenden Tabelle sind die im Anruflistenbericht für Reaktionsgruppen für jeden Anruf, der von der Reaktionsgruppenanwendung empfangen wurde, bereitgestellten Informationen aufgelistet.

### Metriken für den Anruflistenbericht für Reaktionsgruppen

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
<td><p><strong>Anrufer</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Workflow</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Reaktionsgruppenworkflows.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beginn</strong></p></td>
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
<td><p>Eindeutige ID (in Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die einer SIP-Nachricht angefügt ist, die häufig nützliche Informationen für die Problembehandlung von Fehlern bereitstellt.</p></td>
</tr>
</tbody>
</table>

