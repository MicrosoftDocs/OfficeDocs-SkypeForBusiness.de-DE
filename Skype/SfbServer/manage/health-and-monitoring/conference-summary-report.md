---
title: Zusammenfassender Konferenzbericht in Skype for Business Server
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
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Zusammenfassung: Erfahren Sie mehr über den Zusammenfassenden Konferenzbericht in Skype for Business Server.'
ms.openlocfilehash: eaaa97c54a9183beda40848795b454e7dec92c6f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817045"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Zusammenfassender Konferenzbericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den zusammenfassenden Konferenzbericht in Skype for Business Server.
  
Der "Zusammenfassende Konferenzbericht" gibt Ihnen einen Überblick über Ihre Onlinekonferenzsitzungen. Eine Konferenz umfasst in der Regel mehr als zwei Benutzer und erfordert die Verwendung von Konferenzdiensten. Im Vergleich dazu umfasst eine Peer-zu-Peer-Sitzung in der Regel nur zwei Benutzer und erfordert nicht die Verwendung von Skype for Business Server-Konferenzdiensten. Peer-zu-Peer-Aktivitäten werden im zusammenfassenden Bericht über [Peer-zu-Peer-Aktivitäten in Skype for Business Server gemeldet.](peer-to-peer-activity-summary-report.md)
  
Der Zusammenfassende Konferenzbericht gibt Nicht nur an, wie viele Konferenzen in einem bestimmten Zeitraum (stündlich, täglich, wöchentlich, monatlich) abgehalten wurden, sondern auch die Gesamtanzahl der Teilnehmer an diesen Konferenzen sowie die Gesamtanzahl eindeutiger Konferenzorganisatoren.
  
Ein "eindeutiger" Organisator ist jeder, der mindestens eine Konferenz plant. Wenn zum Beispiel Pilar Ackerman eine Konferenz plant, zählt sie als ein eindeutiger Organisator. Wenn Ken Myer 148 Konferenzen plant, zählt auch er als ein eindeutiger Organisator. In der folgenden Tabelle sind beispielsweise acht geplante Konferenzen aufgeführt, aber nur drei eindeutige Organisatoren (Ken Myer, Pilar Ackerman und David Ahs).
  
|**Konferenzorganisator**|**Konferenzdatum**|
|:-----|:-----|
|Ken Myer  <br/> |07.07.2015 10:00 Uhr  <br/> |
|David Ahs  <br/> |07.07.2015 10:00 Uhr  <br/> |
|Ken Myer  <br/> |07.07.2015 11:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 11:00 Uhr  <br/> |
|Ken Myer  <br/> |07.07.2015 13:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 14:00 Uhr  <br/> |
|Ken Myer  <br/> |02.07.2015 10:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |02.07.2015 10:00 Uhr  <br/> |
   
Der "Zusammenfassende Konferenzbericht" zeigt auch an, bei wie vielen Konferenzen Audio- und/oder Videofunktionen genutzt wurden.
  
## <a name="accessing-the-conference-summary-report"></a>Zugriff auf den "Zusammenfassenden Konferenzbericht"

Auf den "Zusammenfassenden Konferenzbericht" können Sie über die Startseite "Monitoring-Berichte" zugreifen. Sie können weiter zum Konferenzaktivitätsbericht aufschlüsseln, indem Sie auf eine der folgenden Metriken klicken:
  
- Konferenzen insgesamt
    
- Teilnehmer insgesamt
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Optimale Nutzung des "Zusammenfassenden Konferenzberichts"

