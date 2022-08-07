---
title: Erstellen einer automatischen Telefonzentrale über Cmdlets
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Erfahren Sie, wie Sie automatische Telefonzentralen über Cmdlets konfigurieren
ms.openlocfilehash: fa52f84f822635505e3d3390855195ba579406f7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270140"
---
# <a name="create-an-auto-attendant-via-cmdlets"></a>Erstellen einer automatischen Telefonzentrale über Cmdlets

## <a name="assumptions"></a>Annahmen

1. PowerShell ist auf Ihrem Computer installiert

   - Einrichten Ihres Computers für [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
   - MSTeams-Modul installiert

     ```PowerShell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - MsOnline-Modul installiert

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. Sie haben Mandantenverwaltungsrechte
3. Sie haben Microsoft Teams Telefon erworben
4. Die unten genannten Anrufwarteschleifen wurden bereits im Anschluss an die Anleitung zum [Erstellen von Anrufwarteschleifen mit PowerShell-Cmdlets](create-a-phone-system-call-queue-via-cmdlets.md) eingerichtet.

**Hinweis**: Einige der cmdlets, auf die unten verwiesen wird, sind möglicherweise Teil der Public Preview-Version des Teams PowerShell-Moduls. Weitere Informationen finden Sie in der [öffentlichen Vorschau "Installieren von Teams PowerShell](teams-powershell-install.md) " und in den [Microsoft Teams PowerShell-Versionshinweisen](teams-powershell-release-notes.md).

Benutzer, die das MicrosoftTeams-Modul bereits installiert haben, sollten `Update-Module MicrosoftTeams` sicherstellen, dass die aktuellste Version installiert ist.

## <a name="scenario"></a>Szenario

Der folgende anruffluss der automatischen Telefonzentrale wird erstellt:

![Diagramm des Anrufflusses der automatischen Telefonzentrale, der mit Cmdlets erstellt wird.](media/create-a-phone-system-auto-attendant-via-cmdlets.png)

Zusätzliche Konfigurationsinformationen:

- Automatische Telefonzentrale: Contoso Main
  - Operator: Adele Vance
  - Spracheingaben aktivieren: Aus
  - Verzeichnissuche: Keine
  - Urlaub:
    - 1. Januar 2022
    - 24. Dezember 2022
    - 25. Dezember 2022

- Automatische Telefonzentrale: Contoso Dial by Name
  - Operator: Adele Vance
  - Zeitzone: UTC
  - Sprache: Englisch USA
  - Aktivieren von Spracheingaben: Ein
  - Gruß: Keine
  - Menü: TTS: "Bitte sagen oder geben Sie den Namen der Person ein, die Sie erreichen möchten. Um zum vorherigen Menü zurückzukehren, drücken Sie 9"
  - Verzeichnissuche: Nach Name wählen
  - Wählbereich: Vertriebs- & Supportmitglieder

## <a name="login"></a>Anmeldung

Sie werden aufgefordert, Ihre Teams-Administratoranmeldeinformationen einzugeben.

```PowerShell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="get-operator-information"></a>Abrufen von Operatorinformationen

```PowerShell
$operatorID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity

$operatorEntity = New-CsAutoAttendantCallableEntity -Identity $operatorID -Type User
```

## <a name="dial-by-name-auto-attendant---resource-account-creation"></a>Automatische Telefonzentrale für die Namensanwahl – Erstellung des Ressourcenkontos

**Hinweis**: Hier wird ein Ressourcenkonto erstellt, sodass in der automatischen Haupttelefonzentrale darauf verwiesen werden kann. Die eigentliche automatische Telefonzentrale für Namensanwahl wird später erstellt.

### <a name="get-license-types"></a>Abrufen von Lizenztypen

```PowerShell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuweisen eines Ressourcenkontos

**Hinweis**: Die Telefonnummer ist hier nicht erforderlich, da die Anrufwarteschleife von einer automatischen Telefonzentrale beendet wird.

- Applicationid
  - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
  - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07

```PowerShell
New-CsOnlineApplicationInstance -UserPrincipalName ContosoDialByNameAA-RA@contoso.com -DisplayName "Contoso Dial By Name AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoDialByNameAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "ContosoDialByNameAA-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$dialByNameApplicationInstanceID = (Get-CsOnlineUser "ContosoDialByNameAA-RA@contoso.com").ObjectID
```

## <a name="contoso-main-menu-auto-attendant"></a>Contoso-Hauptmenü – Automatische Telefonzentrale

### <a name="create-holiday-schedules"></a>Erstellen von Feiertagszeitplänen

```PowerShell
$dtr = New-CsOnlineDateTimeRange -Start "24/12/2022" -End "25/12/2022"

$christmasSchedule = New-CsOnlineSchedule -Name "Christmas" -FixedSchedule -DateTimeRanges @($dtr)

$dtr = New-CsOnlineDateTimeRange -Start "01/01/2022" -End "02/01/2022"

$newyearSchedule = New-CsOnlineSchedule -Name "New Year" -FixedSchedule -DateTimeRanges @($dtr)
```

### <a name="create-address-fax-and-email-information-prompt"></a>Adress-, FAX- und Email-Informationsaufforderung erstellen

```PowerShell
$addressPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To repeat this information at any time press the * key. Our mailing address is: 123 Main Street, Any town, Any Place, County. Our email address is: info@contoso.com. Our fax number is: 929-555-0151"
```

### <a name="create-holiday-prompts-and-menu-options"></a>Erstellen von Feiertagsaufforderungen und Menüoptionen

```PowerShell
$christmasGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the Christmas holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$christmasMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$christmasMenu = New-CsAutoAttendantMenu -Name "Christmas Menu" -MenuOptions @($christmasMenuOption)

$christmasCallFlow = New-CsAutoAttendantCallFlow -Name "Christmas" -Greetings @($christmasGreetingPrompt) -Menu $christmasMenu

$christmasCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $christmasSchedule.Id -CallFlowId $christmasCallFlow.Id

$newyearGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the New Year's holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$newyearMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$newyearMenu = New-CsAutoAttendantMenu -Name "New Year Menu" -MenuOptions @($newyearMenuOption)

$newyearCallFlow = New-CsAutoAttendantCallFlow -Name "New Year" -Greetings @($newyearGreetingPrompt) -Menu $newyearMenu

$newyearCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $newyearSchedule.Id -CallFlowId $newyearCallFlow.Id
```

### <a name="create-after-hours-schedules"></a>Erstellen von Zeitplänen nach Feierabend

```PowerShell
$timerangeMoFr = New-CsOnlineTimeRange -Start 08:30 -end 17:00

$timerangeSa = New-CsOnlineTimeRange -Start 10:00 -end 16:00

$afterHoursSchedule = New-CsOnlineSchedule -Name "After Hours Schedule" -WeeklyRecurrentSchedule -MondayHours @($timerangeMoFr) -TuesdayHours @($timerangeMoFr) -WednesdayHours @($timerangeMoFr) -ThursdayHours @($timerangeMoFr) -FridayHours @($timerangeMoFr) -SaturdayHours @($timerangeSa) -Complement
```

### <a name="create-after-hours-prompts-and-menu-options"></a>Erstellen von Aufforderungen nach Feierabend und Menüoptionen

```PowerShell
$afterHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices are now closed. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time."

$afterHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To leave a voicemail for our sales team press 1.To leave a message for our support team press 2.If you know the name of the person you would like to reach, press 3.For our address, email and fax information press 4."

$afterHoursMenuOption1Target = (Get-Team -displayname "Sales").GroupID

$afterHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption1Target -Type SharedVoiceMail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $afterHoursMenuOption1Entity

$afterHoursMenuOption2Target = (Get-Team -displayname "Support").GroupID

$afterHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption2Target -Type SharedVoicemail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $afterHoursMenuOption2Entity

$dialbynameAAOption3Target = (Get-CsOnlineUser -Identity "ContosoDialByNameAA-RA@contso.com").Identity

$dialbynameAAMenuOption3Entity = New-CsAutoAttendantCallableEntity -Identity $dialbynameAAOption3Target -Type applicationendpoint

$dialbynameAAMenuOption3 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone3 -CallTarget $dialbynameAAMenuOption3Entity

$afterHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt
```

### <a name="create-after-hours-menu-and-call-flow"></a>Menü "Nach Feierabend" und Anruffluss erstellen

```PowerShell
$afterHoursMenu = New-CsAutoAttendantMenu -Name "After Hours Menu" -MenuOptions @($afterHoursMenuOption1, $afterHoursMenuOption2, $dialbynameAAMenuOption3, $afterHoursMenuOption4) -Prompt $afterHoursMenuPrompt

$afterHoursCallFlow = New-CsAutoAttendantCallFlow -Name "After Hours Call Flow" -Greetings @($afterHoursGreetingPrompt) -Menu $afterHoursMenu

$afterHoursCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type AfterHours -ScheduleId $afterHoursSchedule.Id -CallFlowId $afterHoursCallFlow.Id
```

### <a name="create-open-hours-prompts-and-menu-options"></a>Erstellen von Eingabeaufforderungen und Menüoptionen für die Öffnungszeiten

```PowerShell
$openHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt " Thank you for calling Contoso."

$openHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "For Sales press 1. For Support press 2. If you know the name of the person you would like to reach, press 3. For our address, email and fax information, press 4. For all other inquiries press 0 to speak with the operator."

$openHoursMenuOption1Target = (Get-CsOnlineUser "Sales-RA@contoso.com").ObjectID

$openHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption1Target -Type applicationendpoint

$openHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $openHoursMenuOption1Entity

$openHoursMenuOption2Target = (Get-CsOnlineUser "Support-RA@contoso.com").ObjectID

$openHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption2Target -Type applicationendpoint

$openHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $openHoursMenuOption2Entity

$openHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt

$openHoursMenuOption0 = New-CsAutoAttendantMenuOption -Action TransferCallToOperator -DtmfResponse Tone0
```

### <a name="create-open-hours-menu"></a>Menü "Geöffnete Stunden" erstellen

```PowerShell
$openHoursMenu = New-CsAutoAttendantMenu -Name "Open Hours Menu" -MenuOptions @($openHoursMenuOption1, $openHoursMenuOption2, $dialbynameAAMenuOption3, $openHoursMenuOption4, $openHoursMenuOption0) -Prompt $openHoursMenuPrompt

$openHoursCallFlow = New-CsAutoAttendantCallFlow -Name "Open Hours Call Flow" -Greetings @($openHoursGreetingPrompt) -Menu $openHoursMenu
```

### <a name="create-auto-attendant"></a>Erstellen einer automatischen Telefonzentrale

```PowerShell
$autoAttendant = New-CsAutoAttendant -Name "Contoso Main" -DefaultCallFlow $openHoursCallFlow -CallFlows @($afterHoursCallFlow, $christmasCallFlow, $newyearCallFlow) -CallHandlingAssociations @($afterHoursCallHandlingAssociation, $christmasCallHandlingAssociation, $newyearCallHandlingAssociation) -LanguageId "en-US" -TimeZoneId "Eastern Standard Time" -Operator $operatorEntity
```

### <a name="get-license-types"></a>Abrufen von Lizenztypen

```PowerShell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuweisen eines Ressourcenkontos

- Applicationid
  - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
  - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07

```PowerShell
New-CsOnlineApplicationInstance -UserPrincipalName ContosoMainAA-RA@contoso.com -DisplayName "Contoso Main AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoMainAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "ContosoMainAA-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").Identity

$autoAttendantID = (Get-CsAutoAttendant -NameFilter "Contoso Main").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $autoAttendantID -ConfigurationType AutoAttendant
```

### <a name="get-list-of-unassigned-service-numbers"></a>Liste der nicht zugewiesenen Dienstnummern abrufen

```PowerShell
Get-CsPhoneNumberAssignment -PstnAssignmentStatus Unassigned -CapabilitiesContain VoiceApplicationAssignment
```

#### <a name="assign-available-phone-number"></a>Verfügbare Telefonnummer zuweisen
Hinweis: Der der Telefonnummer zugewiesene Verwendungsspeicherort muss mit dem dem Ressourcenkonto zugewiesenen Verwendungsspeicherort übereinstimmen.

```PowerShell
Set-CsPhoneNumberAssignment -Identity ContosoMainAA-RA@contoso.com -PhoneNumber +{spare number from output of above command} -PhoneNumberType CallingPlan
```

## <a name="dial-by-name-auto-attendant---completion"></a>Automatische Telefonzentrale für die Namensanwahl – Abschluss

### <a name="create-dial-scope"></a>Wählbereich erstellen

```PowerShell
$salesGroupID = Find-CsGroup -SearchQuery "Sales" | % { $_.Id }

$supportGroupID = Find-CsGroup -SearchQuery "Support" | % { $_.Id }

$dialScope = New-CsAutoAttendantDialScope -GroupScope -GroupIds @($salesGroupID, $supportGroupID)
```

### <a name="create-prompts-and-menu-options"></a>Erstellen von Eingabeaufforderungen und Menüoptionen

```PowerShell
$dialByNameMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Please say or enter the name of the person you would like to reach. To return to the previous menu press 9"

$dialByNameMenuOption9Target = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").Identity

$dialByNameMenuOption9Entity = New-CsAutoAttendantCallableEntity -Identity $dialByNameMenuOption9Target -Type applicationendpoint

$dialByNameMenuOption9 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone9 -CallTarget $dialByNameMenuOption9Entity

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt -EnableDialByName -DirectorySearchMethod ByName

$dialByNameCallFlow = New-CsAutoAttendantCallFlow -Name "Contoso Dial By Name Call Flow" -Menu $dialByNameMenu

$dialByNameAutoAttendant = New-CsAutoAttendant -Name "Contoso Dial By Name" -DefaultCallFlow $dialByNameCallFlow -LanguageId "en-US" -TimeZoneId "UTC" -Operator $operatorEntity -EnableVoiceResponse -InclusionScope $dialScope
```

### <a name="assign-resource-account"></a>Ressourcenkonto zuweisen

```PowerShell
New-CsOnlineApplicationInstanceAssociation -Identities @($dialByNameApplicationInstanceID) -ConfigurationID $dialByNameAutoAttendant.Id -ConfigurationType AutoAttendant
```
