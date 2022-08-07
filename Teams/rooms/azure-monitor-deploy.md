---
title: Bereitstellen Microsoft Teams-Räume Überwachung mit Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: In diesem Artikel wird erläutert, wie die Überwachung von Microsoft Teams-Räume integriert und end-to-end mithilfe von Azure Monitor bereitgestellt wird.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2b6d1931b0a1818b5146f6ac0e02c225fea3af52
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267450"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Bereitstellen der :::no-loc text="Microsoft Teams Rooms"::: Überwachung mit :::no-loc text="Azure Monitor":::

In diesem Artikel wird erläutert, wie Sie die integrierte End-to-End-Überwachung von Geräten mithilfe :::no-loc text="Azure Monitor":::von :::no-loc text="Microsoft Teams Rooms"::: .

Sie können innerhalb :::no-loc text="Azure Monitor"::: konfigurieren:::no-loc text="Log Analytics":::, um grundlegende Telemetrie und Warnungen bereitzustellen, die Ihnen bei der Verwaltung :::no-loc text="Microsoft Teams Rooms":::helfen. Wenn Ihre Verwaltungslösung ausgereift ist, können Sie sich entscheiden, zusätzliche Daten- und Verwaltungsfunktionen bereitzustellen, um eine detailliertere Ansicht der Geräteverfügbarkeit und -leistung zu erstellen.

Indem Sie diesem Leitfaden folgen, können Sie ein Dashboard wie das folgende Beispiel verwenden, um detaillierte Statusberichte für die Geräteverfügbarkeit, den Anwendungs- und Hardwarestatus sowie :::no-loc text="Microsoft Teams Rooms"::: die Versionsverteilung von Anwendungen und Betriebssystemen zu erhalten.

![Screenshot der Log Analytics-Beispielansicht für Microsoft Teams-Räume.](../media/Deploy-Azure-Monitor-1.png "Log Analytics-Beispielansicht für Microsoft Teams-Räume")

Allgemein müssen Sie die folgenden Aufgaben ausführen:


