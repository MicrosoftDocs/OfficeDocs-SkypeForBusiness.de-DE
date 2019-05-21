---
title: Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: In diesem Artikel wird erläutert, wie Sie die Verwaltung von Microsoft Teams rooms-Geräten in integrierter End-to-End-Weise mithilfe von Azure Monitor bereitstellen.
ms.openlocfilehash: d9f1a78d31fe6ef765fd43554337444533056114
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291500"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor

In diesem Artikel wird erläutert, wie Sie die integrierte End-to-End-Verwaltung von Microsoft Teams rooms-Geräten mithilfe des Azure Monitors einrichten und bereitstellen.

Sie können die Protokollanalyse in Azure Monitor konfigurieren, um grundlegende Telemetrie-und Benachrichtigungsfunktionen bereitzustellen, die Ihnen bei der Verwaltung von Besprechungsraum Geräten in Microsoft Teams helfen. Wenn Ihre Verwaltungslösung ausgereift ist, entscheiden Sie sich möglicherweise für die Bereitstellung zusätzlicher Daten-und Verwaltungsfunktionen, um eine detailliertere Ansicht der Verfügbarkeit und Leistung von Geräten zu erstellen.

Wenn Sie diesem Leitfaden folgen, können Sie ein Dashboard wie im folgenden Beispiel verwenden, um detaillierte Statusberichte für die Geräteverfügbarkeit, die Anwendungs-und Hardware Integrität sowie die Microsoft Teams rooms-Anwendung und die Versions Verteilung des Betriebssystems zu erhalten.

![Beispiel für eine Protokollanalyse Ansicht für Microsoft Teams] -Chatrooms (../media/Deploy-Azure-Monitor-1.png "Beispiel für eine Protokollanalyse Ansicht für Microsoft Teams") -Chatrooms

Allgemein müssen Sie die folgenden Aufgaben ausführen:


