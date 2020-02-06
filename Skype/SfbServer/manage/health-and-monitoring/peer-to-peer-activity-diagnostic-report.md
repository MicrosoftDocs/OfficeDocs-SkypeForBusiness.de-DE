---
title: Diagnosebericht zur Peer-to-Peer-Aktivität in Skype for Business Server
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
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Zusammenfassung: erfahren Sie mehr über den Diagnosebericht zur Peer-to-Peer-Aktivität in Skype for Business Server.'
ms.openlocfilehash: 7491fc6752bbf7c08c7433f83ea58fcd1a2ba86c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817814"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Diagnosebericht zur Peer-to-Peer-Aktivität in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Diagnosebericht zur Peer-to-Peer-Aktivität in Skype for Business Server.
  
Der Diagnosebericht über Peer-to-Peer-Aktivitäten enthält Informationen dazu, ob Ihre Peer-to-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind. Beachten Sie, dass Skype for Business Server zwischen verschiedenen Arten von Fehlern unterscheidet:
  
- **Erwarteter Fehler**. Ein erwarteter Fehler ist in der Regel ein Fehler nur im technisch Sinn. Nehmen Sie beispielsweise an, dass Sie jemanden anrufen, aber er oder Sie nicht im Büro ist und das Telefon nicht annehmen kann. Da der Anruf nicht beantwortet wurde, wird der Anruf technisch als fehlerhaft eingestuft. Auf der anderen Seite war dies ein erwarteter Fehler: Skype for Business Server erwartet nicht, dass Sie das Telefon annehmen, wenn Sie nicht zur Beantwortung des Telefons verfügbar sind. Ebenso tritt ein erwarteter Fehler auf, wenn Sie versuchen, eine Sofortnachricht an einen Benutzer zu senden, der offline ist, oder nur an einem Telefon angemeldet ist, das keine Chatnachrichten unterstützt.
    
- **Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der unter den gegebenen Umständen nicht zu erwarten ist. Wie der Name schon sagt, ist ein unerwarteter Fehler ein Fehler, dessen Auftreten Sie unter gegebenen Umständen nicht erwarten würden. Nehmen wir beispielsweise an, dass Sie jemanden anrufen und diese Person zur Beantwortung des Anrufs zur Verfügung steht. Wenn Skype for Business Server jedoch versucht, Ihren Anruf an die Voicemail weiterzuleiten, schlägt der Anruf fehl, da die Konnektivität zu Exchange Unified Messaging verloren gegangen ist. Das ist ein unerwarteter Fehler: Es kann davon ausgegangen werden, dass Anrufe immer an die Voicemail weitergeleitet werden können. Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Nutzer oder ähnliche Maßnahmen wahrscheinlich nicht behoben werden können.
    
Beachten Sie, dass die Metriken für „Erfolg“, „Erwarteter Fehler“ und „Unerwarteter Fehler“ nicht zwangsläufig identisch mit der Metrik unter „Sitzungen insgesamt“ sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:
  
|**Erfolge**|**Erwartete Fehler**|**Unerwartete Fehler**|**Sitzungen insgesamt**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Wenn Sie 2024 + 469 + 16 addieren, ergibt das insgesamt 2.509 Sitzungen, aber in der Spalte „Sitzungen insgesamt“ wird 2.521 angezeigt. Die „fehlenden“ 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder fehlerhaft eingestuft werden konnten. Das ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der Skype for Business Server nicht vertraut ist. In einer solchen Situation können Aufrufe, die mit diesem Produkt ausgeführt werden und für die dieser Diagnosecode gemeldet wird, nicht immer eindeutig als Erfolg, erwarteter Fehler oder unerwarteter Fehler kategorisiert werden.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Zugreifen auf den Diagnosebericht über Peer-to-Peer-Aktivitäten

Auf den Diagnosebericht über Peer-to-Peer-Aktivitäten greifen Sie über die Startseite für Überwachungsberichte zu. Sie können [in Skype for Business Server auf den Bericht zur Fehlerverteilung](failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:
  
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
   

