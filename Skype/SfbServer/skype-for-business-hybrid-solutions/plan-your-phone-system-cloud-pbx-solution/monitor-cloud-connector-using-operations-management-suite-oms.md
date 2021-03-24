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
description: In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector-Version 2.1 und höher mithilfe von Microsoft Operations Management Suite (OMS) überwachen.
ms.openlocfilehash: 55685aae01bdcc3c7c979627dbba910bb33203fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098541"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector-Version 2.1 und höher mithilfe von Microsoft Operations Management Suite (OMS) überwachen.

Sie können jetzt Ihre Cloud Connector-Bereitstellung, Version 2.1 und höher, mithilfe der Operations Management Suite (OMS), einer Microsoft Cloud-IT-Verwaltungslösung, überwachen. MIT OMS Log Analytics können Sie die Verfügbarkeit und Leistung von Ressourcen, einschließlich physischer und virtueller Computer, überwachen und analysieren. Weitere Informationen zu OMS und Log Analytics finden Sie unter [What is Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)

Dieses Thema enthält die folgenden Abschnitte:

- Voraussetzungen

- Konfigurieren von Cloud Connector für die Verwendung von OMS

- Konfigurieren von OMS

- Analysieren der Warnungen in Ihrem Log Analytics-Repository

- Empfohlener Überwachungssatz

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie OMS verwenden können, um Ihre Cloud Connector-Bereitstellung zu überwachen, benötigen Sie Folgendes:

