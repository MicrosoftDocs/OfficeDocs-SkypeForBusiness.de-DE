---
title: Teams PowerShell-Modul – Unterstützte Versionen
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über die Versionen, die von Teams PowerShell-Modul unterstützt werden, das für die Verwaltung von Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea8a755c75c5f91c5dbf3a4cd4dd749ac576557c
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2022
ms.locfileid: "63762009"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell-Modul – Unterstützte Versionen

Microsoft Teams 4.0.0 oder höher des PowerShell-Moduls (TPM) werden in Zukunft nur noch unterstützt. Alle früheren Versionen befinden sich im Ruhestandspfad.



## <a name="new-organizations"></a>Neue Organisationen

Organisationen, die Teams integriertes PowerShell-Modul verwenden, können ab dem 1. April 2022 nur Teams PowerShell Module 4.0.0 oder höher verwenden.



## <a name="current-organizations-non-tpm-active"></a>Aktuelle Organisationen (nicht TPM aktiv)

Organisationen, die TPM in den letzten drei Monaten (22. Januar bis 22. März) nicht verwendet haben, können ab dem 1. April 2022 nur TPM 4.0.0 oder höher verwenden.



## <a name="current-organizations-tpm-active"></a>Aktuelle Organisationen (TPM aktiv)

Organisationen, die in den letzten drei Monaten (22. Januar bis 22. März) TPM verwendet haben, können ab dem 15. Juni 2022 nur TPM 4.0.0 oder höher verwenden. Es wird empfohlen, Teams PowerShell-Modul auf die neueste Version zu aktualisieren.


## <a name="important-notes"></a>Wichtige Hinweise

- Anmerkungen zu dieser Version Teams PowerShell-Moduls finden Sie [Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md).

- Zum Aktualisieren eines beliebigen PowerShell-Moduls sollten Sie die gleiche Methode zum Installieren des Moduls verwenden. Wenn Sie z. B. "Install-Module" ursprünglich verwendet haben, sollten Sie [Update-Module](/powershell/module/powershellget/update-module) verwenden, um die neueste Version zu erhalten.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Aktualisieren Sie beim Teams Version 1.1.6 des PowerShell-Moduls Ihre Skripts so, dass anstelle `Connect-MicrosoftTeams` von verwendet wird`New-CsOnlineSession`.

-   Während des Updates wird empfohlen, TPM 4.x.x/3.x.x nicht zusammen mit Versionen zu verwenden, die älter als 3.0.0 sind. Beispielsweise empfiehlt es sich nicht, die Versionen 4.0.0 & 2.6.0 zusammen für verschiedene Administratorvorgänge in derselben Organisation zu verwenden. 

- Verwandte Änderungen
  * Updates für Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.0.0 und höher – weitere Details finden Sie unter [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (Message center post – MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Änderungen an der Telefon-Nummernzuweisung: Weitere Details finden Sie unter [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Beitrag im Nachrichtencenter – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>Verwandte Themen

[Teams zu PowerShell-Versionshinweisen](teams-powershell-release-notes.md)

[Installieren Microsoft Teams PowerShell](teams-powershell-install.md)

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/module/teams) 

[Skype for Business-Cmdlet-Referenz](/powershell/module/skype) 
