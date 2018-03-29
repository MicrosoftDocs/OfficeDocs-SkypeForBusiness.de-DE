---
title: Bereitstellen der Verwaltung von Skype Room System V2 mit OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: In diesem Artikel wird erläutert, wie in Microsoft Operations Management Suite mit Weise integrierte, End-to-End-Verwaltung von Skype Raum Systemen v2 Geräte bereitstellen.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Bereitstellen der Verwaltung von Skype Room System V2 mit OMS
 
In diesem Artikel wird erläutert, wie in Microsoft Operations Management Suite mit Weise integrierte, End-to-End-Verwaltung von Skype Raum Systemen v2 Geräte bereitstellen. 
  
Sie können Microsoft Operations Management Suite (OMS) so konfigurieren, dass grundlegende Telemetriedaten bereitgestellt werden, die Ihnen bei der Verwaltung von Geräten für Skype-Besprechungsräume helfen. Wenn Ihre Verwaltungslösung heranreift, können Sie zusätzliche Daten- und Verwaltungsfunktionen erwerben, um eine detailliertere Ansicht der Geräteleistung zu erstellen.
  
Allgemein müssen Sie die folgenden Aufgaben ausführen:
  
1. [Konfigurieren von Geräten für die OMS-Verwaltung ](with-oms.md#config_devices)
    
2. [Zuordnen benutzerdefinierter Felder](with-oms.md#Custom_fields)
    
3. [Definieren der SRS V2-Ansichten in OMS](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a>Suchen und Aufzeichnen von Gerätestandorten, -funktionen und -konfigurationen
<a name="find_devices"> </a>

Im ersten Schritt erstellen Sie eine detaillierte Datenbank aller Geräte im System, der Details zu ihren Funktionen und Konfigurationen und der Standorte. In mittleren Organisationen kann ein Arbeitsblatt für diese Aufgabe ausreichen. Wenn Sie in einer größeren Organisation arbeiten, müssen Sie möglicherweise Inventarverwaltungstools und Dienste von Drittanbietern in Betracht ziehen. Wichtig ist, dass Sie den Standort und alle relevanten Details jedes Geräts aufzeichnen.
  
Anschließend können Sie diese Informationen nutzen, um Techniker zu entsenden und Gerätepatches und -upgrades zu verwalten.
  
## <a name="configure-devices-for-oms-management"></a>Konfigurieren von Geräten für die OMS-Verwaltung 
<a name="config_devices"> </a>

Führen Sie für jedes Gerät SRS wie unter [an den Log Analytics-Dienst in Azure-Computern mit Windows eine Verbindung herstellen](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).
  
## <a name="configure-oms-to-collect-device-event-logs"></a>Konfigurieren von OMS zum Erfassen von Geräteereignisprotokollen
<a name="config_devices"> </a>

Sie müssen speziell zum Sammeln von Ereignisprotokollen von SRS Geräte entsprechend den Schritten unter [Windows-Ereignisprotokoll-Datenquellen im Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)OMS konfigurieren. Ereignisprotokoll SRS auswählen ist "Skype Raum System", und überprüfen Sie die Optionsfelder für alle Typen: Fehler, Warnung und Informationen.
  
## <a name="map-custom-fields"></a>Zuordnen benutzerdefinierter Felder
<a name="Custom_fields"> </a>

Bevor die Kacheln, die in den [Ansichten in OMS definieren die SRS v2](with-oms.md#Views) erstellt verwendet werden können, müssen Sie benutzerdefinierte Felder für die Ansicht zu erstellen. Einzelheiten zum Erstellen von benutzerdefinierter Feldern finden Sie unter [benutzerdefinierte Felder im Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) .
  
Verwenden Sie die unten aufgeführten Zuordnungen, OMS automatisch die _CF hinzufügen, wenn Sie das neue Feld zu definieren. 
  
> [!IMPORTANT]
> Denken Sie daran, dass alle JSON und OMS Felder Groß-/Kleinschreibung beachtet werden. 
  
**Zuordnen von benutzerdefinierten Feldern**

|**JSON-Feld**|**OMS-benutzerdefiniertes Feld**|
|:-----|:-----|
|Beschreibung  <br/> |SRSEventDescription_CF  <br/> |
|ResourceState  <br/> |SRSResourceState_CF  <br/> |
|-Parameterwert  <br/> |SRSOperationName_CF  <br/> |
|OperationResult  <br/> |SRSOperationResult_CF  <br/> |
|OS  <br/> |SRSOSVersion_CF  <br/> |
|OSVersion  <br/> |SRSOSLongVersion_CF  <br/> |
|Alias  <br/> |SRSAlias_CF  <br/> |
|DisplayName  <br/> |SRSDisplayName_CF  <br/> |
|AppVersion  <br/> |SRSAppVersion_CF  <br/> |
|IPv4Address  <br/> |SRSIPv4Address_CF  <br/> |
|IPv6Address  <br/> |SRSIPv6Address_CF  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a>Definieren der SRS V2-Ansichten in OMS
<a name="Views"> </a>

Nachdem Daten erfasst werden und benutzerdefinierte Felder zugeordnet sind, können OMS-Ansicht-Designer Sie ein Dashboard mit Kacheln zum Überwachen von Ereignissen, SRS v2 entwickeln. Verwenden Sie Designer anzeigen, um die folgenden Kacheln erstellen, finden Sie unter [Use Ansicht-Designer zum Erstellen von benutzerdefinierter Ansichten im Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) nach Bedarf.
  
### <a name="create-a-tile-that-shows-healthy-devices"></a>Erstellen einer Kachel, die fehlerfreie Geräte anzeigt

1. Definieren Sie den Fall:  
    
    Diese Kachel zeigt alle Geräte an, die in den letzten zehn Minuten eine Taktnachricht gesendet haben.
    
2. Weisen Sie einen Gruppentitel zu.  
    
   ```
   SRS v2
   ```

3. Aktivieren Sie das neue Gruppe
    
4. Fügen Sie den Legendentext für die Kachel hinzu.
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. Geben Sie die Kachelabfrage ein.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. Geben Sie die Listenabfrage ein.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. Definieren Sie den Spaltentitelnamen.
    
   ```
   Display Name
   ```

8. Definieren der Wert der Spalte Titel
    
   ```
   Last HB
   ```

9. Geben Sie die Navigationsabfrage ein.
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a>Erstellen der Kachel, die Geräte mit Konnektivitätsproblemen anzeigt

1. Definieren Sie den Fall:  
    
    Diese Kachel zeigt alle Geräte an, die nicht in den letzten zehn Minuten eine Taktnachricht gesendet haben. Bei diesen Geräten liegen möglicherweise Probleme mit der Netzwerk-, Exchange- oder Skype for Business-Konnektivität vor.
    
2. Weisen Sie einen Gruppentitel zu.  
    
   ```
   SRS v2
   ```

3. Aktivieren Sie nicht das Kontrollkästchen „Neue Gruppe“. Dies haben Sie bereits beim Erstellen von Kachel 1 getan, und dies ist nicht erneut notwendig.
    
4. Fügen Sie den Legendentext für die Kachel hinzu.
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. Geben Sie die Kachelabfrage ein.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. Geben Sie die Listenabfrage ein.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. Definieren Sie den Spaltentitelnamen.
    
   ```
   Device Name
   ```

8. Definieren Sie den Spaltentitelwert.  
    
   ```
   Last HB
   ```

9. Geben Sie die Navigationsabfrage ein.
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a>Auflisten von Geräten mit Hardwarefehler 

1. Definieren Sie den Fall:  
    
   Diese Kachel zeigt alle Geräte, die eine Meldung angezeigt, eine einen oder mehrere Komponente Hardwareprobleme in den letzten 10 Minuten gesendet. 
    
2. Weisen Sie einen Gruppentitel zu.  
    
   ```
   SRS v2
   ```

3. Aktivieren Sie nicht das Kontrollkästchen „Neue Gruppe“. Dies haben Sie bereits beim Erstellen von Kachel 1 getan, und dies ist nicht erneut notwendig.
    
4. Kachellegende:  
    
   ```
   Devices with a Hardware Error
   ```

5. Kachelabfrage
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. Listenabfrage:
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. Spaltentitelname:  
    
   ```
   Display Name
   ```

8. Spaltentitelwert:  
    
   ```
   Last Error
   ```

9. Navigationsabfrage:  
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a>Auflisten von Geräten mit App-Fehler  

1. Definieren Sie den Fall: 
    
   Diese Kachel zeigt alle SRS-Geräte an, die in den letzten zehn Minuten mindestens einen App-Komponentenfehler gemeldet haben.
    
2. Weisen Sie einen Gruppentitel zu.  
    
   ```
   SRS v2
   ```

3. Aktivieren Sie nicht das Kontrollkästchen „Neue Gruppe“. Dies haben Sie bereits beim Erstellen von Kachel 1 getan, und dies ist nicht erneut notwendig.
    
4. Kachellegende:  
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. Kachelabfrage:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. Listenabfrage:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. Spaltentitelname:  
    
   ```
   Device Name
   ```

8. Spaltentitelwert:  
    
   ```
   Last Error
   ```

9. Navigationsabfrage:
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a>Auflisten von Geräten, die neu gestartet werden mussten

1. Definieren Sie den Fall: 
    
   Diese Kachel zeigt alle SRS-Geräte, die in den letzten 24 Stunden neu gestartet wurden, sowie die Anzahl der Neustarts an.
    
2. Weisen Sie einen Gruppentitel zu.  
    
  ```
  SRS v2
  ```

3. Aktivieren Sie nicht das Kontrollkästchen „Neue Gruppe“. Dies haben Sie bereits beim Erstellen von Kachel 1 getan, und dies ist nicht erneut notwendig.
    
4. Kachellegende:  
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. Kachelabfrage:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. Listenabfrage:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. Spaltentitelname:  
    
   ```
   Display Name
   ```

8. Spaltentitelwert:  
    
   ```
   Number of restarts
   ```

9. Navigationsabfrage:  
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

Damit ist die Erstellung der Ansicht abgeschlossen. Die zurzeit verfügbaren Warnungen werden alle auf mindestens einer dieser Kacheln angezeigt.
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="Views"> </a>

#### 

[Planen der Verwaltung von Skype Raum Systemen v2 mit OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Verwalten von Skype Raum Systemen v2 Geräte mit OMS](../../manage/skype-room-systems-v2/oms.md)

