---
title: Verwenden von PowerShell zum Verbinden von Schichten mit Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie PowerShell verwenden, um Schichten in Blue Yonder Workforce Management zu integrieren.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad0f7e84dcd65f844e457d4821717ff7593593ce
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976018"
---
# <a name="use-powershell-to-connect-shifts-to-blue-yonder-workforce-management"></a>Verwenden von PowerShell zum Verbinden von Schichten mit Blue Yonder Workforce Management

## <a name="overview"></a>Übersicht

Verwenden Sie den [Microsoft Teams Shifts-Connector für Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder), um die Shifts-App in Microsoft Teams mit Blue Yonder Workforce Management (Blue Yonder WFM) zu integrieren. Nachdem eine Verbindung eingerichtet wurde, können Ihre Mitarbeiter in Service und Produktion ihre Zeitpläne in Blue Yonder WFM nahtlos in Schichten anzeigen und verwalten.

In diesem Artikel führen wir Sie durch die Verwendung von PowerShell zum Einrichten und Konfigurieren des Connectors zur Integration von Schichten in Blue Yonder WFM.

Zum Einrichten der Verbindung führen Sie ein PowerShell-Skript aus. Das Skript konfiguriert den Connector, wendet Synchronisierungseinstellungen an, erstellt die Verbindung und ordnet Blue Yonder WFM-Websites Teams zu. Synchronisierungseinstellungen bestimmen die in Schichten aktivierten Features und die Zeitplaninformationen, die zwischen Blue Yonder WFM und Schichten synchronisiert werden. Zuordnungen definieren die Synchronisierungsbeziehung zwischen Ihren Blue Yonder WFM-Websites und -Teams in Teams. Sie können vorhandene Teams und neue Teams zuordnen.

Wir stellen zwei Skripts bereit. Sie können entweder ein Skript verwenden, je nachdem, ob Sie vorhandenen Teams zugeordnet oder neue Teams erstellen möchten, die zugeordnet werden sollen.

Sie können mehrere Verbindungen mit jeweils unterschiedlichen Synchronisierungseinstellungen einrichten. Wenn Ihre Organisation beispielsweise über mehrere Standorte mit unterschiedlichen Zeitplananforderungen verfügt, erstellen Sie eine Verbindung mit eindeutigen Synchronisierungseinstellungen für jeden Standort. Denken Sie daran, dass eine Blue Yonder-WFM-Website zu einem bestimmten Zeitpunkt nur einem Team zugeordnet werden kann. Wenn eine Website bereits einem Team zugeordnet ist, kann sie keinem anderen Team zugeordnet werden.

Mit Blue Yonder WFM als Datensatzsystem können Ihre Mitarbeiter in Service und Produktion Schichten sehen und austauschen, deren Verfügbarkeit verwalten und Abwesenheitszeiten in Schichten auf ihren Geräten anfordern. Vorgesetzte in Service und Produktion können weiterhin Blue Yonder WFM verwenden, um Zeitpläne einzurichten.

> [!NOTE]
> Sie können auch den [Verbinder-Assistenten "Schichten"](shifts-connector-wizard.md) im Microsoft 365 Admin Center verwenden, um Schichten mit Blue Yonder WFM zu verbinden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

### <a name="prerequisites"></a>Voraussetzungen

