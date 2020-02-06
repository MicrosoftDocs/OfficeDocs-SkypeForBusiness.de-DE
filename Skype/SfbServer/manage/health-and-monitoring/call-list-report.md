---
title: Bericht zur Antwortgruppen-Anrufliste in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 'Zusammenfassung: Informationen zur reaktionsgruppenanwendung in Skype for Business Server.'
ms.openlocfilehash: 0d3d0001c5537135c2a81ea39706b0def6718fe0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818106"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>Bericht zur Antwortgruppen-Anrufliste in Skype for Business Server

**Zusammenfassung:** Informieren Sie sich über die Anwendung Reaktionsgruppe in Skype for Business Server.

Die Antwortgruppen Anwendung bietet eine Möglichkeit für Skype for Business Server, Telefonanrufe auf der Grundlage der Nummer, die gewählt wurde, und – optional – auf der Antwort des Anrufers auf eine Reihe von Fragen zu beantworten und weiterzuleiten. Normalerweise werden Reaktionsgruppenanrufe nicht an eine Einzelperson, sondern an ein Personenteam weitergeleitet, das als Agentgruppe bezeichnet wird. Wenn beispielsweise jemand die Telefonnummer Ihres Helpdesks anruft, kann Skype for Business Server diesen Anruf automatisch an den ersten verfügbaren Help Desk-Agenten weiterleiten. Alternativ kann Skype for Business Server eine Reihe von Fragen stellen ("drücken Sie 1, wenn Sie Hardwareprobleme haben. Wenn Sie Softwareprobleme haben, drücken Sie die 2. Drücken Sie 3, wenn Sie Netzwerkprobleme haben. ") und leiten Sie dann den Anruf an den am besten geeigneten Helpdesk-Agenten weiter, basierend auf der Antwort auf diese Fragen.

Der Anruflistenbericht für Reaktionsgruppen stellt eine Sammlung von Anrufen dar, die über einen bestimmten Zeitraum und für einen bestimmten Anruftyp getätigt wurden. Im Reaktionsgruppen-Verwendungsbericht (der zuerst geöffnet werden muss, bevor Sie den Anruflistenbericht für Reaktionsgruppen öffnen können) werden die folgenden Anruftypen erkannt:

- **Empfangene Anrufe**. Gesamtzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.

- **Erfolgreiche Anrufe**. Gesamtzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden.

- **Angebotene Anrufe**. Gesamtzahl der Anrufe, die an einen Reaktionsgruppenagent weitergeleitet wurden.

- **Angenommene Anrufe**. Gesamtzahl der Anrufe, die tatsächlich von einem Reaktionsgruppenagent angenommen wurden.

- **Prozentsatz der verlassenen Anrufe.** Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agenten angenommen wurden. Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und 7 davon beantwortet wurden, ziehen Sie 7 von 10 ab, wonach 3 unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt.

- **Durchgestellte Anrufe**. Gesamtzahl der Reaktionsgruppenanrufe, die aufgrund eines Timeouts oder Überlaufs der Warteschleife durchgestellt wurden.

## <a name="accessing-the-response-group-call-list-report"></a>Zugreifen auf den Anruflistenbericht für Reaktionsgruppen

Auf den Bericht "Anruflisten für die Reaktionsgruppe" kann nur zugegriffen werden, indem Sie auf eine der folgenden Metriken klicken, die im [Bericht zur Reaktionsgruppen Nutzung in Skype for Business Server](response-group-usage-report.md)zu finden sind:

- Empfangene Anrufe

- Erfolgreiche Anrufe

- Angebotene Anrufe

- Angenommene Anrufe

- Durchgestellte Anrufe

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Optimale Nutzung des Anruflistenberichts für Reaktionsgruppen

Mithilfe des Anruflistenberichts für Reaktionsgruppen können Sie die angezeigten Daten auf Anrufe mit einem bestimmten Reaktionsgruppenworkflow beschränken. Dazu müssen Sie im Feld „Workflow-URI“ den Workflow-URI (die SIP-Adresse des Workflows) eingeben. Bevor Sie dies tun können, muss das Feld „Workflow-URI“ tatsächlich angezeigt werden. Wenn Sie die Filteroptionen für den Anruflistenbericht für Reaktionsgruppen anzeigen möchten, klicken Sie im oberen linken Teil des Berichtsfensters auf die Schaltfläche „Parameter ein-/ausblenden“.

Beachten Sie, dass im Anruflistenbericht für Reaktionsgruppen keine Informationen zum Antwortcode oder zur Diagnose-ID angezeigt werden, wenn Sie die Maus über eine dieser Metriken halten. Wenn Sie weitere Informationen benötigen, notieren Sie sich möglicherweise den Antwortcode und/oder die Diagnose-ID, und suchen Sie dann im [Bericht "Top-Fehler" in Skype for Business Server](top-failures-report.md)nach diesen Werten.

Bei einer Frage wie „Welcher Einzelworkflow hat die meisten Anrufe empfangen?“ können Sie die folgenden Aktionen ausführen:

1. Legen Sie im Reaktionsgruppen-Verwendungsbericht den gewünschten Zeitraum fest und klicken Sie dann auf die Metrik „Empfangene Anrufe“. Daraufhin wird der Anruflistenbericht für Reaktionsgruppen geöffnet.

2. Exportieren Sie die im Anruflistenbericht für Reaktionsgruppen angezeigten Daten. Sie können beispielsweise die Daten im Microsoft Excel-Format exportieren und diese Daten dann mit Excel in eine Datei mit durch Komma getrennten Werten konvertieren.

3. Führen Sie Ihre Analysen mit Windows PowerShell aus.

Wenn Sie beispielsweise die Daten in einer Datei mit dem Namen „C:\Data\Response_Group_Call_List_Report.csv“gespeichert haben, können Sie anschließend mithilfe des folgenden Befehls die Gesamtzahl empfangener Anrufe für alle Workflows zurückgeben, die im Bericht aufgelistet sind:

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
| **Von** <br/>         | Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
| **Bis** <br/>           | Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/>        |
| **Workflow-URI** <br/> | Bietet Ihnen die Möglichkeit, die zurückgegebenen Daten auf den angegebenen Reaktionsgruppenworkflow zu beschränken. Geben Sie die Workflow-SIP-Adresse ein, um diesen Filter zu verwenden. Beispiel:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **Anrufe** <br/>        | Sie können die folgenden Anruftypen auswählen: <br/>  Empfangene Anrufe <br/>  Erfolgreiche Anrufe <br/>  Angebotene Anrufe <br/>  Angenommene Anrufe <br/>  Durchgestellte Anrufe <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Anruflistenbericht für Reaktionsgruppen für jeden Anruf, der von der Reaktionsgruppenanwendung empfangen wurde, bereitgestellten Informationen aufgelistet.

**Metriken für den Anruflistenbericht für Reaktionsgruppen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anrufer** <br/> |Nein  <br/> |SIP-Adresse des Anrufers.  <br/> |
|**Workflow** <br/> |Nein  <br/> |SIP-Adresse des Reaktionsgruppenworkflows.  <br/> |
|**Startzeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit des Beginns des Anrufs.  <br/> |
|**Endzeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit des Endes des Anrufs.  <br/> |
|**Antwortcode** <br/> |Nein  <br/> |SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |


