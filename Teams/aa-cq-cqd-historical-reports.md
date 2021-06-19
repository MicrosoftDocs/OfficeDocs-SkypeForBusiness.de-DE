---
title: automatische Telefonzentrale & eines Anrufwarteschlangen-Verlaufsberichts
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: Erfahren Sie, wie Sie mithilfe des Anrufqualitätsdashboards Power BI, um Die automatische Telefonzentrale und Verlaufsdaten der Anrufwarteschleife anzuzeigen.
ms.openlocfilehash: 77b74eb48a16992f7f601bd6cccf3c61b421fc30
ms.sourcegitcommit: 24ae0c223e9d915c505146d422ad049c88a4ed51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53023246"
---
# <a name="auto-attendant--call-queue-historical-report"></a>automatische Telefonzentrale & eines Anrufwarteschlangen-Verlaufsberichts

Die Vorlage für Teams automatische Telefonzentrale & Anrufwarteschleifen-Verlaufsbericht Power BI die folgenden drei Berichte:

- automatische Telefonzentrale – Zeigt Analysen für Anrufe an, die in Ihre automatischen Telefon attendants eins gehen.
- Anrufwarteschleife – Zeigt Analysen für Anrufe an, die in Ihre Anrufwarteschleifen kommen.
- Agent-Zeitachse – Zeigt eine Zeitachsenansicht der Agents an, die an Anrufen in der Anrufwarteschleife aktiv sind.

Diese Berichte verwenden Daten aus dem [Anrufqualitätsdashboard-Datenspeicher.](CQD-Power-BI-query-templates.md) Damit können Organisationen die Anzahl der Anrufe melden, die von automatischen Telefonkonferenzen und Anrufwarteschleifen verarbeitet werden.  Darüber hinaus bieten sie Einblicke in die Leistung des Agents in den Anrufwarteschleifen.

## <a name="what-are-the-requirements"></a>Welche Anforderungen gelten? 

