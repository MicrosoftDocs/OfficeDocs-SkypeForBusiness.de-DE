---
title: Zusammenfassender Bericht über PSTN-Konferenzen in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Zusammenfassung: Erfahren Sie mehr über das PSTN-Konferenz Zusammenfassungsbericht in Skype für Business Server 2015.'
ms.openlocfilehash: cda98ec62d8f59992f028cd9189e5f696ffaf2ac
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569292"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server-2015"></a>Zusammenfassender Bericht über PSTN-Konferenzen in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu PSTN-Konferenz Zusammenfassungsbericht in Skype für Business Server 2015.
  
In Skype für Business Server 2015 ist eine PSTN-Konferenz eine Konferenz in der mindestens ein Teilnehmer den Audioteil Einwählen in eine mit einem Telefon PSTN (public switched Telephone Network). (Ein PSTN-Telefon "Festnetz" ist ein Mobiltelefon oder einem anderen Telefon das Verwenden von Voice over IP-keine vornimmt.) Obwohl als PSTN-Konferenzen in die Überwachungsberichte bezeichnet, werden diese Konferenzen möglicherweise mehr häufig als einwahlkonferenzen bezeichnet.
  
Der „Zusammenfassende Bericht über PSTN-Konferenzen“ liefert Informationen zu allen in Ihrer Organisation durchgeführten PSTN-Konferenzen (das sind alle Konferenzen mit mindestens einem Einwahlbenutzer). Der Bericht enthält Informationen zur Gesamtanzahl der PSTN-Konferenzen, der Gesamtanzahl der Teilnehmer an diesen Konferenzen und vielleicht als wichtigste Information, die Gesamtanzahl der Einwahlbenutzer (Metrik der PSTN-Teilnehmer insgesamt).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Zugreifen auf den „Zusammenfassenden Bericht über PSTN-Konferenzen“

Auf der Startseite „Überwachungsberichte“ können Sie auf den „Zusammenfassenden Bericht über PSTN-Konferenzen“ zugreifen. Dieser Bericht ist nicht mit anderen Berichten verknüpft. Beachten Sie, dass Sie keine ausführlichen Anrufinformationen für eine PSTN-Konferenz abrufen können. Als teilweise Erklärung hierfür kann angeführt werden, dass die einzelnen Endpunkte für die Übertragung dieser Informationen verantwortlich sind. PSTN-Telefone können keine ausführlichen Anrufinformationen nachverfolgen oder übertragen.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Optimale Nutzung des „Zusammenfassenden Berichts über PSTN-Konferenzen“

Um den Prozentsatz Ihrer Konferenzen bestimmen, die Einwahlbenutzer enthalten, vergleichen Sie den Wert der Metrik insgesamt PSTN-Konferenzen mit der Konferenzen insgesamt Metrik im [Conference Summary Report in Skype für Business Server 2015](conference-summary-report.md)gefunden.
  
Wenn Sie nicht, wie viele PSTN-Konferenzen angezeigt erwartungsgemäß Sie haben möglicherweise angezeigt wird, behalten Sie im Hinterkopf, von denen die Möglichkeit zum Organisieren von einer Konferenz, die Zugriffsnummer für Einwahl-Benutzern ermöglicht, die einem Benutzer zugewiesen wurde die konferenzrichtlinie abhängig: ob sehr wenige Benutzer dürfen PS halten Sie sind anscheinend noch nicht sehr wenige PSTN-Konferenzen finden Sie unter würde TN-Konferenzen. Sie können schnell überprüfen, welche der konferenzrichtlinien (sofern vorhanden) Benutzer PSTN-Konferenzen planen, indem Sie den folgenden Befehl aus innerhalb der Skype für Business Server-Verwaltungsshell ausführen können:
  
```
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
  
**Filter im zusammenfassenden Bericht von PSTN-Konferenz**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Bericht über PSTN-Konferenz angegeben werden.
  
**Metriken im zusammenfassenden Konferenzbericht von PSTN-Konferenz**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das ausgewählte Zeitintervall an. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall „Täglich“ verwenden und auf 07.07.2015 klicken, sehen Sie die nach Stunden aufgeschlüsselten Benutzerregistrierungsaktivitäten an diesem Tag.  <br/> |
|**PSTN-Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen, die Zugriff per Einwahl erlaubten.  <br/> |
|**Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Personen, die an Konferenzen mit Einwahlzugriff teilnahmen.  <br/> |
|**Gesamtdauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die Gesamtdauer von Konferenzen mit Audio oder Video.  <br/> |
|**Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben** <br/> |Nein  <br/> |Die Gesamtdauer, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Teilnehmer hat 5 Minuten in einer A/V-Konferenz verbracht und ein zweiter Benutzer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.  <br/> |
|**PSTN-Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die sich in Konferenzen einwählten, die Zugriff per Einwahl erlaubten.  <br/> |
|**PSTN-Teilnehmerminuten insgesamt** <br/> |Nein  <br/> |Die Gesamtdauer, die Einwahlbenutzer in Konferenzen verbrachten. Beispiel: Angenommen, ein Einwahlteilnehmer hat 5 Minuten in einer Konferenz verbracht und ein zweiter Teilnehmer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.  <br/> |
|**Eindeutige Konferenzorganisatoren** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Konferenz mit Einwahlzugriff organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.  <br/> |
   

