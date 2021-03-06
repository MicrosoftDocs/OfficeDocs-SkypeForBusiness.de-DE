---
title: Beispiel für ein PowerShell-Skript – Bereinigung der Bereitstellung in Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skript, um Teams zu deinstallieren und den Ordner "Teams" für Benutzer zu entfernen.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4b0bac09e18a9c6378623066889d6b1a891a4a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809485"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>Beispiel für ein PowerShell-Skript – Bereinigung der Bereitstellung von Teams

Verwenden Sie dieses Skript, um Teams zu entfernen. Mit diesem Skript wird Teams deinstalliert und der Ordner "Teams" für einen Benutzer entfernt. Führen Sie dieses Skript für jedes Benutzerprofil aus, in dem Teams auf einem Computer installiert wurde.


## <a name="sample-script"></a>Beispielskript

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````

## <a name="related-topics"></a>Verwandte Themen

- [Installieren von Microsoft Teams mit Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [Bereitstellen von Microsoft Teams mit Microsoft 365-Apps](https://docs.microsoft.com/deployoffice/teams-install)
