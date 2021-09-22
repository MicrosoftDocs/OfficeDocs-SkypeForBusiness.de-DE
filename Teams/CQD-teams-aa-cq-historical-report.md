---
title: Verwenden des CQD Power BI berichts zum Anzeigen automatische Telefonzentrale & Berichts zum Verlauf von Anrufen in der Anrufwarteschleife
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
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
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie den Power BI-Bericht „Anrufqualitäts-Dashboard“ verwenden, um Verlaufsdaten der automatischen Telefonzentrale und der Anrufwarteschleife anzuzeigen.
ms.openlocfilehash: 73ffd8e993a3dacd0412123d49e19c704df0cb8c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731384"
---
# <a name="what-are-the-requirements"></a>Welche sind die Anforderungen? 
Sie müssen Power BI Desktop installiert haben. Sie können es aus dem [Microsoft Windows Store](https://aka.ms/pbidesktopstore)installieren.

Sie können die kostenlose Version von Power BI Desktop verwenden. Die mindestens kompatible Version ist 2.85.681.0 (September 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Berechtigungen für den Zugriff auf die AQD-Pipeline
Das Konto, das Sie zum Anzeigen des Verlaufsberichts "AA- und CQ-Analysen" verwenden, muss über Berechtigungen für den Zugriff auf die AQD-Datenpipeline verfügen. Weitere Informationen finden Sie in der Zugriffsrolle für [AQD.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>Installation 
Bei den folgenden Schritten wird davon ausgegangen, dass Sie Power BI Desktop bereits auf dem Computer installiert haben und dass Ihr Konto über die erforderlichen Berechtigungen für den Zugriff auf die AQD-Datenpipeline verfügt.

Führen Sie die folgenden Schritte aus:
- Laden Sie die [Vorlage für Anrufwarteschleifen-Berichte](./aa-cq-cqd-historical-reports.md) Teams automatische Telefonzentrale & herunter, und speichern Sie sie in einem Verzeichnis auf Ihrem Computer.

- Doppelklicken Sie auf die Vorlage, Power BI Desktop starten soll.

- Sie werden aufgefordert, die AQD-Datenpipelineregion auszuwählen. Wählen Sie die Region aus, in der sich Ihr Mandant befindet.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot der Schaltfläche Anrufqualitäts-Dashboard im Teams Admin Center.":::

 - Sie können die Region mithilfe des PS-Skype for Business Online-CMdlets (Get-CsTenant) sehen. ServiceInstance-Ausgabe. 
 Die Region wird wie im folgenden Beispiel nach dem / angezeigt: 
 
   microsoftcommunicationsonline/noam-4a-s7 mit der Region noam.
   
 - Der Bericht wird mit Beispieldaten gestartet.
 
 - Um Ihre eigenen Daten zu sehen, klicken Sie auf **der** Registerkarte Start unter Abfragen in Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot der Schaltfläche Anrufqualitäts-Dashboard im Teams Admin Center.":::

- Anschließend werden Sie aufgefordert, sich anzumelden. Wählen Sie **Organisationskonto** und dann **Anmelden** aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot der Schaltfläche Anrufqualitäts-Dashboard im Teams Admin Center.":::

- Wählen Sie **Verbinden** aus, und beobachten Sie die Datenaktualisierung.

## <a name="data-latency-any-aa--cq-analytics"></a>Datenlatenz bei AA- & AQ-Analysen
Daten sind innerhalb von 30 Minuten in der AQD-Datenpipeline verfügbar.

Sie müssen die Daten aktualisieren, um die neuen Analysedaten anzuzeigen. 

## <a name="customization"></a>Anpassung 
Sie können bestimmte Visualisierungsaspekte der Berichte anpassen, z. B. Felder hinzufügen oder entfernen, die in den verschiedenen Visualisierungen angezeigt werden sollen, Ändern des Diagrammtyps usw.

Sie können nur die im Bericht bereitgestellten zusätzlichen Datenfelder hinzufügen.

### <a name="change-color-schema"></a>Farbschema ändern 
Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Installationsschritte bereits abgeschlossen haben.

Führen Sie die folgenden Schritte aus:
- Wählen Sie im Menüband **Registerkarte anzeigen** aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot der Schaltfläche Anrufqualitäts-Dashboard im Teams Admin Center.":::

- Wählen Sie in der Dropdownliste das Farbschema aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot der Schaltfläche Anrufqualitäts-Dashboard im Teams Admin Center.":::


## <a name="cqd-fields-description"></a>Beschreibung der CQD-Felder

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|automatische Telefonzentrale Identity                 |Zeichenfolge                   |Name des AA angefügten Ressourcenkontos<br>Beispiel: aa_test@microsoft.com|
|automatische Telefonzentrale Startzeit der Kette         |datetime                 |Anfangszeit der AA-Kette                    |
|automatische Telefonzentrale -Methode für die Verzeichnissuche  |Zeichenfolge                   |Suchmethode für das letzte Adressbuch        |
|automatische Telefonzentrale Übertragungsaktion          |Zeichenfolge                   |Zieltyp für Anrufübertragung<br>Mögliche Werte:<br>§ unbekannt – Entitätstyp wurde nicht angegeben<br>§ Benutzer – Benutzerentität<br>§ orgaa - Organizational automatische Telefonzentrale entity<br>§ hunt_group - Entität der Anrufwarteschleife<br>§ Anwendung – Entität der Sprachanwendung<br>§ external_pstn - externe PSTN-Entität<br>§ shared_voicemail – Entität für freigegebene Voicemails|
|automatische Telefonzentrale des Anrufergebniss              |Zeichenfolge                   |Anrufergebnis:<br>§ unbekannt – Der Anruf konnte nicht eingerichtet oder übertragen werden, und der Dienst hat keinen aussagekräftigen Fehlergrund erhalten <br>§ transferred_to_user – Anruf an einen Benutzer durch Namensanwahl/Durchwahl oder konfigurierte Menüoption übertragen <br>§ transferred_to_operator – Der Anruf wurde an einen konfigurierten Operator übertragen, z. B. wenn AA mit einem Operator für die Nachstunden konfiguriert ist. <br>§ failover_to_operator - Fallback to-Operator, wenn die Übertragung fehlschlägt oder die Namenserkennung nach drei Durchs dazu nicht funktioniert<br>§ user_terminated – Anrufer hat den Anruf beendet <br>§ service_declined – Anruf wurde vom Dienst abgelehnt. Dies könnte geschehen, wenn der Dienst die automatische Telefonzentrale kann <br>§ service_terminated - Der Back-End-Dienst hat den Aufruf beendet. Dies kann der Fall sein, wenn bei einer Übertragung an das Ziel ein Fehler auft,und kein Operator als Fallback konfiguriert ist. <br>§ failed_to_establish_media – Fehler bei Mediendateien zwischen Anrufer und Dienst <br>§ terminated_no_operator - Fehler bei der Namenserkennung nach drei Versuchen, und es wurde kein Operator konfiguriert <br>§ terminated_transfer_failed - Fehler beim Übertragen an das Ziel, und kein Operator ist konfiguriert <br>§ terminated_automatic_selection - Wenn keine Aktion während oder nach Stunden konfiguriert ist, wird der Aufruf standardmäßig beendet. <br>§ transferred_to_shared_voicemail – Anruf in freigegebene Voicemail übertragen, wenn er als Ziel konfiguriert ist <br>§ oaa_chain_too_long - Wenn eine automatische Telefonzentrale fünf automatische Telefonkonferenzen hintereinander überschreitet, wird der Aufruf beendet, um mögliche Anrufschleifen zu vermeiden. <br>§ oaa_session_too_long - Der Anruf hat die maximal zulässige Sitzungslänge überschritten und das Zeitüberschreitungs-Zeitüberschreitungen erreicht. |
|automatische Telefonzentrale Flow                |Zeichenfolge                   |Kapselt die verschiedenen Zustände automatische Telefonzentrale Aufrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ announcement|
|Ist automatische Telefonzentrale?              |Boolean                  |Gibt an, ob AA an dem Anruf beteiligt ist |
|automatische Telefonzentrale Caller Action Count      |int                      |Anzahl der verwendeten Aktion von Anrufer         |
|automatische Telefonzentrale Verkettungsdauer (Sekunden)   |int                      |Dauer des Anrufs in AA                 |
|Anrufergebnis der Anrufwarteschleife                  |String                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ error<br>§ declined<br>§ overflown<br>§ failed<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Aktion "Endzustand der Anrufwarteschleife"           |String                   |Letzte Aktion der Anrufwarteschleife<br>mögliche Werte:<br>§ forward<br>§ disconnect<br>§ voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other|
|Anrufwarteschleifenidentität                     |String                   |Name des an das AQ angefügten Ressourcenkontos<br>Beispiel: aa_test@microsoft.com|
|Anrufwarteschleife ist Konferenzmodus           |Boolean                  |Auf 1 festgelegt, wenn der Konferenzmodus für AQs aktiviert ist |
|Zieltyp der Anrufwarteschleife                  |String                   |Zieltyp der Anrufumleitung     |
|Von Anrufwarteschlangenidentität übertragen    |Boolean                  |Name des Ressourcenkontos, das an das AQ angefügt ist, von dem dieser Anruf übertragen wurde<br>Beispiel: aa_test@microsoft.com|
|Anzahl der Anrufwarteschleifen-Agenten           |int                      |Die Anzahl der Agents, die für diese Warteschlange zum Zeitpunkt des Anrufs verfügbar sind |
|Anzahl der Anrufwarteschleifen-Agenten                  |int                      |Die Anzahl der Agents, die dieser Warteschlange zum Zeitpunkt des Anrufs zugewiesen sind |
|Involvierte Anrufwarteschleife                  |Boolean                  |Wenn anrufwarteschleife an diesem Aufruf beteiligt ist, ist gleich 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensionen des PowerBI-Datenmodells

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA-Name                                   |Zeichenfolge                   |automatische Telefonzentrale (Ressourcenkonto-ID) |
|AACallFlow                              |Zeichenfolge                   |Kapselt die verschiedenen Zustände automatische Telefonzentrale Aufrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>Ankündigung |
|AACallResult                            |Zeichenfolge                   |Ergebnis eines automatische Telefonzentrale Anrufs:<br>§ unknown<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – Fehler bei der AA-Konfiguration<br>§ service_terminated – Interne AA-Fehler<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |Zeichenfolge                   |Dauer automatische Telefonzentrale Anrufs in Sekunden  |
|AACount                                 |Zeichenfolge                   |# of automatische Telefonzentrale involve in call         |
|AADirectorySearchMethod                 |Zeichenfolge                   |Suchmethode, die in einem Aufruf verwendet wird:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |Zeichenfolge                   |Anrufzeit in UTC                            |
|AATransferAction                        |Zeichenfolge                   |Anrufempfänger:<br>§ unbekannt – Entitätstyp wurde nicht angegeben<br>§ Benutzer – Benutzerentität<br>§ AA – Organisationseinheit automatische Telefonzentrale Entität<br>§ CQ – Entität der Anrufwarteschleife<br>§ Anwendung – Entität der Sprachanwendung<br>§ external_pstn - externe PSTN-Entität<br>§ shared_voicemail – Entität für freigegebene Voicemails      |
|PSTNMinutes                             |int                      |Minutennutzung gesamt                          |
|Anrufergebnis der Anrufwarteschleife                  |Zeichenfolge                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ error<br>§ declined<br>§ overflown<br>§ failed<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Anrufwarteschleifenidentität                     |Zeichenfolge                   |Name des an das AQ angefügten Ressourcenkontos     |
|Zieltyp der Anrufwarteschleife                  |Zeichenfolge                   |Erwartete Anrufumleitungszieltyp:<br>§ User<br>§ Anwendungsendpunkt<br>§ Other     |
|Anrufergebnis der Anrufwarteschleife                  |Zeichenfolge                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ error<br>§ declined<br>§ overflown<br>§ failed<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Aktion "Endzustand der Anrufwarteschleife"           |Zeichenfolge                   |Letzte Aktion der Anrufwarteschleife<br>mögliche Werte:<br>§ forward<br>§ disconnect<br>§ voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other             |
|Name des Agents                              |Zeichenfolge                   |Benutzer-UPN               |


### <a name="measures"></a>Kennzahlen

|Name                                      |Typ                       |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# der Aktion, die vom Benutzer in AA während des Anrufs ausgewählt wurde  |
|PSTNMinutes                             |int                      |Minutennutzung gesamt                                  |
|TotalCallCount                          |int                      |# der Anrufe                                          |
|Durchschnittliche Anrufdauer(Sekunden)         |int                      |Gesamtdauer von Anrufwarteschleifenanrufen in Sekunden     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI Diagrammbeschreibung automatische Telefonzentrale

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle des eingehenden Anrufs                    |Verteilung des Anrufs durch interne/externe Anrufquelle      |
|Verzeichnissuchmethoden gesamt          |Verteilung von Anrufen nach Suchtyp                         |
|Anruferaktion                           |Verteilung des Anrufs nach Anrufempfänger                       |
|Anrufergebnis                             |Verteilung des Anrufs nach endgültigem Anrufstatus                    |
|Anruferaktionsanzahl                     |Verteilung der während des Anrufs verwendeten Aktion "Anruf nach Nummer"  |


### <a name="call-queue"></a>Anrufwarteschleife

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle des eingehenden Anrufs                    |Verteilung des Anrufs durch interne/externe Anrufquelle         |
|Anruflautstärke                             |Verteilung des Anrufs nach Anrufwarteschleifen                            |
|Anruferergebnis                           |Verteilung des Anrufs nach Anrufergebnis                            |
|Aktion "Timeout/Überlaufanruf gesamt"      |Verteilung von NICHT weitergeleiteten (abgebrochenen) Anrufen nach Anrufergebnis   |
|Summen des Übertragungs-/Weiterleitungsziels          |Verteilung des weitergeleiteten Anrufs nach Anrufergebnis                  |
|Verhältnis abgebrochener Anrufe                   |Verhältnis der Anzahl erfolgreicher und abgebrochener Anrufe                    |
|Durchschnittliche Sitzungslänge (Sekunden)        |Anruflänge in Sekunden gruppiert nach abgebrochenen/erfolgreichen Anrufen   |



### <a name="agent-timeline"></a>Agent-Zeitachse

|Name                                                      |Beschreibung                            |
|:-------------------------------------------------------|:--------------------------------------|
|Anzahl Anrufe nach Agent                                        |Verteilung des Anrufs nach Anrufwarteschleife und Agent                 |
|Gesamtanrufdauer (Sekunden) nach Agent und Anrufwarteschleife   |Gesamtdauer (Sekunden) des Anrufs nach Agent und Anrufwarteschleife     |
|Durchschnittliche Anrufdauer (Sekunden) nach Name des Agents            |Durchschnittliche Dauer (Sekunden) des Anrufs nach Agent                  |



## <a name="known-issues"></a>Bekannte Probleme
- Aktuell zeigen Anrufwarteschleife und automatische Telefonant die Ressourcenkonto-ID anstelle der Namen der Anrufwarteschleife/automatischen Telefonant an.  Um den Ganzen Datenverkehr für eine automatische Telefon attendant oder Anrufwarteschleife zu zeigen, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefon attendant oder der Anrufwarteschleife zugewiesen sind.

- Derzeit steht im Dashboard nur ein Verlauf von 28 Tagen zur Verfügung, da Anrufwarteschleifen-/automatische Telefoniedaten als identifizierbare Informationen für Endbenutzer betrachtet werden und den Datenschutzrichtlinien unterliegen.
