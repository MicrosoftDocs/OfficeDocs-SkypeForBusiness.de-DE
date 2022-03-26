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
ms.openlocfilehash: 3fc980420b53d850c48e680d25bdbf6ec437e8f8
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783965"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell-Modul – Unterstützte Versionen

Microsoft Teams von PowerShell-Modulversionen (TPM), die in der Version 4.x.x oder höher verfügbar sind, werden in Zukunft nur noch unterstützt. Alle früheren Versionen befinden sich im Ruhestandspfad. Es wird empfohlen, Teams PowerShell-Modul auf die neueste Version zu aktualisieren.



## <a name="new-organizations"></a>Neue Organisationen

Organisationen, die Teams-Modul integrieren, können ab dem 1. April 2022 Teams PowerShell-Modul der Reihe 4.x.x oder höher verwenden.



## <a name="current-organizations-non-tpm-active"></a>Aktuelle Organisationen (nicht TPM aktiv)

Organisationen, die das Teams PowerShell-Modul in den letzten drei Monaten (22. Januar bis 22. März) nicht verwendet haben, können Teams PowerShell-Modul nur in der Reihe "4.x.x" oder höher ab dem 1. April 2022 verwenden.



## <a name="current-organizations-tpm-active"></a>Aktuelle Organisationen (TPM aktiv)

Organisationen, die in den letzten drei Monaten (22. Januar bis 22. März) das Teams PowerShell-Modul verwendet haben, können ab dem 15. Juni 2022 nur Teams PowerShell-Modul in der Reihe "4.x.x" oder höher verwenden. 



## <a name="important-notes"></a>Wichtige Hinweise

- Anmerkungen zu dieser Version Teams PowerShell-Moduls finden Sie [Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md).

- Zum Aktualisieren eines beliebigen PowerShell-Moduls sollten Sie die gleiche Methode zum Installieren des Moduls verwenden. Wenn Sie z. B. "Install-Module" ursprünglich verwendet haben, sollten Sie [Update-Module](/powershell/module/powershellget/update-module) verwenden, um die neueste Version zu erhalten.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Aktualisieren Sie beim Teams Version 1.1.6 des PowerShell-Moduls Ihre Skripts so, dass anstelle `Connect-MicrosoftTeams` von verwendet wird`New-CsOnlineSession`.

-   Während des Updates wird empfohlen, TPM 4.x.x/3.x.x nicht zusammen mit Versionen zu verwenden, die älter als 3.0.0 sind. Beispielsweise wird die gemeinsame Verwendung der Versionen 4.x.x & 2.6.0 für verschiedene Administratorvorgänge in derselben Organisation nicht empfohlen. 

- Verwandte Änderungen
  * Updates für Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.x.x und höher – weitere Details finden Sie unter [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (Message center post – MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Änderungen an der Telefon-Nummernzuweisung: Weitere Details finden Sie unter [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Beitrag im Nachrichtencenter – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>Verwandte Themen

[Teams zu PowerShell-Versionshinweisen](teams-powershell-release-notes.md)

[Installieren Microsoft Teams PowerShell](teams-powershell-install.md)

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/module/teams) 

[Skype for Business-Cmdlet-Referenz](/powershell/module/skype) 
