---
title: Diagnosebericht über Peer-zu-Peer-Aktivität in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Zusammenfassung: Informationen Sie zu den Diagnosebericht über Peer-zu-Peer-Aktivität in Skype für Business Server.'
ms.openlocfilehash: 097b323d2a9484e14dd056196b7344b61b412339
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198113"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Diagnosebericht über Peer-zu-Peer-Aktivität in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Diagnosebericht über Peer-zu-Peer-Aktivität in Skype für Business Server.
  
Der Diagnosebericht über Peer-to-Peer-Aktivitäten enthält Informationen dazu, ob Ihre Peer-to-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind. Beachten Sie, dass Skype für Business Server zwischen verschiedenen Arten des Fehlers unterschieden wird:
  
- **Erwarteter Fehler**. Ein erwarteter Fehler ist in der Regel ein Fehler nur in der am häufigsten technischen Sinn. Angenommen Sie, Sie rufen Sie eine Person, aber er wird Ihrer Abwesenheit vom Büro und Anrufe entgegennehmen kann. Da der Anruf nicht entgegengenommen wurde, wird der Anruf einen Fehler technisch betrachtet. Andererseits, dies wurde ein erwarteter Fehler: Skype für Business Server nicht erwarten Sie Anrufe entgegennehmen, wenn Sie keine Anrufe entgegennehmen verfügbar sind. Entsprechend wird ein erwarteter Fehler auftreten, wenn Sie versuchen, eine Sofortnachricht an einen Benutzer senden, die offline ist, oder nur für ein Telefon, das keine Sofortnachrichten unterstützt angemeldet ist.
    
- **Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der unter den gegebenen Umständen nicht zu erwarten ist. Wie der Name schon sagt, ist ein unerwarteter Fehler ein Fehler, dessen Auftreten Sie unter gegebenen Umständen nicht erwarten würden. Angenommen, Sie rufen ist eine Person und die Person zur Verfügung, um den Anruf anzunehmen. Wenn Skype für Business Server versucht, den Anruf an die Voicemail weitergeleitet, schlägt der Aufruf jedoch, da die Verbindung mit Exchange Unified Messaging verloren gegangen ist. Das ist ein unerwarteter Fehler: Es kann davon ausgegangen werden, dass Anrufe immer an die Voicemail weitergeleitet werden können. Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Nutzer oder ähnliche Maßnahmen wahrscheinlich nicht behoben werden können.
    
Beachten Sie, dass die Metriken für „Erfolg“, „Erwarteter Fehler“ und „Unerwarteter Fehler“ nicht zwangsläufig identisch mit der Metrik unter „Sitzungen insgesamt“ sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:
  
|**Erfolge**|**Erwartete Fehler**|**Unerwartete Fehler**|**Sitzungen insgesamt**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Wenn Sie 2024 + 469 + 16 addieren, ergibt das insgesamt 2.509 Sitzungen, aber in der Spalte „Sitzungen insgesamt“ wird 2.521 angezeigt. Die „fehlenden“ 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder fehlerhaft eingestuft werden konnten. Manchmal wird, die der Fall sein, wenn ein Drittanbieter-Produkt einen neuen diagnostic Code vorgestellt, der nicht zu Skype für Business Server vertraut ist. In einer solchen Situation können Aufrufe, die mit diesem Produkt ausgeführt werden und für die dieser Diagnosecode gemeldet wird, nicht immer eindeutig als Erfolg, erwarteter Fehler oder unerwarteter Fehler kategorisiert werden.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Zugreifen auf den Diagnosebericht über Peer-to-Peer-Aktivitäten

Auf den Diagnosebericht über Peer-to-Peer-Aktivitäten greifen Sie über die Startseite für Überwachungsberichte zu. Sie können den [Bericht über Fehlerverteilung in Skype für Business Server](failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken:
  
- Anzahl der unerwarteten Fehler
    
- Anzahl der erwarteten Fehler
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Optimales Verwenden des Diagnoseberichts über Peer-to-Peer-Aktivitäten

Es gibt mehrere Möglichkeiten, wie Sie den Diagnosebericht über Peer-to-Peer-Aktivitäten filtern können, aber die Filteroptionen sind standardmäßig ausgeblendet. Um die verfügbaren Filteroptionen anzuzeigen, klicken Sie im Berichtfenster oben rechts auf die Schaltfläche zum Ein- und Ausblenden der Parameter. Danach können Sie die Filteroptionen verwenden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise ansehen. Beispielsweise können Sie im Diagnosebericht über Peer-to-Peer-Aktivitäten nach Kriterien wie etwa Sitzungsmodalität (z. B. Sofortnachrichten, Dateiübertragung oder Anwendungsfreigabe) filtern. Sie können auch auswählen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle sind die Filter aufgelistet, die Sie im Diagnosebericht über Peer-to-Peer-Aktivitäten verwenden können.
  
**Filter im Diagnosebericht über Peer-to-Peer-Aktivitäten**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
|**Modalität** <br/> | Gibt den Typ der Kommunikationsaktivität an, die stattgefunden hat. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Sofortnachrichten <br/>  Dateiübertragung <br/>  Anwendungsfreigabe <br/>  Audio <br/>  Video <br/> |
   
## <a name="metrics-per-modality"></a>Metrik (pro Modalität)

In der folgenden Tabelle sind die Metriken aufgelistet, die im Diagnosebericht über Peer-to-Peer-Aktivitäten für jede Modalität angegeben werden.
  
**Metrik (pro Modalität)**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anzahl der erfolgreichen Sitzungen** <br/> |Nein  <br/> |Die Gesamtzahl der erfolgreichen Peer-to-Peer-Sitzungen.  <br/> |
|**Prozentsatz der erfolgreichen Sitzungen** <br/> |Nein  <br/> |Der Prozentsatz der Peer-to-Peer-Sitzungen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.  <br/> |
|**Anzahl der erwarteten Fehler** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, in denen ein „erwarteter Fehler“ aufgetreten ist.  <br/> Ein erwarteter Fehler ist ein Fehler, der zu erwarten ist. Wenn beispielsweise ein Benutzer seinen Status auf „Nicht stören“ festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.  <br/> |
|**Prozentsatz der erwarteten Fehler** <br/> |Nein  <br/> |Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.  <br/> |
|**Anzahl der unerwarteten Fehler** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, in denen ein „unerwarteter Fehler“ aufgetreten ist.  <br/> Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.  <br/> |
|**Prozentsatz der unerwarteten Fehler** <br/> |Nein  <br/> |Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.  <br/> |
|**Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.  <br/> |
   

