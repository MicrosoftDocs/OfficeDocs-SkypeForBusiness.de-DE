---
title: Zusammenfassender Bericht über Peer-to-Peer-Aktivitäten in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Zusammenfassung: Erfahren Sie mehr über den zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten in Skype for Business Server.'
ms.openlocfilehash: cd228175d0b254e70d4df0019566ee7e8784b2de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622257"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Zusammenfassender Bericht über Peer-to-Peer-Aktivitäten in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten in Skype for Business Server.
  
Der zusammenfassende Bericht über Peer-to-Peer-Aktivitäten bietet eine Übersicht über Ihre Peer-to-Peer-Kommunikationssitzungen. Eine Peer-to-Peer-Sitzung umfasst in der Regel nur zwei Benutzer und erfordert nicht die Verwendung der Skype for Business Server Konferenzdienste. Im Vergleich dazu umfasst eine Konferenz in der Regel mehr als zwei Benutzer und erfordert die Verwendung von Skype for Business Server Konferenzdiensten. Die Konferenzaktivität wird im zusammenfassenden Konferenzbericht gemeldet.
  
Der zusammenfassende Bericht über Peer-to-Peer-Aktivitäten hilft Ihnen bei der Beantwortung von Fragen wie den folgenden:
  
- Wie viele Peer-to-Peer-Chatnachrichten senden meine Benutzer an einem typischen Tag?
    
- Nutzt einer meiner Benutzer tatsächlich die Funktionen Skype for Business Server Anwendungsfreigabe und Dateiübertragung?
    
- Benutzer haben sich darüber beschwert, dass das Netzwerk zu bestimmten Tageszeiten langsam erscheint. Wie viele Minuten werden in diesen Zeiträumen für Peer-to-Peer-Audio- und -Videositzungen aufgewendet?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Zugreifen auf den Zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten

Sie greifen auf den Zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten über die Startseite für Überwachungsberichte zu. Sie öffnen den Bericht über [Peer-to-Peer-Chatnachrichten in Skype for Business Server,](im-report.md) indem Sie auf eine der folgenden Metriken klicken:
  
- Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen
    
- Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten
    
Ebenso können Sie den Bericht über Peer-to-Peer-Sprach- und -Videofunktionen öffnen, indem Sie auf eine der folgenden Metriken klicken:
  
- Peer-zu-Peer-Audiositzungen insgesamt
    
- Peer-to-Peer-Audiositzungsminuten insgesamt
    
- Peer-zu-Peer-Audiositzungen insgesamt
    
- Peer-to-Peer-Audiositzungsminuten insgesamt
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Optimale Nutzung des Zusammenfassenden Berichts über Peer-to-Peer-Aktivitäten

Am Ende des zusammenfassenden Berichts über Peer-to-Peer-Aktivitäten finden Sie Summen für Metriken wie die Gesamtzahl der Peer-to-Peer-Chatsitzungen und die Gesamtzahl der Peer-to-Peer-Chatnachrichten. Dies bietet eine kurze Zusammenfassung der detaillierten Informationen im Text des Berichts.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten auswählen, wie Daten gruppiert werden sollen. In diesem Fall aktivität gruppiert nach Stunde, Tag, Woche oder Monat.
  
In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten verwenden können.
  
**Filter im Zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 17.07.12015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/17/12015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/13/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Ziel** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 17.07.12015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/17/12015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/13/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate werden angezeigt) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall "Täglich" mit dem Startdatum 17.07.12015 und dem Enddatum 28.02.2015 auswählen, werden die Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.12015 12:00 Uhr angezeigt (d. a. Daten insgesamt 31 Tage). <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten bereitgestellt werden.
  
**Metriken des zusammenfassenden Berichts über Peer-to-Peer-Aktivitäten**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 17.07.12015 klicken, wird eine stündliche Aufschlüsselung der Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Peer-to-Peer-Sitzungen insgesamt** <br/> |Nein  <br/> |Gesamtanzahl der durchgeführten Peer-to-Peer-Sitzungen, unabhängig vom Sitzungstyp.  <br/> |
|**Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen** <br/> |Nein  <br/> |Gesamtzahl der Peer-to-Peer-Chatsitzungen. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-to-Peer-Chatnachrichten für den ausgewählten Zeitraum an.  <br/> |
|**Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten** <br/> |Nein  <br/> |Gesamtanzahl der in Peer-to-Peer-Sitzungen gesendeten Chatnachrichten. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-to-Peer-Chatnachrichten für den ausgewählten Zeitraum an.  <br/> |
|**<c0>Peer-zu-Peer-Audiositzungen insgesamt</c0>** <br/> |Nein  <br/> |Gesamtanzahl der Peer-to-Peer-Audioanrufe. Wenn Sie auf dieses Feld klicken, zeigt der Bericht den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den ausgewählten Zeitraum an.  <br/> |
|**Peer-to-Peer-Audiositzungsminuten insgesamt** <br/> |Nein  <br/> |Gesamtdauer für Peer-to-Peer-Audiositzungen. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den ausgewählten Zeitraum an.  <br/> |
|**Durchschnittliche Peer-to-Peer-Audiositzung in Minuten** <br/> |Nein  <br/> |Durchschnittlicher Zeitaufwand für Peer-to-Peer-Audiositzungen. Berechnet durch Dividieren der Gesamtdauer der Audiositzung durch die Gesamtzahl der Audiositzungen.  <br/> |
|**<c0>Peer-zu-Peer-Videositzungen insgesamt</c0>** <br/> |Nein  <br/> |Gesamtzahl der Peer-to-Peer-Videoanrufe. Beachten Sie, dass Videositzungen auch als Audiositzungen gezählt werden: Jede Videositzung wird als eine Videositzung und eine Audiositzung gezählt. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den ausgewählten Zeitraum an.  <br/> |
|**Peer-to-Peer-Videositzungsminuten insgesamt** <br/> |Nein  <br/> |Gesamtdauer der Peer-to-Peer-Videositzungen. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den ausgewählten Zeitraum an.  <br/> |
|**Durchschnittliche Peer-to-Peer-Videositzung in Minuten** <br/> |Nein  <br/> |Durchschnittlicher Zeitaufwand für Peer-to-Peer-Videositzungen. Berechnet durch Dividieren der Gesamtdauer der Videositzung durch die Gesamtzahl der Videositzungen.  <br/> |
|**Peer-to-Peer-Dateiübertragungssitzungen insgesamt** <br/> |Nein  <br/> |Gesamtzahl der Peer-to-Peer-Sitzungen, die Dateiübertragungen umfassten.  <br/> |
|**Peer-to-Peer-Anwendungsfreigabesitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtanzahl der Peer-to-Peer-Sitzungen, die die Anwendungsfreigabe umfassten.  <br/> |
   

