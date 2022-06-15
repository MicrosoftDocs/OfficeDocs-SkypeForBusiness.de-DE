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
ms.openlocfilehash: ad20cc285a9e882c45d2d158601ebcc90236dbf5
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103372"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell-Modul – Unterstützte Versionen

Microsoft Teams PowerShell Module (TPM)-Versionen in der 4.x.x-Serie oder höher sind die einzigen Versionen, die jetzt unterstützt werden. Alle früheren Versionen sind seit dem 15. Juni 2022 vollständig eingestellt, & nicht mehr funktioniert (Nachrichtencenter-Beitrag zur Referenz - MC350371). 

Es wird empfohlen, auf die neueste Teams PowerShell-Modulversion zu aktualisieren.


## <a name="important-notes"></a>Wichtige Hinweise

- Versionshinweise zu allen Teams PowerShell-Modulversionen finden Sie unter [Teams PowerShell-Versionshinweisen](teams-powershell-release-notes.md).

- Zum Aktualisieren eines PowerShell-Moduls sollten Sie dieselbe Methode verwenden, die zum Installieren des Moduls verwendet wird. Wenn Sie z. B. "Install-Module" ursprünglich verwendet haben, sollten Sie [Update-Module](/powershell/module/powershellget/update-module) verwenden, um die neueste Version abzurufen.

  ```powershell
  Update-Module MicrosoftTeams
  ```

- Wenn Sie von Teams PowerShell-Modul Version 1.1.6 aktualisieren, aktualisieren Sie Ihre Skripts so, dass sie anstelle von `New-CsOnlineSession`verwendet werden`Connect-MicrosoftTeams`.

- Während des Updates wird empfohlen, TPM 4.x.x/3.x.x nicht zusammen mit Versionen vor 3.0.0 zu verwenden. Beispielsweise wird die gemeinsame Verwendung der Versionen 4.x.x & 2.6.0 für verschiedene Administratorvorgänge in derselben Organisation nicht empfohlen.

- Verwandte Änderungen
  - Updates für Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.x.x und höher – weitere Details in [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) & [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) (Nachrichtencenterbeitrag – MC340774).

  - Änderungen an Telefon Nummernzuweisung – weitere Details in [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & [Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) (Nachrichtencenterbeitrag – MC316139).

  - Parameteränderungen in Get-CsTenant – weitere Details in [Get-CsTenant](/powershell/module/skype/get-cstenant) (Beitrag im Nachrichtencenter – MC365397).
  
  - Wenn Ihre Skripts Neue/Satz von Richtlinien- oder Konfigurations-Cmdlets mit PSListModifier-Typparametern verwenden, wird empfohlen, die neueste Version (4.2.0 oder höher) zu verwenden.

- Bei Verwendung von TPM 4.x.x oder höher wird empfohlen, keine der [unten](#deprecated-cmdlets) aufgeführten veralteten oder nicht unterstützten Cmdlets zu verwenden.

## <a name="deprecated-cmdlets"></a>Veraltete Cmdlets

- Einige der cmdlets, die kürzlich veraltet waren, sind unten aufgeführt. Details dazu finden Sie in den jeweiligen öffentlichen Dokumentationen.
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- Cmdlets, die für Microsoft Teams Szenarien nicht unterstützt/relevant sind, sind unten aufgeführt.
  - [Get| Set]-CsUserPstnSettings
  - [Get| Festlegen| Aktivieren| Disable]-CsMeetingRoom
  - [Zuschuss| Abrufen| Festlegen| Neu| Remove]-CsConferencingPolicy
  - [Zuschuss| Abrufen| Festlegen| Neu| Remove]-CsClientPolicy
  - [Zuschuss| Get]-CsHostedVoicemailPolicy
  - [Zuschuss| Abrufen| Festlegen| Neu| Remove]-CsMobilityPolicy
  - [Zuschuss| Get]-CsVoiceRoutingPolicy
  - [Zuschuss| Get]-CsBroadcastMeetingPolicy
  - [Zuschuss| Get]-CsCloudMeetingPolicy
  - [Zuschuss| Get]-CsGraphPolicy
  - [Zuschuss| Abrufen| Festlegen| Neu| Remove]-CsExternalUserCommunicationPolicy
  - [Zuschuss| Abrufen| Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [Get| Set]-CsBroadcastMeetingConfiguration
  - [Get| Set]-CsOAuthConfiguration
  - [Get| Set]-CsMeetingConfiguration
  - [Get| Set]-CsTenantHybridConfiguration
  - [Get| Set]-CsPushNotificationConfiguration
  - [Get| Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [Get| Set]-CsTenantPublicProvider
  - Get-CsHostingProvider
  - [Get| Festlegen| Registrieren| Registrierung aufheben]-CsHybridPSTNAppliance
  - [Get| Festlegen| Neu| Remove]-CsHybridPSTNSite
  - [Get| Set]-CsHybridMediationServer
  - [Get| Festlegen| Neu| Remove]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [Get| Festlegen| Neu| Remove]-CsTeamsPinnedApp
  - [Get| Festlegen| Neu| Remove]-CsTenantCatalogApp
  - [Get| Festlegen| Neu| Remove]-CsGlobalCatalogApp
  - [Get| Festlegen| Neu| Remove]-CsDefaultCatalogApp
  - [Get| Festlegen| Neu| Remove]-CsTeamsAppPreset

## <a name="related-topics"></a>Verwandte Themen

[Teams PowerShell–Versionshinweise](teams-powershell-release-notes.md)

[Installieren Microsoft Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet-Referenz](/powershell/module/teams)

[Skype for Business Cmdlet-Referenz](/powershell/module/skype)
