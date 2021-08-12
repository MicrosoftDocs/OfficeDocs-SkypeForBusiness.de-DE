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
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector Version 2.1 und höher mithilfe von Microsoft Operations Management Suite (OMS) überwachen.
ms.openlocfilehash: 1e2156ec8cff777b7bbad595b9792972508edbd455d6a1d27a65b95ad01c5def
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339991"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector Version 2.1 und höher mithilfe von Microsoft Operations Management Suite (OMS) überwachen.

Sie können jetzt Ihre Cloud Connector-Version 2.1 und höher mithilfe von Operations Management Suite (OMS) überwachen, einer Microsoft Cloud IT-Verwaltungslösung. Mit OMS Log Analytics können Sie die Verfügbarkeit und Leistung von Ressourcen, einschließlich physischer und virtueller Computer, überwachen und analysieren. Weitere Informationen zu OMS und Log Analytics finden Sie unter [Was ist Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)

Dieses Thema enthält die folgenden Abschnitte:

- Voraussetzungen

- Konfigurieren von Cloud Connector für die Verwendung von OMS

- Konfigurieren von OMS

- Analysieren der Warnungen in Ihrem Log Analytics-Repository

- Empfohlener Überwachungssatz

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie OMS zum Überwachen Ihrer Cloud Connector-Bereitstellung verwenden können, benötigen Sie Folgendes:

- **Ein Azure-Konto und ein OMS-Arbeitsbereich.** Wenn Sie noch nicht über ein Azure-Konto verfügen, müssen Sie ein Konto für die Verwendung von OMS Log Analytics erstellen. Informationen zum Erstellen eines Azure-Kontos und Einrichten eines OMS-Arbeitsbereichs finden Sie unter ["Erste Schritte mit einem Log Analytics-Arbeitsbereich".](/azure/log-analytics/log-analytics-get-started)

- **Cloud Connector, Version 2.1 oder höher**

- Für die Überwachung von Cloud Connector ist eine **neue Protokollsuche** für Log Analytics erforderlich. Weitere Informationen finden Sie unter [Upgrade Ihres Azure Log Analytics-Arbeitsbereichs auf die neue Protokollsuche.](/azure/log-analytics/log-analytics-log-search-upgrade)

## <a name="configure-cloud-connector-to-use-oms"></a>Konfigurieren von Cloud Connector für die Verwendung von OMS

Sie müssen Ihre lokale Cloud Connector-Umgebung für die Verwendung von OMS konfigurieren. Dazu benötigen Sie Ihre OMS-Arbeitsbereichs-ID und den Schlüssel, die Sie im OMS-Portal wie folgt finden können: Einstellungen - \> verbundene Quellen - Windows \> Server:

