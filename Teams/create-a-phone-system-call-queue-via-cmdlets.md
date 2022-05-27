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
ms.openlocfilehash: 8d62d3648d35cc302e333c2efa552bb2094cb14d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674577"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Erstellen einer Anrufwarteschleife über Cmdlets

## <a name="assumptions"></a>Annahmen

1. PowerShell ist auf Ihrem Computer installiert
   - Einrichten Ihres Computers für [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
   - MSTeams-Modul installiert

     ```powershell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - MsOnline-Modul installiert

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. Sie haben Mandantenverwaltungsrechte
3. Sie haben Microsoft Teams Telefon erworben
4. Die unten genannten Agents, Verteilerlisten und Teams Kanäle wurden bereits erstellt.

Hinweis: Das unten verwendete cmdlet Teams Channel ist Teil der Public Preview-Version von Teams PowerShell-Modul.  Weitere Informationen finden Sie unter ["Installieren Teams öffentlichen PowerShell-Vorschau](teams-powershell-install.md)" und [unter Microsoft Teams PowerShell-Versionshinweisen](teams-powershell-release-notes.md).

Benutzer, die das MicrosoftTeams-Modul bereits installiert haben, sollten `Update-Module MicrosoftTeams` sicherstellen, dass die aktuellste Version installiert ist.

## <a name="scenario"></a>Szenario

Die folgenden drei Anrufwarteschleifen werden erstellt:

Informationen zur Warteschlange für Verkaufsanrufe:

- Vorne von der automatischen Telefonzentrale: Ja
- Direkte Anrufe aus dem PSTN: Nein
- Sprache: Englisch USA
- Gruß: Keine
- Musik im Haltebereich: Wiedergeben einer Audiodatei
  - Dateiname: sales-hold-in-queue-music.wav
- Anrufbeantwortung: Benutzer
  - Bill@contoso.com
  - Mary@contoso.com
- Konferenzmodus: Aktiviert
- Routingmethode: Telefonzentrale
- Anwesenheitsbasiertes Routing: Aus
- Telefonisten können die Anrufannahme deaktivieren: Ja
- Anruf-Agent-Benachrichtigungszeit: 15
- Anrufüberlaufbehandlung: 200
  - Umleiten zu: Adele@contoso.com
- Behandlung des Anruftimeouts: 120 Sekunden
  - Umleiten zu: Adele@contoso.com

Support-Informationen zur Anrufwarteschleife:

- Vorne von der automatischen Telefonzentrale: Ja
- Direkte Anrufe aus dem PSTN: Nein
- Sprache: Englisch UK
- Gruß: Wiedergeben einer Audiodatei
  - Dateiname: support-greeting.wav
- Musik im Haltebereich: Wiedergeben einer Audiodatei
  - Dateiname: support-hold-in-queue-music.wav
- Anrufbeantwortung: Support-Verteilerliste
  - Support@contoso.com
- Konferenzmodus: Aktiviert
- Routingmethode: Längster Leerlauf
- Anwesenheitsbasiertes Routing: NV – standardmäßig aktiviert aufgrund des längsten Leerlaufs
- Anrufer können die Anrufannahme deaktivieren: Nein
- Anruf-Agent-Benachrichtigungszeit: 15
- Anrufüberlaufbehandlung: 200
  - Umleitung: Unterstützen von freigegebenen Voicemails
    - Wiedergeben einer Audiodatei (support-shared-voicemail-greeting.wav)
    - Transkription aktiviert
- Behandlung von Anruftimeouts: 45 Minuten
  - Umleitung: Unterstützen von freigegebenen Voicemails
    - TTS: "Wir entschuldigen uns, dass Sie lange gewartet haben und jetzt Ihren Anruf an die Voicemail durchweisen."
    - Transkription aktiviert

Informationen zur Warteschlange für gemeinsame Anrufe in Einrichtungen:

- Vorne von der automatischen Telefonzentrale: Nein
- Direkte Anrufe aus dem PSTN: Nein (nur interne Anrufe)
- Sprache: Französisch FR
- Gruß: Keine
- Musik im Haltebereich: Standard
- Anrufbeantwortung: Team: Einrichtungen
- Anrufbeantwortungskanal: Helpdesk
  - Kanalbesitzer: Fred@contoso.com
- Konferenzmodus: Aktiviert
- Routingmethode: Round Robin
- Anwesenheitsbasiertes Routing: Ein
- Anrufer können die Anrufannahme deaktivieren: Nein
- Anruf-Agent-Benachrichtigungszeit: 15
- Anrufüberlaufbehandlung: 200
  - Verbindung trennen
- Behandlung von Anruftimeouts: 45 Minuten
  - Verbindung trennen

## <a name="login"></a>Anmeldung

Sie werden aufgefordert, Ihre Teams Administratoranmeldeinformationen einzugeben.

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="sales-queue"></a>Vertriebswarteschlange

### <a name="create-audio-files"></a>Audiodateien erstellen

Ersetzen Sie "d:\\" durch den Pfad zum Speicherort der WAV-Dateien auf Ihrem Computer.

```powershell
$content = Get-Content "d:\sales-hold-in-queue-music.wav" -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
```

### <a name="get-users-id"></a>Benutzer-ID abrufen

```powershell
$userAdeleID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity
$userSalesBillID = (Get-CsOnlineUser -Identity "sip:bill@contoso.com").Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity "sip:mary@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>Liste der unterstützten Sprachen abrufen

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Anrufwarteschleife erstellen

```powershell
New-CsCallQueue -Name "Sales" -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID "en-US"
```

### <a name="get-license-types"></a>Abrufen von Lizenztypen

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuweisen eines Ressourcenkontos

Hinweis: Telefon Nummer ist hier nicht erforderlich, da die Anrufwarteschleife von einer automatischen Telefonzentrale beendet wird.

- Applicationid
  - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
  - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Hinweis: Der unten gezeigte Lizenztyp (PHONESYSTEM_VIRTUALUSER) muss ein Lizenztyp sein, der vom Get-MsolAccountSku cmdlet oben aufgeführt ist.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Sales-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="support-queue"></a>Supportwarteschlange

### <a name="create-audio-files"></a>Erstellen von Audiodateien

Ersetzen Sie "d:\\" durch den Pfad zum Speicherort der WAV-Dateien auf Ihrem Computer.

```powershell
$content = Get-Content "d:\support-greeting.wav" -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content "d:\support-hold-in-queue-music.wav" -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content "d:\support-shared-voicemail-greeting.wav" -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
```

### <a name="get-support-team-group-id"></a>Gruppen-ID des Supportteams abrufen

```powershell
$teamSupportID = (Get-Team -displayname "Support").GroupID
```

### <a name="get-list-of-supported-languages"></a>Liste der unterstützten Sprachen abrufen

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Anrufwarteschleife erstellen

```powershell
New-CsCallQueue -Name "Support" -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID "en-US"
```

### <a name="get-license-types"></a>Abrufen von Lizenztypen

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuweisen eines Ressourcenkontos

Hinweis: Telefon Nummer ist hier nicht erforderlich, da die Anrufwarteschleife von einer automatischen Telefonzentrale beendet wird.

- Applicationid
  - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
  - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Hinweis: Der unten gezeigte Lizenztyp (PHONESYSTEM_VIRTUALUSER) muss ein Lizenztyp sein, der vom Get-MsolAccountSku cmdlet oben aufgeführt ist.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Support-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="facilities-collaborative-calling-queue"></a>Gemeinsame Anrufwarteschleife für Einrichtungen

### <a name="get-facilities-team-group-id"></a>Gruppen-ID des Facilities-Teams abrufen

```powershell
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
```

### <a name="get-facilities-help-desk-team-channel-id"></a>Abrufen der Helpdesk-Teamkanal-ID für Einrichtungen

```powershell
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
```

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>Abrufen der Benutzer-ID des Helpdesk-Kanalbesitzers für Einrichtungen

```powershell
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
```

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Im Auftrag des Aufrufens der Ressourcenkonto-ID abrufen

```powershell
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>Liste der unterstützten Sprachen abrufen

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Anrufwarteschleife erstellen

```powershell
New-CsCallQueue -Name "Facilities" -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID "fr-FR" -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
```

### <a name="get-license-types"></a>Abrufen von Lizenztypen

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuweisen eines Ressourcenkontos

**Hinweis**: Telefon Nummer ist hier nicht erforderlich, da die Anrufwarteschleife von einer automatischen Telefonzentrale an der Front beendet wird.

- Applicationid
  - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
  - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Hinweis: Der unten gezeigte Lizenztyp (PHONESYSTEM_VIRTUALUSER) muss ein Lizenztyp sein, der vom Get-MsolAccountSku cmdlet oben aufgeführt ist.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Facilities-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```
