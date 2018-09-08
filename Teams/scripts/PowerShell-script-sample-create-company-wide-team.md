---
title: PowerShell-Skriptbeispiel – Erstellen eines firmenweiten Teams in Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 02/07/2018
ms.topic: article
ms.service: msteams
description: Mit diesem PowerShell-Skript können Sie ein öffentliches firmenweites Team in Microsoft Teams erstellen.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 6c4c1acf659e391320f1fa713be0e8d6c9e09853
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884096"
---
<a name="powershell-script-sample---create-a-company-wide-team-in-microsoft-teams"></a>PowerShell-Skriptbeispiel – Erstellen eines firmenweiten Teams in Microsoft Teams
-------------------------------------------------------------------------

Dieses PowerShell-Skript erstellt ein öffentliches firmenweites Team in Microsoft Teams. Das Skript verwendet das PowerShell-Modul MicrosoftTeams (zurzeit als Betaversion verfügbar), um ein öffentliches firmenweites Team zu erstellen. Außerdem verwendet es das PowerShell-Modul AzureAD, um die Liste der Benutzer in Ihrem Mandanten abzurufen. 

Eine vollständige Anleitung zur Verwendung dieses PowerShell-Skripts finden Sie im Tutorial [Erstellen eines firmenweiten Teams in Microsoft Teams mithilfe von PowerShell](../Company-wide-team-creation-powershell.yml).