Sie müssen ihre Power BI Desktop haben. Sie können sie über den [Microsoft-Windows Store](https://aka.ms/pbidesktopstore)installieren.

Sie können die kostenlose Version von Power BI Desktop. Die kompatible Mindestversion ist 2.85.681.0 (September 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Berechtigungen für den Zugriff auf die CQD-Pipeline

Das Konto, das Sie zum Anzeigen des AA-Berichts & CQ Analytics-Verlauf verwenden, muss über Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügen. Weitere Informationen finden Sie unter [Zugriffsrolle für AQD.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>Installation 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Power BI Desktop auf dem Computer installiert haben und dass Ihr Konto über die erforderlichen Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügt.

Führen Sie die folgenden Schritte aus:

- Laden Sie [das AQD Power BI Abfragevorlagen herunter,](https://www.microsoft.com/download/details.aspx?id=102291) und speichern Sie die ZIP-Datei in einem Verzeichnis auf Ihrem Computer.

- Doppelklicken Sie auf die ZIP-Datei, um sie zu öffnen.

- Doppelklicken Sie auf die Vorlagendatei "Kombinierte AQ- und AA-Analysen 20201105.pbit", und Power BI Desktop starten.

- Sie werden aufgefordert, den Bereich für die CQD-Datenpipeline auszuwählen. Wählen Sie die Region aus, in der sich Ihr Mandant befindet.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot der Auswahl der Region für die CQD-Datenpipeline":::

- Die Region, in der sich Ihr Mandant befindet, kann mit dem [Cmdlet Get-CsTenant](/powershell/module/skype/get-cstenant) ermittelt werden.

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - Die Region wird nach dem wie im obigen Beispiel angezeigt, wo **/** region ist: noam

 - Der Bericht wird mit Beispieldaten gestartet.
 
 - Um Ihre eigenen Daten zu sehen, wählen Sie **auf der** Registerkarte Start unter Abfragen in einem Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot mit Auswahl der Aktualisierungsoption":::

- Sie werden dann aufgefordert, sich anmelden. Wählen **Sie Organisationskonto** und dann **Anmelden aus.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot showing login":::

- Wählen Sie **Verbinden** aus, und beobachten Sie die Datenaktualisierung.

## <a name="data-latency-and-aa--cq-analytics"></a>Datenlatenz und AA-& AQ-Analysen

Die Daten sind innerhalb von 30 Minuten in der CQD-Datenpipeline verfügbar.

Sie müssen die Daten aktualisieren, um die neuen Analysedaten zu sehen. 

## <a name="customization"></a>Anpassung 

Sie können bestimmte Visualisierungsaspekte der Berichte anpassen, z. B. Felder hinzufügen oder entfernen, die in den verschiedenen Visualisierungen angezeigt werden sollen, Ändern des Diagrammtyps und so weiter.

Dem Bericht können keine weiteren Datenfelder hinzugefügt werden.

### <a name="change-color-schema"></a>Ändern des Farbschemas 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Installationsschritte bereits abgeschlossen haben.

Führen Sie die folgenden Schritte aus:
- Wählen **Sie im Menüband die** Registerkarte Ansicht aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot, in dem die Registerkarte "Ansicht" zum Ändern des Farbschemas ausgewählt wird":::

- Wählen Sie das Farbschema aus der Dropdownliste aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot mit verschiedenen Farbschemas":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definitionen automatische Telefonzentrale und Verlaufsberichte für Anrufwarteschleifen

### <a name="cloud-auto-attendant-analytics"></a>Cloud automatische Telefonzentrale Analytics

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                          |Beschreibung                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Quelle eines eingehenden<sup>Anrufs 1</sup>        |Verteilung von Anrufen nach interner/externer Anrufquelle             |
|Summen der Verzeichnissuchmethode          |Verteilung von Anrufen nach Suchtyp                               |
|Anruferaktion                           |Verteilung von Anrufen nach Anrufempfänger                             |
|Anrufergebnis                             |Verteilung von Anrufen nach endgültigem Anrufstatus                          |
|Anzahl der Anrufer-Aktionen                     |Verteilung von Anrufen nach Rufnummernaktion, die während des Anrufs verwendet wird        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht zur CQD-Tabelle und Feldzuordnung

|Berichtsregisterkarte            |Name der Berichtstabelle     |Globaler Filter                          |
|:---------------------|:---------------------|:--------------------------------------|
|automatische Telefonzentrale        |fAutoAttendant        |AAStartTime liegt innerhalb der letzten 28 Tage. |


|Name der Berichtstabelle            |Name der Quelltabelle            |Wird verarbeitet       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant, <br>#"Gefilterte Zeilen" = Table.SelectRows(Source, each true), <br>#"automatische Telefonzentrale" = Table.AddColumn(#"Filtered Rows", "AA Name", each List.First(Text.Split([AAIdentity], "@"))), <br>#"Changed Type" = Table.TransformColumnTypes(#"automatische Telefonzentrale",{{"AAStartTime", type datetime}}), <br>#"Removed Columns" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|Berichtsabschnitt                                  |Verwendete Feld(n)                              |Angewendete Filter     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Datumsauswahl                                   |AAStartTime                                |Keine                |
|automatische Telefonzentrale                                  |AA-Name                                    |Keine                |
|Quelle eines eingehenden<sup>Anrufs 1</sup>                |Anruftyp<br>TotalCallCount                |Externe Anrufe: Anruftyp ist extern<br>Interne Anrufe: Anruftyp ist intern |
|Summen der Verzeichnissuchmethode                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod ist abs_search_dtmf oder abs_search_name    |
|Anruferaktionen                                  |AATransferAction<br>TotalCallCount         |Keine                                                             |
|Durchschnittliche Sekunden in AA<br>Durchschnittliche Anruferaktionen |AAChainDuration<br>AACallerActionCount     |Keine                                                             |
|Anrufergebnisse                                    |AACallResult<br>TotalCallCount             |Keine                                                             |
|Anzahl der Anruferaktionen                            |AACallerActionCount<br>TotalCallCount      |Keine                                                             |
|Unterer Bereich des Berichts                         |AA-Name<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Anruftyp<br>TotalCallCount |Keine                |

#### <a name="fautoattendant-cqd-fields-description"></a>Beschreibung der fAutoAttendant CQD-Felder

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA-Name                                 |Text                     |Name des Ressourcenkontos, das dem automatische Telefonzentrale<br><br>Wenn der vollständige Name des Ressourcenkontos **aa_test@microsoft.com** dann der Wert wie hier: **aa_test** |
|AACallerActionCount                     |ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der aktionen, die vom Anrufer während automatische Telefonzentrale Anrufs ausgewählt wurden  |
|AACallFlow                              |Text                     |Kapselt die verschiedenen Zustände automatische Telefonzentrale Aufruf von -- möglichen Werten:<br><br>§ abs_search<br>§ Ankündigung<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Text                     |Ergebnis des letzten Aufrufs – mögliche Werte:<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ unbekannt<br>§ user_terminated |
|AAChainDuration                         |Dezimalzahl           |Zusammenfassen: Summe<br>Dauer des Anrufs in automatische Telefonzentrale                     |
|AAChainIndex                            |Text                     |                                                                         |
|AAConnectivityType                      |Text                     |Art des Aufrufs – mögliche Werte:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Text                     |Anzahl der am Anruf beteiligten automatischen Telefonkonferenzen                               |
|AADirectorySearchMethod                 |Text                     |Letzte Adressbuch-Suchmethode – mögliche Werte:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |Datum/Uhrzeit                |automatische Telefonzentrale startzeit eines Anrufs                                           |
|AATransferAction                        |Text                     |Zieltyp für die Anrufübertragung – mögliche Werte:<br><br>***§ Application - Voice Application Entity**§_<br> external_pstn <br>_§ hunt_group - Call Queue *_entity_* _<br>_ * _§ orgaa - Organizational automatische Telefonzentrale entity_**<br>§ shared_voicemail<br>§ unbekannt<br>§ Benutzer |
|Anruftyp<sup>1</sup>                   |Text                     |Art des Aufrufs – mögliche Werte:<br><br>§ Extern<br>§ Intern         |
|IsAAInvolved                            |Text                     |Immer 1                                                                 |
|PSTNMinutes                             |ganze Zahl             |Zusammenfassen: Summe<br>Gesamtminutenverwendung                                     |
|TotalCallCount                          |ganze Zahl             |Zusammenfassen: Summe<br>Immer 1 – wird verwendet, um die Summe aller Anrufe zu liefern.            |


### <a name="cloud-call-queue-analytics"></a>Analyse von Cloudanrufwarteschleifen

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                          |Beschreibung                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Quelle eines eingehenden<sup>Anrufs 1</sup>        |Verteilung des Anrufs nach interner/externer Anrufquelle              |
|Anruflautstärke                             |Verteilung von Anrufen nach Anrufwarteschleifen                                |
|Anruferergebnis                           |Verteilung des Anrufs nach Anrufergebnis                                |
|Aktion "Timeout/Überlaufaufruf Gesamt"      |Verteilung des NICHT weitergeleiteten(abgebrochenen) Anrufs nach Anrufergebnis       |
|Gesamtübertragungsziel für Übertragung/Weiterleitung          |Verteilung des nach Anrufergebnis weitergeleiteten Anrufs                      |
|Verhältnis für abgebrochene Anrufe                   |Verhältnis von erfolgreichem zu abgebrochener Anrufanzahl                        |
|Durchschnittliche Sitzungslänge (Sekunden)        |Anruflänge in Sekunden nach abgebrochenen/erfolgreichen Anrufen       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht zur CQD-Tabelle und Feldzuordnung

|Berichtsregisterkarte         |Berichts-Tabellennamen                                                          |Globaler Filter |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|Anrufwarteschleife         |Datumsangaben<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Keine          |
 
|Name der Berichtstabelle            |Name der Quelltabelle            |Wird verarbeitet       |
|:----------------------------|:----------------------------|:----------------|
|Datumsangaben                        |Datumsangaben                        |Keine             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Removed Columns" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Removed Columns") |
|fCallQueueAnalytics          |CallQueueAnalytics           |Keine             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Keine             |

|Berichtsabschnitt                      |Table -> Field(s) Used                |Angewendete Filter       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Datumsauswahl                       |Dates -> DateTime                     |Keine                  |
|Anrufwarteschlangenidentität                 |dCQ-CQIdentity -> Call Queue Identity |Keine                  |
|Quelle eines eingehenden<sup>Anrufs 1</sup>    |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Type    |Externe Anrufe: Anruftyp ist extern<br>Interne Anrufe: Anruftyp ist intern |
|Avg Waiting Time                    |fCallQueueFinalStateAction -> Average Call Duration (Seconds) |Vor der Übertragung: Das Anrufergebnis der Anrufwarteschleife agent_joined_conference oder transferred_to_agent<br>Vor auflegen: Das Anrufergebnis der Anrufwarteschleife wird agent_joined_conference nicht transferred_to_agent |
|Anrufergebnis                         |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Queue Call Result | Keine |
|Timeout/Überlaufaufrufe Gesamtaktion |fCallQueueFinalStateAction -> Call Count<br>fCallQueueFinalStateAction -> Aktion zum endgültigen Status der Anrufwarteschleife |Aktion zum endgültigen Status einer Anrufwarteschleife wird nicht weitergeleitet |
|Gesamtziel für Übertragungen/Forard       |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Queue Target Type |Keine |
|Anrufvolumen                        |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Identifizieren einer Anrufwarteschleife<br>fCallQueueAnalytics -> Date |Keine |
|Abgebrochene Anrufe                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned is True |
|Durchschnittliche Sitzungslänge (Sekunden)    |fCallQueueFinalStateAction -> Average Call Duration<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |Keine |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>Beschreibung der Felder "dCQ-CQIdenity" im Feld "DCQ-CQIdenity"

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Anrufwarteschlangenidentität                     |Text                     |Name des an die Anrufwarteschleife angefügten Ressourcenkontos<br><br>Wenn der vollständige Name des Ressourcenkontos **cq_test@microsoft.com** dann der Wert wie hier: **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Beschreibung der FCallQueueAnalytics CQD-Felder

|Name                                    |Datentyp                |Beschreibung                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Anrufanzahl                              |ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Anrufe                                          |
|Anrufwarteschleifen-Anrufergebnis                  |Text                     |Endzustand des Anrufwarteschleifenanrufs – mögliche Werte:<br><br>§ agent_joined_conference<br>§ abgelehnt<br>§ getrennt<br>§ Fehler<br>§ fehlgeschlagen<br>§ ungültig<br>§ Überlauf<br>§ timed_out<br>§ transferred_to_agent |
|Anrufwarteschlangenidentität                     |Text                     |Name des an die Anrufwarteschleife angefügten Ressourcenkontos<br><br>Wenn der vollständige Name des Ressourcenkontos **cq_test@microsoft.com** dann der Wert wie hier: **cq_test** |
|Zieltyp der Anrufwarteschleife                  |Text                     |***Zieltyp der Anrufumleitung – mögliche Werte:***<br><br>§ ApplicationEndpoint<br>§ Postfach<br>§ Andere<br>§ Benutzer |
|Anruftyp<sup>1</sup>                   |Text                     |Art des Aufrufs – mögliche Werte:<br><br>§ Extern<br>§ Intern           |
|Datum                                    |Datum/Uhrzeit                |Startdatum und Uhrzeit des Anrufs in der Anrufwarteschleife (UTC)                           | 
|IsAbandoned                             |wahr/falsch               |"True", wenn der Anruf nicht von einem Mitarbeiter beantwortet wurde                                   |
|PSTN Connectivity Type                  |Text                     |Art des Aufrufs – mögliche Werte:<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN Total Minutes                      |ganze Zahl             |Zusammenfassen: Summe<br>Gesamtnutzung in Minuten für PSTN-Anrufe                       |

#### <a name="fcallqueueanalytics-measures-description"></a>Beschreibung der fCallQueueAnalytics-Measures

|Name                                    |Datentyp                |Beschreibung                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% Abgebrochene Anrufe***                 |Prozentsatz               |Measure: TotalCallCount /Total Calls<br>Verhältnis von erfolgreichem zu abgebrochener Anrufanzahl    |
|Anrufe insgesamt                             |ganze Zahl             |Measure: Sum Agent answered calls        |
|TotalCallCount                          |ganze Zahl             |Measure: Summe(Anrufanzahl)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Beschreibung der fCallQueueFinalStateAction CQD-Felder

|Name                                    |Datentyp                |Beschreibung                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durchschnittliche Anrufdauer (Sekunden)         |Dezimalzahl           |Zusammenfassen: Summe<br>Durchschnittliche Anrufdauer in Sekunden |
|Anrufanzahl                              |ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Anrufe                  |
|Anrufwarteschleifen-Anrufergebnis                  |Text                     |Endzustand des Anrufwarteschleifenanrufs – mögliche Werte:<br><br>§ agent_joined_conference<br>§ abgelehnt<br>§ getrennt<br>§ Fehler<br>§ fehlgeschlagen<br>§ ungültig<br>§ Überlauf<br>§ timed_out<br>§ transferred_to_agent |
|Aktion zum endgültigen Status einer Anrufwarteschleife           |Text                     |Letzte Aktion der Anrufwarteschleife – mögliche Werte:<br><br>§ trennen<br>§ disconnect_with_busy<br>§ failed_to_accept_call<br>§ weiterleiten<br>§ shared_voicemail<br>§ Sonstiges<br>§ Voicemail |
|Anrufwarteschlangenidentität                     |Text                     |Name des an die Anrufwarteschleife angefügten Ressourcenkontos<br><br>Wenn der vollständige Name des Ressourcenkontos **cq_test@microsoft.com** dann der Wert wie hier: **cq_test** |
|Datum                                    |Datum/Uhrzeit                |Startdatum und Uhrzeit des Anrufs in der Anrufwarteschleife (UTC)   |
|IsAbandoned                             |wahr/falsch               |"True", wenn der Anruf nicht von einem Mitarbeiter beantwortet wurde           |


### <a name="cloud-call-queue-agent-timeline"></a>Zeitachse für Anrufwarteschleifen-Agent in der Cloud

#### <a name="report-description"></a>Berichtsbeschreibung

|Berichtsabschnitt                                          |Beschreibung                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# Anrufe nach Mitarbeiter                                        |Verteilung von Anrufen nach Anrufwarteschleife und Agent                 |
|Gesamtanrufdauer (Sekunden) nach Agent und Anrufwarteschleife   |Gesamtdauer (Sekunden) des Anrufs nach Agent und Anrufwarteschleife     |
|Durchschnittliche Anrufdauer (Sekunden) nach Agentname           |Durchschnittliche Dauer (Sekunden) des Anrufs nach Agent                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Bericht zur CQD-Tabelle und Feldzuordnung

|Berichtsregisterkarte         |Berichts-Tabellennamen        |Globaler Filter |
|:------------------|:-------------------------|:-------------|
|Agent-Zeitachse     |fAgentTimelineAnalytics   |Keine          |
 
|Name der Berichtstabelle            |Name der Quelltabelle            |Wird verarbeitet       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Changed Type" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|Berichtsabschnitt                                |Verwendete Feld(n)                         |Angewendete Filter       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Name des Mitarbeiters                                    |Name des Mitarbeiters                            |Keine                  |
|Name der Anrufwarteschleife                               |Name der Anrufwarteschleife                       |Keine                  |
|#Calls nach Agent                               |Name des Mitarbeiters<br>Anrufanzahl<br>Datum      |Keine                  |
|Verteilung nach Agent und Anrufwarteschleife          |Name des Mitarbeiters<br>Anrufanzahl<br>Anrufdauer (Minuten)<br>Name der Anrufwarteschleife |Keine                      |
|Unten links                                   |Name des Mitarbeiters<br>Durchschnittliche Anrufdauer (Sekunde)<br>Anrufanzahl<br>Anrufdauer (Minute)<br>Name der Anrufwarteschleife | Keine |
|Durchschnittliche Anrufdauer (Sekunden) nach Agentname |Name des Mitarbeiters<br>Durchschnittliche Anrufdauer (Sekunde)<br>Anrufanzahl<br>Anrufdauer (Minute)<br>Name der Anrufwarteschleife | Keine |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Beschreibung der fAgentTimelineAnalytics CQD-Felder

|Name                                    |Datentyp                |Beschreibung                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Name des Mitarbeiters                              |Text                     |Benutzer-UPN<br>Wenn der vollständige Benutzername **user@microsoft.com** dann wird der Wert wie hier **angezeigt: Benutzer** |
|Durchschnittliche Anrufdauer (Sekunde)          |Dezimalzahl           |Zusammenfassen: Summe<br>Durchschnittliche Dauer von Anrufwarteschleifenanrufen in Sekunden |
|Anrufanzahl                              |ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der vom Mitarbeiter bearbeiteten Anrufe                    |
|Anrufdauer (Minute)                  |ganze Zahl             |Zusammenfassen: Summe<br>Gesamtanrufdauer von Anrufwarteschleifenanrufen in Minuten  |
|Name der Anrufwarteschleife                         |Text                     |Name des an die Anrufwarteschleife angefügten Ressourcenkontos<br><br>Wenn der vollständige Name des Ressourcenkontos **cq_test@microsoft.com** dann der Wert wie hier: **cq_test** |
|Datum                                    |Datum                     |                                                    |


## <a name="known-issues"></a>Bekannte Probleme

- Anrufwarteschleifen und automatische Telefonkonferenzen werden nach der ID des Ressourcenkontos anstelle der Namen der Anrufwarteschlange/automatischen Telefonant angezeigt.  Wenn Sie den ganzen Datenverkehr für eine automatische Telefonkonferenz oder Anrufwarteschleife anzeigen möchten, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefon attendant oder der Anrufwarteschleife zugewiesen sind.

- Der Verlauf von nur 28 Tagen steht im Dashboard zur Verfügung, da Daten aus Anrufwarteschleife und automatischer Telefonkonferenz als persönliche Daten betrachtet werden und den Aufbewahrungsrichtlinien für den Datenschutz unterliegen.

- <sup>1</sup> **Die Quelle eingehender** Anrufe in der automatischen Telefon attendant und die Diagrammen der Anrufwarteschleife zeigen die endgültige Quelle des Anrufs ab und nicht die Quelle des anfänglichen Anrufs. Wenn beispielsweise eine automatische Telefonkonferenz einen externen Anruf erhält und den Anruf an  eine andere automatische Telefonkonferenz oder Anrufwarteschleife überträgt, wird die Eingehende Anrufquelle als Intern angezeigt.
