---
title: Nutzungsbericht über Reaktionsgruppen in Skype for Business Server
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
ms.assetid: 3248b320-a552-400a-8485-6891af4eb0f3
description: 'Zusammenfassung: Erfahren Sie mehr über die Reaktionsgruppenanwendung in Skype for Business Server.'
ms.openlocfilehash: 7b26114e81141e4e77bc3fd6b3887ab109526f50
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768723"
---
# <a name="response-group-usage-report-in-skype-for-business-server"></a>Nutzungsbericht über Reaktionsgruppen in Skype for Business Server

**Zusammenfassung:** Erfahren Sie mehr über die Reaktionsgruppenanwendung in Skype for Business Server.

Die Reaktionsgruppenanwendung bietet Skype for Business Server die Möglichkeit, Anrufe basierend auf der gewählten Nummer und optional auf den Antworten des Anrufers auf eine Reihe von Fragen zu beantworten und weiterzuleiten. Reaktionsgruppenanrufe werden normalerweise nicht an eine Einzelperson weitergeleitet, sondern stattdessen an ein Team von Personen, die als eine Agentgruppe bezeichnet wird. Wenn beispielsweise jemand die Telefonnummer ihres Helpdesks anruft, können Skype for Business Server diesen Anruf automatisch an den ersten verfügbaren Helpdesk-Agent weiterleiten. Alternativ können Skype for Business Server eine Reihe von Fragen stellen ("Drücken Sie 1, wenn Sie Hardwareprobleme haben. Drücken Sie 2, wenn Sie Softwareprobleme haben. Drücken Sie 3, wenn Sie Netzwerkprobleme haben.") und leiten Sie den Anruf basierend auf der Antwort auf diese Fragen an den am besten geeigneten Helpdesk-Agenten weiter.

Der Nutzungsbericht über die Reaktionsgruppe gibt einen detaillierten Einblick in die Anzahl der Telefonanrufe, die von allen Reaktionsgruppenworkflows empfangen wurden. Diese Anrufe werden dann in spezifischere Kategorien unterteilt, z. B. Angebotene Anrufe, Angenommene Anrufe und Prozentsatz abgebrochener Anrufe.

Bei der Verwendung des Nutzungsberichts über die Reaktionsgruppe ist es wichtig, den Unterschied zwischen den gemeldeten Anruftypen zu verstehen:

- **Empfangene Anrufe**. Gesamtanzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung.

- **Erfolgreiche Anrufe**. Gesamtanzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden.

- **Angebotene Anrufe**. Gesamtanzahl der Anrufe, die an einen Reaktionsgruppen-Agenten weitergeleitet wurden.

- **Angenommene Anrufe**. Gesamtanzahl der Anrufe, die von einem Reaktionsgruppen-Agenten tatsächlich angenommen wurden.

- **Prozentsatz abgebrochener Anrufe**. Prozentsatz der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Agenten angenommen wurden. Dieser Wert wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und 7 davon beantwortet wurden, ziehen Sie 7 von 10 ab, wonach drei unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt..

- **Durchgestellte Anrufe**. Gesamtanzahl der Reaktionsgruppenanrufe, die aufgrund einer Timeout- oder Überlaufwarteschleife durchgestellt wurden.

Wenn Sie sich den Nutzungsbericht über die Reaktionsgruppe ansehen und sich nicht mehr an die Definition eines Anruftyps erinnern können, halten Sie einfach die Maus über die Beschriftung des entsprechenden Anruftyps. Daraufhin wird eine QuickInfo mit einer kurzen Beschreibung des Anruftyps angezeigt.

Mit einem Nutzungsbericht über Reaktionsgruppe können Sie nach einem Workflow-URI (die mit dem Workflow verknüpfte SIP-Adresse) filtern. Workflow-URIs werden nicht tatsächlich im Bericht angezeigt. Wenn Sie z. B. mehr darüber erfahren möchten, welche Workflows die meisten Anrufe entgegennehmen oder in welchen Workflows die meisten Anrufe durchgestellt werden, klicken Sie auf die entsprechende Metrik, um den Anruflistenbericht für Reaktionsgruppen für diesen bestimmten Zeitraum anzuzeigen. In diesem Bericht werden die Workflow-URIs aufgelistet.