- **Ein Azure-Konto und ein OMS-Arbeitsbereich.** Wenn Sie noch nicht über ein Azure-Konto verfügen, müssen Sie eins erstellen, um OMS Log Analytics zu verwenden. Informationen zum Erstellen eines Azure-Kontos und zum Einrichten eines OMS-Arbeitsbereichs finden Sie unter Erste Schritte [mit einem Log Analytics-Arbeitsbereich](/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector, Version 2.1 oder höher**

- **Die neue Protokollsuche in Log Analytics** ist für die Cloud Connector-Überwachung erforderlich. Weitere Informationen finden Sie unter [Upgrade your Azure Log Analytics workspace to new log search](/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Konfigurieren von Cloud Connector für die Verwendung von OMS

Sie müssen Ihre lokale Cloud Connector-Umgebung für die Verwendung von OMS konfigurieren. Dazu benötigen Sie ihre OMS-Arbeitsbereichs-ID und den Schlüssel, die Sie mithilfe des OMS-Portals wie folgt finden können: Einstellungen -- Verbundene Quellen \> -- \> Windows-Server:

![Screenshot für Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

Wie Sie Cloud Connector für die Verwendung von OMS konfigurieren, hängt von Ihrem Szenario ab:

- **Wenn Sie eine neue Cloud Connector-Appliance** installieren oder eine Appliance erneut bereitstellen möchten, führen Sie die folgenden Schritte aus, bevor Sie Install-CcAppliance ausführen:

    1. Legen Sie im CloudConnector.ini Datei [Common] den Parameter OMSEnabled auf True.

        Jedes Mal, wenn Cloud Connector bereitgestellt oder aktualisiert wird, wird versucht, den OMS-Agent automatisch auf den VMs zu installieren. Aktivieren Sie dieses Feature, damit der OMS-Agent das automatische Update von Cloud Connector überstehen kann.

    2. Führen Sie zum Konfigurieren der OMS-ID und des Schlüssels Set-CcCredential -AccountType OMSWorkspace aus. 

- **Wenn Sie einen OMS-Agent auf einer vorhandenen Cloud Connector-Appliance** installieren, führen Sie die folgenden Schritte aus:

    1. Legen Sie CloudConnector.ini Datei [Common] im Abschnitt OMSEnabled=true. 

    2. Führen Sie Import-CcConfiguration aus. 

    3. Führen Sie Install-CcOMSAgent aus. 

        > [!NOTE]
        > Wenn die OMSWorkspace-Anmeldeinformationen noch nie festgelegt wurden, werden Sie beim Ausführen von install-CcOMSAgent zur Eingabe der Anmeldeinformationen aufgefordert. 

- **Wenn Sie die OMS-Arbeitsbereichs-ID oder den Schlüssel in einer Cloud Connector-Appliance aktualisieren möchten, die bereits einen OMS-Agent installiert hat:**

    1. Führen Sie zum Konfigurieren der OMS-ID und des Schlüssels Set-CcCredential -AccountType OMSWorkspace aus. 

    2. Führen Sie Install-CcOMSAgent aus, um die Updates anzuwenden. 

- **Überprüfen Sie für alle Szenarien, ob die Agents wie folgt verbunden sind:**

    Wechseln Sie im OMS-Portal zu Einstellungen – \> Verbundene Quellen – \> Windows-Server. Es wird eine Liste der verbundenen Computer angezeigt. 

## <a name="configure-oms"></a>Konfigurieren von OMS

Als Nächstes müssen Sie Ihre OMS-Konfiguration mithilfe des OMS-Portals angeben. Insbesondere müssen Sie:

- Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren an.

- Benachrichtigungen erstellen. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Angeben von Informationen zu Ereignisprotokollen und Leistungsindikatoren

Im OMS-Portal müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:

1. Wechseln Sie zu Einstellungen- \> Daten- \> Windows-Ereignisprotokolle, und fügen Sie Ereignisprotokolle hinzu für: 

   - Lync Server

   - Anwendung

     > [!NOTE]
     > Sie müssen Lync Server manuell in das Textfeld eingeben. Es wird nicht als Option in der Dropdownliste angezeigt. 

     Weitere Informationen finden Sie unter [Windows-Ereignisprotokolldatenquellen in Log Analytics.](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Wechseln Sie zu Einstellungen– \> Daten– \> Windows-Leistungsindikatoren, und fügen Sie Leistungsindikatoren hinzu für: 

   - **Leistungsindikatoren auf Betriebssystemebene**. Sie können Leistungsindikatoren auf Betriebssystemebene hinzufügen, z. B. Prozessorauslastung, Arbeitsspeichernutzung, Netzwerknutzung, oder Sie können vorhandene Lösungen wie Kapazität und Leistung, Netzwerkleistungsüberwachung ohne explizites Hinzufügen von Leistungsindikatoren verwenden. Unabhängig davon, wie Sie sie überwachen möchten, empfiehlt Microsoft, diese Betriebssystemindikatoren zu überwachen.

   - **Skype for Business-Zähler**. Es gibt zahlreiche Leistungsindikatoren, die von Skype for Business bereitgestellt werden. Sie können diese Leistungsindikatoren finden, indem Sie sich bei einem beliebigen Vermittlungsserver anmelden und den Leistungsmonitor öffnen. Diese Leistungsindikatoren beginnen mit "LS:". Microsoft empfiehlt, mindestens mit den folgenden Kapazitätsindikatoren zu beginnen und weitere hinzuzufügen, die von Interesse sind:

     Gesamtzahl der aktiven Anrufe:

       - LS:MediationServer – Eingehende Anrufe(_Total) \- Aktuell 

       - LS:MediationServer – Ausgehende Anrufe(_Total) \- Aktuell 

     Gesamtzahl aktiver Medienumgehungsaufrufe:

       - LS:MediationServer – Eingehende Anrufe(_Total) \- Aktive Medienumgehungsanrufe 

       - LS:MediationServer – Ausgehende Anrufe(_Total) \- Aktive Medienumgehungsanrufe 

     > [!NOTE]
     > Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben. Sie werden nicht als Optionen in der Dropdownliste angezeigt. 

     Weitere Informationen finden Sie unter [Windows- und Linux-Leistungsdatenquellen in Log Analytics.](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Erstellen von Warnungen

Es gibt zwei Arten von Warnungen in OMS: Anzahl der Ergebniswarnungen und Metrikmesswarnungen. Weitere Informationen zum Erstellen von Warnungen finden Sie unter [Arbeiten mit Warnungsregeln in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).

Beim Erstellen von Warnungen sollten Sie Folgendes berücksichtigen:

- Stellen Sie sicher, dass es sich bei der Warnung um eine Benachrichtigung über die Anzahl der Ergebnisse handelt. Dies ist die Standardauswahl. 

- Die Demoabfragen erfordern, dass "Anzahl der Ergebnisse" auf "Größer als 0" festgelegt ist. 

- Es wird empfohlen, zeitfenster und Warnungshäufigkeit auf 5 Minuten zu setzen. 

- Es wird empfohlen, "Warnungen unterdrücken" für Demowarnungen nicht zu aktivieren. 

- Für typische Warnungsszenarien empfiehlt Microsoft das Erstellen eines Benachrichtigungspaars: eine Fehlerwarnung und eine Reset-Warnung. Wählen Sie für die Fehlerwarnung den Schweregrad Kritisch aus. Wählen Sie für die Reset-Warnung den Schweregrad Informational aus.

In den folgenden Abschnitten wird beschrieben, wie Sie Beispielwarnungen erstellen.

 **Erstellen eines Warnungspaars: "RTCMEDSRV wird nicht auf Vermittlungsservern ausgeführt" und "RTCMEDSRV wird wieder auf Vermittlungsservern ausgeführt"**

So erstellen Sie dieses Warnungspaar:

- Die Abfrage für die Fehlerwarnung ist:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    Die Abfrage verwendet den Computerfilter, *in dem Computer "MediationServer" enthält.* Der Filter wählt nur den Computer aus, dessen Name die Zeichenfolge "MediationServer" enthält.

     Ersetzen Sie den Filter durch einen eigenen Computerfilter, oder entfernen Sie ihn einfach. Sie können komplexe Zeichenfolgenfilter ohne reguläre Ausdrücke erstellen. Weitere Informationen finden Sie unter [Zeichenfolgenoperatoren](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Sie können auch reguläre Ausdrücke verwenden. Darüber hinaus können Sie eine Computergruppe erstellen, indem Sie eine Suchabfrage speichern und diese Gruppe als Computerfilter in Ihrer Warnungsabfrage verwenden. Weitere Informationen finden Sie unter [Computergruppen in Log Analytics-Protokollsuchen](/azure/log-analytics/log-analytics-computer-groups).

    Für jeden Computer wird von der Fehlerabfrage das letzte Ereignisprotokoll für den Start- und Dienststopp des RTCMEDSRV-Diensts angezeigt. Es gibt ein Protokoll zurück, wenn das letzte Ereignis das Dienststoppereignis ist. es gibt nichts zurück, wenn das letzte Ereignis das Dienststartereignis ist. Kurz gesagt, die Abfrage würde eine Liste der Server zurückgeben, deren RTCMEDSRV im Zeitfenster beendet wird. 

- Die Abfrage für die Zurücksetzungswarnung ist:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    Die Reset-Abfrage führt genau das Gegenteil der Fehlerabfrage aus. Für jeden Computer wird eins zurückgeben, wenn das letzte Ereignis das Dienststartereignis ist. es gibt nichts zurück, wenn das letzte Ereignis das Dienststoppereignis ist.

**Erstellen eines Warnungspaars: "Zu viele gleichzeitige Anrufe auf Vermittlungsservern" und "Gleichzeitige Anrufe werden wieder normal geladen"**

So erstellen Sie diese Warnung:

- Die Abfrage für die Fehlerwarnung ist:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Für jeden Computer wird die Abfrage die letzten Leistungsindikatoren für eingehenden Anruf und ausgehenden Anruf erhalten und diese beiden Werte summieren. Es gibt ein Protokoll zurück, wenn der Summenwert 500 überschreitet. Es gibt nichts zurück, wenn dies nicht der Derb ist. Kurz gesagt, die Abfrage würde eine Liste der Server zurückgeben, deren gleichzeitige Anrufe im Zeitfenster zu viele sind.

- Die Abfrage für die Zurücksetzungswarnung ist:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    Die Reset-Abfrage führt genau das Gegenteil der Fehlerabfrage aus. Für jeden Computer wird die Abfrage die letzten Leistungsindikatoren für eingehenden Anruf und ausgehenden Anruf erhalten und diese beiden Werte summieren. Es gibt ein Protokoll zurück, wenn der Summenwert kleiner als 500 ist. Andernfalls gibt es nichts zurück.

**Erstellen einer Warnung: Warnung "CPU-Auslastung \> 90 oder RTCMEDIARELAY auf Servern beendet"**

Um diese Warnung zu erstellen, ist die Abfrage:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

Die Abfrage wird alle Prozessorverwendungsindikatoren und Dienststopp-Ereignisse von allen Computern erhalten und ein Protokoll zurückgeben, wenn entweder die Prozessorauslastung 90 % überschreitet oder der Dienst jemals beendet wird. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analysieren der Warnungen in Ihrem Log Analytics-Repository

Verwenden Sie die Warnungsverwaltungslösung, um die Warnungen in Ihrem Repository zu analysieren. Weitere Informationen finden Sie unter [Warnungsverwaltungslösung in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Empfohlene minimale Überwachungssatz

So identifizieren Sie Probleme mit Ereignisprotokollen und Leistungsindikatoren: 

- **Ereignisprotokolle.** Bei jedem Problem sollte ein Ereignispaar mit einer Gruppe von Ereignissen angegeben werden, um anzuzeigen, dass etwas nicht stimmt, während der andere angibt, dass alles gut ist. Für einen bestimmten Zeitraum ist es das letzte aufgezeichnete Ereignis, das angibt, ob für den Zeitraum etwas nicht zulässig ist.

- **Leistungsindikatoren.** Es sollte ein Schwellenwert für die überwachten Leistungsindikatoren festgelegt werden.

In der folgenden Tabelle sind die Dienste aufgeführt, die Von Microsoft die Überwachung empfiehlt, indem die IDs des Stop- und Startereigniss aufgeführt werden:

|Dienstname  <br/> |Zielserverrolle  <br/> |Ereignis-ID beenden  <br/> |Startereignis-ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Vermittlungsserver  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edgeserver  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edgeserver  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edgeserver  <br/> |22003  <br/> |22002  <br/> |

In der folgenden Tabelle sind die Von Microsoft empfohlenen Netzwerkprobleme aufgeführt:


| Monitorname  <br/>                                        | Zielserverrolle  <br/> | Success-Ereignis-ID-Ausdruck  <br/> | Error-Ereignis-ID-Ausdruck  <br/> | Fehlerbeispiel  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Vermittlungsserver bei Ausfall der Gatewaykonnektivität  <br/>    | Vermittlungsserver  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Fehler beim Abschluss des Vermittlungsservers für Gatewayanrufe  <br/> | Vermittlungsserver  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Kritische Netzwerkprobleme  <br/>                           | Edgeserver  <br/>        | 14353                              |                                  | 12288  <br/>           |

Im Folgenden werden die Anrufkapazitätsindikatoren aufgeführt, die überwacht werden sollen. Diese Zahlen sollten weniger als 500 für cloudconnector standard edition sein. weniger als 50 für Die Mindestversion von Cloud Connector.

- LS:MediationServer – Eingehende Anrufe(_Total) \- Aktuell 

- LS:MediationServer – Ausgehende Anrufe(_Total) \- Aktuell 

- LS:MediationServer – Eingehende Anrufe(_Total) \- Aktive Medienumgehungsanrufe

- LS:MediationServer – Ausgehende Anrufe(_Total) \- Aktive Medienumgehungsanrufe

## <a name="see-also"></a>Siehe auch

Weitere Informationen zum Arbeiten mit OMS finden Sie in den folgenden Themen:

- [Suchen von Daten mithilfe von Protokollsuchen in Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics-Sprachreferenz](https://docs.loganalytics.io/docs/Language-Reference)

- [Grundlegendes zu Warnungen in Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Verbinden von Windows-Computern mit dem Protokollanalysedienst in Azure](/azure/log-analytics/log-analytics-windows-agents)