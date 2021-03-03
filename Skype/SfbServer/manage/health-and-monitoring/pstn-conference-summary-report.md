---
title: Zusammenfassender Bericht über Festnetzkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Zusammenfassung: Erfahren Sie mehr über den zusammenfassenden Bericht über PSTN-Konferenz in Skype for Business Server.'
ms.openlocfilehash: aab91995a2c987e1a6e3a10d1f6fc8791b19a4b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814375"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Zusammenfassender Bericht über Festnetzkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Zusammenfassenden Bericht über PSTN-Konferenz in Skype for Business Server.
  
In Skype for Business Server ist eine PstN-Konferenz eine Beliebige Konferenz, bei der sich mindestens ein Teilnehmer über ein Festnetztelefon (Public Switched Telephone Network) in den Audioteil einwählt. (Ein Festnetztelefon ist ein Festnetztelefon, ein Mobiltelefon oder ein anderes Telefon, das Voice over IP nicht verwendet.) Obwohl diese Konferenzen in den Überwachungsberichten als PSTN-Konferenzen bezeichnet werden, werden diese Konferenzen vielleicht häufiger als Einwahlkonferenzen bezeichnet.
  
Der "Zusammenfassende Bericht über PSTN-Konferenzen" liefert Informationen zu allen in Ihrer Organisation durchgeführten PSTN-Konferenzen (das sind alle Konferenzen mit mindestens einem Einwahlbenutzer). Der Bericht enthält Informationen zur Gesamtanzahl der PSTN-Konferenzen, der Gesamtanzahl der Teilnehmer an diesen Konferenzen und vielleicht als wichtigste Information, die Gesamtanzahl der Einwahlbenutzer (Metrik der PSTN-Teilnehmer insgesamt).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Zugreifen auf den "Zusammenfassenden Bericht über PSTN-Konferenzen"

Auf der Startseite "Überwachungsberichte" können Sie auf den "Zusammenfassenden Bericht über PSTN-Konferenzen" zugreifen. Dieser Bericht ist nicht mit anderen Berichten verknüpft. Beachten Sie, dass Sie keine ausführlichen Anrufinformationen für eine PSTN-Konferenz abrufen können. Als teilweise Erklärung hierfür kann angeführt werden, dass die einzelnen Endpunkte für die Übertragung dieser Informationen verantwortlich sind. PSTN-Telefone können keine ausführlichen Anrufinformationen nachverfolgen oder übertragen.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Optimale Nutzung des "Zusammenfassenden Berichts über PSTN-Konferenzen"

Um den Prozentsatz aller Konferenzen zu ermitteln, die Einwahlbenutzer umfassen, vergleichen Sie den Wert der Metriken für pstN-Konferenzen insgesamt mit der Metrik "Konferenzen insgesamt", die im Zusammenfassenden Konferenzbericht [in Skype for Business Server](conference-summary-report.md)enthalten sind.
  
Wenn sie nicht so viele PSTN-Konferenzen sehen, wie Sie möglicherweise erwartet haben, denken Sie daran, dass die Möglichkeit, eine Konferenz zu organisieren, die Einwahlbenutzer zulässt, von der Konferenzrichtlinie abhängt, die einem Benutzer zugewiesen wurde: Wenn nur wenige Benutzer PSTN-Konferenzen halten dürfen, werden offensichtlich nur sehr wenige Festnetzkonferenzen angezeigt. Sie können schnell überprüfen, welche Ihrer Konferenzrichtlinien (sofern vorhanden) Benutzern das Planen von Festnetzkonferenzen ermöglichen, indem Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ausführen:
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Es werden Daten nach dem folgenden Muster zurückgegeben:
  
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

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Bericht über PSTN-Konferenz festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über PSTN-Konferenz verwenden können.
  
**Filter im Zusammenfassenden Bericht über PSTN-Konferenz**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate werden angezeigt) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Intervall "Täglich" mit dem Startdatum 7.7.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 00:00 Uhr bis 07.09.2015 00:00 Uhr angezeigt (d. h. Daten von insgesamt 31 Tagen). <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Bericht über PSTN-Konferenz angegeben werden.
  
**Metriken im Zusammenfassenden Bericht über PSTN-Konferenz**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das ausgewählte Zeitintervall an. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall "Täglich" verwenden und auf den 07.07.2015 klicken, wird eine stündlich aufschlüsselte Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**PSTN-Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen, die Zugriff per Einwahl erlaubten.  <br/> |
|**Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Personen, die an Konferenzen mit Einwahlzugriff teilnahmen.  <br/> |
|**Gesamtdauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die Gesamtdauer von Konferenzen mit Audio oder Video.  <br/> |
|**Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben** <br/> |Nein  <br/> |Die Gesamtdauer, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Teilnehmer hat 5 Minuten in einer A/V-Konferenz verbracht und ein zweiter Benutzer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.  <br/> |
|**PSTN-Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die sich in Konferenzen einwählten, die Zugriff per Einwahl erlaubten.  <br/> |
|**PSTN-Teilnehmerminuten insgesamt** <br/> |Nein  <br/> |Die Gesamtdauer, die Einwahlbenutzer in Konferenzen verbrachten. Beispiel: Angenommen, ein Einwahlteilnehmer hat 5 Minuten in einer Konferenz verbracht und ein zweiter Teilnehmer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.  <br/> |
|**Eindeutige Konferenzorganisatoren** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Konferenz mit Einwahlzugriff organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.  <br/> |
   

