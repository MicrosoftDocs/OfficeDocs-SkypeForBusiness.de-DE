---
title: PowerShell-Skript-Beispiel – unterstützt Sie bei der Bereitstellung von Microsoft-Teams, Bereinigung
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: Verwenden Sie dieses Skript PowerShell Microsoft-Teams, auf den Zielcomputern oder für bestimmte Benutzer bereinigen.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9b95ca42e1f110b72d092ada65b2d672627fac4f
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887282"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="53b37-103">PowerShell-Skript-Beispiel – Bereitstellung von Microsoft-Teams, bereinigen</span><span class="sxs-lookup"><span data-stu-id="53b37-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="53b37-104">Diese PowerShell-Skript kann für die Bereinigung von Microsoft-Teams Zielcomputern oder Benutzer genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="53b37-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="53b37-105">Es sollte für jeden Benutzer auf einem Zielcomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53b37-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="53b37-106">Beispielskript</span><span class="sxs-lookup"><span data-stu-id="53b37-106">Sample script</span></span>

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


