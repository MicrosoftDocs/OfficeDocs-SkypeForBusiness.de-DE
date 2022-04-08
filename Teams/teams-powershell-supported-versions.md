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
description: Erfahren Sie mehr über Versionen, die vom Teams PowerShell-Modul unterstützt werden, das für die Verwaltung von Microsoft Teams verwendet wird.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9eb6754a9fa89d1298e22f6c713e8c4d28d5861
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712959"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell-Modul – Unterstützte Versionen

Microsoft Teams PowerShell-Modulversionen (TPM) in der 4.x.x-Serie oder höher werden die einzigen Versionen sein, die in Zukunft unterstützt werden. Alle früheren Versionen befinden sich auf dem Rentenpfad. Es wird empfohlen, Teams PowerShell-Modul auf die neueste Version zu aktualisieren.



## <a name="new-organizations"></a>Neue Organisationen

Organisationen, die neu in Teams integriert sind, können ab dem 1. April 2022 nur Teams PowerShell-Modul in der 4.x.x-Serie oder höher verwenden.



## <a name="current-organizations-non-tpm-active"></a>Aktuelle Organisationen (nicht TPM aktiv)

Organisationen, die Teams PowerShell-Modul in den letzten drei Monaten (22. Januar – 22. März) nicht verwendet haben, können ab dem 1. April 2022 nur Teams PowerShell-Modul in der 4.x.x-Serie oder höher verwenden.



## <a name="current-organizations-tpm-active"></a>Aktuelle Organisationen (TPM aktiv)

Organisationen, die in den letzten drei Monaten (22. Januar – 22. März) Teams PowerShell-Modul verwendet haben, können ab dem 15. Juni 2022 nur Teams PowerShell-Modul in der 4.x.x-Serie oder höher verwenden. Nachrichtencenter-Beitrag zur Referenz – MC350371. 



## <a name="important-notes"></a>Wichtige Hinweise

- Versionshinweise zu allen Teams PowerShell-Modulversionen finden Sie unter [Teams PowerShell-Versionshinweisen](teams-powershell-release-notes.md).

- Zum Aktualisieren eines PowerShell-Moduls sollten Sie dieselbe Methode verwenden, die zum Installieren des Moduls verwendet wird. Wenn Sie z. B. "Install-Module" ursprünglich verwendet haben, sollten Sie [Update-Module](/powershell/module/powershellget/update-module) verwenden, um die neueste Version abzurufen.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Wenn Sie von Teams PowerShell-Modul Version 1.1.6 aktualisieren, aktualisieren Sie Ihre Skripts so, dass sie anstelle von `New-CsOnlineSession`verwendet werden`Connect-MicrosoftTeams`.

-   Während des Updates wird empfohlen, TPM 4.x.x/3.x.x nicht zusammen mit Älteren als 3.0.0 zu verwenden. Beispielsweise wird die gemeinsame Verwendung der Versionen 4.x.x & 2.6.0 für verschiedene Administratorvorgänge in derselben Organisation nicht empfohlen. 

- Verwandte Änderungen
  * Updates für Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.x.x und höher – weitere Details in [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (Nachrichtencenter-Beitrag – MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Änderungen an Telefon Nummernzuweisung – weitere Details in [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Nachrichtencenterbeitrag – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="deprecated-cmdlets"></a>Veraltete Cmdlets

Einige der Cmdlets, die kürzlich veraltet sind oder für Microsoft Teams Szenarien nicht unterstützt werden, sind unten aufgeführt. Details dazu finden Sie in den jeweiligen öffentlichen Dokumentationen. 

- [Get-CsUserPstnSettings](/powershell/module/skype/get-csuserpstnsettings), [Set-CsUserPstnSettings](/powershell/module/skype/set-csuserpstnsettings)
- [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
- [Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom), [Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom), [Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom), [Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom)
- [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
- [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
- [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  



## <a name="related-topics"></a>Verwandte Themen

[Teams PowerShell–Versionshinweise](teams-powershell-release-notes.md)

[Installieren Microsoft Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet-Referenz](/powershell/module/teams) 

[Skype for Business Cmdlet-Referenz](/powershell/module/skype) 
