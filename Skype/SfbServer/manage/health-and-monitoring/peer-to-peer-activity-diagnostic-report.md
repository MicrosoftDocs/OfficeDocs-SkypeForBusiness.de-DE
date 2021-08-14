---
title: Diagnosebericht über Peer-to-Peer-Aktivitäten in Skype for Business Server
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
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Zusammenfassung: Erfahren Sie mehr über den Diagnosebericht über Peer-to-Peer-Aktivitäten in Skype for Business Server.'
ms.openlocfilehash: d303bd820a7494be2061eb4e36c5413787b83ffcd4fc794f8e98ac3a8d806261
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325102"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Diagnosebericht über Peer-to-Peer-Aktivitäten in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Diagnosebericht über Peer-to-Peer-Aktivitäten in Skype for Business Server.
  
Der Diagnosebericht über Peer-zu-Peer-Aktivitäten enthält Informationen dazu, ob die Peer-zu-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind. Beachten Sie, dass Skype for Business Server zwischen verschiedenen Arten von Fehlern unterscheidet:
  
- **Fehler erwartet.** Ein erwarteter Fehler ist in der Regel nur im technischsten Sinne ein Fehler. Angenommen, Sie rufen jemanden an, aber er ist nicht im Büro und kann das Telefon nicht beantworten. Da der Anruf nicht angenommen wurde, wird der Anruf technisch als Fehler betrachtet. Andererseits war dies ein erwarteter Fehler: Skype for Business Server erwartet nicht, dass Sie das Telefon beantworten, wenn Sie das Telefon nicht beantworten können. Ebenso tritt ein erwarteter Fehler auf, wenn Sie versuchen, eine Chatnachricht an einen Benutzer zu senden, der offline ist oder nur an einem Telefon angemeldet ist, das Chatnachrichten nicht unterstützt.
    
- **Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der gemessen an den Umständen nicht zu erwarten ist. Angenommen, Sie rufen eine Person an, und die Person kann den Anruf annehmen. Angenommen, Sie rufen jemanden an, und diese Person steht zur Annahme des Anrufs zur Verfügung. Wenn Skype for Business Server jedoch versucht, Ihren Anruf an Voicemail weiterzuleiten, schlägt der Anruf fehl, da die Verbindung zu Exchange Unified Messaging verloren gegangen ist. Dies ist ein unerwarteter Fehler: Sie würden erwarten, dass Anrufe immer an Voicemail weitergeleitet werden können. Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Benutzer oder ähnliche Maßnahmen nicht behoben werden können.
    
Beachten Sie, dass die Metriken für "Erfolg", "Erwarteter Fehler" und "Unerwarteter Fehler" nicht zwangsläufig identisch mit der Metrik unter "Sitzungen insgesamt" sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:
  
|**Erfolge**|**Erwartete Fehler**|**Unerwartete Fehler**|**Sitzungen insgesamt**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16   <br/> |2521  <br/> |
   
Wenn Sie 2024 + 469 + 16 hinzufügen, erhalten Sie insgesamt 2.509 Sitzungen, die Spalte "Sitzungen insgesamt" zeigt jedoch insgesamt 2.521 Sitzungen an. Die "fehlenden" 12 Sitzungen sind Sitzungen, die das System nicht als erfolgreich oder nicht erfolgreich kategorisieren konnte. Dies ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der Skype for Business Server nicht vertraut ist. Wenn dies geschieht, können Aufrufe, die mit diesem Produkt getätigt werden und diesen Diagnosecode melden, nicht immer als "Erfolgreich", "Erwarteter Fehler" oder "Unerwarteter Fehler" kategorisiert werden.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Zugreifen auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten

Auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten greifen Sie über die Homepage für Überwachungsberichte zu. Sie können auf den [Bericht über Fehlerverteilung in Skype for Business Server](failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:
  
- Anzahl der unerwarteten Fehler
    
- Anzahl der erwarteten Fehler
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Optimales Verwenden des Diagnoseberichts über Peer-zu-Peer-Aktivitäten

Es gibt mehrere Möglichkeiten, wie Sie den Diagnosebericht über Peer-zu-Peer-Aktivitäten filtern können, aber die Filteroptionen sind standardmäßig ausgeblendet. Um die verfügbaren Filteroptionen anzuzeigen, klicken Sie im Berichtfenster oben rechts auf die Schaltfläche zum Ein- und Ausblenden der Parameter. Danach können Sie die Filteroptionen verwenden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise ansehen. Beispielsweise können Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten nach Kriterien wie etwa Sitzungsmodalität (z. B. Sofortnachrichten, Dateiübertragung oder Anwendungsfreigabe) filtern. Sie können auch auswählen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten verwenden können.
  
**Filter im Diagnosebericht über Peer-zu-Peer-Aktivitäten**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Ziel** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate werden angezeigt) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie z. B. das Intervall "Täglich" mit dem Startdatum 7.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. s. Daten insgesamt 31 Tage). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.<br/> |
|**Modalität** <br/> | Gibt den Typ der Kommunikationsaktivität an, die stattgefunden hat. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Sofortnachrichten <br/>  Dateiübertragung <br/>  Anwendungsfreigabe <br/>  Audio <br/>  Video <br/> |
   
## <a name="metrics-per-modality"></a>Metrik (pro Modalität)

In der folgenden Tabelle werden die Metriken aufgelistet, die im Diagnosebericht über Peer-zu-Peer-Aktivitäten für jede Modalität angegeben werden.
  
**Metrik (pro Modalität)**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anzahl der erfolgreichen Sitzungen** <br/> |Nein  <br/> |Die Gesamtzahl der erfolgreichen Peer-zu-Peer-Sitzungen.  <br/> |
|**Prozentsatz der erfolgreichen Sitzungen** <br/> |Nein  <br/> |Der Prozentsatz der Peer-zu-Peer-Sitzungen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.  <br/> |
|**Anzahl der erwarteten Fehler** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, in denen ein "erwarteter Fehler" aufgetreten ist.  <br/> Ein erwarteter Fehler ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf Nicht stören festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.  <br/> |
|**Prozentsatz der erwarteten Fehler** <br/> |Nein  <br/> |Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.  <br/> |
|**Anzahl der unerwarteten Fehler** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, in denen ein "unerwarteter Fehler" aufgetreten ist.  <br/> Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.  <br/> |
|**Prozentsatz der unerwarteten Fehler** <br/> |Nein  <br/> |Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.  <br/> |
|**Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.  <br/> |
   

