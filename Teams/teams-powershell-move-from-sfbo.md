---
title: Migrieren von Skype for Business OnlineConnector zum Teams PowerShell-Modul
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
ms.openlocfilehash: 9dd03b414eba2ebc10dcfdbbb4e0ea2712fff73ca2cb0eb643aa132936ab1470
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299005"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrieren von Skype for Business OnlineConnector zum Teams PowerShell-Modul

Teams Das PowerShell-Modul stellt einen vollständigen Satz von Cmdlets zum Verwalten von Teams direkt über die PowerShell-Befehlszeile zur Verfügung. Administratoren benötigen keine Skype For Business Online Connector für ihre Teams Verwaltung.

> [!NOTE]
> Teams Administrator wurden über den Beitrag des Nachrichtencenters (MC244740, datiert vom 16. März 2021) benachrichtigt. MC250940, datiert 16. April 2021) über diese Änderung.
>
> Teams Das PowerShell-Modul verwendet die moderne Authentifizierung, aber der zugrunde liegende WinRM-Client (Windows Remote Management) muss so konfiguriert werden, dass die Standardauthentifizierung zulässig ist. Anweisungen zum Aktivieren von WinRM [für die](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) Standardauthentifizierung Windows PowerShell Unter Herunterladen und Installieren von E-Mail.

> [!WARNING]
> Skype for Business Onlineconnectorverbindungen werden ab dem 17. Mai 2021 abgelehnt. Wenden Sie sich an den Microsoft-Support, um Hilfe und Support für die Migration zu Teams PowerShell-Modul zu erhalten.

## <a name="how-to-migrate"></a>Migrieren

Die Migration von der Skype for Business Online Connector zu Teams PowerShell-Modul ist einfach und einfach. Die folgenden Schritte erklären, wie Sie dazu vorgehen müssen.

1. Installieren Sie das neueste Teams PowerShell-Modul. Schritte finden Sie unter [Installieren Microsoft Teams PowerShell.](teams-powershell-install.md)

2. Deinstallieren Skype For Business Online Connector. Wechseln Sie dazu in der Systemsteuerung zu Programme und **Funktionen**, wählen Sie **Skype for Business Online,** Windows PowerShell Modul und dann Deinstallieren **aus.**

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

## <a name="online-support"></a>Onlinesupport

Sparen Sie Zeit, indem Sie Ihre Serviceanfrage online starten. Wir helfen Ihnen, eine Lösung zu finden oder Sie mit dem technischen Support zu verbinden.

1.  Wechseln Sie zum Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) . Wenn Eine Meldung angezeigt wird, die ankn: Sie verfügen nicht über die Berechtigung zum Zugriff auf diese Seite oder zum Ausführen dieser Aktion, sind Sie kein Administrator. Wer verfügt in meinem Unternehmen über Administratorberechtigungen?

2.  Wählen Sie Benötigen **Sie Hilfe? aus.** aus.

3.  Benötigen **Sie Hilfe?** teilen Sie uns mit, wozu Sie Hilfe benötigen, und drücken Sie dann die EINGABETASTE.

4.  Wenn die Ergebnisse nicht helfen, wählen Sie Support **kontaktieren aus.**

5.  Geben Sie eine Beschreibung des Problems ein, bestätigen Sie Ihre Kontaktnummer und E-Mail-Adresse, wählen Sie Ihre bevorzugte Kontaktmethode aus, und wählen Sie dann **Kontakt aus.** Die erwartete Wartezeit wird unter Benötigen Sie Hilfe? angezeigt. aus.

## <a name="related-topics"></a>Verwandte Themen

[Installieren Microsoft Teams PowerShell](teams-powershell-install.md)

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)
