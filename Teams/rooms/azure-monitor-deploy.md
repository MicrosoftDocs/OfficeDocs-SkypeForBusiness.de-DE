---
title: Bereitstellen der Verwaltung von Microsoft Teams-Räumen mit Azure Monitor
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
description: In diesem Artikel wird erläutert, wie Sie die Verwaltung von Microsoft Teams Rooms-Geräten auf integrierte, end-to-end-Weise mithilfe von Azure Monitor bereitstellen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7046fc0010a4337ea14854e356600ccf3428f9d0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117593"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Bereitstellen :::no-loc text="Microsoft Teams Rooms"::: der Verwaltung mit :::no-loc text="Azure Monitor":::

In diesem Artikel wird erläutert, wie Sie integrierte End-to-End-Verwaltung von Geräten mithilfe von einrichten und :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: bereitstellen.

Sie können in konfigurieren, um grundlegende Telemetriedaten und Benachrichtigungen zur Verfügung zu stellen, mit deren Hilfe Sie Geräte :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: im :::no-loc text="Microsoft Teams Rooms"::: Besprechungsraum verwalten können. Wenn Ihre Verwaltungslösung reift, können Sie zusätzliche Daten- und Verwaltungsfunktionen bereitstellen, um eine detailliertere Ansicht der Geräteverfügbarkeit und -leistung zu erstellen.

Wenn Sie diesem Leitfaden folgen, können Sie ein Dashboard wie im folgenden Beispiel verwenden, um detaillierte Statusberichte für geräteverfügbarkeit, Anwendungs- und Hardwarestatus sowie Anwendungs- und :::no-loc text="Microsoft Teams Rooms"::: Betriebssystemversionsverteilung zu erhalten.

