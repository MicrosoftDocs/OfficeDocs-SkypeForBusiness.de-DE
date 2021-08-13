---
title: Anmerkungen zu dieser Microsoft Teams-Räume
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Der Administrator kann die Versionshinweise für Microsoft Teams-Räume lesen, in denen die kumulierten Verbesserungen der Microsoft Teams-Räume.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a76d2ba56a56b3055d0ca6838e512e2074afcf72c93c5590510a22bb946a63eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346142"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Anmerkungen zu dieser Microsoft Teams-Räume

In diesem Artikel werden kumulierte Verbesserungen bei Microsoft Teams-Räume.

## <a name="version-history"></a>Versionsverlauf

|Release |Veröffentlicht an <br/> Microsoft Store |
|--- |--- |
|4.9.12.0 |07/28/2021 |
|4.8.31.0 |05/12/2021 |
|4.8.25.0 |04/22/2021 |
|4.8.19.0 |04/06/2021 |
|4.7.19.0 |02/03/2021 |
|4.7.15.0 |12/11/2020 |
|4.6.23.0 |10/19/2020 |
|4.6.20.0 |09/30/2020 |
|4.5.37.0 |08/14/2020 |
|4.5.35.0 |07/23/2020 |
|4.4.63.0 |06/25/2020 |
|4.4.41.0 |05/06/2020 |
|4.4.25.0 |03/31/2020 |
|4.3.42.0 |03/02/2020 |
|4.3.33.0 |1/10/2020 |
|4.3.23.0 |12/13/2019 |
|4.2.4.0 |10/07/2019 |
|4.1.22.0 |08/15/2019 |
|4.0.105.0 |07/10/2019 |
|4.0.85.0 |04/08/2019 |
|4.0.78.0 |03/14/2019 |
|4.0.76.0 |03/04/2019 |
|4.0.64.0 |12/14/2018 |
|4.0.51.0 |11/17/2018 |
|4.0.31.0 |10/16/2018 |
|4.0.27.0 |10/1/2018 |
|4.0.19.0 |08/31/2018 |
|4.0.18.0 |08/27/2018 |
|4.0.8.0 |07/06/2018 |
|3.1.115.0|06/18/2018 |
|3.1.113.0|06/13/2018 |
|3.1.112.0|06/05/2018 |
|3.1.104.0|04/16/2018 |
|3.1.100.0|03/16/2018 |
|3.1.99.0 |3/14/2018 |
|3.1.98.0 |3/8/2018 |
|3.0.16.0 |11/27/2017 |
|3.0.15.0 |10/3/2017 |
|3.0.12.0 |9/1/2017 |
|3.0.8.0 |11/16/2017 |
|3.0.6.0 |11/16/2017 |
|2.0.2.0 |03/15/2017 |
|RTM (1.0.8) |12/7/2016 |

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Microsoft Teams-Räume und Problemlösung für Features

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

In diesem Update eingeführt:
- Microsoft Teams ist jetzt in den Anwendungseinstellungen verfügbar, sodass Sie kein Skype for Business mehr einrichten müssen. In diesem Modus treten Geräte, die Teams angemeldet sind, als Skype for Business als Gastbenutzer an Besprechungen teil.
- Fix für HDMI-Audio, das zu einer geringeren Anruflautstärke führt. Das HDMI-Audiofeature wird automatisch für alle Geräte mit Anwendungsaufbau 4.9.12.0 aktiviert.

> [!NOTE]
> S Skype for Business Ende des Lebenszyklus wird empfohlen, auf den ausschließlichen Teams zu aktualisieren.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

In diesem Update eingeführt:
- Windows 10 20H2-Support 

