---
title: automatische Telefonzentrale & von Verlaufsberichten für Anrufwarteschleifen
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
description: Erfahren Sie, wie Sie mithilfe des Power BI-Berichts für das Anrufqualitätsdashboard Verlaufsdaten automatische Telefonzentrale Anrufwarteschleife anzeigen.
ms.openlocfilehash: ee54941150a5ba4ade64d6a54cb066f50df2e0a8
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196239"
---
# <a name="auto-attendant--call-queue-historical-report"></a>automatische Telefonzentrale & von Verlaufsberichten für Anrufwarteschleifen

Die Power BI-Vorlage automatische Telefonzentrale & CQD Teams automatische Telefonzentrale & Bericht "Verlauf der Anrufwarteschleife" enthält die folgenden drei Berichte:

- automatische Telefonzentrale – Anzeigen von Analysen für Anrufe, die an Ihre automatischen Telefon attendants gehen.
- Anrufwarteschleife – Zeigt Analysen für Anrufe an, die in Ihre Anrufwarteschleifen ein werden.
- Zeitachse des Agents – Zeigt eine Zeitachsenansicht der Agents an, die an Anrufen in der Anrufwarteschleife aktiv sind.

Diese Berichte verwenden [](CQD-Power-BI-query-templates.md) Daten aus dem Datenspeicher für das Anrufqualitätsdashboard und ermöglichen es Organisationen, über die Anzahl der von automatischen Telefonwarteschleifen und Anrufwarteschleifen verarbeiteten Anrufe sowie die Leistung des Agents in den Anrufwarteschleifen zu berichten.

## <a name="what-are-the-requirements"></a>Welche Anforderungen gelten? 

