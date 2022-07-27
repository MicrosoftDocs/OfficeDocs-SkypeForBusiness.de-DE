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
ms.openlocfilehash: b9bb3cf0990058cd16ed35d52d07f63be6cd90fb
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024008"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Verlaufsbericht für automatische Telefonzentrale und Anrufwarteschleife

Die Power BI-Vorlage "Teams Auto Attendant & Anrufwarteschleifenverlaufsbericht" enthält die folgenden drei Berichte:

- [Automatische Telefonzentrale:](media/cqd-teams-aa-cq-historical-report-sample-aa.png) Zeigt Analysen für Anrufe an, die in Ihren automatischen Telefonzentralen eingehen.
- [Anrufwarteschleife:](media/cqd-teams-aa-cq-historical-report-sample-cq.png) Zeigt Analysen für Anrufe an, die in Ihren Anrufwarteschleifen eingehen.
- [Agent-Zeitachse:](media/cqd-teams-aa-cq-historical-report-sample-at.png) Zeigt eine Zeitachsenansicht der Agents an, die bei Anrufen in der Anrufwarteschleife aktiv sind.

Diese Berichte verwenden Daten aus dem [AQD](CQD-Power-BI-query-templates.md)-Datenspeicher. Die Berichte ermöglichen Es Organisationen, über die Anzahl der Anrufe zu berichten, die von automatischen Telefonzentralen und Anrufwarteschleifen verarbeitet werden.  Die Berichte bieten auch Einblicke in die Agentleistung in den Anrufwarteschleifen.

### <a name="v160-published-on-july-22-2022"></a>V1.60 veröffentlicht am 22. Juli 2022

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
|AACallerActionCount                     |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Aktionen, die während des Anrufs vom Anrufer in der automatischen Telefonzentrale ausgewählt wurden  |
|AACallFlow                              |Text                     |Kapselt die verschiedenen Zustände der Anrufwerte der automatischen Telefonzentrale – mögliche Werte:<br><br>§ abs_search<br>§ announcement<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Text                     |Endergebnis des Aufrufs – mögliche Werte:<br><br>§ failed_to_establish_media (der Medienteil des Anrufs konnte nicht festgestellt werden)<br>§ failover_to_operator (Anruf, der in der Regel aufgrund eines Systemfehlers an den Betreiber weitergeleitet wird)<br>§ oaa_chain_too_long (zu viele Beine im AA)<br>§ oaa_session_too_long (AA-Sitzung dauert zu lange)<br>§ service_declined (AA hat den Anruf nicht angenommen)<br>§ service_terminated (AA-Konfiguration trennt den Anruf)<br>§ terminated_automatic_selection (Die AA-Konfiguration trennt die Anrufe)<br>§ terminated_no_operator (Aufruf aufgrund des Fehlers beendet, kein Operator definiert) <br>§ terminated_transfer_failed (Anruf wurde als Übertragungsfehler beendet - in der Regel zu Ausdr. Rufnummer)<br>***§ transferred_to_operator*** (Anruf wurde an den Operator weitergeleitet - in der Regel aufgrund eines Benutzereingabefehlers)<br>§ transferred_to_receptionist (identisch mit transferred_to_operator)<br>§ transferred_to_self (Anruf wurde an den Anfang der AA zurückgegeben - in der Regel über eine Menüankündigungsoption)<br>§ transferred_to_shared_voicemail (Anruf wurde an freigegebene Voicemail weitergeleitet)<br>§ transferred_to_user (Anruf wurde an einen Benutzer weitergeleitet - umfasst Anrufwarteschleifen)<br>§ unbekannt (unbekannter Fehler)<br>§ user_terminated (Anrufer aufgehängt) |
|AAChainDuration                         |Dezimalzahl           |Zusammenfassen: Summe<br>Dauer des Anrufs in der automatischen Telefonzentrale                     |
|AAChainIndex                            |Text                     |                                                                         |
|AAConnectivityType                      |Text                     |Typ der Aufrufe – mögliche Werte:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Text                     |Anzahl der am Anruf beteiligten automatischen Telefonzentralen                               |
|AADirectorySearchMethod                 |Text                     |Letzte Adressbuch-Suchmethode – mögliche Werte:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |Datum/Uhrzeit                |Startzeit des Anrufs der automatischen Telefonzentrale                                           |
|AATransferAction                        |Text                     |Anrufweiterleitungszieltyp – mögliche Werte:<br><br>***§ application – Sprachanwendungsentität**_<br>§ external_pstn<br>_*_§ hunt_group – Entität "Anrufwarteschleife"_*_<br>_*_§ orgaa – Entität "Automatische Telefonzentrale der Organisation"_**<br>§ shared_voicemail<br>§ unknown<br>§ user |
|Anruftyp<sup>1</sup>                   |Text                     |Typ der Aufrufe – mögliche Werte:<br><br>§ External<br>§ Internal         |
|IsAAInvolved                            |Text                     |Immer 1                                                                 |
|PSTNMinutes                             |Ganze Zahl             |Zusammenfassen: Summe<br>Minutennutzung gesamt                                     |
|TotalCallCount                          |Ganze Zahl             |Zusammenfassen: Summe<br>Immer 1 – wird verwendet, um die Summe aller Anrufe bereitzustellen            |


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
|Anrufanzahl                              |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Anrufe                                          |
|Anrufergebnis der Anrufwarteschleife                  |Text                     |Endzustand des Anrufs der Anrufwarteschleife – mögliche Werte:<br><br>§ agent_joined_conference (angenommene Telefonkonferenzen)<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown (Überlaufbedingung erfüllt)<br>§ timed_out (Timeoutbedingung erfüllt)<br>§ transferred_to_agent (beantwortete Tranfermodusaufrufe {default}) |
|Anrufwarteschleifenidentität                     |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|Zieltyp der Anrufwarteschleife                  |Text                     |***Anrufumleitungszieltyp – mögliche Werte:***<br><br>§ ApplicationEndpoint<br>§ Mailbox<br>§ Other<br>§ User |
|Anruftyp<sup>1</sup>                   |Text                     |Typ der Aufrufe – mögliche Werte:<br><br>§ External<br>§ Internal           |
|Datum                                    |Datum/Uhrzeit                |Startdatum und -uhrzeit des Anrufs der Anrufwarteschleife (Stunde) (UTC)                           | 
|IsAbandoned                             |Wahr/falsch               |TRUE, wenn der Anruf nicht von einem Agent beantwortet wird                                   |
|PSTN-Konnektivitätstyp                  |Text                     |Typ der Aufrufe – mögliche Werte:<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN-Minuten gesamt                      |Ganze Zahl             |Zusammenfassen: Summe<br>Nutzung in Minuten für PSTN-Anrufe gesamt                       |