![Screenshot der Beispielansicht "Log Analytics" für Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Beispielprotokollanalyseansicht für Microsoft Teams Rooms")

Allgemein müssen Sie die folgenden Aufgaben ausführen:


1. [Überprüfen der :::no-loc text="Log Analytics"::: Konfiguration](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Konfigurieren von Testgeräten für :::no-loc text="Log Analytics"::: die Verwaltung](azure-monitor-deploy.md#configure_test_devices)
3. [Zuordnen benutzerdefinierter Felder](azure-monitor-deploy.md#Custom_fields)
4. [Definieren der :::no-loc text="Microsoft Teams Rooms"::: Ansichten in :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definieren von Benachrichtigungen](azure-monitor-deploy.md#Alerts)
6. [Konfigurieren aller Geräte für die Überwachung](azure-monitor-deploy.md#configure_all_devices)
7. [Konfigurieren zusätzlicher :::no-loc text="Azure Monitor"::: Lösungen](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Obwohl bei minimaler Konfiguration ein Computer überwacht werden kann, auf dem ein Betriebssystem ausgeführt wird, gibt es noch einige – spezifische Schritte, die Sie ausführen müssen, bevor Sie mit der Bereitstellung von Agents auf allen :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: Geräten :::no-loc text="Microsoft Teams Rooms"::: beginnen.
> Daher empfehlen wir dringend, alle Konfigurationsschritte in der richtigen Reihenfolge für eine kontrollierte Einrichtung und Konfiguration durchzuführen. Die Qualität des Endergebniss hängt stark von der Qualität der Anfänglichen Konfiguration ab.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Überprüfen der :::no-loc text="Log Analytics"::: Konfiguration
<a name="validate_LogAnalytics"> </a>

Sie benötigen einen Arbeitsbereich, :::no-loc text="Log Analytics"::: um mit dem Sammeln von Protokollen von Geräten zu :::no-loc text="Microsoft Teams Rooms"::: beginnen. Ein Arbeitsbereich ist eine einzigartige :::no-loc text="Log Analytics"::: Umgebung mit einem eigenen Datenrepository, Datenquellen und Lösungen. Wenn Sie bereits über einen Arbeitsbereich verfügen, können Sie ihn verwenden, um Ihre Bereitstellung zu überwachen, oder Alternativ können Sie einen dedizierten Arbeitsbereich erstellen, der ihren :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: Überwachungsanforderungen entspricht.

Wenn Sie einen neuen Arbeitsbereich erstellen müssen, folgen Sie den Anweisungen im Artikel Erstellen eines :::no-loc text="Log Analytics"::: [ :::no-loc text="Log Analytics"::: Arbeitsbereichs im :::no-loc text="Azure"::: Portal.](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Um mit :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: verwenden zu können, müssen Sie über ein aktives Abonnement :::no-loc text="Azure"::: verfügen. Wenn Sie kein Abonnement haben, können Sie ein kostenloses :::no-loc text="Azure"::: [Testabonnement](https://azure.microsoft.com/free) als Ausgangspunkt erstellen.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Konfigurieren :::no-loc text="Log Analytics"::: zum Sammeln von :::no-loc text="Microsoft Teams Rooms"::: Ereignisprotokollen

:::no-loc text="Log Analytics"::: erfasst nur Ereignisse aus den :::no-loc text="Windows"::: Ereignisprotokollen, die in den Einstellungen angegeben sind. Für jedes Protokoll werden nur die Ereignisse mit den ausgewählten Schweregraden erfasst.

Sie müssen konfigurieren, :::no-loc text="Log Analytics"::: um die Protokolle zu erfassen, die zum Überwachen des :::no-loc text="Microsoft Teams Rooms"::: Geräte- und Anwendungsstatus erforderlich sind. :::no-loc text="Microsoft Teams Rooms"::: -Geräte verwenden **:::no-loc text="Skype Room System":::** das Ereignisprotokoll.

Informationen zum :::no-loc text="Log Analytics"::: Konfigurieren der Ereignisse finden Sie unter :::no-loc text="Microsoft Teams Rooms"::: [ :::no-loc text="Windows"::: Ereignisprotokolldatenquellen in :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/data-sources-windows-events)

![Screenshot der Einstellungen für das Ereignisprotokoll](../media/Deploy-Azure-Monitor-2.png "Einstellungen für das Ereignisprotokoll")

> [!IMPORTANT]
> Konfigurieren Sie die Einstellungen für das Ereignisprotokoll, geben Sie als Ereignisprotokollname ein, und aktivieren Sie dann die Kontrollkästchen :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** Fehler, **Warnung** und Informationen.  

## <a name="configure-test-devices-for-azure-monitoring"></a>Konfigurieren von Testgeräten für azure monitoring
<a name="configure_test_devices"> </a>

Sie müssen sich :::no-loc text="Log Analytics"::: vorbereiten, um ereignisse überwachen :::no-loc text="Microsoft Teams Rooms"::: zu können. Zunächst müssen Sie Agents nur auf einem oder zwei Geräten bereitstellen, auf die Sie physischen Zugriff haben, und diese Testgeräte müssen Daten generieren und in den Arbeitsbereich :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: übertragen.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installieren :::no-loc text="Microsoft Monitoring"::: von Agents zum Testen von Geräten

Stellen Sie den Agent auf den Testgeräten mithilfe der Anweisungen unter Verbinden von Computern :::no-loc text="Microsoft Monitoring"::: mit dem Dienst in [ :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: bereit. :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows) Dieser Artikel enthält detaillierte Informationen zu den Schritten zum Bereitstellen von Agent für, Anweisungen zum Abrufen der :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * **Arbeitsbereichs-ID** _ ** :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: und des _Primärschlüssels * zum Abrufen von Geräten, die mit Ihrer Bereitstellung verbunden sind, sowie Schritte zum Überprüfen der Agentkonnektivität mit :::no-loc text="Log Analytics"::: der Instanz.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generieren von :::no-loc text="Microsoft Teams Rooms"::: Beispielereignissen

Nachdem der Agent auf den Testgeräten bereitgestellt wurde, überprüfen Sie, ob die erforderlichen :::no-loc text="Microsoft Monitoring"::: Ereignisprotokolldaten von gesammelt :::no-loc text="Azure Monitor"::: werden.

> [!NOTE]
> Starten Sie das Gerät nach der Installation des Agents neu, und stellen Sie sicher, dass die Besprechungs-App gestartet wird, damit neue Ereignisse im :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: Ereignisprotokoll generiert werden können.

1.  Melden Sie sich beim [ :::no-loc text="Microsoft Azure"::: Portal an,](https://portal.azure.com) wechseln Sie zu :::no-loc text="Log Analytics"::: Ihrem Arbeitsbereich, und wählen Sie sie aus.

2.  Listen Sie die von einem Gerät generierten Herzschlagereignisse :::no-loc text="Microsoft Teams Rooms"::: auf:
    1.  Wählen Sie Ihren Arbeitsbereich aus, wechseln Sie zu **Protokolle,** und verwenden Sie eine Abfrage, um die Heartbeatdatensätze abzurufen, die über die benutzerdefinierten Felder für :::no-loc text="Microsoft Teams Rooms"::: verfügen.
    2.  Beispielabfrage: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Stellen Sie sicher, dass die Abfrage Protokolldatensätze zurückgibt, die Ereignisse enthalten, die von der :::no-loc text="Microsoft Teams Rooms"::: Besprechungs-App generiert werden.

4.  Generieren Sie ein Hardwareproblem, und überprüfen Sie, ob die erforderlichen Ereignisse angemeldet :::no-loc text="Azure Log Analytics"::: sind.
    1.  Trennen Sie eines der Peripheriegeräte im :::no-loc text="Microsoft Teams Rooms"::: Testsystem. Dies kann die Kamera, die Freisprechanlage, das Mikrofon oder die Anzeige im Vorderraum sein.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll in ausgefüllt :::no-loc text="Azure Log Analytics"::: wurde.
    3.  Verwenden Sie eine Abfrage, um Hardwarefehlerereignisse auflisten: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Generieren Sie ein Anwendungsproblem, und überprüfen Sie, ob die erforderlichen Ereignisse protokolliert werden.
    1.  Ändern :::no-loc text="Microsoft Teams Rooms"::: Sie die Anwendungskonfiguration, und geben Sie ein falsches Sip-Adress-/Kennwortpaar (Session Initiation Protocol) ein.
    2.  Warten Sie 10 Minuten, bis das Ereignisprotokoll in ausgefüllt :::no-loc text="Azure Log Analytics"::: wurde.
    3.  Verwenden Sie eine Abfrage, um Anwendungsfehlerereignisse auflisten: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Diese Beispielereignisprotokolle sind erforderlich, bevor benutzerdefinierte Felder konfiguriert werden können. Fahren Sie erst mit dem nächsten Schritt fort, bis Sie die erforderlichen Ereignisprotokolle gesammelt haben.

## <a name="map-custom-fields"></a>Zuordnen benutzerdefinierter Felder
<a name="Custom_fields"> </a>

Sie verwenden benutzerdefinierte Felder, um bestimmte Daten aus den Ereignisprotokollen zu extrahieren. Sie müssen benutzerdefinierte Felder definieren, die später mit Ihren Kacheln, Dashboardansichten und Benachrichtigungen verwendet werden. Lesen [Sie :::no-loc text="Log Analytics"::: Benutzerdefinierte Felder in,](/azure/azure-monitor/platform/custom-fields) und machen Sie sich mit den Konzepten vertraut, bevor Sie mit dem Erstellen Ihrer benutzerdefinierten Felder beginnen.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierten Felder aus den aufgezeichneten Ereignisprotokollen zu extrahieren:

1.  Melden Sie sich beim [ :::no-loc text="Microsoft Azure"::: Portal an,](https://portal.azure.com) wechseln Sie zu :::no-loc text="Log Analytics"::: Ihrem Arbeitsbereich, und wählen Sie sie aus.

2. Listen Sie die von einem Gerät generierten Ereignisse :::no-loc text="Microsoft Teams Rooms"::: auf:
   1.  Wechseln Sie **zu Protokolle,** und verwenden Sie eine Abfrage, um die Datensätze abzurufen, die das benutzerdefinierte Feld enthalten.
   2.  Beispielabfrage: `Event | where Source == "SRS-App" and EventID == 2000`

3. Wählen Sie einen der Datensätze aus, wählen Sie die Schaltfläche links aus, und starten Sie den Assistenten für die Feldextraktion.
4. Markieren Sie die Daten, die Sie aus der RenderedDescription extrahieren möchten, und geben Sie einen Feldtitel an. Die Feldnamen, die Sie verwenden sollten, werden in Tabelle 1 angegeben.
5. Verwenden Sie die zuordnungen, die in *Tabelle 1 angezeigt werden.* :::no-loc text="Log Analytics":::fügt die **\_ CF-Zeichenfolge** automatisch an, wenn Sie das neue Feld definieren.

> [!IMPORTANT]
> Denken Sie daran, dass bei allen :::no-loc text="Log Analytics"::: JSON- und -Feldern die Zwischen- und Kleinschreibung beachtet wird.
> 
> Achten Sie auf die Abfragen, die für jedes benutzerdefinierte Feld in der nachstehenden Tabelle erforderlich sind. Sie müssen die richtigen Abfragen für verwenden, um :::no-loc text="Log Analytics"::: benutzerdefinierte Feldwerte erfolgreich zu extrahieren.
> 
**Tabelle 1**

| **JSON-Feld**                   | **:::no-loc text="Log Analytics"::: Benutzerdefiniertes Feld** | **Ereigniskennung** | **Abfrage, die mit der Extraktion verwendet werden soll**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Beschreibung                      | SRSEventDescription         | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| Version des Betriebssystems                        | SRSOSLongVersion            | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 2000 |
| Status des Konferenzmikrofons     | SRSConfMicrophoneStatus     | **3001**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 3001 |
| Konferenzsprecherstatus        | SRSConfSpeakerStatus        | **3001**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 3001 |
| Standardlautsprecherstatus           | SRSDefaultSpeakerStatus     | **3001**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 3001 |
| Kamerastatus                    | SRSCameraStatus             | **3001**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 3001 |
| Status "Vor der Raumanzeige"     | SRSFORDStatus               | **3001**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 3001 |
| Status des Bewegungssensors             | SRSMotionSensorStatus       | **3001**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 3001 |
| HDMI-Aufnahmestatus               | SRSHDMIIngestStatus         | **3001**     | Ereignis, \| bei dem Quelle == "SRS-App" und EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definieren der :::no-loc text="Microsoft Teams Rooms"::: Ansichten in :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Nachdem Daten gesammelt und benutzerdefinierte Felder zugeordnet wurden, können Sie mit dem Ansichts-Designer ein Dashboard entwickeln, das verschiedene Kacheln zum Überwachen von Ereignissen :::no-loc text="Microsoft Teams Rooms"::: enthält. Erstellen Sie mit dem Ansicht-Designer die folgenden Kacheln. Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Ansichten mithilfe :::no-loc text="Log Analytics"::: von Ansichts-Designer in](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Die vorherigen Schritte in diesem Handbuch sollten abgeschlossen sein, damit die Dashboardkacheln ordnungsgemäß funktionieren.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Erstellen eines Microsoft Teams Rooms-Dashboards mithilfe der Importmethode

Sie können ein Dashboard :::no-loc text="Microsoft Teams Rooms"::: importieren und schnell mit der Überwachung Ihrer Geräte beginnen. Gehen Sie wie folgt vor, um das Dashboard zu importieren:

1.  Holen Sie [sich SkypeRoomSystems_v2.omsview-Dashboarddatei.](https://go.microsoft.com/fwlink/?linkid=835675)
2.  Melden Sie sich beim [ :::no-loc text="Microsoft Azure"::: Portal an,](https://portal.azure.com) wechseln Sie zu :::no-loc text="Log Analytics"::: Ihrem Arbeitsbereich, und wählen Sie sie aus.
3.  Öffnen **Sie Ansichts-Designer**.
4.  Wählen **Sie Importieren** und dann die Datei **SkypeRoomSystems_v2.omsview** aus.
5.  Klicken Sie auf **Speichern**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Manuelles Erstellen eines Microsoft Teams Rooms-Dashboards

Alternativ können Sie ein eigenes Dashboard erstellen und nur die Kacheln hinzufügen, die Sie überwachen möchten.

#### <a name="configure-the-overview-tile"></a>Konfigurieren der Kachel "Übersicht"

1.  Öffnen **Sie Ansichts-Designer**.
2.  Wählen **Sie Übersichtskachel** und dann **Zwei Zahlen** aus dem Katalog aus.
3.  Benennen Sie die Kachel **:::no-loc text="Microsoft Teams Rooms":::** .
4.  Definieren der **ersten Kachel**:<br>
    **Legende:** Geräte, die innerhalb des letzten Monats mindestens einmal einen Herzschlag gesendet haben<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definieren der **zweiten Kachel**:<br>
    **Legende:** Aktive Geräte, die innerhalb der letzten Stunde einen Herzschlag gesendet haben<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Wählen Sie **Übernehmen aus.**

### <a name="create-a-tile-that-displays-active-devices"></a>Erstellen einer Kachel, die aktive Geräte anzeigt

1.  Wählen **Sie Dashboard anzeigen aus,** um mit dem Hinzufügen ihrer Kacheln zu beginnen.
2.  Wählen **Sie im & die Liste** "Nummer" aus.
3.  Definieren Sie die **Eigenschaften Allgemein:**<br>
    **Gruppentitel:** Heartbeat Status<br>
    **Neue Gruppe:** Ausgewählt
4.  Definieren Sie **die Kacheleigenschaften:**<br>
    **Legende:** Aktive Geräte (In den letzten 20 Minuten gesendeter Herzschlag)<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definieren Sie die **Listeneigenschaften:**<br>
    **Listenabfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definieren **von Spaltentiteln**:<br>
    **Name:** Computername<br>
    **Wert:** Letzter Herzschlag
7.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen **Sie Übernehmen** und dann Schließen **aus.**

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Erstellen einer Kachel, die Geräte mit Verbindungsproblemen anzeigt

1.  Wählen **Sie nummer & im** Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften Allgemein:**<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie **die Kacheleigenschaften:**<br>
    **Legende:** Inaktive Geräte (keine Inaktive Nachricht, die in den letzten 20 Minuten gesendet wurde)<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definieren Sie die **Listeneigenschaften:**<br>
    **Listenabfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definieren **von Spaltentiteln**:<br>
    **Name:** Computername<br>
    **Wert:** Letzter Herzschlag
6.  **Navigationsabfrage definieren:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen **Sie Übernehmen** und dann Schließen **aus.**

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Erstellen einer Kachel, auf der Geräte mit einem Hardwarefehler angezeigt werden

1.  Wählen **Sie nummer & im** Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften Allgemein:**<br>
    **Gruppentitel:** Hardwarestatus<br>
    **Neue Gruppe:** Ausgewählt
3.  Definieren Sie **die Kacheleigenschaften:**<br>
    **Legende:** Geräte, bei der in der letzten Stunde ein Hardwarefehler aufgetreten ist<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften:**<br>
    **Listenabfrage:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren **von Spaltentiteln**:<br>
    **Name:** Computername<br>
    **Wert:** Letzter Fehler
6.  **Navigationsabfrage definieren:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen **Sie Übernehmen** und dann Schließen **aus.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Erstellen einer Kachel mit :::no-loc text="Microsoft Teams Rooms"::: Betriebssystemversionen

1.  Wählen **Sie donut & aus** dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften Allgemein:**<br>
    **Gruppentitel:** Betriebssystemdetails<br>
    **Neue Gruppe:** Ausgewählt
3.  Definieren Sie **die Headereigenschaften:**<br>
    **Titel:** Betriebssystemversionen<br>
    **Untertitel:** Geräte mit bestimmten Betriebssystemversionen
4.  Definieren Sie die **Donut-Eigenschaften:**<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Zentrieren von Text:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie die **Listeneigenschaften.**<br>
    **Listenabfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Grafik ausblenden:** Ausgewählt<br>
    **Aktivieren von Sparklines:** Nicht ausgewählt
6.  Definieren **von Spaltentiteln**.<br>
    **Name:** Computername<br>
    **Wert:** Leer lassen
7.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen **Sie Übernehmen** und dann Schließen **aus.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Erstellen einer Kachel mit :::no-loc text="Microsoft Teams Rooms"::: Anwendungsversionen

1.  Wählen **Sie donut & aus** dem Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften Allgemein:**<br>
    **Gruppentitel:** :::no-loc text="Microsoft Teams Rooms"::: Anwendungsdetails<br>
    **Neue Gruppe:** Ausgewählt
3.  Definieren Sie **die Headereigenschaften:**<br>
    **Titel:** Anwendungsversionen<br>
    **Untertitel:** Geräte mit bestimmten Anwendungsversionen
4.  Definieren Sie die **Donut-Eigenschaften:**<br>
    **Abfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Zentrieren von Text:** Geräte<br>
    **Vorgang:** Summe
5.  Definieren Sie die **Listeneigenschaften.**<br>
    **Listenabfrage:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Grafik ausblenden:** Ausgewählt<br>
    **Aktivieren von Sparklines:** Nicht ausgewählt
6.  Definieren **von Spaltentiteln**.<br>
    **Name:** Computername<br>
    **Wert:** Leer lassen
7.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Wählen **Sie Übernehmen** und dann Schließen **aus.**

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Erstellen einer Kachel, die Geräte mit einem Anwendungsfehler anzeigt

1.  Wählen **Sie nummer & im** Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften Allgemein.**<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kacheleigenschaften.**<br>
    **Legende:** Geräte, bei der in der letzten Stunde ein Anwendungsfehler aufgetreten ist<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften.**<br>
    **Listenabfrage:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definieren **von Spaltentiteln**.<br>
    **Name:** Computername<br>
    **Wert:** Letzter Fehler
6.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Wählen **Sie Übernehmen** und dann Schließen **aus.**

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Erstellen einer Kachel, die neu gestartete Geräte anzeigt

1.  Wählen **Sie nummer & im** Katalog aus, und fügen Sie dann eine neue Kachel hinzu.
2.  Definieren Sie die **Eigenschaften Allgemein.**<br>
    **Gruppentitel:** Leer lassen<br>
    **Neue Gruppe:** Nicht ausgewählt
3.  Definieren Sie die **Kacheleigenschaften.**<br>
    **Legende:** Geräte, auf denen die Anwendung in den letzten 24 Stunden neu gestartet wurde, und Anzahl der Neustarts<br>
    **Kachelabfrage:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definieren Sie die **Listeneigenschaften.**<br>
    **Listenabfrage:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definieren **von Spaltentiteln**.<br>
    **Name:** Computername<br>
    **Wert:** Anzahl der Neustarts
6.  Definieren **sie Navigationsabfrage**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Wählen **Sie Übernehmen** und dann Schließen **aus.**
8.  Wählen **Sie Speichern aus,** um Ihr Dashboard zu speichern.

Jetzt haben Sie die Erstellung Ihrer Ansichten abgeschlossen.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Konfigurieren von Benachrichtigungen in :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: kann Benachrichtigungen auslösen, um die Administratoren zu benachrichtigen, wenn bei einer Konsole :::no-loc text="Microsoft Teams Rooms"::: ein Problem vor sich geht.

:::no-loc text="Azure Monitor"::: enthält einen integrierten Benachrichtigungsmechanismus, der die geplanten Protokollsuchen in regelmäßigen Intervallen durch führt. Wenn die Ergebnisse der Protokollsuche bestimmten Kriterien entsprechen, wird ein Warnungsdatensatz erstellt.

Die Regel kann dann automatisch eine oder mehrere Aktionen ausführen, um Sie proaktiv über die Benachrichtigung zu benachrichtigen oder einen anderen Prozess aufrief. Die möglichen Optionen bei Benachrichtigungen sind:
-   Senden einer E-Mail
-   Aufrufen eines externen Prozesses über eine HTTP POST-Anforderung
-   Starten eines Runbooks im :::no-loc text="Azure Automation"::: Dienst

Weitere [Informationen :::no-loc text="Azure Monitor"::: zu den Benachrichtigungen in](/azure/azure-monitor/platform/alerts-unified-log) finden Sie unter Anmelden von Benachrichtigungen. :::no-loc text="Azure Monitor":::

> [!NOTE]
> Die folgenden Beispiele senden E-Mail-Benachrichtigungen, :::no-loc text="Microsoft Teams Rooms"::: wenn ein Gerät eine Hardware oder einen Anwendungsfehler generiert.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Konfigurieren einer E-Mail-Benachrichtigung für :::no-loc text="Microsoft Teams Rooms"::: Hardwareprobleme

Konfigurieren Sie eine Warnungsregel, die nach Geräten sucht, bei denen in der letzten Stunde :::no-loc text="Microsoft Teams Rooms"::: Hardwareprobleme aufgetreten sind.
1.  Melden Sie sich beim [ :::no-loc text="Microsoft Azure"::: Portal an,](https://portal.azure.com) wechseln Sie zu :::no-loc text="Log Analytics"::: Ihrem Arbeitsbereich, und wählen Sie sie aus.

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

5.  Konfigurieren Sie die Einstellungen für die Warnungslogik:<br>
    **Basierend auf:** Anzahl der Ergebnisse<br>
    **Bedingung:** Größer als dann<br>
    **Schwellenwert:** 0<br>

6. Konfigurieren Sie die Auswertungseinstellungen, und wählen Sie **Fertig aus:** <br>
    **Zeitraum (in Minuten):** 60<br>
    **Häufigkeit (in Minuten):** 60<br>

7. Konfigurieren von Aktionsgruppen:
    1.  Wählen **Sie Neu erstellen aus.**
    2.  Geben Sie geeignete Namen für die Felder *Aktionsgruppe und* *Kurzname* an.
    3.  Geben Sie einen *eindeutigen Aktionsnamen an,* wählen Sie **E-Mail/SMS/Push/Voice** und dann **Details bearbeiten aus.**
    4.  Aktivieren Sie **das Kontrollkästchen** E-Mail, und geben Sie die E-Mail-Adresse der Person oder Gruppe an, die die Benachrichtigungen erhält.
    5.  Sie können Auch Ihre Telefonnummer bereitstellen, um per SMS, einem Sprachanruf oder beidem benachrichtigt zu werden.
    6. Wählen Sie **OK aus.**

8. **Passen Sie Aktionen** an, wenn Sie die Betreffzeile der Benachrichtigungs-E-Mails außer Kraft setzen möchten.

9. Geben Sie einen Regelnamen und eine Beschreibung an.<br>
    **Regelname:** :::no-loc text="Microsoft Teams Rooms"::: Hardwarefehlerwarnung<br>
    **Beschreibung:** Liste der Geräte, bei denen innerhalb der letzten Stunde ein Hardwareproblem aufgetreten ist<br>

10. Wählen Sie den vorgesehenen Schweregrad aus, und vergewissern Sie sich, dass die Regel aktiviert ist.

11. Wählen **Sie Warnungsregel erstellen aus.**

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Konfigurieren einer E-Mail-Benachrichtigung für :::no-loc text="Microsoft Teams Rooms"::: Anwendungsprobleme

Wiederholen Sie dasselbe Verfahren, verwenden Sie jedoch die folgende Abfrage, um Geräte auflisten, bei denen in der letzten Stunde Anwendungsprobleme aufgetreten sind.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Jetzt haben Sie das Definieren von Benachrichtigungen abgeschlossen. Sie können zusätzliche Benachrichtigungen mithilfe der vorstehenden Beispiele definieren.

Wenn eine Benachrichtigung generiert wird, erhalten Sie eine E-Mail, in der die Geräte aufgeführt werden, auf denen innerhalb der letzten Stunde ein Problem aufgetreten ist.

! :::no-loc text="Azure Monitor"::: [Beispielbenachrichtigungs-E-Mail](.. /media/Deploy-Azure-Monitor-6.png :::no-loc text="Azure Monitor"::: "Beispielbenachrichtigungs-E-Mail")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Konfigurieren aller Geräte für :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> Nachdem die Dashboards und Benachrichtigungen konfiguriert wurden, können Sie agent auf allen Geräten einrichten und konfigurieren, um :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: die Überwachungsbereitstellung zu abschließen.

Obwohl Sie den Agent manuell auf jedem Gerät installieren und konfigurieren können, wird dringend empfohlen, vorhandene Tools und Methoden für die Softwarebereitstellung :::no-loc text="Microsoft Monitoring"::: zu nutzen.

Wenn Sie Ihre Geräte zum ersten Mal erstellen, sollten Sie die Schritte zum Einrichten und Konfigurieren des Agents als Teil :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: des Buildprozesses verwenden. Weitere Informationen finden Sie unter [Installieren des Agents mithilfe der Befehlszeile.](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Bereitstellen des :::no-loc text="Microsoft Monitoring"::: Agents mithilfe eines Gruppenrichtlinienobjekts (Gruppenrichtlinienobjekt)

Wenn Sie Ihre Geräte bereits vor der Implementierung bereitgestellt haben, können Sie mithilfe des bereitgestellten Skripts die Agents mithilfe von Gruppenrichtlinienobjekten einrichten und :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: :::no-loc text="Active Directory"::: konfigurieren.

1.  Erstellen Sie einen freigegebenen Netzwerkpfad, und gewähren Sie lesezugriff auf **die Gruppe "Domänencomputer".**

2.  Laden Sie die 64-Bit-Version des :::no-loc text="Microsoft Monitoring"::: Agents von :::no-loc text="Windows"::: herunter. <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrahieren Sie den Inhalt des Setuppakets in die Netzwerkfreigabe.
    1.  Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie **dannMMASetup-AMD64.exe /c aus.**
    2.  Geben Sie die gerade erstellte Freigabe an, und extrahieren Sie den Inhalt.

4.  Erstellen Sie ein neues Gruppenrichtlinienobjekt, und weisen Sie es der Organisationseinheit zu, in der :::no-loc text="Microsoft Teams Rooms"::: sich Computerkonten befinden.

5.  Konfigurieren der PowerShell-Ausführungsrichtlinie:
    1.  Bearbeiten des neu erstellten Gruppenrichtlinienobjekts und Navigieren zu Komponenten für Administrative Vorlagen für \\ \\ \\ :::no-loc text="Windows"::: Computerkonfigurationsrichtlinien \\:::no-loc text="Windows PowerShell":::
    2.  Aktivieren Sie **die Skriptausführung aktivieren, und** legen Sie **die Ausführungsrichtlinie so vor,** dass **lokale Skripts zulässig sind.**

6.  Konfigurieren Des Startskripts:
    1.  Kopieren Sie das folgende Skript, und speichern Sie es Install-MMAgent.ps1.
    2.  Ändern Sie die Parameter WorkspaceId, WorkspaceKey und SetupPath so, dass sie Ihrer Konfiguration entsprechen.
    3.  Bearbeiten Sie dasselbe Gruppenrichtlinienobjekt, und navigieren Sie zu Einstellungen für \\ Computerkonfigurationsrichtlinien \\ :::no-loc text="Windows"::: \\ (Start/Herunterfahren)
    4.  Doppelklicken Sie, um **Start** auszuwählen, und wählen Sie **dann PowerShell-Skripts aus.**
    5.  Wählen **Sie Dateien anzeigen** aus, und kopieren **Install-MMAgent.ps1** in diesen Ordner.
    6.  Wählen **Sie Hinzufügen** und dann Durchsuchen **aus.**
    7.  Wählen Sie das ps1-Skript aus, das Sie gerade kopiert haben.

7.  :::no-loc text="Microsoft Teams Rooms"::: sollte der Agent beim zweiten Neustart :::no-loc text="Microsoft Monitoring"::: installiert und konfiguriert werden.

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
> Sie können sich [ :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) auf den Artikel Verwalten und Verwalten des Agents beziehen, wenn Sie einen Agent neu konfigurieren, in einen anderen Arbeitsbereich verschieben oder die Proxyeinstellungen nach der Erstinstallation ändern müssen.

## <a name="additional-solutions"></a>Zusätzliche Lösungen
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: bietet integrierte Verwaltungslösungen über den [Lösungskatalog,](/azure/azure-monitor/insights/solutions) um Sie bei der Überwachung Ihrer Umgebung weiter zu unterstützen. Es wird dringend empfohlen, Ihrem Arbeitsbereich auch Lösungen für [die](/azure/azure-monitor/platform/alert-management-solution) Warnungsverwaltung und den [ :::no-loc text="Azure Log Analytics"::: Agenteninte](/azure/azure-monitor/insights/solution-agenthealth) health hinzuzufügen.

> [!NOTE]
> Die Lösung "Agent Health" kann Ihnen dabei helfen, veraltete oder defekte Agents in Ihrer Umgebung zu identifizieren, und die Warnungsverwaltungslösung enthält Details zu den Benachrichtigungen, die innerhalb eines bestimmten Zeitraums :::no-loc text="Microsoft Monitoring"::: ausgelöst wurden.

## <a name="see-also"></a>Mehr dazu

[Planen :::no-loc text="Microsoft Teams Rooms"::: der Verwaltung mit :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Verwalten :::no-loc text="Microsoft Teams Rooms"::: von Geräten mit :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)