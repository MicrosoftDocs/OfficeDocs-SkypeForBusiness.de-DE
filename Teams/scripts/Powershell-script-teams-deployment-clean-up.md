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
ms.openlocfilehash: 6e543e31dd926075d83ad0ccf7187ac602ba8065
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568086"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="76cd2-103">PowerShell-Skriptbeispiel – Bereinigen von Microsoft Teams-Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="76cd2-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="76cd2-104">Dieses PowerShell-Skript kann zum Bereinigen von Microsoft Teams auf bestimmten Computern oder für bestimmte Benutzer genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="76cd2-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="76cd2-105">Es sollte für alle Benutzer auf dem jeweiligen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76cd2-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="76cd2-106">Beispielskript</span><span class="sxs-lookup"><span data-stu-id="76cd2-106">Sample script</span></span>

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


