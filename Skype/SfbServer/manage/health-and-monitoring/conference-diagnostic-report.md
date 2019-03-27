---
title: Diagnosebericht Konferenz in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
description: 'Zusammenfassung: Erfahren Sie mehr über die Konferenz Diagnosebericht in Skype für Business Server verwendet.'
ms.openlocfilehash: eb7fde75050b6d97172986aef6429cdc19216f59
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879357"
---
# <a name="conference-diagnostic-report-in-skype-for-business-server"></a>Diagnosebericht Konferenz in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Diagnosebericht Konferenz in Skype für Business Server verwendet wird.
  
Der Diagnosebericht über die Konferenz enthält Informationen über erfolgreich durchgeführte Konferenzsitzungen und Fehler bei Konferenzsitzungen. Beachten Sie, dass Skype für Business Server zwischen verschiedenen Arten des Fehlers unterschieden wird:
  
- **Erwarteter Fehler**. Ein erwarteter Fehler ist typischerweise ein rein technischer Fehler. Ein Beispiel: Angenommen, eine Person startet eine Konferenz, legt aber auf, bevor andere Personen der Konferenz beigetreten sind. Das ist technisch gesehen ein Fehler: Die Konferenz wurde initiiert, aber nicht abgeschlossen. Allerdings wäre das ein Fehler, den Sie durchaus erwarten würden. Bricht nämlich der Organisator die Konferenz ab, bevor andere Personen teilnehmen können, würden Sie die Konferenz nicht als abgeschlossen betrachten.
    
- **Unerwarteter Fehler**. Wie der Name schon sagt, ist ein unerwarteter Fehler ein Fehler, dessen Auftreten Sie unter gegebenen Umständen nicht erwarten würden. Ein Beispiel: Angenommen, eine Konferenz konnte nicht durchgeführt werden, weil die Besprechungsrichtlinie des Organisators nicht abgerufen werden konnte. Das ist ein unerwarteter Fehler, denn die Besprechungsrichtlinie eines Benutzers sollte grundsätzlich immer abgerufen werden können.
    
Beachten Sie, dass die Summe aus den Werten für Erfolge, erwartete Fehler und unerwartete Fehler nicht immer mit der Angabe für „Sitzungen insgesamt“ übereinstimmt. Beispielsweise können in dem Bericht folgende Werte angegeben werden:
  
|**Erfolge**|**Erwartete Fehler**|**Unerwartete Fehler**|**Sitzungen insgesamt**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Wenn Sie 2.024 + 469 + 16 addieren, ergibt das insgesamt 2.509 Sitzungen, aber in der Spalte „Sitzungen insgesamt“ wird 2.521 angezeigt. Die „fehlenden“ 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder fehlerhaft kategorisiert werden konnten. Manchmal wird, die der Fall sein, wenn ein Drittanbieter-Produkt einen neuen diagnostic Code vorgestellt, der an den Monitoring Server nicht vertraut ist. In einer solchen Situation können Aufrufe, die mit diesem Produkt ausgeführt werden und für die dieser Diagnosecode gemeldet wird, nicht immer eindeutig als Erfolg, erwarteter Fehler oder unerwarteter Fehler kategorisiert werden.
  
## <a name="accessing-the-conference-diagnostic-report"></a>Öffnen des Diagnoseberichts über die Konferenz

Auf den Diagnosebericht über die Konferenz greifen Sie über die Startseite für Überwachungsberichte zu. Sie können den [Bericht über Fehlerverteilung in Skype für Business Server](failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken:
  
- Anzahl der unerwarteten Fehler
    
- Anzahl der erwarteten Fehler
    
## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Optimales Nutzen des Diagnoseberichts über die Konferenz

Der Diagnosebericht über die Konferenz enthält eine Reihe von Diagrammen. Jede der Spalten in einem Diagramm ist ein Hyperlink. Wenn Sie eine Spalte klicken, können Sie den [Bericht über Fehlerverteilung in Skype für Business Server](failure-distribution-report.md) für diesen Zeitraum und dieser Konferenztyp Drilldown.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie die Daten im Diagnosebericht über Konferenzen nach Kriterien wie etwa dem Konferenztyp (z. B. Konferenzzustandsobjekt-Sitzung) oder dem für die Konferenz verwendeten Edgeserver filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Diagnosebericht über die Konferenz verwenden können.
  
**Filter im Diagnosebericht über die Konferenz**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
|**Konferenzsitzungen** <br/> | Gibt den Typ der Konferenzsitzung an. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Konferenzzustandsobjekt-Sitzungen <br/>  Alle MCU-Sitzungen <br/>  Sofortnachrichtenkonferenzen <br/>  Anwendungsfreigabe <br/>  A/V-Konferenzen <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Diagnosebericht über die Konferenz für jeden Konferenzsitzungstyp angegeben werden.
  
**Metriken im Diagnosebericht über die Konferenz**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anzahl der erfolgreichen Sitzungen** <br/> |Nein  <br/> |Die Gesamtzahl der erfolgreich durchgeführten Sitzungen.  <br/> |
|**Prozentsatz der erfolgreichen Sitzungen** <br/> |Nein  <br/> |Der Prozentsatz der Konferenzen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.  <br/> |
|**Anzahl der erwarteten Fehler** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen, in denen ein „erwarteter Fehler“ aufgetreten ist.  <br/> Ein erwarteter Fehler ist ein Fehler, der zu erwarten ist. Wenn beispielsweise ein Benutzer seinen Status auf „Nicht stören“ festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.  <br/> |
|**Prozentsatz der erwarteten Fehler** <br/> |Nein  <br/> |Der Prozentsatz der Konferenzen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.  <br/> |
|**Anzahl der unerwarteten Fehler** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen, in denen ein „unerwarteter Fehler“ aufgetreten ist.  <br/> Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.  <br/> |
|**Prozentsatz der unerwarteten Fehler** <br/> |Nein  <br/> |Der Prozentsatz der Konferenzen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.  <br/> |
|**Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen, einschließlich Konferenzen ohne Fehler, Konferenzen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Konferenzen.  <br/> |
   