1.  [Überprüfen der Protokollanalyse Konfiguration](azure-monitor-deploy.md#validate_LogAnalytics)
2.  [Konfigurieren von Testgeräten für die Protokollanalyse-Verwaltungseinrichtung](azure-monitor-deploy.md#configure_test_devices)
3.  [Zuordnen benutzerdefinierter Felder](azure-monitor-deploy.md#Custom_fields)
4.  [Definieren der Ansichten von Microsoft Teams Rooms in der Protokollanalyse](azure-monitor-deploy.md#Define_Views)
5.  [Definieren von Benachrichtigungen](azure-monitor-deploy.md#Alerts)
6.  [Konfigurieren aller Geräte für die Überwachung](azure-monitor-deploy.md#configure_all_devices)
7.  [Konfigurieren zusätzlicher Azure Monitor-Lösungen](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Obwohl die Azure Monitor-Protokollanalyse bei minimaler Konfiguration einen Computer unter einem Windows-Betriebssystem überwachen kann, gibt es immer noch einige Microsoft Teams-Räume – bestimmte Schritte, die Sie ausführen müssen, bevor Sie mit der Bereitstellung von Agents für alle Microsoft Teams beginnen. Geräte für Räume.
> Wir empfehlen daher, dass Sie alle Konfigurationsschritte in der richtigen Reihenfolge für eine kontrollierte Einrichtung und Konfiguration durchführen. Die Qualität des Endergebnisses hängt stark von der Qualität der anfänglichen Konfiguration ab.

## <a name="validate-log-analytics-configuration"></a>Überprüfen der Protokollanalyse Konfiguration
<a name="validate_LogAnalytics"> </a>

Sie benötigen einen Protokollanalyse-Arbeitsbereich, um mit dem Sammeln von Protokollen von Microsoft Teams rooms-Geräten zu beginnen. Ein Arbeitsbereich ist eine eindeutige Protokollanalyse Umgebung mit eigenem Daten Repository, Datenquellen und Lösungen. Wenn Sie bereits über einen vorhandenen Protokollanalyse-Arbeitsbereich verfügen, können Sie ihn möglicherweise zum Überwachen der Microsoft Teams rooms-Bereitstellung verwenden, oder Sie können einen dedizierten Arbeitsbereich für die Protokollanalyse erstellen, der für die Überwachungsanforderungen Ihrer Microsoft Teams-Chatrooms spezifisch ist

Wenn Sie einen neuen Arbeitsbereich für die Protokollanalyse erstellen müssen, folgen Sie den Anweisungen im Artikel [Erstellen eines Protokollanalyse Arbeitsbereichs im Azure-Portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) .

> [!NOTE]
> Wenn Sie Protokollanalyse mit Azure Monitor verwenden möchten, benötigen Sie ein Active Azure-Abonnement. Wenn Sie nicht über ein Azure-Abonnement verfügen, können Sie als Ausgangspunkt [ein kostenloses Testabonnement](https://azure.microsoft.com/free) erstellen.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Konfigurieren von Protokollanalysen zum Sammeln von Microsoft Teams rooms-Ereignisprotokollen

Protokollanalyse sammelt nur Ereignisse aus den Windows-Ereignisprotokollen, die in den Einstellungen angegeben sind. Für jedes Protokoll werden nur die Ereignisse mit den ausgewählten severities erfasst.

Sie müssen Protokollanalyse konfigurieren, um die Protokolle zu sammeln, die zum Überwachen des Geräte-und Anwendungsstatus von Microsoft Teams rooms erforderlich sind. Microsoft Teams rooms-Geräte verwenden das Ereignisprotokoll des **Skype Room-Systems** .

Informationen zum Konfigurieren von Protokollanalysen zum Sammeln der Microsoft Teams rooms-Ereignisse finden Sie unter [Windows-Ereignisprotokoll-Datenquellen in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events) .

![Ereignisprotokolleinstellungen] (../media/Deploy-Azure-Monitor-2.png "Ereignisprotokolleinstellungen")

> [!IMPORTANT]
> Konfigurieren Sie die Windows-Ereignisprotokolleinstellungen, und geben Sie **Skype Room System** als Ereignisprotokollnamen ein, und aktivieren Sie dann die Kontrollkästchen **Fehler**, **Warnung**und **Informationen** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Konfigurieren von Testgeräten für die Azure-Überwachung
<a name="configure_test_devices"> </a>

Sie müssen die Protokollanalyse vorbereiten, damit Microsoft Teams rooms – verwandte Ereignisse überwacht werden können. Zunächst müssen Sie die Microsoft-Überwachungs-Agents nur für ein oder zwei Microsoft Teams rooms-Geräte bereitstellen, auf die Sie physischen Zugriff haben, und diese Testgeräte generieren einige Daten, und drücken Sie Sie in den Arbeitsbereich Log Analytics.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Installieren von Microsoft-Überwachungs-Agents zum Testen von Geräten

Stellen Sie den Microsoft-Überwachungs-Agent auf den Testgeräten bereit, indem Sie die Anweisungen unter [Verbinden von Windows-Computern mit dem Protokollanalyse Dienst in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)verwenden. Dieser Artikel enthält detaillierte Informationen zu den Schritten zum Bereitstellen von Microsoft Monitoring Agent für Windows, Anweisungen zum Abrufen der ***Arbeitsbereichs-ID*** für die Protokollanalyse und des ***Primärschlüssels*** zum Abrufen von Microsoft Teams rooms-Geräten, die mit verbunden sind. Ihre Azure Monitor-Bereitstellung und Schritte zum Überprüfen der Agentenkonnektivität zur Protokollanalyse Instanz.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Beispiele für Microsoft Teams rooms-Ereignisse generieren

Nachdem der Microsoft-Überwachungs-Agent auf den Testgeräten bereitgestellt wurde, stellen Sie sicher, dass die erforderlichen Ereignisprotokolldaten von Azure Monitor erfasst werden.

> [!NOTE]
> Starten Sie das Gerät nach der Installation des Microsoft-Überwachungs-Agents neu, und stellen Sie sicher, dass die Microsoft Teams rooms-Besprechungs-App gestartet wird, damit Sie neue Ereignisse im Ereignisprotokoll generieren kann.

1.  Melden Sie sich beim [Microsoft Azure-Portal](https://portal.azure.com) an, und wechseln Sie zur Protokollanalyse, und wählen Sie Ihren Arbeitsbereich aus.

2.  Listen Sie die Heartbeat-Ereignisse auf, die von einem Microsoft Teams rooms-Gerät generiert wurden:
    1.  Wählen Sie Ihren Arbeitsbereich aus, und wechseln Sie zu **Protokolle** , und verwenden Sie eine Abfrage, um die Heartbeat-Einträge abzurufen, die die benutzerdefinierten Felder für Microsoft Teams-Chatrooms enthalten.
    2.  Beispielabfrage:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Stellen Sie sicher, dass die Abfrageprotokoll Datensätze zurückgibt, die Ereignisse enthalten, die von der Microsoft Teams rooms-Besprechungs-App generiert wurden.

4.  Generieren Sie ein Hardwareproblem, und überprüfen Sie, ob die erforderlichen Ereignisse in Azure Log Analytics protokolliert werden.
    1.  Ziehen Sie eines der Peripheriegeräte auf dem Microsoft Teams-System testen. Hierbei kann es sich um die Kamera-, Freisprech-, Mikrofon-oder Front Raum Anzeige handeln.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll in Azure Log Analytics ausgefüllt wird.
    3.  Verwenden einer Abfrage zum Auflisten von Hardwarefehler Ereignissen:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Generieren Sie ein Anwendungsproblem, und überprüfen Sie, ob die erforderlichen Ereignisse protokolliert werden.
    1.  Ändern Sie die Anwendungskonfiguration von Microsoft Teams rooms, und geben Sie ein falsches SIP-Adresse/Kennwort-Paar (Session Initiation Protocol) ein.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll in Azure Log Analytics ausgefüllt wird.
    3.  Verwenden einer Abfrage zum Auflisten von Anwendungsfehler Ereignissen:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Diese Beispiel Ereignisprotokolle sind erforderlich, bevor benutzerdefinierte Felder konfiguriert werden können. Fahren Sie nicht mit dem nächsten Schritt fort, bis Sie die erforderlichen Ereignisprotokolle gesammelt haben.

## <a name="map-custom-fields"></a>Zuordnen benutzerdefinierter Felder
<a name="Custom_fields"> </a>

Sie verwenden benutzerdefinierte Felder, um bestimmte Daten aus den Ereignisprotokollen zu extrahieren. Sie müssen benutzerdefinierte Felder definieren, die später für Ihre Kacheln, Dashboard-Ansichten und Benachrichtigungen verwendet werden. Lesen Sie [benutzerdefinierte Felder in der Protokollanalyse](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) , und machen Sie sich mit den Konzepten vertraut, bevor Sie mit dem Erstellen Ihrer benutzerdefinierten Felder beginnen.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierten Felder aus den erfassten Ereignisprotokollen zu extrahieren:

1.  Melden Sie sich beim [Microsoft Azure-Portal](https://portal.azure.com) an, und wechseln Sie zur Protokollanalyse, und wählen Sie Ihren Arbeitsbereich aus.

2. Listen Sie die Ereignisse auf, die von einem Microsoft Teams rooms-Gerät generiert wurden:
   1.  Wechseln Sie zu **Protokolle** , und verwenden Sie eine Abfrage, um die Datensätze abzurufen, die das benutzerdefinierte Feld aufweisen.
   2.  Beispielabfrage:`Event | where Source == "SRS-App" and EventID == 2000`

3. Wählen Sie einen der Datensätze aus, wählen Sie die Schaltfläche links aus, und starten Sie den Feld Extraktions-Assistenten.
4. Markieren Sie die Daten, die Sie aus dem RenderedDescription extrahieren möchten, und geben Sie einen Feld Titel ein. Die Feldnamen, die Sie verwenden sollten, werden in Tabelle 1 bereitgestellt.

   ![Benutzerdefinierte Felddefinition] (../media/Deploy-Azure-Monitor-4.png "Benutzerdefinierte Felddefinition")

5. Verwenden Sie die in *Tabelle 1*gezeigten Zuordnungen. Log Analytics fügt die ** \_CF** -Zeichenfolge beim Definieren des neuen Felds automatisch an.

> [!IMPORTANT]
> Beachten Sie, dass bei allen JSON-und Log Analytics-Feldern die Groß-/Kleinschreibung beachtet wird.
> 
> Achten Sie auf die Abfragen, die für jedes benutzerdefinierte Feld in der folgenden Tabelle erforderlich sind. Sie müssen die richtigen Abfragen für die Protokollanalyse verwenden, um benutzerdefinierte Feldwerte erfolgreich zu extrahieren.
> 
 ![Benutzerdefinierte Felddefinition] (../media/Deploy-Azure-Monitor-5.png "Benutzerdefinierte Felddefinition")

**Tabelle 1**

| **JSON-Feld**                   | **Benutzerdefiniertes Feld ' Protokollanalyse '** | **Ereigniskennung** | **Abfrage, die mit der Extraktion verwendet werden soll**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Beschreibung                      | SRSEventDescription         | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| OS                               | SRSOSVersion                | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| Version des Betriebssystems                        | SRSOSLongVersion            | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 2000 |
| Konferenz Mikrofon Status     | SRSConfMicrophoneStatus     | **3001**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 3001 |
| Konferenz Lautsprecher Status        | SRSConfSpeakerStatus        | **3001**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 3001 |
| Standardlautsprecher Status           | SRSDefaultSpeakerStatus     | **3001**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 3001 |
| Kamerastatus                    | SRSCameraStatus             | **3001**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 3001 |
| Anzeigestatus der Vorderseite des Raums     | SRSFORDStatus               | **3001**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 3001 |
| Bewegungs Sensor Status             | SRSMotionSensorStatus       | **3001**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 3001 |
| HDMI-Aufnahmestatus               | SRSHDMIIngestStatus         | **3001**     | Ereignis \| , bei dem Source = = "SRS-app" und Ereignis Ereignis = = 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Definieren der Ansichten von Microsoft Teams Rooms in der Protokollanalyse
<a name="Define_Views"> </a>

Nachdem Daten gesammelt und benutzerdefinierte Felder zugeordnet wurden, können Sie mit dem Ansicht-Designer ein Dashboard entwickeln, das verschiedene Kacheln zum Überwachen von Microsoft Teams rooms-Ereignissen enthält. Erstellen Sie mit dem Ansicht-Designer die folgenden Kacheln. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Ansichten mithilfe des Ansicht-Designers in der Protokollanalyse](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) .

> [!NOTE]
> Die vorherigen Schritte in diesem Leitfaden sollten für die ordnungsgemäße Funktionsweise der Dashboard-Kacheln abgeschlossen sein.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Erstellen eines Microsoft Teams rooms-Dashboards mithilfe der Import-Methode

Sie können ein Microsoft Teams rooms-Dashboard importieren und Ihre Geräte schnell überwachen. Führen Sie die folgenden Schritte aus, um das Dashboard zu importieren:

1.  Rufen Sie die [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) -dashboarddatei ab.
2.  Melden Sie sich beim [Microsoft Azure-Portal](https://portal.azure.com) an, und wechseln Sie zur Protokollanalyse, und wählen Sie Ihren Arbeitsbereich aus.
3.  Öffnen Sie den **Ansicht-Designer**.
4.  Wählen Sie **importieren**aus, und wählen Sie dann die Datei **SkypeRoomSystems_v2. omsview** aus.
5.  Wählen Sie **Speichern**aus.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Manuelles Erstellen eines Microsoft Teams rooms-Dashboards

Sie können auch ein eigenes Dashboard erstellen und nur die Kacheln hinzufügen, die Sie überwachen möchten.

#### <a name="configure-the-overview-tile"></a>Konfigurieren der Kachel "Übersicht"

1.  Öffnen Sie den **Ansicht-Designer**.
2.  Wählen Sie **Übersicht-Kachel**aus, und wählen Sie dann im Katalog **zwei Zahlen** aus.
3.  Benennen Sie die **Microsoft Teams**-Kachel Räume.
4.  Definieren der **ersten Kachel**:<br>
    **Legende:** Geräte, die mindestens einmal innerhalb des letzten Monats einen Heartbeat gesendet haben<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definieren Sie die **zweite Kachel**:<br>
    **Legende:** Aktive Geräte, die innerhalb der letzten Stunde einen Heartbeat gesendet haben<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Wählen Sie über **nehmen**aus.

### <a name="create-a-tile-that-displays-active-devices"></a>Erstellen einer Kachel, auf der aktive Geräte angezeigt werden

1.  Wählen Sie **Dashboard anzeigen** aus, um das Hinzufügen Ihrer Kacheln zu beginnen.
2.  Wählen Sie im Katalog die **Nummer & Liste** aus.
3.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Heartbeat-Status<br>
    **Neue Gruppe:** Ausgewählten
4.  Definieren Sie die **Kachel** Eigenschaften:<br>
    **Legende:** Aktive Geräte (in den letzten 20 Minuten gesendeter Heartbeat)<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definieren Sie die **Listen** Eigenschaften:<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definieren von **Spaltentiteln**:<br>
    **Name:** Computer Name<br>
    **Wert:** Letzter Heartbeat
7.  **Navigations Abfrage**definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie über **nehmen**und dann **Schließen**aus.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Erstellen einer Kachel, auf der Geräte mit Verbindungsproblemen angezeigt werden

1.  Wählen Sie im Katalog **Number & List** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kachel** Eigenschaften:<br>
    **Legende:** Inaktive Geräte (in den letzten 20 Minuten wurde keine Heartbeat-Nachricht gesendet)<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definieren Sie die **Listen** Eigenschaften:<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definieren von **Spaltentiteln**:<br>
    **Name:** Computer Name<br>
    **Wert:** Letzter Heartbeat
6.  **Navigations Abfrage**definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie über **nehmen**und dann **Schließen**aus.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Erstellen einer Kachel, die Geräte mit einem Hardwarefehler anzeigt

1.  Wählen Sie im Katalog **Number & List** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Hardware Status<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Kachel** Eigenschaften:<br>
    **Legende:** Geräte, die in der letzten Stunde einen Hardwarefehler auftraten<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listen** Eigenschaften:<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren von **Spaltentiteln**:<br>
    **Name:** Computer Name<br>
    **Wert:** Letzter Fehler
6.  **Navigations Abfrage**definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie über **nehmen**und dann **Schließen**aus.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Erstellen einer Kachel, in der die Betriebs System Versionen von Microsoft Teams rooms angezeigt werden

1.  Wählen Sie im Katalog die **Liste Donut-&** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Details zum Betriebs System<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Header** Eigenschaften:<br>
    **Titel:** Betriebs System Versionen<br>
    Unter **Titel:** Geräte mit bestimmten Betriebssystemversionen
4.  Definieren Sie **** die Donut-Eigenschaften:<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Zentrieren von Text:** Geräte<br>
    **Operation:** Summe
5.  Definieren Sie die **Listen** Eigenschaften.<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Diagramm ausblenden:** Ausgewählten<br>
    **Aktivieren von Sparklines:** Nicht ausgewählt
6.  Definieren von **Spaltentiteln**<br>
    **Name:** Computer Name<br>
    **Wert:** Leer lassen
7.  **Navigations Abfrage**definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie über **nehmen** und dann **Schließen**aus.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Erstellen einer Kachel, in der Microsoft Teams rooms-Anwendungsversionen angezeigt werden

1.  Wählen Sie im Katalog die **Liste Donut-&** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Anwendungsdetails für Microsoft Teams rooms<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Header** Eigenschaften:<br>
    **Titel:** Anwendungsversionen<br>
    Unter **Titel:** Geräte, auf denen bestimmte Anwendungsversionen ausgeführt werden
4.  Definieren Sie **** die Donut-Eigenschaften:<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Zentrieren von Text:** Geräte<br>
    **Operation:** Summe
5.  Definieren Sie die **Listen** Eigenschaften.<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Diagramm ausblenden:** Ausgewählten<br>
    **Aktivieren von Sparklines:** Nicht ausgewählt
6.  Definieren von **Spaltentiteln**<br>
    **Name:** Computer Name<br>
    **Wert:** Leer lassen
7.  **Navigations Abfrage**definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie über **nehmen** und dann **Schließen**aus.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Erstellen einer Kachel, die Geräte mit einem Anwendungsfehler anzeigt

1.  Wählen Sie im Katalog **Number & List** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kachel** Eigenschaften.<br>
    **Legende:** Geräte, die in der letzten Stunde einen Anwendungsfehler erlebt haben<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listen** Eigenschaften.<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren von **Spaltentiteln**<br>
    **Name:** Computer Name<br>
    **Wert:** Letzter Fehler
6.  **Navigations Abfrage**definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie über **nehmen** und dann **Schließen**aus.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Erstellen einer Kachel, auf der neu gestartete Geräte angezeigt werden

1.  Wählen Sie im Katalog **Number & List** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kachel** Eigenschaften.<br>
    **Legende:** Geräte, auf denen die Anwendung in den letzten 24 Stunden neu gestartet wurde, und die Anzahl der Neustarts<br>
    **Kachelabfrage: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listen** Eigenschaften.<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definieren von **Spaltentiteln**<br>
    **Name:** Computer Name<br>
    **Wert:** Anzahl der Neustarts
6.  **Navigations Abfrage**definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie über **nehmen** und dann **Schließen**aus.
8.  Wählen Sie **Speichern** aus, um das Dashboard zu speichern.

Sie haben nun die Erstellung ihrer Ansichten abgeschlossen.

## <a name="configure-alerts-in-azure-monitor"></a>Konfigurieren von Benachrichtigungen in Azure Monitor
<a name="Alerts"> </a>

Azure Monitor kann Benachrichtigungen auslösen, damit die Administratoren benachrichtigt werden, wenn eine Microsoft Teams rooms-Konsole auf ein Problem stößt.

Azure Monitor umfasst einen integrierten Warnungs Mechanismus, der in regelmäßigen Abständen über geplante Protokoll suchen ausgeführt wird. Wenn die Ergebnisse der Protokollsuche einigen bestimmten Kriterien entsprechen, wird ein Warnungseintrag erstellt.

Die Regel kann dann automatisch eine oder mehrere Aktionen ausführen, um Sie proaktiv über die Benachrichtigung zu informieren oder einen anderen Prozess aufzurufen. Mögliche Optionen mit Benachrichtigungen sind:
-   Senden einer e-Mail
-   Aufrufen eines externen Prozesses über eine HTTP POST-Anforderung
-   Starten eines runbooks im Azure-Automatisierungs Dienst

Weitere Informationen zu den Warnungen in Azure Monitor finden Sie unter [Protokoll Benachrichtigungen in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) .

> [!NOTE]
> Die folgenden Beispiele senden e-Mail-Benachrichtigungen, wenn ein Microsoft Teams rooms-Gerät einen Hardware-oder Anwendungsfehler generiert.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Konfigurieren einer e-Mail-Benachrichtigung für Microsoft Teams rooms-Hardwareprobleme

Konfigurieren Sie eine Warnungsregel, die auf Geräte von Microsoft Teams rooms überprüft, die innerhalb der letzten Stunde Hardwareprobleme aufgetreten sind.
1.  Melden Sie sich beim [Microsoft Azure-Portal](https://portal.azure.com) an, und wechseln Sie zur Protokollanalyse, und wählen Sie Ihren Arbeitsbereich aus.

2. Navigieren Sie zu Ihrem Arbeitsbereich für die Protokollanalyse, und wählen Sie **Benachrichtigungen** und dann **neue Warnungsregel** aus.

3. Wählen Sie **Bedingung hinzufügen** und dann **benutzerdefinierte Protokollsuche** aus.

4.  Geben Sie die folgende Abfrage in das Textfeld Suchabfrage ein.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Konfigurieren der Warnungs Logik Einstellungen:<br>
    **Basierend auf:** Anzahl der Ergebnisse<br>
    **Bedingung:** Größer als<br>
    **Schwelle:** 0<br>

6. Konfigurieren Sie Evaluierungs Einstellungen, und wählen Sie **Fertig**aus: <br>
    **Zeitraum (in Minuten):** 60<br>
    **Häufigkeit (in Minuten):** 60<br>

7. Konfigurieren von Aktionsgruppen:
    1.  Wählen Sie **neu erstellen** aus.
    2.  Geben Sie geeignete Namen für die Felder *Aktionsgruppenname* und Kurzname an. **
    3.  Geben Sie einen eindeutigen *Aktionsnamen* an, wählen Sie **e-Mail/SMS/Push/Voice**aus, und wählen Sie dann **Details bearbeiten**aus.
    4.  Aktivieren Sie das Kontrollkästchen e-Mail, und geben Sie die e-Mail-Adresse der Person oder Gruppe an, die die Benachrichtigungen erhalten soll.
    5.  Sie können auch Ihre Telefonnummer angeben, um mit SMS, einem Sprachanruf oder beides benachrichtigt zu werden.
    6. Wählen Sie **OK**aus.

8. **Passen Sie Aktionen** an, wenn Sie die Betreffzeile der Benachrichtigungs-e-Mails außer Kraft setzen möchten.

9. Geben Sie einen Regelnamen und eine Beschreibung an.<br>
    **Regel Name:** Microsoft Teams rooms-Hardware Fehler Warnung<br>
    **Beschreibung:** Liste der Geräte, die innerhalb der letzten Stunde auf ein Hardwareproblem gestoßen sind<br>

10. Wählen Sie den gewünschten Schweregrad aus, und stellen Sie sicher, dass die Regel aktiviert ist.

11. Wählen Sie **Warnungsregel erstellen**aus.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Konfigurieren einer e-Mail-Benachrichtigung für Microsoft Teams rooms-Anwendungsprobleme

Wiederholen Sie den Vorgang, aber verwenden Sie die folgende Abfrage, um Geräte aufzulisten, die innerhalb der letzten Stunde auf Anwendungsprobleme gestoßen sind.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Sie haben nun die Definition von Benachrichtigungen abgeschlossen. Mithilfe der obigen Beispiele können Sie zusätzliche Benachrichtigungen definieren.

Wenn eine Benachrichtigung generiert wird, erhalten Sie eine e-Mail mit einer Liste der Geräte, die innerhalb der letzten Stunde auf ein Problem gestoßen sind.

![Beispiel für eine Azure Monitor-Warnungs-e-Mail] (../media/Deploy-Azure-Monitor-6.png "Beispiel für eine Azure Monitor-Warnungs-e-Mail")

## <a name="configure-all-devices-for-azure-monitoring"></a>Konfigurieren aller Geräte für die Azure-Überwachung
<a name="configure_all_devices"></a> Nachdem die Dashboards und Benachrichtigungen konfiguriert sind, können Sie den Microsoft-Überwachungs-Agent auf allen Microsoft Teams rooms-Geräten einrichten und konfigurieren, um die Überwachungs Bereitstellung abzuschließen.

Obwohl Sie den Microsoft-Überwachungs-Agent manuell auf jedem Gerät installieren und konfigurieren können, empfehlen wir dringend, vorhandene Softwarebereitstellungstools und-Methoden zu nutzen.

Wenn Sie Ihre Microsoft Teams rooms-Geräte zum ersten Mal erstellen, möchten Sie möglicherweise die Setup-und Konfigurationsschritte des Microsoft-Überwachungs-Agents als Teil des Buildprozesses einbeziehen. Weitere Informationen finden Sie unter [Installieren des Agents über die Befehlszeile](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Bereitstellen des Microsoft-Überwachungs-Agents mithilfe eines Gruppenrichtlinienobjekts (GPO)

Wenn Sie Ihre Microsoft Teams rooms-Geräte bereits bereitgestellt haben, bevor Sie die Azure-Überwachung implementieren, können Sie das bereitgestellte Skript verwenden, um die Agents mithilfe von Active Directory-Gruppenrichtlinienobjekten einzurichten und zu konfigurieren.

1.  Erstellen Sie einen freigegebenen Netzwerkpfad, und erteilen Sie den Lesezugriff auf die Gruppe " **Domänencomputer** ".

2.  Laden Sie die 64-Bit-Version des Microsoft-Überwachungs-Agents für Windows von herunter.<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrahieren Sie den Inhalt des Setuppakets in die Netzwerkfreigabe.
    1.  Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie dann **MMASetup-amd64. exe/c aus.**
    2.  Geben Sie die soeben erstellte Freigabe an, und extrahieren Sie den Inhalt.

4.  Erstellen Sie ein neues Gruppenrichtlinienobjekt, und weisen Sie es der Organisationseinheit zu, in der sich die Computerkonten von Microsoft Teams Rooms befinden.

5.  Konfigurieren der PowerShell-Ausführungsrichtlinie:
    1.  Bearbeiten Sie das neu erstellte Gruppenrichtlinienobjekt, und navigieren Sie \\ zu \\ den Computer \\ Konfigurationsrichtlinien \\ administrative Vorlagen Windows-Komponenten Windows PowerShell
    2.  Aktivieren **Sie die Skriptausführung** aktivieren, und setzen Sie die **Ausführungsrichtlinie** so, dass **lokale Skripts zulässig**sind.

6.  Konfigurieren des Startskripts:
    1.  Kopieren Sie das folgende Skript, und speichern Sie es als install-MMAgent. ps1.
    2.  Ändern Sie die Parameter für die Workspace-, WorkspaceKey-und SetupPath, um ihrer Konfiguration zu entsprechen.
    3.  Bearbeiten desselben Gruppenrichtlinienobjekts und navigieren zu den Windows \\ - \\ Einstellungs \\ Skripts für Computer Konfigurationsrichtlinien (Start/Shutdown)
    4.  Doppelklicken Sie auf **Start**, und wählen Sie dann **PowerShell-Skripts**aus.
    5.  Wählen Sie **Dateien anzeigen**aus, und kopieren Sie dann die Datei **install-MMAgent. ps1** in diesen Ordner.
    6.  Wählen Sie **Hinzufügen**und dann **Durchsuchen**aus.
    7.  Wählen Sie das ps1-Skript aus, das Sie soeben kopiert haben.

7.  Microsoft Teams rooms-Geräte sollten den Microsoft-Überwachungs-Agent beim zweiten Neustart installieren und konfigurieren.

```
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> Sie können auf den Artikel [Verwalten und Verwalten des Log Analytics-Agents](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) verweisen, wenn Sie einen Agenten neu konfigurieren, in einen anderen Arbeitsbereich verschieben oder Proxyeinstellungen nach der ersten Installation ändern müssen.

## <a name="additional-solutions"></a>Weitere Lösungen
<a name="Solutions"> </a>

Azure Monitor bietet integrierte Verwaltungslösungen über seinen [Lösungskatalog](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) , damit Sie Ihre Umgebung weiter überwachen können. Wir empfehlen dringend, dass Sie Ihrem Arbeitsbereich auch [Warnungsverwaltung](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) und [Azure Log Analytics-Agent](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) -Integritäts Lösungen hinzufügen.

> [!NOTE]
> Die Lösung für den Agentenstatus kann Ihnen dabei helfen, veraltete oder beschädigte Microsoft-Überwachungs-Agents in Ihrer Umgebung zu identifizieren, und die Warnungs Verwaltungslösung enthält Details zu den Benachrichtigungen, die innerhalb eines bestimmten Zeitraums ausgelöst wurden.

## <a name="see-also"></a>Siehe auch

[Planen der Verwaltung von Microsoft Teams Rooms mit Azure Monitor](azure-monitor-plan.md)

[Verwalten von Microsoft Teams rooms-Geräten mit Azure Monitor](azure-monitor-manage.md)