Power BI Desktop muss installiert sein. Sie können sie aus dem [Microsoft Windows Store installieren.](https://aka.ms/pbidesktopstore)

Sie können die kostenlose Version von Power BI Desktop verwenden. Die kompatible Mindestversion ist 2.85.681.0 (September 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Berechtigungen für den Zugriff auf die CQD-Pipeline

Das Konto, das Sie zum Anzeigen des AA- & CQ Analytics-Verlaufsberichts verwenden, benötigt Berechtigungen für den Zugriff auf die CQD-Datenpipeline. Weitere Informationen finden Sie in der Zugriffsrolle für das [AQD.](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd)

## <a name="installation"></a>Installation 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie Power BI Desktop bereits auf dem Computer installiert haben und Dass Ihr Konto über die erforderlichen Berechtigungen für den Zugriff auf die CQD-Datenpipeline verfügt.

Führen Sie die folgenden Schritte aus:

- Laden Sie die [Power BI-Abfragevorlagen für AQD](https://www.microsoft.com/download/details.aspx?id=102291) herunter, und speichern Sie die ZIP-Datei in einem Verzeichnis auf Ihrem Computer.

- Doppelklicken Sie auf die ZIP-Datei, um sie zu öffnen.

- Doppelklicken Sie auf die Vorlagendatei "CQ und AA kombinierte Analytics 20201105.pbit", und Power BI Desktop sollte gestartet werden.

- Sie werden aufgefordert, den Bereich für die CQD-Datenpipeline auszuwählen. Wählen Sie die Region aus, in der sich Ihr Mandant befindet.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot: Auswählen des CQD-Datenpipelinebereichs":::

 - Sie können die Region mithilfe des Skype for Business Online-PowerShell-Cmdlets (Get-CsTenant) sehen. "ServiceInstance"-Ausgabe. 
 Die Region wird nach dem /-Beispiel in folgendem Beispiel angezeigt:

   microsoftcommunicationsonline/noam-4a-s7 mit der Region noam.
 
 - Der Bericht wird mit Beispieldaten gestartet.
 
 - Zum Anzeigen Ihrer eigenen  Daten klicken Sie auf der Registerkarte "Start" unter "Abfragen" in Power BI Desktop auf "Aktualisieren".

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot mit Auswahl der Aktualisierungsoption":::

- Sie werden dann aufgefordert, sich anmelden. Wählen Sie **"Organisationskonto"** und dann **"Anmelden" aus.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot mit Anmeldung":::

- Wählen Sie **"Verbinden"** aus, und beobachten Sie die Datenaktualisierung.

## <a name="data-latency-and-aa--cq-analytics"></a>Datenlatenz und AA-& A-Analysen

Die Daten sind innerhalb von 30 Minuten in der Datenpipeline für AQD verfügbar.

Sie müssen die Daten aktualisieren, um die neuen Analysedaten zu sehen. 

## <a name="customization"></a>Anpassung 

Sie können bestimmte Visualisierungsaspekte der Berichte anpassen, z. B. Felder hinzufügen oder entfernen, die in den verschiedenen Visualisierungen angezeigt werden sollen, Ändern des Diagrammtyps usw.

Sie können keine weiteren Datenfelder als die im Bericht bereitgestellten hinzufügen.

### <a name="change-color-schema"></a>Ändern des Farbschemas 

Bei den folgenden Schritten wird davon ausgegangen, dass Sie die Installationsschritte bereits abgeschlossen haben.

Führen Sie die folgenden Schritte aus:
- Wählen Sie **im Menüband die Registerkarte** "Ansicht" aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot: Auswählen der Registerkarte "Ansicht", um das Farbschema zu ändern":::

- Wählen Sie in der Dropdownliste das Farbschema aus.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot mit verschiedenen Farbschemas":::

## <a name="cqd-fields-description"></a>Beschreibung von CQD-Feldern

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|automatische Telefonzentrale Identität                 |Zeichenfolge                   |Name des ressourcenkontos, das AA zugeordnet ist<br>Beispiel: aa_test@microsoft.com|
|automatische Telefonzentrale Verkettungsstartzeit         |datetime                 |Startzeit der AA-Kette                    |
|automatische Telefonzentrale der Verzeichnissuche  |Zeichenfolge                   |Suchmethode für das letzte Adressbuch        |
|automatische Telefonzentrale'-Übertragungsaktion          |Zeichenfolge                   |Zieltyp für Anrufübertragung<br>mögliche Werte:<br>§ unknown - Entitätstyp wurde nicht angegeben<br>§ Benutzer – Benutzerentität<br>§ orgaa - Organizational automatische Telefonzentrale entity<br>§ hunt_group - Entität der Anrufwarteschleife<br>§ application - voice application entity<br>§ external_pstn - externe Entität des PSTNs<br>§ shared_voicemail – Entität für freigegebene Voicemails|
|automatische Telefonzentrale Anrufergebnis              |Zeichenfolge                   |Anrufergebnis:<br>§ unbekannt<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|automatische Telefonzentrale des Anrufflusses                |Zeichenfolge                   |Kapselt die verschiedenen Zustände automatische Telefonzentrale Aufrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ Ankündigung|
|Ist automatische Telefonzentrale beteiligt              |Boolean                  |Gibt an, ob AA an dem Anruf beteiligt ist |
|automatische Telefonzentrale Caller Action Count      |int                      |Anzahl der vom Anrufer verwendeten Aktion         |
|automatische Telefonzentrale Dauer (Sekunden) der Kette   |int                      |Dauer des Anrufs in AA                 |
|Anrufwarteschleifen-Anrufergebnis                  |String                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ overflown<br>§ fehlgeschlagen<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Aktion zum endgültigen Zustand der Anrufwarteschleife           |String                   |Letzte Aktion der Anrufwarteschleife<br>mögliche Werte:<br>§ weiterleiten<br>§ trennen<br>§ Voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ andere|
|Identität der Anrufwarteschleife                     |String                   |Name des Ressourcenkontos, das dem AQ angefügt ist<br>Beispiel: aa_test@microsoft.com|
|Anrufwarteschleife ist Konferenzmodus           |Boolean                  |Auf 1 festgelegt, wenn der Konferenzmodus für AQ aktiviert ist |
|Zieltyp der Anrufwarteschleife                  |String                   |Zieltyp der Anrufumleitung     |
|Von Anrufwarteschleifenidentität übertragen    |Boolean                  |Name des Ressourcenkontos, das dem AQ zugeordnet ist, von dem dieser Anruf übertragen wurde<br>Beispiel: aa_test@microsoft.com|
|Anrufwarteschleifen-Agent opt-in Count           |int                      |Die Anzahl der agents, die für diese Warteschlange zum Zeitpunkt des Anrufs verfügbar sind |
|Anzahl des Mitarbeiters in der Anrufwarteschleife                  |int                      |Die Anzahl der dieser Warteschlange zum Zeitpunkt des Anrufs zugewiesenen Agents |
|Ist die Anrufwarteschleife beteiligt?                  |Boolean                  |Wenn die Anrufwarteschleife an diesem Anruf beteiligt ist, ist 1 |


### <a name="power-bi-data-model-dimensions"></a>Dimensionen des Power BI-Datenmodells

|Name                                    |Datentyp                |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA Name                                   |Zeichenfolge                   |automatische Telefonzentrale-ID (Ressourcenkonto-ID) |
|AACallFlow                              |Zeichenfolge                   |Kapselt die verschiedenen Zustände automatische Telefonzentrale Aufrufs<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ Ankündigung |
|AACallResult                            |Zeichenfolge                   |Ergebnis eines automatische Telefonzentrale Anrufs:<br>§ unbekannt<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – Fehler bei der AA-Konfiguration<br>§ service_terminated – interne AA-Fehler<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |Zeichenfolge                   |Dauer automatische Telefonzentrale Anrufs in Sekunden  |
|AACount                                 |Zeichenfolge                   |Anzahl der automatische Telefonzentrale in den Anruf         |
|AADirectorySearchMethod                 |Zeichenfolge                   |Suchmethode, die beim Aufruf verwendet wird:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |Zeichenfolge                   |Anrufzeit in UTC      |
|AATransferAction                        |Zeichenfolge                   |Anrufempfänger:<br>§ unknown - Entitätstyp wurde nicht angegeben<br>§ Benutzer – Benutzerentität<br>§ AA – Organisations- automatische Telefonzentrale Entität<br>§ CQ – Entität der Anrufwarteschleife<br>§ application - voice application entity<br>§ external_pstn - externe Entität des PSTNs<br>§ shared_voicemail – Entität für freigegebene Voicemails      |
|PSTNMinutes                             |int                      |Gesamtminütige Nutzung                          |
|Anrufwarteschleifen-Anrufergebnis                  |Zeichenfolge                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ overflown<br>§ fehlgeschlagen<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identität der Anrufwarteschleife                     |Zeichenfolge                   |Name des Ressourcenkontos, das dem AQ angefügt ist     |
|Zieltyp der Anrufwarteschleife                  |Zeichenfolge                   |Erwarteter Zieltyp für die Anrufumleitung:<br>§ Benutzer<br>§ Anwendungsendpunkt<br>§ Andere     |
|Anrufwarteschleifen-Anrufergebnis                  |Zeichenfolge                   |Endzustand des Anrufwarteschleifenanrufs<br>mögliche Werte:<br>§ Fehler<br>§ abgelehnt<br>§ overflown<br>§ fehlgeschlagen<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|Aktion zum endgültigen Zustand der Anrufwarteschleife           |Zeichenfolge                   |Letzte Aktion der Anrufwarteschleife<br>mögliche Werte:<br>§ weiterleiten<br>§ trennen<br>§ Voicemail<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ andere             |
|Agentname                              |Zeichenfolge                   |Benutzer-UPN               |


### <a name="measures"></a>Kennzahlen

|Name                                      |Typ                       |Beschreibung                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |Aktions-Nr., die während des Anrufs vom Benutzer in AA ausgewählt wurde  |
|PSTNMinutes                             |int                      |Gesamtminütige Nutzung                                  |
|TotalCallCount                          |int                      |Anzahl Anrufe                                          |
|Durchschnittliche Anrufdauer(Sekunden)         |int                      |Gesamtdauer von Anrufwarteschleifenanrufen in Sekunden     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI graph description automatische Telefonzentrale

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle für eingehenden Anruf                    |Verteilung des Anrufs durch interne/externe Anrufquelle<sup>1</sup>|
|Summen der Verzeichnissuchmethode          |Verteilung des Anrufs nach Suchtyp                         |
|Anruferaktion                           |Verteilung des Anrufs nach Anrufempfänger                       |
|Anrufergebnis                             |Verteilung des Anrufs nach Dem Status des letzten Anrufs                    |
|Anzahl der Anruferaktion                     |Verteilung der Aktion "Anruf nach Nummer", die während des Anrufs verwendet wird  |


### <a name="call-queue"></a>Anrufwarteschleife

|Name                                      |Beschreibung                            |
|:---------------------------------------|:--------------------------------------|
|Quelle für eingehenden Anruf                    |Verteilung des Anrufs durch interne/externe Anrufquelle<sup>1</sup>   |
|Anruflautstärke                             |Verteilung von Anrufen durch Anrufwarteschleifen                            |
|Anruferergebnis                           |Verteilung des Anrufs nach Anrufergebnis                            |
|Aktion "Timeout/Überlaufaufruf Gesamt"      |Verteilung des NICHT weitergeleiteten(abgebrochenen) Anrufs nach Anrufergebnis   |
|Gesamtübergangs-/Weiterleitungszielsummen          |Verteilung des nach Anrufergebnis weitergeleiteten Anrufs                  |
|Verhältnis für abgebrochene Anrufe                   |Verhältnis von "Anzahl erfolgreich" zu "Abgebrochen"                    |
|Durchschnittliche Sitzungslänge (Sekunden)        |Anruflänge in Sekunden nach abgebrochenen/erfolgreichen Anrufen   |



### <a name="agent-timeline"></a>Zeitachse des Mitarbeiters

|Name                                                      |Beschreibung                            |
|:-------------------------------------------------------|:--------------------------------------|
|#Anrufe nach Agent                                        |Verteilung von Anrufen durch Anrufwarteschleife und Agent                 |
|Gesamtanrufdauer (Sekunden) nach Agent und Anrufwarteschleife   |Gesamtdauer (Sekunden) des Anrufs nach Agent und Anrufwarteschleife     |
|Durchschnittliche Anrufdauer (Sekunden) nach Agentname            |Durchschnittliche Dauer (Sekunden) des Anrufs nach Agent                  |



## <a name="known-issues"></a>Bekannte Probleme

- Anrufwarteschleife und automatische Telefonkonferenzen werden nach der ID des Ressourcenkontos anstelle der Namen der Anrufwarteschleife/der automatischen Telefonwarteschleife angezeigt.  Wenn Sie den ganzen Datenverkehr für eine automatische Telefonwarteschlange oder Anrufwarteschleife anzeigen möchten, müssen Sie alle Ressourcenkonten auswählen, die der automatischen Telefonwarteschlange oder Anrufwarteschleife zugeordnet sind.

- Der Verlauf von nur 28 Tagen steht im Dashboard zur Verfügung, da Daten der Anrufwarteschleife/der automatischen Telefonkonferenz als identifizierbare Informationen für Endbenutzer angesehen werden und den Aufbewahrungsrichtlinien für den Datenschutz unterliegen.

- <sup>1 Die</sup> **Quelle des eingehenden Anrufs** in der automatischen Telefon attendant und die Diagrammen der Anrufwarteschleife zeigen die endgültige Quelle des Anrufs und nicht die Quelle des ersten Anrufs. Wenn beispielsweise eine automatische Telefonkonferenz einen externen Anruf empfängt und den Anruf  an eine andere automatische Telefonwarteschleife oder Anrufwarteschleife überträgt, wird die Quelle für eingehende Anrufe als "Intern" gemeldet.
