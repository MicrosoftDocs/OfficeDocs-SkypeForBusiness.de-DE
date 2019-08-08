---
title: PowerShell-Skriptbeispiel – Unterstützung beim Bereinigen von Microsoft Teams-Bereitstellungen
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
audience: admin
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: Mit diesem PowerShell-Skript können Sie Microsoft Teams auf bestimmten Computern oder für bestimmte Benutzer bereinigen.
localization_priority: Normal
ms.openlocfilehash: aa5ba0c6e94510449e1afd9c2fc03524c1846f9c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242876"
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
        Remove-Item -Path $TeamsPath -Recurse
                    
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
````


