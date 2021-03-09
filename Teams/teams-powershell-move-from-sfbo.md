---
title: Wechseln von Skype for Business Online Connector zum Teams PowerShell-Modul
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie von Skype for Business Online Connector zum Teams PowerShell-Modul wechseln, um Teams zu verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569081"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Wechseln von Skype for Business Online Connector zum Teams PowerShell-Modul

Um von der Verwendung von Skype for Business Online Connector zum Teams PowerShell-Modul zu wechseln, um Teams zu verwalten, müssen Sie Ihre vorhandenen PowerShell-Skripts aktualisieren. In diesem Artikel wird erläutert, wie Sie dies tun.

1. Installieren Sie das neueste Teams PowerShell-Modul. Die Schritte finden Sie unter [Installieren von Microsoft Teams Powershell](teams-powershell-install.md).
2. Deinstallieren Sie Skype for Business Online Connector. Wechseln Sie dazu in der Systemsteuerung zu Programme **und Features,** wählen **Sie Skype for Business Online, Windows PowerShell Modul** und dann **Deinstallieren aus.** 
3. Ändern Sie in Ihren PowerShell-Skripts den Modulnamen, auf den verwiesen wird, von ```Import-Module``` ```SkypeOnlineConnector``` oder in ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Ändern Sie z. B. ```Import-Module -Name SkypeOnlineConnector``` in ```Import-Module -Name MicrosoftTeams``` .
4. Wenn Sie Teams PowerShell Module 2.0 oder höher verwenden, ändern Sie New-csOnlineSession in Connect-MicrosoftTeams. 

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

[Installieren von Microsoft Teams Powershell](teams-powershell-install.md)

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Versionshinweise zu Teams PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdletreferenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdletreferenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
