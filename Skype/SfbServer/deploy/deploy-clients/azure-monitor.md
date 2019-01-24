---
title: Bereitstellen von Skype Raum v2 systemverwaltung mit Azure Monitor
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: In diesem Artikel wird erläutert, wie Verwaltung von Skype Raum Systemen v2 Geräte in Azure Monitor mit integrierten, End-to-End-Weise bereitstellen.
ms.openlocfilehash: 6a90f5b1dcbbdbab9c4149717e16a01c3a5f5ba1
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "29448470"
---
# <a name="deploy-skype-room-systems-v2-management-with-azure-monitor"></a>Bereitstellen von Skype Raum v2 systemverwaltung mit Azure Monitor

In diesem Artikel wird erläutert, wie einrichten und Bereitstellen von integrierte, End-to-End-Verwaltung von Skype Raum Systemen v2 Geräten mithilfe von Azure überwachen.

Sie können Log Analytics in Azure Bildschirm aus, geben Sie grundlegende Telemetrie konfigurieren, und Warnungen, die Ihnen helfen verwalten Skype meeting Room Geräte. Der Management-Lösung Laufe der Zeit, empfiehlt es sich zum Bereitstellen von zusätzlichen Daten und Management-Funktionen für eine ausführlichere Ansicht des Geräts Verfügbarkeit und Leistung zu erstellen.

Wie im folgenden Beispiel wird ein Dashboard können Sie anhand dieses Handbuchs detaillierten Status für das Gerät Verfügbarkeit, Anwendung und Hardware-Integrität und Skype Raum Systemen v2 Anwendung und Betriebssystem Version Verteilung reporting abzurufen.

![Beispiel Protokoll Analytics-Ansicht für SRS v2] (../../media/Deploy-Azure-Monitor-1.png "Beispiel Protokoll Analytics-Ansicht für SRS v2")

Allgemein müssen Sie die folgenden Aufgaben ausführen:


