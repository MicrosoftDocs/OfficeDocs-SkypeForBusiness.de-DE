---
title: Konferenzbeitrittszeit in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
description: 'Zusammenfassung: Erfahren Sie mehr über die Zusammenfassung Konferenzbeitrittszeit in Skype für Business Server.'
ms.openlocfilehash: 8264ac8df7a6299484c88121ac1352401833ebe9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874207"
---
# <a name="conference-join-time-report-in-skype-for-business-server"></a>Konferenzbeitrittszeit in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den zusammenfassenden Konferenzbeitrittszeit in Skype für Business Server.
  
Mit dem Bericht über Zeitpunkt des Konferenzbeitritts können Sie bestimmen, wie lange die Benutzer benötigen, um einer Konferenz beizutreten. Dieser Bericht enthält die durchschnittliche Zeit für den Beitritt (in Millisekunden) sowie eine Übersicht darüber, wie viele Benutzer in maximal 2 Sekunden einer Konferenz beitreten konnten, wie viele Benutzer zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten usw.
  
## <a name="accessing-the-conference-join-time-report"></a>Zugriff auf den Bericht über Zeitpunkt des Konferenzbeitritts

Auf den Bericht über den Zeitpunkt des Konferenzbeitritts können Sie über die Startseite für Überwachungsberichte zugreifen.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Zeitpunkt des Konferenzbeitritts verwenden können.
  
**Filter im Bericht über Zeitpunkt des Konferenzbeitritts**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
|**Konferenzsitzungen** <br/> | Der Sitzungstyp. Gültige Werte sind: <br/>  [Alle] <br/>  Konferenzzustandsobjekt-Sitzungen (der Konferenzzustand ist zentrale Richtlinie sowie Zustandsverwaltung für Online-Besprechungen und koordiniert alle Aspekte einer Konferenz) <br/>  Anwendungsfreigabe <br/>  A/V-Konferenzen <br/>  Wenn Sie [Alle] auswählen, wird die Gesamtzeit für den Konferenzbeitritt oben im Bericht angezeigt. Beachten Sie, dass diese Gesamtwerte nur für Konferenzen sind, die mit Microsoft Exchange oder Microsoft Outlook geplant wurden. <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Zeitpunkt des Konferenzbeitritts angegeben werden.
  
**Metriken im Bericht über Zeitpunkt des Konferenzbeitritts**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Datum** <br/> Der eigentliche Name dieser Metrik hängt vom ausgewählten Intervall ab.  <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.  <br/> |
|**Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.  <br/> |
|**Mittelwert (ms)** <br/> |Nein  <br/> |Die durchschnittliche Zeit (in Millisekunden), die die Teilnehmer für den Konferenzbeitritt benötigten.  <br/> |
|**Sitzungen \< 2 Sekunden, Anzahl** <br/> |Nein  <br/> |Die Anzahl der Teilnehmer, die der Konferenz in weniger als 2 Sekunden beitreten konnten.  <br/> |
|**Sitzungen \< 2 Sekunden, Prozentsatz** <br/> |Nein  <br/> ||
|**Sitzungen 2-5 Sekunden, Anzahl** <br/> |Nein  <br/> |Die Anzahl der Teilnehmer, die zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten.  <br/> |
|**Sitzungen 2-5 Sekunden, Prozentsatz** <br/> |Nein  <br/> |Der Prozentsatz der Gesamtteilnehmer, die zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten.  <br/> |
|**Sitzungen 5-10 Sekunden, Anzahl** <br/> |Nein  <br/> |Die Anzahl der Teilnehmer, die zwischen 5 und 10 Sekunden für den Konferenzbeitritt benötigten.  <br/> |
|**Sitzungen 5-10 Sekunden, Prozentsatz** <br/> |Nein  <br/> |Der Prozentsatz der Gesamtteilnehmer, die zwischen 5 und 10 Sekunden für den Konferenzbeitritt benötigten.  <br/> |
|**Sitzungen \> 10 Sekunden, Anzahl** <br/> |Nein  <br/> |Die Anzahl der Teilnehmer, die mehr als 10 Sekunden für den Konferenzbeitritt benötigten.  <br/> |
|**Sitzungen \> 10 Sekunden, Prozentsatz** <br/> |Nein  <br/> |Der Prozentsatz der Gesamtteilnehmer, die mehr als 10 Sekunden für den Konferenzbeitritt benötigten.  <br/> |
   