Die Gesamtwerte für die meisten Metriken, die im zusammenfassenden Konferenzbericht verwendet werden, finden Sie unten im Bericht. Scrollen Sie nach unten, um Werte wie die Gesamtzahl der Konferenzen, die im angegebenen Zeitraum abgehalten wurden, und die Gesamtzahl der Personen, die an diesen Konferenzen teilgenommen haben, zu sehen. Eine Metrik, die nicht am Ende des Berichts gesamt ist, sind eindeutige Konferenzorganisatoren insgesamt. Warum nicht? Dies ist ein Grund. Angenommen, Sie sehen sich die Daten eines Monats an. An Tag 1 hatten Sie 34 eindeutige Konferenzorganisatoren; An Tag 2 hatten Sie 27 eindeutige Konferenzorganisatoren. Bedeutet dies, dass Sie 61 eindeutige Konferenzorganisatoren für diese zwei Tage hatten? Nicht unbedingt. Schließlich können alle 27 Personen, die Konferenzen am 2. Tag organisiert haben, zu den 34 Personen gehören, die Konferenzen am ersten Tag organisiert haben. Beachten Sie in diesem einfachen Bericht beispielsweise, dass Ken Myer und Pilar Ackerman Konferenzen sowohl am 7.07.2015 als auch am 02.07.2015 geplant haben:
  
|**Konferenzorganisator**|**Konferenzdatum**|
|:-----|:-----|
|Ken Myer  <br/> |07.07.2015 10:00 Uhr  <br/> |
|David Ahs  <br/> |07.07.2015 10:00 Uhr  <br/> |
|Ken Myer  <br/> |07.07.2015 11:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 11:00 Uhr  <br/> |
|Ken Myer  <br/> |07.07.2015 13:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 14:00 Uhr  <br/> |
|Ken Myer  <br/> |02.07.2015 10:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |02.07.2015 10:00 Uhr  <br/> |
   
Wenn Sie genauer wissen möchten, wie viele eindeutige Konferenzorganisatoren es insgesamt gab, ändern Sie einfach den Zeitraum. Schauen Sie zum Beispiel die Daten nach Monaten anstatt nach Tagen aufgeschlüsselt durch.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Konferenzbericht festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Konferenzbericht verwenden können.
  
**Filter im Zusammenfassenden Konferenzbericht**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Intervall "Täglich" mit dem Startdatum 7.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 00:00 Uhr bis 07.09.2015 00:00 Uhr angezeigt (d. h. Daten von insgesamt 31 Tagen). <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Konferenzbericht angegeben werden.
  
**Metriken im Zusammenfassenden Konferenzbericht**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall "Täglich" verwenden und auf den 07.07.2015 klicken, wird eine stündlich aufschlüsselte Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen (unabhängig vom Konferenztyp), die stattfanden. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.  <br/> |
|**Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Personen, die an den Konferenzen teilnahmen. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.  <br/> |
|**Durchschnittliche Anzahl der Teilnehmer pro Konferenz** <br/> |Nein  <br/> |Die durchschnittliche Anzahl der Personen, die an einer Konferenz teilnahmen. Errechnet sich durch Dividieren der Gesamtzahl der Konferenzen durch die Gesamtzahl der Teilnehmer.  <br/> |
|**A/V-Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen mit Audio oder Video.  <br/> |
|**Gesamtdauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die Gesamtzahl der Minuten, die für Konferenzen mit Audio bzw. aufgewendet wurden.  <br/> Die Metrik "Gesamt-A/V-Konferenzminuten" fasst alle Audio-/Videokonferenztypen zusammen, einschließlich: A/V-Konferenzen; #A0 App-Freigabekonferenzen; Datenkonferenzen; und PSTN-Konferenzen.  <br/> |
|**Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben** <br/> |Nein  <br/> |Die Gesamtzahl der Minuten, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Benutzer verbringt 5 Minuten in einer A/V-Konferenz, und ein zweiter Benutzer verbringt 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 5 + 3 = 8 Minuten.  <br/> |
|**Durchschnittliche Dauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die durchschnittliche Anzahl der Minuten pro A/V-Konferenz.  <br/> |
|**Eindeutige Konferenzorganisatoren insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Konferenz organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.  <br/> |
|**Konferenznachrichten insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sofortnachrichten, die während Konferenzen gesendet wurden.  <br/> |
   

