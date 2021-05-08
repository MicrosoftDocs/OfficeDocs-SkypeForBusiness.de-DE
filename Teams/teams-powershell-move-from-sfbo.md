---
title: Wechseln von Skype for Business OnlineConnector zum Teams PowerShell-Modul
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
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094126"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Wechseln von Skype for Business OnlineConnector zum Teams PowerShell-Modul

Um von der Verwendung von Skype for Business Online Connector zum Teams PowerShell-Modul zum Verwalten von Teams zu wechseln, müssen Sie Ihre vorhandenen PowerShell-Skripts aktualisieren. In diesem Artikel wird erläutert, wie Sie dazu vor gehen.

1. Installieren Sie das neueste Teams PowerShell-Modul. Die schritte finden Sie unter [Installieren Microsoft Teams Powershell.](teams-powershell-install.md)
2. Deinstallieren Skype For Business Online Connector. Wechseln Sie dazu in der Systemsteuerung zu Programme und **Funktionen**, wählen Sie **Skype for Business Online, Windows PowerShell Modul** und dann Deinstallieren **aus.** 
3. Ändern Sie in Ihren PowerShell-Skripts den Modulnamen, auf den in verwiesen wird, von oder in ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Ändern Sie z. ```Import-Module -Name SkypeOnlineConnector``` B. in ```Import-Module -Name MicrosoftTeams``` .
4. Wenn Sie Teams PowerShell Module 2.0 oder höher verwenden, ändern Sie New-csOnlineSession in Verbinden-MicrosoftTeams. 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>Verwandte Themen

[Installieren Microsoft Teams Powershell](teams-powershell-install.md)

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)