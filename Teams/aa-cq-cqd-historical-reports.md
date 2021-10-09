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
ms.openlocfilehash: 4594a673225a167e762bcfee63067f70e7fe10b4
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249557"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Verlaufsbericht für automatische Telefonzentrale und Anrufwarteschleife

Die Power BI-Vorlage „Verlaufsbericht für AQD-Teams, automatische Telefonzentrale und Anrufwarteschleife“ enthält die folgenden drei Berichte:

- [Automatische Telefonzentrale:](media/cqd-teams-aa-cq-historical-report-sample-aa.png) Zeigt Analysen für Anrufe an, die in Ihren automatischen Telefonzentralen eingehen.
- [Anrufwarteschleife:](media/cqd-teams-aa-cq-historical-report-sample-cq.png) Zeigt Analysen für Anrufe an, die in Ihren Anrufwarteschleifen eingehen.
- [Agent-Zeitachse:](media/cqd-teams-aa-cq-historical-report-sample-at.png) Zeigt eine Zeitachsenansicht der Agents an, die bei Anrufen in der Anrufwarteschleife aktiv sind.

Diese Berichte verwenden Daten aus dem [AQD](CQD-Power-BI-query-templates.md)-Datenspeicher. Sie ermöglichen es Organisationen, die Anzahl der Anrufe zu melden, die von automatischen Telefonzentralen und Anrufwarteschleifen verarbeitet werden.  Sie bieten auch Einblicke in die Agentleistung in den Anrufwarteschleifen.

## <a name="prerequisites"></a>Voraussetzungen

