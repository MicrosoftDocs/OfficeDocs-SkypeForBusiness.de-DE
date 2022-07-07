---
title: Verwenden von PowerShell zum Verwalten Ihrer Shifts-Verbindung mit Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie PowerShell verwenden, um Ihre Shifts-Verbindung mit Blue Yonder Workforce Management zu verwalten.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4edf815a3ce21a820fa292a06d41275c97d78a5
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647821"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Verwenden von PowerShell zum Verwalten Ihrer Shifts-Verbindung mit Blue Yonder Workforce Management

## <a name="overview"></a>Übersicht

Mit dem [Microsoft Teams Shifts-Connector für Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) können Sie die Schichten-App in Microsoft Teams in Blue Yonder Workforce Management (Blue Yonder WFM) integrieren. Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in Service und Produktion nahtlos ihre Zeitpläne in Blue Yonder WFM innerhalb von Schichten anzeigen und verwalten.

Sie können den [Verbinder-Assistenten "Schichten"](shifts-connector-wizard.md) in der Microsoft 365 Admin Center oder [PowerShell](shifts-connector-blue-yonder-powershell-setup.md) verwenden, um eine Verbindung einzurichten. Nachdem eine Verbindung eingerichtet wurde, verwalten Sie sie mithilfe von [PowerShell-Cmdlets für den Shifts-Connector](#shifts-connector-cmdlets).

In diesem Artikel wird beschrieben, wie PowerShell für folgende Zwecke verwendet wird:

- [Überprüfen des Verbindungseinrichtungsstatus](#check-connection-setup-status)
- [Anzeigen eines Fehlerberichts für eine Verbindung](#view-an-error-report-for-a-connection)
- [Beheben von Verbindungsfehlern](#resolve-connection-errors)
- [Ändern der Verbindungseinstellungen](#change-connection-settings)
- [Aufheben der Zuordnung eines Teams zu einer Verbindung und Zuordnen zu einer anderen Verbindung](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Deaktivieren der Synchronisierung für eine Verbindung](#disable-sync-for-a-connection)

> [!NOTE]
> In diesem Artikel wird davon ausgegangen, dass Sie bereits eine Verbindung mit Blue Yonder WFM eingerichtet haben, entweder mithilfe des Assistenten oder mit PowerShell.

## <a name="before-you-begin"></a>Bevor Sie beginnen

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Einrichten der Umgebung

> [!NOTE]
> Führen Sie die folgenden Schritte aus, um Ihre Umgebung einzurichten, bevor Sie befehle oder Skripts in diesem Artikel ausführen.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. Stellen Sie eine Verbindung mit Teams her.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an. Sie sind jetzt für die Ausführung der Skripts in diesem Artikel und der Shifts-Connector-Cmdlets eingerichtet.

## <a name="check-connection-setup-status"></a>Überprüfen des Verbindungseinrichtungsstatus

<a name="setup_status"> </a>

So überprüfen Sie den Status der eingerichteten Verbindung mithilfe der Vorgangs-ID, die Sie per E-Mail erhalten haben:

1. [Richten Sie Ihre Umgebung](#set-up-your-environment) ein (sofern noch nicht geschehen).
1. Führen Sie den folgenden Befehl aus. Mit diesem Befehl erhalten Sie den Gesamtstatus der Teamzuordnungen für die Verbindung.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Weitere Informationen finden Sie unter [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation).

## <a name="view-an-error-report-for-a-connection"></a>Anzeigen eines Fehlerberichts für eine Verbindung

<a name="error_report"> </a>

Sie können einen Bericht ausführen, der Fehlerdetails für eine Verbindung anzeigt. Der Bericht listet Team- und Benutzerzuordnungen auf, die erfolgreich waren und fehlgeschlagen sind. Es enthält auch Informationen zu allen Problemen im Zusammenhang mit den Konten, die mit der Verbindung verbunden sind.

1. [Richten Sie Ihre Umgebung](#set-up-your-environment) ein (sofern noch nicht geschehen).
1. Dient zum Abrufen einer Liste von Fehlerberichten für eine Verbindung.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Führen Sie den folgenden Befehl aus, um einen bestimmten Fehlerbericht anzuzeigen:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Weitere Informationen finden Sie unter [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport).

## <a name="resolve-connection-errors"></a>Beheben von Verbindungsfehlern

### <a name="user-mapping-errors"></a>Fehler bei der Benutzerzuordnung

Benutzerzuordnungsfehler können auftreten, wenn ein oder mehrere Benutzer in einer Blue Yonder-WFM Instanz kein Mitglied des zugeordneten Teams in Teams sind. Um dieses Problem zu beheben, stellen Sie sicher, dass die Benutzer im zugeordneten Team mit den Benutzern in der Blue Yonder-WFM-Instanz übereinstimmen.

Um Details zu nicht zugeordneten Benutzern anzuzeigen, [richten Sie Ihre Umgebung](#set-up-your-environment) ein (sofern noch nicht geschehen), und führen Sie dann das folgende Skript aus.

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

### <a name="account-authorization-errors"></a>Kontoautorisierungsfehler

Kontoautorisierungsfehler können auftreten, wenn das Blue Yonder WFM-Dienstkonto oder die Anmeldeinformationen des Microsoft 365-Systemkontos falsch sind oder nicht über die erforderlichen Berechtigungen verfügen.

Um Ihr Blue Yonder-WFM-Dienstkonto oder die Anmeldeinformationen des Microsoft 365-Systemkontos für die Verbindung zu ändern, können Sie das Cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) ausführen oder das PowerShell-Skript im Abschnitt ["Verbindungseinstellungen ändern"](#change-connection-settings) dieses Artikels verwenden.

## <a name="change-connection-settings"></a>Ändern der Verbindungseinstellungen
<a name="change_settings"> </a>

Verwenden Sie dieses Skript, um Verbindungseinstellungen zu ändern. Zu den Einstellungen, die Sie ändern können, gehören Ihr Blue Yonder WFM-Dienstkonto und -Kennwort, Ihr Microsoft 365-Systemkonto, Teamzuordnungen und Synchronisierungseinstellungen.

Zu den Synchronisierungseinstellungen gehören die Synchronisierungshäufigkeit (in Minuten) und die Zeitplandaten, die zwischen Blue Yonder WFM und Schichten synchronisiert werden. Zeitplandaten werden in den folgenden Parametern definiert, die Sie anzeigen können, indem [Sie Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) ausführen.

- Der **Parameter "enabledConnectorScenarios**" definiert Daten, die von Blue Yonder WFM mit Schichten synchronisiert werden. Optionen sind `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff`. `TimeOffRequest`
- Der Parameter **enabledWfiScenarios** definiert Daten, die von Schichten zu Blue Yonder WFM synchronisiert werden. Optionen sind `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Wenn Sie sich dafür entscheiden, offene Schichten, offene Schichtanforderungen, Tauschanforderungen oder Abwesenheitsanfragen zwischen Schichten und Blue Yonder WFM nicht zu synchronisieren, müssen Sie einen weiteren Schritt ausführen, um die Funktion in Schichten auszublenden. Nachdem Sie dieses Skript ausgeführt haben, stellen Sie sicher, dass Sie die Schritte im Abschnitt ["Offene Schichten deaktivieren", "Schichtanforderungen öffnen", "Tauschanforderungen" und "Abwesenheitsanforderungen](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) " weiter unten in diesem Artikel ausführen.

> [!IMPORTANT]
> Für Einstellungen, die Sie nicht ändern möchten, müssen Sie die ursprünglichen Einstellungen erneut eingeben, wenn Sie vom Skript dazu aufgefordert werden.

[Richten Sie Ihre Umgebung](#set-up-your-environment) ein (falls noch nicht geschehen), und führen Sie dann das folgende Skript aus.

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deaktivieren von offenen Schichten, offenen Schichtanforderungen, Swapanforderungen und Abwesenheitsanfragen

> [!IMPORTANT]
> Führen Sie diese Schritte nur aus, wenn Sie offene Schichten, Offene Schichtanforderungen, Swapanforderungen oder Abwesenheitsanforderungen mithilfe des Skripts im Abschnitt " [Verbindungseinstellungen ändern"](#change-connection-settings) weiter oben in diesem Artikel oder mithilfe des Cmdlets ["Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) " deaktivieren möchten. Wenn Sie diesen Schritt abschließen, wird die Funktion in Schichten ausgeblendet. Ohne diesen zweiten Schritt sehen Benutzer die Funktion weiterhin in Schichten und erhalten die Fehlermeldung "Nicht unterstützter Vorgang", wenn sie versuchen, sie zu verwenden.

Verwenden Sie zum Ausblenden geöffneter Schichten, Swapanforderungen und Abwesenheitsanforderungen in Schichten den Graph-API [Ressourcentyp "Zeitplan](/graph/api/resources/schedule)", um die folgenden Parameter ```false``` für jedes Team festzulegen, das Sie einer Blue Yonder-WFM Instanz zugeordnet haben:

- Offene Schichten: ```openShiftsEnabled```
- Swapanforderungen:  ```swapShiftsRequestsEnabled```
- Abwesenheitsanforderungen: ```timeOffRequestsEnabled```

Um offene Schichtanforderungen in Schichten auszublenden, wechseln **Sie zu "Einstellungen** " in "Schichten", und deaktivieren Sie dann die Einstellung " **Schichten** öffnen".

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Aufheben der Zuordnung eines Teams zu einer Verbindung und Zuordnen zu einer anderen Verbindung

> [!NOTE]
> Das Microsoft 365-Systemkonto muss für beide Verbindungen identisch sein. Andernfalls wird die Fehlermeldung "Dieses festgelegte Akteurprofil verfügt nicht über Teambesitzberechtigungen" angezeigt.

Wenn Sie die Zuordnung eines Teams aus einer Verbindung aufheben und einer anderen Verbindung zuordnen möchten:

1. [Richten Sie Ihre Umgebung](#set-up-your-environment) ein (sofern noch nicht geschehen).
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

Weitere Informationen finden Sie unter [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) und [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap).

## <a name="disable-sync-for-a-connection"></a>Deaktivieren der Synchronisierung für eine Verbindung

Verwenden Sie dieses Skript, um die Synchronisierung für eine Verbindung zu deaktivieren. Beachten Sie, dass mit diesem Skript keine Verbindung entfernt oder gelöscht wird. Die Synchronisierung wird deaktiviert, sodass keine Daten zwischen Schichten und Blue Yonder-WFM für die angegebene Verbindung synchronisiert werden.

[Richten Sie Ihre Umgebung](#set-up-your-environment) ein (falls noch nicht geschehen), und führen Sie dann das folgende Skript aus.

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

## <a name="shifts-connector-cmdlets"></a>Verbinder-Cmdlets für Schichten

Hilfe zu Konnektor-Cmdlets für Schichten finden Sie unter " **CsTeamsShiftsConnection** " in der [Microsoft Teams PowerShell-Cmdlet-Referenz](/powershell/teams/intro). Hier sind Links zu einigen häufig verwendeten Cmdlets.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>Verwandte Artikel

- [Schichtenverbinder](shifts-connectors.md)
- [Verwenden des Verbinder-Assistenten "Schichten" zum Verbinden von Schichten mit Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Verwenden von PowerShell zum Verbinden von Schichten mit Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Verwalten der Schichten-App](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](../../teams-powershell-overview.md)
