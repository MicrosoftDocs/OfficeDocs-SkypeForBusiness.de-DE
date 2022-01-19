---
title: Erstellen einer Anrufwarteschleife über Cmdlets
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Anrufwarteschleifen über Cmdlets konfigurieren.
ms.openlocfilehash: 8ffbef5541a230755bb7439507e3002a5cb92462
ms.sourcegitcommit: 268660f101609852f02f3f9d1a8436f2a99dade7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2022
ms.locfileid: "62071110"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Erstellen einer Anrufwarteschleife über Cmdlets

## <a name="assumptions"></a>Annahmen
1)  PowerShell ist auf dem Computer installiert
- Einrichten Ihres Computers für [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
- MSTeams-Modul installiert ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- MSOnline-Modul installiert ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  Sie verfügen über Mandantenverwaltungsrechte
3)  Sie haben Ihr Microsoft Teams Telefon
4)  Die agents, Verteilerlisten und Teams weiter unten genannten Kanäle wurden bereits erstellt.

Hinweis: Das unten Teams Kanal-Cmdlet ist Teil der öffentlichen Preview-Version Teams PowerShell-Moduls.  Weitere Informationen finden Sie unter [Installieren Teams PowerShell Public Preview](teams-powershell-install.md) und Microsoft Teams [PowerShell-Versionshinweise.](teams-powershell-release-notes.md)

Benutzer, die das MicrosoftTeams-Modul bereits installiert haben, sollten sicherstellen, dass die neueste ````Update-Module MicrosoftTeams```` Version installiert ist.


## <a name="scenario"></a>Szenario

Die folgenden drei Anrufwarteschleifen werden erstellt:

Informationen zur Anrufwarteschleife für Verkaufsanrufe:
- Von vorn automatische Telefonzentrale: Ja
- Direkte Anrufe über das Festnetz: Nein
- Sprache: Englisch USA
- Begrüßung: Keine
- Musik im Halteraum: Wiedergabe einer Audiodatei
- - Dateiname: sales-hold-in-queue-music.wav
- Anrufbeantwortung: Benutzer
- - Bill@contoso.com
- - Mary@contoso.com
- Konferenzmodus: Ein
- Routingmethode: Attendant
- Anwesenheitsbasiertes Routing: Aus
- Telefonmitarbeiter können die Anrufanrufe abmelden: Ja
- Benachrichtigungszeit des Telefonmitarbeiters: 15
- Anrufüberlaufbehandlung: 200
- - Redirect to: Adele@contoso.com
- Behandlung von Anruftimeouts: 120 Sekunden
- - Redirect to: Adele@contoso.com

Support-Informationen zur Anrufwarteschleife:
- Von vorn automatische Telefonzentrale: Ja
- Direkte Anrufe über das Festnetz: Nein
-   Sprache: Englisch (Großbritannien)
-   Begrüßung: Wiedergabe einer Audiodatei
-   - Dateiname: support-greeting.wav
-   Musik im Halteraum: Wiedergabe einer Audiodatei
-   - Dateiname: support-hold-in-queue-music.wav
-   Anrufbeantwortung: Supportverteilerliste
-   - Support@contoso.com
-   Konferenzmodus: Ein
-   Routingmethode: Längster Leerlauf
-   Anwesenheitsbasiertes Routing: N/A – standardmäßig aktiviert aufgrund des längsten Leerlaufs
-   Telefonmitarbeiter können die Anrufanrufe abmelden: Nein
-   Benachrichtigungszeit des Telefonmitarbeiters: 15
-   Anrufüberlaufbehandlung: 200
-   - Umleiten: Unterstützen von geteilten Voicemails
- - -   Wiedergabe einer Audiodatei (support-shared-voicemail-greeting.wav)
- - -   Transkription aktiviert
-   Behandlung von Anruftimeouts: 45 Minuten
-   - Umleiten: Unterstützen von geteilten Voicemails
- - - TTS: "Es tut uns leid, dass Sie lange gewartet haben und Ihren Anruf jetzt an die Voicemail übertragen."
- - - Transkription aktiviert


Informationen zur Anrufwarteschleife für die Zusammenarbeit:
- Vor den automatische Telefonzentrale: Nein
- Direkte Anrufe über das Festnetz: Nein (nur interne Anrufe)
-   Sprache: Französisch FR
-   Begrüßung: Keine
-   Musik im Halteraum: Standard
-   Anrufbeantwortung: Team: Einrichtungen
-   Anrufbeantwortungskanal: Helpdesk
-   - Kanalbesitzer: Fred@contoso.com
-   Konferenzmodus: Ein
-   Routingmethode: Round-1-1
-   Anwesenheitsbasiertes Routing: Ein
-   Telefonmitarbeiter können die Anrufanrufe abmelden: Nein
-   Benachrichtigungszeit des Telefonmitarbeiters: 15
-   Anrufüberlaufbehandlung: 200
-   - Verbindung trennen
-   Behandlung von Anruftimeouts: 45 Minuten
-   - Verbindung trennen


## <a name="login"></a>Anmeldung
Sie werden aufgefordert, Ihre Anmeldeinformationen als Teams ein.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>Verkaufswarteschlange
### <a name="create-audio-files"></a>Erstellen von Audiodateien
Ersetzen Sie "d: \\ " durch den Pfad, in dem die WAV-Dateien auf Ihrem Computer gespeichert sind.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>Benutzer-ID erhalten
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>Liste der unterstützten Sprachen
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Anrufwarteschleife erstellen
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>Lizenztypen erhalten
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuordnen eines Ressourcenkontos
Hinweis: Telefon nummer, die hier nicht erforderlich ist, da die Anrufwarteschleife durch eine Anrufwarteschleife vorne automatische Telefonzentrale
- ApplicationID
- - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
- - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>Supportwarteschlange
### <a name="create-audio-files"></a>Erstellen von Audiodateien
Ersetzen Sie "d: \\ " durch den Pfad, in dem die WAV-Dateien auf Ihrem Computer gespeichert sind.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>Supportteam-Gruppen-ID erhalten
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>Liste der unterstützten Sprachen
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Anrufwarteschleife erstellen
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>Lizenztypen erhalten
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuordnen eines Ressourcenkontos
Hinweis: Telefon nummer, die hier nicht erforderlich ist, da die Anrufwarteschleife von einem Anrufwarteschleifen-Automatische Telefonzentrale
- ApplicationID
- - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
- - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>Einrichtungen, Anrufwarteschleife für zusammenarbeitliche Zusammenarbeit
### <a name="get-facilities-team-group-id"></a>Gruppen-ID der Gruppe "Einrichtungen erhalten"
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Hilfe-Helpdesk-Teamkanal-ID erhalten
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-ower-user-id"></a>Get Facilities Help Desk channel ower user ID
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Aufrufen der Ressourcenkonto-ID
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>Liste der unterstützten Sprachen
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Anrufwarteschleife erstellen
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>Lizenztypen erhalten
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuordnen eines Ressourcenkontos
Hinweis: Telefon nummer, die hier nicht erforderlich ist, da die Anrufwarteschleife von einem Anrufwarteschleifen-Automatische Telefonzentrale
- ApplicationID
- - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
- - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
