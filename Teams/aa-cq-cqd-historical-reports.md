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
ms.openlocfilehash: d3c8bd7181bab9ee7c199aedbac8a6fcc4c78d75
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121543"
---
# <a name="auto-attendant--call-queue-historical-report"></a>automatische Telefonzentrale & eines Anrufwarteschlangen-Verlaufsberichts

Die Vorlage für Teams automatische Telefonzentrale & Anrufwarteschleifen-Verlaufsbericht Power BI die folgenden drei Berichte:

- automatische Telefonzentrale – Zeigt Analysen für Anrufe an, die in Ihre automatischen Telefon attendants eins gehen.
- Anrufwarteschleife – Zeigt Analysen für Anrufe an, die in Ihre Anrufwarteschleifen kommen.
- Agent-Zeitachse – Zeigt eine Zeitachsenansicht der Agents an, die an Anrufen in der Anrufwarteschleife aktiv sind.

Diese Berichte verwenden [](CQD-Power-BI-query-templates.md) Daten aus dem Datenspeicher für das Anrufqualitätsdashboard und ermöglichen es Organisationen, über die Anzahl der Anrufe, die von automatischen Telefonkonferenzen und Anrufwarteschleifen verarbeitet werden, sowie die Leistung des Agents in den Anrufwarteschleifen zu melden.

## <a name="what-are-the-requirements"></a>Welche Anforderungen gelten? 

