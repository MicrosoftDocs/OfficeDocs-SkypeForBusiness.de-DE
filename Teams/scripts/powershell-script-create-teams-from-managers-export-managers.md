---
title: PowerShell-Skriptbeispiel – Export Manager und ihre directs
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.reviewer: brandber
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skript, um eine Liste der Manager und deren direkt für Ihre Organisation zu exportieren, um ein Team für jeden Manager zu erstellen, dessen directs als Teammitglieder verwendet werden.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ccc5e5f435ccb096b3cd552fc8e2e87204a4abc
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951080"
---
# <a name="powershell-script-sample---export-managers-and-their-directs"></a><span data-ttu-id="c7058-103">PowerShell-Skriptbeispiel – Export Manager und ihre directs</span><span class="sxs-lookup"><span data-stu-id="c7058-103">PowerShell script sample - Export managers and their directs</span></span>

<span data-ttu-id="c7058-104">Verwenden Sie dieses PowerShell-Skript, um eine Liste der Manager und deren directs für Ihre Organisation zu exportieren, und zwar in Vorbereitung auf die Erstellung eines People Manager-Teams für jeden Manager, dessen directs als Teammitglieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7058-104">Use this PowerShell script to export a list of managers and their directs for your organization, in preparation for creating a people manager team for each manager with their directs as team members.</span></span>

<span data-ttu-id="c7058-105">Wenn Sie mehr über dieses PowerShell-Skript erfahren möchten, lesen Sie [Erstellen von Personen-Manager-Teams](../create-manager-directs-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c7058-105">To learn about this PowerShell script, read [Create people manager teams](../create-manager-directs-teams.md).</span></span>

<span data-ttu-id="c7058-106">Wenn PowerShell für Sie neu ist und Sie bei den ersten Schritten Hilfe benötigen, lesen Sie [Übersicht über Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="c7058-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="export-managers-script"></a><span data-ttu-id="c7058-107">Export-Manager-Skript</span><span class="sxs-lookup"><span data-stu-id="c7058-107">Export-Managers script</span></span>

```powershell
<# 
.SYNOPSIS 
  Name: Export-ManagersDirectsFromAAD.ps1 
  The purpose of this sample script is to build a list of managers and direct reports to use with the New-TeamsFromManagers.ps1 to create a team for each people manager and their directs.
   
.DESCRIPTION 
 This sample script create new Teams based on the tab delimited .txt file you provide of managers and direct reports. It assumes that DisplayName is not null.
 
.NOTES 
  &copy; 2020 Microsoft Corporation. All rights reserved. This document is provided 
    "as-is." Information and views expressed in this document, including URL and 
    other Internet Web site references, may change without notice.
 
.EXAMPLE 
  Export-ManagersDirectsFromAAD.ps1
#> 

#Also create a type that validated the users licenses to ease the create-team burden
#also add checks to see if the types are appropriately in place.

#region Configurable Inputs
$OutputFile = "ExportedManagersDirects.txt"
#endregion

#region Data Model
class DirectReport {
    [string] $UserPrincipalName
}
class Manager {
    [ValidateNotNullOrEmpty()] [string] $UserPrincipalName
    [string] $DisplayName
    [System.Collections.ObjectModel.Collection[DirectReport]]$DirectReports

    Manager (){
        $this.DirectReports = New-Object -TypeName System.Collections.ObjectModel.Collection["DirectReport"]
    }
}
#endregion

#region Helper Functions
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}
#endregion

#region Script Execution
#Step 1: Retrieve AAD users - attribute filtering off DirectReport cannot be applied
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to retrieve ALL Azure AD users."
$AllAADUsers = Get-AzureADUser -All $true -Filter "UserType eq 'Member' and AccountEnabled eq true"
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Azure AD Users Complete.. `n"

#Step 2: Iterate through users, identify Managers and Directs
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to Retrieve Directs Reports"
$Managers = New-Object -TypeName System.Collections.ObjectModel.Collection["Manager"]
foreach ($user in $AllAADUsers) {
    $directs = Get-AzureADUserDirectReport -ObjectId $user.UserPrincipalName
        if ($null -ne $directs) {
            if ($user.DisplayName -ne "") {
                $manager = New-Object -TypeName Manager
                $manager.UserPrincipalName = $user.UserPrincipalName
                $manager.DisplayName = $user.DisplayName

                foreach ($direct in $directs) {
                    $directReport = New-Object -TypeName DirectReport
                    $directReport.UserPrincipalName = $direct.UserPrincipalName
                    $manager.DirectReports.Add($directReport)
                }
                $Managers.Add($manager)
                
            }
        Write-Host "$(Get-Timestamp) Info: Added Manager: $($manager.UserPrincipalName)"
        $i++
    }
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Direct Reports Complete.. `n"

#Step 3: Output in tab delimited .txt format
$output = New-Object -TypeName System.Collections.ObjectModel.Collection["String"]
$header = "Name`tDisplayName`tDirects"
$output.Add($header)

foreach ($manager in $Managers) {
    [string] $directs = ""
    foreach ($direct in $manager.DirectReports)
    {
        $directs += $direct.UserPrincipalName + ','
    }
    $directs = $directs.Substring(0,$directs.Length-1)
    $row = "$($manager.UserPrincipalName)`t$($manager.DisplayName)`t$($directs)"
    $output.Add($row) 
}

#If Output File already exists from a previous run, it will be replaced.
$testPath = Test-Path .\$($OutputFile)
if ($testPath) {
    Remove-Item .\$($OutputFile)
}

foreach ($line in $output) {
    $line | Out-File -FilePath .\$($OutputFile) -Append
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Exported tab delimited output to $($OutputFile). `n"
#endregion



```


