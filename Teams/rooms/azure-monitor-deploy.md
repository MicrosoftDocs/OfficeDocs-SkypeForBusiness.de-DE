---
title: Bereitstellen Microsoft Teams-Räume Überwachungsüberwachung mit Azure Monitor
ms.author: czawideh
author: cazawideh
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
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: In diesem Artikel wird erläutert, wie Sie die Überwachung ihrer Microsoft Teams-Räume mit Azure Monitor in einer integrierten End-to-End-Weise bereitstellen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b991465bfff8f67fdbd3bdc9c03eba485690d5fb
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503872"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Bereitstellen der :::no-loc text="Microsoft Teams Rooms"::: Überwachung mit :::no-loc text="Azure Monitor":::

In diesem Artikel wird beschrieben, wie Sie integrierte End-to-End-Überwachung von Geräten :::no-loc text="Microsoft Teams Rooms"::: mithilfe von einrichten und bereitstellen :::no-loc text="Azure Monitor":::.

Sie können innerhalb von :::no-loc text="Log Analytics"::: konfigurieren :::no-loc text="Azure Monitor"::: , um einfache Telemetrie und Warnungen zur Verwaltung von bereitstellen :::no-loc text="Microsoft Teams Rooms":::. Wenn Ihre Managementlösung reift, können Sie zusätzliche Daten- und Verwaltungsfunktionen bereitstellen, um eine detailliertere Ansicht der Geräteverfügbarkeit und -leistung zu erstellen.

Durch Folgen dieses Leitfadens können Sie ein Dashboard wie das folgende Beispiel verwenden, um detaillierte Statusberichte zur Geräteverfügbarkeit, Anwendungs- und Hardwarestatus sowie :::no-loc text="Microsoft Teams Rooms"::: Anwendungs- und Betriebssystemversionsverteilung zu erhalten.

![Screenshot der Beispielansicht "Protokollanalyse" für Microsoft Teams-Räume.](../media/Deploy-Azure-Monitor-1.png "Beispielansicht für die Protokollanalyse für Microsoft Teams-Räume")

Allgemein müssen Sie die folgenden Aufgaben ausführen:


1. [Überprüfen der :::no-loc text="Log Analytics"::: Konfiguration](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Konfigurieren von Testgeräten für die Verwaltung :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#configure_test_devices)
3. [Zuordnen benutzerdefinierter Felder](azure-monitor-deploy.md#Custom_fields)
4. [Definieren Sie die :::no-loc text="Microsoft Teams Rooms"::: Ansichten in :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definieren von Warnungen](azure-monitor-deploy.md#Alerts)
6. [Konfigurieren aller Geräte für die Überwachung](azure-monitor-deploy.md#configure_all_devices)
7. [Konfigurieren zusätzlicher :::no-loc text="Azure Monitor"::: Lösungen](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Obwohl sie mit einer minimalen Konfiguration einen Computer überwachen kann, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: auf dem ein Betriebssystem ausgeführt wird, :::no-loc text="Microsoft Teams Rooms":::müssen Sie dennoch einige spezifische Schritte ausführen, bevor Sie mit der Bereitstellung von Agents auf allen Geräten :::no-loc text="Microsoft Teams Rooms"::: beginnen.
> Daher wird dringend empfohlen, alle Konfigurationsschritte in der richtigen Reihenfolge für eine kontrollierte Einrichtung und Konfiguration durchzuführen. Die Qualität des Endergebniss hängt stark von der Qualität der Anfänglichen Konfiguration ab.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Überprüfen der :::no-loc text="Log Analytics"::: Konfiguration
<a name="validate_LogAnalytics"> </a>

Sie benötigen einen Arbeitsbereich, um :::no-loc text="Log Analytics"::: mit dem Sammeln von Protokollen von zu beginnen :::no-loc text="Microsoft Teams Rooms":::. Ein Arbeitsbereich ist eine einzigartige Umgebung :::no-loc text="Log Analytics"::: mit einem eigenen Datenrepository, Datenquellen und Lösungen. Wenn Sie bereits über einen vorhandenen :::no-loc text="Log Analytics"::: Arbeitsbereich verfügen, :::no-loc text="Microsoft Teams Rooms"::: können Sie ihn zum Überwachen der Bereitstellung verwenden, oder Sie können alternativ einen dedizierten Arbeitsbereich erstellen, :::no-loc text="Log Analytics"::: der Ihren :::no-loc text="Microsoft Teams Rooms"::: Überwachungsanforderungen entspricht.

Wenn Sie einen neuen Arbeitsbereich erstellen müssen :::no-loc text="Log Analytics"::: , folgen Sie den Anweisungen im Artikel Erstellen [eines :::no-loc text="Log Analytics"::: Arbeitsbereichs im Portal :::no-loc text="Azure"::: .](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Um mit :::no-loc text="Log Analytics"::: verwenden zu :::no-loc text="Azure Monitor":::können, müssen Sie über ein aktives Abonnement :::no-loc text="Azure"::: verfügen. Wenn Sie nicht über ein Abonnement :::no-loc text="Azure"::: verfügen, können Sie als Ausgangspunkt [](https://azure.microsoft.com/free) ein kostenloses Testabonnement erstellen.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Konfigurieren für :::no-loc text="Log Analytics"::: die Erfassung von Ereignisprotokollen :::no-loc text="Microsoft Teams Rooms":::

:::no-loc text="Log Analytics"::: erfasst nur Ereignisse aus den :::no-loc text="Windows"::: Ereignisprotokollen, die in den Einstellungen angegeben sind. Für jedes Protokoll werden nur die Ereignisse mit den ausgewählten Schweregraden erfasst.

Sie müssen konfigurieren, um :::no-loc text="Log Analytics"::: die Protokolle zu erfassen, die zum Überwachen des Geräte- :::no-loc text="Microsoft Teams Rooms"::: und Anwendungsstatus erforderlich sind. :::no-loc text="Microsoft Teams Rooms"::: verwenden Sie das **:::no-loc text="Skype Room System":::** Ereignisprotokoll.

Informationen zum Konfigurieren :::no-loc text="Log Analytics"::: der Ereignisersammelung :::no-loc text="Microsoft Teams Rooms"::: finden Sie unter [:::no-loc text="Windows"::: Datenquellen für Ereignisprotokolle in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)

![Screenshot der Einstellungen für das Ereignisprotokoll](../media/Deploy-Azure-Monitor-2.png "Einstellungen des Ereignisprotokolls")

> [!IMPORTANT]
> Konfigurieren :::no-loc text="Windows"::: Sie die Einstellungen für das Ereignisprotokoll, geben **:::no-loc text="Skype Room System":::** Sie als Ereignisprotokollnamen ein, und aktivieren Sie dann die Kontrollkästchen **Fehler, Warnung** **und Informationen**.

## <a name="configure-test-devices-for-azure-monitoring"></a>Konfigurieren von Testgeräten für Azure Monitoring
<a name="configure_test_devices"> </a>

Sie müssen die Überwachung :::no-loc text="Log Analytics"::: von Ereignissen im Zusammenhang mit der :::no-loc text="Microsoft Teams Rooms":::Überwachung vorbereiten. Zunächst müssen Sie :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: Agents auf einem oder zwei Geräten bereitstellen, auf die Sie physischen Zugriff haben. Mit diesen Testgeräten können Sie Daten generieren und an den Arbeitsbereich :::no-loc text="Log Analytics"::: übertragen.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installieren von :::no-loc text="Microsoft Monitoring"::: Agents zum Testen von Geräten

Stellen Sie den :::no-loc text="Microsoft Monitoring"::: Agent auf den Testgeräten bereit, indem Sie die Anweisungen unter [:::no-loc text="Windows"::: Verbinden dem Dienst :::no-loc text="Log Analytics"::: in befolgen:::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). :::no-loc text="Microsoft Monitoring"::: Dieser Artikel enthält detaillierte Informationen zu den Schritten zum Bereitstellen des Agents :::no-loc text="Windows":::für , *:::no-loc text="Log Analytics"::: Anweisungen zum Beziehen der Arbeitsbereichs-ID_ und des _ *_primärschlüssels_**:::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::, um Geräte mit Ihrer Bereitstellung zu verbinden, sowie Schritte zum Überprüfen der Agentkonnektivität:::no-loc text="Log Analytics"::: mit Instanz.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generieren von Beispielereignissen :::no-loc text="Microsoft Teams Rooms":::

Nachdem der :::no-loc text="Microsoft Monitoring"::: Agent auf den Testgeräten bereitgestellt wurde, überprüfen Sie, ob die erforderlichen Ereignisprotokolldaten von gesammelt werden :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Starten Sie das Gerät nach der Installation :::no-loc text="Microsoft Monitoring"::: des Agents neu, und stellen Sie sicher, :::no-loc text="Microsoft Teams Rooms"::: dass die Besprechungs-App gestartet wird, damit neue Ereignisse im Ereignisprotokoll generiert werden können.

1.  Melden Sie sich beim Portal [an:::no-loc text="Microsoft Azure":::,](https://portal.azure.com) wechseln Sie zu, :::no-loc text="Log Analytics"::: und wählen Sie Ihren Arbeitsbereich aus.

2.  Auflisten der von einem Gerät generierten Heartbeat-Ereignisse :::no-loc text="Microsoft Teams Rooms"::: :
    1.  Wählen Sie Ihren Arbeitsbereich aus, wechseln Sie zu **Protokolle** , und verwenden Sie eine Abfrage, um die Heartbeat-Datensätze abzurufen, die die benutzerdefinierten Felder für enthalten :::no-loc text="Microsoft Teams Rooms":::sollen.
    2.  Beispielabfrage: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Stellen Sie sicher, dass die Abfrage Protokolldatensätze zurückgibt, die von der Besprechungs-App generierte :::no-loc text="Microsoft Teams Rooms"::: Ereignisse enthalten.

4.  Generieren Sie ein Hardwareproblem, und überprüfen Sie, ob die erforderlichen Ereignisse bei angemeldet sind :::no-loc text="Azure Log Analytics":::.
    1.  Trennen Sie eines der Peripheriegeräte aus dem Testsystem :::no-loc text="Microsoft Teams Rooms"::: . Dies kann die Kamera, der Lautsprecher, das Mikrofon oder die Anzeige im Vorderraum sein.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll in ausgefüllt wurde :::no-loc text="Azure Log Analytics":::.
    3.  Verwenden Sie eine Abfrage, um Hardwarefehlerereignisse auflisten: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Generieren Sie ein Anwendungsproblem, und überprüfen Sie, ob die erforderlichen Ereignisse protokolliert werden.
    1.  Ändern Sie :::no-loc text="Microsoft Teams Rooms"::: die Kontokonfiguration, und geben Sie ein falsches E-Mail-/Kennwortpaar ein.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll in ausgefüllt wurde :::no-loc text="Azure Log Analytics":::.
    3.  Verwenden Sie eine Abfrage zum Auflisten von Anwendungsfehlerereignissen: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Diese Beispielereignisprotokolle sind erforderlich, bevor benutzerdefinierte Felder konfiguriert werden können. Fahren Sie erst mit dem nächsten Schritt fort, wenn Sie die erforderlichen Ereignisprotokolle gesammelt haben.

## <a name="map-custom-fields"></a>Zuordnen benutzerdefinierter Felder
<a name="Custom_fields"> </a>

Sie verwenden benutzerdefinierte Felder, um bestimmte Daten aus den Ereignisprotokollen zu extrahieren. Sie müssen benutzerdefinierte Felder definieren, die später mit Ihren Kacheln, Dashboardansichten und Warnungen verwendet werden. Lesen [Sie Benutzerdefinierte Felder in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) , und machen Sie sich mit den Konzepten vertraut, bevor Sie mit dem Erstellen Ihrer benutzerdefinierten Felder beginnen.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierten Felder aus den erfassten Ereignisprotokollen zu extrahieren:

1.  Melden Sie sich beim Portal [an:::no-loc text="Microsoft Azure":::,](https://portal.azure.com) wechseln Sie zu, :::no-loc text="Log Analytics"::: und wählen Sie Ihren Arbeitsbereich aus.

2. Auflisten der von einem Gerät generierten :::no-loc text="Microsoft Teams Rooms"::: Ereignisse:
   1.  Wechseln Sie **zu Protokolle** , und verwenden Sie eine Abfrage, um die Datensätze abzurufen, die das benutzerdefinierte Feld enthalten sollen.
   2.  Beispielabfrage: `Event | where Source == "SRS-App" and EventID == 2000`

3. Wählen Sie einen der Datensätze aus, klicken Sie auf die Schaltfläche links, und starten Sie den Assistenten für die Feldextraktion.
4. Markieren Sie die Daten, die Sie aus "RenderedDescription" extrahieren möchten, und geben Sie einen Feldtitel an. Die Feldnamen, die Sie verwenden sollten, sind in Tabelle 1 angegeben.
5. Verwenden Sie die Zuordnungen in *Tabelle 1*. :::no-loc text="Log Analytics":::fügt die **CF-Zeichenfolge automatisch\_** an, wenn Sie das neue Feld definieren.

> [!IMPORTANT]
> Denken Sie daran, dass bei allen JSON- :::no-loc text="Log Analytics"::: und -Feldern die Zwischen- und Kleinschreibung beachtet wird.
> 
> Achten Sie auf die Abfragen, die für jedes benutzerdefinierte Feld in der folgenden Tabelle erforderlich sind. Sie müssen die richtigen Abfragen für verwenden, um :::no-loc text="Log Analytics"::: erfolgreich benutzerdefinierte Feldwerte zu extrahieren.
> 
**Tabelle 1**

| **JSON-Feld**                   | **:::no-loc text="Log Analytics"::: Benutzerdefiniertes Feld** | **Ereigniskennung** | **Abfrage zur Verwendung mit der Extraktion**                   |
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
| Konferenzmikrofonstatus     | SRSConfMicrophoneStatus     | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Konferenzlautsprecherstatus        | SRSConfSpeakerStatus        | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Standardlautsprecherstatus           | SRSDefaultSpeakerStatus     | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Kamerastatus                    | SRSCameraStatus             | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Status 'Vor dem Raum anzeigen'     | SRSFORDStatus               | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| Status des Bewegungssensors             | SRSMotionSensorStatus       | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |
| HDMI-Aufnahmestatus               | SRSHDMIIngestStatus         | **3001**     | Ereignis \| , bei dem Source == "SRS-App" und EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definieren Sie die :::no-loc text="Microsoft Teams Rooms"::: Ansichten in :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Nachdem Daten gesammelt und benutzerdefinierte Felder zugeordnet wurden, können Sie mit dem Ansichts-Designer ein Dashboard entwickeln, das verschiedene Kacheln zum Überwachen von Ereignissen :::no-loc text="Microsoft Teams Rooms"::: enthält. Erstellen Sie mit dem Ansicht-Designer die folgenden Kacheln. Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Ansichten mithilfe des Ansichts-Designers in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Die vorherigen Schritte in diesem Leitfaden sollten abgeschlossen worden sein, damit die Dashboardkacheln ordnungsgemäß funktionieren.
>
> [!IMPORTANT]
> [Der Ansichts-Designer in Azure Monitor wird am 31. August 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) fortgesetzt und die Funktionen zum Erstellen und Klonen wurden am 30. November 2020 deaktiviert. Stattdessen können Arbeitsmappen verwendet werden. Weitere Informationen zum Leitfaden zum Übergang von Ansichts-Designer zu Arbeitsmappen finden Sie unter [Schnellstart mit vordefinierten Ansichts-Designervorlagen](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Manuelles Erstellen Microsoft Teams-Räume Dashboards

Alternativ können Sie ein eigenes Dashboard erstellen und nur die Kacheln hinzufügen, die Sie überwachen möchten.

#### <a name="configure-the-overview-tile"></a>Konfigurieren der Kachel "Übersicht"

1.  Öffnen **Sie den Ansichts-Designer**.
2.  Wählen **Sie Übersichtskachel** und dann **Zwei Zahlen** aus dem Katalog aus.
3.  Geben Sie der Kachel den Namen **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Definieren der **ersten Kachel**:<br>
    **Legende:** Geräte, die innerhalb des letzten Monats mindestens einmal einen Herzschlag gesendet haben<br>
    **Abfrage:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definieren Sie die **zweite Kachel**:<br>
    **Legende:** Aktive Geräte, die innerhalb der letzten Stunde einen Herzschlag gesendet haben<br>
    **Abfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Wählen Sie **Übernehmen aus**.

### <a name="create-a-tile-that-displays-active-devices"></a>Erstellen einer Kachel, auf der aktive Geräte angezeigt werden

1.  Wählen Sie **Dashboard anzeigen aus** , um mit dem Hinzufügen Ihrer Kacheln zu beginnen.
2.  Wählen **Sie nummer & aus dem** Katalog aus.
3.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Heartbeat-Status<br>
    **Neue Gruppe:** Ausgewählt
4.  Definieren Sie die **Kacheleigenschaften** :<br>
    **Legende:** Aktive Geräte (Heartbeat, gesendet in den letzten 20 Minuten)<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definieren Sie die **Listeneigenschaften** :<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definieren **von Spaltentiteln**:<br>
    **Name:** Computername<br>
    **Wert:** Last Heartbeat
7.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen **Sie Übernehmen** und dann Schließen **aus**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Erstellen einer Kachel, auf der Geräte mit Verbindungsproblemen angezeigt werden

1.  Wählen **Sie & aus dem** Katalog Nummerieren aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kacheleigenschaften** :<br>
    **Legende:** Inaktive Geräte (keine Heartbeat-Nachricht, die in den letzten 20 Minuten gesendet wurde)<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definieren Sie die **Listeneigenschaften** :<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definieren **von Spaltentiteln**:<br>
    **Name:** Computername<br>
    **Wert:** Last Heartbeat
6.  **Navigationsabfrage definieren**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen **Sie Übernehmen** und dann Schließen **aus**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Erstellen einer Kachel, auf der Geräte mit einem Hardwarefehler angezeigt werden

1.  Wählen **Sie & aus dem** Katalog Nummerieren aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Hardwarestatus<br>
    **Neue Gruppe:** Ausgewählt
3.  Definieren Sie die **Kacheleigenschaften** :<br>
    **Legende:** Geräte, bei der in der letzten Stunde ein Hardwarefehler aufgetreten ist<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften** :<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren **von Spaltentiteln**:<br>
    **Name:** Computername<br>
    **Wert:** Letzter Fehler
6.  **Navigationsabfrage definieren**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen **Sie Übernehmen** und dann Schließen **aus**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Erstellen einer Kachel, auf der Betriebssystemversionen :::no-loc text="Microsoft Teams Rooms"::: angezeigt werden

1.  Wählen **Sie donut & aus** dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** Details zum Betriebssystem<br>
    **Neue Gruppe:** Ausgewählt
3.  Definieren Sie die **Headereigenschaften** :<br>
    **Titel:** Betriebssystemversionen<br>
    **Untertitel:** Geräte mit bestimmten Betriebssystemversionen
4.  Definieren Sie die **Donut-Eigenschaften** :<br>
    **Abfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Text zentrieren:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie die **Listeneigenschaften** .<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ausblenden Graph:** Ausgewählt<br>
    **Aktivieren von Sparklines:** Nicht ausgewählt
6.  Definieren **sie Spaltentitel**.<br>
    **Name:** Computername<br>
    **Wert:** Leer lassen
7.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen **Sie Übernehmen** und dann **Schließen aus**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Erstellen einer Kachel, auf der Anwendungsversionen :::no-loc text="Microsoft Teams Rooms"::: angezeigt werden

1.  Wählen **Sie donut & aus** dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften:<br>
    **Gruppentitel:** :::no-loc text="Microsoft Teams Rooms"::: Anwendungsdetails<br>
    **Neue Gruppe:** Ausgewählt
3.  Definieren Sie die **Headereigenschaften** :<br>
    **Titel:** Anwendungsversionen<br>
    **Untertitel:** Geräte mit bestimmten Anwendungsversionen
4.  Definieren Sie die **Donut-Eigenschaften** :<br>
    **Abfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Text zentrieren:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie die **Listeneigenschaften** .<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ausblenden Graph:** Ausgewählt<br>
    **Aktivieren von Sparklines:** Nicht ausgewählt
6.  Definieren **sie Spaltentitel**.<br>
    **Name:** Computername<br>
    **Wert:** Leer lassen
7.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen **Sie Übernehmen** und dann **Schließen aus**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Erstellen einer Kachel, auf der Geräte mit einem Anwendungsfehler angezeigt werden

1.  Wählen **Sie & aus dem** Katalog Nummerieren aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kacheleigenschaften** .<br>
    **Legende:** Geräte, bei der in der letzten Stunde ein Anwendungsfehler aufgetreten ist<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften** .<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren **sie Spaltentitel**.<br>
    **Name:** Computername<br>
    **Wert:** Letzter Fehler
6.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen **Sie Übernehmen** und dann **Schließen aus**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Erstellen einer Kachel, auf der neu gestartete Geräte angezeigt werden

1.  Wählen **Sie & aus dem** Katalog Nummerieren aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **allgemeinen** Eigenschaften.<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kacheleigenschaften** .<br>
    **Legende:** Geräte, auf denen die Anwendung in den letzten 24 Stunden neu gestartet wurde, und Anzahl der Neustarts<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften** .<br>
    **Listenabfrage:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definieren **sie Spaltentitel**.<br>
    **Name:** Computername<br>
    **Wert:** Anzahl der Neustarts
6.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen **Sie Übernehmen** und dann **Schließen aus**.
8.  Wählen Sie **Speichern** aus, um Ihr Dashboard zu speichern.

Jetzt haben Sie die Erstellung Ihrer Ansichten abgeschlossen.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Konfigurieren von Benachrichtigungen in :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: können Warnungen auslösen, um Administratoren zu benachrichtigen, wenn bei einer :::no-loc text="Microsoft Teams Rooms"::: Konsole ein Problem auftreten.

:::no-loc text="Azure Monitor"::: enthält einen integrierten Warnungsmechanismus, der planmäßige Protokollsuchen in regelmäßigen Intervallen durch führt. Wenn die Ergebnisse der Protokollsuche bestimmten Kriterien entsprechen, wird ein Warnungsdatensatz erstellt.

Die Regel kann dann automatisch eine oder mehrere Aktionen ausführen, um Sie proaktiv über die Warnung zu benachrichtigen oder einen anderen Prozess auf aufruft. Mit Benachrichtigungen stehen die folgenden Optionen zur Verfügung:
-   Senden einer E-Mail
-   Aufrufen eines externen Prozesses über eine HTTP POST-Anforderung
-   Starten eines Runbook im :::no-loc text="Azure Automation"::: Dienst

Weitere [Informationen zu den Benachrichtigungen in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) :::no-loc text="Azure Monitor":::finden Sie unter Anmelden.

> [!NOTE]
> Die folgenden Beispiele senden E-Mail-Benachrichtigungen :::no-loc text="Microsoft Teams Rooms"::: , wenn ein Gerät einen Hardware- oder Anwendungsfehler generiert.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Konfigurieren einer E-Mail-Benachrichtigung bei :::no-loc text="Microsoft Teams Rooms"::: Hardwareproblemen

Konfigurieren Sie eine Warnungsregel, die Geräte :::no-loc text="Microsoft Teams Rooms"::: überprüft, bei denen innerhalb der letzten Stunde Hardwareprobleme aufgetreten sind.
1.  Melden Sie sich beim Portal [an:::no-loc text="Microsoft Azure":::,](https://portal.azure.com) wechseln Sie zu, :::no-loc text="Log Analytics"::: und wählen Sie Ihren Arbeitsbereich aus.

2. Navigieren Sie zu Ihrem :::no-loc text="Log Analytics"::: Arbeitsbereich, wählen Sie **Benachrichtigungen** und dann **Neue Warnungsregel aus.**

3. Wählen **Sie Bedingung hinzufügen** und dann **Benutzerdefinierte Protokollsuche aus.**

4.  Geben Sie die folgende Abfrage in das Textfeld Abfrage durchsuchen ein.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Konfigurieren Sie die Einstellungen für die Benachrichtigungslogik:<br>
    **Basierend auf:** Anzahl der Ergebnisse<br>
    **Bedingung:** Größer als<br>
    **Schwellenwert:** 0<br>

6. Konfigurieren Sie die Auswertungseinstellungen, und wählen Sie **Fertig:** <br>
    **Zeitraum (in Minuten):** 60<br>
    **Häufigkeit (in Minuten):** 60<br>

7. Konfigurieren von Aktionsgruppen:
    1.  Wählen Sie **"Neu erstellen" aus.**
    2.  Stellen Sie geeignete Namen für die Felder *Aktionsgruppe und* *Kurzname zur Verfügung* .
    3.  Geben Sie einen *eindeutigen Aktionsnamen an* , wählen Sie **E-Mail/SMS/Push/Voice** und dann **Details bearbeiten aus**.
    4.  Aktivieren Sie das **Kontrollkästchen** E-Mail, und geben Sie die E-Mail-Adresse der Person oder Gruppe an, die die Benachrichtigungen erhalten soll.
    5.  Sie können auch Ihre Telefonnummer bereitstellen, um per SMS, einem Sprachanruf oder mit beidem benachrichtigt zu werden.
    6. Wählen Sie **OK aus**.

8. **Passen Sie Aktionen** an, wenn Sie die Betreffzeile der Benachrichtigungs-E-Mails überschreiben möchten.

9. Geben Sie einen Regelnamen und eine Beschreibung an.<br>
    **Regelname:** :::no-loc text="Microsoft Teams Rooms"::: Hardwarefehlerwarnung<br>
    **Beschreibung:** Liste der Geräte, bei denen innerhalb der letzten Stunde ein Hardwareproblem aufgetreten ist<br>

10. Wählen Sie den vorgesehenen Schweregrad aus, und stellen Sie sicher, dass die Regel aktiviert ist.

11. Wählen Sie **Warnungsregel erstellen aus**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Konfigurieren einer E-Mail-Benachrichtigung für Anwendungsprobleme :::no-loc text="Microsoft Teams Rooms":::

Wiederholen Sie das gleiche Verfahren, aber verwenden Sie die folgende Abfrage, um Geräte auflisten, bei denen innerhalb der letzten Stunde Anwendungsprobleme aufgetreten sind.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Jetzt haben Sie die Definition von Benachrichtigungen abgeschlossen. Mithilfe der obigen Beispiele können Sie zusätzliche Warnungen definieren.

Wenn eine Benachrichtigung generiert wird, erhalten Sie eine E-Mail, in der die Geräte aufgeführt sind, auf denen innerhalb der letzten Stunde ein Problem aufgetreten ist.

! [Beispielbenachrichtigungs-E-Mail :::no-loc text="Azure Monitor"::: ](.. /media/Deploy-Azure-Monitor-6.png "Beispielbenachrichtigungs-E-Mail :::no-loc text="Azure Monitor"::: ")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Konfigurieren Sie alle Geräte für :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Nachdem die Dashboards und Benachrichtigungen konfiguriert wurden, :::no-loc text="Microsoft Monitoring"::: können Sie agent :::no-loc text="Microsoft Teams Rooms"::: auf allen Geräten einrichten und konfigurieren, um die Überwachungsbereitstellung abschließen zu können.

Sie können den Agent zwar manuell :::no-loc text="Microsoft Monitoring"::: auf jedem Gerät installieren und konfigurieren, es wird jedoch dringend empfohlen, vorhandene Softwarebereitstellungstools und -methoden zu nutzen.

Wenn Sie Ihre Geräte zum ersten :::no-loc text="Microsoft Teams Rooms"::: Mal erstellen, :::no-loc text="Microsoft Monitoring"::: sollten Sie die Einrichtungs- und Konfigurationsschritte des Agents als Teil des Erstellungsprozesses verwenden. Weitere Informationen finden Sie unter [Installieren des Agents über die Befehlszeile](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Bereitstellen des :::no-loc text="Microsoft Monitoring"::: Agents mithilfe eines Gruppenrichtlinienobjekts (Group Policy Object, GPO)

Wenn Sie Ihre Geräte bereits vor :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::der Implementierung bereitgestellt haben, können Sie das bereitgestellte Skript verwenden, um die Agents :::no-loc text="Active Directory"::: mithilfe von Gruppenrichtlinienobjekten ein- und zu konfigurieren.

1.  Erstellen Sie einen freigegebenen Netzwerkpfad, und erteilen Sie der Gruppe **"Domänencomputer** " Lesezugriff.

2.  Laden Sie die 64-Bit-Version des :::no-loc text="Microsoft Monitoring"::: Agents für von :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrahieren Sie den Inhalt des Setuppakets in die Netzwerkfreigabe.
    1.  Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie dannMMASetup-AMD64.exe **/c aus.**
    2.  Geben Sie die  gerade erstellte Freigabe an, und extrahieren Sie den Inhalt.

4.  Erstellen Sie ein neues Gruppenrichtlinienobjekt, und weisen Sie es der Organisationseinheit zu, in der :::no-loc text="Microsoft Teams Rooms"::: sich Computerkonten befinden.

5.  Konfigurieren der PowerShell-Ausführungsrichtlinie:
    1.  Bearbeiten des neu erstellten Gruppenrichtlinienobjekts und Navigieren zu \\ Komponenten für administrative Vorlagen für Computerkonfigurationsrichtlinien \\ :::no-loc text="Windows"::: \\ \\ :::no-loc text="Windows PowerShell":::
    2.  Aktivieren Sie **die Skriptausführung aktivieren, und** legen Sie **die Ausführungsrichtlinie so festgelegt** , **dass lokale Skripts zulässig sind**.

6.  Konfigurieren Sie das Startskript:
    1.  Kopieren Sie das folgende Skript, und speichern Sie es Install-MMAgent.ps1.
    2.  Ändern Sie die Parameter WorkspaceId, WorkspaceKey und SetupPath so, dass sie Ihrer Konfiguration entsprechen.
    3.  Bearbeiten Sie das gleiche Gruppenrichtlinienobjekt, und navigieren Sie zu Computerkonfigurationsrichtlinien \\ :::no-loc text="Windows"::: \\ Einstellungen \\ Skripts (Start/Herunterfahren)
    4.  Doppelklicken Sie, um **Start** auszuwählen, und wählen Sie dann **PowerShell-Skripts aus**.
    5.  Wählen **Sie Dateien anzeigen** aus, und kopieren Sie **Install-MMAgent.ps1** Datei in diesen Ordner.
    6.  Wählen **Sie Hinzufügen** und dann **Durchsuchen aus**.
    7.  Wählen Sie das ps1-Skript aus, das Sie gerade kopiert haben.

7.  :::no-loc text="Microsoft Teams Rooms"::: sollten den Agent nach dem :::no-loc text="Microsoft Monitoring"::: zweiten Neustart installieren und konfigurieren.

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
> Sie können sich auf [:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage) den Artikel Verwalten und Warten des Agents beziehen, wenn Sie einen Agent neu konfigurieren, ihn in einen anderen Arbeitsbereich verschieben oder Proxyeinstellungen nach der Erstinstallation ändern müssen.

## <a name="additional-solutions"></a>Zusätzliche Lösungen
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: bietet über den Lösungskatalog integrierte Verwaltungslösungen [, die Ihnen](/azure/azure-monitor/insights/solutions) bei der Überwachung Ihrer Umgebung helfen. Es wird dringend empfohlen[, dem](/azure/azure-monitor/platform/alert-management-solution) [:::no-loc text="Azure Log Analytics":::](/azure/azure-monitor/insights/solution-agenthealth) Arbeitsbereich auch Benachrichtigungsverwaltungs- und Agentinte health-Lösungen hinzuzufügen.

> [!NOTE]
> Die Agent Health-Lösung :::no-loc text="Microsoft Monitoring"::: kann Ihnen dabei helfen, veraltete oder defekte Agents in Ihrer Umgebung zu identifizieren, und die Warnungsverwaltungslösung bietet Details zu den Warnungen, die innerhalb eines bestimmten Zeitraums ausgelöst wurden.

## <a name="see-also"></a>Mehr dazu

[Planen der :::no-loc text="Microsoft Teams Rooms"::: Verwaltung mit :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Geräte :::no-loc text="Microsoft Teams Rooms"::: verwalten mit :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