[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

### <a name="admin-role-to-manage-the-connector-using-powershell"></a>Administratorrolle zum Verwalten des Connectors mithilfe von PowerShell

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Einrichten der Umgebung

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="connect-to-teams"></a>Verbinden zu Teams

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an. Sie sind jetzt für die Ausführung der Skripts in diesem Artikel und der Shifts-Connector-Cmdlets eingerichtet.

## <a name="identify-the-teams-you-want-to-map"></a>Identifizieren der Teams, die Sie zuordnen möchten

> [!NOTE]
> Führen Sie diesen Schritt aus, wenn Sie Blue Yonder WFM-Websites vorhandenen Teams zuordnen. Wenn Sie neue Teams für die Zuordnung erstellen, können Sie diesen Schritt überspringen.

Wechseln Sie in der Azure-Portal zur Seite ["Alle Gruppen](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups)", um eine Liste der Team-IDs von Teams in Ihrer Organisation abzurufen.

Notieren Sie sich die Team-IDs der Teams, die Sie zuordnen möchten. Das Skript fordert Sie auf, diese Informationen einzugeben.

> [!NOTE]
> Wenn ein oder mehrere Teams über einen vorhandenen Zeitplan verfügen, entfernt das Skript die Zeitpläne aus diesen Teams. Andernfalls werden doppelte Schichten angezeigt.

## <a name="run-the-script"></a>Ausführen des Skripts

Führen Sie das Skript aus:

- [Führen Sie dieses Skript](#set-up-a-connection-and-create-new-teams-to-map) aus, um eine Verbindung einzurichten und neue Teams für die Zuordnung zu erstellen.
- Führen [Sie dieses Skript](#set-up-a-connection-and-map-to-existing-teams) aus, um eine Verbindung einzurichten und vorhandenen Teams zuzuordnen.

Das Skript führt die folgenden Aktionen aus. Sie werden aufgefordert, Setup- und Konfigurationsdetails einzugeben.

1. Testet und überprüft die Verbindung mit Blue Yonder WFM mithilfe der anmeldeinformationen und Dienst-URLs des Blue Yonder WFM-Dienstkontos, die Sie eingeben.
1. Konfiguriert den Shifts-Connector.
1. Wendet Synchronisierungseinstellungen an. Diese Einstellungen umfassen die Synchronisierungshäufigkeit (in Minuten) und die Zeitplandaten, die zwischen Blue Yonder WFM und Schichten synchronisiert werden. Zeitplandaten sind in den folgenden Parametern definiert:

    - Der **Parameter "enabledConnectorScenarios** " definiert Daten, die von Blue Yonder WFM mit Schichten synchronisiert werden. Optionen sind `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff`. `TimeOffRequest`
    - Der Parameter **enabledWfiScenarios** definiert Daten, die von Schichten in Blue Yonder WFM synchronisiert werden. Optionen sind `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    Weitere Informationen finden Sie unter [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps). Um die Liste der unterstützten Synchronisierungsoptionen für jeden Parameter anzuzeigen, führen Sie [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps) aus.

    > [!IMPORTANT]
    > Das Skript aktiviert die Synchronisierung für alle diese Optionen. Wenn Sie die Synchronisierungseinstellungen ändern möchten, können Sie dies tun, nachdem die Verbindung eingerichtet wurde. Weitere Informationen finden Sie unter [Verwenden von PowerShell zum Verwalten Ihrer Schichtverbindung mit Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

1. Erstellt die Verbindung.
1. Karten Blue Yonder WFM-Websites an Teams. Zuordnungen basieren auf den Blue Yonder WFM-Website-IDs und TeamIds, die Sie eingeben, oder auf neuen Teams, die Sie erstellen, je nach ausgeführtem Skript. Wenn ein Team über einen vorhandenen Zeitplan verfügt, entfernt das Skript Zeitplandaten für den von Ihnen angegebenen Datums- und Uhrzeitbereich.

Eine Erfolgsmeldung auf dem Bildschirm gibt an, dass Ihre Verbindung erfolgreich eingerichtet wurde.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Wenn Sie Änderungen an einer Verbindung vornehmen müssen

Informationen zum Ändern einer Verbindung nach der Einrichtung finden [Sie unter Verwenden von PowerShell zum Verwalten Ihrer Schichtenverbindung mit Blue Yonder Workforce Management](shifts-connector-powershell-manage.md). Sie können z. B. Synchronisierungseinstellungen, Teamzuordnungen aktualisieren und die Synchronisierung für eine Verbindung deaktivieren.

## <a name="scripts"></a>Skripts

### <a name="set-up-a-connection-and-create-new-teams-to-map"></a>Einrichten einer Verbindung und Erstellen neuer Teams zur Zuordnung

```powershell
#Map WFM sites to teams script
Write-Host "Map WFM sites to teams"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName 
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency"

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail $AdminEmailList
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles 
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

#Create a new Teams team with owner set to system account and name set to the site name
Write-Host "Creating a Teams team"
$teamsTeamName = Read-Host -Prompt "Input the Teams team name"
$Team = New-Team -DisplayName $teamsTeamName -Visibility "Public" -Owner $teamsUserId
Write-Host "Success"
$TeamsTeamId=$Team.GroupId

#add users to the Team for Shifts
Write-Host "Adding users to Teams team"
$currentUser = Read-Host -Prompt "Input the current user's user name or ID"
Add-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
$failedWfmUsers=@()
foreach ($user in $WFMUsers) {
    try {
    $userEmail = $user.Name + "@" +$domain
    Add-TeamUser -GroupId $TeamsTeamId -User $userEmail
    } catch {
        $failedWfmUsers+=$user
    }
}
if($failedWfmUsers.Count -gt 0){
    Write-Host "There are WFM users not existed in Teams tenant:"
    write $failedWfmUsers
}

#Enable scheduling in the group
$RequestBody = @{
    Enabled = $true
    TimeZone = "America/Los_Angeles"
}
$teamUpdateUrl="https://graph.microsoft.com/v1.0/teams/"+$TeamsTeamId+"/schedule"
$Schedule = Invoke-MgGraphRequest -Uri $teamUpdateUrl -Method PUT -Body $RequestBody

#Create a mapping of the new team to the site 
Write-Host "Create a mapping of the new team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"

$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}

#The Teams admin was set as an owner directly when creating a new team, removing it from owners
Remove-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
Disconnect-MgGraph
```

### <a name="set-up-a-connection-and-map-to-existing-teams"></a>Einrichten einer Verbindung und Zuordnen zu vorhandenen Teams

```powershell
#Map WFM sites to existing teams script
Write-Host "Map WFM sites to existing teams"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview) 
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName 
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365 user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency in minutes. Value should be equal to or more than 10."

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail AdminEmailList

$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles 
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

$TeamsTeamId = Read-Host -Prompt "Input the ID of the Teams team to be mapped"
#Clear schedule of the Teams team
Write-Host "Clear schedule of the existing team"
$startTime = Read-Host -Prompt "Input the start time of clear schedule"
$endTime = Read-Host -Prompt "Input the end time of clear schedule"

$entityTypeString = Read-Host -Prompt 'Input the entity types of clear schedule'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$entityType = $entityTypeString -Split {$Delimiters -contains $_}
$entityType = $entityType.Trim()
$entityType = $entityType.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
Remove-CsTeamsShiftsScheduleRecord -TeamId $TeamsTeamId -DateRangeStartDate $startTime -DateRangeEndDate $endTime -ClearSchedulingGroup:$True -EntityType $entityType -DesignatedActorId $$teamsUserId

#Create a mapping of the new team to the site 
Write-Host "Create a mapping of the existing team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"


$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Disconnect-MgGraph
```

## <a name="shifts-connector-cmdlets"></a>Verbinder-Cmdlets für Schichten

Hilfe zu Shifts-Connector-Cmdlets, einschließlich der in den Skripts verwendeten Cmdlets, finden Sie in der [Teams PowerShell-Cmdlet-Referenz](/powershell/teams/intro?view=teams-ps) nach **CsTeamsShiftsConnection**. Hier sind Links zu einigen häufig verwendeten Cmdlets.

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

- [Schichtenverbinder](shifts-connectors.md)
- [Verwenden von PowerShell zum Verwalten Ihrer Schichtverbindung mit Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Verwalten der Schichten-App](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](../../teams-powershell-overview.md)
- [Teams PowerShell-Cmdlet-Referenz](/powershell/teams/intro?view=teams-ps)