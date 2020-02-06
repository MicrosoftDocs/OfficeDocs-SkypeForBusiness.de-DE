---
title: Bericht zur PSTN-Konferenz Zusammenfassung in Skype for Business Server
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
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Zusammenfassung: erfahren Sie mehr über den Bericht zur PSTN-Konferenz Zusammenfassung in Skype for Business Server.'
ms.openlocfilehash: 1b45ab5c58f9796d2019c96731d40cf3f567a8ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817754"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Bericht zur PSTN-Konferenz Zusammenfassung in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den Bericht zur PSTN-Konferenz Zusammenfassung in Skype for Business Server.
  
In Skype for Business Server ist eine PSTN-Konferenz eine Konferenz, bei der sich mindestens ein Teilnehmer über ein PSTN-Telefon (Public Switched Telephone Network) in den Audioteil einwählt. (Bei einem PSTN-Telefon handelt es sich um ein Festnetztelefon, ein Mobiltelefon oder ein anderes Telefon, das keine VoIP-Nutzung durchführt.) Obwohl Sie in den Überwachungsberichten als PSTN-Konferenzen bezeichnet werden, werden diese Konferenzen vielleicht häufiger als Einwahlkonferenzen bezeichnet.
  
Der „Zusammenfassende Bericht über PSTN-Konferenzen“ liefert Informationen zu allen in Ihrer Organisation durchgeführten PSTN-Konferenzen (das sind alle Konferenzen mit mindestens einem Einwahlbenutzer). Der Bericht enthält Informationen zur Gesamtanzahl der PSTN-Konferenzen, der Gesamtanzahl der Teilnehmer an diesen Konferenzen und vielleicht als wichtigste Information, die Gesamtanzahl der Einwahlbenutzer (Metrik der PSTN-Teilnehmer insgesamt).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Zugreifen auf den „Zusammenfassenden Bericht über PSTN-Konferenzen“

Auf der Startseite „Überwachungsberichte“ können Sie auf den „Zusammenfassenden Bericht über PSTN-Konferenzen“ zugreifen. Dieser Bericht ist nicht mit anderen Berichten verknüpft. Beachten Sie, dass Sie keine ausführlichen Anrufinformationen für eine PSTN-Konferenz abrufen können. Als teilweise Erklärung hierfür kann angeführt werden, dass die einzelnen Endpunkte für die Übertragung dieser Informationen verantwortlich sind. PSTN-Telefone können keine ausführlichen Anrufinformationen nachverfolgen oder übertragen.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Optimale Nutzung des „Zusammenfassenden Berichts über PSTN-Konferenzen“

Um den Prozentsatz aller ihrer Konferenzen zu ermitteln, die Einwahlbenutzer einbeziehen, vergleichen Sie den Wert der Gesamt Metrik für PSTN-Konferenzen mit der Gesamtzahl der Konferenzen, die im [Bericht "Konferenz Zusammenfassung" in Skype for Business Server](conference-summary-report.md)zu finden ist.
  
Wenn Sie nicht so viele PSTN-Konferenzen sehen, wie Sie vielleicht erwartet hätten, sollten Sie Bedenken, dass die Möglichkeit zum Organisieren einer Konferenz, die Einwahlbenutzer ermöglicht, von der konferenzrichtlinie abhängt, die einem Benutzer zugewiesen wurde: Wenn nur wenige ihrer Benutzer PS halten dürfen TN-Konferenzen sehen Sie offensichtlich nur sehr wenige PSTN-Konferenzen. Sie können schnell überprüfen, welche ihrer Konferenzrichtlinien (sofern vorhanden) es Benutzern ermöglichen, PSTN-Konferenzen zu planen, indem Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ausführen:
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:
  
<pre>
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True
</pre>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im zusammenfassenden Bericht über PSTN-Konferenz festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über PSTN-Konferenz verwenden können.
  
**Filter im Zusammenfassenden Bericht über PSTN-Konferenz**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Bericht über PSTN-Konferenz angegeben werden.
  
**Metriken im Zusammenfassenden Bericht über PSTN-Konferenz**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das ausgewählte Zeitintervall an. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall „Täglich“ verwenden und auf 07.07.2015 klicken, sehen Sie die nach Stunden aufgeschlüsselten Benutzerregistrierungsaktivitäten an diesem Tag.  <br/> |
|**PSTN-Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen, die Zugriff per Einwahl erlaubten.  <br/> |
|**Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Personen, die an Konferenzen mit Einwahlzugriff teilnahmen.  <br/> |
|**Gesamtdauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die Gesamtdauer von Konferenzen mit Audio oder Video.  <br/> |
|**Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben** <br/> |Nein  <br/> |Die Gesamtdauer, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Teilnehmer hat 5 Minuten in einer A/V-Konferenz verbracht und ein zweiter Benutzer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.  <br/> |
|**PSTN-Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die sich in Konferenzen einwählten, die Zugriff per Einwahl erlaubten.  <br/> |
|**PSTN-Teilnehmerminuten insgesamt** <br/> |Nein  <br/> |Die Gesamtdauer, die Einwahlbenutzer in Konferenzen verbrachten. Beispiel: Angenommen, ein Einwahlteilnehmer hat 5 Minuten in einer Konferenz verbracht und ein zweiter Teilnehmer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.  <br/> |
|**Eindeutige Konferenzorganisatoren** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Konferenz mit Einwahlzugriff organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.  <br/> |
   