### <a name="power-bi-desktop"></a>Power BI Desktop
Sie müssen Power BI Desktop installiert haben. Sie können es aus dem [Microsoft Windows Store](https://aka.ms/pbidesktopstore)installieren.

Sie können die kostenlose Version von Power BI Desktop verwenden. Die mindestens kompatible Version ist 2.85.681.0 (September 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Berechtigungen für den Zugriff auf die AQD-Pipeline

Das Konto, das Sie zum Anzeigen des Verlaufsberichts "AA- und CQ-Analysen" verwenden, muss über Berechtigungen für den Zugriff auf die AQD-Datenpipeline verfügen. Weitere Informationen finden Sie unter [AQD-Zugriffsrolle](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Installation 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie Power BI Desktop bereits auf dem Computer installiert haben und dass Ihr Konto über die erforderlichen Berechtigungen für den Zugriff auf die AQD-Datenpipeline verfügt.

Führen Sie die folgenden Schritte durch:

- Laden Sie die [AQD Power BI-Abfragevorlagen](https://www.microsoft.com/download/details.aspx?id=102291) herunter, und speichern Sie die ZIP-Datei in einem Verzeichnis auf Ihrem Computer.

- Doppelklicken Sie auf die ZIP-Datei, um sie zu öffnen.

- Doppelklicken Sie auf die Vorlagendatei "Kombinierte CQ- und AA-Analysen 20201105.pbit", und Power BI Desktop sollte starten.

- Sie werden aufgefordert, die AQD-Datenpipelineregion auszuwählen. Wählen Sie die Region aus, in der sich Ihr Mandant befindet.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot der Auswahl des Datenpipelinebereichs für AQD":::

- Die Region, in der sich Ihr Mandant befindet, kann mithilfe des Cmdlets [Get-CsTenant](/powershell/module/skype/get-cstenant) abgerufen werden.

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - Die Region wird nach dem **/** angezeigt, wie im obigen Beispiel, in dem sich die Region befindet: noam

 - Der Bericht wird mit Beispieldaten gestartet.
 
 - Um Ihre eigenen Daten anzuzeigen, wählen Sie **Aktualisieren** auf der Registerkarte "Start" unter "Abfragen" in Power BI Desktop aus.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot, in dem die Aktualisierungsoption ausgewählt wird":::

- Anschließend werden Sie aufgefordert, sich anzumelden. Wählen Sie **Organisationskonto** und dann **Anmelden** aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot mit Der Anmeldung.":::

- Wählen Sie **Verbinden** aus, und beobachten Sie die Datenaktualisierung.

## <a name="data-latency-and-aa--cq-analytics"></a>Datenlatenz und AA- und CQ-Analysen

Daten sind innerhalb von 30 Minuten in der AQD-Datenpipeline verfügbar.

Sie müssen die Daten aktualisieren, um die neuen Analysedaten anzuzeigen. 

## <a name="customization"></a>Anpassung 

Sie können bestimmte Visualisierungsaspekte der Berichte anpassen, z. B. das Hinzufügen oder Entfernen von Feldern, die in den verschiedenen Visualisierungen angezeigt werden sollen, das Ändern des Diagrammtyps usw.

Sie können dem Bericht keine zusätzlichen Datenfelder hinzufügen.

### <a name="change-color-schema"></a>Farbschema ändern 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Installationsschritte bereits abgeschlossen haben.

Führen Sie die folgenden Schritte durch:
- Wählen Sie im Menüband **Registerkarte anzeigen** aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot: Auswählen der Registerkarte "Ansicht" zum Ändern des Farbschemas":::

- Wählen Sie in der Dropdownliste das Farbschema aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot mit verschiedenen Farbschemas":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definitionen der Verlaufsberichte für automatische Telefonzentrale und Anrufwarteschleife

### <a name="cloud-auto-attendant-analytics"></a>Analysen der automatischen Cloud-Telefonzentrale

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                          |Beschreibung                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Eingehende Anrufquelle<sup>1</sup>        |Verteilung von Anrufen nach interner/externer Anrufquelle             |
|Verzeichnissuchmethoden gesamt          |Verteilung von Anrufen nach Suchtyp                               |
|Anruferaktion                           |Verteilung von Anrufen nach Anrufempfänger                             |
|Anrufergebnis                             |Verteilung von Anrufen nach Endzustand des Anrufs                          |
|Anruferaktionsanzahl                     |Verteilung von Anrufen nach Nummernaktion, die während des Anrufs verwendet wird        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht an AQD-Tabelle und Feldzuordnung

|Registerkarte "Bericht"            |Berichtstabellenname     |Globalfilter                          |
|:---------------------|:---------------------|:--------------------------------------|
|Automatische Telefonzentrale        |fAutoAttendant        |AAStartTime liegt innerhalb der letzten 28 Tage |


|Berichtstabellenname            |Quelltabellenname            |Verarbeitung       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Quelle = AutoAttendant, <br>#"Gefilterte Zeilen" = Table.SelectRows(Quelle, jeweils TRUE), <br>#"Automatische Telefonzentrale" = Table.AddColumn(#"Gefilterte Zeilen", "AA-Name", jeweils List.First(Text.Split([AAIdentity], "@"))), <br>#"Geänderter Typ" = Table.TransformColumnTypes(#"Automatische Telefonzentrale",{{"AAStartTime", typ datetime}}), <br>#"Entfernte Spalten" = Table.RemoveColumns(#"Geänderter Typ",{"AAIdentity"}) |


|Berichtsabschnitt                                  |Feld(er) verwendet                              |Filter angewendet     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Datumsauswahl                                   |AAStartTime                                |Keine                |
|Automatische Telefonzentrale                                  |AA-Name                                    |Keine                |
|Eingehende Anrufquelle<sup>1</sup>                |Anruftyp<br>TotalCallCount                |Externe Anrufe: Anruftyp ist extern<br>Interne Anrufe: Anruftyp ist intern |
|Verzeichnissuchmethoden gesamt                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod ist abs_search_dtmf oder abs_search_name    |
|Anruferaktionen                                  |AATransferAction<br>TotalCallCount         |Keine                                                             |
|Durchschnittliche Sekunden in AA<br>Durchschnittliche Anruferaktionen |AAChainDuration<br>AACallerActionCount     |Keine                                                             |
|Anrufergebnisse                                    |AACallResult<br>TotalCallCount             |Keine                                                             |
|Anruferaktionsanzahl                            |AACallerActionCount<br>TotalCallCount      |Keine                                                             |
|Unterer Abschnitt des Berichts                         |AA-Name<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Anruftyp<br>TotalCallCount |Keine                |

#### <a name="fautoattendant-cqd-fields-description"></a>Beschreibung der fAutoAttendant AQD-Felder

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA-Name                                 |Text                     |Name des Ressourcenkontos, das an die automatische Telefonzentrale angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **aa_test@microsoft.com** ist, lautet dieser Wert wie folgt: **aa_test** |
|AACallerActionCount                     |ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Aktionen, die während des Anrufs vom Anrufer in der automatischen Telefonzentrale ausgewählt wurden  |
|AACallFlow                              |Text                     |Kapselt die verschiedenen Zustände des Anrufs der automatischen Telefonzentrale – mögliche Werte:<br><br>§ abs_search<br>§ announcement<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Text                     |Endergebnis des Anrufs – mögliche Werte:<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ unknown<br>§ user_terminated |
|AAChainDuration                         |Dezimalzahl           |Zusammenfassen: Summe<br>Dauer des Anrufs in der automatischen Telefonzentrale                     |
|AAChainIndex                            |Text                     |                                                                         |
|AAConnectivityType                      |Text                     |Anruftyp – mögliche Werte:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Text                     |Anzahl der am Anruf beteiligten automatischen Telefonzentralen                               |
|AADirectorySearchMethod                 |Text                     |Letzte Adressbuchsuchmethode – mögliche Werte:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |Datum/Uhrzeit                |Startzeit des Anrufs der automatischen Telefonzentrale                                           |
|AATransferAction                        |Text                     |Zieltyp für Anrufübertragung – mögliche Werte:<br><br>***§ application – Sprachanwendungsentität**_<br>§ external_pstn<br>_*_§ hunt_group – Entität "Anrufwarteschleife"_*_<br>_*_§ orgaa – Entität "Automatische Telefonzentrale der Organisation"_**<br>§ shared_voicemail<br>§ unknown<br>§ user |
|Anruftyp<sup>1</sup>                   |Text                     |Anruftyp – mögliche Werte:<br><br>§ External<br>§ Internal         |
|IsAAInvolved                            |Text                     |Immer 1                                                                 |
|PSTNMinutes                             |ganze Zahl             |Zusammenfassen: Summe<br>Minutennutzung gesamt                                     |
|TotalCallCount                          |ganze Zahl             |Zusammenfassen: Summe<br>Immer 1 – wird verwendet, um die Summe aller Anrufe bereitzustellen            |


### <a name="cloud-call-queue-analytics"></a>Cloudanrufwarteschleife-Analysen

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                          |Beschreibung                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Eingehende Anrufquelle<sup>1</sup>        |Verteilung des Anrufs nach interner/externer Anrufquelle              |
|Anruflautstärke                             |Verteilung des Anrufs nach Anrufwarteschleifen                                |
|Anruferergebnis                           |Verteilung des Anrufs nach Anrufergebnis                                |
|Aktion "Timeout/Überlaufanruf gesamt"      |Verteilung von NICHT weitergeleiteten (abgebrochenen) Anrufen nach Anrufergebnis       |
|Summen des Übertragungs-/Weiterleitungsziels          |Verteilung des weitergeleiteten Anrufs nach Anrufergebnis                      |
|Verhältnis abgebrochener Anrufe                   |Verhältnis der Anzahl erfolgreicher und abgebrochener Anrufe                        |
|Durchschnittliche Sitzungslänge (Sekunden)        |Anruflänge in Sekunden gruppiert nach abgebrochenen/erfolgreichen Anrufen       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht an AQD-Tabelle und Feldzuordnung

|Registerkarte "Bericht"         |Berichtstabellennamen                                                          |Globalfilter |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|Anrufwarteschleife         |Datumsangaben<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Keine          |
 
|Berichtstabellenname            |Quelltabellenname            |Verarbeitung       |
|:----------------------------|:----------------------------|:----------------|
|Datumsangaben                        |Datumsangaben                        |Keine             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Quelle = CallQueueAnalytics, <br>#"Entfernte Spalten" = Table.RemoveColumns(Quelle,{"Anrufanzahl", "Anrufergebnis der Anrufwarteschleife", "Datum", "PSTN-Konnektivitätstyp", "Zieltyp der Anrufwarteschleife", "PSTN-Minuten gesamt"}),<br>Distinct = Table.Distinct(#"Entfernte Spalten") |
|fCallQueueAnalytics          |CallQueueAnalytics           |Keine             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Keine             |

|Berichtsabschnitt                      |Tabelle -> Feld(er) verwendet                |Filter angewendet       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Datumsauswahl                       |Datum -> Datum/Uhrzeit                     |Keine                  |
|Anrufwarteschleifenidentität                 |dCQ-CQIdentity -> Anrufwarteschleifenidentität |Keine                  |
|Eingehende Anrufquelle<sup>1</sup>    |fCallQueueAnalytics -> Anrufanzahl<br>fCallQueueAnalytics -> Anruftyp    |Externe Anrufe: Anruftyp ist extern<br>Interne Anrufe: Anruftyp ist intern |
|Durchschnittliche Wartezeit                    |fCallQueueFinalStateAction -> Durchschnittliche Anrufdauer (Sekunden) |Vor der Übertragung: Anrufergebnis der Anrufwarteschleife ist agent_joined_conference oder transferred_to_agent<br>Vor dem Auflegen: Anrufergebnis der Anrufwarteschleife ist nicht agent_joined_conference oder transferred_to_agent |
|Anrufergebnis                         |fCallQueueAnalytics -> Anrufanzahl<br>fCallQueueAnalytics -> Anrufergebnis der Anrufwarteschleife | Keine |
|Aktion "Timeout/Überlaufanrufe gesamt" |fCallQueueFinalStateAction -> Anrufanzahl<br>fCallQueueFinalStateAction -> Aktion "Endzustand der Anrufwarteschleife" |Die Aktion "Endzustand der Anrufwarteschleife" ist nicht weitergeleitet |
|Summen des Übertragungs-/Weiterleitungsziels       |fCallQueueAnalytics -> Anrufanzahl<br>fCallQueueAnalytics -> Zieltyp der Anrufwarteschleife |Keine |
|Anrufvolumes                        |fCallQueueAnalytics -> Anrufanzahl<br>fCallQueueAnalytics -> Anrufwarteschleifenidentifizierung<br>fCallQueueAnalytics -> Datum |Keine |
|Abgebrochene Anrufe                     |fCallQueueAnalytics -> %Abgebrochene Anrufe<br>fCallQueueAnalytics -> Anrufanzahl<br>fCallQueueAnalytics -> Datum<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned ist TRUE |
|Durchschnittliche Sitzungslänge (Sekunden)    |fCallQueueFinalStateAction -> Durchschnittliche Anrufdauer<br>fCallQueueFinalStateAction -> Datum<br>fCallQueueFinalStateAction -> IsAbandoned |Keine |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>Beschreibung der dCQ-CQIdenity AQD-Felder

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Anrufwarteschleifenidentität                     |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Beschreibung der fCallQueueAnalytics AQD-Felder

|Name                                    |Datentyp                |Beschreibung                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Anrufanzahl                              |ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Anrufe                                          |
|Anrufergebnis der Anrufwarteschleife                  |Text                     |Endzustand des Anrufs der Anrufwarteschleife – mögliche Werte:<br><br>§ agent_joined_conference<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown<br>§ timed_out<br>§ transferred_to_agent |
|Anrufwarteschleifenidentität                     |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|Zieltyp der Anrufwarteschleife                  |Text                     |***Zieltyp für Anrufumleitung – mögliche Werte:***<br><br>§ ApplicationEndpoint<br>§ Mailbox<br>§ Other<br>§ User |
|Anruftyp<sup>1</sup>                   |Text                     |Anruftyp – mögliche Werte:<br><br>§ External<br>§ Internal           |
|Datum                                    |Datum/Uhrzeit                |Startdatum und -uhrzeit des Anrufs der Anrufwarteschleife (Stunde) (UTC)                           | 
|IsAbandoned                             |true/false               |TRUE, wenn der Anruf nicht von einem Agent beantwortet wird                                   |
|PSTN-Konnektivitätstyp                  |Text                     |Anruftyp – mögliche Werte:<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN-Minuten gesamt                      |ganze Zahl             |Zusammenfassen: Summe<br>Nutzung in Minuten für PSTN-Anrufe gesamt                       |

#### <a name="fcallqueueanalytics-measures-description"></a>Beschreibung der fCallQueueAnalytics Kennzahlen

|Name                                    |Datentyp                |Beschreibung                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% Abgebrochene Anrufe***                 |Prozent               |Kennzahl: TotalCallCount / Anrufe gesamt<br>Verhältnis der Anzahl erfolgreicher und abgebrochener Anrufe    |
|Anrufe gesamt                             |ganze Zahl             |Kennzahl: Vom Agent beantwortete Anrufe summieren        |
|TotalCallCount                          |ganze Zahl             |Kennzahl: Summe (Anrufanzahl)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Beschreibung der fCallQueueFinalStateAction AQD-Felder

|Name                                    |Datentyp                |Beschreibung                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durchschnittliche Anrufdauer (Sekunden)         |Dezimalzahl           |Zusammenfassen: Summe<br>Durchschnittliche Anrufdauer in Sekunden |
|Anrufanzahl                              |ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Anrufe                  |
|Anrufergebnis der Anrufwarteschleife                  |Text                     |Endzustand des Anrufs der Anrufwarteschleife – mögliche Werte:<br><br>§ agent_joined_conference<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown<br>§ timed_out<br>§ transferred_to_agent |
|Aktion "Endzustand der Anrufwarteschleife"           |Text                     |Letzte Aktion der Anrufwarteschleife – mögliche Werte:<br><br>§ disconnect<br>§ disconnect_with_busy<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ other<br>§ voicemail |
|Anrufwarteschleifenidentität                     |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|Datum                                    |Datum/Uhrzeit                |Startdatum und -uhrzeit des Anrufs der Anrufwarteschleife (Stunde) (UTC)   |
|IsAbandoned                             |true/false               |TRUE, wenn der Anruf nicht von einem Agent beantwortet wird           |


### <a name="cloud-call-queue-agent-timeline"></a>Zeitachse des Cloudanrufwarteschleifen-Agents

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                                          |Beschreibung                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Anzahl Anrufe nach Agent                                        |Verteilung des Anrufs nach Anrufwarteschleife und Agent                 |
|Gesamtanrufdauer (Sekunden) nach Agent und Anrufwarteschleife   |Gesamtdauer (Sekunden) des Anrufs nach Agent und Anrufwarteschleife     |
|Durchschnittliche Anrufdauer (Sekunden) nach Name des Agents           |Durchschnittliche Dauer (Sekunden) des Anrufs nach Agent                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht an AQD-Tabelle und Feldzuordnung

|Registerkarte "Bericht"         |Berichtstabellennamen        |Globalfilter |
|:------------------|:-------------------------|:-------------|
|Zeitachse des Agents     |fAgentTimelineAnalytics   |Keine          |
 
|Berichtstabellenname            |Quelltabellenname            |Verarbeitung       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Quelle = AgentTimelineAnalytics, <br>#"Geänderter Typ" = Table.TransformColumnTypes(Quelle,{{"Anrufanzahl", Int64.Type}, {"Anrufdauer (Minute)", Int64.Type}, {"Durchschnittliche Anrufdauer (Sekunde)", Nummer eingeben}, {"Datum", Datum eingeben}})|

|Berichtsabschnitt                                |Feld(er) verwendet                         |Filter angewendet       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Name des Agents                                    |Name des Agents                            |Keine                  |
|Name der Anrufwarteschleife                               |Name der Anrufwarteschleife                       |Keine                  |
|Anzahl Anrufe nach Agent                               |Name des Agents<br>Anrufanzahl<br>Datum      |Keine                  |
|Verteilung nach Agent und Anrufwarteschleife          |Name des Agents<br>Anrufanzahl<br>Anrufdauer (Minuten)<br>Name der Anrufwarteschleife |Keine                      |
|Unten links                                   |Name des Agents<br>Durchschnittliche Anrufdauer (Sekunde)<br>Anrufanzahl<br>Anrufdauer (Minute)<br>Name der Anrufwarteschleife | Keine |
|Durchschnittliche Anrufdauer (Sekunden) nach Name des Agents |Name des Agents<br>Durchschnittliche Anrufdauer (Sekunde)<br>Anrufanzahl<br>Anrufdauer (Minute)<br>Name der Anrufwarteschleife | Keine |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Beschreibung der fAgentTimelineAnalytics AQD-Felder

|Name                                    |Datentyp                |Beschreibung                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Name des Agents                              |Text                     |Benutzer-UPN<br>Wenn der vollständige Benutzername **user@microsoft.com** ist, lautet dieser Wert wie folgt: **user** |
|Durchschnittliche Anrufdauer (Sekunde)          |Dezimalzahl           |Zusammenfassen: Summe<br>Die durchschnittliche Dauer der Anrufe der Anrufwarteschleife in Sekunden |
|Anrufanzahl                              |ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der vom Agent verarbeiteten Anrufe                    |
|Anrufdauer (Minute)                  |ganze Zahl             |Zusammenfassen: Summe<br>Anrufdauer der Anrufe der Anrufwarteschleife insgesamt in Minuten  |
|Name der Anrufwarteschleife                         |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|Datum                                    |Datum                     |                                                    |


> [!NOTE]
> 1) Dieser Bericht zeigt die Anrufanzahl aus der Perspektive der Agents, daher ist die Gesamtzahl der Anrufe in diesem Bericht normalerweise höher als die Gesamtzahl der Anrufe im Bericht **Cloud-Anrufwarteschleifenanalyse.** Jeder Anruf in der Warteschlange kann einem oder mehreren Agents mindestens einmal präsentiert werden, bevor er beantwortet wird. Jeder Anruf in der Warteschleife, der einem Mitarbeiter angezeigt wird, wird auf diesen Bericht angerechnet, auch wenn er vom Agent nicht beantwortet wurde. Der Unterschied bei der Anrufanzahl zwischen diesen beiden Berichten ist bei der **Weiterleitungsoption Attendant** deutlicher, die jeden Agent für jeden Anruf anruft. 
> 2) Wenn beim ersten Anruf ein Anruf bei der ersten Anrufwarteschleife eintrifft und die Anzahl der bereits in dieser Warteschlange wartenden Anrufe das Limit für die Behandlung von Anrufen überschreitet und die Umleitungsoption Anrufe an eine zweite Anrufwarteschleife sendet, werden die Agents in der zweiten Anrufwarteschleife in diesem Bericht als in der ersten Anrufwarteschleife angezeigt.  

## <a name="known-issues"></a>Bekannte Probleme

- Anrufwarteschleifen und automatische Telefonzentralen werden anhand der ID des Ressourcenkontos anstelle der Namen der Anrufwarteschleife/automatischen Telefonzentralen angezeigt.  Um den gesamten Datenverkehr für eine automatische Telefonzentrale oder Anrufwarteschleife anzuzeigen, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefonzentrale oder Anrufwarteschleife zugewiesen sind.

- Der Verlauf von nur 28 Tagen ist im Dashboard verfügbar, da die Daten der Anrufwarteschleife/automatischen Telefonzentrale als personenbezogene Daten betrachtet werden und den Datenaufbewahrungsrichtlinien unterliegen.

- <sup>1</sup> **Eingehende Anrufquelle** in den Diagrammen für die automatische Telefonzentrale und die Anrufwarteschleife zeigen die letzte Anrufabschnittsquelle anstelle der ersten Anrufabschnittsquelle an. Wenn beispielsweise eine automatische Telefonzentrale einen externen Anruf empfängt und den Anruf an eine andere automatische Telefonzentrale oder Anrufwarteschleife überträgt, wird die **eingehende Anrufquelle** als intern gemeldet.
