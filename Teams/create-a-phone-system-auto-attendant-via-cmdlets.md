---
title: Erstellen einer automatischen Telefon attendant über Cmdlets
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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Erfahren Sie, wie Sie automatische Telefon attendants über Cmdlets konfigurieren.
ms.openlocfilehash: 3911010b201e2b19376c24c6c4b84ae8dbcc5db8
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457465"
---
# <a name="create-an-auto-attendant-via-cmdlets"></a>Erstellen einer automatischen Telefon attendant über Cmdlets

## <a name="assumptions"></a>Annahmen
1)  PowerShell ist auf dem Computer installiert
- Einrichten Ihres Computers für [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
- MSTeams-Modul installiert ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- MSOnline-Modul installiert ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  Sie verfügen über Mandantenverwaltungsrechte
3)  Sie haben Ihre Microsoft Teams Telefon
4)  Die nachstehend genannten Anrufwarteschleifen wurden nach dem Leitfaden Erstellen von [Anrufwarteschleifen mit PowerShell-Cmdlets bereits eingerichtet](create-a-phone-system-call-queue-via-cmdlets.md) .
                                                                                               
Hinweis: Einige der unten aufgeführten Cmdlets sind möglicherweise Teil der öffentlichen Preview-Version Teams PowerShell-Moduls.  Weitere Informationen finden Sie unter [Installieren Teams PowerShell Public Preview](teams-powershell-install.md) und Microsoft Teams [PowerShell-Versionshinweise](teams-powershell-release-notes.md).

Benutzer, die das MicrosoftTeams-Modul ````Update-Module MicrosoftTeams```` bereits installiert haben, sollten sicherstellen, dass die neueste Version installiert ist.

## <a name="scenario"></a>Szenario

Der folgende Anruffluss für die automatische Telefon attendant wird erstellt:

![Diagramm des automatischen Attenanten-Anrufflusses, der mit Cmdlets erstellt wird.](media/create-a-phone-system-auto-attendant-via-cmdlets.png)

Zusätzliche Konfigurationsinformationen:

- automatische Telefonzentrale: Contso Main
- - Operator: Adele Vance
- - Spracheingaben aktivieren: Aus
- - Verzeichnissuche: Keine
- - Feiertage:
- - - 1. Januar 2022
- - - 24. Dezember 2022
- - - 25. Dezember 2022

- automatische Telefonzentrale: Contoso-Namenswahl
- - Operator: Adele Vance
- - Zeitzone: UTC
- - Sprache: Englisch USA
- - Aktivieren von Spracheingaben: Ein
- - Begrüßung: Keine
- - Menü: TTS, "Sagen Sie bitte den Namen der Person, die Sie erreichen möchten, oder geben Sie den Namen ein. Drücken Sie 9", um zum vorherigen Menü zurückzukehren.
- - Verzeichnissuche: Namenswahl
- - Wählbereich: Vertriebsmitarbeiter & Supportmitglieder

## <a name="login"></a>Anmeldung
Sie werden aufgefordert, Ihre Anmeldeinformationen als Teams ein.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="get-operator-information"></a>Operatorinformationen erhalten
````
$operatorID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID

$operatorEntity = New-CsAutoAttendantCallableEntity -Identity $operatorID -Type User
````

## <a name="dial-by-name-auto-attendant---resource-account-creation"></a>Namens-automatische Telefonzentrale – Erstellung eines Ressourcenkontos
Hinweis: Hier wird ein Ressourcenkonto erstellt, damit in der automatischen Hauptverteiler darauf verwiesen werden kann.  Die tatsächliche automatische Telefon attendant für Namensanwahl wird später erstellt.

### <a name="get-license-types"></a>Lizenztypen erhalten
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuordnen von Ressourcenkonto
Hinweis: Telefon nummer, die hier nicht erforderlich ist, da die Anrufwarteschleife per Telefonwarteschleife automatische Telefonzentrale
- ApplicationID
- - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
- - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName ContosoDialByNameAA-RA@contoso.com -DisplayName "Contoso Dial By Name AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoDialByNameAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “ContosoDialByNameAA-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$dialByNameApplicationInstanceID = (Get-CsOnlineUser "ContosoDialByNameAA-RA@contoso.com").ObjectID
````

## <a name="contoso-main-menu-auto-attendant"></a>Contoso-Hauptmenü automatische Telefonzentrale
### <a name="create-holiday-schedules"></a>Erstellen von Feiertagszeitplänen
````
$dtr = New-CsOnlineDateTimeRange -Start "24/12/2022" -End "25/12/2022"

$christmasSchedule = New-CsOnlineSchedule -Name "Christmas" -FixedSchedule -DateTimeRanges @($dtr)

$dtr = New-CsOnlineDateTimeRange -Start "01/01/2022" -End "02/01/2022"

