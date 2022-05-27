---
title: Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS)
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Bereitstellung von Cloud Connector, Version 2.1 und höher, mithilfe von Microsoft Operations Management Suite (OMS) überwachen.
ms.openlocfilehash: c10eac34e065ab76cb570a21752838c308b6afd8
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676507"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition wird zusammen mit Skype for Business Online am 31. Juli 2021 eingestellt. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams mit [Direct Routing](/MicrosoftTeams/direct-routing-landing-page) verbinden.

Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Bereitstellung von Cloud Connector, Version 2.1 und höher, mithilfe von Microsoft Operations Management Suite (OMS) überwachen.

Sie können jetzt Ihre Cloud Connector Version 2.1 und höher mithilfe von Operations Management Suite (OMS) überwachen, einer Microsoft Cloud IT Management-Lösung. OMS Log Analytics ermöglicht Es Ihnen, die Verfügbarkeit und Leistung von Ressourcen einschließlich physischer und virtueller Computer zu überwachen und zu analysieren. Weitere Informationen zu OMS und Log Analytics finden Sie unter [Was ist Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)

Dieses Thema enthält die folgenden Abschnitte:

- Voraussetzungen

- Konfigurieren von Cloud Connector für die Verwendung von OMS

- Konfigurieren von OMS

- Analysieren der Warnungen in Ihrem Log Analytics-Repository

- Empfohlener Überwachungssatz

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie OMS zur Überwachung Ihrer Cloud Connector-Bereitstellung verwenden können, benötigen Sie Folgendes:

