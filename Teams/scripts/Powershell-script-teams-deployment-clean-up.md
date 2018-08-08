---
title: PowerShell-Skript-Beispiel – unterstützt Sie bei der Bereitstellung von Microsoft-Teams, Bereinigung
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: Verwenden Sie dieses Skript PowerShell Microsoft-Teams, auf den Zielcomputern oder für bestimmte Benutzer bereinigen.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e159c06a27151523e52db5bf7e0aa2eab33620a9
ms.sourcegitcommit: dba47a65b0725806c98702bb7362a1b105cc93df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "21249192"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>PowerShell-Skript-Beispiel – Bereitstellung von Microsoft-Teams, bereinigen
-------------------------------------------------------------------------

Diese PowerShell-Skript kann für die Bereinigung von Microsoft-Teams Zielcomputern oder Benutzer genutzt werden. Es sollte für jeden Benutzer auf einem Zielcomputer ausgeführt werden. 


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


