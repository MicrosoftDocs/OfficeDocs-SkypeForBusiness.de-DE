---
title: PowerShell-Skriptbeispiel – Bereinigung der Teams-Bereitstellung
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skript, um Teams zu deinstallieren und den Teams-Ordner für Benutzer zu entfernen.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7875cb01b928567d5883f36e21eb2f0de0bccf6
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825689"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell-Skriptbeispiel – Bereinigung der Teams-Bereitstellung

Verwenden Sie dieses Skript, um Teams zu entfernen. Dieses Skript deinstalliert Teams und entfernt den Teams-Ordner für einen Benutzer. Führen Sie dieses Skript für jedes Benutzerprofil aus, in dem Teams auf einem Computer installiert wurde.


## <a name="sample-script"></a>Beispielskript

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

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
- [Bereitstellen von Teams mit Microsoft 365 Apps](/deployoffice/teams-install)
