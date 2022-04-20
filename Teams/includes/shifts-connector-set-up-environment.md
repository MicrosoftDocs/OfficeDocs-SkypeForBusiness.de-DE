---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976017"
---
1. Installieren Sie PowerShell, Version 7 oder höher. Eine schrittweise Anleitung finden Sie unter [Installieren von PowerShell auf Windows](/powershell/scripting/install/installing-powershell-on-windows).

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

1. Installieren Sie das Teams Preview-PowerShell-Modul.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Stellen Sie sicher, dass sie mindestens Version 4.1.0 ist und die Shifts-Connector-Cmdlets enthält.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. Legen Sie fest, dass PowerShell beendet wird, wenn beim Ausführen des Skripts ein Fehler auftritt.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Aktivieren Sie die Ausführung von Skripts in Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```