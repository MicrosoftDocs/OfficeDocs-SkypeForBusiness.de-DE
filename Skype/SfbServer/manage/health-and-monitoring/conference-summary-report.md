---
title: Zusammenfassungsbericht Konferenz in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Zusammenfassung: Erfahren Sie mehr über die Konferenz Zusammenfassungsbericht in Skype für Business Server.'
ms.openlocfilehash: a6b494395a1d4074907947ef626f9d36b4e239db
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897001"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Zusammenfassungsbericht Konferenz in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den zusammenfassenden Konferenzbericht in Skype für Business Server.
  
Der „Zusammenfassende Konferenzbericht“ gibt Ihnen einen Überblick über Ihre Onlinekonferenzsitzungen. Eine Konferenz umfasst mehr als 2 Benutzer in der Regel und erfordert die Verwendung von Live Meeting-Dienste. Demgegenüber erstellt eine Peer-zu-Peer-Sitzung in der Regel nur 2 Benutzer umfasst und erfordert die Verwendung von Skype für Konferenzdienste Business Server nicht. Peer-zu-Peer-Aktivitäten sind für die [Peer-zu-Peer-Aktivität Zusammenfassung Bericht in Skype für Business Server](peer-to-peer-activity-summary-report.md)gemeldet.
  
Im Conference Summary Report nicht nur erfahren Sie, wie vielen Konferenzen während eines bestimmten Zeitraums (stündlich, täglich, wöchentlich, monatlich) abgehaltenen sondern weist Sie auch die Gesamtzahl der Personen, die Teil in diese Konferenzen haben und die Gesamtzahl der eindeutige Konferenz Organisatoren.
  
Der Organisator einer "unique" ist jeder Benutzer, die mindestens eine Konferenz ansetzt. Wenn zum Beispiel Pilar Ackerman eine Konferenz plant, zählt sie als ein eindeutiger Organisator. Wenn Ken Myer 148 Konferenzen plant, zählt auch er als ein eindeutiger Organisator. So sind in der folgenden Tabelle acht geplante Konferenzen aufgeführt, jedoch nur drei eindeutige Organisatoren (Ken Myer, Pilar Ackerman und David Ahs).
  
|**Konferenzorganisator**|**Konferenzdatum**|
|:-----|:-----|
|Ken Myer  <br/> |07.07.2015 10:00  <br/> |
|David Ahs  <br/> |07.07.2015 10:00  <br/> |
|Ken Myer  <br/> |07.07.2015 11:00  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 11:00  <br/> |
|Ken Myer  <br/> |07.07.2015 13:00  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 14:00  <br/> |
|Ken Myer  <br/> |02.07.2015 10:00  <br/> |
|Pilar Ackerman  <br/> |02.07.2015 10:00  <br/> |
   
Der „Zusammenfassende Konferenzbericht“ zeigt auch an, bei wie vielen Konferenzen Audio- und/oder Videofunktionen genutzt wurden.
  
## <a name="accessing-the-conference-summary-report"></a>Zugriff auf den „Zusammenfassenden Konferenzbericht“

Auf den zusammenfassenden Konferenzbericht können Sie über die Startseite für Überwachungsberichte zugreifen. Sie können einen Drilldown weiter zum Konferenzaktivitätsbericht ausführen, indem Sie auf eine der folgenden Metriken klicken:
  
- Konferenzen insgesamt
    
- Teilnehmer insgesamt
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Optimale Nutzung des „Zusammenfassenden Konferenzberichts“

