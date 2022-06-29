---
title: Versionshinweise für Microsoft Teams-Räume (Windows)
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Admin können die Versionshinweise für Microsoft Teams-Räume lesen, in denen kumulative Verbesserungen in Microsoft Teams-Räume aufgeführt werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d4ac16e7214a6340eb74f1c154661f78a50992ee
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529697"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Versionshinweise für Microsoft Teams-Räume

In diesem Artikel werden kumulative Verbesserungen in Microsoft Teams-Räume erläutert.

Es gibt zwei Arten von Updates für Teams-Räume: Teams-Räume-App-Updates und Teams-Webclient. 

Teams-Räume App-Updates erfolgen entweder über den Microsoft Store oder über [manuelle Updates](manual-update.md). Dadurch wird die Universelle Windows-Plattform(UWP)-Anwendung aktualisiert, die lokal auf dem Gerät installiert ist.

Teams-Webclientupdates erfolgen über die Teams-Web-App-Übermittlungsdienste. Dies ist ein cloudbasierter Dienst, der kein Update für die lokale UWP-Anwendung erfordert, die auf dem Gerät installiert ist.

Weitere Informationen dazu, wie Teams-Updates ausgeführt werden, finden Sie [im Updateprozess von Teams.](../teams-client-update.md)

Teams-Räume unterliegt der Modern-Lifecycle-Richtlinie. Weitere Informationen finden Sie [im Teams-Updateprozess](../teams-client-update.md#servicing-agreement) .

## <a name="version-history"></a>Versionsverlauf

|Release |Veröffentlicht in <br/> Microsoft Store |
|--- |--- |
|4.12.138.0 |5/26/2022 |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|Teams Web-Client Release | Dezember 2021 |
|Teams Web-Client Release | Oktober 2021 |
|4.10.10.0 |10/1/2021 |
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

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Microsoft Teams-Räume Einführung und Problemlösung von Features

### <a name="4121380-5262022"></a>4.12.138.0 (5/26/2022)

In diesem Update eingeführt:
- Fehlerkorrektur für mehrere gleichzeitige Videostreams von Jabra Panacast 50 (Besprechungsvideo, Videoinhaltskamera)
- Cloudübergreifende Besprechungen können jetzt das Standardaudiogerät für Konferenzen verwenden.
- Qualitäts- und Zuverlässigkeitskorrekturen

### <a name="4121260-4272022"></a>4.12.126.0 (4/27/2022)

In diesem Update eingeführt:
- IT-Administratoren können ein Teams-Räume-Gerät registrieren, um öffentliche Vorschaufeatures über die XML-Einstellung zu erhalten. Nach der Registrierung erhält das Gerät Beta-Features. Alle Features, die zu Betatests gehören, werden in [der öffentlichen Vorschau von Microsoft Teams angekündigt – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)<sup>1,2</sup>  
- IT-Administratoren können die Anzeigeauflösung im Vorderraum festlegen und remote über DIE XML-Einstellungen<sup>2</sup> skalieren.
- IT-Administratoren können die Microsoft-Rauschunterdrückung über DIE XML-Einstellung<sup>3</sup> deaktivieren. 
- IT-Administratoren können die Bereinigung von Downloadordnern auf dem Gerät über die Registrierungsschlüsseleinstellung 4 außer Kraft setzen<sup>.</sup>
- Ermöglichen der Teilnahme von Benutzern an Teams-Besprechungen, die in einer anderen Cloud gehostet werden (d. h., GCCH-Kunde können an Teams-Besprechungen teilnehmen, die in der kommerziellen Cloud gehostet werden, und umgekehrt) 
- Teams-Räume blockieren jetzt das Starten des Edgebrowsers aus URLs in PowerPoint Live als zusätzliche Sicherheitsmaßnahme für Teams-Räume mit Touchanzeigen 
- Die Oberfläche "Jetzt besprechen" wurde verbessert, um Anweisungen für Benutzer hinzuzufügen, um Benutzer zum Chatroom einzuladen. 
- Unterstützung für Windows 10 21H2-Featureversion für Teams-Räume   
- Neuer Cortana-Einstiegspunkt auf dem Startbildschirm, Schaltfläche "Freigeben/Präsentieren" ist zurück 

> <sup>1</sup> Anweisungen für die Registrierung von MTR-Windows-Geräten für die öffentliche Vorschau finden Sie [hier](../public-preview-doc-updates.md#enable-public-preview)
> 
> <sup>2</sup> Auflösung der Anzeige vor dem Raum und Remoteskalierung über XML finden Sie [hier](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)
>
> <sup>3</sup> Derzeit wird nur die Administratoreinstellung veröffentlicht. Die Benutzersteuerung und Aktivierung der Rauschunterdrückung folgt nach der Version 4.12 im Mai 2022. 
>
> <sup>4</sup> Anweisungen zum Aufräumen von Geräten finden Sie [hier](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)
> 
> 
> [!NOTE]
> Windows 10 21H2-Featureupdate wird nach 7 Tagen nach der Installation der Anwendung aktualisiert, oder Administratoren können stattdessen manuelle Updates verwenden, um die Installation zu beschleunigen. Microsoft Teams-Räume Anwendungsversion 4.12 mit diesen Änderungen beginnt mit dem Rollout im April 2022 und dem Rollout in 2-3 Wochen. Die Anwendungsupdates werden über den Windows Store bereitgestellt, und die Anwendung wird automatisch installiert. Dies wird nur für Microsoft Teams-Räume unter Windows eingeführt. Was Sie zur Vorbereitung tun müssen: Möglicherweise möchten Sie Ihre Benutzer über diese aktualisierte Erfahrung informieren und Ihre Schulung und Dokumentation entsprechend aktualisieren.

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

In diesem Update eingeführt:
- Fehlerkorrektur für Kamerarahmen, die alle Inhalte in der Kameraansicht verbessern.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

In diesem Update eingeführt:
- Layout der ersten Zeile (Vorschau) für MTR unter Windows<sup>1</sup> 
- Admin Einstellung, um das Layout der ersten Zeile als Standard festzulegen  
- Jetzt besprechen und App-Update nur für Teams aufrufen, Teams-Standardclientmodi<sup>1,2</sup>
- Wechseln zwischen mehreren Videokameras in<sup>Teams-Besprechungen 1</sup> 
- Standardeinstellung der Videokamera 
- Update des Cortana-Push-to-Talk-Symbols auf der MTR-Konsole 
- Azure AD Premium 1-Lizenzeinschluss in Room Standard- und Premium-SKUs 
- AAD-Richtlinien für bedingten Zugriff unterstützen<sup>3</sup> 
- Standardmäßig aktivierte Cortana-Sprachaktivierung in der Windows-Willkommensseite
- Remote-PTZ-Steuerelemente unterstützen<sup>4</sup>

> <sup>1</sup> Diese Features werden mithilfe des Teams-Webclients eingeführt und werden in den nächsten Wochen eingeführt. Weitere Informationen zu [Microsoft Teams-Updates](../teams-client-update.md) finden Sie hier.
> 
> <sup>2</sup> Teams-Räume unter Windows, die nur in Microsoft Teams ausgeführt werden, oder Skype for Business und Microsoft Teams (Standard) werden mit neuen Besprechungs- und Anruferfahrungen aktualisiert, andere Modi sind von diesem Update jedoch nicht betroffen.
> 
> <sup>3</sup> Weitere Informationen zum Einrichten von [AAD-Richtlinien für bedingten Zugriff](../rooms/rooms-authentication.md#azure-ad-conditional-access) für Teams-Räume.
> 
> <sup>4</sup> Dieses Feature erfordert, dass IT-Administratoren die App für Remote-PTZ-Steuerelemente des Teams-Desktopclients konfigurieren.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>Teams-Räume Webclientupdate (Dezember 2021)

In diesem Update eingeführt:
- Teilen des Videolayouts auf zwei Front-of-Room-Bildschirme, wenn Inhalte nicht freigegeben werden

### <a name="teams-rooms-web-client-update-october-2021"></a>Teams-Räume Webclientupdate (Oktober 2021)

In diesem Update eingeführt:
- Einheitliche Listensteuerung mit Dem Teams-Desktopclient mit strukturierter Besprechungsgruppierung, Besprechungsoptionen und Steuerelementen für Referenten/Teilnehmer, Erhöhung der Sortierreihenfolge der Hand und Möglichkeit, Benutzer aus Chat oder Besprechungseinladung direkt aus der Teilnehmerliste einzuladen 
- Ausrichtung von Universal bar call controls with desktop client in meeting call controls, Layout button and meeting status information
- Unterstützung des dynamischen Katalogs für einzel- und duale Raumvorschauen
- Einheitliche Layoutauswahl für die Option "Raum vorn" konsolidiert
- Spotlight oder Anheften mehrerer Teilnehmer in Teams-Besprechungen
- Unterstützung großer Besprechungen mit Referenten-/Teilnehmersteuerelementen, die durch Tippen auf Teilnehmer aus der Teilnehmerliste zugänglich sind
- Möglichkeit, eine Besprechung für Besprechungen zu sperren, in denen der Raum organisiert ist, sowie das Bewusstsein für gesperrte Besprechungen
- Unterstützung der Nutzung des Referentenmodus (Weatherman), wenn ein Remotebenutzer Inhalte mit der Referentenansichtsoption teilt
- Reaktionsunterstützung in Teams-Besprechungen 

> [!NOTE]
> Webclientupdates sind für alle Teams-Räume mit den Anwendungsversionen 4.10 und 4.9 verfügbar. Administratoren können sich in kürze für Teams-Räume Public Preview-Programm registrieren, um den Einstieg in die Webclientfeatures zu erreichen.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

In diesem Update eingeführt:
- Die Raumfernbedienung ermöglicht es Benutzern, die grundlegenden Funktionen des Raums mithilfe von Teams auf ihrem Mobilgerät zu steuern *
- Logitech scribe content camera support for BLE button for sharing into meeting
- Chatblasen stellen Benachrichtigungen für den Besprechungschat bereit, um mithilfe des Besprechungschats auf das Gesagte aufmerksam zu machen *
- Unterstützung für große Kataloge und den Zusammen-Modus ist jetzt in GCC High verfügbar
- Neue Fähigkeiten zu Cortana hinzugefügt, Person nach Namen zur Besprechung hinzufügen und nach Namen anrufen 
- Cortana Push to Talk ist standardmäßig auf allen Geräten aktiviert. Weitere Informationen finden Sie [unter Cortana-Sprachunterstützung in Teams](../cortana-in-teams.md).

> [!NOTE]
> Veralteter 19H1-Support. Min. Betriebssystemversion, die von 4.10 unterstützt wird, ist 19H2.

> [!NOTE]
> *Diese Features werden mithilfe des Teams-Diensts eingeführt und funktionieren mit allen Anwendungsversionen, die größer als 4.9 sind.

> [!NOTE]
> Um sowohl über die Teams Mobile-App als auch über MTR-W an der geplanten Besprechung teilzunehmen, suchen Sie das Raumkonto in der Liste in der Teams Mobile-App, und drücken Sie das Menü "Diesen Raum steuern", und Sie können die Anrufsteuerung über die App steuern.

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

In diesem Update eingeführt:
- Der Modus "Nur Microsoft Teams" ist jetzt in den Anwendungseinstellungen verfügbar, sodass Sie kein Skype for Business Konto mehr einrichten müssen. In diesem Modus nehmen geräte, die nur im Teams-Modus angemeldet sind, als Gastbenutzer Skype for Business Besprechungen teil.
- Fix für HDMI-Audio, was zu einer geringeren Anruflautstärke führt. Das HDMI-Audiofeature wird automatisch für alle Geräte mit Anwendungsbuild 4.9.12.0 aktiviert.

> [!NOTE]
> Wenn Skype for Business das Ende des Lebenszyklus erreicht, empfiehlt es sich, auf den Nur-Teams-Modus zu aktualisieren.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

In diesem Update eingeführt:
- Windows 10 20H2-Support 

> [!NOTE]
> Crestron UC-Engine (BIOS-Versionsdatum mit "KYSKLi") Teams-Räume Kompatibilitätsprobleme aufweisen, und aktualisierte Treiber werden in naher Zukunft von System-OEMs bereitgestellt. Windows 10 20H2 wird diesen Geräten nicht angeboten. Weitere Informationen zur Unterstützung von Windows-Versionen finden Sie [unter Windows 10 Versionsunterstützung](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

In diesem Update eingeführt:
- Behebung eines Problems, bei dem Rauminformationen auf Teams-Räume Konsolen nicht für Raumkonten angezeigt werden, die in der globalen Adressliste (GAL) ausgeblendet sind

> [!NOTE]
> GCCH-Kunden können das Upgradepaket von [einem Microsoft Teams-Räume Gerät manuell aktualisieren](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

In diesem Update eingeführt:
- Unterstützung von Government Community Cloud High (GCCH) für Teams-Räume. GCCH-Kunden mit vorhandenen Teams-Räume-Geräten können Version 4.8.19.0 von [einem manuellen Update eines Microsoft Teams-Räume Geräts](manual-update.md) herunterladen.
- Teilnehmen an Zoombesprechungen mit besserer Videoqualität (Unterstützung von 720p) und Empfangen der Videogalerie der Teilnehmer
- Skype for Business Banner für Anmeldefehler wurde für den Standardmodus von Teams entfernt. Diese Änderung unterstützt Organisationen beim Entfernen Skype for Business Infrastruktur
- Die Verknüpfungs-Analyse von Teams-Besprechungen behandelt jetzt die sicheren Links von Microsoft Defender Advanced Threat Protection, um den nahtlosen Beitritt zu externen Teams zu ermöglichen.
- Behebung des Problems bei der Skalierung freigegebener Inhalte in Skype for Business Besprechungen, wenn auf dem PC des Sharers in Windows ein benutzerdefinierter DPI-Wert festgelegt ist
- Qualitäts- und Zuverlässigkeitskorrekturen

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

In diesem Update eingeführt:
- Qualitäts- und Zuverlässigkeitskorrekturen

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

In diesem Update eingeführt:

- Teilen von HDMI-Audio für Besprechungsteilnehmer in Teams-Besprechungen
- Cortana-Sprachfertigkeiten (Vorschau)
- Verhindern Sie das Aufheben der Stummschaltung basierend auf Audioberechtigungen, wenn Teams-Räume als Teilnehmer beitritt. Weitere Informationen finden Sie unter [Verwalten von Teilnehmeraudioberechtigungen in Teams-Besprechungen](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Spotlight-Video einer Person aus der Teams Room-Konsole und Nutzen von hervorgehobenem Video auf Raumanzeigen

> [!NOTE]
> Cortana-Sprachfertigkeiten sind für ausgewählte Audioperipheriegeräte für Mandanten im USA verfügbar. In Zukunft werden weitere Länder oder Regionen hinzugefügt. Weitere Informationen finden Sie [unter Cortana-Sprachunterstützung in Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

In diesem Update eingeführt:

- Fix für weißen Halbbildschirm beim Aufrufen der Bildschirmtastatur in der Teams-Besprechung

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

In diesem Update eingeführt:

- Weitere Videos mit 3x3-Videogalerie vor Raumanzeigen anzeigen  
- Starten lokaler Live-Untertitel von MTR
- Teilnehmen an Zoombesprechungen von Teams-Räume mit direktem Gastbeitritt (Vorschau)

> [!NOTE]
> 3x3-Videogalerie und lokale Live-Untertitel werden über den Microsoft Teams-Dienst bereitgestellt. Diese Features sind für alle Teams-Räume Geräte mit Anwendungsversion 4.5.37.0 und höher verfügbar.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

In diesem Update eingeführt:

- Koordinierte Besprechungen zwischen Microsoft Teams und Surface Hub 2S
- Beheben eines Anmeldefehlers bei Skype for Business, wenn [Windows 10 Update KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) oder [Windows 10 Update KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) installiert ist

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

In diesem Update eingeführt:

- Teilnehmen an Cisco Webex-Besprechungen von Teams-Räume mit direktem Gastbeitritt
- Aktivieren und automatische Registrierung von Teams Admin Center
- Windows 10 1909 Release-Support
- Wechseln zum Layout des Videokatalogs, auch wenn Inhalt vorhanden ist
- Unterstützung virtueller Raise Hands für Teilnehmer und Steuerelemente für Referenten
- Anpassbare Standardlautstärkeeinstellung für Konferenzen und Standardlautsprecher
- Suchen und Aufrufen von Verbundbenutzern (Mandant) aus dem Teams-Raum

> [!IMPORTANT]
> Version 4.5 ist die letzte Version, die Windows 10 Version 1803 unterstützt. Zukünftige Versionen werden systemen mit Windows 10 Version 1803 nicht angeboten. Weitere Informationen zur Unterstützung von Windows-Versionen finden Sie [unter Windows 10 Versionsunterstützung](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

In diesem Update eingeführt:

- Qualitäts- und Zuverlässigkeitskorrekturen
- Fix für das Problem "Die Anwendung wird nach dem Update auf 4.4.41.0 nicht gestartet"

> [!NOTE]
> Wenn Ihr Gerät nicht automatisch auf Version 4.4.63.0 aktualisiert wird, führen Sie die Schritte in [Microsoft Teams-Räume Anwendung nach dem Update auf Version 4.4.41.0 nicht gestartet wird](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update), um das Problem zu beheben.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

In diesem Update eingeführt:

- Zuverlässigkeitskorrekturen für den Anwendungsstart in Windows 10 Kiosk

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

In diesem Update eingeführt:

- Unterstützung der modernen Authentifizierung für Exchange und Skype for Business
- Unterstützung für dynamische Notrufe für Teams (Dienstkomponenten erforderlich und mithilfe von Teams-Clientringen veröffentlicht)
- Möglichkeit zum Deaktivieren doppelter Inhalte außerhalb der Besprechung für duale Anzeigeräume mitHILFE von XML
- Begrüßungsbildschirm der Anwendung
- Hinweise zu Open Source Software (OSS) in den Geräteeinstellungen

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

In diesem Update eingeführt:

- Richtlinienupdates für "Windows Aktualisierungen for Business"
- Fix für Geräteereignisse, in denen fehlerberichterstattung in Azure Monitor angezeigt wird

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

In diesem Update eingeführt:

- Ein Fix für ein Problem beim Ändern der Fenstergröße/Flackern, das in bestimmten Konfigurationen auftritt
- Kalenderverarbeitung für Besprechungen von Drittanbietern entfernt
- Cortana-Statuseinstellung entfernt

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

In diesem Update eingeführt:

- Automatisches Annehmen von näherungsbasierten Anrufen und Administratoreinstellungen, um dies zu steuern
- Aktualisieren der Benutzeroberfläche Admin Einstellungen unter Hinzufügung der Gerätekonfiguration auf der Registerkarte "Info"
- Raumsteuerung zurück zum Hauptbildschirm
- SKU des Besprechungsraums in GCC verfügbar
- Unterstützung von Inhaltskameras für Surface Pro-basiertes System (mindestens erforderlicher App-Build: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

In diesem Update eingeführt:

- Windows 10 1903-Support. Windows 10 1903-Update wird in einigen Tagen nach dem App-Update angeboten
- Korrekturen für Bildschirmtastaturen werden nicht zuverlässig angezeigt

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

In diesem Update eingeführt:

- Eine neue Inhaltskamerafunktion, mit der Benutzer ein herkömmliches Whiteboard intelligent in ihre Teams-Besprechung einbeziehen können
- Zusätzliche Verbesserungen an der Konsolen-UI, um die Übersichtlichkeit zu reduzieren und die Einstellungen in eine neue Seitenleiste zu verschieben, auf die über "Mehr" auf der Konsole zugegriffen wird
- Deaktivierte Schaltfläche "Freigabeschacht", wenn das lokale Inhaltskabel nicht verbunden ist oder eine Inhaltskamera nicht angeschlossen ist
- Es wurde ein Problem mit der Bildschirmtastatur behoben, bei dem sie erst nach einem MTR-Systemneustart zum ersten Mal angezeigt wurde.
- Qualitäts- und Zuverlässigkeitskorrekturen

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

In diesem Update eingeführt:

- Skype Room System Store-App wird in "Microsoft Teams-Räume" umbenannt
- Microsoft Teams-Räume Konsolenbenutzeroberfläche neu ausgerichtet auf Microsoft Teams
- Designupdate: Benutzerdefiniertes Hintergrundbild nur vor Raumanzeigen beibehalten und den Konsolenhintergrund zu einer neutralen Farbe machen, um sicherzustellen, dass die Steuerelemente der Konsolen-Benutzeroberfläche den Farbkontrast erfüllen – Barrierefreiheitsanforderungen
- Universelle Leiste für Anrufsteuerungen in Besprechungen für Teams-Anrufe/-Besprechungen, um eine konsistente Benutzererfahrung mit Microsoft Teams-PCs/ Web-/Mobile-Clients<sup>zu ermöglichen 1</sup>
- Bewertung von Feedback zur Anrufqualität nach Teams-Anrufen/-Besprechungen<sup>1</sup>
- Empfangen/Rendern von Microsoft Whiteboard auf Microsoft Teams-Räume Anzeige vor dem Raum, wenn sie vom PC/ Web/ Mobile Teams-Client<sup>1</sup> <sup>2</sup> freigegeben wird
- Die Unterstützung für Windows 10 Version 1809-Upgrades wurde aufgrund von Kompatibilitätsproblemen mit Microsoft Teams-Räume Client entfernt. Windows 10 Version 19H1-Unterstützung wird in zukünftigen Versionen hinzugefügt

<sup>1</sup> Microsoft Teams-Dienstrollout mithilfe von Teams-Ringen. Dieses Feature ist möglicherweise früher oder später als das Clientupdate 4.0.105.0 verfügbar.

<sup>2</sup> Erfordert, dass IT-Administratoren Microsoft Whiteboard aktivieren. Wenn Sie über eine Bildschirmvorschau mit Toucheingabe verfügen, müssen Sie mehrere Touchanzeigen mithilfe von Windows-Einstellungen mit Geräteadministratoranmeldung kalibrieren, um Microsoft Whiteboard für die Zusammenarbeit von einer Raumanzeige zu verwenden, die in einer Teams-Besprechung freigegeben ist.

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

In diesem Update eingeführt:

- Behebt ein Problem mit der Funktion "Feedback geben"
- Optimierungen zur Vorbereitung auf das bevorstehende Microsoft Teams-Räume Geräteupgrade auf Windows 10 Version 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

In diesem Update eingeführt:

- Fix für den Fehler "Beim App-Start hängen", der Geräte auf älteren Windows 10 RS2-Build betrifft.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

In diesem Update eingeführt:

- DTMF-Tastatur für P2P-Besprechungen und PSTN-Anrufe in Microsoft Teams. Um Microsoft Teams zum Standardanrufclient zu machen, müssen Administratoren "IsTeamsDefaultClient" auf "true" festlegen.
- Anheften des eingehenden Videos eines Remoteteilnehmers an den Vollbildmodus auf der Raumanzeige. Verwenden des Befehls "Anheften" aus der Teilnehmerliste auf der Konsole
- Verbesserungen an Wartebereichsbenachrichtigungen mit zusätzlicher Benachrichtigung "Vor dem Raum"
- Das Umwandlungssymbol für die Vorder- und Raumanzeige wurde entfernt, wenn der Bluetooth-Beacon auf Microsoft Teams-Räume Gerät nicht aktiviert ist.
- Beheben eines Problems mit der Lautstärkeregelung in Teams-Besprechungen

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

In diesem Update eingeführt:

- Anzeigen von Inhalten auf beiden Front-of-Room-Displays (FoR) auf Zwei-Bildschirm-Raumsystemen
- Verbesserungen bei der Benutzeroberfläche von Design und Raumfront
- Clientseitige TLS 1.2-Unterstützung. Für lokale Kunden erfordert die Aktivierung der Kommunikation über TLS 1.2 für Microsoft Teams-Räume Skype for Business Server kumulatives Update 9 (CU9) 2015 oder Skype for Business Server kumulatives Update 1 (CU1) von 2019.

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

In diesem Update eingeführt:

- Unterstützung der dualen Anzeige (Vor dem Raum) für Teams-Besprechungen

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

In diesem Update eingeführt:

- Qualitäts- und Zuverlässigkeitskorrekturen

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

In diesem Update eingeführt:

- Codeänderungen, die erforderlich sind, um die Microsoft Teams-Räume-App für ein späteres Windows 10 Version 1803-Upgrade vorzubereiten
- Behebung eines Formatierungsproblems mit lokalisierten EULAs (speziell Norwegisch), wodurch verhindert wird, dass das Setupfenster der EULA OOBE weitergeht
- Codeänderungen, die erforderlich sind, um Microsoft Teams-Räume Anwendung auf älteren Lync Room Systems auszuführen. Weitere Informationen [finden Sie hier](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

In diesem Update eingeführt:

- Hotfix für Crestron-Anwendung, der nicht gestartet wird, auf den normalerweise zugegriffen werden kann, wenn die App-Schaltfläche auf einem Crestron SR-Gerät gedrückt wird. Microsoft Teams-Räume Nach der Installation von 4.0.19.0 ist ein Neustart der App erforderlich.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

In diesem Update eingeführt:

- Featureverbesserungen "Problem melden" im Teams-Modus (entspricht "Feedback geben" im Skype for Business Modus)
- Aktivieren der Rückfallmöglichkeit von Teams in Skype for Business-Modus für SIP-Anrufe
- Verbesserungen bei der Barrierefreiheit (Sprachausgabe, Bildschirmlupe)
- App automatisch neu starten, wenn dies erforderlich ist, nachdem Änderungen an der XML-Bereitstellung angewendet wurden
- Verschiedene Korrekturen

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

In diesem Update eingeführt:

- Dieses Update ermöglicht die Unterstützung von Skype for Business und Teams-Besprechungen auf Raumsystemen.This update enables both Skype for Business *and* Teams meetings support on Room Systems devices. Teams ist standardmäßig deaktiviert, sobald das Update angewendet wurde. Administratoren können Teams lokal in den Geräteeinstellungen oder über einen XML-Remote-Push aktivieren.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

In diesem Update eingeführt:

- Fix zur Behebung von Fehlern, die auf einigen Systemen während des App-Starts beobachtet wurden.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

In diesem Update eingeführt:

- Änderungen, die es Microsoft ermöglichen, Windows Aktualisierungen flexibler zu verwalten.
- Keine Änderung an der Endbenutzererfahrung.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

In diesem Update eingeführt:

- Beheben von Problemen mit der Reaktionsfähigkeit der Konsole auf Surface Pro 2017-basierten Geräten, die mit zwei Front-of-Room-Displays und Videoaufnahme verbunden sind
- Automatische Überprüfung, um sicherzustellen, dass auf dem System das neueste Bereitstellungsskript ausgeführt wird

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

In diesem Update eingeführt:

- Fix zur Verbesserung des OSK-Verhaltens (Bildschirmtastatur) in Systemen mit Windows 10 Version 1709
- Verbesserungen bei der Vorbereitung auf zukünftige Betriebssystemupdates

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

In diesem Update eingeführt:

- Anwendung zur Verbesserung der Telemetrie aktualisiert

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

In diesem Update eingeführt:

- Behebt ein Problem, bei dem zeitweilige Probleme beim Teilnehmen an Besprechungen auftreten können.
- Behebt ein Problem, von dem bekannt ist, dass es zu einem "Hängen" des Geräts führt.

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

In diesem Update eingeführt:

- Fehler-/Absturzkorrekturen zur Verbesserung der Stabilität
- Unterstützung für Konsole mit variabler Größe
- Ausladen der Peripherieaudioverarbeitung (zusätzliche Medien-Zulassungsliste)
- Optimierungen, die IT-Experten das Erstellen von Selbstverwaltungsimages mit Windows 10 Version 1709 Januar Update und höher ermöglichen.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

In diesem Update eingeführt:

- Behebt ein Problem mit der Funktion "Feedback geben".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

In diesem Update eingeführt:

- Unterstützung für Dock-Hardware der [Polycom MSR-Serie](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Unterstützung der [Logitech Brio](https://www.logitech.com/product/brio)
- Behebt ein Problem, bei dem Anzeigen (Konsole und Front-of-Room) nicht in den Ruhemodus wechseln, wenn keine Aktivität im Raum vorhanden ist.

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

In diesem Update eingeführt:

- Wird auf einem Surface Pro(2017)-Tablet ausgeführt
- Unterstützt Windows 10 Enterprise Creator's Update (Englisch, Build 1703)
- Unterstützung für [Crestron](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system) SR-Dockhardware
- OEM-Unterstützung für Umgebungssteuerelemente (Crestron)

Die 64-Bit-Version von Windows 10 Enterprise Anniversary-Edition (Englisch, Version 1607) wird ab Microsoft Teams-Räume Version 3.0.12.0 (Update 3) nicht mehr unterstützt.

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

In diesem Update eingeführt:

- Behebt Probleme, die bei der Suche nach Verbundbenutzern über das Suchfeld "Teilnehmer" beobachtet wurden. Vor diesem Fix wurden Suchergebnisse für externe Verbundbenutzer möglicherweise nicht ordnungsgemäß aufgelöst und stattdessen falsche Ergebnisse zurückgegeben.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

In diesem Update eingeführt:

- Dual-Screen Unterstützung (für legacy system parity)
- Designs (integrierte Designs und die Möglichkeit zum Festlegen eines benutzerdefinierten Designs)
- Möglichkeit, Feedback für öffentliche Builds zu geben
- Verbesserte Telemetrie rund um die Zuverlässigkeit des Besprechungsbeitritts
- Verbesserte OMS-Berichterstellung
- Möglichkeit für IT-Admin, Geräte remote zu konfigurieren

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

In diesem Update eingeführt:

- In-App-Benutzerauswahl für Audio- und Video-USB-Geräte im Besprechungsraum
- Integrierte Raumkonsolen-Statusberichte für Kunden, die Microsoft Operations Management Suite verwenden, jetzt Azure Monitor

### <a name="release-to-market-1272016"></a>Markteinführung (7.12.2016)

**Feature(e):**

 **Für Skype for Business konzipiert**

- One-Touch-Teilnahme an Skype-Besprechungen
- Skype-Besprechung Für Räume mit bildschirmfüllendem HD-Video und HD-Breitbandaudio optimiert
- Alle Teilnehmer können über ihr bevorzugtes Gerät eine Verbindung mit der Skype-Besprechung herstellen – ganz gleich, wo sie sich gerade aufhalten.
- Sie können Personen aus Ihrem Verzeichnis, wo Sie ihre Verfügbarkeit sofort sehen können, oder telefonisch einladen.
- Unterstützt Skype for Business-PSTN-Konferenzen und -PSTN-Anrufe als Ersatz für das eigenständige Konferenztelefon in Ihrem Raum.

 **Neue Möglichkeiten für Besprechungsräume**

- Eigene Skype-Besprechungs-App mit Optimierung für einen Touchcontroller in der Tischmitte und einen großen Bildschirm vorn im Raum
- Wiederverwenden vorhandener Investitionen in Ihrem Front-of-Room-Display oder Projektoren
- Für alle Arten von Besprechungsräumen geeignet – von kleinen Besprechungsräumen bis hin zu großen Konferenzräumen
- Für Skype for Business zertifizierte Audio- und Videogeräte für verschiedene Raumgrößen
- Integrierte kabelgebundene Erfassung zum Projizieren der Desktopfreigabe für den Raum und die Skype-Besprechung

 **Leicht bereitzustellen, einfach zu verwalten**

- Always-On-Appliance, die die Displays automatisch aktiviert, wenn personen im Raum erkannt werden
- Einfache Bereitstellung und Aktualisierung der UWP-App (Universal Windows Platform) für Skype-Besprechungen
- Feste Bindung des Geräts an die Skype-Besprechungs-App durch Windows AppLocker
- Überwacht und verwaltet als Windows 10 Enterprise Gerät über Intune und Configuration Manager (MDM)
- Zuverlässigkeit der Unternehmensklasse
- Geringer Aufwand für Endbenutzerschulungen dank der vertrauten Skype-Benutzeroberfläche
- Wird auf Surface Pro 4 Tablet ausgeführt

<a name="See"> </a>
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Vorbereiten der Umgebung](rooms-prep.md)

[Unterstützung für Microsoft Teams-Räume Current Branch-Versionen](rooms-lifecycle-support.md)

[Bekannte Probleme](known-issues.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)
