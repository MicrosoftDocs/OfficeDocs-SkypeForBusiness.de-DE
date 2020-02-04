---
title: 'Lync Server 2013: Bericht zur Antwortgruppen-Anrufliste'
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
ms.openlocfilehash: 94c06e2029ca1a22a0a9f73249cff3251e2fcbc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Bericht zur Antwortgruppen-Anrufliste in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die Anwendung Reaktionsgruppe bietet eine Möglichkeit für Microsoft lync Server 2013, Telefonanrufe auf der Grundlage der Nummer, die gewählt wurde, und – optional – für die Antworten des Anrufers auf eine Reihe von Fragen zu beantworten und weiterzuleiten. Normalerweise werden Reaktionsgruppenanrufe nicht an eine Einzelperson, sondern an ein Personenteam weitergeleitet, das als Agentgruppe bezeichnet wird. Wenn beispielsweise jemand die Telefonnummer Ihres Helpdesks anruft, kann lync Server 2013 diesen Anruf automatisch an den ersten verfügbaren Help Desk-Agenten weiterleiten. Alternativ kann lync Server eine Reihe von Fragen stellen ("drücken Sie 1, wenn Sie Hardwareprobleme haben. Wenn Sie Softwareprobleme haben, drücken Sie die 2. Drücken Sie 3, wenn Sie Netzwerkprobleme haben. ") und leiten Sie dann den Anruf an den am besten geeigneten Helpdesk-Agenten weiter, basierend auf der Antwort auf diese Fragen.

Der Anruflistenbericht für Reaktionsgruppen stellt eine Sammlung von Anrufen dar, die über einen bestimmten Zeitraum und für einen bestimmten Anruftyp getätigt wurden. Im Reaktionsgruppen-Verwendungsbericht (der zuerst geöffnet werden muss, bevor Sie den Anruflistenbericht für Reaktionsgruppen öffnen können) werden die folgenden Anruftypen erkannt:

  - **Empfangene Anrufe**. Gesamtzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.

  - **Erfolgreiche Anrufe**. Gesamtzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden.

  - **Angebotene Anrufe**. Gesamtzahl der Anrufe, die an einen Reaktionsgruppenagent weitergeleitet wurden.

  - **Angenommene Anrufe**. Gesamtzahl der Anrufe, die tatsächlich von einem Reaktionsgruppenagent angenommen wurden.

  - Prozentsatz abgebrochener Anrufe. Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agenten angenommen wurden. Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und 7 davon beantwortet wurden, ziehen Sie 7 von 10 ab, wonach 3 unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt.

  - **Durchgestellte Anrufe**. Gesamtzahl der Reaktionsgruppenanrufe, die aufgrund eines Timeouts oder Überlaufs der Warteschleife durchgestellt wurden.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>Zugreifen auf den Anruflistenbericht für Reaktionsgruppen

Auf den Bericht "Anruflisten für die Reaktionsgruppe" kann nur zugegriffen werden, indem Sie auf eine der folgenden Metriken im [Bericht zur Reaktionsgruppen Nutzung in lync Server 2013](lync-server-2013-response-group-usage-report.md)klicken:

  - Empfangene Anrufe

  - Erfolgreiche Anrufe

  - Angebotene Anrufe

  - Angenommene Anrufe

  - Durchgestellte Anrufe

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Optimale Nutzung des Anruflistenberichts für Reaktionsgruppen

Mithilfe des Anruflistenberichts für Reaktionsgruppen können Sie die angezeigten Daten auf Anrufe mit einem bestimmten Reaktionsgruppenworkflow beschränken. Dazu müssen Sie im Feld „Workflow-URI“ den Workflow-URI (die SIP-Adresse des Workflows) eingeben. Bevor Sie dies tun können, muss das Feld „Workflow-URI“ tatsächlich angezeigt werden. Wenn Sie die Filteroptionen für den Anruflistenbericht für Reaktionsgruppen anzeigen möchten, klicken Sie im oberen linken Teil des Berichtsfensters auf die Schaltfläche „Parameter ein-/ausblenden“.

Beachten Sie, dass im Anruflistenbericht für Reaktionsgruppen keine Informationen zum Antwortcode oder zur Diagnose-ID angezeigt werden, wenn Sie die Maus über eine dieser Metriken halten. Wenn Sie weitere Informationen benötigen, notieren Sie sich möglicherweise den Antwortcode und/oder die Diagnose-ID, und suchen Sie dann im [Bericht "Top-Fehler" in lync Server 2013](lync-server-2013-top-failures-report.md)nach diesen Werten.

Bei einer Frage wie „Welcher Einzelworkflow hat die meisten Anrufe empfangen?“ können Sie die folgenden Aktionen ausführen:

1.  Legen Sie im Reaktionsgruppen-Verwendungsbericht den gewünschten Zeitraum fest und klicken Sie dann auf die Metrik „Empfangene Anrufe“. Daraufhin wird der Anruflistenbericht für Reaktionsgruppen geöffnet.

2.  Exportieren Sie die im Anruflistenbericht für Reaktionsgruppen angezeigten Daten. Sie können beispielsweise die Daten im Microsoft Excel-Format exportieren und diese Daten dann mit Excel in eine Datei mit durch Komma getrennten Werten konvertieren.

3.  Führen Sie Ihre Analysen mit Windows PowerShell aus.

Wenn Sie beispielsweise die Daten in einer Datei mit dem Namen C\\: Daten\\Antwort\_Gruppen\_-Anruf\_Listen\_Bericht. csv gespeichert haben, können Sie den folgenden Befehl verwenden, um die Gesamtzahl der empfangenen Anrufe für jeden im Bericht aufgelisteten Workflow zurückzugeben:

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
<td><p><strong>Startzeitpunkt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit des Beginns des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endzeitpunkt</strong></p></td>
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
<td><p>Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