#### <a name="fcallqueueanalytics-measures-description"></a>Beschreibung der fCallQueueAnalytics Kennzahlen

|Name                                    |Datentyp                |Beschreibung                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% Abgebrochene Anrufe***                 |Prozent               |Measure: Anzahl abgebrochener Anrufe / Gesamtanrufe    |
|Anrufe gesamt                             |Ganze Zahl             |Kennzahl: Vom Agent beantwortete Anrufe summieren        |
|TotalCallCount                          |Ganze Zahl             |Kennzahl: Summe (Anrufanzahl)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Beschreibung der fCallQueueFinalStateAction AQD-Felder

|Name                                    |Datentyp                |Beschreibung                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durchschnittliche Anrufdauer (Sekunden)         |Dezimalzahl           |Zusammenfassen: Summe<br>Durchschnittliche Anrufdauer in Sekunden |
|Anrufanzahl                              |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Anrufe                  |
|Anrufergebnis der Anrufwarteschleife                  |Text                     |Endzustand des Anrufs der Anrufwarteschleife – mögliche Werte:<br><br>§ agent_joined_conference (angenommene Telefonkonferenzen)<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown (Überlaufbedingung erfüllt)<br>§ timed_out (Timeoutbedingung erfüllt)<br>§ transferred_to_agent (beantwortete Übertragungsmodus ruft {default} auf. |
|Aktion "Endzustand der Anrufwarteschleife"           |Text                     |Letzte Aktion der Anrufwarteschleife – mögliche Werte:<br><br>§ disconnect (timed_out Aufrufe)<br>§ disconnect_with_busy (Überlaufaufrufe)<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ other<br>§ voicemail |
|Anrufwarteschleifenidentität                     |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|Datum                                    |Datum/Uhrzeit                |Startdatum und -uhrzeit des Anrufs der Anrufwarteschleife (Stunde) (UTC)   |
|IsAbandoned                             |Wahr/falsch               |TRUE, wenn der Anruf nicht von einem Agent beantwortet wird           |


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
|Name des Agents                              |Text                     |Benutzer-UPN<br>Wenn der vollständige Benutzername **user@microsoft.com** ist, lautet dieser Wert: **Benutzer** |
|Durchschnittliche Anrufdauer (Sekunde)          |Dezimalzahl           |Zusammenfassen: Summe<br>Die durchschnittliche Dauer von Anrufwarteschleifenanrufen in Sekunden |
|Anrufanzahl                              |Ganze Zahl             |Zusammenfassen: Summe<br>Anzahl der Dem Agent angezeigten Anrufe     |
|Anrufdauer (Minute)                  |Ganze Zahl             |Zusammenfassen: Summe<br>Gesamtanrufdauer der angenommenen Anrufwarteschleifenanrufe in Minuten (abgerundet auf die nächste Minute)  |
|Name der Anrufwarteschleife                         |Text                     |Name des Ressourcenkontos, das an die Anrufwarteschleife angefügt ist<br><br>Wenn der vollständige Ressourcenkontoname **cq_test@microsoft.com** ist, lautet dieser Wert wie folgt: **cq_test** |
|Datum                                    |Datum                     |                                                    |


> [!NOTE]
> 1) Dieser Bericht zeigt die Anrufanzahl aus der Sicht der Agents, und daher ist die Anrufanzahl in diesem Bericht in der Regel höher als die Gesamtzahl der Anrufe im **Cloud Call Queue Analytics-Bericht** . Jeder Anruf in der Warteschleife kann mindestens einmal vor der Beantwortung einem oder mehreren Agents angezeigt werden. Jeder Anruf in der Anrufwarteschleife, der einem Agent angezeigt wird, wird auf diesen Bericht gezählt, auch wenn er vom Agent nicht beantwortet wurde. Der Unterschied bei der Anrufanzahl zwischen diesen beiden Berichten ist mit der **Weiterleitungsoption der Telefonzentrale** , die jeden Agent für jeden Anruf anruft, ausgeprägter. 
> 2) Wenn ein Anruf zum ersten Mal in der ersten Anrufwarteschleife ankommt, wenn die Anzahl der Anrufe, die bereits in dieser Warteschleife warten, den Grenzwert für die **Anrufüberlaufbehandlung** überschreitet und wenn die Umleitungsoption Anrufe an eine zweite Anrufwarteschleife sendet, werden die Agents in der zweiten Anrufwarteschleife als in der ersten Anrufwarteschleife in diesem Bericht angezeigt. 

