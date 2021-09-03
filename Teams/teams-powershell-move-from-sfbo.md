---
title: Migrieren von Skype for Business Online Connector zum PowerShell Teams Modul
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie von Skype for Business Online Connector zum PowerShell Teams Modul wechseln, um Ihre Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866357"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrieren von Skype for Business Online Connector zum PowerShell Teams Modul

Teams Das PowerShell-Modul stellt einen vollständigen Satz von Cmdlets zum Verwalten von Teams direkt über die PowerShell-Befehlszeile zur Verfügung. Administratoren müssen for Skype For Business Online Connector nicht für ihre Teams verwenden.

> [!NOTE]
> Teams-Administrator wurden über den Beitrag des Nachrichtencenters (MC244740, dated 16. März 2021; MC250940, datiert 16. April 2021) über diese Änderung.
>
> Teams Das PowerShell-Modul verwendet die moderne Authentifizierung, aber der zugrunde liegende WinRM-Client (Windows Remote Management) muss so konfiguriert werden, dass die Standardauthentifizierung zulässig ist. Anweisungen [zum Aktivieren](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) von WinRM für die Standardauthentifizierung finden Windows PowerShell unter Herunterladen und Installieren von E-Mail-Funktionen.

## <a name="how-to-migrate"></a>Migrieren

Das Migrieren von Skype for Business Online Connector zu Teams PowerShell-Modul ist einfach und einfach. In den folgenden Schritten wird erläutert, wie Sie dazu vorgehen müssen.

1. Installieren Sie das neueste Teams PowerShell-Modul. Die schritte finden Sie unter [Installieren Microsoft Teams PowerShell.](teams-powershell-install.md)

2. Deinstallieren Skype For Business Online Connector. Wechseln Sie dazu in der Systemsteuerung zu Programme und **Funktionen**, wählen Sie **Skype for Business Online, Windows PowerShell Modul** und dann Deinstallieren **aus.**

3. Ändern Sie in Ihren PowerShell-Skripts den Namen des Moduls, auf das verwiesen wird, in ```Import-Module```

    `SkypeOnlineConnector` oder `LyncOnlineConnector` auf `MicrosoftTeams` .

    Ändern Sie z. `Import-Module -Name SkypeOnlineConnector` B. in `Import-Module -Name MicrosoftTeams` .

4. Wenn Sie Teams PowerShell-Modul 2.0 oder höher verwenden, aktualisieren Sie Ihre Skripts, die sich auf `New-CsOnlineSession` `Connect-MicrosoftTeams` beziehen. `Import-PsSession`ist nicht mehr erforderlich, um eine Skype for Business-Remote-PowerShell-Sitzung so einrichten, wie dies bei Verwendung von implizit `Connect-MicrosoftTeams` erfolgt.

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>Verwandte Themen

[Installieren Microsoft Teams PowerShell](teams-powershell-install.md)

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)
