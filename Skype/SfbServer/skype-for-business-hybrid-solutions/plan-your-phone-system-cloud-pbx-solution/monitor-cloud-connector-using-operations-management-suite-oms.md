---
title: Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS).
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
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Cloud Connector-Version 2,1 und höher mithilfe von Microsoft Operations Management Suite (OMS) überwachen.
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359091"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS).

> [!Important]
> Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen. Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Cloud Connector-Version 2,1 und höher mithilfe von Microsoft Operations Management Suite (OMS) überwachen.

Sie können jetzt Ihre Cloud Connector-Version 2,1 und höher mithilfe von Operations Management Suite (OMS), einer Microsoft Cloud-IT-Verwaltungslösung, überwachen. Mit der OMS-Protokollanalyse können Sie die Verfügbarkeit und Leistung von Ressourcen, einschließlich physischer und virtueller Computer, überwachen und analysieren. Weitere Informationen zu OMS und zur Protokollanalyse finden Sie unter [Was ist Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

Dieses Thema enthält die folgenden Abschnitte:

- Voraussetzungen

- Konfigurieren von Cloud Connector für die Verwendung von OMS

- Konfigurieren von OMS

- Analysieren der Warnungen in Ihrem Protokollanalyse-Repository

- Empfohlene Überwachungsgruppe

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie OMS zum Überwachen Ihrer Cloud Connector-Bereitstellung verwenden können, benötigen Sie Folgendes:

- **Ein Azure-Konto und ein OMS-Arbeitsbereich.** Wenn Sie noch nicht über ein Azure-Konto verfügen, müssen Sie eine erstellen, um die OMS-Protokollanalyse zu verwenden. Informationen zum Erstellen eines Azure-Kontos und zum Einrichten eines OMS-Arbeitsbereichs finden Sie unter [Erste Schritte mit einem Log Analytics-Arbeitsbereich](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector Version 2,1 oder höher**

- **Log Analytics die neue Protokollsuche** ist für die Cloud Connector-Überwachung erforderlich. Weitere Informationen finden Sie unter [Aktualisieren des Azure Log Analytics-Arbeitsbereichs auf die neue Protokollsuche](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Konfigurieren von Cloud Connector für die Verwendung von OMS

Sie müssen Ihre lokale Cloud Connector-Umgebung für die Verwendung von OMS konfigurieren. Dazu benötigen Sie die OMS-Arbeitsbereichs-ID und den Schlüssel, die Sie über das OMS-Portal wie folgt finden: Settings-- \> Connected sources-- \> Windows Servers:

![Screenshot für Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

Wie Sie Cloud Connector für die Verwendung von OMS konfigurieren, hängt von Ihrem Szenario ab:

- **Wenn Sie eine neue Cloud Connector-Appliance installieren oder eine Appliance erneut bereitstellen möchten**, führen Sie die folgenden Schritte aus, bevor Sie Install-ccappliance "ausführen:

    1. Legen Sie im Abschnitt CloudConnector.ini Datei [common] den Parameter OMSEnabled auf true fest.

        Jedes Mal, wenn Cloud Connector bereitgestellt oder aktualisiert wird, wird versucht, den OMS-Agent automatisch auf den VMS zu installieren. Aktivieren Sie dieses Feature, damit der OMS-Agent das automatische Update für Cloud Connector überleben kann.

    2. Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie die Einstellung-CcCredential-AccountType OMSWorkspace aus. 

- **Wenn Sie einen OMS-Agent in einer vorhandenen Cloud Connector-Appliance installieren**, führen Sie die folgenden Schritte aus:

    1. Legen Sie im Abschnitt CloudConnector.ini Datei [common] OMSEnabled = true fest. 

    2. Führen Sie Import-CcConfiguration aus. 

    3. Führen Sie Install-CcOMSAgent aus. 

        > [!NOTE]
        > Wenn die OMSWorkspace-Anmeldeinformationen noch nie festgelegt wurden, werden Sie zur Eingabe der Anmeldeinformationen aufgefordert, wenn Sie Install-CcOMSAgent ausführen. 

- **Wenn Sie die OMS-Arbeitsbereichs-ID oder den Schlüssel in einer Cloud Connector-Appliance aktualisieren möchten, die bereits einen OMS-Agent installiert hat:**

    1. Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie die Einstellung-CcCredential-AccountType OMSWorkspace aus. 

    2. Um die Updates zu übernehmen, führen Sie Install-CcOMSAgent aus. 

- **Stellen Sie für alle Szenarien sicher, dass die Agents wie folgt verbunden sind:**

    Wechseln Sie im OMS-Portal zu Einstellungen – \> verbundene Quellen – \> Windows-Server. Es wird eine Liste der verbundenen Computer angezeigt. 

## <a name="configure-oms"></a>Konfigurieren von OMS

Als nächstes müssen Sie die OMS-Konfiguration mithilfe des OMS-Portals angeben. Konkret gilt Folgendes:

- Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren an.

- Benachrichtigungen erstellen. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Angeben von Informationen zu Ereignisprotokollen und Leistungsindikatoren

Im OMS-Portal müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:

1. Wechseln Sie zu Einstellungen- \> Daten- \> Windows-Ereignisprotokolle, und fügen Sie Ereignisprotokolle für hinzu: 

   - Lync Server

   - Anwendung

     > [!NOTE]
     > Sie müssen lync Server manuell in das Textfeld eingeben. Es wird nicht als Option in der Dropdownliste angezeigt. 

     Weitere Informationen finden Sie unter [Windows-Ereignisprotokoll-Datenquellen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Wechseln Sie zu Einstellungen- \> Daten- \> Windows-Leistungsindikatoren, und fügen Sie Leistungsindikatoren für hinzu: 

   - **Leistungsindikatoren auf Betriebssystemebene**. Sie können Leistungsindikatoren auf Betriebssystemebene hinzufügen, beispielsweise Prozessorauslastung, Speicherauslastung, Netzwerkauslastung oder vorhandene Lösungen wie Kapazität und Leistung, Netzwerk Leistungsüberwachung ohne explizites Hinzufügen von Leistungsindikatoren verwenden. Unabhängig davon, wie Sie diese überwachen möchten, empfiehlt Microsoft, diese Betriebssystem-Leistungsindikatoren zu überwachen.

   - **Skype for Business Zähler**. Es gibt zahlreiche Leistungsindikatoren, die von Skype for Business bereitgestellt werden. Sie finden diese Leistungsindikatoren, indem Sie sich bei jeder Vermittlungsserver anmelden und den System Monitor öffnen. Diese Indikatoren beginnen mit "ls:". Microsoft empfiehlt, dass Sie mindestens mit den folgenden Kapazitäts Indikatoren beginnen und weitere interessante hinzufügen:

     Aktive Aufrufe insgesamt:

       - LS: MediationServer-eingehende Anrufe (_Total) \- aktuell 

       - LS: MediationServer-ausgehende Anrufe (_Total) \- aktuell 

     Gesamtzahl aktiver Medien Umgehungs Aufrufe:

       - LS: MediationServer-eingehende Anrufe (_Total) \- aktive Medien Umgehungs Aufrufe 

       - LS: MediationServer-ausgehende Anrufe (_Total) \- aktive Medien Umgehungs Aufrufe 

     > [!NOTE]
     > Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben. Sie werden in der Dropdownliste nicht als Optionen angezeigt. 

     Weitere Informationen finden Sie unter [Windows und Linux Performance Data Sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) .

### <a name="create-alerts"></a>Erstellen von Benachrichtigungen

Es gibt zwei Arten von Warnungen in OMS: Anzahl der Ergebnis Warnungen und Metriken für die Messung von Warnungen. Weitere Informationen zum Erstellen von Warnungen finden Sie unter [Working with Alert Rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Beachten Sie beim Erstellen von Warnungen Folgendes:

- Stellen Sie sicher, dass es sich bei der Warnung um eine Anzahl von Ergebnis Warnungen handelt, bei der es sich um die Standardauswahl handelt. 

- Die Demo-Abfragen erfordern, dass "number of Results" auf "größer als 0" festgelegt ist. 

- Es wird empfohlen, dass Sie sowohl Zeitfenster als auch Warnungs Häufigkeit auf 5 Minuten festlegen. 

- Es wird empfohlen, die Option "Warnungen unterdrücken" für Demo Warnungen nicht zu aktivieren. 

- Für typische Warnungs Szenarien empfiehlt Microsoft das Erstellen eines Warnungs Paars: eine Fehlermeldung und eine Warnung für einen Reset. Wählen Sie für die Fehlermeldung Schweregrad kritisch aus. Wählen Sie für die Warnung zurücksetzen die Option Severity Level Information aus.

In den folgenden Abschnitten wird beschrieben, wie Sie Beispielwarnungen erstellen.

 **Erstellen eines Warnungs Paars: "RTCMEDSRV wird nicht auf Vermittlungsservern" und "RTCMEDSRV wird wieder in den Vermittlungsservern" gestartet.**

So erstellen Sie dieses Warnungs paar:

- Die Abfrage für die Fehlermeldung lautet wie folgt:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    Die Abfrage verwendet den Computerfilter  *, auf dem Computer "MediationServer" enthält*  . Der Filter wählt nur den Computer aus, dessen Name die Zeichenfolge "MediationServer" enthält.

     Sie würden den Filter durch ihren eigenen Computerfilter ersetzen oder einfach entfernen. Sie können komplexe Zeichenfolgenfilter ohne reguläre Ausdrücke erstellen. Weitere Informationen finden Sie unter [String Operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Sie können auch festlegen, dass reguläre Ausdrücke verwendet werden. Darüber hinaus können Sie eine Computergruppe erstellen, indem Sie eine Suchabfrage speichern und diese Gruppe als Computerfilter in ihrer Warnungs Abfrage verwenden. Weitere Informationen finden Sie unter [Computer Gruppen in Log Analytics-Suchprotokoll suchen](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Für jeden Computer Ruft die Fehler Abfrage das letzte Ereignisprotokoll sowohl für den RTCMEDSRV-Dienststart als auch für den Dienst Stopp ab. Wenn das letzte Ereignis das Dienstbeendigungsereignis ist, wird ein Protokoll zurückgegeben. Es gibt Nothing zurück, wenn das letzte Ereignis das Dienststart Ereignis ist. Kurz gesagt, würde die Abfrage eine Liste von Servern zurückgeben, deren RTCMEDSRV im Zeitfenster angehalten wurde. 

- Die Abfrage für die Zurücksetzungs Warnung lautet wie folgt:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    Die Reset-Abfrage macht genau das Gegenteil der Fehler Abfrage. Für jeden Computer wird eine zurückgegeben, wenn das letzte Ereignis das Dienststart Ereignis ist; andernfalls false. Es gibt Nothing zurück, wenn das letzte Ereignis das Dienstbeendigungsereignis ist.

**Erstellen eines Warnungs Paars: "zu viele gleichzeitige Anrufe in Vermittlungsservern" und "gleichzeitige Anrufe fallen wieder auf normale Last"**

So erstellen Sie diese Warnung:

- Die Abfrage für die Fehlermeldung lautet wie folgt:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Für jeden Computer Ruft die Abfrage die letzten Leistungsindikatoren für eingehende und ausgehende Anrufe ab und summiert diese beiden Werte. Wenn der Summenwert 500 überschreitet, wird ein Protokoll zurückgegeben. Wenn dies nicht der Fall ist, wird Nothing zurückgegeben. Kurz gesagt, würde die Abfrage eine Liste von Servern zurückgeben, deren gleichzeitige Anrufe zu viele im Zeitfenster sind.

- Die Abfrage für die Zurücksetzungs Warnung lautet wie folgt:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    Die Reset-Abfrage macht genau das Gegenteil der Fehler Abfrage. Für jeden Computer Ruft die Abfrage die letzten Leistungsindikatoren für eingehende und ausgehende Anrufe ab und summiert diese beiden Werte. Wenn der Summenwert kleiner als 500 ist, wird ein Protokoll zurückgegeben. Andernfalls wird nichts zurückgegeben.

**Warnung erstellen: "CPU-Auslastung \> 90 oder RTCMEDIARELAY in Servern angehalten"-Warnung**

Zum Erstellen dieser Warnung lautet die Abfrage wie folgt:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

Die Abfrage ruft alle Prozessor Nutzungszähler-und Dienst Stoppereignisse von allen Computern ab und gibt ein Protokoll zurück, wenn die Prozessorauslastung 90% überschreitet oder der Dienst jemals angehalten wird. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analysieren der Warnungen in Ihrem Protokollanalyse-Repository

Verwenden Sie die Warnungs Verwaltungslösung, um die Warnungen in Ihrem Repository zu analysieren. Weitere Informationen finden Sie unter [Alert Management Solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .

## <a name="recommended-minimal-monitoring-set"></a>Empfohlener minimaler Überwachungs Satz

So identifizieren Sie Probleme mit Ereignisprotokollen und Leistungsindikatoren: 

- **Ereignisprotokolle.** Bei jedem Problem sollte ein Ereignispaar vorhanden sein, wobei eine Gruppe von Ereignissen darauf hinweist, dass etwas falsch ist, während die andere angibt, dass alles gut ist. Für einen bestimmten Zeitraum ist es das letzte aufgezeichnete Ereignis, das angibt, ob für diesen Zeitraum ein Fehler aufgetreten ist.

- **Leistungsindikatoren.** Für die überwachten Leistungsindikatoren sollte ein Schwellenwert vorhanden sein.

In der folgenden Tabelle sind die Dienste aufgeführt, die von Microsoft überwachen empfohlen werden, indem die Ereignis-IDs Stop und Start aufgelistet werden:

|Dienst Name  <br/> |Ziel Server Rolle  <br/> |Ereignis-ID beenden  <br/> |Start Ereignis-ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Vermittlungsserver  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edgeserver  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edgeserver  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edgeserver  <br/> |22003  <br/> |22002  <br/> |

In der folgenden Tabelle sind die Netzwerkprobleme aufgeführt, die von Microsoft überwachen empfohlen werden:


| Monitor Name  <br/>                                        | Ziel Server Rolle  <br/> | Erfolgsereignis-ID-Ausdruck  <br/> | Fehlerereignis-ID-Ausdruck  <br/> | Fehler Beispiel  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Vermittlungsserver auf Gateway-Verbindungsfehler  <br/>    | Vermittlungsserver  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Vermittlungsserver zu Gateway-Anruf Abschluss Fehler  <br/> | Vermittlungsserver  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Wichtige Netzwerkprobleme  <br/>                           | Edgeserver  <br/>        | 14353                              |                                  | 12288  <br/>           |

Im folgenden sind die Leistungsindikatoren für die Anrufkapazität aufgeführt, die überwacht werden sollten. Diese Zahlen sollten niedriger sein als 500 für Cloud Connector Standard Edition; kleiner als 50 für Cloud Connector Minimum Edition.

- LS: MediationServer-eingehende Anrufe (_Total) \- aktuell 

- LS: MediationServer-ausgehende Anrufe (_Total) \- aktuell 

- LS: MediationServer-eingehende Anrufe (_Total) \- aktive Medien Umgehungs Aufrufe

- LS: MediationServer-ausgehende Anrufe (_Total) \- aktive Medien Umgehungs Aufrufe

## <a name="see-also"></a>Weitere Artikel

Weitere Informationen zum Arbeiten mit OMS finden Sie in den folgenden Themen:

- [Suchen von Daten mithilfe von Protokoll suchen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics – Sprachreferenz](https://docs.loganalytics.io/docs/Language-Reference)

- [Grundlegendes zu Warnungen in Protokollanalysen](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Verbinden von Windows-Computern mit dem Log Analytics-Dienst in Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