1. [Überprüfen der :::no-loc text="Log Analytics"::: Konfiguration](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Konfigurieren von Testgeräten für :::no-loc text="Log Analytics"::: die Verwaltungseinrichtung](azure-monitor-deploy.md#configure_test_devices)
3. [Zuordnen benutzerdefinierter Felder](azure-monitor-deploy.md#Custom_fields)
4. [Definieren der :::no-loc text="Microsoft Teams Rooms"::: Ansichten in :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definieren von Warnungen](azure-monitor-deploy.md#Alerts)
6. [Konfigurieren aller Geräte für die Überwachung](azure-monitor-deploy.md#configure_all_devices)
7. [Konfigurieren zusätzlicher :::no-loc text="Azure Monitor"::: Lösungen](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Obwohl mit minimaler Konfiguration ein Computer überwacht werden kann, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: auf dem ein :::no-loc text="Windows"::: Betriebssystem ausgeführt wird, gibt es noch einige :::no-loc text="Microsoft Teams Rooms":::spezifische Schritte, die Sie ausführen müssen, bevor Sie mit der Bereitstellung von Agents auf allen :::no-loc text="Microsoft Teams Rooms"::: Geräten beginnen.
> Daher wird dringend empfohlen, alle Konfigurationsschritte in der richtigen Reihenfolge für eine kontrollierte Einrichtung und Konfiguration durchzuführen. Die Qualität des Endergebnisses hängt stark von der Qualität der Erstkonfiguration ab.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Überprüfen der :::no-loc text="Log Analytics"::: Konfiguration
<a name="validate_LogAnalytics"> </a>

Sie benötigen einen :::no-loc text="Log Analytics"::: Arbeitsbereich, um mit dem Sammeln von Protokollen zu :::no-loc text="Microsoft Teams Rooms":::beginnen. Ein Arbeitsbereich ist eine einzigartige :::no-loc text="Log Analytics"::: Umgebung mit einem eigenen Datenrepository, Datenquellen und Lösungen. Wenn Sie bereits über einen vorhandenen :::no-loc text="Log Analytics"::: Arbeitsbereich verfügen, können Sie ihn verwenden, um Ihre :::no-loc text="Microsoft Teams Rooms"::: Bereitstellung zu überwachen, oder Alternativ können Sie einen dedizierten :::no-loc text="Log Analytics"::: Arbeitsbereich erstellen, der ihren :::no-loc text="Microsoft Teams Rooms"::: Überwachungsanforderungen entspricht.

Wenn Sie einen neuen :::no-loc text="Log Analytics"::: Arbeitsbereich erstellen müssen, folgen Sie den Anweisungen im Artikel ["Erstellen eines :::no-loc text="Log Analytics"::: Arbeitsbereichs im :::no-loc text="Azure"::: Portal](/azure/azure-monitor/learn/quick-create-workspace)".

> [!NOTE]
> Für die Verwendung :::no-loc text="Log Analytics"::: mit :::no-loc text="Azure Monitor":::benötigen Sie ein aktives :::no-loc text="Azure"::: Abonnement. Wenn Sie nicht über ein :::no-loc text="Azure"::: Abonnement verfügen, können Sie [ein kostenloses Testabonnement](https://azure.microsoft.com/free) als Ausgangspunkt erstellen.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Konfigurieren :::no-loc text="Log Analytics"::: der Erfassung von :::no-loc text="Microsoft Teams Rooms"::: Ereignisprotokollen

:::no-loc text="Log Analytics"::: sammelt nur Ereignisse aus den :::no-loc text="Windows"::: Ereignisprotokollen, die in den Einstellungen angegeben sind. Für jedes Protokoll werden nur die Ereignisse mit den ausgewählten Schweregraden erfasst.

Sie müssen konfigurieren :::no-loc text="Log Analytics"::: , um die Protokolle zu sammeln, die zum Überwachen :::no-loc text="Microsoft Teams Rooms"::: des Geräte- und Anwendungsstatus erforderlich sind. :::no-loc text="Microsoft Teams Rooms"::: verwenden Sie das **:::no-loc text="Skype Room System":::** Ereignisprotokoll.

Informationen zum Konfigurieren :::no-loc text="Log Analytics"::: der :::no-loc text="Microsoft Teams Rooms"::: Ereignisse finden Sie [:::no-loc text="Windows"::: unter Ereignisprotokolldatenquellen in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)

![Screenshot der Ereignisprotokolleinstellungen.](../media/Deploy-Azure-Monitor-2.png "Ereignisprotokolleinstellungen")

> [!IMPORTANT]
> Konfigurieren Sie :::no-loc text="Windows"::: die Einstellungen für das Ereignisprotokoll, geben Sie den Namen des Ereignisprotokolls ein **:::no-loc text="Skype Room System":::** , und aktivieren Sie dann die Kontrollkästchen **"Fehler**", **"Warnung**" und " **Informationen** ".

## <a name="configure-test-devices-for-azure-monitoring"></a>Konfigurieren von Testgeräten für Azure Monitoring
<a name="configure_test_devices"> </a>

Sie müssen sich darauf vorbereiten :::no-loc text="Log Analytics"::: , dass Sie –bezogene Ereignisse überwachen :::no-loc text="Microsoft Teams Rooms":::können. Zunächst müssen Sie Agents auf einem oder zwei :::no-loc text="Microsoft Teams Rooms"::: Geräten bereitstellen:::no-loc text="Microsoft Monitoring":::, auf die Sie physischen Zugriff haben, und diese Testgeräte erhalten, um einige Daten zu generieren und an den :::no-loc text="Log Analytics"::: Arbeitsbereich zu übertragen.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installieren von :::no-loc text="Microsoft Monitoring"::: Agents zum Testen von Geräten

Stellen Sie den :::no-loc text="Microsoft Monitoring"::: Agent auf den Testgeräten bereit, indem Sie die Anweisungen in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows)verwenden. Dieser Artikel enthält ausführliche Informationen zu den Schritten zum Bereitstellen des :::no-loc text="Microsoft Monitoring"::: Agents für :::no-loc text="Windows":::, Anweisungen zum Abrufen der :::no-loc text="Log Analytics"::: ***Arbeitsbereichs-ID** _ und des _ *_primärschlüssels_**, um Geräte zu erhalten :::no-loc text="Microsoft Teams Rooms"::: , die mit Ihrer :::no-loc text="Azure Monitor"::: Bereitstellung verbunden sind, sowie Schritte zum Überprüfen der Agentkonnektivität mit :::no-loc text="Log Analytics"::: der Instanz.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generieren von Beispielereignissen :::no-loc text="Microsoft Teams Rooms":::

Überprüfen Sie nach der Bereitstellung des :::no-loc text="Microsoft Monitoring"::: Agents auf den Testgeräten, ob die erforderlichen Ereignisprotokolldaten von :::no-loc text="Azure Monitor":::erfasst werden.

> [!NOTE]
> Starten Sie das Gerät nach der Installation des :::no-loc text="Microsoft Monitoring"::: Agents neu, und stellen Sie sicher, dass die :::no-loc text="Microsoft Teams Rooms"::: Besprechungs-App gestartet wird, damit neue Ereignisse im Ereignisprotokoll generiert werden können.

1.  Melden Sie sich beim [:::no-loc text="Microsoft Azure"::: Portal](https://portal.azure.com) an, und wechseln Sie zu :::no-loc text="Log Analytics"::: Ihrem Arbeitsbereich, und wählen Sie sie aus.

2.  Auflisten der von einem :::no-loc text="Microsoft Teams Rooms"::: Gerät generierten Taktereignisse:
    1.  Wählen Sie Ihren Arbeitsbereich aus, wechseln Sie zu **"Protokolle"** , und verwenden Sie eine Abfrage, um die Taktdatensätze abzurufen, die die benutzerdefinierten Felder für :::no-loc text="Microsoft Teams Rooms":::enthalten.
    2.  Beispielabfrage: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Stellen Sie sicher, dass die Abfrage Protokolldatensätze zurückgibt, die von der :::no-loc text="Microsoft Teams Rooms"::: Besprechungs-App generierte Ereignisse enthalten.

4.  Generieren Sie ein Hardwareproblem, und überprüfen Sie, ob die erforderlichen Ereignisse angemeldet :::no-loc text="Azure Log Analytics":::sind.
    1.  Trennen Sie eines der Peripheriegeräte im Testsystem :::no-loc text="Microsoft Teams Rooms"::: . Dies kann die Kamera, der Lautsprecher, das Mikrofon oder das Front room Display sein.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll in :::no-loc text="Azure Log Analytics":::gefüllt ist.
    3.  Verwenden Sie eine Abfrage zum Auflisten von Hardwarefehlerereignissen: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Generieren Sie ein Anwendungsproblem, und überprüfen Sie, ob die erforderlichen Ereignisse protokolliert werden.
    1.  Ändern Sie die :::no-loc text="Microsoft Teams Rooms"::: Kontokonfiguration, und geben Sie ein falsches Email/Kennwortpaar ein.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll in :::no-loc text="Azure Log Analytics":::gefüllt ist.
    3.  Verwenden Sie eine Abfrage zum Auflisten von Anwendungsfehlerereignissen: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Diese Beispielereignisprotokolle sind erforderlich, bevor benutzerdefinierte Felder konfiguriert werden können. Fahren Sie erst mit dem nächsten Schritt fort, wenn Sie die erforderlichen Ereignisprotokolle gesammelt haben.

## <a name="map-custom-fields"></a>Zuordnen benutzerdefinierter Felder
<a name="Custom_fields"> </a>

Sie verwenden benutzerdefinierte Felder, um bestimmte Daten aus den Ereignisprotokollen zu extrahieren. Sie müssen benutzerdefinierte Felder definieren, die später mit Ihren Kacheln, Dashboardansichten und Warnungen verwendet werden. Sehen Sie [sich benutzerdefinierte Felder an :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) , und machen Sie sich mit den Konzepten vertraut, bevor Sie mit dem Erstellen ihrer benutzerdefinierten Felder beginnen.

Führen Sie die folgenden Schritte aus, um ihre benutzerdefinierten Felder aus den erfassten Ereignisprotokollen zu extrahieren:

1.  Melden Sie sich beim [:::no-loc text="Microsoft Azure"::: Portal](https://portal.azure.com) an, und wechseln Sie zu :::no-loc text="Log Analytics"::: Ihrem Arbeitsbereich, und wählen Sie sie aus.

2. Auflisten der von einem :::no-loc text="Microsoft Teams Rooms"::: Gerät generierten Ereignisse:
   1.  Wechseln Sie zu **"Protokolle"** , und verwenden Sie eine Abfrage, um die Datensätze abzurufen, die das benutzerdefinierte Feld enthalten.
   2.  Beispielabfrage: `Event | where Source == "SRS-App" and EventID == 2000`

3. Wählen Sie einen der Datensätze aus, wählen Sie die Schaltfläche links aus, und starten Sie den Feldextraktions-Assistenten.
4. Markieren Sie die Daten, die Sie aus der RenderedDescription extrahieren möchten, und geben Sie einen Feldtitel an. Die Feldnamen, die Sie verwenden sollten, sind in Tabelle 1 angegeben.
5. Verwenden Sie die in *Tabelle 1* gezeigten Zuordnungen. :::no-loc text="Log Analytics"::: fügt die **\_CF-Zeichenfolge** automatisch an, wenn Sie das neue Feld definieren.

> [!IMPORTANT]
> Denken Sie daran, dass bei allen JSON- und :::no-loc text="Log Analytics"::: Feldern die Groß-/Kleinschreibung beachtet wird.
> 
> Achten Sie auf die Abfragen, die für jedes benutzerdefinierte Feld in der folgenden Tabelle erforderlich sind. Sie müssen die richtigen Abfragen :::no-loc text="Log Analytics"::: verwenden, um benutzerdefinierte Feldwerte erfolgreich zu extrahieren.
> 
**Tabelle 1**

| **JSON-Feld**                   | **:::no-loc text="Log Analytics"::: Benutzerdefiniertes Feld** | **Ereigniskennung** | **Abfrage, die mit der Extraktion verwendet werden soll**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Beschreibung                      | SRSEventDescription         | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| Version des Betriebssystems                        | SRSOSLongVersion            | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 2000 |
| Status des Konferenzmikrofons     | SRSConfMicrophoneStatus     | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Konferenzsprecherstatus        | SRSConfSpeakerStatus        | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Standardlautsprecherstatus           | SRSDefaultSpeakerStatus     | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Kamerastatus                    | SRSCameraStatus             | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Status der Anzeige vor dem Raum     | SRSFORDStatus               | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Status des Bewegungssensors             | SRSMotionSensorStatus       | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| HDMI-Aufnahmestatus               | SRSHDMIIngestStatus         | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definieren der :::no-loc text="Microsoft Teams Rooms"::: Ansichten in :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Nachdem Daten gesammelt und benutzerdefinierte Felder zugeordnet wurden, können Sie den Ansichts-Designer verwenden, um ein Dashboard zu entwickeln, das verschiedene Kacheln zum Überwachen :::no-loc text="Microsoft Teams Rooms"::: von Ereignissen enthält. Erstellen Sie mit dem Ansicht-Designer die folgenden Kacheln. Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Ansichten mithilfe des Ansichts-Designers in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Die vorherigen Schritte in diesem Handbuch sollten ausgeführt worden sein, damit die Dashboardkacheln ordnungsgemäß funktionieren.
>
> [!IMPORTANT]
> [Der Ansichts-Designer in Azure Monitor wird am 31. August 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) eingestellt, und die Funktionen zum Erstellen und Klonen wurden am 30. November 2020 deaktiviert. Stattdessen können Arbeitsmappen verwendet werden. Weitere Informationen zum Leitfaden für den Übergang des Ansichts-Designers zu Arbeitsmappen finden Sie in der [Schnellstartanleitung mit voreingestellten Ansichts-Designervorlagen](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Manuelles Erstellen eines Microsoft Teams-Räume-Dashboards

Alternativ können Sie ein eigenes Dashboard erstellen und nur die Kacheln hinzufügen, die Sie überwachen möchten.

#### <a name="configure-the-overview-tile"></a>Konfigurieren der Kachel "Übersicht"

1.  Öffnen **Sie den Ansichts-Designer**.
2.  Wählen Sie " **Übersicht kachel**" und dann **"Zwei Zahlen** " aus dem Katalog aus.
3.  Benennen Sie die Kachel **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Definieren Sie die **erste Kachel**:<br>
    **Legende:** Geräte, die mindestens einmal innerhalb des letzten Monats einen Takt gesendet haben<br>
    **Abfrage:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definieren Sie die **zweite Kachel**:<br>
    **Legende:** Aktive Geräte, die innerhalb der letzten Stunde einen Takt gesendet haben<br>
    **Abfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Wählen Sie **"Übernehmen" aus**.

### <a name="create-a-tile-that-displays-active-devices"></a>Erstellen einer Kachel, die aktive Geräte anzeigt

1.  Wählen Sie **"Dashboard anzeigen** " aus, um mit dem Hinzufügen Ihrer Kacheln zu beginnen.
2.  Wählen Sie **& Liste** im Katalog aus.
3.  Definieren Sie die **Eigenschaften "Allgemein** ":<br>
    **Gruppentitel:** Taktstatus<br>
    **Neue Gruppe:** Ausgewählten
4.  Definieren Sie die **Kacheleigenschaften** :<br>
    **Legende:** Aktive Geräte (Takt, der in den letzten 20 Minuten gesendet wurde)<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definieren Sie die **Listeneigenschaften** :<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  **Spaltentitel definieren**:<br>
    **Namen:** Computername<br>
    **Wert:** Letzter Takt
7.  Definieren Sie **die Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **"Übernehmen"** und dann **"Schließen**" aus.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Erstellen einer Kachel, die Geräte mit Verbindungsproblemen anzeigt

1.  Wählen Sie **"Zahl" & Liste** aus dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften "Allgemein** ":<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kacheleigenschaften** :<br>
    **Legende:** Inaktive Geräte (keine Taktnachricht, die in den letzten 20 Minuten gesendet wurde)<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definieren Sie die **Listeneigenschaften** :<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  **Spaltentitel definieren**:<br>
    **Namen:** Computername<br>
    **Wert:** Letzter Takt
6.  **Navigationsabfrage** definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie **"Übernehmen"** und dann **"Schließen**" aus.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Erstellen einer Kachel, die Geräte anzeigt, die einen Hardwarefehler aufweisen

1.  Wählen Sie **"Zahl" & Liste** aus dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften "Allgemein** ":<br>
    **Gruppentitel:** Hardwarestatus<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Kacheleigenschaften** :<br>
    **Legende:** Geräte, bei denen in der letzten Stunde ein Hardwarefehler aufgetreten ist<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften** :<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  **Spaltentitel definieren**:<br>
    **Namen:** Computername<br>
    **Wert:** Letzter Fehler
6.  **Navigationsabfrage** definieren:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie **"Übernehmen"** und dann **"Schließen**" aus.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Erstellen einer Kachel, die Betriebssystemversionen anzeigt :::no-loc text="Microsoft Teams Rooms":::

1.  Wählen Sie **donut & Liste** aus dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften "Allgemein** ":<br>
    **Gruppentitel:** Betriebssystemdetails<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Headereigenschaften** :<br>
    **Titel:** Betriebssystemversionen<br>
    **Untertitel:** Geräte mit bestimmten Betriebssystemversionen
4.  Definieren Sie die **Donut-Eigenschaften** :<br>
    **Abfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Text zentrieren:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie die **Listeneigenschaften** .<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Grafik ausblenden:** Ausgewählten<br>
    **Sparklines aktivieren:** Nicht ausgewählt
6.  **Spaltentitel definieren**.<br>
    **Namen:** Computername<br>
    **Wert:** Leer lassen
7.  Definieren Sie **die Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **"Übernehmen"** und dann **"Schließen**" aus.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Erstellen einer Kachel, die Anwendungsversionen anzeigt :::no-loc text="Microsoft Teams Rooms":::

1.  Wählen Sie **donut & Liste** aus dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften "Allgemein** ":<br>
    **Gruppentitel:** :::no-loc text="Microsoft Teams Rooms"::: Anwendungsdetails<br>
    **Neue Gruppe:** Ausgewählten
3.  Definieren Sie die **Headereigenschaften** :<br>
    **Titel:** Anwendungsversionen<br>
    **Untertitel:** Geräte mit bestimmten Anwendungsversionen
4.  Definieren Sie die **Donut-Eigenschaften** :<br>
    **Abfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Text zentrieren:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie die **Listeneigenschaften** .<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Grafik ausblenden:** Ausgewählten<br>
    **Sparklines aktivieren:** Nicht ausgewählt
6.  **Spaltentitel definieren**.<br>
    **Namen:** Computername<br>
    **Wert:** Leer lassen
7.  Definieren Sie **die Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen Sie **"Übernehmen"** und dann **"Schließen**" aus.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Erstellen einer Kachel, die Geräte anzeigt, die einen Anwendungsfehler aufweisen

1.  Wählen Sie **"Zahl" & Liste** aus dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften "Allgemein** ".<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kacheleigenschaften** .<br>
    **Legende:** Geräte, bei denen in der letzten Stunde ein Anwendungsfehler aufgetreten ist<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften** .<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  **Spaltentitel definieren**.<br>
    **Namen:** Computername<br>
    **Wert:** Letzter Fehler
6.  Definieren Sie **die Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen Sie **"Übernehmen"** und dann **"Schließen**" aus.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Erstellen einer Kachel, die neu gestartete Geräte anzeigt

1.  Wählen Sie **"Zahl" & Liste** aus dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften "Allgemein** ".<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kacheleigenschaften** .<br>
    **Legende:** Geräte, auf denen die Anwendung in den letzten 24 Stunden neu gestartet wurde, und Anzahl der Neustarts<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften** .<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  **Spaltentitel definieren**.<br>
    **Namen:** Computername<br>
    **Wert:** Anzahl der Neustarts
6.  Definieren Sie **die Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen Sie **"Übernehmen"** und dann **"Schließen**" aus.
8.  Wählen Sie **"Speichern"** aus, um Ihr Dashboard zu speichern.

Jetzt haben Sie die Erstellung Ihrer Ansichten abgeschlossen.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Konfigurieren von Warnungen in :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: kann Warnungen auslösen, um die Administratoren zu benachrichtigen, wenn eine :::no-loc text="Microsoft Teams Rooms"::: Konsole auf ein Problem stößt.

:::no-loc text="Azure Monitor"::: enthält einen integrierten Benachrichtigungsmechanismus, der geplante Protokollsuchen in regelmäßigen Abständen durchläuft. Wenn die Ergebnisse der Protokollsuche bestimmten Kriterien entsprechen, wird ein Warnungsdatensatz erstellt.

Die Regel kann dann automatisch eine oder mehrere Aktionen ausführen, um Sie proaktiv über die Warnung zu benachrichtigen oder einen anderen Prozess aufzurufen. Mögliche Optionen für Warnungen sind:
-   Senden einer E-Mail
-   Aufrufen eines externen Prozesses über eine HTTP POST-Anforderung
-   Starten eines Runbook im :::no-loc text="Azure Automation"::: Dienst

Weitere Informationen zu den [Warnungen in finden Sie unter "Protokollbenachrichtigungen" in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) :::no-loc text="Azure Monitor":::.

> [!NOTE]
> In den folgenden Beispielen werden E-Mail-Benachrichtigungen gesendet, wenn ein :::no-loc text="Microsoft Teams Rooms"::: Gerät eine Hardware oder einen Anwendungsfehler generiert.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Konfigurieren einer E-Mail-Benachrichtigung für :::no-loc text="Microsoft Teams Rooms"::: Hardwareprobleme

Konfigurieren Sie eine Warnungsregel, die nach Geräten sucht :::no-loc text="Microsoft Teams Rooms"::: , bei denen innerhalb der letzten Stunde Hardwareprobleme aufgetreten sind.
1.  Melden Sie sich beim [:::no-loc text="Microsoft Azure"::: Portal](https://portal.azure.com) an, und wechseln Sie zu :::no-loc text="Log Analytics"::: Ihrem Arbeitsbereich, und wählen Sie sie aus.

2. Navigieren Sie zu Ihrem :::no-loc text="Log Analytics"::: Arbeitsbereich, wählen Sie **"Warnungen**" und dann "**Neue Warnungsregel**" aus.

3. Wählen Sie **"Bedingung hinzufügen"** und dann **"Benutzerdefinierte Protokollsuche"** aus.

4.  Geben Sie die folgende Abfrage in das Textfeld der Suchabfrage ein.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Konfigurieren Sie die Einstellungen für die Warnungslogik:<br>
    **Basierend auf:** Anzahl der Ergebnisse<br>
    **Zustand:** Größer als<br>
    **Schwellenwert:** 0<br>

6. Konfigurieren Sie die Auswertungseinstellungen, und wählen Sie **"Fertig" aus**: <br>
    **Zeitraum (in Minuten):** 60<br>
    **Häufigkeit (in Minuten):** 60<br>

7. Konfigurieren von Aktionsgruppen:
    1.  Wählen Sie **"Neu erstellen" aus.**
    2.  Geben Sie geeignete Namen für die Felder " *Aktionsgruppe"* und " *Kurzname" an* .
    3.  Geben Sie einen eindeutigen *Aktionsnamen* an, wählen Sie **Email/SMS/Push/Voice** und dann **"Details bearbeiten"** aus.
    4.  Aktivieren Sie das Kontrollkästchen **Email**, und geben Sie die E-Mail-Adresse der Person oder Gruppe an, die die Benachrichtigungen erhalten soll.
    5.  Sie können auch Ihre Telefonnummer angeben, um per SMS, einem Sprachanruf oder beidem benachrichtigt zu werden.
    6. Wählen Sie **"OK**" aus.

8. **Passen Sie Aktionen** an, wenn Sie die Betreffzeile der Benachrichtigungs-E-Mails überschreiben möchten.

9. Geben Sie einen Regelnamen und eine Beschreibung an.<br>
    **Regelname:** :::no-loc text="Microsoft Teams Rooms"::: Hardwarefehlerwarnung<br>
    **Beschreibung:** Liste der Geräte, bei denen innerhalb der letzten Stunde ein Hardwareproblem aufgetreten ist<br>

10. Wählen Sie den beabsichtigten Schweregrad aus, und stellen Sie sicher, dass die Regel aktiviert ist.

11. Wählen Sie **"Warnungsregel erstellen**" aus.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Konfigurieren einer E-Mail-Warnung für :::no-loc text="Microsoft Teams Rooms"::: Anwendungsprobleme

Wiederholen Sie dasselbe Verfahren, verwenden Sie jedoch die folgende Abfrage, um Geräte auflisten, bei denen in der letzten Stunde Anwendungsprobleme aufgetreten sind.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Jetzt haben Sie die Definition von Warnungen abgeschlossen. Sie können zusätzliche Warnungen mithilfe der obigen Beispiele definieren.

Wenn eine Benachrichtigung generiert wird, erhalten Sie eine E-Mail, in der die Geräte aufgelistet werden, bei denen innerhalb der letzten Stunde ein Problem aufgetreten ist.

! [Beispielbenachrichtigungs-E-Mail :::no-loc text="Azure Monitor"::: ](.. /media/Deploy-Azure-Monitor-6.png "Beispielbenachrichtigungs-E-Mail :::no-loc text="Azure Monitor"::: ")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Konfigurieren aller Geräte für :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Nachdem die Dashboards und Warnungen konfiguriert wurden, können Sie den Agent auf allen :::no-loc text="Microsoft Teams Rooms"::: Geräten einrichten und konfigurieren:::no-loc text="Microsoft Monitoring":::, um ihre Überwachungsbereitstellung abzuschließen.

Obwohl Sie den :::no-loc text="Microsoft Monitoring"::: Agent manuell auf jedem Gerät installieren und konfigurieren können, wird dringend empfohlen, vorhandene Softwarebereitstellungstools und -methoden zu nutzen.

Wenn Sie Ihre :::no-loc text="Microsoft Teams Rooms"::: Geräte zum ersten Mal erstellen, sollten Sie die :::no-loc text="Microsoft Monitoring"::: Einrichtungs- und Konfigurationsschritte des Agents als Teil des Buildprozesses einbeziehen. Weitere Informationen finden Sie unter [Installieren des Agents mithilfe der Befehlszeile](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Bereitstellen des :::no-loc text="Microsoft Monitoring"::: Agents mithilfe eines Gruppenrichtlinie-Objekts (GPO)

Wenn Sie Ihre :::no-loc text="Microsoft Teams Rooms"::: Geräte bereits vor der Implementierung :::no-loc text="Azure Monitoring":::bereitgestellt haben, können Sie das bereitgestellte Skript verwenden, um die Agents mithilfe :::no-loc text="Active Directory"::: von Gruppenrichtlinienobjekten einzurichten und zu konfigurieren.

1.  Erstellen Sie einen freigegebenen Netzwerkpfad, und gewähren Sie der Gruppe **"Domänencomputer** " Lesezugriff.

2.  Laden Sie die 64-Bit-Version des :::no-loc text="Microsoft Monitoring"::: Agents von :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrahieren Sie den Inhalt des Setuppakets in die Netzwerkfreigabe.
    1.  Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie dann **MMASetup-AMD64.exe /c** aus.
    2.  Geben Sie die soeben erstellte Freigabe an, und extrahieren Sie den Inhalt.

4.  Erstellen Sie ein neues Gruppenrichtlinie-Objekt, und weisen Sie es der Organisationseinheit zu, in :::no-loc text="Microsoft Teams Rooms"::: der sich Computerkonten befinden.

5.  Konfigurieren der PowerShell-Ausführungsrichtlinie:
    1.  Bearbeiten Sie das neu erstellte Gruppenrichtlinie-Objekt, und navigieren Sie zu Komponenten für administrative Vorlagen \\ :::no-loc text="Windows"::: für Computerkonfigurationsrichtlinien \\ \\.\\ :::no-loc text="Windows PowerShell":::
    2.  Aktivieren Sie die **Skriptausführung aktivieren** und legen Sie die **Ausführungsrichtlinie** auf **"Lokale Skripts zulassen**" fest.

6.  Konfigurieren Sie das Startskript:
    1.  Kopieren Sie das folgende Skript, und speichern Sie es als Install-MMAgent.ps1.
    2.  Ändern Sie die Parameter WorkspaceId, WorkspaceKey und SetupPath so, dass sie Ihrer Konfiguration entsprechen.
    3.  Bearbeiten Sie dasselbe Gruppenrichtlinie-Objekt, und navigieren Sie zu Einstellungsskripts für Computerkonfigurationsrichtlinien \\ \\ :::no-loc text="Windows"::: \\ (Start/Herunterfahren)
    4.  Doppelklicken Sie, um **"Start**" auszuwählen, und wählen Sie dann **PowerShell-Skripts** aus.
    5.  Wählen Sie **"Dateien anzeigen"** aus, und kopieren Sie dann die **Install-MMAgent.ps1** Datei in diesen Ordner.
    6.  Wählen Sie **"Hinzufügen"** und dann **"Durchsuchen"** aus.
    7.  Wählen Sie das ps1-Skript aus, das Sie gerade kopiert haben.

7.  :::no-loc text="Microsoft Teams Rooms"::: sollte den Agent mit dem :::no-loc text="Microsoft Monitoring"::: zweiten Neustart installieren und konfigurieren.

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
> Sie können auf den Artikel ["Verwalten und Verwalten des :::no-loc text="Log Analytics"::: Agents](/azure/azure-monitor/platform/agent-manage) " verweisen, wenn Sie einen Agent neu konfigurieren, in einen anderen Arbeitsbereich verschieben oder Proxyeinstellungen nach der Erstinstallation ändern müssen.

## <a name="additional-solutions"></a>Zusätzliche Lösungen
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: bietet integrierte Verwaltungslösungen über den [Lösungskatalog](/azure/azure-monitor/insights/solutions) , um Ihre Umgebung weiter zu überwachen. Es wird dringend empfohlen, dass Sie Ihrem Arbeitsbereich auch [Warnungsverwaltungs-](/azure/azure-monitor/platform/alert-management-solution) und [:::no-loc text="Azure Log Analytics"::: Agent-Integritätslösungen](/azure/azure-monitor/insights/solution-agenthealth) hinzufügen.

> [!NOTE]
> Die Agent-Integritätslösung kann Ihnen helfen, veraltete oder fehlerhafte :::no-loc text="Microsoft Monitoring"::: Agents in Ihrer Umgebung zu identifizieren, und die Warnungsverwaltungslösung enthält Details zu den Warnungen, die innerhalb eines bestimmten Zeitraums ausgelöst wurden.

## <a name="see-also"></a>Siehe auch

[Planen der :::no-loc text="Microsoft Teams Rooms"::: Verwaltung mit :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Verwalten von :::no-loc text="Microsoft Teams Rooms"::: Geräten mit :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