## <a name="accessing-the-response-group-usage-report"></a>Zugreifen auf den Nutzungsbericht über die Reaktionsgruppe

Der Zugriff auf den Nutzungsbericht für Reaktionsgruppen erfolgt über die Startseite für Überwachungsberichte. Sie können einen Drilldown zum [Anruflistenbericht](call-list-report.md) für Reaktionsgruppen in Skype for Business Server ausführen, indem Sie auf eine der folgenden Metriken klicken:

- Empfangene Anrufe

- Erfolgreiche Anrufe

- Angebotene Anrufe

- Angenommene Anrufe

- Durchgestellte Anrufe

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Optimale Verwendung des Nutzungsberichts über die Reaktionsgruppe

Eine der interessantesten Verwendungen des Nutzungsberichts über die Reaktionsgruppe ist vielleicht nicht auf den ersten Blick erkennbar: die Möglichkeit zum Abrufen von Nutzungsinformationen für einen einzelnen Reaktionsgruppenworkflow.

> [!CAUTION]
> Bei einem Reaktionsgruppenworkflow handelt es sich im Wesentlichen um eine Reihe von Anweisungen, die bestimmen, was Skype for Business Server bewirkt, wenn ein Benutzer eine bestimmte Telefonnummer wählt. Hierzu ist jeder Workflow eindeutig einer Telefonnummer zugeordnet. Wenn jemand diese Nummer anruft, wird durch den Workflow festgelegt, wie der Anruf verarbeitet wird. Beispielsweise kann der Anruf zur Beantwortung einer Reihe von Fragen an das interaktive Sprachantwortsystem weitergeleitet werden, sodass der Anrufer zur Eingabe weiterer Informationen aufgefordert wird ("Drücken Sie 1 für Hardwaresupport. Drücken Sie 2 für Softwaresupport."). Alternativ dazu kann der Anruf vom Workflow in eine Warteschleife gestellt und gehalten werden, bis ein Agent zum Entgegennehmen des Anrufs verfügbar ist. Auch die Verfügbarkeit von Agenten zur Anrufannahme wird vom Workflow vorgegeben: Mithilfe von Workflows werden sowohl Geschäftszeiten (die Wochentage und Tageszeiten, zu denen Agenten für die Annahme von Anrufen verfügbar sind) als auch Feiertage (Tage, an denen keine Agenten zur Anrufannahme bereitstehen) konfiguriert. Jedes Mal, wenn eine Telefonnummer gewählt wird, die zur Reaktionsgruppenanwendung gehört, wird eigentlich ein Reaktionsgruppenworkflow angerufen. 

Obwohl im Nutzungsbericht über Reaktionsgruppe keine Workflow-URIs angezeigt werden, kann dennoch die Nutzungsstatistik für einen einzelnen Workflow angezeigt werden, was oftmals sehr nützlich sein kann. Angenommen, Sie haben vor kurzem eine neue Anzeigenkampagne lanciert und möchten gern erfahren, ob interessierte Leute anrufen, um mehr über dieses Produkt zu erfahren. Wenn Sie mit der in der Anzeigenkampagne genannten Telefonnummer einen Reaktionsgruppenworkflow verknüpft haben, können Sie auf einfache Weise feststellen, wie viele Personen (wenn überhaupt) diese Nummer gewählt haben.

Sie können auch einen ähnlichen Ansatz verwenden, um die Anzahl der Anrufe zu messen, die von Ihrem internen Helpdesk oder Ihrer Kundendienstabteilung behandelt werden.

Um Nutzungsstatistiken für einen bestimmten Workflow zu überprüfen, geben Sie den Workflow-URI in das Feld "Workflow-URI" ein. Wie bereits erwähnt, werden Workflow-URIs (die einem Workflow zugeordnete SIP-Adresse) nicht im Bericht angezeigt. Das bedeutet, dass Sie eine andere Möglichkeit zum Ermitteln des URI eines Workflows finden müssen. Eine Möglichkeit hierfür ist die Verwendung von Windows PowerShell und der Skype for Business Server-Verwaltungsshell. Mit diesem Befehl werden beispielsweise die URIs für alle Reaktionsgruppenworkflows zurückgegeben:

```PowerShell
Get-CsRgsWorkflow | Select-Object Name, PrimaryUri
```

Dadurch werden Daten ähnlich wie die folgenden zurückgegeben:

<pre>
Name                            PrimaryUri
----                            ----------
Customer Support                sip:support@litwareinc.com
Help Desk                       sip:helpdesk@litwareinc.com
New Ad Campaign                 sip:newads@litwareinc.com
</pre>

Mit diesem Befehl werden Informationen für einen einzelnen Workflow mit dem Namen "New Ad Campaign" zurückgegeben:

```PowerShell
Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri
```

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Reaktionsgruppen-Verwendungsbericht Daten für all Ihre Reaktionsgruppen-Workflows anzeigen oder für einen einzelnen Workflow. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Reaktionsgruppen-Verwendungsbericht verwenden können.

**Reaktionsgruppen-Verwendungsbericht – Filter**


| **Name**               | **Beschreibung**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **From** <br/>         | Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/>                                                                                                                              |
| **Bis** <br/>           | Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/>                                                                                                                                     |
| **Intervall** <br/>     | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate werden angezeigt) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie z. B. das Intervall "Täglich" mit dem Startdatum 7.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. s. Daten insgesamt 31 Tage). <br/> |
| **Workflow-URI** <br/> | Damit können Sie die zurückgegebenen Daten auf den angegebenen Reaktionsgruppen-Workflow beschränken. Geben Sie zur Verwendung dieses Filters die SIP-Adresse des Workflows ein. Beispielsweise:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Reaktionsgruppen-Verwendungsbericht angegeben werden.

**Reaktionsgruppen-Verwendungsbericht – Metriken**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das ausgewählte Zeitintervall an. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 7.07.2015 klicken, wird eine stündliche Aufschlüsselung der Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Empfangene Anrufe** <br/> |Nein  <br/> |Gesamtanzahl der empfangenen Anrufe von allen Instanzen der Reaktionsgruppenanwendung. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.  <br/> |
|**Erfolgreiche Anrufe** <br/> |Nein  <br/> |Gesamtanzahl der Anrufe, die von der Reaktionsgruppenanwendung angenommen wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.  <br/> |
|**Angebotene Anrufe** <br/> |Nein  <br/> |Gesamtanzahl der Anrufe, die an einen Reaktionsgruppenvertreter weitergeleitet wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.  <br/> |
|**Angenommene Anrufe** <br/> |Nein  <br/> |Gesamtanzahl der Anrufe, die von einem Reaktionsgruppenvertreter tatsächlich angenommen wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.  <br/> |
|**Prozentsatz abgebrochener Anrufe** <br/> |Nein  <br/> |Gesamtanzahl der Anrufe, die von der Reaktionsgruppenanwendung empfangen, aber nicht von einem Vertreter angenommen wurden. Dies wird berechnet, indem die angenommenen Anrufe von den empfangenen Anrufen abgezogen werden und dieser Wert dann durch die Anzahl der empfangenen Anrufe geteilt wird. Wenn Sie beispielsweise 10 Anrufe empfangen haben und sieben davon beantwortet wurden, ziehen Sie sieben von 10 ab, wonach drei unbeantwortete Anrufe übrig bleiben. Dieser Wert wird dann durch 10 geteilt, woraus sich ein Prozentsatz von 30 % für abgebrochene Anrufe ergibt.  <br/> |
|**Durchschnittliche Anrufminuten pro Agent** <br/> |Nein  <br/> |Durchschnittliche Dauer, die ein Reaktionsgruppenvertreter für einen Anruf aufwendete.  <br/> |
|**Durchgestellte Anrufe** <br/> |Nein  <br/> |Gesamtanzahl der Reaktionsgruppenanrufe, die aufgrund einer Timeout- oder Überlaufwarteschleife durchgestellt wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht die Anrufliste der Reaktionsgruppe für die gewählte Zeitspanne an.  <br/> |


