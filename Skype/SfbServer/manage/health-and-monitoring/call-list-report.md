---
title: Anruflistenbericht für Reaktionsgruppen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 'Zusammenfassung: Erfahren Sie mehr über die Reaktionsgruppenanwendung in Skype for Business Server.'
ms.openlocfilehash: 46193159c9cb29f63b3fc4ca9053a3e9dd098d01
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773615"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>Anruflistenbericht für Reaktionsgruppen in Skype for Business Server

**Zusammenfassung:** Erfahren Sie mehr über die Reaktionsgruppenanwendung in Skype for Business Server.

Die Reaktionsgruppenanwendung bietet Skype for Business Server die Möglichkeit, Anrufe basierend auf der gewählten Nummer und optional auf den Antworten des Anrufers auf eine Reihe von Fragen zu beantworten und weiterzuleiten. Reaktionsgruppenanrufe werden normalerweise nicht an eine Einzelperson weitergeleitet, sondern stattdessen an ein Team von Personen, die als eine Agentgruppe bezeichnet wird. Wenn beispielsweise jemand die Telefonnummer ihres Helpdesks anruft, können Skype for Business Server diesen Anruf automatisch an den ersten verfügbaren Helpdesk-Agent weiterleiten. Alternativ können Skype for Business Server eine Reihe von Fragen stellen ("Drücken Sie 1, wenn Sie Hardwareprobleme haben. Drücken Sie 2, wenn Sie Softwareprobleme haben. Drücken Sie 3, wenn Netzwerkprobleme auftreten.") und leiten Sie den Anruf dann basierend auf der Antwort auf diese Fragen an den am besten geeigneten Helpdesk-Agenten weiter.

Der  Anruflistenbericht für Reaktionsgruppen stellt eine Sammlung von Anrufen dar, die über einen bestimmten Zeitraum und für einen bestimmten Anruftyp getätigt wurden. Im Reaktionsgruppen-Verwendungsbericht (der zuerst geöffnet werden muss, bevor Sie den Anruflistenbericht für Reaktionsgruppen öffnen können) werden die folgenden Anruftypen erkannt:

- **Empfangene Anrufe**. Gesamtzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.

- **Erfolgreiche Anrufe**. Gesamtanzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden.

- **Angebotene Anrufe**. Gesamtanzahl der Anrufe, die an einen Reaktionsgruppen-Agenten weitergeleitet wurden.

- **Angenommene Anrufe**. Gesamtanzahl der Anrufe, die von einem Reaktionsgruppen-Agenten tatsächlich angenommen wurden.

- **Prozentsatz der abgebrochenen Anrufe.** Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agenten angenommen wurden. Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und 7 davon beantwortet wurden, ziehen Sie 7 von 10 ab, wonach drei unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt..

- **Durchgestellte Anrufe**. Gesamtzahl der Reaktionsgruppenanrufe, die aufgrund eines Timeouts oder Überlaufs der Warteschleife durchgestellt wurden.

## <a name="accessing-the-response-group-call-list-report"></a>Zugreifen auf den Anruflistenbericht für Reaktionsgruppen

Auf den Anruflistenbericht für Reaktionsgruppen kann nur zugegriffen werden, indem Sie auf eine der folgenden Metriken klicken, die im Nutzungsbericht über [Reaktionsgruppen in Skype for Business Server](response-group-usage-report.md)zu finden sind:

- Empfangene Anrufe

- Erfolgreiche Anrufe

- Angebotene Anrufe

- Angenommene Anrufe

- Durchgestellte Anrufe

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Optimale Nutzung des Anruflistenberichts für Reaktionsgruppen

