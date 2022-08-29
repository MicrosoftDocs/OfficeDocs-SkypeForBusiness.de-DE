---
title: Verlaufsbericht für automatische Telefonzentrale und Anrufwarteschleife
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: Erfahren Sie, wie Sie den Power BI-Bericht „Anrufqualitäts-Dashboard“ verwenden, um Verlaufsdaten der automatischen Telefonzentrale und der Anrufwarteschleife anzuzeigen.
ms.openlocfilehash: ec345a66a06b03bb9926ff74ceac7b85b31a0190
ms.sourcegitcommit: 850038f2248c1ea412f7b5daca26c0598baffa3c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2022
ms.locfileid: "67443342"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Verlaufsbericht für automatische Telefonzentrale und Anrufwarteschleife

Die Power BI-Vorlage "Teams Auto Attendant & Anrufwarteschleifenverlaufsbericht" enthält die folgenden drei Berichte:

- [Automatische Telefonzentrale:](media/cqd-teams-aa-cq-historical-report-sample-aa.png) Zeigt Analysen für Anrufe an, die in Ihren automatischen Telefonzentralen eingehen.
- [Anrufwarteschleife:](media/cqd-teams-aa-cq-historical-report-sample-cq.png) Zeigt Analysen für Anrufe an, die in Ihren Anrufwarteschleifen eingehen.
- [Agent-Zeitachse:](media/cqd-teams-aa-cq-historical-report-sample-at.png) Zeigt eine Zeitachsenansicht der Agents an, die bei Anrufen in der Anrufwarteschleife aktiv sind.

Diese Berichte verwenden Daten aus dem [AQD](CQD-Power-BI-query-templates.md)-Datenspeicher. Die Berichte ermöglichen Es Organisationen, über die Anzahl der Anrufe zu berichten, die von automatischen Telefonzentralen und Anrufwarteschleifen verarbeitet werden.  Die Berichte bieten auch Einblicke in die Agentleistung in den Anrufwarteschleifen.

### <a name="v163-published-on-august-24-2022"></a>V1.63 veröffentlicht am 24. August 2022

## <a name="prerequisites"></a>Voraussetzungen