Wenn PowerShell für Sie neu ist und Sie bei den ersten Schritten Hilfe benötigen, lesen Sie [Übersicht über Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Beispielskript

> [!TIP]
> Bei einer PowerShell-Skriptdatei handelt es sich um eine Textdatei mit der Erweiterung „.ps1“. Um dieses Skript zu verwenden, klicken Sie auf **Kopieren**, und fügen Sie dann den Code in eine Textdatei ein. Speichern Sie die Datei unter dem Namen „CreateCompanyWideTeam.ps1“ – fertig ist Ihr PowerShell-Skript.

````powershell
<#
.SYNOPSIS
This script allows you to create a company-wide team.
.DESCRIPTION
Use this script with the MicrosoftTeams PowerShell version 0.9.0 beta module to create a team with members and channels that you specify. Also leverages the AzureAD module to find all members to add.
.PARAMETER Owners
The comma-separated list of owners for your Team, who handle team settings and membership management. The owners should be specified by their User Principal Name. You must specify a minimum of two owners.
.PARAMETER TeamName
The name of your company-wide team. For example, this could be your company name.
.PARAMETER TeamDescription
The description of your company-wide team, in quotes.
.PARAMETER Channels
The comma-separated list of names of all the initial channels you want to set up. For example: "Announcements","Social at Work","Teamwork at Contoso".
.PARAMETER GroupID
If you have already created the group for your company-wide team, specify its GroupID. You can get this value from the display of the “Get-AzureADGroup | Sort DisplayName | Select DisplayName,ObjectID” command. This script had an issue during the rest of the execution and stopped early. 
.PARAMETER Members
The comma-separated list of members for your team that you want to manually add. To use this script a minimum of two members must be added. The members should be specified by their User Principal Name. To manually just add a single member, use the “Add-TeamUser -GroupId $IdOfGroup -Role Member -User $member” command.
#>
param(
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Owners,
    [Parameter(Mandatory=$false)][System.String]$TeamName,
    [Parameter(Mandatory=$false)][System.String]$TeamDescription,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Channels,
    [Parameter(Mandatory=$false)][System.String]$GroupID,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Members
)

function Create-Team(){
    Write-Host("Starting Team Creation")
    $GroupID = (New-Team -DisplayName $TeamName -AccessType Public -Description $TeamDescription).GroupId

    if([string]::IsNullOrEmpty($GroupID)){
        Write-Host("Team creation failed, please investigate and try again")
        Return
    }

    Write-Host("Team GroupID:", $GroupID)

    return ,$GroupID
} 

 
function Add-Channels($IdOfGroup){
        Write-Host("Starting Channel addition")
    foreach($channel in $Channels)
        {
            Write-Host("Enter Channel Description for " + $channel + " channel")
            $channelDescription = Read-Host
            New-TeamChannel -GroupId $IdOfGroup -DisplayName $channel -Description $channelDescription
        }
}
 
 
function Add-Members ($IdOfGroup){
    Write-Host("Starting Member addition")
    $allUsersInTenant = $Members 

    ## Only fetch full user list, if one isn't supplied
    if([string]::IsNullOrEmpty($Members))
    {
        $Error.Clear()
 

        Write-Host("Starting connection to AzureAD module") 
        Connect-AzureAD
 
        if($Error){
            Write-Host("Unable to connect to AzureAD. Please investigate and try again. To install the commandlet, use this command: Install-Module AzureAD")
            Return
        }
    
        

       ## Fetch all the users and create the member list
        $allUsersInTenant = (Get-AzureADUser).UserPrincipalName 

 
        Disconnect-AzureAD
    } 
    
    $NotAddedMembers = [System.Collections.ArrayList]@()
    $existingTeamMembers = (Get-TeamUser -GroupId $IdOfGroup).User

    foreach($user in $allUsersInTenant){
        $Error.Clear()

        if(!$existingTeamMembers.Contains($user)){
            Write-Host($user)

            if($Owners.Contains($user)){
                Add-TeamUser -GroupId $IdOfGroup -Role Owner -User $user.ToString()
                
                if($Error){
                    $NotAddedMembers.Add([Tuple]::Create($user,"Owner"))
                }
            }
            else{
                Add-TeamUser -GroupId $IdOfGroup -Role Member -User $user.ToString()
                
                if($Error) {
                    $NotAddedMembers.Add([Tuple]::Create($user,"Member"))
                }
            }
        }
    } 

    if($NotAddedMembers.Count > 0) {
        Write-Host("There are some members that did not get added, please retry these specific users")
        Write-Host($NotAddedMembers)
    } 


    ##Clear member addition errors
    $Error.Clear()
}
 
 
 
 
##Main Script
$Error.Clear()
Write-Host("Starting connection to MicrosoftTeams module") 

Connect-MicrosoftTeams
 
if($Error){
    Write-Host("There was an error installing\connecting to the Microsoft Teams PowerShell module. Please investigate. To install the module use the follow command: Install-Module MicrosoftTeams ")
    Return
}

##Create the team if existing GroupID isn't supplied. It's possible a Tenant Wide team was created, but there was an error adding members.
if([string]::IsNullOrEmpty($GroupID)){

    if([string]::IsNullOrEmpty($TeamName)){
        Write-Host("Missing an argument for parameter 'TeamName' and 'GroupID'. Specify a parameter of type 'System.String' and try again for either GroupID or TeamName and TeamDescription")
        Return
    }
    $GroupID = Create-Team
} 
 
if($Channels.Count -gt 0){
    Add-Channels $GroupID
} 

Add-Members $GroupID 
 
Disconnect-MicrosoftTeams

````


## <a name="script-explanation"></a>Erläuterung des Skripts


Eine vollständige Anleitung zur Verwendung dieses PowerShell-Skripts finden Sie im Tutorial [Erstellen eines firmenweiten Teams in Microsoft Teams mithilfe von PowerShell](../Company-wide-team-creation-powershell.yml).

Das Skript enthält fünf Abschnitte (von oben nach unten):
1. **Dokumentation und Variablendefinitionen**
2. **Function Create-Team**: Erstellt bei Bedarf ein Team. Wenn Sie keine Gruppen-ID („GroupID“) angeben, erstellt dieser Abschnitt das Team mit dem angegebenen Teamnamen („TeamName“) und der angegebenen Teambeschreibung („TeamDescription“).
3. **Function Add-Channels**: Wenn Sie Kanäle angegeben haben, wird hier die Kanalbeschreibung angefordert und anschließend der Kanal erstellt. 
4. **Function Add-Members**: Dieser Abschnitt ist für die gesamte Mitgliederverwaltung zuständig. Der Abschnitt stellt eine Verbindung mit AzureAD her, ruft eine Gruppe von Benutzern ab und fügt diese zum Team hinzu, wenn Sie keine Mitgliederliste bereitstellen. Der Abschnitt verarbeitet die Logik zum Hinzufügen von Besitzern und Mitgliedern. Mitglieder, die bereits zum Team gehören, werden nicht hinzugefügt. 
5. **Hauptprogramm**: In dieser Reihenfolge werden die Funktionen ausgeführt. 


