---
title: Bereitstellen der Verwaltung von Skype Room System V2 mit OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: In diesem Artikel wird erläutert, wie in Microsoft Operations Management Suite mit Weise integrierte, End-to-End-Verwaltung von Skype Raum Systemen v2 Geräte bereitstellen.
ms.openlocfilehash: d56b67d17cd66ceaf88a2cbe0b222d4769667c4c
ms.sourcegitcommit: 1f345f13c8edf04efb0a8dd02d6c11f793ba201a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "22109037"
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Bereitstellen der Verwaltung von Skype Room System V2 mit OMS
 
In diesem Artikel wird erläutert, wie einrichten und Bereitstellen von integrierte, End-to-End-Verwaltung von Skype Raum Systemen v2 Geräten mithilfe von Microsoft Operations Management Suite.
  
Sie können Microsoft Operations Management Suite um bieten grundlegende Telemetrie konfigurieren, und Warnungen, die Ihnen helfen verwalten Skype meeting Room Geräte. Der Management-Lösung Laufe der Zeit, empfiehlt es sich zum Bereitstellen von zusätzlichen Daten und Management-Funktionen für eine ausführlichere Ansicht des Geräts Verfügbarkeit und Leistung zu erstellen.

Wie im folgenden Beispiel wird ein Dashboard können Sie anhand dieses Handbuchs detaillierten Status für das Gerät Verfügbarkeit, Anwendung und Hardware Integrität und Skype Raum Systemen v2 Application Version Verteilung reporting abzurufen.

![Beispiel-OMS-Ansicht für SRS v2] (../../media/Deploy_OMS_1.png "Beispiel-OMS-Ansicht für SRS v2")
  
Allgemein müssen Sie die folgenden Aufgaben ausführen:


