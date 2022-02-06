---
title: Zusammenfassender Konferenzbericht in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Zusammenfassung: Erfahren Sie mehr über den zusammenfassenden Konferenzbericht in Skype for Business Server.'
---

# <a name="conference-summary-report-in-skype-for-business-server"></a>Zusammenfassender Konferenzbericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den zusammenfassenden Konferenzbericht in Skype for Business Server.
  
Der "Zusammenfassende Konferenzbericht" gibt Ihnen einen Überblick über Ihre Onlinekonferenzsitzungen. Eine Konferenz umfasst in der Regel mehr als zwei Benutzer und erfordert die Verwendung von Konferenzdiensten. Im Vergleich dazu umfasst eine Peer-to-Peer-Sitzung in der Regel nur zwei Benutzer und erfordert nicht die Verwendung von Skype for Business Server Konferenzdiensten. Peer-to-Peer-Aktivitäten werden [im zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten in Skype for Business Server](peer-to-peer-activity-summary-report.md) gemeldet.
  
Der zusammenfassende Konferenzbericht gibt nicht nur an, wie viele Konferenzen während eines bestimmten Zeitraums (stündlich, täglich, wöchentlich, monatlich) abgehalten wurden, sondern auch die Gesamtzahl der Personen, die an diesen Konferenzen teilgenommen haben, und die Gesamtzahl der eindeutigen Konferenzorganisatoren.
  
Ein "eindeutiger" Organisator ist jeder, der mindestens eine Konferenz plant. Wenn zum Beispiel Pilar Ackerman eine Konferenz plant, zählt sie als ein eindeutiger Organisator. Wenn Ken Myer 148 Konferenzen plant, zählt auch er als ein eindeutiger Organisator. Die folgende Tabelle zeigt beispielsweise acht geplante Konferenzen, aber nur drei eindeutige Organisatoren (Ken Myer, Pilar Ackerman und David Ahs).
  
|**Konferenzorganisator**|**Konferenzdatum**|
|:-----|:-----|
|Ken Myer  <br/> |7.07.2015 10:00 Uhr  <br/> |
|David Ahs  <br/> |7.07.2015 10:00 Uhr  <br/> |
|Ken Myer  <br/> |7.07.2015 11:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |7.07.2015 11:00 Uhr  <br/> |
|Ken Myer  <br/> |7.07.2015 13:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |7.07.2015 14:00 Uhr  <br/> |
|Ken Myer  <br/> |02.07.2015 10:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |02.07.2015 10:00 Uhr  <br/> |
   
Der "Zusammenfassende Konferenzbericht" zeigt auch an, bei wie vielen Konferenzen Audio- und/oder Videofunktionen genutzt wurden.
  
## <a name="accessing-the-conference-summary-report"></a>Zugriff auf den "Zusammenfassenden Konferenzbericht"

Auf den "Zusammenfassenden Konferenzbericht" können Sie über die Startseite "Monitoring-Berichte" zugreifen. Sie können weiter zum Konferenzaktivitätsbericht aufschlüsseln, indem Sie auf eine der folgenden Metriken klicken:
  
- Konferenzen insgesamt
    
- Teilnehmer insgesamt
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Optimale Nutzung des "Zusammenfassenden Konferenzberichts"

Gesamtwerte für die meisten Metriken, die im zusammenfassenden Konferenzbericht verwendet werden, finden Sie unten im Bericht. Scrollen Sie nach unten, um Werte wie die Gesamtzahl der Konferenzen, die während des angegebenen Zeitraums abgehalten wurden, und die Gesamtzahl der Personen anzuzeigen, die an diesen Konferenzen teilgenommen haben. Eine Metrik, die am ende des Berichts nicht summiert wird, ist die Gesamtzahl eindeutiger Konferenzorganisatoren. Warum nicht? Dies ist ein Grund. Angenommen, Sie sehen sich die Daten eines Monats an. An Tag 1 hatten Sie 34 eindeutige Konferenzorganisatoren; an Tag 2 hatten Sie 27 eindeutige Konferenzorganisatoren. Bedeutet dies, dass Sie 61 eindeutige Konferenzorganisatoren für diese beiden Tage hatten? Nicht unbedingt. Schließlich gehören alle 27 Personen, die Konferenzen am 2. Tag organisiert haben, möglicherweise zu den 34 Personen, die Konferenzen an Tag 1 organisiert haben. Beachten Sie in diesem einfachen Bericht beispielsweise, dass Ken Myer und Pilar Ackerman Konferenzen sowohl am 7.07.2015 als auch am 2.07.2015 geplant haben:
  
|**Konferenzorganisator**|**Konferenzdatum**|
|:-----|:-----|
|Ken Myer  <br/> |7.07.2015 10:00 Uhr  <br/> |
|David Ahs  <br/> |7.07.2015 10:00 Uhr  <br/> |
|Ken Myer  <br/> |7.07.2015 11:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |7.07.2015 11:00 Uhr  <br/> |
|Ken Myer  <br/> |7.07.2015 13:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |7.07.2015 14:00 Uhr  <br/> |
|Ken Myer  <br/> |02.07.2015 10:00 Uhr  <br/> |
|Pilar Ackerman  <br/> |02.07.2015 10:00 Uhr  <br/> |
   
Wenn Sie genauer wissen möchten, wie viele eindeutige Konferenzorganisatoren es insgesamt gab, ändern Sie einfach den Zeitraum. Schauen Sie zum Beispiel die Daten nach Monaten anstatt nach Tagen aufgeschlüsselt durch.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Konferenzbericht festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Konferenzbericht verwenden können.
  
**Filter im Zusammenfassenden Konferenzbericht**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie z. B. das Intervall "Täglich" mit dem Startdatum 7.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. s. Daten insgesamt 31 Tage). <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Konferenzbericht angegeben werden.
  
**Metriken im Zusammenfassenden Konferenzbericht**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 7.07.2015 klicken, wird eine stündliche Aufschlüsselung der Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen (unabhängig vom Konferenztyp), die stattfanden. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.  <br/> |
|**Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Personen, die an den Konferenzen teilnahmen. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.  <br/> |
|**Durchschnittliche Anzahl der Teilnehmer pro Konferenz** <br/> |Nein  <br/> |Die durchschnittliche Anzahl der Personen, die an einer Konferenz teilnahmen. Errechnet sich durch Dividieren der Gesamtzahl der Konferenzen durch die Gesamtzahl der Teilnehmer.  <br/> |
|**A/V-Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen mit Audio oder Video.  <br/> |
|**Gesamtdauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die Gesamtzahl der Minuten, die für Konferenzen mit Audio bzw. aufgewendet wurden.  <br/> Die Metrik "A/V-Konferenzminuten insgesamt" fasst alle Audio-/Visuellen Konferenztypen zusammen, einschließlich: A/V-Konferenzen; Chatkonferenzen; App-Freigabekonferenzen; Datenkonferenzen; und PSTN-Konferenzen.  <br/> |
|**Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben** <br/> |Nein  <br/> |Die Gesamtzahl der Minuten, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Benutzer verbringt 5 Minuten in einer A/V-Konferenz, und ein zweiter Benutzer verbringt 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 5 + 3 = 8 Minuten.  <br/> |
|**Durchschnittliche Dauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die durchschnittliche Anzahl der Minuten pro A/V-Konferenz.  <br/> |
|**Eindeutige Konferenzorganisatoren insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Konferenz organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.  <br/> |
|**Konferenznachrichten insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sofortnachrichten, die während Konferenzen gesendet wurden.  <br/> |
   