- **Ein Azure-Konto und ein OMS-Arbeitsbereich.** Wenn Sie noch nicht über ein Azure-Konto verfügen, müssen Sie ein Konto erstellen, um OMS Log Analytics verwenden zu können. Informationen zum Erstellen eines Azure-Kontos und zum Einrichten eines OMS-Arbeitsbereichs finden Sie [unter Erste Schritte mit einem Log Analytics-Arbeitsbereich](/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector, Version 2.1 oder höher**

- Für die Cloud Connector-Überwachung ist eine **neue Protokollsuche für Log Analytics** erforderlich. Weitere Informationen finden Sie unter [Upgrade Ihres Azure Log Analytics-Arbeitsbereichs auf eine neue Protokollsuche](/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Konfigurieren von Cloud Connector für die Verwendung von OMS

Sie müssen Ihre lokale Cloud Connector-Umgebung für die Verwendung von OMS konfigurieren. Dazu benötigen Sie Ihre OMS-Arbeitsbereichs-ID und Ihren OMS-Schlüssel, die Sie im OMS-Portal wie folgt finden können: Einstellungen --\>Connected Sources --\> Windows Servers:

![Screenshot für Cloud Connector OMS.](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

Wie Sie Cloud Connector für die Verwendung von OMS konfigurieren, hängt von Ihrem Szenario ab:

- **Wenn Sie eine neue Cloud Connector-Appliance installieren oder eine Appliance erneut bereitstellen möchten**, führen Sie die folgenden Schritte aus, bevor Sie Install-CcAppliance ausführen:

  1. Legen Sie im Abschnitt CloudConnector.ini Datei [Common] den PARAMETER OMSEnabled auf True fest.

     Jedes Mal, wenn Cloud Connector bereitgestellt oder aktualisiert wird, wird versucht, den OMS-Agent automatisch auf den VMs zu installieren. Aktivieren Sie dieses Feature, damit der OMS-Agent das automatische Update von Cloud Connector überstehen kann.

  2. Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie Set-CcCredential -AccountType OMSWorkspace aus.

- **Wenn Sie einen OMS-Agent auf einer vorhandenen Cloud Connector-Appliance installieren**, führen Sie die folgenden Schritte aus:

  1. Legen Sie im Abschnitt CloudConnector.ini Datei [Common] OMSEnabled=true fest.

  2. Führen Sie Import-CcConfiguration aus.

  3. Führen Sie Install-CcOMSAgent aus.

     > [!NOTE]
     > Wenn die OMSWorkspace-Anmeldeinformationen noch nie festgelegt wurden, werden Sie beim Ausführen von install-CcOMSAgent zur Eingabe der Anmeldeinformationen aufgefordert.

- **Wenn Sie die OMS-Arbeitsbereichs-ID oder den OMS-Schlüssel in einer Cloud Connector-Appliance aktualisieren möchten, die bereits einen OMS-Agent installiert hat:**

  1. Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie Set-CcCredential -AccountType OMSWorkspace aus.

  2. Um die Updates anzuwenden, führen Sie Install-CcOMSAgent aus.

- **Stellen Sie für alle Szenarien sicher, dass die Agents wie folgt verbunden sind:**

    Wechseln Sie im OMS-Portal zu Einstellungen –\> Verbundene Quellen –\> Windows Server. Es wird eine Liste der verbundenen Computer angezeigt.

## <a name="configure-oms"></a>Konfigurieren von OMS

Als Nächstes müssen Sie Ihre OMS-Konfiguration mithilfe des OMS-Portals angeben. Insbesondere müssen Sie:

- Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren an.

- Benachrichtigungen erstellen.

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Angeben von Informationen zu Ereignisprotokollen und Leistungsindikatoren

Im OMS-Portal müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:

1. Wechseln Sie zu Einstellungen-Data-Windows-Ereignisprotokollen\>\>, und fügen Sie Ereignisprotokolle für Folgendes hinzu:

   - Lync Server

   - Anwendung

     > [!NOTE]
     > Sie müssen Lync Server manuell in das Textfeld eingeben. Es wird nicht als Option in der Dropdownliste angezeigt.

     Weitere Informationen finden Sie [unter Windows ereignisprotokolldatenquellen in Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Wechseln Sie zu Einstellungen-Data\>-\> Windows Performance Counters, und fügen Sie Leistungsindikatoren für Folgendes hinzu:

   - **Indikatoren auf Betriebssystemebene**. Sie können Leistungsindikatoren auf Betriebssystemebene hinzufügen, z. B. Prozessorauslastung, Speicherauslastung, Netzwerknutzung, oder Sie können vorhandene Lösungen wie Kapazität und Leistung, Netzwerk-Leistungsmonitor verwenden, ohne Zähler explizit hinzuzufügen. Unabhängig davon, wie Sie sich entscheiden, sie zu überwachen, empfiehlt Microsoft, diese BS-Leistungsindikatoren zu überwachen.

   - **Skype for Business Zähler.** Es gibt zahlreiche Zähler von Skype for Business zur Verfügung gestellt. Sie finden diese Leistungsindikatoren, indem Sie sich bei einem beliebigen Vermittlungsserver anmelden und die Leistungsmonitor öffnen. Diese Leistungsindikatoren beginnen mit "LS:". Microsoft empfiehlt, mindestens mit den folgenden Kapazitätsindikatoren zu beginnen und weitere interessante Elemente hinzuzufügen:

     Gesamtzahl der aktiven Anrufe:

     - LS:MediationServer - Eingehende Anrufe(_Total)\- aktuell

     - LS:MediationServer - Ausgehende Anrufe(_Total)\- aktuell

     Gesamtanzahl aktiver Medienumgehungsaufrufe:

     - LS:MediationServer – Eingehende Anrufe (_Total)\- Anrufe über die Umgehung aktiver Medien

     - LS:MediationServer – Ausgehende Anrufe (_Total)\- Anrufe in der aktiven Medienumgehung

     > [!NOTE]
     > Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben. Sie werden nicht als Optionen in der Dropdownliste angezeigt.

     Weitere Informationen finden Sie [unter Windows und Linux-Leistungsdatenquellen in Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Erstellen von Warnungen

Es gibt zwei Arten von Warnungen in OMS: Anzahl der Ergebniswarnungen und metrische Messwarnungen. Weitere Informationen zum Erstellen von Warnungen finden [Sie unter Arbeiten mit Warnungsregeln in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).

Beim Erstellen von Warnungen sollten Sie Folgendes berücksichtigen:

- Stellen Sie sicher, dass es sich bei der Warnung um eine Warnung mit der Anzahl der Ergebnisse handelt, bei der es sich um die Standardauswahl handelt.

- Die Demoabfragen erfordern, dass "Anzahl der Ergebnisse" auf "Größer als 0" festgelegt ist.

- Es wird empfohlen, sowohl das Zeitfenster als auch die Benachrichtigungshäufigkeit auf 5 Minuten festzulegen.

- Es wird empfohlen, "Benachrichtigungen unterdrücken" nicht für Demobenachrichtigungen zu aktivieren.

- Für typische Warnungsszenarien empfiehlt Microsoft das Erstellen eines Warnungspaars: eine Fehler- und eine Rücksetzbenachrichtigung. Wählen Sie für die Fehlerwarnung den Schweregrad "Kritisch" aus. wählen Sie für die Warnung zum Zurücksetzen den Schweregrad "Informational" aus.

In den folgenden Abschnitten wird beschrieben, wie Sie Beispielwarnungen erstellen.

#### <a name="create-an-alert-pair-rtcmedsrv-is-not-running-in-mediation-servers-and-rtcmedsrv-is-back-in-running-in-mediation-servers"></a>Erstellen Eines Warnungspaars: "RTCMEDSRV wird NICHT auf Vermittlungsservern ausgeführt" und "RTCMEDSRV wird wieder auf Vermittlungsservern ausgeführt"

So erstellen Sie dieses Warnungspaar:

- Die Abfrage für die Fehlerwarnung lautet:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    Die Abfrage verwendet den Computerfilter  *, in dem Computer "MediationServer" enthält*  . Der Filter wählt nur den Computer aus, dessen Name die Zeichenfolge "MediationServer" enthält.

     Sie ersetzen den Filter durch Ihren eigenen Computerfilter oder entfernen ihn einfach. Sie können komplexe Zeichenfolgenfilter ohne reguläre Ausdrücke erstellen. Sie können auch reguläre Ausdrücke verwenden. Darüber hinaus können Sie eine Computergruppe erstellen, indem Sie eine Suchabfrage speichern und diese Gruppe als Computerfilter in Ihrer Warnungsabfrage verwenden. Weitere Informationen finden Sie [unter Computergruppen in Log Analytics-Protokollsuchen](/azure/log-analytics/log-analytics-computer-groups).

    Für jeden Computer ruft die Fehlerabfrage das letzte Ereignisprotokoll sowohl für den RTCMEDSRV-Dienststart als auch für den Dienststopp ab. Es wird ein Protokoll zurückgegeben, wenn das letzte Ereignis das Dienststoppereignis ist. es gibt nichts zurück, wenn das letzte Ereignis das Dienststartereignis ist. Kurz gesagt würde die Abfrage eine Liste der Server zurückgeben, deren RTCMEDSRV im Zeitfenster beendet wird.

- Die Abfrage für die Rücksetzwarnung lautet:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    Die Rücksetzabfrage führt genau das Gegenteil der Fehlerabfrage aus. Für jeden Computer wird eins zurückgegeben, wenn das letzte Ereignis das Dienststartereignis ist. es gibt nichts zurück, wenn das letzte Ereignis das Dienststoppereignis ist.

#### <a name="create-an-alert-pair--too-many-concurrent-calls-in-mediation-servers-and-concurrent-calls-fall-back-to-normal-load"></a>Erstellen Eines Warnungspaars: "Zu viele gleichzeitige Anrufe auf Vermittlungsservern" und "Gleichzeitige Anrufe fallen auf normales Laden zurück"

So erstellen Sie diese Warnung:

- Die Abfrage für die Fehlerwarnung lautet:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Für jeden Computer ruft die Abfrage die letzten Leistungsindikatoren für eingehenden und ausgehenden Anruf ab und addiert diese beiden Werte. Es wird ein Protokoll zurückgegeben, wenn der Summenwert 500 überschreitet. andernfalls wird nichts zurückgegeben. Kurz gesagt würde die Abfrage eine Liste der Server zurückgeben, deren gleichzeitige Aufrufe im Zeitfenster zu viele sind.

- Die Abfrage für die Rücksetzwarnung lautet:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    Die Rücksetzabfrage führt genau das Gegenteil der Fehlerabfrage aus. Für jeden Computer ruft die Abfrage die letzten Leistungsindikatoren für eingehenden und ausgehenden Anruf ab und addiert diese beiden Werte. Es wird ein Protokoll zurückgegeben, wenn der Summenwert kleiner als 500 ist. andernfalls wird nichts zurückgegeben.

#### <a name="create-an-alert-cpu-usage--90-or-rtcmediarelay-stopped-in-servers-alert"></a>Erstellen einer Warnung: Benachrichtigung "CPU-Auslastung \> 90 oder RTCMEDIARELAY wurde auf Servern beendet"

Um diese Warnung zu erstellen, lautet die Abfrage wie folgt:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

Die Abfrage ruft alle Prozessornutzungszähler und das Dienststoppereignis von allen Computern ab und gibt ein Protokoll zurück, wenn die Prozessorauslastung 90 % überschreitet oder der Dienst jemals beendet wird.

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analysieren der Warnungen in Ihrem Log Analytics-Repository

Verwenden Sie die Warnungsverwaltungslösung, um die Warnungen in Ihrem Repository zu analysieren. Weitere Informationen finden Sie [unter Warnungsverwaltungslösung in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Empfohlener minimaler Überwachungssatz

So identifizieren Sie Probleme mit Ereignisprotokollen und Leistungsindikatoren:

- **Ereignisprotokolle.** Bei jedem Problem sollte es ein Ereignispaar geben, wobei eine Gruppe von Ereignissen darauf hinweist, dass etwas nicht stimmt, während das andere darauf hinweist, dass alles gut ist. Für einen bestimmten Zeitraum ist es das letzte aufgezeichnete Ereignis, das angibt, ob etwas für diesen Zeitraum nicht stimmt.

- **Leistungsindikatoren.** Es sollte ein Schwellenwert für die überwachten Leistungsindikatoren vorhanden sein.

In der folgenden Tabelle sind die Dienste aufgeführt, die Von Microsoft empfohlen werden, indem die Stopp- und Startereignis-IDs aufgelistet werden:

|Dienstname  <br/> |Zielserverrolle  <br/> |Ereignis-ID beenden  <br/> |Startereignis-ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Vermittlungsserver  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edgeserver  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edgeserver  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edgeserver  <br/> |22003  <br/> |22002  <br/> |

In der folgenden Tabelle sind die Netzwerkprobleme aufgeführt, die Von Microsoft empfohlen werden:


| Monitorname  <br/>                                        | Zielserverrolle  <br/> | Ausdruck der Erfolgsereignis-ID  <br/> | Fehlerereignis-ID-Ausdruck  <br/> | Fehlerbeispiel  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Vermittlungsserver- zu Gatewayverbindungsfehler  <br/>    | Vermittlungsserver  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Vermittlungsserver zum Abschluss von Gatewayanrufen  <br/> | Vermittlungsserver  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Kritische Netzwerkprobleme  <br/>                           | Edgeserver  <br/>        | 14353                              |                                  | 12288  <br/>           |

Im Folgenden sind die Anrufkapazitätszähler aufgeführt, die überwacht werden sollen. Diese Zahlen sollten weniger als 500 für die Cloud Connector-Standardedition betragen. weniger als 50 für die Mindestedition von Cloud Connector.

- LS:MediationServer - Eingehende Anrufe(_Total)\- aktuell

- LS:MediationServer - Ausgehende Anrufe(_Total)\- aktuell

- LS:MediationServer – Eingehende Anrufe (_Total)\- Anrufe über die Umgehung aktiver Medien

- LS:MediationServer – Ausgehende Anrufe (_Total)\- Anrufe in der aktiven Medienumgehung

## <a name="see-also"></a>Siehe auch

Weitere Informationen zum Arbeiten mit OMS finden Sie in den folgenden Themen:

- [Suchen von Daten mithilfe von Protokollsuchen in Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Grundlegendes zu Warnungen in Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Verbinden Windows von Computern an den Log Analytics-Dienst in Azure](/azure/log-analytics/log-analytics-windows-agents)