---
title: PowerShell-Skriptbeispiel – Unterstützung beim Bereinigen von Microsoft Teams-Bereitstellungen
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: Mit diesem PowerShell-Skript können Sie Microsoft Teams auf bestimmten Computern oder für bestimmte Benutzer bereinigen.
localization_priority: Normal
ms.openlocfilehash: cd19bb3b0d26069d339b61b5d4bf059fef724407
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920612"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>PowerShell-Skriptbeispiel – Bereinigen von Microsoft Teams-Bereitstellungen
-------------------------------------------------------------------------

Dieses PowerShell-Skript kann zum Bereinigen von Microsoft Teams auf bestimmten Computern oder für bestimmte Benutzer genutzt werden. Es sollte für alle Benutzer auf dem jeweiligen Computer ausgeführt werden. 


## <a name="sample-script"></a>Beispielskript

````powershell
<#
.SYNOPSIS
This script allows you to uninstall the Microsoft Teams app and remove Teams directory for a user.
.DESCRIPTION
Use this script to clear the installed Microsoft Teams application. Run this PowerShell script for each user profile for which the Teams App was installed on a machine. After the PowerShell has executed on all user profiles, Teams can be redeployed.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if (Test-Path -Path $TeamsUpdateExePath) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process -FilePath $TeamsUpdateExePath -ArgumentList "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    if (Test-Path -Path $TeamsPath) {
        Write-Host "Deleting Teams directory"
        Remove-Item –Path $TeamsPath -Recurse
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
````