> [!NOTE]
> Für das UC-Engine (BIOS-Versionsdatum mit "KYSKLi") Teams-Räume liegen Kompatibilitätsprobleme vor, und aktualisierte Treiber werden in naher Zukunft von System-OEMs bereitgestellt. Windows 10 20H2 wird diesen Geräten nicht angeboten. Weitere Informationen zur Unterstützung Windows Version finden Sie unter Windows 10 [Release-Support.](./rooms-lifecycle-support.md#windows-10-release-support)

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

In diesem Update eingeführt:
- Fix für ein Problem, bei dem Rauminformationen auf Teams-Räume-Konsolen für Raumkonten, die aus der globalen Adressliste (GAL) ausgeblendet sind, nicht angezeigt werden

> [!NOTE]
> GCCH-Kunden können das Upgradepaket von [Manuelles Aktualisieren eines](manual-update.md) Microsoft Teams-Räume herunterladen.

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

In diesem Update eingeführt:
- Government Community Cloud High (GCCH) support for Teams-Räume. GCCH-Kunden mit vorhandenen Teams-Räume können Version 4.8.19.0 über manuelles Aktualisieren eines Microsoft Teams-Räume [herunterladen.](manual-update.md)
- Teilnehmen an Zoom-Besprechungen mit besserer Videoqualität (720p-Unterstützung) und Empfangen der Videogalerie von Teilnehmern
- Skype for Business Banner "Anmeldefehler" wurde für den Teams entfernt. Diese Änderung unterstützt Organisationen, die Skype for Business entfernen.
- Teams Besprechungen werden jetzt mit der Analyse von Verknüpfungen behandelt Microsoft Defender Advanced Thread Protection Tresor Links, um die nahtlose Teilnahme an externen Teams zu ermöglichen
- Fix für das Problem mit der Skalierung von freigegebenen Inhalten in Skype for Business Besprechungen, wenn auf dem PC des Freigebens ein benutzerdefinierter DPI-Wert in einer Windows
- Qualitäts- und Zuverlässigkeitsfixes

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

In diesem Update eingeführt:
- Qualitäts- und Zuverlässigkeitsfixes

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

In diesem Update eingeführt:

- Freigeben von HDMI-Audio für Besprechungsteilnehmer in Teams Besprechung
- Cortana (Vorschau)
- Verhindern Sie die Stummschaltung basierend auf Audioberechtigungen, Teams Raum als Teilnehmer teilnehmen. Weitere Informationen finden Sie unter [Verwalten von Teilnehmeraudioberechtigungen in Teams Besprechungen.](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a)
- Spotlight someone's video from Teams Room console and consume spotlighted video on room displays

> [!NOTE]
> Cortana Sprachkenntnisse stehen für ausgewählte Audioperipheriegeräte für Mandanten in den USA zur Verfügung. Weitere Länder oder Regionen werden in Zukunft hinzugefügt. Weitere Informationen finden Sie unter [Cortana Sprachunterstützung in Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

In diesem Update eingeführt:

- Fix für weiße Hälfte des Bildschirms beim Aufrufen der Bildschirmtastatur in Teams Besprechung

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

In diesem Update eingeführt:

- Weitere Videos mit 3 x 3-Videogalerie vor den Raumanzeigen anzeigen  
- Starten lokaler Live-Untertitel über MTR
- Teilnehmen an Zoombesprechungen Teams-Räume mit direkter Gasteinwahl (Vorschau)

> [!NOTE]
> 3 x 3-Videogalerie und lokale Liveuntertitel werden über den Microsoft Teams übermittelt. Diese Features sind für alle Teams-Räume mit Anwendungsversion 4.5.37.0 und höher verfügbar.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

In diesem Update eingeführt:

- Koordinierte Besprechungen zwischen Microsoft Teams und Surface Hub 2S
- Beheben eines Skype bei einem Anmeldefehler bei Windows 10 bei der Installation von [KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) oder Windows 10 [Update KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709)

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

In diesem Update eingeführt:

- Teilnehmen an Cisco WebEx-Besprechungen über Teams-Räume mit direkter Gasteinwahl
- Teams Admin Center-Aktivierung und automatische Registrierung
- Windows 10 1909 Release-Support
- Wechseln zum Layout des Videokatalogs auch dann, wenn Inhalte vorhanden sind
- Unterstützung virtueller Hände für Teilnehmer und Steuerelemente für Präsentierende
- Anpassbare Standardlautstärkeeinstellung für Konferenzen und Standardlautsprecher
- Suchen und Anrufen von Partnerbenutzern (Mandant) aus Teams Raum

> [!IMPORTANT]
> Version 4.5 ist die letzte Version zur Windows 10 Version 1803. zukünftige Versionen werden für Systeme mit Windows 10 Version 1803 nicht mehr angeboten. Weitere Informationen zur Unterstützung Windows Version finden Sie unter Windows 10 [Release-Support.](./rooms-lifecycle-support.md#windows-10-release-support)

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

In diesem Update eingeführt:

- Qualitäts- und Zuverlässigkeitsfixes
- Fix für das Problem "Die Anwendung wird nach dem Update auf 4.4.41.0 nicht gestartet".

> [!NOTE]
> Wenn Ihr Gerät nicht automatisch auf Version 4.4.63.0 aktualisiert wird, führen Sie die Schritte in Microsoft Teams-Räume-Anwendung wird nach dem Update auf Version [4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) nicht gestartet, um das Problem zu beheben.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

In diesem Update eingeführt:

- Zuverlässigkeitsfixes für den Anwendungsstart in Windows 10 Kiosk

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

In diesem Update eingeführt:

- Unterstützung der modernen Authentifizierung Exchange und Skype for Business
- Unterstützung für dynamische Notrufe für Teams (Servicekomponenten erforderlich und mithilfe von Teams-Ringen freigegeben)
- Möglichkeit zum Deaktivieren von doppelten Inhalten aus der Besprechung für zwei Räume mit XML
- Begrüßungsbildschirm der Anwendung
- Hinweise zur Open Source Software (OSS) in den Geräteeinstellungen

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

In diesem Update eingeführt:

- Richtlinienupdates für "Windows Updates for Business"
- Fix für die Meldung von Geräteereignissen, bei denen Fehler im Azure Monitor angezeigt werden

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

In diesem Update eingeführt:

- Ein Fix für ein Problem mit Größenänderung/Flimmern des Fensters, das in bestimmten Konfigurationen zu sehen ist
- Kalenderverarbeitung für Besprechungen von Drittanbietern wurde entfernt
- Cortana Statuseinstellung entfernt

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

In diesem Update eingeführt:

- Automatische Antwort für näherungsbasierte Anrufe und Administratoreinstellung, um dies zu steuern
- Geräteadministrator Einstellungen Benutzeroberflächenaktualisierung mit Ergänzung der Gerätekonfiguration auf der Registerkarte "Informationen"
- Raumsteuerung zurück zum Hauptbildschirm
- Besprechungsraum SKU in GCC
- Unterstützung der Inhaltskamera für Surface Pro System (mindestens erforderliche App-Build: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

In diesem Update eingeführt:

- Windows 10 1903-Support. Windows 10 1903-Update wird einige Tage nach dem App-Update angeboten.
- Korrekturen für Bildschirmtastatur werden nicht zuverlässig angezeigt

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

In diesem Update eingeführt:

- Ein neues Feature für die Inhaltskamera, mit dem Benutzer ein herkömmliches Whiteboard intelligent in ihre Besprechung Teams können
- Weitere Verbesserungen an der Konsolenbenutzeroberfläche, um unübersichtlich zu machen und Einstellungen in eine neue Seitenleiste verschoben, auf die über "Mehr" auf der Konsole zugegriffen wird
- Deaktivierte Schaltfläche "Taskleiste freigeben", wenn das lokale Inhaltskabel nicht angeschlossen oder keine Inhaltskamera angeschlossen ist
- Ein Problem mit der Bildschirmtastatur wurde behoben, bei dem die Bildschirmtastatur erst nach einem Neustart des MTR-Systems zum ersten Mal angezeigt wurde.
- Qualitäts- und Zuverlässigkeitsfixes

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

In diesem Update eingeführt:

- Skype Room System Store-App wird in "Microsoft Teams-Räume" umbenennt
- Microsoft Teams-Räume der Konsolen-Benutzeroberfläche ist auf eine Microsoft Teams
- Designupdate: Benutzerdefiniertes Hintergrundbild nur vor Raumanzeigen behalten, während Konsolenhintergrund zu einer neutralen Farbe wird, um sicherzustellen, dass die UI-Steuerelemente der Konsole Farbkontrast erfüllen – Anforderungen an die Barrierefreiheit
- Universelle Leiste für Steuerelemente für Besprechungsanrufe für Teams-Anrufe/-Besprechungen, um eine konsistente Erfahrung mit Microsoft Teams PC/Web/Mobile Clients<sup>1 zu bieten.</sup>
- Bewertung von Feedback zur Anrufqualität nach Teams/Besprechungen<sup>1</sup>
- Empfangen/Rendern von Microsoft Whiteboard auf Microsoft Teams-Räume vor dem Raum, wenn sie vom PC/ Aus dem Web/mobilen Teams<sup>1</sup> <sup>2 freigegeben werden</sup>
- Der Support für Windows 10 Version 1809-Upgrades wurde aufgrund von Kompatibilitätsproblemen mit dem Microsoft Teams-Räume entfernt. Windows 10 Support für Version 19H1 wird in zukünftigen Versionen hinzugefügt

<sup>1 Microsoft Teams</sup> Rollout des Diensts mithilfe Teams Ringen. Dieses Feature ist möglicherweise vor oder nach dem Clientupdate 4.0.105.0 verfügbar.

<sup>2</sup> IT-Administratoren müssen die Microsoft Whiteboard. Außerdem müssen Sie bei einer Touch-fähigen Front-Of-Room-Anzeige mehrere Touchbildschirme mithilfe von Windows-Einstellungen bei Geräteadministratoranmeldung kalibrieren, um Microsoft Whiteboard für die Zusammenarbeit von einer Raumanzeige zu verwenden, die in einer Teams-Besprechung freigegeben ist.

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

In diesem Update eingeführt:

- Behebt ein Problem mit dem Feature "Feedback geben".
- Optimierungen als Vorbereitung auf das bevorstehende Microsoft Teams-Räume Geräteupgrade auf Windows 10 Version 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

In diesem Update eingeführt:

- Fix für den Fehler "Beim App-Start auflegen", der auf Geräten mit älteren RS2-Windows 10 war.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

In diesem Update eingeführt:

- MFV-Tastatur für Microsoft Teams P2P-Besprechungen und PSTN-Anrufe. Damit Microsoft Teams Standardclient für Anrufe verwenden können, müssen Administratoren "IsTeamsDefaultClient" auf "true" festlegen.
- Heften Sie das eingehende Video eines Remoteteilnehmers an den Vollbildmodus vor dem Raumbildschirm an. Verwenden des Befehls "Anheften" aus der Teilnehmerliste auf der Konsole
- Verbesserungen bei Benachrichtigungen für den Wartebereich und zusätzlich zu "Vor den Raum"-Benachrichtigungen
- Das Umwandlungssymbol für die Raumanzeige wird entfernt, wenn Bluetooth auf einem Gerät nicht aktiviert Microsoft Teams-Räume ist
- Beheben eines Problems mit der Lautstärkeregelung in Teams Besprechungen

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

In diesem Update eingeführt:

- Anzeigen von Inhalten auf beiden Raum vorne (FoR)-Anzeigen auf Raumsystemen mit zwei Bildschirmen
- Verbesserungen an der Benutzeroberfläche von "Theming" und "Front of Room"
- Clientseitige Unterstützung von TLS 1.2. Für lokale Kunden ist für die Aktivierung der Kommunikation über TLS 1.2 für Microsoft Teams-Räume Skype for Business Server 2015 Kumulatives Update 9 (CU9) oder Skype for Business Server 2019 Kumulatives Update 1 (CU1) erforderlich.

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

In diesem Update eingeführt:

- Unterstützung für zwei Monitore (vor dem Raum) für Teams Besprechungen

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

In diesem Update eingeführt:

- Qualitäts- und Zuverlässigkeitsfixes

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

In diesem Update eingeführt:

- Erforderliche Codeänderungen zum Vorbereiten der Microsoft Teams-Räume-App für eine spätere Windows 10 Version 1803
- Beheben eines Formatierungsproblems mit lokalisierten EULAs (speziell Norwegisch), wodurch verhindert wird, dass das Setupfenster des EULA OOBE nicht mehr weiter kommt
- Codeänderungen, die erforderlich sind, damit Microsoft Teams-Räume Auf älteren Lync Room Systems ausgeführt werden kann. Weitere Informationen [finden Sie hier.](./lrs-migration.md)

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

In diesem Update eingeführt:

- Hotfix for Crestron application not launching which would normally be accessible when the app button on a Crestron SR device is pressed. Microsoft Teams-Räume Neustart der App nach der Installation von 4.0.19.0 erforderlich.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

In diesem Update eingeführt:

- Featureverbesserungen für "Problem melden" im Teams (Äquivalent zu "Feedback" im Skype for Business)
- Ermöglichen des Rückfallens vom Teams in den Skype for Business für SIP-Anrufe
- Verbesserungen der Barrierefreiheit (Sprachausgabe, Bildschirmlupe)
- App automatisch neu starten, wenn dies erforderlich ist, nachdem Änderungen der XML-Bereitstellung angewendet wurden
- Sonstige Fehlerbehebungen

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

In diesem Update eingeführt:

- Dieses Update ermöglicht sowohl Skype for Business *als* Teams Unterstützung von Besprechungen auf Raumsystemen. Teams ist standardmäßig deaktiviert, sobald das Update angewendet wurde. Administratoren können Eine Teams in geräteeinstellungen oder über einen Remote-XML-Push aktivieren.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

In diesem Update eingeführt:

- Beheben Sie den Fehler, der bei einigen Systemen beim Starten der App beobachtet wurde.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

In diesem Update eingeführt:

- Änderungen, die Microsoft eine flexiblere Verwaltung Windows ermöglichen.
- Keine Änderung an der Endbenutzererfahrung.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

In diesem Update eingeführt:

- Beheben von Problemen mit der Reaktionsfähigkeit der Konsole, die auf Surface Pro 2017-basierten Geräten beobachtet wurden, die an zwei Front-of-Room-Anzeigen und die Videoaufnahme angeschlossen sind
- Automatische Überprüfung, um sicherzustellen, dass auf dem System die neuesten Bereitstellungsskripts ausgeführt werden

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

In diesem Update eingeführt:

- Fix zum Verbessern des OSK-Verhaltens (Bildschirmtastatur) in Windows 10-basierten Systemen mit Version 1709
- Verbesserungen bei der Vorbereitung zukünftiger Betriebssystemupdates

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

In diesem Update eingeführt:

- Anwendung zur Verbesserung der Telemetrie aktualisiert

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

In diesem Update eingeführt:

- Behebt ein Problem, bei dem zeitweilige Besprechungs-Join-Probleme auftreten können
- Behebt ein Problem, bei dem bekannt ist, dass das Gerät hängen bleibt.

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

In diesem Update eingeführt:

- Fehler-/Absturzkorrekturen zur Verbesserung der Stabilität
- Unterstützung für Konsolen variabler Größe
- Auslagerung von Peripherieaudioverarbeitung (zusätzliche Medien-Allowlist)
- Optimierungen, die IT-Profis das Erstellen von Do-It-Yourself-Bildern Windows 10 Version 1709 Januar Update und höher ermöglichen.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

In diesem Update eingeführt:

- Behebt ein Problem mit dem Feature "Feedback geben".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

In diesem Update eingeführt:

- Unterstützung für [Dockhardware der Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Support für [Logitech Brio](https://www.logitech.com/product/brio)
- Behebt ein Problem, bei dem Anzeigen (Konsole und Front-of-Room) nicht in den Ruhemodus wechseln können, wenn keine Aktivität im Raum vorhanden ist.

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

In diesem Update eingeführt:

- Wird auf einem Surface Pro (2017) ausgeführt
- Unterstützt Windows 10 Enterprise Creator's Update (englische Sprache, Build 1703)
- Unterstützung für [die Hardware der Docking-Station "Crestron SR"](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- OEM-Unterstützung für Umgebungssteuerelemente (Crestron)

Die 64-Bit-Version von Windows 10 Enterprise Anniversary Edition (Englisch, Version 1607) wird ab Version 3.0.12.0 (Update 3 Microsoft Teams-Räume) nicht mehr unterstützt.

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

In diesem Update eingeführt:

- Behebt Probleme, die bei der Suche nach Partnerbenutzern über das Suchfeld "Teilnehmer" beobachtet wurden. Vor diesem Fix wurden die Suchergebnisse für externe Verbundbenutzer möglicherweise nicht ordnungsgemäß aufgelöst und es wurden stattdessen falsche Ergebnisse zurückgegeben.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

In diesem Update eingeführt:

- Dual-Screen (für ältere Systemparität)
- Designs (integrierte Designs und die Möglichkeit zum Festlegen eines benutzerdefinierten Designs)
- Möglichkeit zum Abgeben von Feedback für öffentliche Builds
- Verbesserte Telemetrie rund um die Zuverlässigkeit von Besprechungs-Teilnahmen
- Verbesserte OMS-Berichterstellung
- Möglichkeit für IT-Administratoren, Geräte remote zu konfigurieren

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

In diesem Update eingeführt:

- App-in-app-Benutzerauswahl von Audio- und Video-USB-Geräten für Besprechungsraum
- Statusberichte für integrierte Raumkonsolen für Kunden, die microsoft Operations Management Suite verwenden, jetzt Azure Monitor

### <a name="release-to-market-1272016"></a>Release to Market (07.12.2016)

**Features:**

 **Für Skype for Business konzipiert**

- One-Touch-Teilnahme an Skype-Besprechungen
- Skype-Besprechung für Räume mit ausfüllenden HD-Videos und HD-Breitbandaudio optimiert
- Alle Teilnehmer können über ihr bevorzugtes Gerät eine Verbindung mit der Skype-Besprechung herstellen – ganz gleich, wo sie sich gerade aufhalten.
- Sie können Personen aus Ihrem Verzeichnis, wo Sie ihre Verfügbarkeit sofort sehen können, oder telefonisch einladen.
- Unterstützt Skype for Business-PSTN-Konferenzen und -PSTN-Anrufe als Ersatz für das eigenständige Konferenztelefon in Ihrem Raum.

 **Neue Möglichkeiten für Besprechungsräume**

- Eigene Skype-Besprechungs-App mit Optimierung für einen Touchcontroller in der Tischmitte und einen großen Bildschirm vorn im Raum
- Vorhandene Investitionen wiederverwenden im Front-of-Raum-Display oder in Projektoren
- Für alle Arten von Besprechungsräumen geeignet – von kleinen Besprechungsräumen bis hin zu großen Konferenzräumen
- Für Skype for Business zertifizierte Audio- und Videogeräte für verschiedene Raumgrößen
- Integrierte verkabelte Erfassung zum Projizieren der Desktopfreigabe in den Raum und die Skype-Besprechung

 **Leicht bereitzustellen, einfach zu verwalten**

- Ein stets aktiviertes Gerät, mit dem die Anzeigen automatisch aktiviert werden, wenn Personen im Raum erkannt werden
- Einfache Bereitstellung und Aktualisierung der UWP-App (Universal Windows Platform) für Skype-Besprechungen
- Feste Bindung des Geräts an die Skype-Besprechungs-App durch Windows AppLocker
- Überwacht und verwaltet als mobiles Windows 10 Enterprise über Intune und Configuration Manager (MDM)
- Zuverlässigkeit der Unternehmensklasse
- Geringer Aufwand für Endbenutzerschulungen dank der vertrauten Skype-Benutzeroberfläche
- Wird auf einem Surface Pro 4 ausgeführt.

<a name="See"> </a>
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Vorbereiten der Umgebung](rooms-prep.md)

[Unterstützung für Microsoft Teams-Räume Current Branch-Versionen](rooms-lifecycle-support.md)

[Bekannte Probleme](known-issues.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Microsoft Teams Rooms verwalten](rooms-manage.md)