## <a name="known-issues"></a>Bekannte Probleme

- Anrufwarteschleifen und automatische Telefonzentralen werden anhand der ID des Ressourcenkontos anstelle der Namen der Anrufwarteschleife/automatischen Telefonzentralen angezeigt.  Um den gesamten Datenverkehr für eine automatische Telefonzentrale oder Anrufwarteschleife anzuzeigen, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefonzentrale oder Anrufwarteschleife zugewiesen sind.

- Im Dashboard sind nur 28 Tage des Verlaufs verfügbar, da Anrufwarteschleifen-/automatische Telefonzentralendaten als personenbezogene Daten betrachtet werden und den Aufbewahrungsrichtlinien für den Datenschutz unterliegen.

- In einigen Szenarien kann sich die Anzahl der Anrufe, die der Agent angenommen hat, im Cloud Call Queue Agent-Zeitachsenbericht von der Anzahl der Anrufe unterscheiden, die im Teams-Clientanrufverlauf angezeigt werden. Der Anrufverlauf des Teams-Clients ist korrekt. Der Support wird derzeit untersucht, aber zurzeit ist keine geschätzte Zeit für die Reparatur verfügbar.

- <sup>1</sup> **Eingehende Anrufquelle** in den Diagrammen für die automatische Telefonzentrale und die Anrufwarteschleife zeigen die letzte Anrufabschnittsquelle anstelle der ersten Anrufabschnittsquelle an. Wenn beispielsweise eine automatische Telefonzentrale einen externen Anruf empfängt und den Anruf an eine andere automatische Telefonzentrale oder Anrufwarteschleife überträgt, wird die **eingehende Anrufquelle** als intern gemeldet.

## <a name="version-history"></a>Versionsverlauf
|Version  |Veröffentlichungsdatum     |Dateiname                                                           |Beschreibung                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.60     |22. Juli 2022      |CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit |Siehe:<br>Automatische CQD Teams-Telefonzentrale & Verlaufsberichte der Anrufwarteschleife – Ändern Log.docx in der heruntergeladenen ZIP-Datei für eine Liste der Änderungen                                                                             |
|1.00     |5. November 2020   |CQ und AA kombinierte Analytics 20201105.pbit                         |Erstveröffentlichung                                     |