Mithilfe des Anruflistenberichts für Reaktionsgruppen können Sie die angezeigten Daten auf Anfrufe mit einem bestimmten Reaktionsgruppenworkflow beschränken. Dazu müssen Sie im Feld "Workflow-URI" den Workflow-URI (die SIP-Adresse des Workflows) eingeben. Bevor Sie dies tun können, muss das Feld "Workflow-URI" tatsächlich angezeigt werden. Wenn Sie die Filteroptionen für den Anruflistenbericht für Reaktionsgruppen anzeigen möchten, klicken Sie im oberen linken Teil des Berichtsfensters auf die Schaltfläche "Parameter ein-/ausblenden".

Beachten Sie, dass im Anruflistenbericht für Reaktionsgruppen keine Informationen zum Antwortcode oder zur Diagnose-ID angezeigt werden, wenn Sie die Maus über eine dieser Metriken halten. Wenn Sie weitere Informationen benötigen, notieren Sie sich möglicherweise den Antwortcode und/oder die Diagnose-ID, und suchen Sie dann im [Bericht über häufigste Fehler in Skype for Business Server](top-failures-report.md)nach diesen Werten.

Bei einer Frage wie "Welcher Einzelworkflow hat die meisten Anrufe empfangen?" können Sie die folgenden Aktionen ausführen:

1. Legen Sie im Reaktionsgruppen-Verwendungsbericht den gewünschten Zeitraum fest, und klicken Sie dann auf die Metrik "Empfangene Anrufe". Daraufhin wird der Anruflistenbericht für Reaktionsgruppen geöffnet.

2. Exportieren Sie die im Anruflistenbericht für Reaktionsgruppen angezeigten Daten. Sie können beispielsweise die Daten im Microsoft Excel-Format exportieren und diese Daten dann mit Excel in eine Datei mit durch Komma getrennten Werten konvertieren.

3. Führen Sie Ihre Analysen mit Windows PowerShell aus.

Wenn Sie beispielsweise die Daten in einer Datei mit dem Namen "C:\Data\Response_Group_Call_List_Report.csv"gespeichert haben, können Sie anschließend mithilfe des folgenden Befehls die Gesamtzahl empfangener Anrufe für alle Workflows zurückgeben, die im Bericht aufgelistet sind:

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

Dadurch werden Informationen bereitgestellt, die den Folgenden ähneln:

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anruflistenbericht für Reaktionsgruppen verwenden können.

**Filter für den Anruflistenbericht für Reaktionsgruppen**


| **Name**               | **Beschreibung**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **From** <br/>         | Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
| **Bis** <br/>           | Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/>        |
| **Workflow-URI** <br/> | Damit können Sie die zurückgegebenen Daten auf den angegebenen Reaktionsgruppen-Workflow beschränken. Geben Sie zur Verwendung dieses Filters die SIP-Adresse des Workflows ein. Beispielsweise:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **Aufrufe** <br/>        | Sie können die folgenden Anruftypen auswählen: <br/>  Empfangene Anrufe <br/>  Erfolgreiche Anrufe <br/>  Angebotene Anrufe <br/>  Angenommene Anrufe <br/>  Durchgestellte Anrufe <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Anruflistenbericht für Reaktionsgruppen für jeden Anruf, der von der Reaktionsgruppenanwendung empfangen wurde, bereitgestellten Informationen aufgelistet.

**Metriken für den Anruflistenbericht für Reaktionsgruppen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Caller** <br/> |Nein  <br/> |SIP-Adresse des Anrufers.  <br/> |
|**Workflow** <br/> |Nein  <br/> |SIP-Adresse des Reaktionsgruppenworkflows.  <br/> |
|**Startzeit** <br/> |Nein  <br/> |Datum und Uhrzeit des Beginns des Anrufs.  <br/> |
|**Endzeit** <br/> |Nein  <br/> |Datum und Uhrzeit des Endes des Anrufs.  <br/> |
|**Antwortcode** <br/> |Nein  <br/> |SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in Form eines Headers vom Typ "ms-diagnostics"), die einer SIP-Nachricht angefügt ist, die häufig nützliche Informationen für die Problembehandlung von Fehlern bereitstellt.  <br/> |