Gesamtwerte für den Großteil der Auswertungskriterien auf im Conference Summary Report können am unteren Rand des Berichts gefunden werden. Führen Sie einen Bildlauf nach unten zu finden Sie unter Werte wie die Gesamtzahl der Konferenzen, die während des angegebenen Zeitraums gehalten und die Gesamtzahl der Personen, die an diese Konferenzen teilgenommen haben. Eine Metrik, die nicht am unteren Rand des Berichts summiert wird ist eindeutige konferenzorganisatoren insgesamt. Warum funktioniert sie nicht? Hier ist ein Grund. Angenommen Sie, einem Monat im Wert von Daten angezeigt werden. Am Tag 1 mussten Sie 34 eindeutige konferenzorganisatoren; am Tag 2 mussten Sie 27 eindeutige konferenzorganisatoren. Bedeutet das, dass Sie für diese zwei Tage 61 eindeutige konferenzorganisatoren kommuniziert? Nicht unbedingt. Nachdem alle möglicherweise alle 27 Personen, die Konferenzen am Tag 2 organisiert unter anderem 34, die Konferenzen am Tag 1 organisiert hat. Beispielsweise in diesem einfachen Bericht, beachten Sie, dass Ken Myer "und" Pilar Ackerman Konferenzen beide auf 7/7/2015 geplant und auf 7/2/2015:
  
|**Konferenzorganisator**|**Konferenzdatum**|
|:-----|:-----|
|Ken Myer  <br/> |07.07.2015 10:00  <br/> |
|David Ahs  <br/> |07.07.2015 10:00  <br/> |
|Ken Myer  <br/> |07.07.2015 11:00  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 11:00  <br/> |
|Ken Myer  <br/> |07.07.2015 13:00  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 14:00  <br/> |
|Ken Myer  <br/> |02.07.2015 10:00  <br/> |
|Pilar Ackerman  <br/> |02.07.2015 10:00  <br/> |
   
Wenn Sie genauer wissen möchten, wie viele eindeutige Konferenzorganisatoren es insgesamt gab, ändern Sie einfach den Zeitraum. Schauen Sie zum Beispiel die Daten nach Monaten anstatt nach Tagen aufgeschlüsselt durch.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Konferenzbericht festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Konferenzbericht verwenden können.
  
**Filter im Zusammenfassenden Konferenzbericht**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Konferenzbericht angegeben werden.
  
**Metriken im Zusammenfassenden Konferenzbericht**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an. Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 07.07.2015 klicken, wird eine stündliche Übersicht der Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen (unabhängig vom Konferenztyp), die stattfanden. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.  <br/> |
|**Teilnehmer insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Personen, die an den Konferenzen teilnahmen. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.  <br/> |
|**Durchschnittliche Teilnehmeranzahl pro Konferenz** <br/> |Nein  <br/> |Die durchschnittliche Anzahl der Personen, die an einer Konferenz teilnahmen. Errechnet sich durch Dividieren der Gesamtzahl der Konferenzen durch die Gesamtzahl der Teilnehmer.  <br/> |
|**A/V-Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen mit Audio oder Video.  <br/> |
|**Gesamtdauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die Gesamtzahl der Minuten, die für Konferenzen mit Audio bzw. aufgewendet wurden.  <br/> Der gesamte A / V-Konferenz Minuten Metrik werden alle audiovisuelle Konferenz Typen, einschließlich zusammengefasst: A / V-Konferenzen Sofortnachrichtenkonferenzen; Anwendungsfreigabe Konferenzen; Datenkonferenzen; und PSTN-Konferenzen.  <br/> |
|**Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben** <br/> |Nein  <br/> |Die Gesamtzahl der Minuten, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Benutzer verbringt 5 Minuten in einer A/V-Konferenz und ein zweiter Benutzer verbringt 3 Minuten in der gleichen Konferenz. Dies ergibt eine Gesamtdauer von 5 + 3 = 8 Minuten.  <br/> |
|**Durchschnittliche Dauer der A/V-Konferenzen in Minuten** <br/> |Nein  <br/> |Die durchschnittliche Anzahl der Minuten pro A/V-Konferenz.  <br/> |
|**Eindeutige Konferenzorganisatoren insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Konferenz organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.  <br/> |
|**Konferenznachrichten insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sofortnachrichten, die während Konferenzen gesendet wurden.  <br/> |
   

