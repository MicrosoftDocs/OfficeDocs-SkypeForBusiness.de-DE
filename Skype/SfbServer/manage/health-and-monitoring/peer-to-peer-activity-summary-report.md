---
title: Zusammenfassender Bericht über Peer-zu-Peer-Aktivitäten in Skype for Business Server
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
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Zusammenfassung: Erfahren Sie mehr über den zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten in Skype for Business Server.'
ms.openlocfilehash: b1dddaefc7e824bc7b4387d13c92143e253d69f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816795"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Zusammenfassender Bericht über Peer-zu-Peer-Aktivitäten in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten in Skype for Business Server.
  
Der zusammenfassende Bericht über Peer-zu-Peer-Aktivitäten bietet eine Übersicht über Ihre Peer-zu-Peer-Kommunikationssitzungen. Eine Peer-zu-Peer-Sitzung umfasst in der Regel nur zwei Benutzer und erfordert nicht die Verwendung der Skype for Business Server-Konferenzdienste. Im Vergleich dazu umfasst eine Konferenz in der Regel mehr als zwei Benutzer und erfordert die Verwendung von Skype for Business Server-Konferenzdiensten. Konferenzaktivität wird im zusammenfassenden Konferenzbericht gemeldet.
  
Der zusammenfassende Bericht über Peer-to-Peer-Aktivitäten hilft Ihnen bei der Beantwortung von Fragen wie den folgenden:
  
- Wie viele Peer-zu-Peer-Chatnachrichten senden meine Benutzer an einem typischen Tag?
    
- Nutzen meine Benutzer tatsächlich die Skype for Business Server-Anwendungsfreigabe- und Dateiübertragungsfunktionen?
    
- Benutzer haben sich beschwert, dass das Netzwerk zu bestimmten Tageszeiten langsam zu sein scheint. Wie viele Minuten werden in diesen Zeiträumen für Peer-zu-Peer-Audio- und -Videositzungen verwendet?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Zugreifen auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten

Sie greifen über die Startseite für Überwachungsberichte auf den Zusammenfassenden Bericht über Peer-zu-Peer-Aktivitäten zu. Sie öffnen den Bericht über [Peer-zu-Peer-Chat in Skype for Business Server,](im-report.md) indem Sie auf eine der folgenden Metriken klicken:
  
- Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen
    
- Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten
    
Ebenso können Sie den Bericht über Peer-to-Peer-Sprach- und -Videodaten öffnen, indem Sie auf eine der folgenden Metriken klicken:
  
- Peer-zu-Peer-Audiositzungen insgesamt
    
- Peer-zu-Peer-Audiositzungsminuten insgesamt
    
- Peer-zu-Peer-Audiositzungen insgesamt
    
- Peer-zu-Peer-Audiositzungsminuten insgesamt
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Optimale Nutzung des zusammenfassenden Berichts über Peer-to-Peer-Aktivitäten

Unten im Zusammenfassenden Bericht über Peer-zu-Peer-Aktivitäten finden Sie Gesamtwerte für Metriken wie Peer-zu-Peer-Sitzungen insgesamt und Peer-zu-Peer-Nachrichten insgesamt. Dies bietet eine kurze Zusammenfassung der detaillierten Informationen im Textkörper des Berichts.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten auswählen, wie Daten zusammengefasst werden sollen. In diesem Fall die Aktivität nach Stunde, Tag, Woche oder Monat.
  
In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten verwenden können.
  
**Filter im Zusammenfassenden Bericht über Peer-zu-Peer-Aktivitäten**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/17/12015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/13/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/17/12015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/13/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate werden angezeigt) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Tägliche Intervall mit dem Startdatum 17.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 00:00 Uhr bis 07.09.2015 00:00 Uhr angezeigt (d. h. Daten von insgesamt 31 Tagen). <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten bereitgestellt werden.
  
**Metriken im Zusammenfassenden Bericht über Peer-zu-Peer-Aktivitäten**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall "Täglich" verwenden und auf den 17.07.12015 klicken, wird eine stündlich aufschlüsselte Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Peer-zu-Peer-Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die unabhängig vom Sitzungstyp durchgeführt wurden.  <br/> |
|**Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen** <br/> |Nein  <br/> |Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-Nachrichten für den ausgewählten Zeitraum an.  <br/> |
|**Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten** <br/> |Nein  <br/> |Gesamtanzahl der Chatnachrichten, die in Peer-zu-Peer-Sitzungen gesendet wurden. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-Nachrichten für den ausgewählten Zeitraum an.  <br/> |
|**<c0>Peer-zu-Peer-Audiositzungen insgesamt</c0>** <br/> |Nein  <br/> |Gesamtanzahl der Peer-zu-Peer-Audioanrufe. Wenn Sie auf dieses Feld klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videonachrichten für den ausgewählten Zeitraum angezeigt.  <br/> |
|**Peer-zu-Peer-Audiositzungsminuten insgesamt** <br/> |Nein  <br/> |Gesamtzeit in Peer-zu-Peer-Audiositzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videonachrichten für den ausgewählten Zeitraum angezeigt.  <br/> |
|**Durchschnittliche Peer-zu-Peer-Audiositzung in Minuten** <br/> |Nein  <br/> |Durchschnittliche Zeit in Peer-zu-Peer-Audiositzungen. Wird berechnet, indem die Gesamtzeit der Audiositzung durch die Gesamtzahl der Audiositzungen dividiert wird.  <br/> |
|**<c0>Peer-zu-Peer-Videositzungen insgesamt</c0>** <br/> |Nein  <br/> |Gesamtanzahl der Peer-zu-Peer-Videoanrufe. Beachten Sie, dass Videositzungen auch als Audiositzungen gezählt werden: Jede Videositzung wird als eine Videositzung und eine Audiositzung gezählt. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videonachrichten für den ausgewählten Zeitraum angezeigt.  <br/> |
|**Peer-zu-Peer-Videositzungsminuten insgesamt** <br/> |Nein  <br/> |Gesamtzeit in Peer-zu-Peer-Videositzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videonachrichten für den ausgewählten Zeitraum angezeigt.  <br/> |
|**Durchschnittliche Peer-zu-Peer-Videositzung in Minuten** <br/> |Nein  <br/> |Durchschnittliche Zeit in Peer-zu-Peer-Videositzungen. Wird berechnet, indem die Gesamtzeit der Videositzungen durch die Gesamtzahl der Videositzungen geteilt wird.  <br/> |
|**Peer-zu-Peer-Dateiübertragungssitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die Dateiübertragungen enthalten.  <br/> |
|**Peer-zu-Peer-Anwendungsfreigabesitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die die Anwendungsfreigabe umfassten.  <br/> |
   

