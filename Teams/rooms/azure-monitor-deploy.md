---
title: Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: In diesem Artikel wird erläutert, wie Sie die Verwaltung von Microsoft Teams rooms-Geräten in integrierter End-to-End-Weise mithilfe von Azure Monitor bereitstellen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05c490c157c9f6530ca79ecdd8df19f15d94c68
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662100"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Bereitstellen der :::no-loc text="Microsoft Teams Rooms"::: Verwaltung mit :::no-loc text="Azure Monitor":::

In diesem Artikel wird erläutert, wie Sie integriertes End-to-End-Management von Geräten mithilfe von einrichten und bereitstellen :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: .

Sie können :::no-loc text="Log Analytics"::: innerhalb konfigurieren :::no-loc text="Azure Monitor"::: , um grundlegende Telemetrie und Benachrichtigungen bereitzustellen, die Ihnen bei der Verwaltung von :::no-loc text="Microsoft Teams Rooms"::: Besprechungsraum Geräten helfen. Wenn Ihre Verwaltungslösung ausgereift ist, entscheiden Sie sich möglicherweise für die Bereitstellung zusätzlicher Daten-und Verwaltungsfunktionen, um eine detailliertere Ansicht der Verfügbarkeit und Leistung von Geräten zu erstellen.

Wenn Sie diesem Leitfaden folgen, können Sie ein Dashboard wie im folgenden Beispiel verwenden, um detaillierte Statusberichte für die Geräteverfügbarkeit, die Anwendungs-und Hardware Integrität sowie die :::no-loc text="Microsoft Teams Rooms"::: Versions Verteilung von Anwendungen und Betriebssystemen zu erhalten.

![Screenshot der Beispielansicht "Protokollanalyse" für Microsoft Teams-Chatrooms](../media/Deploy-Azure-Monitor-1.png "Beispiel für eine Protokollanalyse Ansicht für Microsoft Teams-Chatrooms")

Allgemein müssen Sie die folgenden Aufgaben ausführen:


1. [Überprüfen der :::no-loc text="Log Analytics"::: Konfiguration](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Konfigurieren von Testgeräten für die :::no-loc text="Log Analytics"::: Verwaltungseinrichtung](azure-monitor-deploy.md#configure_test_devices)
3. [Zuordnen benutzerdefinierter Felder](azure-monitor-deploy.md#Custom_fields)
4. [Definieren der :::no-loc text="Microsoft Teams Rooms"::: Ansichten in :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definieren von Benachrichtigungen](azure-monitor-deploy.md#Alerts)
6. [Konfigurieren aller Geräte für die Überwachung](azure-monitor-deploy.md#configure_all_devices)
7. [Konfigurieren zusätzlicher :::no-loc text="Azure Monitor"::: Lösungen](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Obwohl mit minimaler Konfiguration :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: einen Computer mit einem Betriebssystem überwachen kann :::no-loc text="Windows"::: , gibt es noch einige :::no-loc text="Microsoft Teams Rooms"::: spezifische Schritte, die Sie ausführen müssen, bevor Sie mit der Bereitstellung von Agents auf allen :::no-loc text="Microsoft Teams Rooms"::: Geräten beginnen.
> Wir empfehlen daher, dass Sie alle Konfigurationsschritte in der richtigen Reihenfolge für eine kontrollierte Einrichtung und Konfiguration durchführen. Die Qualität des Endergebnisses hängt stark von der Qualität der anfänglichen Konfiguration ab.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Überprüfen der :::no-loc text="Log Analytics"::: Konfiguration
<a name="validate_LogAnalytics"> </a>

Sie benötigen einen :::no-loc text="Log Analytics"::: Arbeitsbereich, um mit dem Sammeln von Protokollen von Geräten zu beginnen :::no-loc text="Microsoft Teams Rooms"::: . Ein Arbeitsbereich ist eine einzigartige :::no-loc text="Log Analytics"::: Umgebung mit eigenem Daten-Repository, Datenquellen und Lösungen. Wenn Sie bereits über einen vorhandenen :::no-loc text="Log Analytics"::: Arbeitsbereich verfügen, können Sie ihn zum Überwachen der :::no-loc text="Microsoft Teams Rooms"::: Bereitstellung verwenden, oder Sie können einen dedizierten Arbeitsbereich erstellen, der :::no-loc text="Log Analytics"::: für Ihre :::no-loc text="Microsoft Teams Rooms"::: Überwachungsanforderungen spezifisch ist.

Wenn Sie einen neuen :::no-loc text="Log Analytics"::: Arbeitsbereich erstellen müssen, folgen Sie den Anweisungen im Artikel [Erstellen eines :::no-loc text="Log Analytics"::: Arbeitsbereichs im :::no-loc text="Azure"::: Portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) .

> [!NOTE]
> Um mit zu verwenden :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: , müssen Sie über ein aktives :::no-loc text="Azure"::: Abonnement verfügen. Wenn Sie nicht über ein :::no-loc text="Azure"::: Abonnement verfügen, können Sie als Ausgangspunkt [ein kostenloses Testabonnement](https://azure.microsoft.com/free) erstellen.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Konfigurieren :::no-loc text="Log Analytics"::: zum Sammeln von :::no-loc text="Microsoft Teams Rooms"::: Ereignisprotokollen

:::no-loc text="Log Analytics"::: sammelt nur Ereignisse aus den :::no-loc text="Windows"::: Ereignisprotokollen, die in den Einstellungen angegeben sind. Für jedes Protokoll werden nur die Ereignisse mit den ausgewählten severities erfasst.

Sie müssen konfigurieren :::no-loc text="Log Analytics"::: , um die Protokolle zu sammeln, die erforderlich sind, um den :::no-loc text="Microsoft Teams Rooms"::: Geräte-und Anwendungsstatus zu überwachen. :::no-loc text="Microsoft Teams Rooms"::: Geräte verwenden das **:::no-loc text="Skype Room System":::** Ereignisprotokoll.

Informationen zum Konfigurieren :::no-loc text="Log Analytics"::: zum Sammeln der :::no-loc text="Microsoft Teams Rooms"::: Ereignisse finden Sie unter [ :::no-loc text="Windows"::: Ereignisprotokoll- :::no-loc text="Azure Monitor"::: Datenquellen in](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Screenshot der Ereignisprotokolleinstellungen](../media/Deploy-Azure-Monitor-2.png "Ereignisprotokolleinstellungen")

> [!IMPORTANT]
> Konfigurieren Sie :::no-loc text="Windows"::: Die Ereignisprotokolleinstellungen **:::no-loc text="Skype Room System":::** , geben Sie den Namen des Ereignisprotokolls ein, und aktivieren Sie dann die Kontrollkästchen **Fehler**, **Warnung** und **Informationen** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Konfigurieren von Testgeräten für die Azure-Überwachung
<a name="configure_test_devices"> </a>

Sie müssen sich vorbereiten :::no-loc text="Log Analytics"::: , damit verwandte Ereignisse überwacht werden können :::no-loc text="Microsoft Teams Rooms"::: . Zunächst müssen Sie :::no-loc text="Microsoft Monitoring"::: Agents auf nur ein oder zwei Geräte bereitstellen, :::no-loc text="Microsoft Teams Rooms"::: auf die Sie physischen Zugriff haben, und diese Testgeräte generieren einige Daten und schieben Sie in den :::no-loc text="Log Analytics"::: Arbeitsbereich.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installieren :::no-loc text="Microsoft Monitoring"::: von Agents zum Testen von Geräten

Stellen :::no-loc text="Microsoft Monitoring"::: Sie den Agenten auf den Testgeräten bereit, indem Sie die Anweisungen unter [Verbinden von :::no-loc text="Windows"::: Computern mit dem :::no-loc text="Log Analytics"::: Dienst in :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)verwenden. Dieser Artikel enthält detaillierte Informationen zu den Schritten zum Bereitstellen des :::no-loc text="Microsoft Monitoring"::: Agents :::no-loc text="Windows"::: , Anweisungen zum Abrufen der :::no-loc text="Log Analytics":::  * *_Arbeitsbereichs-ID_* _ und des _*_Primärschlüssels_*_ zum Abrufen von Geräten, die mit :::no-loc text="Microsoft Teams Rooms"::: Ihrer :::no-loc text="Azure Monitor"::: Bereitstellung verbunden sind, sowie Schritte zum Überprüfen der Agent-Konnektivität mit :::no-loc text="Log Analytics"::: Instanzen.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generieren von Beispiel :::no-loc text="Microsoft Teams Rooms"::: Ereignissen

Nachdem der :::no-loc text="Microsoft Monitoring"::: Agent auf den Testgeräten bereitgestellt wurde, stellen Sie sicher, dass die erforderlichen Ereignisprotokolldaten von erfasst werden :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Starten Sie das Gerät nach der Installation des :::no-loc text="Microsoft Monitoring"::: Agents neu, und stellen Sie sicher, dass die :::no-loc text="Microsoft Teams Rooms"::: Besprechungs-App gestartet wird, damit Sie neue Ereignisse im Ereignisprotokoll generieren kann.

1.  Registrieren Sie sich beim [ :::no-loc text="Microsoft Azure"::: Portal](https://portal.azure.com) , und :::no-loc text="Log Analytics"::: Wählen Sie Ihren Arbeitsbereich aus.

2.  Auflisten der von einem Gerät generierten Heartbeat-Ereignisse :::no-loc text="Microsoft Teams Rooms"::: :
    1.  Wählen Sie Ihren Arbeitsbereich aus, und wechseln Sie zu _ *Logs**, und verwenden Sie eine Abfrage, um die Heartbeat-Datensätze abzurufen, für die die benutzerdefinierten Felder vorhanden sein sollen :::no-loc text="Microsoft Teams Rooms"::: .
    2.  Beispielabfrage: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Stellen Sie sicher, dass die Abfrageprotokoll Datensätze zurückgibt, die Ereignisse enthalten, die von der :::no-loc text="Microsoft Teams Rooms"::: Besprechungs-App generiert wurden.

4.  Generieren Sie ein Hardwareproblem, und überprüfen Sie, ob die erforderlichen Ereignisse angemeldet sind :::no-loc text="Azure Log Analytics"::: .
    1.  Ziehen Sie eines der Peripheriegeräte des Test :::no-loc text="Microsoft Teams Rooms"::: Systems ab. Hierbei kann es sich um die Kamera-, Freisprech-, Mikrofon-oder Front Raum Anzeige handeln.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll ausgefüllt wird :::no-loc text="Azure Log Analytics"::: .
    3.  Verwenden einer Abfrage zum Auflisten von Hardwarefehler Ereignissen: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Generieren Sie ein Anwendungsproblem, und überprüfen Sie, ob die erforderlichen Ereignisse protokolliert werden.
    1.  Ändern Sie :::no-loc text="Microsoft Teams Rooms"::: die Anwendungskonfiguration, und geben Sie ein falsches SIP-Adresse/Kennwort-Paar (Session Initiation Protocol) ein.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll ausgefüllt wird :::no-loc text="Azure Log Analytics"::: .
    3.  Verwenden einer Abfrage zum Auflisten von Anwendungsfehler Ereignissen: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Diese Beispiel Ereignisprotokolle sind erforderlich, bevor benutzerdefinierte Felder konfiguriert werden können. Fahren Sie nicht mit dem nächsten Schritt fort, bis Sie die erforderlichen Ereignisprotokolle gesammelt haben.

## <a name="map-custom-fields"></a>Zuordnen benutzerdefinierter Felder
<a name="Custom_fields"> </a>

Sie verwenden benutzerdefinierte Felder, um bestimmte Daten aus den Ereignisprotokollen zu extrahieren. Sie müssen benutzerdefinierte Felder definieren, die später für Ihre Kacheln, Dashboard-Ansichten und Benachrichtigungen verwendet werden. Lesen Sie [benutzerdefinierte :::no-loc text="Log Analytics"::: Felder in](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) , und machen Sie sich mit den Konzepten vertraut, bevor Sie mit dem Erstellen Ihrer benutzerdefinierten Felder beginnen.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierten Felder aus den erfassten Ereignisprotokollen zu extrahieren:

1.  Registrieren Sie sich beim [ :::no-loc text="Microsoft Azure"::: Portal](https://portal.azure.com) , und :::no-loc text="Log Analytics"::: Wählen Sie Ihren Arbeitsbereich aus.

2. Listen Sie die Ereignisse auf, die von einem Gerät generiert wurden :::no-loc text="Microsoft Teams Rooms"::: :
   1.  Wechseln Sie zu **Protokolle** , und verwenden Sie eine Abfrage, um die Datensätze abzurufen, die das benutzerdefinierte Feld aufweisen.
   2.  Beispielabfrage: `Event | where Source == "SRS-App" and EventID == 2000`

3. Wählen Sie einen der Datensätze aus, wählen Sie die Schaltfläche links aus, und starten Sie den Feld Extraktions-Assistenten.
4. Markieren Sie die Daten, die Sie aus dem RenderedDescription extrahieren möchten, und geben Sie einen Feld Titel ein. Die Feldnamen, die Sie verwenden sollten, werden in Tabelle 1 bereitgestellt.
5. Verwenden Sie die in *Tabelle 1* gezeigten Zuordnungen. :::no-loc text="Log Analytics":::Fügt die **\_ CF** -Zeichenfolge beim Definieren des neuen Felds automatisch an.

> [!IMPORTANT]
> Beachten Sie, dass bei allen JSON :::no-loc text="Log Analytics"::: -und Feldern die Groß-/Kleinschreibung beachtet wird.
> 
> Achten Sie auf die Abfragen, die für jedes benutzerdefinierte Feld in der folgenden Tabelle erforderlich sind. Sie müssen die richtigen Abfragen verwenden :::no-loc text="Log Analytics"::: , um benutzerdefinierte Feldwerte erfolgreich zu extrahieren.
> 
**Tabelle 1**

| **JSON-Feld**                   | **:::no-loc text="Log Analytics"::: benutzerdefiniertes Feld** | **Ereigniskennung** | **Abfrage, die mit der Extraktion verwendet werden soll**                   |
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


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definieren der :::no-loc text="Microsoft Teams Rooms"::: Ansichten in :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Nachdem Daten gesammelt und benutzerdefinierte Felder zugeordnet wurden, können Sie mit dem Ansicht-Designer ein Dashboard entwickeln, das verschiedene Kacheln zum Überwachen von :::no-loc text="Microsoft Teams Rooms"::: Ereignissen enthält. Erstellen Sie mit dem Ansicht-Designer die folgenden Kacheln. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Ansichten mit dem Ansicht :::no-loc text="Log Analytics"::: -Designer in](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Die vorherigen Schritte in diesem Leitfaden sollten für die ordnungsgemäße Funktionsweise der Dashboard-Kacheln abgeschlossen sein.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Erstellen eines Microsoft Teams rooms-Dashboards mithilfe der Import-Methode

Sie können ein :::no-loc text="Microsoft Teams Rooms"::: Dashboard importieren und Ihre Geräte schnell überwachen. Führen Sie die folgenden Schritte aus, um das Dashboard zu importieren:

1.  Rufen Sie die [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) -dashboarddatei ab.
2.  Registrieren Sie sich beim [ :::no-loc text="Microsoft Azure"::: Portal](https://portal.azure.com) , und :::no-loc text="Log Analytics"::: Wählen Sie Ihren Arbeitsbereich aus.
3.  Öffnen Sie den **Ansicht-Designer**.
4.  Wählen Sie **importieren** aus, und wählen Sie dann die Datei **SkypeRoomSystems_v2. omsview** aus.
5.  Klicken Sie auf **Speichern**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Manuelles Erstellen eines Microsoft Teams rooms-Dashboards

Sie können auch ein eigenes Dashboard erstellen und nur die Kacheln hinzufügen, die Sie überwachen möchten.

#### <a name="configure-the-overview-tile"></a>Konfigurieren der Kachel "Übersicht"

1.  Öffnen Sie den **Ansicht-Designer**.
2.  Wählen Sie **Übersicht-Kachel** aus, und wählen Sie dann im Katalog **zwei Zahlen** aus.
3.  Benennen Sie die Kachel **:::no-loc text="Microsoft Teams Rooms":::** .
4.  Definieren der **ersten Kachel**:<br>
    **Legende:** Geräte, die mindestens einmal innerhalb des letzten Monats einen Heartbeat gesendet haben<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definieren Sie die **zweite Kachel**:<br>
    **Legende:** Aktive Geräte, die innerhalb der letzten Stunde einen Heartbeat gesendet haben<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Wählen Sie über **nehmen** aus.

### <a name="create-a-tile-that-displays-active-devices"></a>Erstellen einer Kachel, auf der aktive Geräte angezeigt werden

1.  Wählen Sie **Dashboard anzeigen** aus, um das Hinzufügen Ihrer Kacheln zu beginnen.
2.  Wählen Sie **Zahl & Liste** aus dem Katalog aus.
3.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Heartbeat-Status<br>
    **Neue Gruppe:** Ausgewählten
4.  Definieren Sie die **Kachel** Eigenschaften:<br>
    **Legende:** Aktive Geräte (in den letzten 20 Minuten gesendeter Heartbeat)<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definieren Sie die **Listen** Eigenschaften:<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definieren von **Spaltentiteln**:<br>
    **Name:** Computer Name<br>
    **Wert:** Letzter Heartbeat
7.  **Navigations Abfrage** definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie über **nehmen** und dann **Schließen** aus.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Erstellen einer Kachel, auf der Geräte mit Verbindungsproblemen angezeigt werden

1.  Wählen Sie im Katalog **Zahl & Liste** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kachel** Eigenschaften:<br>
    **Legende:** Inaktive Geräte (in den letzten 20 Minuten wurde keine Heartbeat-Nachricht gesendet)<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definieren Sie die **Listen** Eigenschaften:<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definieren von **Spaltentiteln**:<br>
    **Name:** Computer Name<br>
    **Wert:** Letzter Heartbeat
6.  **Navigations Abfrage** definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie über **nehmen** und dann **Schließen** aus.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Erstellen einer Kachel, die Geräte mit einem Hardwarefehler anzeigt

1.  Wählen Sie im Katalog **Zahl & Liste** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Hardware Status<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Kachel** Eigenschaften:<br>
    **Legende:** Geräte, die in der letzten Stunde einen Hardwarefehler auftraten<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listen** Eigenschaften:<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren von **Spaltentiteln**:<br>
    **Name:** Computer Name<br>
    **Wert:** Letzter Fehler
6.  **Navigations Abfrage** definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie über **nehmen** und dann **Schließen** aus.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Erstellen einer Kachel, in der :::no-loc text="Microsoft Teams Rooms"::: Betriebs System Versionen angezeigt werden

1.  Wählen Sie im Katalog **Donut & Liste** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Details zum Betriebs System<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Header** Eigenschaften:<br>
    **Titel:** Betriebs System Versionen<br>
    Unter **Titel:** Geräte mit bestimmten Betriebssystemversionen
4.  Definieren Sie die **Donut** -Eigenschaften:<br>
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
7.  **Navigations Abfrage** definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie über **nehmen** und dann **Schließen** aus.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Erstellen einer Kachel, in der :::no-loc text="Microsoft Teams Rooms"::: Anwendungsversionen angezeigt werden

1.  Wählen Sie im Katalog **Donut & Liste** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** :::no-loc text="Microsoft Teams Rooms"::: Anwendungsdetails<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Header** Eigenschaften:<br>
    **Titel:** Anwendungsversionen<br>
    Unter **Titel:** Geräte, auf denen bestimmte Anwendungsversionen ausgeführt werden
4.  Definieren Sie die **Donut** -Eigenschaften:<br>
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
7.  **Navigations Abfrage** definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie über **nehmen** und dann **Schließen** aus.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Erstellen einer Kachel, die Geräte mit einem Anwendungsfehler anzeigt

1.  Wählen Sie im Katalog **Zahl & Liste** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kachel** Eigenschaften.<br>
    **Legende:** Geräte, die in der letzten Stunde einen Anwendungsfehler erlebt haben<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listen** Eigenschaften.<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren von **Spaltentiteln**<br>
    **Name:** Computer Name<br>
    **Wert:** Letzter Fehler
6.  **Navigations Abfrage** definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie über **nehmen** und dann **Schließen** aus.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Erstellen einer Kachel, auf der neu gestartete Geräte angezeigt werden

1.  Wählen Sie im Katalog **Zahl & Liste** aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kachel** Eigenschaften.<br>
    **Legende:** Geräte, auf denen die Anwendung in den letzten 24 Stunden neu gestartet wurde, und die Anzahl der Neustarts<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listen** Eigenschaften.<br>
    **Listen Abfrage:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definieren von **Spaltentiteln**<br>
    **Name:** Computer Name<br>
    **Wert:** Anzahl der Neustarts
6.  **Navigations Abfrage** definieren<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie über **nehmen** und dann **Schließen** aus.
8.  Wählen Sie **Speichern** aus, um das Dashboard zu speichern.

Sie haben nun die Erstellung ihrer Ansichten abgeschlossen.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Konfigurieren von Benachrichtigungen in :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: kann Benachrichtigungen auslösen, damit die Administratoren benachrichtigt werden, wenn in einer :::no-loc text="Microsoft Teams Rooms"::: Konsole ein Problem auftritt.

:::no-loc text="Azure Monitor"::: enthält einen integrierten Benachrichtigungsmechanismus, der in regelmäßigen Abständen über geplante Protokoll suchen ausgeführt wird. Wenn die Ergebnisse der Protokollsuche einigen bestimmten Kriterien entsprechen, wird ein Warnungseintrag erstellt.

Die Regel kann dann automatisch eine oder mehrere Aktionen ausführen, um Sie proaktiv über die Benachrichtigung zu informieren oder einen anderen Prozess aufzurufen. Mögliche Optionen mit Benachrichtigungen sind:
-   Senden einer e-Mail
-   Aufrufen eines externen Prozesses über eine HTTP POST-Anforderung
-   Starten eines runbooks in :::no-loc text="Azure Automation"::: Dienst

Weitere Informationen zu den Benachrichtigungen finden Sie unter [Protokollieren von Benachrichtigungen :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) in :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Die folgenden Beispiele senden e-Mail-Benachrichtigungen, wenn ein :::no-loc text="Microsoft Teams Rooms"::: Gerät einen Hardware-oder Anwendungsfehler generiert.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Konfigurieren einer e-Mail-Benachrichtigung für :::no-loc text="Microsoft Teams Rooms"::: Hardwareprobleme

Konfigurieren Sie eine Warnungsregel, die nach :::no-loc text="Microsoft Teams Rooms"::: Geräten sucht, die innerhalb der letzten Stunde Hardwareprobleme aufgetreten sind.
1.  Registrieren Sie sich beim [ :::no-loc text="Microsoft Azure"::: Portal](https://portal.azure.com) , und :::no-loc text="Log Analytics"::: Wählen Sie Ihren Arbeitsbereich aus.

2. Navigieren Sie zu Ihrem :::no-loc text="Log Analytics"::: Arbeitsbereich, und wählen Sie **Benachrichtigungen** und dann **neue Warnungsregel** aus.

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
    **Schwellenwert:** 0<br>

6. Konfigurieren Sie Evaluierungs Einstellungen, und wählen Sie **Fertig** aus: <br>
    **Zeitraum (in Minuten):** 60<br>
    **Häufigkeit (in Minuten):** 60<br>

7. Konfigurieren von Aktionsgruppen:
    1.  Wählen Sie **neu erstellen** aus.
    2.  Geben Sie geeignete Namen für die Felder *Aktionsgruppenname* und *Kurzname* an.
    3.  Geben Sie einen eindeutigen *Aktionsnamen* an, wählen Sie **e-Mail/SMS/Push/Voice** aus, und wählen Sie dann **Details bearbeiten** aus.
    4.  Aktivieren Sie das Kontrollkästchen **e-Mail** , und geben Sie die e-Mail-Adresse der Person oder Gruppe an, die die Benachrichtigungen erhalten soll.
    5.  Sie können auch Ihre Telefonnummer angeben, um mit SMS, einem Sprachanruf oder beides benachrichtigt zu werden.
    6. Wählen Sie **OK** aus.

8. **Passen Sie Aktionen** an, wenn Sie die Betreffzeile der Benachrichtigungs-e-Mails außer Kraft setzen möchten.

9. Geben Sie einen Regelnamen und eine Beschreibung an.<br>
    **Regel Name:** :::no-loc text="Microsoft Teams Rooms"::: Warnung bei Hardware Fehler<br>
    **Beschreibung:** Liste der Geräte, die innerhalb der letzten Stunde auf ein Hardwareproblem gestoßen sind<br>

10. Wählen Sie den gewünschten Schweregrad aus, und stellen Sie sicher, dass die Regel aktiviert ist.

11. Wählen Sie **Warnungsregel erstellen** aus.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Konfigurieren einer e-Mail-Benachrichtigung für :::no-loc text="Microsoft Teams Rooms"::: Anwendungsprobleme

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

! [Beispiel :::no-loc text="Azure Monitor"::: Benachrichtigungs-e-Mail] (.. /Media/Deploy-Azure-Monitor-6.png "Beispiel :::no-loc text="Azure Monitor"::: Benachrichtigungs-e-Mail")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Konfigurieren aller Geräte für :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> Nachdem die Dashboards und Benachrichtigungen konfiguriert sind, können Sie den :::no-loc text="Microsoft Monitoring"::: Agenten auf allen Geräten einrichten und konfigurieren, :::no-loc text="Microsoft Teams Rooms"::: um die Überwachungs Bereitstellung abzuschließen.

Obwohl Sie den :::no-loc text="Microsoft Monitoring"::: Agenten auf jedem Gerät manuell installieren und konfigurieren können, empfehlen wir dringend, vorhandene Softwarebereitstellungstools und-Methoden zu nutzen.

Wenn Sie Ihre :::no-loc text="Microsoft Teams Rooms"::: Geräte zum ersten Mal erstellen, möchten Sie möglicherweise die :::no-loc text="Microsoft Monitoring"::: Setup-und Konfigurationsschritte des Agents als Teil des Buildprozesses einbeziehen. Weitere Informationen finden Sie unter [Installieren des Agents über die Befehlszeile](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Bereitstellen :::no-loc text="Microsoft Monitoring"::: des Agents mithilfe eines Gruppenrichtlinienobjekts (GPO)

Wenn Sie Ihre Geräte bereits :::no-loc text="Microsoft Teams Rooms"::: vor der Implementierung bereitgestellt :::no-loc text="Azure Monitoring"::: haben, können Sie das bereitgestellte Skript verwenden, um die Agents mithilfe von :::no-loc text="Active Directory"::: Gruppenrichtlinienobjekten einzurichten und zu konfigurieren.

1.  Erstellen Sie einen freigegebenen Netzwerkpfad, und erteilen Sie den Lesezugriff auf die Gruppe " **Domänencomputer** ".

2.  Laden Sie die 64-Bit-Version des :::no-loc text="Microsoft Monitoring"::: Agents für from herunter. :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrahieren Sie den Inhalt des Setuppakets in die Netzwerkfreigabe.
    1.  Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie dann **MMASetup-AMD64.exe/c** aus.
    2.  Geben Sie die soeben erstellte Freigabe an, und extrahieren Sie den Inhalt.

4.  Erstellen Sie ein neues Gruppenrichtlinienobjekt, und weisen Sie es der Organisationseinheit zu, in der sich :::no-loc text="Microsoft Teams Rooms"::: Computerkonten befinden.

5.  Konfigurieren der PowerShell-Ausführungsrichtlinie:
    1.  Bearbeiten Sie das neu erstellte Gruppenrichtlinienobjekt, und navigieren Sie zu den Computer Konfigurations \\ Richtlinien- \\ \\ :::no-loc text="Windows"::: Komponenten \\ für administrative Vorlagen. :::no-loc text="Windows PowerShell":::
    2.  Aktivieren **Sie die Skriptausführung** aktivieren, und setzen Sie die **Ausführungsrichtlinie** so, dass **lokale Skripts zulässig** sind.

6.  Konfigurieren des Startskripts:
    1.  Kopieren Sie das folgende Skript, und speichern Sie es als Install-MMAgent.ps1.
    2.  Ändern Sie die Parameter für die Workspace-, WorkspaceKey-und SetupPath, um ihrer Konfiguration zu entsprechen.
    3.  Bearbeiten desselben Gruppenrichtlinienobjekts und navigieren zu den Einstellungs Skripts für Computer Konfigurations \\ Richtlinien \\ :::no-loc text="Windows"::: \\ (Start/Shutdown)
    4.  Doppelklicken Sie auf **Start**, und wählen Sie dann **PowerShell-Skripts** aus.
    5.  Wählen Sie **Dateien anzeigen** aus, und kopieren Sie dann die **Install-MMAgent.ps1** Datei in diesen Ordner.
    6.  Wählen Sie **Hinzufügen** und dann **Durchsuchen** aus.
    7.  Wählen Sie das ps1-Skript aus, das Sie soeben kopiert haben.

7.  :::no-loc text="Microsoft Teams Rooms"::: Geräte sollten den :::no-loc text="Microsoft Monitoring"::: Agenten beim zweiten Neustart installieren und konfigurieren.

```PowerShell
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
> Sie finden den Artikel [Verwalten und Verwalten des :::no-loc text="Log Analytics"::: Agents](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) , wenn Sie einen Agenten neu konfigurieren, in einen anderen Arbeitsbereich verschieben oder Proxyeinstellungen nach der ersten Installation ändern müssen.

## <a name="additional-solutions"></a>Weitere Lösungen
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: bietet integrierte Verwaltungslösungen über den [Lösungskatalog](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) , damit Sie Ihre Umgebung weiter überwachen können. Wir empfehlen dringend, dass Sie Ihrem Arbeitsbereich auch [Warnungs Verwaltungs](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) -und [ :::no-loc text="Azure Log Analytics"::: Agenten Integritäts](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) Lösungen hinzufügen.

> [!NOTE]
> Die Lösung für den Agentenstatus kann Ihnen dabei helfen, veraltete oder fehlerhafte :::no-loc text="Microsoft Monitoring"::: Agents in Ihrer Umgebung zu identifizieren, und die Warnungs Verwaltungslösung enthält Details zu den Benachrichtigungen, die innerhalb eines bestimmten Zeitraums ausgelöst wurden.

## <a name="see-also"></a>Weitere Informationen

[Plan :::no-loc text="Microsoft Teams Rooms"::: Verwaltung mit :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Verwalten :::no-loc text="Microsoft Teams Rooms"::: von Geräten mit :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