### <a name="power-bi-desktop"></a>Power BI Desktop
Sie müssen Power BI Desktop installiert haben. Sie können es aus dem [Microsoft Windows Store](https://aka.ms/pbidesktopstore)installieren.

Sie können die kostenlose Version von Power BI Desktop verwenden. Die mindestens kompatible Version ist 2.85.681.0 (September 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Berechtigungen für den Zugriff auf die AQD-Pipeline

Das Konto, das Sie zum Anzeigen des Verlaufsberichts verwenden, muss über Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügen. Weitere Informationen finden Sie unter [CQD-Zugriffsrolle](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Installation 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie Power BI Desktop bereits auf Ihrem Computer installiert haben und dass Ihr Konto über die erforderlichen Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügt.

Führen Sie die folgenden Schritte durch:

- Laden Sie die [AQD Power BI-Abfragevorlagen](https://www.microsoft.com/download/details.aspx?id=102291) herunter, und speichern Sie die ZIP-Datei in einem Verzeichnis auf Ihrem Computer.

- Doppelklicken Sie auf die ZIP-Datei, um sie zu öffnen.

- Doppelklicken Sie auf die Vorlagendatei "CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit". Die Power BI Desktop sollte gestartet werden.

- Sie werden aufgefordert, den CQD-Datenpipelinebereich auszuwählen. Wählen Sie die Region aus, in der sich Ihr Mandant befindet.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot der Auswahl des CQD-Datenpipelinebereichs.":::

- Die Region, in der sich Ihr Mandant befindet, kann mithilfe des Cmdlets [Get-CsTenant](/powershell/module/skype/get-cstenant) abgerufen werden.

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - Der Bereich wird nach dem **/** wie im obigen Beispiel angezeigt, in dem die Region folgendermaßen lautet: noam

 - Der Bericht wird mit Beispieldaten gestartet.
 
 - Um Ihre eigenen Daten anzuzeigen, wählen Sie **Aktualisieren** auf der Registerkarte "Start" unter "Abfragen" in Power BI Desktop aus.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot, in dem die Aktualisierungsoption ausgewählt wird.":::

- Sie werden aufgefordert, sich anzumelden. Wählen Sie **"Organisationskonto** " und dann **"Anmelden"** aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot der Anmeldung.":::

- Wählen Sie **Verbinden** aus, und beobachten Sie die Datenaktualisierung.

## <a name="data-latency-and-aa--cq-analytics"></a>Datenlatenz und AA- und CQ-Analysen

Daten sind in der Regel innerhalb von 30 Minuten nach Abschluss des Anrufs verfügbar. Es gibt jedoch Situationen, in denen es mehrere Stunden dauern kann, bis Daten angezeigt werden. 

Sie müssen die Daten aktualisieren, um neue Daten anzuzeigen.

## <a name="customization"></a>Anpassung 

Sie können bestimmte Visualisierungsaspekte der Berichte anpassen, z. B. das Hinzufügen oder Entfernen von Feldern, die in den verschiedenen Visualisierungen angezeigt werden sollen, das Ändern des Diagrammtyps usw.

Der Bericht enthält alle derzeit verfügbaren Datenmetriken.

### <a name="change-color-schema"></a>Farbschema ändern 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Installationsschritte bereits abgeschlossen haben.

Führen Sie die folgenden Schritte durch:
- Wählen Sie im Menüband **Registerkarte anzeigen** aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot, in dem die Registerkarte &quot;Ansicht&quot; ausgewählt wird, um das Farbschema zu ändern.":::

- Wählen Sie in der Dropdownliste das Farbschema aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot mit verschiedenen Farbschemas.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definitionen der Verlaufsberichte für automatische Telefonzentrale und Anrufwarteschleife

### <a name="cloud-auto-attendant-analytics"></a>Analysen der automatischen Cloud-Telefonzentrale

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                          |Beschreibung                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Eingehende Anrufquelle<sup>1</sup>        |Verteilung von Anrufen nach interner/externer Anrufquelle            |
|Verzeichnissuchmethode                 |Verteilung von Anrufen nach Suchtyp                              |
|Anzahl der Anruferaktionen                     |Verteilung von Anrufen nach Nummernaktion, die während des Anrufs verwendet wird       |
|Durchschnittliche Sekunden in AA                   |Durchschnittliche Anzahl von Sekunden, die Anrufer im AA verbringen                 |
|Durchschnittliche Anruferaktionen                  |Durchschnittliche Anzahl von Aktionen, die Aufrufer in der AA ausführen               |
|Anrufergebnisse                            |Verteilung von Anrufen nach Endzustand des Anrufs                         |
|Unterer Abschnitt des Berichts                 |Aufschlüsselung des Anrufflusses                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht an AQD-Tabelle und Feldzuordnung

|Registerkarte "Bericht"            |Berichtstabellenname     |Quelltabellenname            |Globalfilter                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Automatische Telefonzentrale        |fAutoAttendant        |AutoAttendant                |Keine                                   |

|Berichtsabschnitt                                  |Feld(er) verwendet                              |Filter angewendet     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Datumsauswahl                                   |AAStartTime                                |Keine                |
|Zeitbereichsauswahl                             |AAStartHour                                |Keine                |
|Automatische Telefonzentrale                                  |AA-Name                                    |Keine                |
|Eingehende Anrufquelle<sup>1</sup>                |Anruftyp<br>Summe von TotalCallCount (Measure) |Externe Anrufe: Anruftyp ist extern<br>Interne Anrufe: Anruftyp ist intern |
|Verzeichnissuchmethode                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod ist abs_search_dtmf oder abs_search_name    |
|Anzahl der Anruferaktionen                             |AACallerActionCount<br>TotalCallCount      |Keine                                                             |
|Durchschnittliche Sekunden in AA                           |AAChainDuration (Measure)                  |Keine                                                             |
|Durchschnittliche Anruferaktionen                          |AACallerActionCount (Measure)              |Keine                                                             |
|Anrufergebnisse                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |Keine                                       |
|Unterer Abschnitt des Berichts                         |AA-Name<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Anruftyp<br>MM-DD<br>TotalCallCount |Keine       |

#### <a name="fautoattendant-cqd-fields-description"></a>Beschreibung der fAutoAttendant AQD-Felder

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA-Name                                 |Text                     |Name des Ressourcenkontos, das an die automatische Telefonzentrale angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **aa_test@microsoft.com** ist, lautet dieser Wert wie folgt: **aa_test** |
|AACallerActionCount                     |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Aktionen, die während des Anrufs vom Anrufer in der automatischen Telefonzentrale ausgewählt wurden  |
|AACallerActionCount (Measure)          |Ganze Zahl             |Identisch mit der obigen Ausnahme ist 0, wenn keine Anrufe statt leer sind                              |
|AACallFlow                              |Text                     |Kapselt die verschiedenen Zustände der Anrufwerte der automatischen Telefonzentrale – mögliche Werte:<br><br>§ abs_search<br>§ announcement<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Text                     |Endergebnis des Aufrufs – mögliche Werte:<br><br>§ failed_to_establish_media (der Medienteil des Anrufs konnte nicht festgestellt werden)<br>§ failover_to_operator (Anruf, der in der Regel aufgrund eines Systemfehlers an den Betreiber weitergeleitet wird)<br>§ oaa_chain_too_long (zu viele Beine im AA)<br>§ oaa_session_too_long (AA-Sitzung dauert zu lange)<br>§ service_declined (AA hat den Anruf nicht angenommen)<br>§ service_terminated (Die AA-Konfiguration trennt den Anruf oder anrufaufgehängt)<br>§ terminated_automatic_selection (Die AA-Konfiguration trennt die Anrufe)<br>§ terminated_no_operator (Aufruf aufgrund des Fehlers beendet, kein Operator definiert) <br>§ terminated_transfer_failed (Anruf als Übertragungsfehler beendet - in der Regel an externe Rufnummer)<br>§ transfer_in_progress (AA->AA-Übertragung)<br>§ transferred_to_operator (Anruf wurde an den Betreiber weitergeleitet - in der Regel aufgrund eines Benutzerfehlers)<br>§ transferred_to_receptionist (identisch mit transferred_to_operator)<br>§ transferred_to_self (Anruf wurde an den Anfang der AA zurückgegeben - in der Regel über eine Menüankündigungsoption)<br>§ transferred_to_shared_voicemail (Anruf wurde an freigegebene Voicemail weitergeleitet)<br>§ transferred_to_user (Anruf wurde an einen Benutzer weitergeleitet - umfasst Anrufwarteschleifen)<br>§ unbekannt (unbekannter Zustand)<br>§ user_terminated (Anrufer aufgehängt) |
|AA-Anruflegende                          |Text                     |Einrichten von Legendenelementen basierend auf AACallResult                               |
|AAChainDuration                         |Dezimalzahl           |Zusammenfassen: Summe<br>Dauer des Anrufs in der automatischen Telefonzentrale                     |
|AAChainDuration (Measure)               |Dezimalzahl           |Identisch mit der obigen Ausnahme ist 0, wenn keine Anrufe statt leer sind              |
|AAChainIndex                            |Text                     |                                                                         |
|AAConnectivityType                      |Text                     |Typ der Aufrufe – mögliche Werte:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Text                     |Anzahl der am Anruf beteiligten automatischen Telefonzentralen                               |
|AADirectorySearchMethod                 |Text                     |Letzte Adressbuch-Suchmethode – mögliche Werte:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Dezimalzahl           |Startstunde der automatischen Telefonzentrale                                           |
|AAStartTime                             |Datum/Uhrzeit                |Startzeit des Anrufs der automatischen Telefonzentrale                                           |
|AATransferAction                        |Text                     |Anrufweiterleitungszieltyp – mögliche Werte:<br><br>§ Anwendung - VoIP-Anwendungsentität<br>§ external_pstn<br>§ hunt_group - Anrufwarteschleifenentität<br>§ orgaa - Entität "Automatische Telefonzentrale"<br>§ shared_voicemail<br>§ unknown<br>§ user |
|Anruftyp<sup>1</sup>                   |Text                     |Typ der Aufrufe – mögliche Werte:<br><br>§ External<br>§ Internal           |
|IsAAInvolved                            |Text                     |Immer 1                                                                 |
|MM-DD                                   |Text                     |Anruf der automatischen Telefonzentrale am Monatstag                                            |
|PSTNMinutes                             |Ganze Zahl             |Zusammenfassen: Summe<br>Minutennutzung gesamt                                     |
|TotalCallCount                          |Ganze Zahl             |Zusammenfassen: Summe<br>Immer 1 – wird verwendet, um die Summe aller Anrufe bereitzustellen            |
|Summe von TotalCallCount (Measure)         |Ganze Zahl             |Identisch mit der obigen Ausnahme ist 0, wenn keine Anrufe statt leer sind              |


### <a name="cloud-call-queue-analytics"></a>Cloudanrufwarteschleife-Analysen

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                          |Beschreibung                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Eingehende Anrufquelle<sup>1</sup>        |Verteilung von Anrufen nach interner/externer Anrufquelle             |
|Durchschnittliche Wartezeit (Sekunden)             |Wartezeit für beantwortete und abgebrochene Anrufe                          |
|Anruflautstärke und Anzahl der Agent-Opt-Ins      |Verteilung von Anrufen nach Anrufwarteschleifen/ Maximale Anzahl von Agent-Opt-Ins  |
|Anrufergebnisse                            |Verteilung von Anrufen nach Anrufergebnis                               |
|Abgebrochene Anrufe                         |Verteilung abgebrochener Anrufe durch Anrufwarteschleifen                     |
|Durchschnittliche Sitzungslänge (Sekunden)        |Anruflänge in Sekunden gruppiert nach Anrufergebnis                      |
|Ziele für Anrufüberlauf/Timeout      |Verteilung der Anrufe, bei denen ein Timeout aufgetreten ist oder übergelaufen ist                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht an AQD-Tabelle und Feldzuordnung

|Registerkarte "Bericht"            |Berichtstabellenname                                   |Quelltabellenname                               |Globalfilter       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|Anrufwarteschleife            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |Keine                |

|Berichtsabschnitt                      |Tabelle -> Feld(er) verwendet                |Filter angewendet       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Datumsauswahl                       |fCallQueueAnalytics -> Datum           |Keine                  |
|Zeitbereichsauswahl                 |fCallQueueAnalytics -> CQHour         |Keine                  |
|Ressourcenkonto der Anrufwarteschleife         |fCallQueueAnalytics -> CQ-Name        |Keine                  |
|Eingehende Anrufquelle<sup>1</sup>    |fCallQueueAnalytics -> Summe der Anrufanzahl (Measure)<br>fCallQueueAnalytics -> Anruftyp    |Externe Anrufe: Anruftyp ist extern<br>Interne Anrufe: Anruftyp ist intern |
|Durchschn. Wartezeit (Sekunden) – Vor der Antwort |fCallQueueFinalStateAction -> Durchschnittliche CQ-Dauer (Measure) |Das Anrufergebnis der Anrufwarteschleife ist agent_joined_conference oder transferred_to_agent|
|Durchschn. Wartezeit (Sekunden) – Vor dem Abbruch |fCallQueueFinalStateAction -> Durchschnittliche Anrufdauer (Measure) |Das Anrufergebnis der Anrufwarteschleife ist nicht agent_joined_conference, transferred_to_agent, überlaufen, timed_out |
|Anruflautstärke und Agent-Opt-In Anzahl   |fCallQueueAnalytics -> Anrufanzahl<br>fCallQueueAnalytics -> Anrufwarteschleifen-Agent–Opt-In-Anzahl<br>fCallQueueAnalytics -> CQ-Name<br>fCallQueueAnalytics -> Datum |Keine |
|Abgebrochene Anrufe                     |fCallQueueAnalytics -> Datum<br>fCallQueueAnalytics -> TotalCallCount | Anrufwarteschleifen-Anrufergebnislegende wird abgebrochen |
|Durchschnittliche Sitzungslänge (Sekunden)    |fCallQueueFinalStateAction -> Durchschnittliche Anrufwarteschleifendauer (Sek.)<br>Anrufwarteschleifen-Anrufergebnislegende |Durchschnittliche Anrufwarteschleifendauer (Sek.) > 0 |
|Ziele für Anrufüberlauf/Timeout  |fCallQueueAnalytics -> Anrufanzahl<br>fCallQueueAnalytics -> Zieltyp der Anrufwarteschleife<br>fCallQueue-Zieltyplegende |Die Zieltyplegende der Anrufwarteschleife enthält nicht "Abgebrochen" und "Agent beantwortet" |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Beschreibung der fCallQueueAnalytics AQD-Felder

|Name                                    |Datentyp                |Beschreibung                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Anrufanzahl                              |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Anrufe                                          |
|Anzahl der Anrufwarteschleifen-Agenten                  |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der in der Anrufwarteschleife konfigurierten Agents            |
|Anzahl der Anrufwarteschleifen-Agent-Opt-Ins           |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Agents, die sich für die Anrufwarteschleife angemeldet haben              |
|Anrufergebnis der Anrufwarteschleife                  |Text                     |Endzustand des Anrufs der Anrufwarteschleife – mögliche Werte:<br><br>§ agent_joined_conference (angenommene Telefonkonferenzen)<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown (Überlaufbedingung erfüllt)<br>§ timed_out (Timeoutbedingung erfüllt)<br>§ transferred_to_agent (beantwortete Übertragungsmodusaufrufe {default}) |
|Anrufwarteschleifen-Anrufergebnislegende           |Text                     |Einrichten von Legendenelementen basierend auf dem Ergebnis der Anrufwarteschleife                             |
|Zieltyp der Anrufwarteschleife                  |Text                     |***Anrufumleitungszieltyp – mögliche Werte:***<br><br>§ ApplicationEndpoint<br>§ Mailbox<br>§ Other<br>§ User |
|Zieltyplegende der Anrufwarteschleife           |Text                     |Einrichten von Legendenelementen basierend auf dem Zieltyp der Anrufwarteschleife                        |
|Anruftyp<sup>1</sup>                   |Text                     |Typ der Aufrufe – mögliche Werte:<br><br>§ External<br>§ Internal             |
|CQ-Name                                 |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|CQ Hour                                 |Ganze Zahl             |Startstunde für Anrufwarteschleifen                                                 |
|Datum                                    |Datum/Uhrzeit                |Startdatum und -uhrzeit des Anrufs in der Anrufwarteschleife (Stunde)                                 | 
|DateTimeCQName                          |Text                     |Eindeutiger Schlüssel zum Filtern nach fCallQueueFinalStateAction                     |
|PSTN-Konnektivitätstyp                  |Text                     |Typ der Aufrufe – mögliche Werte:<br><br>§ ExternalCall<br>§ InternalCall     |
|PSTN-Minuten gesamt                      |Ganze Zahl             |Zusammenfassen: Summe<br>Nutzung in Minuten für PSTN-Anrufe gesamt                       |
|Summe der Anrufanzahl (Measure)             |Ganze Zahl             |Identisch mit der Anrufanzahl ist jedoch 0, wenn kein Anruf erfolgt                          |
|TotalCallCount (Measure)                |Ganze Zahl             |Zusammenfassen: Summe<br>Anrufanzahl                                                |


#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Beschreibung der fCallQueueFinalStateAction AQD-Felder

|Name                                    |Datentyp                |Beschreibung                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durchschnittliche Anrufdauer (Sekunden)         |Dezimalzahl           |Zusammenfassen: Summe<br>Durchschnittliche Anrufdauer in Sekunden für abgebrochene Anrufe    |
|Durchschnittliche Anrufwarteschleifendauer (Sek.)       |Dezimalzahl           |Zusammenfassen: Summe<br>Durchschnittliche Wartezeit in Sekunden für beantwortete Anrufe           |
|Durchschn. durchschnittliche Anrufdauer (Measure)  |Ganze Zahl             |Identisch mit der durchschnittlichen Anrufdauer (Sekunden) ist jedoch 0, wenn keine Anrufe   |
|Durchschn. durchschnittliche CQ-Dauer (Measure)    |Ganze Zahl             |Identisch mit der durchschnittlichen Anrufwarteschleifendauer (Sek.) ist jedoch 0, wenn keine Anrufe |
|Anrufanzahl                              |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Anrufe                                         |
|Anrufergebnis der Anrufwarteschleife                  |Text                     |Endzustand des Anrufs der Anrufwarteschleife – mögliche Werte:<br><br>§ agent_joined_conference (angenommene Telefonkonferenzen)<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown (Überlaufbedingung erfüllt)<br>§ timed_out (Timeoutbedingung erfüllt)<br>§ transferred_to_agent (beantwortete Übertragungsmodus ruft {default} auf. |
|Anrufwarteschleifen-Anrufergebnislegende           |Text                     |Einrichten von Legendenelementen basierend auf dem Anrufergebnis der Anrufwarteschleife                      |
|Aktion "Endzustand der Anrufwarteschleife"           |Text                     |Letzte Aktion der Anrufwarteschleife – mögliche Werte:<br><br>§ disconnect (timed_out Aufrufe)<br>§ disconnect_with_busy (Überlaufaufrufe)<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ other<br>§ voicemail                |
|CQ-Name                                 |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|Datum                                    |Datum/Uhrzeit                |Startdatum und -uhrzeit des Anrufs in der Anrufwarteschleife (Stunde)                                 |
|DateTimeCQName                          |Text                     |Eindeutiger Schlüssel zum Filtern nach fCallQueueFinalStateAction                     |
|IsAbandoned                             |Wahr/falsch               |TRUE, wenn der Anruf nicht von einem Agent beantwortet wird                                   |


### <a name="cloud-call-queue-agent-timeline"></a>Zeitachse des Cloudanrufwarteschleifen-Agents

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                                          |Beschreibung                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Anzahl der Anrufe nach Agent                                |Verteilung von Anrufen nach Anrufwarteschleife und Agent                |
|Verteilung nach Agent und Warteschlange                     |Verteilung von Anrufen nach Agent und Anrufwarteschleife                |
|Tabelle (unten rechts)                                    |Verteilung von Anrufen nach Agent mit durchschnittlichem Und Gesamtanrufdauer |
|Durchschnittliche Anrufdauer (Sekunden) nach Agent                |Durchschnittliche Dauer (Sekunden) des Anrufs nach Agent                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht an AQD-Tabelle und Feldzuordnung

|Registerkarte "Bericht"            |Berichtstabellenname           |Quelltabellenname         |Globalfilter       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Zeitachse des Agents        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |Keine                |


|Berichtsabschnitt                                |Feld(er) verwendet                         |Filter angewendet       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Datumsauswahl                                 |Datetime                              |Keine                  |
|Agent-Benutzernamenauswahl                       |Name des Agents                            |Keine                  |
|Ressourcenkontenauswahl der Anrufwarteschleife          |CQ-Name                               |Keine                  |
|Anzahl der Anrufe nach Agent                      |Name des Agents<br>Anrufanzahl<br>Hour      |Keine                  |
|Verteilung nach Agent und Anrufwarteschleife          |Name des Agents<br>Durchschnittliche Anrufdauer (Sekunden)<br>Anrufanzahl<br>CQ-Name |Keine                      |
|Unten links                                   |Name des Agents<br>Durchschnittliche Anrufdauer (Sekunden)<br>Anrufanzahl<br>Anrufdauer (Minute)<br>CQ-Name<br>Hour<br>MM-DD | Keine |
|Durchschnittliche Anrufdauer (Sekunden) nach Agent      |Name des Agents<br>Durchschnittliche Anrufdauer (Sekunden) | Keine |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Beschreibung der fAgentTimelineAnalytics AQD-Felder

|Name                                    |Datentyp                |Beschreibung                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Name des Agents                              |Text                     |Benutzer-UPN<br>Wenn der vollständige Benutzername **user@microsoft.com** ist, lautet dieser Wert: **Benutzer** |
|Durchschnittliche Anrufdauer (Sekunden)         |Dezimalzahl           |Zusammenfassen: Summe<br>Die durchschnittliche Dauer von Anrufwarteschleifenanrufen in Sekunden |
|Anrufanzahl                              |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der vom Agent angenommenen Anrufe     |
|Anrufdauer (Minuten)                 |Ganze Zahl             |Zusammenfassen: Summe<br>Gesamtanrufdauer der angenommenen Anrufwarteschleifenanrufe in Minuten (abgerundet auf die nächste Minute)  |
|CQ-Name                                 |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|Datum                                    |Datum                     |Datum des Anrufs                                             |
|Datetime                                |Datetime                 |Datum des Anrufs                                             |
|Hour                                    |Ganze Zahl             |Anrufstunde                                             |
|MM-DD                                   |Text                     |Monat und Anruftag                                    |


> [!NOTE]
> Wenn ein Anruf in der ersten Anrufwarteschleife eingeht, wenn die Anzahl der Anrufe, die bereits in dieser Warteschleife warten, den Grenzwert für die **Anrufüberlaufbehandlung** erreicht hat und wenn die Umleitungsoption neue Anrufe an eine zweite Anrufwarteschleife sendet, werden die Agents in der zweiten Anrufwarteschleife als in der ersten Anrufwarteschleife in diesem Bericht angezeigt. 

## <a name="known-issues"></a>Bekannte Probleme

- Anrufwarteschleifen und automatische Telefonzentralen werden anhand der ID des Ressourcenkontos anstelle der Namen der Anrufwarteschleife/automatischen Telefonzentralen angezeigt.  Um den gesamten Datenverkehr für eine automatische Telefonzentrale oder Anrufwarteschleife anzuzeigen, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefonzentrale oder Anrufwarteschleife zugewiesen sind.

- Im Dashboard sind nur 28 Tage des Verlaufs verfügbar, da Anrufwarteschleifen-/automatische Telefonzentralendaten als personenbezogene Daten betrachtet werden und den Aufbewahrungsrichtlinien für den Datenschutz unterliegen.

- In einigen Szenarien kann sich die Anzahl der Anrufe, die der Agent angenommen hat, im Cloud Call Queue Agent-Zeitachsenbericht von der Anzahl der Anrufe unterscheiden, die im Teams-Clientanrufverlauf angezeigt werden. Der Anrufverlauf des Teams-Clients ist korrekt. Der Support wird derzeit untersucht, aber zurzeit ist keine geschätzte Zeit für die Reparatur verfügbar.

- <sup>1</sup> **Eingehende Anrufquelle** in den Diagrammen für die automatische Telefonzentrale und die Anrufwarteschleife zeigen die letzte Anrufabschnittsquelle anstelle der ersten Anrufabschnittsquelle an. Wenn beispielsweise eine automatische Telefonzentrale einen externen Anruf empfängt und den Anruf an eine andere automatische Telefonzentrale oder Anrufwarteschleife überträgt, wird die **eingehende Anrufquelle** als intern gemeldet.

## <a name="version-history"></a>Versionsverlauf
|Version  |Veröffentlichungsdatum     |Dateiname                                                           |Beschreibung                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.63     |24. August 2022    |CQD Teams Auto Attendant & Call Queue Historical Report V1.63.pbit |Siehe:<br>Automatische CQD Teams-Telefonzentrale & Verlaufsberichte der Anrufwarteschleife – Ändern Log.docx in der heruntergeladenen ZIP-Datei für eine Liste der Änderungen                                                                             |
|1.60     |22. Juli 2022      |CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit |Siehe:<br>Automatische CQD Teams-Telefonzentrale & Verlaufsberichte der Anrufwarteschleife – Ändern Log.docx in der heruntergeladenen ZIP-Datei für eine Liste der Änderungen                                                                             |
|1.00     |5. November 2020   |CQ und AA kombinierte Analytics 20201105.pbit                         |Erstveröffentlichung                                     |



