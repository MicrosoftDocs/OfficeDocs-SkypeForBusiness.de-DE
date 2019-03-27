---
title: Peer-zu-Peer- und-videoaktivität in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Zusammenfassung: Erfahren Sie mehr über die Peer-zu-Peer-- und-videoaktivität in Skype für Business Server.'
ms.openlocfilehash: a4572d23a4c41ce423bdc96634ed8a3b9a9b1042
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897622"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>Peer-zu-Peer- und-videoaktivität in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Peer-zu-Peer-- und-videoaktivität in Skype für Business Server.
  
Der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität bietet eine detaillierte Aufstellung der Sprach- und -Videoanrufe für einen bestimmten Zeitraum (z. B. Anrufe pro Stunde oder Anrufe pro Tag). Darüber hinaus können Sie mit diesem Bericht alle getätigten Sprach- und Videoanrufe oder aber nur die erfolgreichen bzw. fehlgeschlagenen Anrufe anzeigen. In diesem Bericht werden die Anrufinformationen in den folgenden Kategorien angezeigt:
  
- Anrufe pro Pool
    
- Anrufe pro Anruftyp (beispielsweise Skype für Unternehmen Skype für Business Anruf im Vergleich zu einer Skype für Business Anruf an eine Person auf das PSTN-Netzwerk)
    
- Anrufe pro Zugriffstyp (beim internen Netzwerk angemeldete Benutzer bzw. beim externen Netzwerk angemeldete Benutzer)
    
- Anrufe pro Vermittlungsserver
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>So greifen Sie auf den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität zu

Auf den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität können Sie nur zugreifen, indem Sie den zusammenfassenden Bericht über Peer-to-Peer-Aktivität öffnen und dann auf die folgenden Metriken klicken:
  
- Peer-to-Peer-Audiositzungen insgesamt
    
- Gesamtdauer der Peer-to-Peer-Audiositzungen in Minuten
    
- Peer-to-Peer-Videositzungen insgesamt
    
- Gesamtdauer der Peer-to-Peer-Videositzungen in Minuten
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>So nutzen Sie den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität optimal

Es gibt eine Reihe von Möglichkeiten, um den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität zu filtern. Diese Filteroptionen sind jedoch standardmäßig ausgeblendet. Klicken Sie zum Anzeigen der verfügbaren Filteroptionen auf die Schaltfläche **Parameter ein-/ausblenden** in der oberen rechten Ecke des Berichtfensters.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität verwenden können.
  
**Filter im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Medientyp** <br/> | Gibt den Typ der in der Sitzung verwendeten Medien an. Wählen Sie eine der folgenden Optionen aus: <br/>  Both <br/>  Audio <br/>  Video <br/> |
|**Anrufanordnung** <br/> | Gibt an, ob die Sitzung erfolgreich oder fehlerhaft war. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Erfolgreiche Anrufe <br/>  Fehlerhafte Anrufe <br/> |
|**Bericht nach** <br/> | Gibt die Werte an, die in dem Bericht verwendet werden sollen. Wählen Sie eine der folgenden Optionen aus: <br/>  Sitzungsanzahl <br/>  Anrufminuten <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für jeden Pool angegeben werden.
  
**Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Pool**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Pool** <br/> |Nein  <br/> |Name des Registrar-Pools oder Edgeservers für den Anruf verwendet.  <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.  <br/> |
|**Gesamt** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Anruftyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für jeden Anruftyp angegeben werden.
  
**Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Anruftyp**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruftyp** <br/> |Nein  <br/> | Gibt den Typ des Anrufs an, der ausgeführt wurde. Folgende Werte sind möglich: <br/>  UC-zu-UC <br/>  UC-zu-PSTN <br/>  PSTN-zu-UC <br/>  PSTN-zu-PSTN <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.  <br/> |
|**Gesamt** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Zugriffstyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für jeden Netzwerkzugriffstyp angegeben werden.
  
**Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Zugriffstyp**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Aktivitätstyp** <br/> |Nein  <br/> | Gibt an, ob die Clients am internen oder am externen Netzwerk angemeldet wurden, als der Anruf getätigt wurde. Diese Metrik hat normalerweise einen der folgenden Werte: <br/>  Intern <br/>  Extern <br/>  Gemischt <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.  <br/> |
|**Gesamt** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Vermittlungsserver

Die folgende Tabelle enthält die Informationen in der Peer-zu-Peer- und-videoaktivität für jeden Vermittlungsserver bereitgestellt.
  
**Metriken für den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität nach Vermittlungsserver**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Vermittlungsserver** <br/> |Nein  <br/> |Name des Vermittlungsservers.  <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.  <br/> |
|**Gesamt** <br/> |Nein  <br/> |Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.  <br/> |
   

