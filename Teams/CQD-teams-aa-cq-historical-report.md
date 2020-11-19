---
title: Verwenden des CQD Power BI-Berichts zum Anzeigen der automatischen Telefonzentrale & Verlaufsbericht zur Anrufwarteschlange
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie den Power BI-Bericht "Anrufqualität" verwenden, um automatische Telefonzentrale und Verlaufsdaten der Anrufwarteschlange anzuzeigen.
ms.openlocfilehash: 16f8682e8f1bc444e2694a0586ff21cf442288cd
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130426"
---
# <a name="what-are-the-requirements"></a>Was sind die Voraussetzungen? 
Sie müssen Power BI Desktop installiert haben. Sie können es über den [Microsoft Windows Store](https://aka.ms/pbidesktopstore)installieren.

Sie können die ﻿kostenlose Version von Power BI Desktop verwenden. Die Mindest-kompatible Version ist 2.85.681.0 (September 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Berechtigungen für den Zugriff auf die CQD-Pipeline
Das Konto, das Sie zum Anzeigen des Verlaufsberichts AA & CQ Analytics verwenden, muss über Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügen. Weitere Informationen finden Sie in der [CQD-Access-Rolle](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) .

## <a name="installation"></a>Installation 
Bei den folgenden Schritten wird davon ausgegangen, dass Sie Power BI Desktop bereits auf dem Computer installiert haben und dass Ihr Konto über die erforderlichen Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügt.

Führen Sie die folgenden Schritte aus:
- Laden Sie die [CQD Teams-automatische Telefonzentrale & Anrufwarteschlange-Verlaufsberichts Vorlage](https://aka.ms/TAPAACQAnalytics) herunter, und speichern Sie Sie in einem Verzeichnis auf Ihrem Computer.

- Doppelklicken Sie auf die Vorlage, und der Power BI-Desktop sollte gestartet werden.

- Sie werden aufgefordert, den CQD-Datenpipeline Bereich auszuwählen. Wählen Sie den Bereich aus, in dem sich der Mandant befindet.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot der Schaltfläche "Anrufqualität" im Team Admin Center":::

 - Sie können die Region mit dem Skype for Business Online PS-Cmdlet (Get-CsTenant) anzeigen. ServiceInstance-Ausgabe. 
 Der Bereich wird nach dem/like in diesem Beispiel angezeigt: 
 
   microsoftcommunicationsonline/Noam-4a-S7, wobei die Region Noam ist.
   
 - Der Bericht wird mit Beispieldaten gestartet.
 
 - Wenn Sie Ihre eigenen Daten anzeigen möchten, klicken Sie auf der Registerkarte Start Unterabfragen in Power BI Desktop auf **Aktualisieren** .

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot der Schaltfläche "Anrufqualität" im Team Admin Center":::

- Sie werden dann zur Anmeldung aufgefordert. Wählen Sie **organisationskonto** aus, und wählen Sie dann **Anmelden** aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot der Schaltfläche "Anrufqualität" im Team Admin Center":::

- Wählen Sie **verbinden** aus, und überwachen Sie die Datenaktualisierung.

## <a name="data-latency-any-aa--cq-analytics"></a>Datenlatenz alle AA-& CQ-Analysen
Daten werden innerhalb von 30 Minuten in der CQD-Datenpipeline zur Verfügung stehen.

Sie müssen die Daten aktualisieren, damit die neuen Analyse Daten angezeigt werden. 

## <a name="customization"></a>Anpassung 
Sie können bestimmte Visualisierungs Aspekte der Berichte anpassen, beispielsweise das Hinzufügen oder Entfernen von Feldern, die in den verschiedenen Visualisierungen angezeigt werden sollen, Ändern des Diagrammtyps usw.

Sie können keine weiteren Datenfelder hinzufügen, die nicht im Bericht angegeben sind.

### <a name="change-color-schema"></a>Ändern des Farbschemas 
Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Installationsschritte bereits abgeschlossen haben.

Führen Sie die folgenden Schritte aus:
- Wählen Sie im Menüband die **Registerkarte Ansicht** aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot der Schaltfläche "Anrufqualität" im Team Admin Center":::

- Wählen Sie das Farbschema aus der Dropdownliste aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot der Schaltfläche "Anrufqualität" im Team Admin Center":::


## <a name="cqd-fields-description"></a>Beschreibung der CQD-Felder

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identität der automatischen Telefonzentrale                 |Zeichenfolge                   |Name des an AA angefügten Ressourcenkontos<br>Beispiel: aa_test@Microsoft.com|
|Anfangszeit der automatischen Telefonzentrale         |datetime                 |Anfangszeit der AA-Kette                    |
|Verzeichnis Suchmethode für die automatische Telefonzentrale  |Zeichenfolge                   |Suchmethode für das letzte Adressbuch        |
|Übertragungs Aktion für automatische Telefonzentrale          |Zeichenfolge                   |Zieltyp der Anrufübertragung<br>Mögliche Werte:<br>§ unbekannt-Entitätstyp wurde nicht angegeben<br>§ Benutzer-Benutzer-Entität<br>§ orgaa-Entität "organisatorische automatische Telefonzentrale"<br>§ hunt_group-Anruf Warteschlangen Entität<br>§ Anwendung-Voice Application Entity<br>§ external_pstn-externes PSTN-Element<br>§ shared_voicemail-freigegebene Voicemail-Entität|
|Anruf Ergebnis der automatischen Telefonzentrale              |Zeichenfolge                   |Anruf Ergebnis:<br>§ unbekannt<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Anruffluss der automatischen Telefonzentrale                |Zeichenfolge                   |Kapselt die verschiedenen Zustände des automatischen Telefonzentralen Anrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ Bekanntmachung|
|Ist die automatische Telefonzentrale beteiligt              |Boolean                  |Angezeigt, wenn AA an dem Anruf beteiligt ist |
|Anzahl der Rufnummernanzeige für die automatische Telefonzentrale      |int                      |Anzahl der verwendeten Aktion durch den Anrufer         |
|Sekunden für die automatische Telefonzentrale-Ketten Dauer   |int                      |Dauer des Anrufs in AA                 |
|Ergebnis des Anruf Warteschlangen Anrufs                  |String                   |Endgültiger Zustand der Anrufwarteschlange<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ übergelaufen<br>§ fehlerhaft<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Letzte Status Aktion der Anrufwarteschlange           |String                   |Letzte Aktion der Anrufwarteschlange<br>mögliche Werte:<br>§ weiterleiten<br>§ Trennen<br>§ Voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ Sonstiges|
|Identität der Anrufwarteschlange                     |String                   |Name des an CQ angeschlossenen Ressourcenkontos<br>Beispiel: aa_test@Microsoft.com|
|Anrufwarteschlange ist Konferenzmodus           |Boolean                  |Auf 1 setzen, wenn der Konferenzmodus auf CQ aktiviert ist |
|Zieltyp der Anrufwarteschlange                  |String                   |Erwarteter Zieltyp der Anrufumleitung     |
|Von der Anruf Warteschlangenidentität übertragen    |Boolean                  |Name des dem CQ zugeordneten Ressourcenkontos, aus dem dieser Anruf übertragen wurde<br>Beispiel: aa_test@Microsoft.com|
|Anruf Warteschlangen-Agent wählen Sie Anzahl aus.           |int                      |Anzahl der für diese Warteschlange verfügbaren Agents zum Zeitpunkt des Anrufs |
|Anzahl der Anruf Warteschlangen-Agents                  |int                      |Anzahl der Agents, die dieser Warteschlange zum Zeitpunkt des Anrufs zugeordnet sind |
|Ist die Anrufwarteschlange involviert                  |Boolean                  |Wenn die Anrufwarteschlange in diesen Aufruf gleich 1 involviert ist |


### <a name="powerbi-data-model-dimensions"></a>PowerBI-Datenmodell Dimensionen

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA-Name                                   |Zeichenfolge                   |Automatische Telefonzentrale-ID (Ressourcenkonto-ID) |
|AACallFlow                              |Zeichenfolge                   |Kapselt die verschiedenen Zustände des automatischen Telefonzentralen Anrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>Ankündigung |
|AACallResult                            |Zeichenfolge                   |Ergebnis des Anrufs einer automatischen Telefonzentrale:<br>§ unbekannt<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – Fehler der AA-Konfiguration<br>§ service_terminated – interne AA-Fehler<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |Zeichenfolge                   |Dauer des Anrufs der automatischen Telefonzentrale in Sekunden  |
|AACount                                 |Zeichenfolge                   |# der automatischen Telefonzentrale beinhaltet einen Anruf         |
|AADirectorySearchMethod                 |Zeichenfolge                   |In Call verwendete Suchmethode:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |Zeichenfolge                   |Anrufzeiten in UTC                            |
|AATransferAction                        |Zeichenfolge                   |Empfänger des Anrufs:<br>§ unbekannt-Entitätstyp wurde nicht angegeben<br>§ Benutzer-Benutzer-Entität<br>§ AA – Organisation der automatischen Telefonzentrale<br>§ CQ-Anruf Warteschlangen Entität<br>§ Anwendung-Voice Application Entity<br>§ external_pstn-externes PSTN-Element<br>§ shared_voicemail-freigegebene Voicemail-Entität      |
|PSTNMinutes                             |int                      |Gesamt Minuten Verbrauch                          |
|Ergebnis des Anruf Warteschlangen Anrufs                  |Zeichenfolge                   |Endgültiger Zustand der Anrufwarteschlange<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ übergelaufen<br>§ fehlerhaft<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identität der Anrufwarteschlange                     |Zeichenfolge                   |Name des an CQ angeschlossenen Ressourcenkontos     |
|Zieltyp der Anrufwarteschlange                  |Zeichenfolge                   |Erwarteter Zieltyp der Anrufumleitung:<br>§ Nutzer<br>§ Anwendungsendpunkt<br>§ Sonstiges     |
|Ergebnis des Anruf Warteschlangen Anrufs                  |Zeichenfolge                   |Endgültiger Zustand der Anrufwarteschlange<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ übergelaufen<br>§ fehlerhaft<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Letzte Status Aktion der Anrufwarteschlange           |Zeichenfolge                   |Letzte Aktion der Anrufwarteschlange<br>mögliche Werte:<br>§ weiterleiten<br>§ Trennen<br>§ Voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ Sonstiges             |
|Name des Agents                              |Zeichenfolge                   |Benutzer-UPN               |


### <a name="measures"></a>Kennzahlen

|Name                                      |Typ                       |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |die vom Benutzer in AA während des Anrufs ausgewählte Aktion  |
|PSTNMinutes                             |int                      |Gesamt Minuten Verbrauch                                  |
|TotalCallCount                          |int                      |Anzahl von Anrufen                                          |
|Durchschnittliche Anrufdauer (Sekunden)         |int                      |Gesamtdauer der Anruf Warteschlangen Anrufe in Sekunden     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI Graph Description, automatische Telefonzentrale

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle für eingehende Anrufe                    |Verteilung des Anrufs nach interner/externer Anruf Quelle      |
|Ergebnisse der Verzeichnis Suchmethode          |Verteilung des Anrufs nach Suchtyp                         |
|Aktion für Anrufer                           |Verteilung des Anrufs per Anrufempfänger                       |
|Anruf Ergebnis                             |Verteilung des Anrufs nach dem endgültigen Anruf Zustand                    |
|Anzahl der Rufnummernanzeige                     |Verteilung der während des Anrufs verwendeten Aktion "Anruf nach Nummer"  |


### <a name="call-queue"></a>Anrufwarteschlange

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle für eingehende Anrufe                    |Verteilung des Anrufs nach interner/externer Anruf Quelle         |
|Anruflautstärke                             |Verteilung von Anrufen über Anrufwarteschlangen                            |
|Ergebnis des Anrufers                           |Verteilung des Anruf Ergebnisses                            |
|Timeout/Überlauf Anruf Gesamtaktion      |Verteilung des Anrufs von nicht weitergeleiteten (aufgegebenen) anrufen durch Anruf Ergebnis   |
|Ziel Gesamtwerte übertragen/weiterleiten          |Verteilung des Anrufs weitergeleitet durch Anruf Ergebnis                  |
|Verhältnis für verlassene Anrufe                   |Verhältnis der erfolgreichen zur aufgegebenen Anzahl von Anrufen                    |
|Durchschnittliche Sitzungsdauer (Sekunden)        |Anruflänge in Sekunden, gruppiert nach verlassenen/erfolgreichen anrufen   |



### <a name="agent-timeline"></a>Agent-Zeitachse

|Name                                                      |Beschreibung                            |
|:-------------------------------------------------------|:--------------------------------------|
|# Anrufe nach Agenten                                        |Verteilung des Anrufs nach Anrufwarteschlange und-Agent                 |
|Gesamtdauer des Anrufs (Sekunden) nach Agent und Anrufwarteschlange   |Gesamtdauer (Sekunden) des Anrufs nach Agent und Anrufwarteschlange     |
|Durchschnittliche Anrufdauer (Sekunden) nach Agenten Name            |Durchschnittliche Dauer (Sekunden) des Anrufs nach Agent                  |



## <a name="known-issues"></a>Bekannte Probleme
- Derzeit zeigen die Anrufwarteschlange und die automatische Telefonzentrale anstelle der Namen der Anrufwarteschlange/der automatischen Telefonzentrale eine Ressourcenkonten-ID an.  Wenn Sie den gesamten Datenverkehr für eine automatische Telefonzentrale oder eine Anrufwarteschlange anzeigen möchten, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefonzentrale oder der Anrufwarteschlange zugewiesen sind.

- Derzeit sind im Dashboard nur 28 Tage Protokoll verfügbar, da die Daten für die Anrufwarteschlange/automatische Telefonzentrale als Endbenutzer identifizierbare Informationen gelten und den Datenschutzrichtlinien unterliegen.
