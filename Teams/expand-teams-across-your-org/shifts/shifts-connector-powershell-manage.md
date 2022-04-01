---
title: Verwenden von PowerShell zum Verwalten Ihrer Schichtenverbindung zur Personalverwaltung von Blue Yonder
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie PowerShell verwenden, um Ihre Schichten-Verbindung mit der Personalverwaltung von Blue Yonder zu verwalten.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593661"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Verwenden von PowerShell zum Verwalten Ihrer Schichtenverbindung zur Personalverwaltung von Blue Yonder

## <a name="overview"></a>Übersicht

Der Microsoft Teams Umschalten für [Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) ermöglicht Es Ihnen, die Schichten-App in Microsoft Teams mit Blue Yonder Workforce Management (Blue Yonder WFM) zu integrieren. Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in der Frontline ihre Zeitpläne in Blue Yonder WFM direkt in Schichten anzeigen und verwalten.

Sie können den Assistenten [schichtenverbinder](shifts-connector-wizard.md) in der Microsoft 365 Admin Center [oder PowerShell](shifts-connector-blue-yonder-powershell-setup.md) verwenden, um eine Verbindung herzustellen. Nachdem eine Verbindung eingerichtet wurde, verwalten Sie sie mithilfe von [PowerShell-Cmdlets für den Shifts-Connector](#shifts-connector-cmdlets).

In diesem Artikel wird beschrieben, wie Sie PowerShell für folgende Aufgaben verwenden:

- [Überprüfen des Verbindungseinrichtungsstatus](#check-connection-setup-status)
- [Anzeigen eines Fehlerberichts für eine Verbindung](#view-an-error-report-for-a-connection)
- [Beheben von Verbindungsfehlern](#resolve-connection-errors)
- [Ändern der Verbindungseinstellungen](#change-connection-settings)
- [Unmap an team from one connection and map it to another connection](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Deaktivieren der Synchronisierung für eine Verbindung](#disable-sync-for-a-connection)

> [!NOTE]
> In diesem Artikel wird davon ausgegangen, dass Sie bereits eine Verbindung mit Blue Yonder WFM eingerichtet haben, entweder mithilfe des Assistenten oder von PowerShell.

## <a name="before-you-begin"></a>Bevor Sie beginnen

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Einrichten der Umgebung

> [!NOTE]
> Führen Sie die folgenden Schritte aus, um Ihre Umgebung ein eingerichtet zu haben, bevor Sie Befehle oder Skripts in diesem Artikel ausführen.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>Überprüfen des Verbindungseinrichtungsstatus
<a name="setup_status"> </a>

So überprüfen Sie den Status der eingerichteten Verbindung mithilfe der Vorgangs-ID, die Sie per E-Mail erhalten haben:

1. [Richten Sie Ihre Umgebung ein](#set-up-your-environment) (sofern noch nicht vorhanden).
1. Führen Sie den folgenden Befehl aus. Mit diesem Befehl erhalten Sie den Gesamtstatus der Teamzuordnungen für die Verbindung.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Weitere Informationen finden Sie unter [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps).

## <a name="view-an-error-report-for-a-connection"></a>Anzeigen eines Fehlerberichts für eine Verbindung
<a name="error_report"> </a>

Sie können einen Bericht ausführen, in dem Fehlerdetails für eine Verbindung angezeigt werden. Im Bericht werden die Team- und Benutzerzuordnungen aufgeführt, die erfolgreich waren und fehlgeschlagen sind. Darüber hinaus werden Informationen zu Allen Problemen im Zusammenhang mit den Konten, die mit der Verbindung verbunden sind, zur Verfügung stehen.

1. [Richten Sie Ihre Umgebung ein](#set-up-your-environment) (sofern noch nicht vorhanden).
1. Erhalten Sie eine Liste der Fehlerberichte für eine Verbindung.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Führen Sie zum Anzeigen eines bestimmten Fehlerberichts den folgenden Befehl aus:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Weitere Informationen finden Sie unter [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps).

## <a name="resolve-connection-errors"></a>Beheben von Verbindungsfehlern

### <a name="user-mapping-errors"></a>Fehler bei der Benutzerzuordnung

Fehler bei der Benutzerzuordnung können auftreten, wenn ein oder mehrere Benutzer auf einer Blue Yonder WFM-Website kein Mitglied des zugeordneten Teams in Teams. Um dieses Problem zu beheben, stellen Sie sicher, dass die Benutzer im zugeordneten Team den Benutzern auf der Blue Yonder WFM-Website entsprechen.

Um Details zu nicht zugeordneten Benutzern [anzuzeigen, richten](#set-up-your-environment) Sie Ihre Umgebung ein (sofern noch nicht vorhanden), und führen Sie dann das folgende Skript aus.

```powershell
#View sync errors script 
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x 
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>Fehler bei der Kontoautorisierung

Fehler bei der Kontoautorisierung können auftreten, wenn die Anmeldeinformationen für das Blue Yonder WFM-Dienstkonto oder Microsoft 365-Systemkonto falsch sind oder nicht über die erforderlichen Berechtigungen verfügen.

Zum Ändern der Anmeldeinformationen ihres Blue Yonder WFM-Dienstkontos oder des Microsoft 365-Systemkontos für die Verbindung können Sie das [Cmdlet Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) ausführen oder das PowerShell-Skript im Abschnitt Verbindungseinstellungen ändern dieses Artikels verwenden.[](#change-connection-settings)

## <a name="change-connection-settings"></a>Ändern der Verbindungseinstellungen
<a name="change_settings"> </a>

Verwenden Sie dieses Skript, um Verbindungseinstellungen zu ändern. Einstellungen, die Sie ändern können, gehören Ihr Blue Yonder WFM-Dienstkonto und -Kennwort, Microsoft 365-Systemkonto, Teamzuordnungen und Synchronisierungseinstellungen.

Zu den Synchronisierungseinstellungen gehören die Synchronisierungshäufigkeit (in Minuten) und die Zeitplandaten, die zwischen Blue Yonder WFM und Schichten synchronisiert werden. Zeitplandaten werden in den folgenden Parametern definiert, die Sie anzeigen können, indem [Sie Get-CsTeamsShiftsConnectionConnector ausführen](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps).

- Der **Parameter enabledConnectorScenarios** definiert Daten, die von Blue Yonder WFM in Schichten synchronisiert werden. Die Optionen sind `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff`, `TimeOffRequest`.
- Der **Parameter enabledWfiScenarios** definiert Daten, die von Schichten zu Blue Yonder WFM synchronisiert werden. Die Optionen sind `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Wenn Sie offene Schichten, offene Schichtanforderungen, Tauschanfragen oder Anfragen für freie Zeit zwischen Schichten und Blue Yonder WFM nicht synchronisieren möchten, müssen Sie noch einen weiteren Schritt zum Ausblenden der Funktion in Schichten tun. Nachdem Sie dieses Skript ausgeführt haben, stellen Sie sicher, dass Sie die Schritte im Abschnitt Deaktivieren geöffneter Schichten, offener Schichtenanforderungen [,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) Tauschanforderungen und Anfragen für arbeits freie Zeit weiter unten in diesem Artikel ausführen.

> [!IMPORTANT]
> Für Einstellungen, die Sie nicht ändern möchten, müssen Sie die ursprünglichen Einstellungen erneut eingeben, wenn Sie vom Skript dazu aufgefordert werden.

[Richten Sie Ihre Umgebung ein](#set-up-your-environment) (sofern noch nicht vorhanden), und führen Sie dann das folgende Skript aus.

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview) 
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping 
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping 
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deaktivieren sie offene Schichten, offene Schichten, Tauschanfragen und Anfragen für freie Zeit.

> [!IMPORTANT]
> Führen Sie diese Schritte nur aus, wenn Sie im Abschnitt Verbindungseinstellungen ändern weiter oben in diesem Artikel oder mithilfe des [Cmdlets Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) offene Schichten, offene Schichtanforderungen, Tauschanforderungen oder Anfragen zur arbeits freien Zeit deaktiviert haben.[](#change-connection-settings) Bei Abschluss dieses Schritts wird die Funktion in Schichten ausgeblendet. Ohne diesen zweiten Schritt wird den Benutzern weiterhin die Funktion in Schichten angezeigt, und wenn sie versuchen, sie zu verwenden, wird die Fehlermeldung "Nicht unterstützter Vorgang" angezeigt.

Verwenden Sie zum Ausblenden geöffneter Schichten, Tauschanforderungen und Anfragen für freie Zeitverschiebungen in Schichten den Ressourcentyp " [](/graph/api/resources/schedule?view=graph-rest-1.0) Graph-API ```false``` Schedule", um die folgenden Parameter für jedes Team zu definieren, das Sie einer Blue Yonder WFM-Website zugeordnet haben:

- Offene Schichten: ```openShiftsEnabled```
- Tauschanforderungen:  ```swapShiftsRequestsEnabled```
- Anfragen für freizeite Zeit: ```timeOffRequestsEnabled```

Um offene Schichtenanforderungen in Schichten auszublenden, wechseln **Sie in Einstellungen** zu Schicht, und deaktivieren Sie dann die Einstellung **Offene Schichten**.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Unmap an team from one connection and map it to another connection

> [!NOTE]
> Das Microsoft 365 Systemkonto muss für beide Verbindungen gleich sein. Wenn dies nicht zu sehen ist, wird die Fehlermeldung "Dieses festgelegte Akteur-Profil hat keine Berechtigungen für Teambesitz" angezeigt.

Wenn Sie die Zuordnung eines Teams von einer Verbindung zu einer anderen Verbindung wieder herstellen möchten:

1. [Richten Sie Ihre Umgebung ein](#set-up-your-environment) (sofern noch nicht vorhanden).
1. Zeigen Sie eine Liste aller Teamzuordnungen für eine Verbindung an.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Entfernen Sie eine Teamzuordnung aus der Verbindung.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Ordnen Sie das Team einer anderen Verbindung zu.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Weitere Informationen finden Sie unter [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps) und [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps).

## <a name="disable-sync-for-a-connection"></a>Deaktivieren der Synchronisierung für eine Verbindung

Verwenden Sie dieses Skript, um die Synchronisierung für eine Verbindung zu deaktivieren. Beachten Sie, dass mit diesem Skript keine Verbindung entfernt oder gelöscht wird. Damit wird die Synchronisierung deaktiviert, sodass für die von Ihnen festgelegte Verbindung keine Daten zwischen Shifts und Blue Yonder WFM synchronisiert werden.

[Richten Sie Ihre Umgebung ein](#set-up-your-environment) (sofern noch nicht vorhanden), und führen Sie dann das folgende Skript aus.

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Verschiebt Connector-Cmdlets

Wenn Sie Hilfe zu Denk-Cmdlets für Schichten brauchen, suchen Sie in der Referenz [Teams PowerShell-Cmdlet](/powershell/teams/intro?view=teams-ps) nach **CsTeamsShiftsConnection**. Hier finden Sie Links zu einigen häufig verwendeten Cmdlets.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>Verwandte Artikel

- [Verschiebt Verbinder](shifts-connectors.md)
- [Verwenden des Assistenten "Schichtenconnector", um Schichten mit der Personalverwaltung in Blue Yonder zu verbinden](shifts-connector-wizard.md)
- [Verwenden von PowerShell zum Verbinden von Schichten mit der Personalverwaltung in Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)
- [Verwalten der Schichten-App](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](../../teams-powershell-overview.md)