1.  [Überprüfen der Konfiguration des Operations Management Suite](with-oms.md#validate_OMS)
2.  [Konfigurieren von Testgeräten für Vorgänge Management Suite-Einrichtung](with-oms.md#configure_test_devices)
3.  [Zuordnen benutzerdefinierter Felder](with-oms.md#Custom_fields)
4.  [Definieren von Skype Raum Systemen v2 Ansichten in Operations Management Suite](with-oms.md#Define_Views)
5.  [Definieren von Warnungen](with-oms.md#Alerts)
6.  [Konfigurieren Sie aller Geräte für Vorgänge Management Suite](with-oms.md#configure_all_devices)
7.  [Konfigurieren Sie zusätzliche Vorgänge Management Suite-Lösungen](with-oms.md#Solutions)

> [!IMPORTANT]
> Obwohl mit minimaler Konfiguration der Vorgänge Management Suite einen Computer mit einem Windows-Betriebssystem überwachen können, sind noch einige Skype Raum Systeme v2-spezifische Schritte, die Sie vor Beginn der Bereitstellung von Agents zu allen Skype Raum durchführen müssen Systeme Geräte.
> Aus diesem Grund empfiehlt es sich, dass Sie in der richtigen Reihenfolge für eine gesteuerte Setup und Konfiguration alle Konfigurationsschritte ausführen. Die Qualität des Ergebnisses End hängt die Qualität der Erstkonfiguration sehr viel.

## <a name="validate-operations-management-suite-configuration"></a>Überprüfen der Konfiguration des Operations Management Suite
<a name="validate_OMS"> </a>

Sie benötigen ein Operations Management Suite Workspace zum Erfassen von Protokollen von Skype Raum Systemen v2 Geräten zu starten. Ein Arbeitsbereich ist eine eindeutige Protokoll Analytics-Umgebung mit einem eigenen Daten-Repository, Datenquellen und -Lösungen. Wenn Sie bereits einen vorhandenen Protokoll Analytics Arbeitsbereich haben, können Sie es zum Überwachen der Skype Raum Systemen v2-bereitstellungs verwenden, oder erstellen muss ein dedizierter Protokoll Analytics Arbeitsbereich speziell für die Überwachung zu Skype Raum Systemen v2.

Wenn Sie ein neues Protokoll Analytics Workspace erstellen müssen, führen Sie die Schritte im Artikel [Erstellen eines Arbeitsbereichs Protokoll Analytics im Azure-portal](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)

> [!NOTE]
> Um Protokolldateien Analytics mit Operations Management Suite verwenden, müssen Sie ein aktives Azure-Abonnement verfügen. Wenn Sie nicht über ein Azure-Abonnement verfügen, können Sie [eine kostenlose Testversion](https://azure.microsoft.com/free) als Ausgangspunkt erstellen.


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-v2-event-logs"></a>Konfigurieren der Vorgänge Management Suite Skype Raum Systemen v2 Ereignisprotokolle erfassen

Protokoll Analytics sammelt Ereignisse nur aus der Windows-Ereignisprotokolle, die in den Einstellungen angegeben sind. Für jedes Protokoll werden nur die Ereignisse mit der ausgewählten Schweregrade erfasst.

Sie müssen so konfigurieren Sie Vorgänge Management Suite, um die Protokolle erforderlich, um die Überwachung Skype Raum Systemen v2 Geräte- und Status gespeichert. Skype-Chatroom-Systemen v2 Geräten verwenden **Skype Raum** Systemereignisprotokoll.

Vorgänge Management Suite erfassen die Skype Raum Systemen v2 Ereignisse konfigurieren finden Sie in [Windows-Ereignisprotokoll-Datenquellen im Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

![Ereignisprotokoll-Einstellungen] (../../media/Deploy_OMS_2.png "Ereignisprotokoll-Einstellungen")


> [!IMPORTANT]
> Wählen Sie **Skype Raum** Systemereignisprotokoll, und wählen Sie dann das Kontrollkästchen **Fehler**, **Warnung**und **Informationen** aus.

## <a name="configure-test-devices-for-operations-management-suite-setup"></a>Konfigurieren von Testgeräten für Vorgänge Management Suite-setup
<a name="configure_test_devices"> </a>

Sie müssen vorbereiten Vorgänge Management Suite Skype Raum Systemen v2-bezogenen Ereignisse überwachen können. Zu, Sie müssen Vorgänge Management Suite Agents nur ein oder zwei Skype Raum Systemen v2 Geräte bereitstellen, dass physische Zugriff auf und die haben Testgeräte einige Daten zu generieren und schieben Sie ihn in den Protokolldateien Analytics Arbeitsbereich.

### <a name="install-operations-management-suite-agents-to-test-devices"></a>Installieren der Operations Management Suite-Agents zum Testen von Geräten

Bereitstellen des Vorgänge Management Suite Agents Testgeräte mithilfe der Anweisungen unter [an den Log Analytics-Dienst in Azure-Computern mit Windows eine Verbindung herstellen](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows). In diesem Artikel erhalten Sie detaillierte Informationen zu den Schritten für die Bereitstellung von Microsoft Monitoring-Agent für Windows, Informationen zum Beziehen der Vorgänge Management Suite *Workspace-ID* und der *Primärschlüssel* für Skype Raum Systemen v2 Geräte erhalten möchten mit Ihrer Bereitstellung Vorgänge Management Suite und Schritte zum Überprüfen der Agentkonnektivität zu Protokoll Analytics verbunden ist.

### <a name="generate-sample-skype-room-systems-events"></a>Beispiel Skype Raum Systeme Ereignisse generieren

Nachdem der Agent Vorgänge Management Suite auf Testgeräte bereitgestellt wird, stellen Sie sicher, dass die erforderlichen Ereignisprotokolldaten von Protokolldateien Analytics gesammelt werden.

1.  Melden Sie sich am [Microsoft Operations Management Suite-Portal](http://aka.ms/omsportal).

2.  Die von einem Skype Raum Systemen v2 Gerät generierten Ereignisse aufgelistet:
    1.  Wechseln Sie auf **Protokoll suchen** und verwenden Sie eine Abfrage, um die Datensätze abzurufen, die das benutzerdefinierte Feld.
    2.  Beispielabfrage:`Event | where Source == "SRS-App"`

3.  Stellen Sie sicher, dass die Abfrage Datensätze zurückgibt, die erfolgreiche Heartbeat-Ereignisse umfassen.

4.  Generiert ein Hardwareproblem, und überprüfen Sie, dass die erforderlichen Ereignisse in Operations Management Suite angemeldet sind.
    1.  Trennen Sie eine der Geräte auf den Test Skype Raum Systemen v2 System. Dies könnte die Kamera, Freisprechtelefon, Mikrofon oder Vordergrund Raum anzeigen
    2.  Warten Sie 10 Minuten für das Ereignisprotokoll in Operations Management Suite aufgefüllt werden.
    3.  Verwenden einer Abfrage zu Liste Hardwareereignisse Fehler:`Event | where EventID == 3001`

5.  Generieren eines Problems Anwendung, und überprüfen Sie, ob die erforderlichen Ereignisse protokolliert werden.
    1.  Ändern Sie Skype-Chatroom-Systemen v2 Anwendungskonfiguration, und geben Sie eine falsche Session Initiation Protocol (SIP) Adresse/Kennwort-Paar.
    2.  Warten Sie 10 Minuten für das Ereignisprotokoll in Operations Management Suite aufgefüllt werden.
    3.  Verwenden Sie eine Abfrage Liste Anwendungsereignisse Fehler:`Event | where EventID == 2001`

> [!IMPORTANT]
> Diese Beispiel Ereignisprotokolle sind erforderlich, bevor benutzerdefinierte Felder konfiguriert werden können. Fortfahren Sie nicht mit dem nächsten Schritt, bis Sie die erforderlichen Ereignisprotokolle gesammelt haben.

## <a name="map-custom-fields"></a>Zuordnen benutzerdefinierter Felder
<a name="Custom_fields"> </a>

Sie können benutzerdefinierte Felder verwenden, um bestimmte Daten aus den Ereignisprotokollen zu extrahieren. Sie müssen benutzerdefinierte Felder definieren, die später mit Kacheln, Dashboard-Ansichten und Warnungen verwendet wird. Finden Sie unter [benutzerdefinierte Felder im Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) , und machen Sie sich mit den Konzepten vertraut, bevor Sie die benutzerdefinierten Felder erstellen.

Gehen Sie folgendermaßen vor, um die benutzerdefinierten Felder aus den aufgezeichneten Ereignisprotokollen zu extrahieren:

1.  Melden Sie sich am [Microsoft Operations Management Suite-Portal](http://aka.ms/omsportal).

2.  Die von einem Skype Raum Systemen v2 Gerät generierten Ereignisse aufgelistet:
    1.  Wechseln Sie auf **Protokoll suchen** und verwenden Sie eine Abfrage, um die Datensätze abzurufen, die das benutzerdefinierte Feld.
    2.  Beispielabfrage:`Event | where Source == "SRS-App"`

3.  Wählen Sie einen der Einträge aus, wählen Sie die Schaltfläche auf der linken Seite, und starten Sie im Feld Extraction-Assistent.

   ![Feld Extraction-Assistent] (../../media/Deploy_OMS_3.png "Feld Extraction-Assistent")

4.  Markieren Sie die Daten aus der RenderedDescription extrahieren, und geben Sie einen Titel Feld möchten. In Tabelle 1 werden die Namen der Felder, die Sie verwenden sollten, bereitgestellt.

   ![Definition für ein benutzerdefiniertes Feld] (../../media/Deploy_OMS_4.png "Definition für ein benutzerdefiniertes Feld")

5.  Verwenden Sie die Zuordnungen in *Tabelle 1*dargestellt. Vorgänge Management Suite wird automatisch hinzufügen der ** \_CF** Zeichenfolge, die das neue Feld zu definieren.

> [!IMPORTANT]
> Denken Sie daran, dass alle JSON und Vorgänge Management Suite Felder Groß-/Kleinschreibung beachtet werden.

> Achten Sie auf den Status des Kontrollkästchens EventID, in der folgenden Tabelle können. Stellen Sie sicher, dass Sie den Status dieses Kontrollkästchens für Vorgänge Management Suite zum Extrahieren von benutzerdefinierten Feldwerte erfolgreich zu bestätigen.
> 
> ![Definition für ein benutzerdefiniertes Feld] (../../media/Deploy_OMS_5.png "Definition für ein benutzerdefiniertes Feld") 

**Tabelle 1**

| JSON-Feld                   | Benutzerdefiniertes OMS-Feld           | Ereigniskennung        |
|:-----------------------------|:---------------------------|:----------------|
| Beschreibung                  | SRSEventDescription_CF     | Nicht aktiviert    |
| ResourceState                | SRSResourceState_CF        | Nicht aktiviert    |
| -Parameterwert                | SRSOperationName_CF        | Nicht aktiviert    |
| OperationResult              | SRSOperationResult_CF      | Nicht aktiviert    |
| OS                           | SRSOSVersion_CF            | Nicht aktiviert    |
| OSVersion                    | SRSOSLongVersion_CF        | Nicht aktiviert    |
| Alias                        | SRSAlias_CF                | Nicht aktiviert    |
| DisplayName                  | SRSDisplayName_CF          | Nicht aktiviert    |
| AppVersion                   | SRSAppVersion_CF           | Nicht aktiviert    |
| IPv4Address                  | SRSIPv4Address_CF          | Nicht aktiviert    |
| IPv6Address                  | SRSIPv6Address_CF          | Nicht aktiviert    |
| Am Anfang Status Raum anzeigen | SRSFORDStatus_CF           | 3001            |
| Kamera-status                | SRSCameraStatus_CF         | 3001            |
| Mikrofon Konferenzstatus | SRSConfMicrophoneStatus_CF | 3001            |
| Lautsprecher Konferenzstatus    | SRSConfSpeakerStatus_CF    | 3001            |
| Standardstatus für Lautsprecher       | SRSDefaultSpeakerStatus_CF | 3001            |
| Motion Sensorstatus         | SRSMotionSensorStatus_CF   | 3001            |
| HDMI Aufnahme status           | SRSHDMIIngestStatus_CF     | 3001            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a>Definieren von Skype Raum Systemen v2 Ansichten in Operations Management Suite
<a name="Define_Views"> </a>

Nachdem Daten erfasst werden und benutzerdefinierte Felder zugeordnet sind, können Vorgänge Management Suite Ansicht-Designer Sie ein Dashboard mit verschiedenen Kacheln zum Überwachen des Skype Raum Systemen v2 entwickeln. Erstellen Sie mit dem Ansicht-Designer die folgenden Kacheln. Weitere Informationen finden Sie unter [Verwendung Ansicht-Designer zum Erstellen von benutzerdefinierter Ansichten im Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)

> [!NOTE]
> Vorherigen Schritte in diesem Handbuch sollten für das Dashboard Kacheln ordnungsgemäß abgeschlossen wurden, ist.


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>Erstellen eines Skype Raum Systemen v2-Dashboards mithilfe der Importmethode

Sie können ein Dashboard Vorgänge Management Suite importieren und Überwachung Ihrer Geräte sofort zu starten. Führen Sie die folgenden Schritte aus, um das Dashboard zu importieren:

1.  Rufen Sie die [SkypeRoomSystems_v2.omsview](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview) -Dashboard-Datei.
2.  Melden Sie sich am [Microsoft Operations Management Suite-Portal](http://aka.ms/omsportal).
3.  Öffnen Sie **Designer anzeigen**.
4.  Die Option **Importieren**aus, und wählen Sie dann die Datei **SkypeRoomSystems_v2.omsview** aus.
5.  Wählen Sie **Speichern**aus.

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>Erstellen Sie ein Skype Raum Systemen v2 Dashboard manuell

Alternativ können Sie Ihr eigenes Dashboard erstellen und Hinzufügen von nur Kacheln, mit denen Sie überwachen möchten.

#### <a name="configure-the-overview-tile"></a>Konfigurieren Sie die Kachel "Übersicht"
1.  Öffnen Sie **Designer anzeigen**.
2.  Wählen Sie **Übersicht über die Kachel aus**, und wählen Sie dann aus dem Katalog **zweier Zahlen** .
3.  Nennen Sie die Kachel **Skype Raum Systemen v2**.
4.  Definieren Sie die **erste Kachel**:<br>
    **Legende:** Geräte, die einen Takt mindestens einmal innerhalb des letzten Monats gesendet<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definieren Sie die **zweite Kachel**:<br>
    **Legende:** Aktive Geräte, die innerhalb der letzten Stunde Takt gesendet<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Wählen Sie **Übernehmen**.

### <a name="create-a-tile-that-displays-active-devices"></a>Erstellen von Kacheln, die aktiven Geräte anzeigt
1.  Wählen Sie **Ansicht Dashboard** mit dem Hinzufügen der Kacheln beginnen.
2.  Wählen Sie aus dem Katalog **Anzahl & Liste**
3.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Heartbeat-Status<br>
    **Neue Gruppe:** Ausgewählt
4.  Definieren Sie die **Kachel** -Eigenschaften:<br>
    **Legende:** Aktive Geräte (Heartbeat gesendet, die in den letzten 20 Minuten)<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definieren Sie die **Liste** Eigenschaften:<br>
    **Abfrage aufgelistet:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definieren Sie **Spaltentitel**:<br>
    **Name:** Anzeigename<br>
    **Wert:** Letzter Takt
7.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **anwenden**und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Erstellen Sie eine Kachel, die Geräte angezeigt, die Probleme mit der Konnektivität
1.  Wählen Sie aus dem Katalog **Anzahl & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Leer lassen<br>
    **Neue Gruppe:** Nicht aktiviert
3.  Definieren Sie die **Kachel** -Eigenschaften:<br>
    **Legende:** Inaktive Geräte (keine Heartbeat-Nachricht gesendet, die in den letzten 20 Minuten)<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definieren Sie die **Liste** Eigenschaften:<br>
    **Abfrage aufgelistet:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definieren Sie **Spaltentitel**:<br>
    **Name:** Anzeigename<br>
    **Wert:** Letzter Takt
6.  **Navigation Abfrage**zu definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie **anwenden**und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Erstellen Sie eine Kachel, die Geräte angezeigt, die ein Hardwarefehler

1.  Wählen Sie aus dem Katalog **Anzahl & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Hardwarestatus<br>
    **Neue Gruppe:** Ausgewählt
3.  Definieren Sie die **Kachel** -Eigenschaften:<br>
    **Legende:** Geräte, die in der letzten Stunde einen Hardwarefehler auftraten <br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Liste** Eigenschaften:<br>
    **Abfrage aufgelistet:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```
5.  Definieren Sie **Spaltentitel**:<br>
    **Name:** Anzeigename<br>
    **Wert:** Letzten Fehler
6.  **Navigation Abfrage**zu definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie **anwenden**und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a>Erstellen Sie eine Kachel, die Skype Raum Systemen v2 Betriebssystemversionen angezeigt wird.

1.  Wählen Sie aus dem Katalog **rad & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Einzelheiten zu Syetem <br>
    **Neue Gruppe:** Ausgewählt
3.  **Header** -Eigenschaften zu definieren:<br>
    **Titel:** Versionen des Betriebssystems<br>
    **Untertitel:** Geräte, auf denen bestimmte Betriebssystemversionen
4.  Definieren Sie die **Rad** -Eigenschaften:<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Text zentrieren:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie **die Listeneigenschaften** .<br>
    **Abfrage aufgelistet:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ausblenden Diagramm:** Ausgewählt<br>
    **Sparklines aktivieren:** Nicht aktiviert
6.  Definieren Sie **Spaltentitel**.<br>
    **Name:** Anzeigename<br>
    **Wert:** Leer lassen
7.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **anwenden** und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a>Erstellen von Kacheln, die Skype Raum Systemen v2 Anwendungsversionen anzeigt

1.  Wählen Sie aus dem Katalog **rad & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Skype-Chatroom-Systemen v2 Anwendungsdetails <br>
    **Neue Gruppe:** Ausgewählt
3.  **Header** -Eigenschaften zu definieren:<br>
    **Titel:** Anwendungsversionen<br>
    **Untertitel:** Geräte, auf denen bestimmte Anwendungsversionen
4.  Definieren Sie die **Rad** -Eigenschaften:<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Text zentrieren:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie **die Listeneigenschaften** .<br>
    **Abfrage aufgelistet:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ausblenden Diagramm:** Ausgewählt<br>
    **Sparklines aktivieren:** Nicht aktiviert
6.  Definieren Sie **Spaltentitel**.<br>
    **Name:** Anzeigename<br>
    **Wert:** Leer lassen
7.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **anwenden** und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Erstellen Sie eine Kachel, die Geräte angezeigt, die einen Application-Fehler

1.  Wählen Sie aus dem Katalog **Anzahl & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppieren Titel:** Leer lassen<br>
    **Neue Gruppe:** Nicht aktiviert
3.  Definieren Sie die **Kachel** -Eigenschaften.<br>
    **Legende:** Geräte, die in der letzten Stunde einen Anwendungsfehler auftreten<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie **die Listeneigenschaften** .<br>
    **Abfrage aufgelistet:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren Sie **Spaltentitel**.<br>
    **Name:** Anzeigename<br>
    **Wert:** Letzten Fehler
6.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie **anwenden** und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Erstellen von Kacheln, die Geräte anzeigt, die neu gestartet wurden

1.  Wählen Sie aus dem Katalog **Anzahl & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppieren Titel:** Leer lassen<br>
    **Neue Gruppe:** Nicht aktiviert
3.  Definieren Sie die **Kachel** -Eigenschaften.<br>
    **Legende:** Geräte, auf dem die Anwendung in den letzten 24 Stunden und die Anzahl an Neustarts neu gestartet wurde<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie **die Listeneigenschaften** .<br>
    **Abfrage aufgelistet:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definieren Sie **Spaltentitel**.<br>
    **Name:** Anzeigename<br>
    **Wert:** Anzahl an Neustarts
6.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie **anwenden** und dann auf **Schließen**.
8.  Wählen Sie **Speichern** , um das Dashboard zu speichern.

Nachdem Sie Ihre Ansichten erstellen abgeschlossen haben.

Die Microsoft Operations Management Suite-Portal oder Vorgänge Management Suite mobilen Clients für [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [ios-](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)oder [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) können Sie Ihre Ansichten zugreifen.

## <a name="configure-alerts-in-operations-management-suite"></a>Konfigurieren von Warnungen in Operations Management Suite
<a name="Alerts"></a> Bei einer Skype Raum Systemen v2 Gerät ein Problem auftritt, kann Microsoft Operations Management Suite Alarme, um die Administratoren mit den Details des Problems benachrichtigen auslösen.

Vorgänge Management Suite umfasst eine integrierte Alarm-Mechanismen, die über geplanten Protokoll Suchvorgänge in geplanten Intervallen ausgeführt wird. Wenn die Ergebnisse der Suche Protokoll einige bestimmten Kriterien erfüllen, wird ein Warnung Datensatz erstellt.

![OMS Alarm-Mechanismen] (../../media/Deploy_OMS_6.png "OMS Alarm-Mechanismen")

Die Regel kann dann automatisch ausführen eine oder mehrere Aktionen zum proaktiv benachrichtigen Sie über die Benachrichtigung oder einem anderen Prozess aufzurufen. Die möglichen Optionen von Warnungen für Vorgänge Management Suite sind:
-   Senden einer e-Mail
-   Aufrufen von einem externen Prozess über eine HTTP POST-Anforderung
-   Starten einer Runbook in Azure Automation service

Finden Sie unter [Understanding Warnungen im Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) erfahren Sie mehr über die Warnungen in Operations Management Suite.

> [!NOTE]
> In den folgenden Beispielen sendet e-Mail-Benachrichtigungen, wenn ein Skype Raum Systemen v2 Gerät ein Hardware oder ein Anwendungsfehler generiert. 


### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a>Konfigurieren Sie eine e-Mail-Warnung für Skype Raum Systemen v2 Hardwareprobleme

Konfigurieren Sie eine Warnung Regel, die Skype Raum Systemen v2 Geräte überprüft, die innerhalb der letzten Stunde Hardwareprobleme kommuniziert haben.
1.  Melden Sie sich am [Microsoft Operations Management Suite-Portal](http://aka.ms/omsportal).

2.  Wählen Sie die **Log-Suche**.

3.  Geben Sie die folgende Abfrage aus, und wählen Sie dann auf **Ausführen**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF 
    |sort by TimeGenerated desc
    ```

4.  Nachdem die Abfrage ausgeführt wird, wählen Sie **Alert**. Die Seite **Warnungsregel hinzufügen** wird geöffnet.

5.  Konfigurieren von Benachrichtigungseinstellungen mit den folgenden Informationen:<br>
    **Regelname:** Skype-Raum Systemen v2 Hardware Fehler Benachrichtigung<br>
    **Beschreibung:** Liste der Geräte, die innerhalb der letzten Stunde ein Hardwareproblem aufgetreten ist<br>
    **Schweregrad:** Wichtige<br>
    **Abfrage:** Verwenden Sie die vorab aufgefüllten Search-Abfrage<br>
    **Zeitfenster:** 1 Stunde<br>
    **Benachrichtigungshäufigkeit:** 1 Stunde<br>
    **Anzahl der Ergebnisse:** Größer als 0<br>
    **E-Mail-Betreff:** Skype-Raum Systemen v2 Hardware Fehler Benachrichtigung<br>
    **Empfänger:** Schließen Sie die e-Mail-Adressen mit Semikolons als Trennzeichen ein<br>

6.  Wählen Sie **Speichern**aus.

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a>Konfigurieren Sie eine e-Mail-Benachrichtigung bei Problemen mit Skype Raum Systemen v2

Konfigurieren Sie eine Regel, die für Skype Raum Systeme v2 Geräte überprüft, die Anwendungsprobleme innerhalb der letzten Stunde kommuniziert haben.
1.  Wählen Sie die **Log-Suche**.

2.  Geben Sie die folgende Abfrage aus, und wählen Sie dann auf **Ausführen**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  Nachdem die Abfrage ausgeführt wird, wählen Sie **Alert**. Die Seite **Warnungsregel hinzufügen** wird geöffnet.

4.  Konfigurieren von Benachrichtigungseinstellungen mit den folgenden Informationen:<br>
    **Regelname:** Skype-Raum Systemen v2 Anwendung Fehler Benachrichtigung<br>
    **Beschreibung:** Liste der Geräte, die innerhalb der letzten Stunde ein Application-Problem aufgetreten ist<br>
    **Schweregrad:** Wichtige<br>
    **Abfrage:** Verwenden Sie die vorab aufgefüllten Search-Abfrage<br>
    **Zeitfenster:** 1 Stunde<br>
    **Benachrichtigungshäufigkeit:** 1 Stunde<br>
    **Anzahl der Ergebnisse:** Größer als 0<br>
    **E-Mail-Betreff:** Skype-Raum Systemen v2 Anwendung Fehler Benachrichtigung<br>
    **Empfänger:** Schließen Sie die e-Mail-Adressen mit Semikolons als Trennzeichen ein

5.  Wählen Sie **Speichern**aus.

Sie haben nun definierende Benachrichtigungen abgeschlossen. Sie können zusätzliche Warnungen mithilfe der obigen Beispielen definieren.

Wenn eine Warnung generiert wird, erhalten Sie eine e-Mail, in der die Geräte aufgelistet, die innerhalb der letzten Stunde ein Problem aufgetreten ist.

![Beispiel-OMS warnen, e-Mail] (../../media/Deploy_OMS_7.png "Beispiel-OMS warnen, e-Mail")

Sie verwenden eine Seite Benachrichtigungseinstellungen Ändern einer vorhandenen Warnungen Konfigurations zu deaktivieren oder entfernen Sie eine Benachrichtigung.

![OMS-Warnung Einstellungen] (../../media/Deploy_OMS_8.png "OMS-Warnung Einstellungen")

> [!NOTE]
> Sie müssen möglicherweise mithilfe das Azure Portal hinzufügen oder ändern Vorgänge Management Suite Benachrichtigungen, wenn Vorgänge Management Suite Arbeitsbereich Vorgänge Management Suite Benachrichtigungen in Azure erweitern konfiguriert ist. Weitere Informationen finden Sie unter [Extend-Benachrichtigungen vom OMS-Portal in Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).

## <a name="configure-all-devices-for-operations-management-suite"></a>Konfigurieren Sie aller Geräte für Vorgänge Management Suite
<a name="configure_all_devices"></a> Nachdem Dashboards und Benachrichtigungen konfiguriert sind, können Sie einrichten und Konfigurieren von Agents Vorgänge Management Suite auf allen Skype Raum Systemen v2 Geräten zum Abschluss der bereitstellungs von monitoring.

Obwohl Sie installieren und die Vorgänge Management Suite-Agents auf jedem Gerät manuell konfigurieren können, empfiehlt es sich, dass Sie vorhandene Bereitstellung Softwaretools und Methoden nutzen.

Wenn Sie Ihre Skype Raum Systemen v2 Geräte zum ersten Mal erstellen, möchten Sie möglicherweise die Vorgänge Management Suite-Agent-Setup und Konfiguration Schritte im Rahmen des Buildprozesses enthalten. Weitere Informationen finden Sie unter [Installieren des Agents über die Befehlszeile](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a>Bereitstellen von Operationen Management Suite-Agents mithilfe eines Gruppenrichtlinienobjekts

Wenn Sie vor der Implementierung von Operations Management Suite bereits Skype Raum Systemen v2 Geräte bereitgestellt, können Sie die bereitgestellten Skripts zum Einrichten und konfigurieren die Agents mithilfe von Gruppenrichtlinien für Active Directory.

1.  Erstellen Sie einen freigegebenen Netzwerkpfad, und erteilen Sie der Gruppe " **Domänencomputer** ".

2.  Laden Sie die 64-Bit-Version des Operations Management Suite-Agent für Windows aus<http://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrahieren Sie den Inhalt des Setup-Pakets in der Netzwerkfreigabe aus.
    1.  Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie die **MMASetup-AMD64.exe/c**
    2.  Geben Sie die Freigabe, die Sie gerade erstellt haben, und extrahieren Sie den Inhalt.

4.  Erstellen eines neuen Gruppenrichtlinienobjekts, und weisen Sie es mit der Organisationseinheit, in dem Skype Raum Systemen v2 Konten auf dem Computer gespeichert sind.

5.  PowerShell-Ausführungsrichtlinie zu konfigurieren:
    1.  Das neu erstellte Gruppenrichtlinienobjekt bearbeiten, und navigieren Sie zu Computerkonfiguration \\ Richtlinien \\ Administrative Vorlagen \\ Windows-Komponenten \\ Windows PowerShell
    2.  Aktivieren Sie die **Ausführung des Skripts zu aktivieren** , und legen Sie **Ausführungsrichtlinie** auf **Lokale Skripts zulassen**.

6.  Konfigurieren Sie das Startskript:
    1.  Kopieren Sie das folgende Skript, und speichern Sie es als Install-OMSAgent.ps1.
    2.  Ändern Sie die Parameter WorkspaceId, WorkspaceKey und SetupPath entsprechend Ihrer Konfiguration.
    3.  Das gleiche Gruppenrichtlinienobjekt bearbeiten, und navigieren Sie zu Computerkonfiguration \\ Richtlinien \\ Windows-Einstellungen \\ Skripts (Start/Herunterfahren)
    4.  Durch Doppelklicken Sie können Sie **beim Start**wählen, und wählen Sie dann die **PowerShell-Skripts**.
    5.  Wählen Sie **Dateien anzeigen**, und klicken Sie dann kopieren Sie die **Installation OMSAgent.ps1** -Datei in diesen Ordner.
    6.  Wählen Sie **Hinzufügen**und dann auf **Durchsuchen**.
    7.  Wählen Sie das ps1-Skript, die, das Sie soeben kopiert.

7.  Skype Raum Systemen v2 Geräte sollten installieren und konfigurieren den Microsoft-Monitoring-Agent mit der zweiten Neustart.


    ```
    # Install-OMSAgent.ps1
    <# 
    Date:        04/20/2018 
    Script:      Install-OMSAgent.ps1 
    Version:     1.0
    #> 
    
    # Set the parameters
    $WorkspaceId = "<your workspace id>"
    $WorkspaceKey = "<your workspace key>"
    $SetupPath = "\\Server\Share"
    
    $SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"
    
    # $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"
    
    # Start PowerShell logging
    Start-Transcript -Path C:\OMSAgentInstall.Log  
    
    # Check if the Microsoft Monitoring Agent is installed
    $mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'
    
    # Check if the Microsoft Monitoring agent is installed 
    if (!$mma)
    {
        #Install agent
        Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
    }
    
    # Check if the agent has a valid configuration
    $CheckOMS = $mma.GetCloudWorkspace($WorkspaceId).AgentId
    if (!$CheckOMS)
    {
        # Apply new configuration
        $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
        $mma.ReloadConfiguration()
    } 
    
    Stop-Transcript 
    
    ```
    
> [!NOTE]
> Sie können Sie den Artikel, [Verwaltung und Wartung des Protokolldateien Analytics-Agents](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) verweisen, wenn Sie einen Agent konfigurieren, mit einem anderen Arbeitsbereich zu verschieben oder Ändern von Proxyeinstellungen nach der Erstinstallation müssen.

## <a name="additional-solutions"></a>Zusätzliche Lösungen
<a name="Solutions"> </a>

Vorgänge Management Suite bietet integrierte Lösungen über seine [Lösungskatalog](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) , um weitere Sie Ihre Umgebung überwachen können. Es wird dringend empfohlen, Arbeitsbereich Vorgänge Management Suite sowie [Alert-Management](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) und [Agent Health](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) Lösungen hinzuzufügen.

![OMS-Ansichten] (../../media/Deploy_OMS_9.png "OMS-Ansichten")

> [!NOTE]
> Die Integrität der Agent-Lösung kann Ihnen veraltete oder fehlerhafte Vorgänge Management Suite-Agenten in Ihrer Umgebung identifizieren und die Alert-Management-Lösung finden Sie Informationen über die Warnungen, die innerhalb eines bestimmten Zeitraums ausgelöst worden sein.

## <a name="see-also"></a>Siehe auch

[Planen der Verwaltung von Skype Room System V2 mit OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Verwalten von Skype Room Systems v2-Geräten mit OMS](../../manage/skype-room-systems-v2/oms.md)
