---
title: Verwenden des CQD Power BI-Berichts zum Anzeigen automatische Telefonzentrale & Verlaufsberichts der Anrufwarteschlange
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
description: Erfahren Sie, wie Sie den Power BI-Bericht "Anrufqualitätsdashboard" verwenden, um automatische Telefonzentrale und Verlaufsdaten der Anrufwarteschlange anzuzeigen.
ms.openlocfilehash: cfd72d0397407205aef729188c630e99148f154c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111511"
---
# <a name="what-are-the-requirements"></a>Welche Anforderungen gelten? 
Power BI Desktop muss installiert sein. Sie können sie aus dem [Microsoft Windows Store installieren.](https://aka.ms/pbidesktopstore)

Sie können die kostenlose Version von Power BI Desktop verwenden. Die mindestens kompatible Version ist 2.85.681.0 (September 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Berechtigungen für den Zugriff auf die CQD-Pipeline
Das Konto, das Sie zum Anzeigen des & CQ Analytics-Verlaufsberichts verwenden, muss über Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügen. Weitere Informationen finden Sie in der [CQD-Zugriffsrolle.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>Installation 
Die folgenden Schritte gehen davon aus, dass Sie Power BI Desktop bereits auf dem Computer installiert haben und dass Ihr Konto über die erforderlichen Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügt.

Führen Sie die folgenden Schritte aus:
- Laden Sie [die Vorlage "CQD Teams automatische Telefonzentrale & Anrufwarteschlange : Verlaufsbericht" herunter,](./aa-cq-cqd-historical-reports.md) und speichern Sie sie in einem Verzeichnis auf Ihrem Computer.

- Doppelklicken Sie auf die Vorlage, und Power BI Desktop sollte gestartet werden.

- Sie werden aufgefordert, den CQD-Datenpipelinebereich auszuwählen. Wählen Sie die Region aus, in der sich Ihr Mandant befindet.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot der Schaltfläche "Anrufqualitätsdashboard" im Teams Admin Center":::

 - Sie können die Region mit dem Skype for Business Online PS-Cmdlet (Get-CsTenant) sehen. ServiceInstance-Ausgabe. 
 Der Bereich wird nach dem /wie in diesem Beispiel angezeigt: 
 
   microsoftcommunicationsonline/noam-4a-s7, in dem die Region noam ist.
   
 - Der Bericht wird mit Beispieldaten gestartet.
 
 - Wenn Sie Ihre eigenen  Daten anzeigen, klicken Sie auf der Registerkarte Start unter Abfragen in Power BI Desktop auf Aktualisieren.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot der Schaltfläche "Anrufqualitätsdashboard" im Teams Admin Center":::

- Sie werden dann aufgefordert, sich zu melden. Wählen **Sie Organisationskonto** und dann **Anmelden aus.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot der Schaltfläche "Anrufqualitätsdashboard" im Teams Admin Center":::

- Wählen **Sie Verbinden** aus, und schauen Sie sich die Datenaktualisierung an.

## <a name="data-latency-any-aa--cq-analytics"></a>Datenlatenz Alle AA- & CQ-Analysen
Daten sind innerhalb von 30 Minuten in der CQD-Datenpipeline verfügbar.

Sie müssen die Daten aktualisieren, um die neuen Analysedaten sehen zu können. 

## <a name="customization"></a>Anpassung 
Sie können bestimmte Visualisierungsaspekte der Berichte anpassen, z. B. Das Hinzufügen oder Entfernen von Feldern, die in den verschiedenen Visualisierungen angezeigt werden sollen, das Ändern des Diagrammtyps usw.

Sie können keine weiteren Datenfelder als die im Bericht angegebenen hinzufügen.

### <a name="change-color-schema"></a>Ändern des Farbschemas 
Die folgenden Schritte gehen davon aus, dass Sie die Installationsschritte bereits abgeschlossen haben.

Führen Sie die folgenden Schritte aus:
- Wählen **Sie im Menüband die** Registerkarte Ansicht aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot der Schaltfläche "Anrufqualitätsdashboard" im Teams Admin Center":::

- Wählen Sie das Farbschema aus der Dropdownliste aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot der Schaltfläche "Anrufqualitätsdashboard" im Teams Admin Center":::


## <a name="cqd-fields-description"></a>Beschreibung von CQD-Feldern

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|automatische Telefonzentrale Identität                 |Zeichenfolge                   |Name des an AA angefügten Ressourcenkontos<br>Beispiel: aa_test@microsoft.com|
|automatische Telefonzentrale Startzeit der Kette         |datetime                 |Startzeit der AA-Kette                    |
|automatische Telefonzentrale Directory Search Method  |Zeichenfolge                   |Suchmethode für das letzte Adressbuch        |
|automatische Telefonzentrale Übertragungsaktion          |Zeichenfolge                   |Anrufübertragungszieltyp<br>Mögliche Werte:<br>§ unbekannt – Entitätstyp wurde nicht angegeben<br>§ Benutzer – Benutzerentität<br>§ orgaa – Organisations- automatische Telefonzentrale Entität<br>§ hunt_group – Entität "Anrufwarteschlange"<br>§ Anwendung – Sprachanwendungsentität<br>§ external_pstn - externe PSTN-Entität<br>§ shared_voicemail – freigegebene Voicemailentität|
|automatische Telefonzentrale Anrufergebnis              |Zeichenfolge                   |Anrufergebnis:<br>§ unbekannt<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|automatische Telefonzentrale Anruffluss                |Zeichenfolge                   |Kapselt die verschiedenen Zustände automatische Telefonzentrale Anrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>Ankündigung von §|
|Ist automatische Telefonzentrale beteiligt              |Boolean                  |Angegeben, wenn AA an dem Anruf beteiligt ist |
|automatische Telefonzentrale Anzahl der Anruferaktion      |int                      |Anzahl der vom Anrufer verwendeten Aktionen         |
|automatische Telefonzentrale Chain Duration Seconds   |int                      |Anrufdauer in AA                 |
|Anrufergebnis der Anrufwarteschlange                  |String                   |Anrufwarteschlange anruft den enden Zustand<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ überlaufen<br>§ fehlgeschlagen<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Aktion zum endgültigen Status der Anrufwarteschlange           |String                   |Letzte Aktion der Anrufwarteschlange<br>mögliche Werte:<br>§ weiterleiten<br>§ Trennen<br>§ Voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ sonstige|
|Anrufwarteschlangeidentität                     |String                   |Name des Ressourcenkontos, das an CQ angefügt ist<br>Beispiel: aa_test@microsoft.com|
|Anrufwarteschlange ist Konferenzmodus           |Boolean                  |Auf 1 festgelegt, wenn der Konferenzmodus für CQ aktiviert ist |
|Zieltyp der Anrufwarteschlange                  |String                   |Zieltyp der erwarteten Anrufumleitung     |
|Aus Der Anrufwarteschlange übertragene Identität    |Boolean                  |Name des Ressourcenkontos, das an CQ angefügt ist, von dem dieser Aufruf übertragen wurde<br>Beispiel: aa_test@microsoft.com|
|Call Queue Agent Opt In Count           |int                      |Anzahl der Agents, die für diese Warteschlange zum Zeitpunkt des Anrufs verfügbar sind |
|Anzahl der Anrufwarteschlangenmitarbeiter                  |int                      |Anzahl der Agents, die dieser Warteschlange zum Zeitpunkt des Anrufs zugewiesen sind |
|Ist Anrufwarteschlange involviert                  |Boolean                  |Wenn anrufwarteschlange an diesem Anruf gleich 1 beteiligt ist |


### <a name="powerbi-data-model-dimensions"></a>Dimensionen des PowerBI-Datenmodells

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA-Name                                   |Zeichenfolge                   |automatische Telefonzentrale ID (Ressourcenkonto-ID) |
|AACallFlow                              |Zeichenfolge                   |Kapselt die verschiedenen Zustände automatische Telefonzentrale Anrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>Ankündigung |
|AACallResult                            |Zeichenfolge                   |Ergebnis eines automatische Telefonzentrale Anrufs:<br>§ unbekannt<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – Fehler der AA-Konfiguration<br>§ service_terminated – interne AA-Fehler<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |Zeichenfolge                   |Dauer automatische Telefonzentrale Anrufs in Sekunden  |
|AACount                                 |Zeichenfolge                   |# der automatische Telefonzentrale an Anrufen beteiligen         |
|AADirectorySearchMethod                 |Zeichenfolge                   |Im Aufruf verwendete Suchmethode:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |Zeichenfolge                   |Anrufzeit in UTC                            |
|AATransferAction                        |Zeichenfolge                   |Anrufempfänger:<br>§ unbekannt – Entitätstyp wurde nicht angegeben<br>§ Benutzer – Benutzerentität<br>§ AA – Organisations- automatische Telefonzentrale Entität<br>§ CQ – Entität "Anrufwarteschlange"<br>§ Anwendung – Sprachanwendungsentität<br>§ external_pstn - externe PSTN-Entität<br>§ shared_voicemail – freigegebene Voicemailentität      |
|PSTNMinutes                             |int                      |Gesamtminutennutzung                          |
|Anrufergebnis der Anrufwarteschlange                  |Zeichenfolge                   |Anrufwarteschlange anruft den enden Zustand<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ überlaufen<br>§ fehlgeschlagen<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Anrufwarteschlangeidentität                     |Zeichenfolge                   |Name des Ressourcenkontos, das an CQ angefügt ist     |
|Zieltyp der Anrufwarteschlange                  |Zeichenfolge                   |Zieltyp der erwarteten Anrufumleitung:<br>§ Benutzer<br>§ Anwendungsendpunkt<br>§ Sonstiges     |
|Anrufergebnis der Anrufwarteschlange                  |Zeichenfolge                   |Anrufwarteschlange anruft den enden Zustand<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ überlaufen<br>§ fehlgeschlagen<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Aktion zum endgültigen Status der Anrufwarteschlange           |Zeichenfolge                   |Letzte Aktion der Anrufwarteschlange<br>mögliche Werte:<br>§ weiterleiten<br>§ Trennen<br>§ Voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ sonstige             |
|Agentname                              |Zeichenfolge                   |Benutzer-UPN               |


### <a name="measures"></a>Kennzahlen

|Name                                      |Typ                       |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# der Aktion, die vom Benutzer in AA während des Anrufs ausgewählt wurde  |
|PSTNMinutes                             |int                      |Gesamtminutennutzung                                  |
|TotalCallCount                          |int                      |# der Anrufe                                          |
|Durchschnittliche Anrufdauer(Sekunden)         |int                      |Gesamtdauer von Anrufwarteschlangenanrufen in Sekunden     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI Graph description automatische Telefonzentrale

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle für eingehenden Anruf                    |Verteilung des Anrufs nach interner/externer Anrufquelle      |
|Summen der Verzeichnissuchemethode          |Verteilung des Anrufs nach Suchtyp                         |
|Anruferaktion                           |Anrufverteilung nach Anrufempfänger                       |
|Anrufergebnis                             |Verteilung des Anrufs nach endgültigem Anrufzustand                    |
|Anzahl der Aufruferaktion                     |Verteilung des Anrufs nach Rufnummernaktion, die während des Anrufs verwendet wird  |


### <a name="call-queue"></a>Anrufwarteschlange

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle für eingehenden Anruf                    |Verteilung des Anrufs nach interner/externer Anrufquelle         |
|Anruflautstärke                             |Verteilung von Anrufen nach Anrufwarteschlangen                            |
|Anruferergebnis                           |Verteilung des Anrufs nach Anrufergebnis                            |
|Timeout-/Überlauf-Aufrufsummenaktion      |Verteilung des NICHT weitergeleiteten(abgebrochenen) Anrufs nach Anrufergebnis   |
|Summen des Transfer-/Forward-Ziels          |Verteilung des nach Anrufergebnis weitergeleiteten Anrufs                  |
|Verhältnis "Abgebrochene Anrufe"                   |Verhältnis von erfolgreicher zu abgebrochener Anrufanzahl                    |
|Durchschnittliche Sitzungsdauer (Sekunden)        |Anruflänge in Sekunden nach abgebrochenen/erfolgreichen Anrufen   |



### <a name="agent-timeline"></a>Zeitachse des Agenten

|Name                                                      |Beschreibung                            |
|:-------------------------------------------------------|:--------------------------------------|
|# Anrufe nach Agent                                        |Verteilung von Anrufen nach Anrufwarteschlange und Agent                 |
|Gesamtanrufdauer (Sekunden) nach Agent und Anrufwarteschlange   |Gesamtdauer (Sekunden) des Anrufs nach Agent und Anrufwarteschlange     |
|Durchschnittliche Anrufdauer (Sekunden) nach Agentname            |Durchschnittliche Anrufdauer (Sekunden) nach Agent                  |



## <a name="known-issues"></a>Bekannte Probleme
- Derzeit zeigen Anrufwarteschlange und automatische Telefonwarteschlange die Ressourcenkonten-ID anstelle der Namen der Anrufwarteschlange/automatischen Telefonwarteschlange an.  Wenn Sie den ganzen Datenverkehr für eine automatische Telefonwarteschlange oder Anrufwarteschlange anzeigen möchten, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefonwarteschlange oder Anrufwarteschlange zugewiesen sind.

- Derzeit steht im Dashboard nur ein Verlauf von 28 Tagen zur Verfügung, da Anrufwarteschlange-/automatische Telefonkonferenzdaten als identifizierbare Informationen des Endbenutzers betrachtet werden und den Datenschutzaufbewahrungsrichtlinien unterliegen.
