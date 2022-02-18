---
title: Beispielskript – Microsoft Teams PowerShell-Skript der Firewall
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: medium
search.appverid: MET150
description: Ein Beispielskript, das zum Konfigurieren von Windows verwendet werden kann, Teams Verbindungen durch Windows zulassen.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1131868af2b81b1d786bd760518f56633ec8aa83
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893758"
---
# <a name="sample-script---microsoft-teams-firewall-powershell-script"></a>Beispielskript – Microsoft Teams PowerShell-Skript der Firewall

Dieses Beispielskript, das auf Clientcomputern im Kontext eines Administratorkontos mit erweiterten Berechtigungen ausgeführt werden muss, erstellt eine neue eingehende Firewallregel für jeden Benutzerordner unter C:\Users. Wenn Teams diese Regel findet, kann sie verhindern, dass die Teams-Anwendung Benutzer zum Erstellen von Firewallregeln auffordert, wenn der Benutzer seinen ersten Aufruf über Teams tätigt.

```powershell

<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions.
   The script will create a new inbound firewall rule for each user folder found in c:\users.
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