1.  [Überprüfen der Konfiguration des Protokolls Analytics](azure-monitor.md#validate_LogAnalytics)
2.  [Konfigurieren von Testgeräten für Protokoll Analytics-Einrichtung](azure-monitor.md#configure_test_devices)
3.  [Zuordnen benutzerdefinierter Felder](azure-monitor.md#Custom_fields)
4.  [Definieren von Skype Raum Systemen v2 Ansichten im Protokoll Analytics](azure-monitor.md#Define_Views)
5.  [Definieren von Warnungen](azure-monitor.md#Alerts)
6.  [Konfigurieren Sie aller Geräte für die Überwachung](azure-monitor.md#configure_all_devices)
7.  [Konfigurieren von zusätzlichen Azure Monitor-Lösungen](azure-monitor.md#Solutions)

> [!IMPORTANT]
> Obwohl mit minimaler Konfiguration Azure Monitor Protokoll Analytics einen Computer mit einem Windows-Betriebssystem überwachen können, sind noch einige Skype Raum Systeme v2-spezifische Schritte, die Sie vor Beginn der Bereitstellung von Agents für alle Skype Raum Systeme durchführen müssen Geräte.
> Aus diesem Grund empfiehlt es sich, dass Sie in der richtigen Reihenfolge für eine gesteuerte Setup und Konfiguration alle Konfigurationsschritte ausführen. Die Qualität des Ergebnisses End hängt die Qualität der Erstkonfiguration sehr viel.

## <a name="validate-log-analytics-configuration"></a>Überprüfen der Konfiguration des Protokolls Analytics
<a name="validate_LogAnalytics"> </a>

Sie benötigen einen Protokoll Analytics Arbeitsbereich zum Erfassen von Protokollen von Skype Raum Systemen v2 Geräten zu starten. Ein Arbeitsbereich ist eine eindeutige Protokoll Analytics-Umgebung mit einem eigenen Daten-Repository, Datenquellen und -Lösungen. Wenn Sie bereits einen vorhandenen Protokoll Analytics Arbeitsbereich verfügen, können Sie es zum Überwachen der Skype Raum Systemen v2-bereitstellungs verwenden oder Alternativ erstellen einen dedizierten Protokoll Analytics Arbeitsbereich bestimmte auf Ihre Skype Raum Systemen v2 monitoring Bedürfnisse.

Wenn Sie ein neues Protokoll Analytics Workspace erstellen müssen, führen Sie die Schritte im Artikel [Erstellen eines Arbeitsbereichs Protokoll Analytics im Azure-portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Um Protokolldateien Analytics mit Azure Monitor verwenden, müssen Sie ein aktives Azure-Abonnement verfügen. Wenn Sie nicht über ein Azure-Abonnement verfügen, können Sie [eine kostenlose Testversion](https://azure.microsoft.com/free) als Ausgangspunkt erstellen.

### <a name="configure-log-analytics-to-collect-skype-room-systems-v2-event-logs"></a>Konfigurieren von Protokolldateien Analytics Skype Raum Systemen v2 Ereignisprotokolle erfassen

Protokoll Analytics sammelt Ereignisse nur aus der Windows-Ereignisprotokolle, die in den Einstellungen angegeben sind. Für jedes Protokoll werden nur die Ereignisse mit der ausgewählten Schweregrade erfasst.

Sie müssen so konfigurieren Sie Log Analytics, um die Protokolle erforderlich, um die Überwachung Skype Raum Systemen v2 Geräte- und Status gespeichert. Skype-Chatroom-Systemen v2 Geräten verwenden **Skype Raum** Systemereignisprotokoll.

Protokoll Analytics erfassen die Skype Raum Systemen v2 Ereignisse konfigurieren finden Sie in [Windows-Ereignisprotokoll-Datenquellen in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Ereignisprotokoll-Einstellungen] (../../media/Deploy-Azure-Monitor-2.png "Ereignisprotokoll-Einstellungen")

> [!IMPORTANT]
> Konfigurieren Sie der Einstellungen für die Windows-Ereignisprotokoll und geben Sie **Skype Raum System** als Ereignisprotokoll ein, und wählen Sie dann das Kontrollkästchen **Fehler**, **Warnung**und **Informationen** aus.

## <a name="configure-test-devices-for-azure-monitoring"></a>Konfigurieren von Testgeräten für die Überwachung von Azure
<a name="configure_test_devices"> </a>

Sie müssen vorbereiten Protokoll Analytics Skype Raum Systemen v2-bezogenen Ereignisse überwachen können. Zunächst müssen Sie nur ein oder zwei Skype Raum Systemen v2 Geräte, die Ihnen Zugang zu den Microsoft-Monitoring-Agenten, und erhalten die Testgeräte einige Daten zu generieren und schieben Sie ihn in den Protokolldateien Analytics Arbeitsbereich.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Installieren von Microsoft-Monitoring-Agents zum Testen von Geräten

Bereitstellen des Microsoft-Monitoring-Agents Testgeräte mithilfe der Anweisungen unter [an den Log Analytics-Dienst in Azure-Computern mit Windows eine Verbindung herstellen](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Dieser Artikel enthält detaillierte Informationen zu den Schritten für die Bereitstellung von Microsoft Monitoring-Agent für Windows, Informationen zum Beziehen der Log Analytics ***Workspace-ID*** und der ***Primärschlüssel*** für Skype Raum Systemen v2 Geräte erhalten möchten, die mit verbunden Ihrer Bereitstellung auf Azure Monitor und Schritte zum Agentkonnektivität zu Protokoll Analytics-Instanz zu überprüfen.

### <a name="generate-sample-skype-room-systems-events"></a>Beispiel Skype Raum Systeme Ereignisse generieren

Nachdem Sie der Microsoft-Monitoring-Agent auf den Testgeräten bereitgestellt wird, stellen Sie sicher, dass die erforderlichen Ereignisprotokolldaten von Azure Monitor gesammelt werden.

> [!NOTE]
> Starten Sie das Gerät neu, nach der Installation des Microsoft-Monitoring-Agents, und stellen Sie sicher, dass Skype Raum Systemen v2 Besprechung app gestartet wird,, sodass sie neue Ereignisse in das Ereignisprotokoll generieren kann.

1.  Melden Sie sich am [Microsoft Azure-Portal](https://portal.azure.com) und wechseln Sie zur Analyse der Protokolldatei, und wählen Sie den Arbeitsbereich.

2.  Die Heartbeat-Ereignissen, die von einem Skype Raum Systemen v2 Gerät aufgelistet:
    1.  Wählen Sie den Arbeitsbereich und wechseln Sie zur **Protokolle** und verwenden Sie eine Abfrage, um die Heartbeat-Datensätze abzurufen, die die benutzerdefinierten Feldern für SRS v2 müssen.
    2.  Beispielabfrage:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Stellen Sie sicher, dass die Abfrage Datensätze zurückgibt, die von der app Skype Raum Systemen v2 Besprechungen generierten Ereignisse enthalten.

4.  Generiert ein Hardwareproblem, und überprüfen Sie, dass die erforderlichen Ereignisse in Azure Protokoll Analytics angemeldet sind.
    1.  Trennen Sie eine der Geräte auf den Test Skype Raum Systemen v2 System. Dies könnte die Kamera, Freisprechtelefon, Mikrofon oder Vordergrund Raum anzeigen
    2.  Warten Sie 10 Minuten für das Ereignisprotokoll in Azure Protokoll Analytics aufgefüllt werden.
    3.  Verwenden einer Abfrage zu Liste Hardwareereignisse Fehler:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Generieren eines Problems Anwendung, und überprüfen Sie, ob die erforderlichen Ereignisse protokolliert werden.
    1.  Ändern Sie Skype-Chatroom-Systemen v2 Anwendungskonfiguration, und geben Sie eine falsche Session Initiation Protocol (SIP) Adresse/Kennwort-Paar.
    2.  Warten Sie 10 Minuten für das Ereignisprotokoll in Azure Protokoll Analytics aufgefüllt werden.
    3.  Verwenden Sie eine Abfrage Liste Anwendungsereignisse Fehler:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Diese Beispiel Ereignisprotokolle sind erforderlich, bevor benutzerdefinierte Felder konfiguriert werden können. Fortfahren Sie nicht mit dem nächsten Schritt, bis Sie die erforderlichen Ereignisprotokolle gesammelt haben.

## <a name="map-custom-fields"></a>Zuordnen benutzerdefinierter Felder
<a name="Custom_fields"> </a>

Sie können benutzerdefinierte Felder verwenden, um bestimmte Daten aus den Ereignisprotokollen zu extrahieren. Sie müssen benutzerdefinierte Felder definieren, die später mit Kacheln, Dashboard-Ansichten und Warnungen verwendet wird. Finden Sie unter [benutzerdefinierte Felder im Protokoll Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) , und machen Sie sich mit den Konzepten vertraut, bevor Sie die benutzerdefinierten Felder erstellen.

Gehen Sie folgendermaßen vor, um die benutzerdefinierten Felder aus den aufgezeichneten Ereignisprotokollen zu extrahieren:

1.  Melden Sie sich am [Microsoft Azure-Portal](https://portal.azure.com) und wechseln Sie zur Analyse der Protokolldatei, und wählen Sie den Arbeitsbereich.

2. Die von einem Skype Raum Systemen v2 Gerät generierten Ereignisse aufgelistet:
   1.  Besuchen Sie **Protokolle (klassisch)** und verwenden Sie eine Abfrage, um die Datensätze abzurufen, die das benutzerdefinierte Feld.
   2.  Beispielabfrage:`Event | where Source == "SRS-App" and EventID == 2000`

3. Wählen Sie einen der Einträge aus, wählen Sie die Schaltfläche auf der linken Seite, und starten Sie im Feld Extraction-Assistent.

   ![Feld Extraction-Assistent] (../../media/Deploy-Azure-Monitor-3.png "Feld Extraction-Assistent")

4. Markieren Sie die Daten aus der RenderedDescription extrahieren, und geben Sie einen Titel Feld möchten. In Tabelle 1 werden die Namen der Felder, die Sie verwenden sollten, bereitgestellt.

   ![Definition für ein benutzerdefiniertes Feld] (../../media/Deploy-Azure-Monitor-4.png "Definition für ein benutzerdefiniertes Feld")

5. Verwenden Sie die Zuordnungen in *Tabelle 1*dargestellt. Protokoll Analytics wird automatisch die Erweiterung der ** \_CF** Zeichenfolge, die das neue Feld zu definieren.

> [!IMPORTANT]
> Denken Sie daran, dass alle JSON und Protokoll Analytics Felder Groß-/Kleinschreibung beachtet werden.
> 
> Achten Sie auf die Abfragen für benutzerdefinierte Felder in der folgenden Tabelle erforderlich. Sie müssen die richtigen Abfragen für Analytics-Protokoll verwenden, um Werte für benutzerdefinierte Felder erfolgreich zu extrahieren.
> 
 ![Definition für ein benutzerdefiniertes Feld] (../../media/Deploy-Azure-Monitor-5.png "Definition für ein benutzerdefiniertes Feld")

**Tabelle 1**

| JSON-Feld                   | **Melden Sie sich Analytics benutzerdefiniertes Feld** | Ereigniskennung | **Abfrage und die Extrahierung verwenden**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Beschreibung                      | SRSEventDescription         | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| ResourceState                    | SRSResourceState            | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| OperationName                    | SRSOperationName            | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| OperationResult                  | SRSOperationResult          | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| OS                               | SRSOSVersion                | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| Version des Betriebssystems                        | SRSOSLongVersion            | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| Alias                            | SRSAlias                    | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| DisplayName                      | SRSDisplayName              | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| AppVersion                       | SRSAppVersion               | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | US-$ 2.000     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 2000 |
| Mikrofon Konferenzstatus     | SRSConfMicrophoneStatus     | **3001**     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 3001 |
| Lautsprecher Konferenzstatus        | SRSConfSpeakerStatus        | **3001**     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 3001 |
| Standardstatus für Lautsprecher           | SRSDefaultSpeakerStatus     | **3001**     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 3001 |
| Kamera-status                    | SRSCameraStatus             | **3001**     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 3001 |
| Am Anfang Status Raum anzeigen     | SRSFORDStatus               | **3001**     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 3001 |
| Motion Sensorstatus             | SRSMotionSensorStatus       | **3001**     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 3001 |
| HDMI Aufnahme status               | SRSHDMIIngestStatus         | **3001**     | Ereignis \| , in dem Quellcode == "SRS-App" und EventID == 3001 |


## <a name="define-the-skype-room-systems-v2-views-in-log-analytics"></a>Definieren von Skype Raum Systemen v2 Ansichten im Protokoll Analytics
<a name="Define_Views"> </a>

Nachdem Daten erfasst werden und benutzerdefinierte Felder zugeordnet sind, können Ansicht-Designer Sie ein Dashboard mit verschiedenen Kacheln zum Überwachen des Skype Raum Systemen v2 entwickeln. Erstellen Sie mit dem Ansicht-Designer die folgenden Kacheln. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Ansichten mithilfe der Ansicht-Designer im Protokoll Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Vorherigen Schritte in diesem Handbuch soll für das Dashboard Kacheln ordnungsgemäß abgeschlossen wurden, ist.

### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>Erstellen eines Skype Raum Systemen v2-Dashboards mithilfe der Importmethode

Sie können importieren ein Skype Raum Systemen v2-Dashboards und Überwachung Ihrer Geräte schnell zu starten. Führen Sie die folgenden Schritte aus, um das Dashboard zu importieren:

1.  Rufen Sie die [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) -Dashboard-Datei.
2.  Melden Sie sich am [Microsoft Azure-Portal](https://portal.azure.com) und wechseln Sie zur Analyse der Protokolldatei, und wählen Sie den Arbeitsbereich.
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
2.  Wählen Sie aus dem Katalog **nummerieren & Liste**
3.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Heartbeat-Status<br>
    **Neue Gruppe:** Ausgewählt
4.  Definieren Sie die **Kachel** -Eigenschaften:<br>
    **Legende:** Aktive Geräte (Heartbeat gesendet, die in den letzten 20 Minuten)<br>
    Kachelabfrage: 
5.  Definieren Sie die **Liste** Eigenschaften:<br>
    Listenabfrage: 
6.  Definieren Sie **Spaltentitel**:<br>
    **Name:** Name des Computers<br>
    **Wert:** Letzter Takt
7.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **anwenden**und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Erstellen Sie eine Kachel, die Geräte angezeigt, die Probleme mit der Konnektivität

1.  Wählen Sie aus dem Katalog **nummerieren & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Leer lassen<br>
    **Neue Gruppe:** Nicht aktiviert
3.  Definieren Sie die **Kachel** -Eigenschaften:<br>
    **Legende:** Inaktive Geräte (keine Heartbeat-Nachricht gesendet, die in den letzten 20 Minuten)<br>
    Kachelabfrage: 
4.  Definieren Sie die **Liste** Eigenschaften:<br>
    Listenabfrage: 
5.  Definieren Sie **Spaltentitel**:<br>
    **Name:** Name des Computers<br>
    **Wert:** Letzter Takt
6.  **Navigation Abfrage**zu definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie **anwenden**und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Erstellen Sie eine Kachel, die Geräte angezeigt, die ein Hardwarefehler

1.  Wählen Sie aus dem Katalog **nummerieren & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Hardwarestatus<br>
    **Neue Gruppe:** Ausgewählt
3.  Definieren Sie die **Kachel** -Eigenschaften:<br>
    **Legende:** Geräte, die in der letzten Stunde einen Hardwarefehler auftraten<br>
    Kachelabfrage: 
4.  Definieren Sie die **Liste** Eigenschaften:<br>
    Listenabfrage: 
5.  Definieren Sie **Spaltentitel**:<br>
    **Name:** Name des Computers<br>
    **Wert:** Letzten Fehler
6.  **Navigation Abfrage**zu definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie **anwenden**und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a>Erstellen Sie eine Kachel, die Skype Raum Systemen v2 Betriebssystemversionen angezeigt wird.

1.  Wählen Sie aus dem Katalog **Rad & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Betriebssystem-details<br>
    **Neue Gruppe:** Ausgewählt
3.  **Header** -Eigenschaften zu definieren:<br>
    **Titel:** Versionen des Betriebssystems<br>
    **Untertitel:** Geräte, auf denen bestimmte Betriebssystemversionen
4.  Definieren Sie die **Rad** -Eigenschaften:<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Text zentrieren:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie **die Listeneigenschaften** .<br>
    Listenabfrage: <br>
    **Ausblenden Diagramm:** Ausgewählt<br>
    **Sparklines aktivieren:** Nicht aktiviert
6.  Definieren Sie **Spaltentitel**.<br>
    **Name:** Name des Computers<br>
    **Wert:** Leer lassen
7.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **anwenden** und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a>Erstellen von Kacheln, die Skype Raum Systemen v2 Anwendungsversionen anzeigt

1.  Wählen Sie aus dem Katalog **Rad & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppieren Titel:** Skype-Chatroom-Systemen v2 Anwendungsdetails<br>
    **Neue Gruppe:** Ausgewählt
3.  **Header** -Eigenschaften zu definieren:<br>
    **Titel:** Anwendungsversionen<br>
    **Untertitel:** Geräte, auf denen bestimmte Anwendungsversionen
4.  Definieren Sie die **Rad** -Eigenschaften:<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Text zentrieren:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie **die Listeneigenschaften** .<br>
    Listenabfrage: <br>
    **Ausblenden Diagramm:** Ausgewählt<br>
    **Sparklines aktivieren:** Nicht aktiviert
6.  Definieren Sie **Spaltentitel**.<br>
    **Name:** Name des Computers<br>
    **Wert:** Leer lassen
7.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **anwenden** und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Erstellen Sie eine Kachel, die Geräte angezeigt, die einen Application-Fehler

1.  Wählen Sie aus dem Katalog **nummerieren & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppieren Titel:** Leer lassen<br>
    **Neue Gruppe:** Nicht aktiviert
3.  Definieren Sie die **Kachel** -Eigenschaften.<br>
    **Legende:** Geräte, die in der letzten Stunde einen Anwendungsfehler auftreten<br>
    Kachelabfrage: 
4.  Definieren Sie **die Listeneigenschaften** .<br>
    Listenabfrage: 
5.  Definieren Sie **Spaltentitel**.<br>
    **Name:** Name des Computers<br>
    **Wert:** Letzten Fehler
6.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie **anwenden** und dann auf **Schließen**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Erstellen von Kacheln, die Geräte anzeigt, die neu gestartet wurden

1.  Wählen Sie aus dem Katalog **nummerieren & Liste** aus, und fügen Sie eine neue Tile.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppieren Titel:** Leer lassen<br>
    **Neue Gruppe:** Nicht aktiviert
3.  Definieren Sie die **Kachel** -Eigenschaften.<br>
    **Legende:** Geräte, auf dem die Anwendung in den letzten 24 Stunden und die Anzahl an Neustarts neu gestartet wurde<br>
    Kachelabfrage: 
4.  Definieren Sie **die Listeneigenschaften** .<br>
    Listenabfrage: 
5.  Definieren Sie **Spaltentitel**.<br>
    **Name:** Name des Computers<br>
    **Wert:** Anzahl an Neustarts
6.  **Navigation Abfrage**definiert.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie **anwenden** und dann auf **Schließen**.
8.  Wählen Sie **Speichern** , um das Dashboard zu speichern.

Nachdem Sie Ihre Ansichten erstellen abgeschlossen haben.

## <a name="configure-alerts-in-azure-monitor"></a>Konfigurieren von Warnungen in Azure Monitor
<a name="Alerts"> </a>

Azure überwachen kann auslösen Alarme, um die Administratoren benachrichtigen, wenn eine Skype Raum Systemen v2 Konsole ein Problem auftritt.

Azure Monitor umfasst eine integrierte Alarm-Mechanismen, die über geplanten Protokoll Suchvorgänge in geplanten Intervallen ausgeführt wird. Wenn die Ergebnisse der Suche Protokoll einige bestimmten Kriterien erfüllen, wird ein Warnung Datensatz erstellt.

Die Regel kann dann automatisch ausführen eine oder mehrere Aktionen zum proaktiv benachrichtigen Sie über die Benachrichtigung oder einem anderen Prozess aufzurufen. Die möglichen Optionen von Warnungen sind:
-   Senden einer e-Mail
-   Aufrufen von einem externen Prozess über eine HTTP POST-Anforderung
-   Starten einer Runbook in Azure Automation service

Finden Sie unter erfahren Sie mehr über die Warnungen in Azure Monitor [Warnungen in Azure Monitor melden](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) .

> [!NOTE]
> In den folgenden Beispielen sendet e-Mail-Benachrichtigungen, wenn ein Skype Raum Systemen v2 Gerät ein Hardware oder ein Anwendungsfehler generiert.

### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a>Konfigurieren Sie eine e-Mail-Warnung für Skype Raum Systemen v2 Hardwareprobleme

Konfigurieren Sie eine Warnung Regel, die Skype Raum Systemen v2 Geräte, die innerhalb der letzten Stunde Hardwareprobleme aufgetreten überprüft.
1.  Melden Sie sich am [Microsoft Azure-Portal](https://portal.azure.com) und wechseln Sie zur Analyse der Protokolldatei, und wählen Sie den Arbeitsbereich.

2. Navigieren Sie in den Arbeitsbereich Protokoll Analytics und wählen Sie **Benachrichtigungen** , und wählen Sie dann **neue Regel**

3. Wählen Sie **Bedingung hinzufügen** und dann **benutzerdefinierte Protokoll-Suche**

4.  Geben Sie die folgende Abfrage im Textfeld Abfrage suchen.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Konfigurieren Sie die Warnung Logik Einstellungen:<br>
    **Basierend auf:** Anzahl der Ergebnisse<br>
    **Bedingung:** Klicken Sie dann größer<br>
    **Treshold:** 0<br>

6. Konfigurieren Sie der Einstellungen für die Bewertung, und wählen Sie **Fertig**: <br>
    **Zeitraum (in Minuten):** 60<br>
    **Häufigkeit (in Minuten):** 60<br>

7. Konfigurieren Sie die Aktivitätsgruppen:
    1.  Wählen Sie **Erstellen einer neuen**
    2.  Enthalten Sie geeignete Namen für die *Aktion Gruppennamen* und die *Kurznamen* Felder.
    3.  Geben Sie einen eindeutigen *Namen der Aktion* und wählen Sie **E-Mail/SMS/Push/Stimme**, und wählen Sie dann auf **Details bearbeiten**.
    4.  Aktivieren Sie das Kontrollkästchen E-Mail, und geben Sie die e-Mail-Adresse der Person oder Gruppe, die Benachrichtigungen erhalten.
    5.  Sie können auch Ihre Telefonnummer ein, um benachrichtigt zu werden mit SMS, einen Anruf oder beide angeben.
    6. Wählen Sie **OK**aus.

8. **Aktionen anpassen,** Wenn Sie die Betreffzeile der alert-e-Mails außer Kraft setzen möchten.

9. Geben Sie einen Regelnamen und eine Beschreibung ein.<br>
    **Regelname:** Skype-Raum Systemen v2 Hardware Fehler Benachrichtigung<br>
    **Beschreibung:** Liste der Geräte, die innerhalb der letzten Stunde ein Hardwareproblem aufgetreten ist<br>

10. Wählen Sie den gewünschten Schweregrad, und stellen Sie sicher, dass die Regel aktiviert ist.

11. Wählen Sie die **Regel erstellen**.

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a>Konfigurieren Sie eine e-Mail-Benachrichtigung bei Problemen mit Skype Raum Systemen v2

Wiederholen Sie die gleiche Schritte aus, aber verwenden Sie die folgende Abfrage in der Liste Geräte, die innerhalb der letzten Stunde Anwendungsprobleme aufgetreten.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Sie haben nun definierende Benachrichtigungen abgeschlossen. Sie können zusätzliche Warnungen mithilfe der obigen Beispielen definieren.

Wenn eine Warnung generiert wird, erhalten Sie eine e-Mail, in der die Geräte aufgelistet, die innerhalb der letzten Stunde ein Problem aufgetreten ist.

![Warn-e-Beispiel Azure Monitor] (../../media/Deploy-Azure-Monitor-6.png "Warn-e-Beispiel Azure Monitor")

## <a name="configure-all-devices-for-azure-monitoring"></a>Konfigurieren Sie aller Geräte für die Überwachung von Azure
<a name="configure_all_devices"></a> Nachdem Dashboards und Benachrichtigungen konfiguriert sind, können Sie einrichten und Konfigurieren von Microsoft-Monitoring-Agent auf allen Geräten von Skype Raum Systemen v2 für die Durchführung die Überwachung Bereitstellung.

Obwohl Sie installieren und den Microsoft-Monitoring-Agent auf jedem Gerät manuell konfigurieren können, empfiehlt es sich, dass Sie vorhandene Bereitstellung Softwaretools und Methoden nutzen.

Wenn Sie Ihre Skype Raum Systemen v2 Geräte zum ersten Mal erstellen, empfiehlt es sich, die Microsoft Monitoring-Agent-Setup und Konfiguration Schritte im Rahmen des Buildprozesses enthalten. Weitere Informationen finden Sie unter [Installieren des Agents über die Befehlszeile](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Bereitstellen von Microsoft Monitoring Agent mithilfe einer Gruppenrichtlinienobjekt (GPO)

Wenn Sie Ihre Skype Raum Systemen v2 Geräte bereits vor der Implementierung von Azure Monitoring bereitgestellt, können Sie die bereitgestellten Skripts zum Einrichten und konfigurieren die Agents mithilfe von Active Directory-Gruppenrichtlinienobjekten verwenden.

1.  Erstellen Sie einen freigegebenen Netzwerkpfad, und erteilen Sie der Gruppe " **Domänencomputer** ".

2.  Laden Sie die 64-Bit-Version des Microsoft Monitoring-Agent für Windows aus<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrahieren Sie den Inhalt des Setup-Pakets in der Netzwerkfreigabe aus.
    1.  Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie die **MMASetup-AMD64.exe/c**
    2.  Geben Sie die Freigabe, die Sie gerade erstellt haben, und extrahieren Sie den Inhalt.

4.  Erstellen eines neuen Gruppenrichtlinienobjekts, und weisen Sie es mit der Organisationseinheit, in dem Skype Raum Systemen v2 Konten auf dem Computer gespeichert sind.

5.  PowerShell-Ausführungsrichtlinie zu konfigurieren:
    1.  Das neu erstellte Gruppenrichtlinienobjekt bearbeiten, und navigieren Sie zu Computerkonfiguration \\ Richtlinien \\ Administrative Vorlagen \\ Windows-Komponenten \\ Windows PowerShell
    2.  Aktivieren Sie die **Ausführung des Skripts zu aktivieren** , und legen Sie **Ausführungsrichtlinie** auf **Lokale Skripts zulassen**.

6.  Konfigurieren Sie das Startskript:
    1.  Kopieren Sie das folgende Skript, und speichern Sie es als Install-MMAgent.ps1.
    2.  Ändern Sie die Parameter WorkspaceId, WorkspaceKey und SetupPath entsprechend Ihrer Konfiguration.
    3.  Das gleiche Gruppenrichtlinienobjekt bearbeiten, und navigieren Sie zu Computerkonfiguration \\ Richtlinien \\ Windows-Einstellungen \\ Skripts (Start/Herunterfahren)
    4.  Durch Doppelklicken Sie können Sie **beim Start**wählen, und wählen Sie dann die **PowerShell-Skripts**.
    5.  Wählen Sie **Dateien anzeigen**, und klicken Sie dann kopieren Sie die **Installation MMAgent.ps1** -Datei in diesen Ordner.
    6.  Wählen Sie **Hinzufügen**und dann auf **Durchsuchen**.
    7.  Wählen Sie das ps1-Skript, die, das Sie soeben kopiert.

7.  Skype Raum Systemen v2 Geräte sollten installieren und konfigurieren den Microsoft-Monitoring-Agent mit der zweiten Neustart.

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
> Sie können Sie den Artikel, [Verwaltung und Wartung des Protokolldateien Analytics-Agents](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) verweisen, wenn Sie einen Agent konfigurieren, mit einem anderen Arbeitsbereich zu verschieben oder Ändern von Proxyeinstellungen nach der Erstinstallation müssen.

## <a name="additional-solutions"></a>Zusätzliche Lösungen
<a name="Solutions"> </a>

Azure Monitor bietet integrierten Management-Lösungen über seine [Lösungskatalog](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) , um weitere Sie Ihre Umgebung überwachen können. Es wird dringend empfohlen, den Arbeitsbereich sowie [Alert-Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) und [Azure Protokoll Analytics Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) Lösungen hinzuzufügen.

> [!NOTE]
> Die Integrität der Agent-Lösung kann Ihnen veraltete oder fehlerhaft Microsoft Monitoring-Agents in Ihrer Umgebung identifizieren und die Alert-Management-Lösung finden Sie Informationen über die Warnungen, die innerhalb eines bestimmten Zeitraums ausgelöst worden sein.

## <a name="see-also"></a>Siehe auch

[Planen der Verwaltung von Skype Raum Systemen v2 mit Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[Verwalten von Skype Raum Systemen v2 Geräte mit Azure Monitor](../../manage/skype-room-systems-v2/azure-monitor.md)