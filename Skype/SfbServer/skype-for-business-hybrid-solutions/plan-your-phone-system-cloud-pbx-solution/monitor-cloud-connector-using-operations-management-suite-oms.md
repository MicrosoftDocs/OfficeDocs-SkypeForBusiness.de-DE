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
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector-Version 2,1 und spätere Bereitstellung mithilfe von Microsoft Operations Management Suite (OMS) überwachen.
ms.openlocfilehash: 6258ad9386b895f97a6f6dc0a1b40ce1076568aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287265"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS).

In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector-Version 2,1 und spätere Bereitstellung mithilfe von Microsoft Operations Management Suite (OMS) überwachen.

Sie können jetzt die Bereitstellung von Cloud Connector, Version 2,1 und höher, mithilfe von Operations Management Suite (OMS), einer Microsoft Cloud-IT-Verwaltungslösung, überwachen. Mithilfe der OMS-Protokollanalyse können Sie die Verfügbarkeit und Leistung von Ressourcen, einschließlich physischer und virtueller Computer, überwachen und analysieren. Weitere Informationen zu OMS und zur Protokollanalyse finden Sie unter [Was ist Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).

Dieses Thema enthält die folgenden Abschnitte:

- Voraussetzungen

- Konfigurieren des Cloud Connectors für die Verwendung von OMS

- Konfigurieren von OMS

- Analysieren der Warnungen in Ihrem Protokollanalyse-Repository

- Empfohlener Überwachungs Satz

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie OMS zum Überwachen Ihrer Cloud Connector-Bereitstellung verwenden können, benötigen Sie Folgendes:

- **Ein Azure-Konto und ein OMS-Arbeitsbereich** Wenn Sie noch nicht über ein Azure-Konto verfügen, müssen Sie eins erstellen, um OMS-Protokollanalyse verwenden zu können. Informationen dazu, wie Sie ein Azure-Konto erstellen und einen OMS-Arbeitsbereich einrichten, finden Sie unter [Erste Schritte mit einem Protokollanalyse-Arbeitsbereich](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector, Version 2,1 oder höher**

- Protokollanalyse für die Überwachung des Cloud-Connectors ist eine **neue Protokollsuche** erforderlich. Weitere Informationen finden Sie unter [Aktualisieren des Azure Log Analytics-Arbeitsbereichs auf eine neue Protokollsuche](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Konfigurieren des Cloud Connectors für die Verwendung von OMS

Sie müssen die lokale Cloud Connector-Umgebung für die Verwendung von OMS konfigurieren. Dazu benötigen Sie die OMS-Arbeitsbereichs-ID und den Schlüssel, die Sie mithilfe des OMS-Portals wie folgt finden können: Einstellungen –\>verbundene Quellen –\> Windows-Server:

![Screenshot für Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

Wie Sie den Cloud Connector für die Verwendung von OMS konfigurieren, hängt von Ihrem Szenario ab:

- **Wenn Sie eine neue Cloud Connector-Appliance installieren oder eine Appliance erneut bereitstellen möchten**, führen Sie die folgenden Schritte aus, bevor Sie Install-CcAppliance ausführen:

1. Legen Sie im Abschnitt CloudConnector. ini-Datei [common] den OMSEnabled-Parameter auf true fest.

    Jedes Mal, wenn Cloud Connector bereitgestellt oder aktualisiert wird, versucht der OMS-Agent automatisch auf den VMS zu installieren. Aktivieren Sie dieses Feature, damit der OMS-Agent die automatische Aktualisierung des Cloud Connectors überleben kann.

2. Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie "Satz-CcCredential-AccountType OMSWorkspace" aus. 

- **Wenn Sie einen OMS-Agent auf einer vorhandenen Cloud Connector-Appliance installieren**, gehen Sie folgendermaßen vor:

1. Legen Sie im Abschnitt CloudConnector. ini-Datei [common] OMSEnabled = true fest. 

2. Führen Sie Import-CcConfiguration aus. 

3. Führen Sie Install-CcOMSAgent aus. 

    > [!NOTE]
    > Wenn die OMSWorkspace-Anmeldeinformationen noch nie eingerichtet wurden, werden Sie beim Ausführen von install-CcOMSAgent zur Eingabe der Anmeldeinformationen aufgefordert. 

- **Wenn Sie die OMS-Arbeitsbereichs-ID oder den Schlüssel in einer Cloud Connector-Appliance aktualisieren möchten, die bereits einen OMS-Agent installiert hat:**

1. Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie "Satz-CcCredential-AccountType OMSWorkspace" aus. 

2. Führen Sie zum Anwenden der Updates die CcOMSAgent-Installation aus. 

- **Überprüfen Sie in allen Szenarien, ob die Agents wie folgt verbunden sind:**

    Wechseln Sie im OMS-Portal zu Einstellungen –\> verbundene Quellen –\> Windows-Server. Es wird eine Liste der verbundenen Computer angezeigt. 

## <a name="configure-oms"></a>Konfigurieren von OMS

Als nächstes müssen Sie Ihre OMS-Konfiguration mithilfe des OMS-Portals angeben. Insbesondere müssen Sie Folgendes tun:

- Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren an.

- Erstellen von Benachrichtigungen 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Angeben von Informationen zu Ereignisprotokollen und Leistungsindikatoren

Im OMS-Portal müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:

1. Wechseln Sie zu Einstellungen\>-Daten\>-Windows-Ereignisprotokolle, und fügen Sie Ereignisprotokolle für Folgendes hinzu: 

   - Lync Server

   - Anwendung

     > [!NOTE]
     > Sie müssen lync Server manuell in das Textfeld eingeben. Sie wird in der Dropdownliste nicht als Option angezeigt. 

     Weitere Informationen finden Sie unter [Windows-Ereignisprotokoll-Datenquellen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events) .

2. Wechseln Sie zu Einstellungen\>-Daten\> -Windows-Leistungsindikatoren, und fügen Sie Leistungsindikatoren hinzu für: 

   - **Zähler für Betriebssystemebene**. Sie können Zähler auf Betriebssystemebene hinzufügen, beispielsweise Prozessorauslastung, Speicherauslastung, Netzwerkauslastung, oder Sie können vorhandene Lösungen wie Kapazität und Leistung, Netzwerk Leistungs Monitor verwenden, ohne explizit Leistungsindikatoren hinzuzufügen. Unabhängig davon, wie Sie sich entscheiden, diese zu überwachen, empfiehlt Microsoft, diese Betriebssystem Zähler zu überwachen.

   - **Skype for Business-Leistungsindikatoren** Skype for Business stellt zahlreiche Leistungsindikatoren zur Verfügung. Sie können diese Leistungsindikatoren finden, indem Sie sich bei einem beliebigen Vermittlungs Server anmelden und den System Monitor öffnen. Diese Leistungsindikatoren beginnen mit "ls:". Microsoft empfiehlt, dass Sie mindestens mit den folgenden Kapazitäts Zählern beginnen und andere Personen hinzufügen, die von Interesse sind:

     Aktive Anrufe insgesamt:

   - LS: MediationServer-eingehende Anrufe (_Total\- ) aktuell 

   - LS: MediationServer-Outbound Calls (_Total\- ) Current 

     Gesamtzahl der aktiven Medien Umgehungs Anrufe:

   - LS: MediationServer-eingehende Anrufe (_Total\- ) aktive Medien Umgehungs Anrufe 

   - LS: MediationServer-Outbound Calls (_Total\- ) Active Media Bypass-Anrufe 

     > [!NOTE]
     > Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben. Sie werden in der Dropdownliste nicht als Optionen angezeigt. 

     Weitere Informationen finden Sie unter [Windows-und Linux-Leistungsdatenquellen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) .

### <a name="create-alerts"></a>Erstellen von Benachrichtigungen

Es gibt zwei Arten von Benachrichtigungen in OMS: Anzahl der Ergebnisse und Metriken für die Messung. Weitere Informationen zum Erstellen von Benachrichtigungen finden Sie unter [Arbeiten mit Warnungsregeln in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Beim Erstellen von Benachrichtigungen sollten Sie Folgendes berücksichtigen:

- Stellen Sie sicher, dass es sich bei der Benachrichtigung um eine Anzahl von Ergebnissen handelt, bei der es sich um die Standardauswahl handelt. 

- Bei den Demo-Abfragen muss "Anzahl der Ergebnisse" auf "größer als 0" festgesetzt werden. 

- Es wird empfohlen, dass Sie sowohl Zeitfenster als auch Warnungs Häufigkeit auf 5 Minuten einstellen. 

- Es wird empfohlen, dass Sie die Option "Benachrichtigungen unterdrücken" nicht für Demo Benachrichtigungen aktivieren. 

- Für typische Benachrichtigungsszenarien empfiehlt Microsoft, ein Warnungs paar zu erstellen: eine Fehlermeldung und eine Benachrichtigung zum Zurücksetzen. Wählen Sie für die Fehlermeldung Schweregrad kritisch aus. Wählen Sie für die Warnung zurücksetzen die Option Schweregrad Information aus.

In den folgenden Abschnitten wird beschrieben, wie Beispiel Benachrichtigungen erstellt werden.

 **Erstellen eines Warnungs Paars: "RTCMEDSRV wird nicht auf Vermittlungsservern ausgeführt" und "RTCMEDSRV ist wieder in der Ausführung in Vermittlungsservern"**

So erstellen Sie dieses Warnungs paar:

- Die Abfrage für die Fehlermeldung lautet wie folgt:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    Die Abfrage verwendet den Computerfilter *, auf dem Computer "MediationServer" enthält* . Der Filter markiert nur den Computer, dessen Name die Zeichenfolge "MediationServer" enthält.

     Ersetzen Sie den Filter durch ihren eigenen Computerfilter, oder entfernen Sie ihn einfach. Sie können komplexe Zeichenfolgenfilter ohne reguläre Ausdrücke erstellen. Weitere Informationen finden Sie unter [Zeichenfolgenoperatoren](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Sie können auch die Verwendung regulärer Ausdrücke auswählen. Darüber hinaus können Sie eine Computergruppe erstellen, indem Sie eine Suchabfrage speichern und diese Gruppe als ihren Computerfilter in ihrer Warnungs Abfrage verwenden. Weitere Informationen finden Sie unter [Computer Gruppen in Log-Analyse-Protokoll suchen](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Für jeden Computer erhält die Fehler Abfrage das letzte Ereignisprotokoll sowohl für den Start des RTCMEDSRV-Diensts als auch für den Dienst Stopp. Wenn es sich bei dem letzten Ereignis um das Dienst Stoppereignis handelt, gibt es ein Protokoll zurück. Wenn es sich bei dem letzten Ereignis um das Startereignis des Diensts handelt, wird Nothing zurückgegeben. Kurz gesagt: die Abfrage gibt eine Liste der Server zurück, deren RTCMEDSRV im Zeitfenster angehalten wurde. 

- Die Abfrage für die Reset-Benachrichtigung lautet wie folgt:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    Die Zurücksetzungs Abfrage führt genau das Gegenteil der Fehler Abfrage aus. Für jeden Computer wird ein Wert zurückgegeben, wenn es sich bei dem letzten Ereignis um das Dienststart Ereignis handelt. Wenn es sich bei dem letzten Ereignis um das Dienst Stoppereignis handelt, wird Nothing zurückgegeben.

  **Erstellen eines Warnungs Paars: "zu viele gleichzeitige Anrufe in Vermittlungsservern" und "gleichzeitige Anrufe fallen auf normale Last zurück"**

So erstellen Sie diese Benachrichtigung:

- Die Abfrage für die Fehlermeldung lautet wie folgt:

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Die Abfrage ruft für jeden Computer die letzten Leistungsindikatoren für eingehenden und ausgehenden Anruf ab und addiert diese beiden Werte. Wenn der Summenwert 500 überschreitet, wird ein Protokoll zurückgegeben. Wenn dies nicht der Fall ist, wird Nothing zurückgegeben. Kurz gesagt: die Abfrage gibt eine Liste der Server zurück, deren gleichzeitige Anrufe im Zeitfenster zu viele sind.

- Die Abfrage für die Reset-Benachrichtigung lautet wie folgt:

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    Die Zurücksetzungs Abfrage führt genau das Gegenteil der Fehler Abfrage aus. Die Abfrage ruft für jeden Computer die letzten Leistungsindikatoren für eingehenden und ausgehenden Anruf ab und addiert diese beiden Werte. Wenn der Sum-Wert kleiner als 500 ist, wird ein Protokoll zurückgegeben. Andernfalls wird nichts zurückgegeben.

  **Erstellen einer Benachrichtigung: "CPU- \> Auslastung 90 oder RTCMEDIARELAY in den Servern angehalten"**

Um diese Benachrichtigung zu erstellen, lautet die Abfrage wie folgt:

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

Die Abfrage ruft alle Prozessor Nutzungszähler und Dienst Stoppereignisse von allen Computern ab und gibt ein Protokoll zurück, wenn entweder die Prozessorauslastung 90% überschreitet oder der Dienst jemals beendet wird. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analysieren der Warnungen in Ihrem Protokollanalyse-Repository

Verwenden Sie die Warnungs Verwaltungslösung, um die Warnungen in Ihrem Repository zu analysieren. Weitere Informationen finden Sie unter [Warnungs Verwaltungslösung in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .

## <a name="recommended-minimal-monitoring-set"></a>Empfohlener minimaler Überwachungs Satz

So ermitteln Sie Probleme mit Ereignisprotokollen und Leistungsindikatoren: 

- **Ereignisprotokolle** Bei jedem Problem sollte ein Ereignispaar vorhanden sein, bei dem eine Gruppe von Ereignissen angibt, dass etwas falsch ist, während die andere Person angibt, dass alles gut ist. Für einen bestimmten Zeitraum ist es das letzte aufgezeichnete Ereignis, das angibt, ob für diesen Zeitraum ein Fehler aufgetreten ist.

- **Leistungsindikatoren** Für die überwachten Leistungsindikatoren sollte ein Schwellenwert vorhanden sein.

In der folgenden Tabelle sind die Dienste aufgeführt, die Microsoft überwachen empfiehlt, indem Sie die Start-und Stoppereignis-IDs auflisten:

|Dienst Name  <br/> |Ziel Server Rolle  <br/> |Ereignis-ID beenden  <br/> |Ereignis-ID starten  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Vermittlungsserver  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edgeserver  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edgeserver  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edgeserver  <br/> |22003  <br/> |22002  <br/> |

In der folgenden Tabelle sind die Netzwerkprobleme aufgeführt, die von Microsoft überwacht werden sollten:


| Monitor Name  <br/>                                        | Ziel Server Rolle  <br/> | Erfolgsereignis-ID-Ausdruck  <br/> | Fehlerereignis-ID-Ausdruck  <br/> | Beispiel für Fehler  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Verbindungsfehler beim Vermittlungs Server zum Gateway  <br/>    | Vermittlungsserver  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Fehler bei Vermittlungs Server zum Gateway-Anruf Abschluss  <br/> | Vermittlungsserver  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Kritische Netzwerkprobleme  <br/>                           | Edgeserver  <br/>        | 14353                              |                                  | 12288  <br/>           |

Im folgenden sind die Leistungsindikatoren für die Anrufkapazität aufgeführt, die überwacht werden sollen. Diese Zahlen sollten kürzer sein als 500 für Cloud Connector Standard Edition; weniger als 50 für Cloud Connector mindestens Edition.

- LS: MediationServer-eingehende Anrufe (_Total\- ) aktuell 

- LS: MediationServer-Outbound Calls (_Total\- ) Current 

- LS: MediationServer-eingehende Anrufe (_Total\- ) aktive Medien Umgehungs Anrufe

- LS: MediationServer-Outbound Calls (_Total\- ) Active Media Bypass-Anrufe

## <a name="see-also"></a>Siehe auch

Weitere Informationen zum Arbeiten mit OMS finden Sie unter den folgenden Themen:

- [Suchen von Daten mithilfe von Protokoll suchen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics-Sprachreferenz](https://docs.loganalytics.io/docs/Language-Reference)

- [Grundlegendes zu Warnungen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Verbinden von Windows-Computern mit dem Protokollanalyse Dienst in Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