$newyearSchedule = New-CsOnlineSchedule -Name "New Year" -FixedSchedule -DateTimeRanges @($dtr)
````

### <a name="create-address-fax-and-email-information-prompt"></a>Eingabeaufforderung für Adress-, FAX- und E-Mail-Informationen erstellen
````
$addressPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To repeat this information at any time press the * key. Our mailing address is: 123 Main Street, Any town, Any Place, County. Our email address is: info@contoso.com. Our fax number is: 929-555-0151"
````

### <a name="create-holiday-prompts-and-menu-options"></a>Feiertags-Eingabeaufforderungen und Menüoptionen erstellen
````
$christmasGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the Christmas holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$christmasMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$christmasMenu = New-CsAutoAttendantMenu -Name "Christmas Menu" -MenuOptions @($christmasMenuOption)

$christmasCallFlow = New-CsAutoAttendantCallFlow -Name "Christmas" -Greetings @($christmasGreetingPrompt) -Menu $christmasMenu

$christmasCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $christmasSchedule.Id -CallFlowId $christmasCallFlow.Id

$newyearGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the New Year’s holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$newyearMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$newyearMenu = New-CsAutoAttendantMenu -Name "New Year Menu" -MenuOptions @($newyearMenuOption)

$newyearCallFlow = New-CsAutoAttendantCallFlow -Name "New Year" -Greetings @($newyearGreetingPrompt) -Menu $newyearMenu

$newyearCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $newyearSchedule.Id -CallFlowId $newyearCallFlow.Id
````

### <a name="create-after-hours-schedules"></a>Erstellen von Terminplänen nach Stunden
````
$timerangeMoFr = New-CsOnlineTimeRange -Start 08:30 -end 17:00

$timerangeSa = New-CsOnlineTimeRange -Start 10:00 -end 16:00

$afterHoursSchedule = New-CsOnlineSchedule -Name "After Hours Schedule" -WeeklyRecurrentSchedule -MondayHours @($timerangeMoFr) -TuesdayHours @($timerangeMoFr) -WednesdayHours @($timerangeMoFr) -ThursdayHours @($timerangeMoFr) -FridayHours @($timerangeMoFr) -SaturdayHours @($timerangeSa) -Complement
````

### <a name="create-after-hours-prompts-and-menu-options"></a>Eingabeaufforderungen und Menüoptionen für "Nach Stunden erstellen"
````
$afterHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices are now closed. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time."

$afterHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt “To leave a voicemail for our sales team press 1.To leave a message for our support team press 2.If you know the name of the person you would like to reach, press 3.For our address, email and fax information press 4.”

$afterHoursMenuOption1Target = (Get-Team -displayname "Sales").GroupID

$afterHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption1Target -Type SharedVoiceMail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $afterHoursMenuOption1Entity

$afterHoursMenuOption2Target = (Get-Team -displayname "Support").GroupID

$afterHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption2Target -Type SharedVoicemail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $afterHoursMenuOption2Entity

$dialbynameAAOption3Target = (Get-CsOnlineUser -Identity “ContosoDialByNameAA-RA@contso.com”).ObjectID

$dialbynameAAMenuOption3Entity = New-CsAutoAttendantCallableEntity -Identity $dialbynameAAOption3Target -Type applicationendpoint

$dialbynameAAMenuOption3 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone3 -CallTarget $dialbynameAAMenuOption3Entity

$afterHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt
````

### <a name="create-after-hours-menu-and-call-flow"></a>Menü "Nach Stunden erstellen" und Anruf Flow
````
$afterHoursMenu = New-CsAutoAttendantMenu -Name "After Hours Menu" -MenuOptions @($afterHoursMenuOption1, $afterHoursMenuOption2, $dialbynameAAMenuOption3, $afterHoursMenuOption4) -Prompt $afterHoursMenuPrompt

$afterHoursCallFlow = New-CsAutoAttendantCallFlow -Name "After Hours Call Flow" -Greetings @($afterHoursGreetingPrompt) -Menu $afterHoursMenu

$afterHoursCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type AfterHours -ScheduleId $afterHoursSchedule.Id -CallFlowId $afterHoursCallFlow.Id
````

### <a name="create-open-hours-prompts-and-menu-options"></a>Erstellen von Eingabeaufforderungen und Menüoptionen für offene Stunden
````
$openHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt " Thank you for calling Contoso."

$openHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt “For Sales press 1. For Support press 2. If you know the name of the person you would like to reach, press 3. For our address, email and fax information, press 4. For all other inquiries press 0 to speak with the operator.”

$openHoursMenuOption1Target = (Get-CsOnlineUser "Sales-RA@contoso.com").ObjectID

$openHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption1Target -Type applicationendpoint

$openHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $openHoursMenuOption1Entity

$openHoursMenuOption2Target = (Get-CsOnlineUser "Support-RA@contoso.com").ObjectID

$openHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption2Target -Type applicationendpoint

$openHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $openHoursMenuOption2Entity

$openHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt

$openHoursMenuOption0 = New-CsAutoAttendantMenuOption -Action TransferCallToOperator -DtmfResponse Tone0
````

### <a name="create-open-hours-menu"></a>Open Hours-Menü erstellen
````
$openHoursMenu = New-CsAutoAttendantMenu -Name "Open Hours Menu" -MenuOptions @($openHoursMenuOption1, $openHoursMenuOption2, $dialbynameAAMenuOption3, $openHoursMenuOption4, $openHoursMenuOption0) -Prompt $openHoursMenuPrompt

$openHoursCallFlow = New-CsAutoAttendantCallFlow -Name "Open Hours Call Flow" -Greetings @($openHoursGreetingPrompt) -Menu $openHoursMenu
````

### <a name="create-auto-attendant"></a>Erstellen automatische Telefonzentrale
````
$autoAttendant = New-CsAutoAttendant -Name “Contoso Main” -DefaultCallFlow $openHoursCallFlow -CallFlows @($afterHoursCallFlow, $christmasCallFlow, $newyearCallFlow) -CallHandlingAssociations @($afterHoursCallHandlingAssociation, $christmasCallHandlingAssociation, $newyearCallHandlingAssociation) -LanguageId “en-US” -TimeZoneId “Eastern Standard Time” -Operator $operatorEntity
````

### <a name="get-license-types"></a>Lizenztypen erhalten
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Erstellen und Zuordnen von Ressourcenkonto
- ApplicationID
- - Automatische Telefonzentrale: ce933385-9390-45d1-9512-c8d228074e07
- - Anrufwarteschleife: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName ContosoMainAA-RA@contoso.com -DisplayName "Contoso Main AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoMainAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “ContosoMainAA-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").ObjectID

$autoAttendantID = (Get-CsAutoAttendant -NameFilter "Contoso Main").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $autoAttendantID -ConfigurationType AutoAttendant
````

### <a name="get-list-of-unassigned-service-numbers"></a>Liste der nicht zugewiesenen Leistungsnummern erhalten
````
Get-CsOnlineTelephoneNumber -IsNotAssigned -InventoryType Service
````

#### <a name="assign-available-phone-number"></a>Verfügbare Telefonnummer zuweisen
Hinweis: Der der Telefonnummer zugewiesene Verwendungsstandort muss mit dem dem Ressourcenkonto zugeordneten Verwendungsstandort übereinstimmen.

````
Set-CsPhoneNumberAssignment -Identity ContosoMainAA-RA@contoso.com -PhoneNumber +{spare number from output of above command} -PhoneNumberType CallingPlan
````

## <a name="dial-by-name-auto-attendant---completion"></a>Namenswahl- automatische Telefonzentrale – Fertigstellung
### <a name="create-dial-scope"></a>Erstellen des Wählbereichs
````
$salesGroupID = Find-CsGroup -SearchQuery "Sales" | % { $_.Id }

$supportGroupID = Find-CsGroup -SearchQuery "Support" | % { $_.Id }

$dialScope = New-CsAutoAttendantDialScope -GroupScope -GroupIds @($salesGroupID, $supportGroupID)
````

### <a name="create-prompts-and-menu-options"></a>Erstellen von Eingabeaufforderungen und Menüoptionen
````
$dialByNameMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Please say or enter the name of the person you would like to reach. To return to the previous menu press 9”

$dialByNameMenuOption9Target = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").ObjectID

$dialByNameMenuOption9Entity = New-CsAutoAttendantCallableEntity -Identity $dialByNameMenuOption9Target -Type applicationendpoint

$dialByNameMenuOption9 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone9 -CallTarget $dialByNameMenuOption9Entity

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt -EnableDialByName -DirectorySearchMethod ByName

$dialByNameCallFlow = New-CsAutoAttendantCallFlow -Name "Contoso Dial By Name Call Flow" -Menu $dialByNameMenu

$dialByNameAutoAttendant = New-CsAutoAttendant -Name “Contoso Dial By Name” -DefaultCallFlow $dialByNameCallFlow -LanguageId “en-US” -TimeZoneId “UTC” -Operator $operatorEntity -EnableVoiceResponse -InclusionScope $dialScope
````

### <a name="assign-resource-account"></a>Ressourcenkonto zuordnen
````
New-CsOnlineApplicationInstanceAssociation -Identities @($dialByNameApplicationInstanceID) -ConfigurationID $dialByNameAutoAttendant.Id -ConfigurationType AutoAttendant
````