Sie müssen ihre Power BI Desktop haben. Sie können sie über den [Microsoft-Windows Store](https://aka.ms/pbidesktopstore)installieren.

Sie können die kostenlose Version von Power BI Desktop. Die kompatible Mindestversion ist 2.85.681.0 (September 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Berechtigungen für den Zugriff auf die CQD-Pipeline

Das Konto, das Sie zum Anzeigen des AA-Berichts & CQ Analytics-Verlauf verwenden, muss über Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügen. Weitere Informationen finden Sie in der Zugriffsrolle für [AQD.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>Installation 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Power BI Desktop auf dem Computer installiert haben und dass Ihr Konto über die erforderlichen Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügt.

Führen Sie die folgenden Schritte aus:

- Laden Sie [das AQD Power BI Abfragevorlagen herunter,](https://www.microsoft.com/download/details.aspx?id=102291) und speichern Sie die ZIP-Datei in einem Verzeichnis auf Ihrem Computer.

- Doppelklicken Sie auf die ZIP-Datei, um sie zu öffnen.

- Doppelklicken Sie auf die Vorlagendatei "Kombinierte AQ- und AA-Analysen 20201105.pbit", und Power BI Desktop starten.

- Sie werden aufgefordert, den Bereich für die CQD-Datenpipeline auszuwählen. Wählen Sie die Region aus, in der sich Ihr Mandant befindet.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot der Auswahl der Region für die CQD-Datenpipeline":::

 - Sie können die Region mithilfe des Skype for Business Online-PowerShell-Cmdlets (Get-CsTenant) sehen. ServiceInstance-Ausgabe. 
 Die Region wird wie im folgenden Beispiel nach dem / angezeigt:

   microsoftcommunicationsonline/noam-4a-s7 mit der Region noam.
 
 - Der Bericht wird mit Beispieldaten gestartet.
 
 - Um Ihre eigenen Daten zu sehen, klicken Sie auf **der** Registerkarte Start unter Abfragen in Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot mit Auswahl der Aktualisierungsoption":::

- Sie werden dann aufgefordert, sich anmelden. Wählen **Sie Organisationskonto** und dann **Anmelden aus.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot showing login":::

- Wählen Sie **Verbinden** aus, und beobachten Sie die Datenaktualisierung.

## <a name="data-latency-and-aa--cq-analytics"></a>Datenlatenz und AA-& AQ-Analysen

Die Daten sind innerhalb von 30 Minuten in der CQD-Datenpipeline verfügbar.

Sie müssen die Daten aktualisieren, um die neuen Analysedaten zu sehen. 

## <a name="customization"></a>Anpassung 

Sie können bestimmte Visualisierungsaspekte der Berichte anpassen, z. B. Felder hinzufügen oder entfernen, die in den verschiedenen Visualisierungen angezeigt werden sollen, Ändern des Diagrammtyps usw.

Sie können keine weiteren Datenfelder als die im Bericht bereitgestellten hinzufügen.

### <a name="change-color-schema"></a>Ändern des Farbschemas 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Installationsschritte bereits abgeschlossen haben.

Führen Sie die folgenden Schritte aus:
- Wählen **Sie im Menüband die** Registerkarte Ansicht aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot, in dem die Registerkarte "Ansicht" zum Ändern des Farbschemas ausgewählt wird":::

- Wählen Sie das Farbschema aus der Dropdownliste aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot mit verschiedenen Farbschemas":::

## <a name="cqd-fields-description"></a>Beschreibung der CQD-Felder

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|automatische Telefonzentrale Identity                 |Zeichenfolge                   |Name des AA angefügten Ressourcenkontos<br>Beispiel: aa_test@microsoft.com|
|automatische Telefonzentrale Startzeit der Kette         |datetime                 |Anfangszeit der AA-Kette                    |
|automatische Telefonzentrale -Methode für die Verzeichnissuche  |Zeichenfolge                   |Suchmethode für das letzte Adressbuch        |
|automatische Telefonzentrale Übertragungsaktion          |Zeichenfolge                   |Zieltyp für Anrufübertragung<br>mögliche Werte:<br>§ unbekannt – Entitätstyp wurde nicht angegeben<br>§ Benutzer – Benutzerentität<br>§ orgaa - Organizational automatische Telefonzentrale entity<br>§ hunt_group - Entität der Anrufwarteschleife<br>§ Anwendung – Entität der Sprachanwendung<br>§ external_pstn - externe PSTN-Entität<br>§ shared_voicemail – Entität für freigegebene Voicemails|
|automatische Telefonzentrale des Anrufergebniss              |Zeichenfolge                   |Anrufergebnis:<br>§ unbekannt<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|automatische Telefonzentrale Flow                |Zeichenfolge                   |Kapselt die verschiedenen Zustände automatische Telefonzentrale Aufrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ Ankündigung|
|Ist automatische Telefonzentrale?              |Boolean                  |Gibt an, ob AA an dem Anruf beteiligt ist |
|automatische Telefonzentrale Caller Action Count      |int                      |Anzahl der verwendeten Aktion von Anrufer         |
|automatische Telefonzentrale Verkettungsdauer (Sekunden)   |int                      |Dauer des Anrufs in AA                 |
|Anrufwarteschleifen-Anrufergebnis                  |String                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ Überlauf<br>§ fehlgeschlagen<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Aktion zum endgültigen Status einer Anrufwarteschleife           |String                   |Letzte Aktion der Anrufwarteschleife<br>mögliche Werte:<br>§ weiterleiten<br>§ trennen<br>§ Voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ Sonstiges|
|Anrufwarteschlangenidentität                     |String                   |Name des an das AQ angefügten Ressourcenkontos<br>Beispiel: aa_test@microsoft.com|
|Anrufwarteschleife ist Konferenzmodus           |Boolean                  |Auf 1 festgelegt, wenn der Konferenzmodus für AQs aktiviert ist |
|Zieltyp der Anrufwarteschleife                  |String                   |Zieltyp der Anrufumleitung     |
|Von Anrufwarteschlangenidentität übertragen    |Boolean                  |Name des Ressourcenkontos, das an das AQ angefügt ist, von dem dieser Anruf übertragen wurde<br>Beispiel: aa_test@microsoft.com|
|Anzahl der Anrufwarteschleifen-Agenten           |int                      |Die Anzahl der Agents, die für diese Warteschlange zum Zeitpunkt des Anrufs verfügbar sind |
|Anzahl der Anrufwarteschleifen-Agenten                  |int                      |Die Anzahl der Agents, die dieser Warteschlange zum Zeitpunkt des Anrufs zugewiesen sind |
|Involvierte Anrufwarteschleife                  |Boolean                  |Wenn anrufwarteschleife an diesem Aufruf beteiligt ist, ist gleich 1 |


### <a name="power-bi-data-model-dimensions"></a>Power BI von Datenmodellabmessungen

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA-Name                                   |Zeichenfolge                   |automatische Telefonzentrale (Ressourcenkonto-ID) |
|AACallFlow                              |Zeichenfolge                   |Kapselt die verschiedenen Zustände automatische Telefonzentrale Aufrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ Ankündigung |
|AACallResult                            |Zeichenfolge                   |Ergebnis eines automatische Telefonzentrale Anrufs:<br>§ unbekannt<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – Fehler bei der AA-Konfiguration<br>§ service_terminated – interne AA-Fehler<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |Zeichenfolge                   |Dauer automatische Telefonzentrale Anrufs in Sekunden  |
|AACount                                 |Zeichenfolge                   |# of automatische Telefonzentrale involve in call         |
|AADirectorySearchMethod                 |Zeichenfolge                   |Suchmethode, die in einem Aufruf verwendet wird:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |Zeichenfolge                   |Anrufzeit in UTC      |
|AATransferAction                        |Zeichenfolge                   |Anrufempfänger:<br>§ unbekannt – Entitätstyp wurde nicht angegeben<br>§ Benutzer – Benutzerentität<br>§ AA – Organisationseinheit automatische Telefonzentrale Entität<br>§ CQ – Entität der Anrufwarteschleife<br>§ Anwendung – Entität der Sprachanwendung<br>§ external_pstn - externe PSTN-Entität<br>§ shared_voicemail – Entität für freigegebene Voicemails      |
|PSTNMinutes                             |int                      |Gesamtminutenverwendung                          |
|Anrufwarteschleifen-Anrufergebnis                  |Zeichenfolge                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ Überlauf<br>§ fehlgeschlagen<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Anrufwarteschlangenidentität                     |Zeichenfolge                   |Name des an das AQ angefügten Ressourcenkontos     |
|Zieltyp der Anrufwarteschleife                  |Zeichenfolge                   |Erwartete Anrufumleitungszieltyp:<br>§ Benutzer<br>§ Anwendungsendpunkt<br>§ Andere     |
|Anrufwarteschleifen-Anrufergebnis                  |Zeichenfolge                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ Überlauf<br>§ fehlgeschlagen<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|Aktion zum endgültigen Status einer Anrufwarteschleife           |Zeichenfolge                   |Letzte Aktion der Anrufwarteschleife<br>mögliche Werte:<br>§ weiterleiten<br>§ trennen<br>§ Voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ Sonstiges             |
|Name des Mitarbeiters                              |Zeichenfolge                   |Benutzer-UPN               |


### <a name="measures"></a>Kennzahlen

|Name                                      |Typ                       |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# der Aktion, die vom Benutzer in AA während des Anrufs ausgewählt wurde  |
|PSTNMinutes                             |int                      |Gesamtminutenverwendung                                  |
|TotalCallCount                          |int                      |# der Anrufe                                          |
|Durchschnittliche Anrufdauer(Sekunden)         |int                      |Gesamtdauer von Anrufwarteschleifenanrufen in Sekunden     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI Diagrammbeschreibung automatische Telefonzentrale

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle für eingehenden Anruf                    |Verteilung des Anrufs durch interne/externe<sup>Anrufquelle 1</sup>|
|Summen der Verzeichnissuchmethode          |Verteilung von Anrufen nach Suchtyp                         |
|Anruferaktion                           |Verteilung des Anrufs nach Anrufempfänger                       |
|Anrufergebnis                             |Verteilung des Anrufs nach endgültigem Anrufstatus                    |
|Anzahl der Anrufer-Aktionen                     |Verteilung der während des Anrufs verwendeten Aktion "Anruf nach Nummer"  |


### <a name="call-queue"></a>Anrufwarteschleife

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle für eingehenden Anruf                    |Verteilung des Anrufs durch interne/externe<sup>Anrufquelle 1</sup>   |
|Anruflautstärke                             |Verteilung von Anrufen nach Anrufwarteschleifen                            |
|Anruferergebnis                           |Verteilung des Anrufs nach Anrufergebnis                            |
|Aktion "Timeout/Überlaufaufruf Gesamt"      |Verteilung des NICHT weitergeleiteten(abgebrochenen) Anrufs nach Anrufergebnis   |
|Gesamtübertragungsziel für Übertragung/Weiterleitung          |Verteilung des nach Anrufergebnis weitergeleiteten Anrufs                  |
|Verhältnis für abgebrochene Anrufe                   |Verhältnis von erfolgreichem zu abgebrochener Anrufanzahl                    |
|Durchschnittliche Sitzungslänge (Sekunden)        |Anruflänge in Sekunden nach abgebrochenen/erfolgreichen Anrufen   |



### <a name="agent-timeline"></a>Agent-Zeitachse

|Name                                                      |Beschreibung                            |
|:-------------------------------------------------------|:--------------------------------------|
|# Anrufe nach Mitarbeiter                                        |Verteilung von Anrufen nach Anrufwarteschleife und Agent                 |
|Gesamtanrufdauer (Sekunden) nach Agent und Anrufwarteschleife   |Gesamtdauer (Sekunden) des Anrufs nach Agent und Anrufwarteschleife     |
|Durchschnittliche Anrufdauer (Sekunden) nach Agentname            |Durchschnittliche Dauer (Sekunden) des Anrufs nach Agent                  |



## <a name="known-issues"></a>Bekannte Probleme

- Anrufwarteschleife und automatische Telefonkonferenzen werden nach der ID des Ressourcenkontos anstelle der Namen von Anrufwarteschleife/automatischer Telefonant angezeigt.  Um den Ganzen Datenverkehr für eine automatische Telefon attendant oder Anrufwarteschleife zu zeigen, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefonkonferenz oder der Anrufwarteschleife zugewiesen sind.

- Der Verlauf von nur 28 Tagen steht im Dashboard zur Verfügung, da Anrufwarteschleifen-/automatische Telefonkonferenzdaten als personenbezogene Informationen für Endbenutzer betrachtet werden und den Aufbewahrungsrichtlinien für den Datenschutz unterliegen.

- <sup>1</sup> **Die Quelle eingehender** Anrufe in der automatischen Telefon attendant und die Diagrammen "Anrufwarteschleife" zeigen die endgültige Quelle der Anrufwarteschleife und nicht die Quelle des anfänglichen Anrufs. Wenn beispielsweise eine automatische Telefonkonferenz einen externen Anruf erhält und den Anruf an  eine andere automatische Telefonkonferenz oder Anrufwarteschleife überträgt, wird die eingehende Anrufquelle als Intern angezeigt.
