---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593669"
---
1. Installieren Sie PowerShell, Version 7 oder höher. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Installieren von PowerShell auf Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Führen Sie PowerShell im Administratormodus aus.
1. Installieren Sie das Microsoft Graph PowerShell-Modul.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Vergewissern Sie sich, dass die Version 1.6.1 oder höher ist.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Installieren Sie Teams Preview-PowerShell-Modul.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Vergewissern Sie sich, dass es mindestens Version 4.1.0 ist und die Cmdlets für Schichtenconnector enthält.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. Installieren Sie das MSAL PowerShell-Modul.

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. Stellen Sie das Beenden von PowerShell ein, wenn beim Ausführen des Skripts ein Fehler auftritt.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Aktivieren Sie Skripts für die Ausführung in Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```