![Screenshot für Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

Wie Sie Cloud Connector für die Verwendung von OMS konfigurieren, hängt von Ihrem Szenario ab:

- **Wenn Sie eine neue Cloud Connector-Appliance installieren oder eine Appliance erneut bereitstellen möchten,** führen Sie die folgenden Schritte aus, bevor Sie Install-CcAppliance ausführen:

    1. Legen Sie im Abschnitt CloudConnector.ini Datei [Common] den Parameter OMSEnabled auf "True" fest.

        Jedes Mal, wenn Cloud Connector bereitgestellt oder aktualisiert wird, versucht er, den OMS-Agent automatisch auf den VMs zu installieren. Aktivieren Sie dieses Feature, damit der OMS-Agent das automatische Update von Cloud Connector überstehen kann.

    2. Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie Set-CcCredential -AccountType OMSWorkspace aus. 

- **Wenn Sie einen OMS-Agent in einer vorhandenen Cloud Connector-Appliance installieren,** führen Sie die folgenden Schritte aus:

    1. Legen Sie im Abschnitt CloudConnector.ini Datei [Common] OMSEnabled=true fest. 

    2. Führen Sie "Import-CcConfiguration" aus. 

    3. Führen Sie Install-CcOMSAgent aus. 

        > [!NOTE]
        > Wenn die OMSWorkspace-Anmeldeinformationen noch nie festgelegt wurden, werden Sie beim Ausführen von install-CcOMSAgent zur Eingabe der Anmeldeinformationen aufgefordert. 

- **Wenn Sie die OMS-Arbeitsbereichs-ID oder den Schlüssel in einer Cloud Connector-Appliance aktualisieren möchten, die bereits einen OMS-Agent installiert hat:**

    1. Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie Set-CcCredential -AccountType OMSWorkspace aus. 

    2. Führen Sie Install-CcOMSAgent aus, um die Updates anzuwenden. 

- **Stellen Sie für alle Szenarien sicher, dass die Agents wie folgt verbunden sind:**

    Wechseln Sie im OMS-Portal zu Einstellungen – \> verbundene Quellen – Windows \> Server. Es wird eine Liste der verbundenen Computer angezeigt. 

## <a name="configure-oms"></a>Konfigurieren von OMS

Als Nächstes müssen Sie Ihre OMS-Konfiguration mithilfe des OMS-Portals angeben. Insbesondere müssen Sie Folgendes ausführen:

- Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren an.

- Benachrichtigungen erstellen. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Angeben von Informationen zu Ereignisprotokollen und Leistungsindikatoren

Im OMS-Portal müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:

1. Wechseln Sie zu Einstellungen– \> Daten- \> Windows Ereignisprotokollen, und fügen Sie Ereignisprotokolle für: 

   - Lync Server

   - Anwendung

     > [!NOTE]
     > Sie müssen Lync Server manuell in das Textfeld eingeben. Es wird nicht als Option in der Dropdownliste angezeigt. 

     Weitere Informationen finden Sie unter [Windows Ereignisprotokolldatenquellen in Log Analytics.](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Wechseln Sie zu Einstellungen– \> Daten- \> Windows Leistungsindikatoren, und fügen Sie Leistungsindikatoren für Folgendes hinzu: 

   - **Leistungsindikatoren auf Betriebssystemebene.** Sie können Leistungsindikatoren auf Betriebssystemebene hinzufügen, z. B. Prozessorauslastung, Speicherauslastung, Netzwerkauslastung oder vorhandene Lösungen wie Kapazität und Leistung, Netzwerkleistungsmonitor, ohne explizit Leistungsindikatoren hinzuzufügen. Unabhängig davon, wie Sie diese überwachen möchten, empfiehlt Microsoft, diese Betriebssystemzähler zu überwachen.

   - **Skype for Business Indikatoren.** Es gibt zahlreiche Leistungsindikatoren, die von Skype for Business bereitgestellt werden. Sie finden diese Leistungsindikatoren, indem Sie sich bei einem beliebigen Vermittlungsserver anmelden und den Leistungsmonitor öffnen. Diese Indikatoren beginnen mit "LS:". Microsoft empfiehlt, mindestens mit den folgenden Kapazitätszählern zu beginnen und andere, die von Interesse sind, hinzuzufügen:

     Aktive Anrufe insgesamt:

       - LS:MediationServer – Eingehende Anrufe(_Total) \- aktuell 

       - LS:MediationServer – Ausgehende Anrufe(_Total) \- aktuell 

     Aktive Medienumgehungsaufrufe insgesamt:

       - LS:MediationServer – Eingehende Anrufe(_Total) \- Aktive Medienumgehungsaufrufe 

       - LS:MediationServer – Ausgehende Anrufe(_Total) \- Aktive Medienumgehungsaufrufe 

     > [!NOTE]
     > Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben. Sie werden nicht als Optionen in der Dropdownliste angezeigt. 

     Weitere Informationen finden Sie unter [Windows und Linux-Leistungsdatenquellen in Log Analytics.](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Erstellen von Warnungen

Es gibt zwei Arten von Warnungen in OMS: Anzahl der Ergebniswarnungen und Metrikmessungswarnungen. Weitere Informationen zum Erstellen von Warnungen finden Sie unter [Arbeiten mit Warnungsregeln in Log Analytics.](/azure/log-analytics/log-analytics-alerts-creating)

Beim Erstellen von Warnungen sollten Sie Folgendes berücksichtigen:

- Stellen Sie sicher, dass es sich bei der Warnung um eine Warnung mit der Anzahl der Ergebnisse handelt, bei der es sich um die Standardauswahl handelt. 

- Die Demoabfragen erfordern, dass "Anzahl der Ergebnisse" auf "Größer als 0" festgelegt ist. 

- Es wird empfohlen, sowohl das Zeitfenster als auch die Benachrichtigungshäufigkeit auf 5 Minuten festzulegen. 

- Es wird empfohlen, "Warnungen unterdrücken" für Demobenachrichtigungen nicht zu aktivieren. 

- Für typische Warnungsszenarien empfiehlt Microsoft das Erstellen eines Warnungspaars: eine Fehlerwarnung und eine Zurücksetzungswarnung. Wählen Sie für die Fehlerwarnung den Schweregrad "Kritisch" aus. wählen Sie für die Zurücksetzungswarnung den Schweregrad "Informational" aus.

In den folgenden Abschnitten wird beschrieben, wie Sie Beispielwarnungen erstellen.

 **Erstellen Sie ein Warnungspaar: "RTCMEDSRV wird NICHT auf Vermittlungsservern ausgeführt" und "RTCMEDSRV wird wieder auf Vermittlungsservern ausgeführt"**

So erstellen Sie dieses Warnungspaar:

- Die Abfrage für die Fehlerwarnung lautet:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    Die Abfrage verwendet den *Computerfilter, wobei Computer "MediationServer" enthält.* Der Filter wählt nur den Computer aus, dessen Name die Zeichenfolge "MediationServer" enthält.

     Sie würden den Filter durch Ihren eigenen Computerfilter ersetzen oder einfach entfernen. Sie können komplexe Zeichenfolgenfilter ohne reguläre Ausdrücke erstellen. Weitere Informationen finden Sie unter [Zeichenfolgenoperatoren.](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators) Sie können auch reguläre Ausdrücke verwenden. Darüber hinaus können Sie eine Computergruppe erstellen, indem Sie eine Suchabfrage speichern und diese Gruppe als Computerfilter in Der Warnungsabfrage verwenden. Weitere Informationen finden Sie unter [Computergruppen in Log Analytics-Protokollsuchen.](/azure/log-analytics/log-analytics-computer-groups)

    Für jeden Computer ruft die Fehlerabfrage das letzte Ereignisprotokoll für den RTCMEDSRV-Dienststart und den Dienststopp ab. Es wird ein Protokoll zurückgegeben, wenn das letzte Ereignis das Dienststoppereignis ist. es wird nichts zurückgegeben, wenn das letzte Ereignis das Dienststartereignis ist. Kurz gesagt würde die Abfrage eine Liste der Server zurückgeben, deren RTCMEDSRV im Zeitfenster beendet wird. 

- Die Abfrage für die Zurücksetzungswarnung lautet:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    Die Zurücksetzungsabfrage führt genau das Gegenteil der Fehlerabfrage aus. Für jeden Computer wird eins zurückgegeben, wenn das letzte Ereignis das Startereignis des Diensts ist. wenn das letzte Ereignis das Dienststoppereignis ist, wird nichts zurückgegeben.

**Erstellen Sie ein Warnungspaar: "Zu viele gleichzeitige Anrufe in Vermittlungsservern" und "Gleichzeitige Anrufe fallen auf normale Last zurück"**

So erstellen Sie diese Warnung:

- Die Abfrage für die Fehlerwarnung lautet:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Für jeden Computer ruft die Abfrage die letzten Leistungsindikatoren für eingehende und ausgehende Anrufe ab und summiert diese beiden Werte. Wenn der Summenwert 500 überschreitet, wird ein Protokoll zurückgegeben. wenn dies nicht der Fall ist, wird nichts zurückgegeben. Kurz gesagt, würde die Abfrage eine Liste der Server zurückgeben, deren gleichzeitige Aufrufe im Zeitfenster zu viele sind.

- Die Abfrage für die Zurücksetzungswarnung lautet:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    Die Zurücksetzungsabfrage führt genau das Gegenteil der Fehlerabfrage aus. Für jeden Computer ruft die Abfrage die letzten Leistungsindikatoren für eingehende und ausgehende Anrufe ab und summiert diese beiden Werte. Es wird ein Protokoll zurückgegeben, wenn der Summenwert kleiner als 500 ist. andernfalls wird nichts zurückgegeben.

**Erstellen einer Warnung: Warnung \> "CPU-Auslastung 90 oder RTCMEDIARELAY in Servern beendet"**

Zum Erstellen dieser Warnung lautet die Abfrage wie folgt:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

Die Abfrage ruft den gesamten Prozessornutzungszähler und das Dienststoppereignis von allen Computern ab und gibt ein Protokoll zurück, wenn die Prozessorauslastung 90 % überschreitet oder der Dienst beendet wird. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analysieren der Warnungen in Ihrem Log Analytics-Repository

Verwenden Sie die Warnungsverwaltungslösung, um die Warnungen in Ihrem Repository zu analysieren. Weitere Informationen finden Sie unter [Warnungsverwaltungslösung in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Empfohlener minimaler Überwachungssatz

So identifizieren Sie Probleme mit Ereignisprotokollen und Leistungsindikatoren: 

- **Ereignisprotokolle.** Für jedes Problem sollte ein Ereignispaar vorhanden sein, mit einem Satz von Ereignissen, um darauf hinzuweisen, dass etwas falsch ist, während das andere angibt, dass alles gut ist. Für einen bestimmten Zeitraum ist es das letzte aufgezeichnete Ereignis, das angibt, ob für diesen Zeitraum ein Fehler aufgetreten ist.

- **Leistungsindikatoren.** Es sollte ein Schwellenwert für die überwachten Indikatoren vorhanden sein.

In der folgenden Tabelle sind die Von Microsoft empfohlenen Dienste aufgeführt, indem die Ereignis-IDs für "Beenden" und "Starten" aufgelistet werden:

|Dienstname  <br/> |Zielserverrolle  <br/> |Stoppereignis-ID  <br/> |Startereignis-ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Vermittlungsserver  <br/> |25003  <br/> |25002  <br/> |
|Rtcsrv  <br/> |Edgeserver  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edgeserver  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edgeserver  <br/> |22003  <br/> |22002  <br/> |

In der folgenden Tabelle sind die Netzwerkprobleme aufgeführt, die Microsoft zu überwachen empfiehlt:


| Monitorname  <br/>                                        | Zielserverrolle  <br/> | Ausdruck der Erfolgsereignis-ID  <br/> | Fehlerereignis-ID-Ausdruck  <br/> | Fehlerbeispiel  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Verbindungsfehler zwischen Vermittlungsserver und Gateway  <br/>    | Vermittlungsserver  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Anrufabschlussfehler zwischen Vermittlungsserver und Gateway  <br/> | Vermittlungsserver  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Kritische Netzwerkprobleme  <br/>                           | Edgeserver  <br/>        | 14353                              |                                  | 12288  <br/>           |

Im Folgenden sind die Anrufkapazitätszähler aufgeführt, die überwacht werden sollten. Diese Zahlen sollten kleiner als 500 für Cloud Connector Standard Edition sein. weniger als 50 für die Mindestversion von Cloud Connector.

- LS:MediationServer – Eingehende Anrufe(_Total) \- aktuell 

- LS:MediationServer – Ausgehende Anrufe(_Total) \- aktuell 

- LS:MediationServer – Eingehende Anrufe(_Total) \- Aktive Medienumgehungsaufrufe

- LS:MediationServer – Ausgehende Anrufe(_Total) \- Aktive Medienumgehungsaufrufe

## <a name="see-also"></a>Siehe auch

Weitere Informationen zum Arbeiten mit OMS finden Sie in den folgenden Themen:

- [Suchen von Daten mithilfe von Protokollsuchen in Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics-Sprachreferenz](https://docs.loganalytics.io/docs/Language-Reference)

- [Grundlegendes zu Warnungen in Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Verbinden Windows Von Computern zum Log Analytics-Dienst in Azure](/azure/log-analytics/log-analytics-windows-agents)