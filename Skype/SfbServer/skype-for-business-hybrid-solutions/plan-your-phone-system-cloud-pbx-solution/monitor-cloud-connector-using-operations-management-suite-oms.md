---
title: Überwachen von Cloud-Connector mithilfe von Operationen Management Suite (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lesen Sie in diesem Thema erfahren, wie Ihre Cloud-Connector-Version 2.1 und höher Bereitstellung überwachen, mithilfe von Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 36d70a1504eab085d319e46d03c3c6f0bd9d14f3
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839823"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Überwachen von Cloud-Connector mithilfe von Operationen Management Suite (OMS)

Lesen Sie in diesem Thema erfahren, wie Ihre Cloud-Connector-Version 2.1 und höher Bereitstellung überwachen, mithilfe von Microsoft Operations Management Suite (OMS).

Sie können nun Ihre Cloud-Connector-Version 2.1 und höher Bereitstellung mithilfe von Operationen Management Suite (OMS), eine Cloud von Microsoft IT-Management-Lösung überwachen. OMS-Protokoll Analytics können Sie zum Überwachen und analysieren die Verfügbarkeit und Leistung von Ressourcen, einschließlich der physischen und virtuellen Computern. Weitere Informationen zu OMS und Protokoll Analytics, finden Sie unter [Was Vorgänge Management Suite (OMS) ist?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).

Dieses Thema enthält die folgenden Abschnitte:

- Voraussetzungen

- Konfigurieren von Cloud-Connector zur Verwendung von OMS

- Konfigurieren von OMS

- Analysieren der Benachrichtigungen in das Protokoll Analytics repository

- Empfohlene monitoring set

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie zum Überwachen der bereitstellungs Cloud Connector OMS verwenden können, benötigen Sie Folgendes:

- **Ein Azure-Konto und einem OMS-Arbeitsbereich.** Wenn Sie bereits ein Azure-Konto besitzen, müssen Sie die Verwendung von OMS-Protokoll Analytics erstellen. Informationen dazu, wie Sie ein Azure-Konto erstellen und Einrichten von einem OMS-Arbeitsbereich finden Sie unter [Erste Schritte mit einem Protokoll Analytics Arbeitsbereich](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud-Connector Version 2.1 oder höher**

- **Protokoll Analytics neue Protokoll Suche** ist erforderlich für die Überwachung von Cloud-Connector. Weitere Informationen finden Sie unter [Upgrade Azure Protokoll Analytics Arbeitsbereich mit neue Log-Suche](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Konfigurieren von Cloud-Connector zur Verwendung von OMS

Sie müssen die Cloud Connector lokale Umgebung zur Verwendung von OMS konfigurieren. Zu diesem Zweck benötigen Sie Ihre OMS Workspace-ID und Schlüssel, den Sie mithilfe des OMS-Portal finden: Einstellungen –\>Datenquellen verbunden –\> Windows-Servern:

![Screenshot für Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

Konfiguration von Cloud-Connector zur Verwendung von OMS, hängt von Ihrem Szenario:

- **Wenn Sie eine neue Cloud-Connector Appliance installieren oder Sie eine Einheit erneut bereitstellen möchten**, gehen Sie folgendermaßen vor dem Ausführen von Install-CcAppliance vor:

1. Legen Sie in der Datei CloudConnector.ini [allgemeine] Abschnitt des OMSEnabled-Parameters auf true fest.

    Jedes Mal Cloud-Connector bereitgestellt oder aktualisiert, versucht er, den OMS-Agenten automatisch auf den virtuellen Computern zu installieren. Aktivieren Sie dieses Feature, sodass der OMS-Agent die automatische Aktualisierung von Cloud-Connector überstehen kann.

2. Um die OMS-ID und Schlüssel zu konfigurieren, führen Sie Set-CcCredential - AccountType OMSWorkspace aus. 

- **Wenn Sie einen OMS-Agenten auf einer vorhandenen Cloud Connector Appliance installieren**, gehen Sie folgendermaßen vor:

1. Legen Sie in der Datei CloudConnector.ini [allgemeine] Abschnitt OMSEnabled = True. 

2. Import-CcConfiguration ausführen. 

3. Führen Sie Install-CcOMSAgent aus. 

    > [!NOTE]
    > Wenn die Anmeldeinformationen des OMSWorkspace nicht festgelegt wurde, werden Sie für die Anmeldeinformationen aufgefordert, wenn Sie Install-CcOMSAgent ausführen. 

- **Wenn Sie die OMS Workspace-ID oder der Schlüssel in einer Cloud-Connector Appliance aktualisieren möchten installiert, die bereits einen OMS-Agent:**

1. Um die OMS-ID und Schlüssel zu konfigurieren, führen Sie Set-CcCredential - AccountType OMSWorkspace aus. 

2. Führen Sie zum Anwenden von Updates installieren CcOMSAgent aus. 

- **Stellen Sie sicher, dass die Agents wie folgt verbunden sind, in allen Szenarien:**

    Wechseln Sie in das Portal OMS zu Einstellungen -\> verbundene Datenquellen -\> Windows-Servern. Sehen Sie eine Liste der verbundenen Computer ein. 

## <a name="configure-oms"></a>Konfigurieren von OMS

Im nächsten Schritt müssen Sie die OMS-Konfiguration mithilfe des OMS-Portals angeben. Insbesondere müssen Sie:

- Geben Sie Informationen zur Ereignisprotokolle und Leistungsindikatoren.

- Erstellen Sie Benachrichtigungen. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren

Im Portal OMS müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:

1. Wechseln Sie zu Einstellungen -\>Daten -\>Windows-Ereignisprotokolle, und fügen Sie die Ereignisprotokolle auf: 

   - Lync Server

   - Anwendung

     > [!NOTE]
     > Sie müssen die Lync Server manuell in das Textfeld eingeben. Es wird nicht als Option in der Dropdown-Liste angezeigt. 

     Weitere Informationen finden Sie unter [Windows-Ereignisprotokoll-Datenquellen im Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Wechseln Sie zu Einstellungen -\>Daten -\> Windows-Leistungsindikatoren und Leistungsindikatoren für hinzufügen: 

   - **OS level-Leistungsindikatoren**. Können Sie OS Ebene Leistungsindikatoren wie Prozessorverwendung, die Speicherverwendung, Netzwerkauslastung, hinzufügen oder vorhandene Lösungen wie Kapazität und Leistung, Leistung Netzwerkmonitor ohne explizit Leistungsindikatoren hinzufügen können. Unabhängig davon, wie Sie sie überwachen möchten empfiehlt es sich, dass Sie die OS Leistungsindikatoren überwachen.

   - **Skype für Business Leistungsindikatoren**. Es gibt zahlreiche von Skype für Unternehmen bereitgestellten Leistungsindikatoren. Anmeldung an einem beliebigen Vermittlungsserver und dem Systemmonitor öffnen, um diese Indikatoren finden. Mit diesen Zählern beginnen mit "LS:". Microsoft empfiehlt, dass Sie mit den folgenden Leistungsindikatoren Kapazität mindestens starten, und fügen andere Personen, die von Interesse sind:

     Aktive Anrufe gesamt:

   - LS:MediationServer - eingehende Calls(_Total)\- aktuellen 

   - LS:MediationServer - ausgehende Calls(_Total)\- aktuellen 

     Total medienumgehung aktiven Anrufe:

   - LS:MediationServer - eingehende Calls(_Total)\- Active medienumgehung Anrufe 

   - LS:MediationServer - ausgehende Calls(_Total)\- Active medienumgehung Anrufe 

     > [!NOTE]
     > Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben. Sie werden nicht als Optionen in der Dropdown-Liste angezeigt. 

     Weitere Informationen finden Sie unter [Windows und Linux Leistung Datenquellen im Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Benachrichtigungen erstellen

Es gibt zwei Arten von Warnungen in OMS: Anzahl der Ergebnisse Benachrichtigungen und Benachrichtigungen für metrischen Maßeinheiten. Weitere Informationen zum Erstellen von Warnungen finden Sie unter [Arbeiten mit Warnung Regeln in Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Beim Erstellen von Warnungen, sollten Sie Folgendes berücksichtigen:

- Stellen Sie sicher, dass die Benachrichtigung eine Benachrichtigung für die Anzahl der Ergebnisse ist die Standardauswahl. 

- Die Demo Abfragen erfordern, dass "Anzahl der Ergebnisse" zu "größer als 0" festgelegt ist. 

- Es wird empfohlen, dass Sie Zeitfenster und benachrichtigungshäufigkeit auf 5 Minuten festgelegt. 

- Es wird empfohlen, dass Sie nicht "Unterdrücken Benachrichtigungen" Demo Warnungen aktivieren. 

- Warnung Standardszenarien Microsoft empfiehlt ein Paar von Benachrichtigungen erstellen: eine Fehlermeldung und Zurücksetzen einer Warnung. Wählen Sie die fehlerbenachrichtigung für Schweregrad Kritisch. Wählen Sie für die Warnung zurücksetzen Schweregrad Information aus.

In den folgenden Abschnitten wird beschrieben, wie zum Beispiel für Warnungen zu erstellen.

 **Erstellen einer Warnung Paar: "RTCMEDSRV wird nicht ausgeführt, in der Vermittlungsserver" und "RTCMEDSRV wieder Ausführung in hat Vermittlungsserver"**

Diese Warnung Paar zu erstellen:

- Die Abfrage für die Fehlermeldung ist:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    Die Abfrage verwendet die Computer Filter *, auf dem Computer "MediationServer" enthält* . Der Filter wählt nur auf den Computer, dessen Name die Zeichenfolge "MediationServer" enthält.

     Sie ersetzen Sie den Filter durch Ihren eigenen Computer Filter oder einfach zu entfernen. Sie können komplexe Zeichenfolge Filter ohne reguläre Ausdrücke zu erstellen. Weitere Informationen finden Sie unter [Operatoren](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Sie können auch auswählen, reguläre Ausdrücke verwendet. Darüber hinaus können Sie eine Computergruppe erstellen, indem eine Suchabfrage zu speichern und diese Gruppe als Ihren Computer Filter in der Warnung Abfrage. Weitere Informationen finden Sie unter [Computergruppen im Protokoll Analytics melden Suchvorgänge](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Für jeden Computer die Abfrage Fehler Ruft das letzte Ereignisprotokoll für den RTCMEDSRV Service Anfang und Stop-service. Wird zurückgegeben, die eine melden, wenn das letzte Ereignis Service Stop-Ereignis; nothing wird zurückgegeben, wenn das letzte Ereignis Service Start-Ereignis ist. Kurz gesagt, würde die Abfrage eine Liste der Server zurück, deren RTCMEDSRV im Zeitfenster beendet wurde. 

- Die Abfrage für die Benachrichtigung zurücksetzen ist:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    Die Reset-Abfrage ist genau das gegenteilige, was der Abfrage Fehler. Für jeden Computer wird es eine zurück, wenn das letzte Ereignis ist Ereignis den Dienst zu starten. nothing wird zurückgegeben, wenn das letzte Ereignis Service Stop-Ereignis ist.

  **Erstellen einer Warnung Paar: "zu viele gleichzeitige Anrufe in Vermittlungsserver" und "gleichzeitiger Anrufe auf zurückgegriffen normaler Auslastung"**

So erstellen Sie diese Warnung:

- Die Abfrage für die Fehlermeldung ist:

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Für jeden Computer erhalten die Abfrage den letzten Leistungsindikatoren für eingehende Anrufe und ausgehende Anrufe und Summe diese beiden Werte. Wird zurückgegeben, die eine melden, wenn der Summenwert 500; überschreitet nothing wird zurückgegeben, wenn dies nicht der Fall. Kurz gesagt, würde die Abfrage eine Liste der Server zurück, deren gleichzeitige Anrufe zu viele im Zeitfenster sind.

- Die Abfrage für die Benachrichtigung zurücksetzen ist:

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    Die Reset-Abfrage ist genau das gegenteilige, was der Abfrage Fehler. Für jeden Computer erhalten die Abfrage den letzten Leistungsindikatoren für eingehende Anrufe und ausgehende Anrufe und Summe diese beiden Werte. Es wird ein Protokoll, wenn der Summenwert ist kleiner als 500 zurückgeben. Es gibt nichts anders zurück.

  **Erstellen einer Warnung: "CPU-Auslastung \> 90 oder RTCMEDIARELAY im Server beendet" Benachrichtigung**

Um diese Warnung zu erstellen, ist die Abfrage:

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

Die Abfrage erhalten alle Prozessor Usage Leistungsindikator und Service Stop-Ereignis von allen Computern und zurückgeben, die jemals ein Protokoll überschreitet entweder Prozessorverwendung 90 % oder Dienst beendet wurde. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analysieren der Benachrichtigungen in das Protokoll Analytics repository

Verwenden Sie zum Analysieren von Benachrichtigungen in Ihrem Repository der Alert-Management-Lösung. Weitere Informationen finden Sie unter [Alert-Management-Lösung in Betrieb Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Empfohlene monitoring Mindestsatz

Um Probleme mit Ereignisprotokollen und Leistungsindikatoren zu ermitteln: 

- **Ereignisprotokolle.** Für jedes Problem sollte ein paar Ereignisse mit einem Satz von Ereignissen, um anzugeben, dass etwas falsch ist, während die andere gibt an, dass alles ist. Für jeden angegebenen Zeitraum, es ist das letzte Ereignis aufgezeichnet, mit denen angegeben wird, ob der für diesen Zeitraum ist.

- **Leistungsindikatoren.** Es sollte ein Schwellenwert für die überwachten Leistungsindikatoren.

Die folgende Tabelle enthält die Dienste, dass Microsoft empfiehlt die Überwachung durch die Stopp und Start-Ereignis-IDs aufgelistet:

|Dienstname  <br/> |Ziel-Serverrolle  <br/> |Ereignis-ID beenden  <br/> |Start-Ereignis-ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Vermittlungsserver  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edgeserver  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edgeserver  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edgeserver  <br/> |22003  <br/> |22002  <br/> |

Die folgende Tabelle enthält die Netzwerkprobleme, die Microsoft überwachen empfiehlt:


| Name des Monitors  <br/>                                        | Ziel-Serverrolle  <br/> | Ereignis-ID-Ausdruck Erfolg  <br/> | Ausdruck, der Ereignis-ID  <br/> | Fehler bei diesem Beispiel wird  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Vermittlungsserver zu Verbindungsproblemen gateway  <br/>    | Vermittlungsserver  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Vermittlungsserver an Gateway rufen Sie nach Abschluss Fehler  <br/> | Vermittlungsserver  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Kritische Netzwerkprobleme  <br/>                           | Edgeserver  <br/>        | 14353                              |                                  | 12288  <br/>           |

Im folgenden werden die Anruf-Kapazität Leistungsindikatoren, die überwacht werden sollen. Sollten weniger, die Veröffentlichung dieser Nummern werden 500 für die Cloud Connector standard Edition; weniger als 50 für Cloud Connector minimale Edition.

- LS:MediationServer - eingehende Calls(_Total)\- aktuellen 

- LS:MediationServer - ausgehende Calls(_Total)\- aktuellen 

- LS:MediationServer - eingehende Calls(_Total)\- Active medienumgehung Anrufe

- LS:MediationServer - ausgehende Calls(_Total)\- Active medienumgehung Anrufe

## <a name="see-also"></a>Siehe auch

Weitere Informationen zum Arbeiten mit OMS finden Sie unter den folgenden:

- [Suchen nach Daten anhand Protokolldateien Suchvorgänge in Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure Protokoll Analytics-Sprachreferenz (engl.)](https://docs.loganalytics.io/docs/Language-Reference)

- [Grundlegendes zu Warnungen im Protokoll Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Verbinden von Computern mit Windows mit dem Protokoll Analytics-Dienst in Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


