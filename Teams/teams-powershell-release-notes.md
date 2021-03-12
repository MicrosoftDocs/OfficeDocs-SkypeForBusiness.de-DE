---
title: Versionshinweise zu Microsoft Teams PowerShell
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über die neuesten Änderungen in Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e464071252ebbd713495ba070ba3f9ae8a23c3b
ms.sourcegitcommit: 74f12ed15e1aa1106fa47b95597bde451b0b37f4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741896"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Versionshinweise zu Microsoft Teams PowerShell

Diese Seite enthält das neueste Änderungsprotokoll von Teams PowerShell sowohl für allgemeine Verfügbarkeit als auch für Public Preview-Versionen.

## <a name="release-notes"></a>Versionshinweise

> [!NOTE]
> **-preview** in der folgenden Versionsspalte stellt Updates für die öffentliche Vorschau von Teams PowerShell dar.

| Datum | Version | Updates |
|------- | -------------------- | ------------------------------ |
| März 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Verwendet MSAL für die Authentifizierung & Autorisierung</li><li>Umgestalten von Richtlinienpaket-Cmdlets und Addierung von Gruppenpaketzuordnungen</li><li>Erhebliche Leistungsverbesserungen für Get-Team Cmdlet</li> <li>Verbesserte Protokollierungs- und Debuggingoption für vorhandene Cmdlets </li> <li>Hinzugefügte Vorlagenverwaltungs-Cmdlets</li> <li>Veraltete New-CsOnlineSession</li>|
| Februar 2021 | [1.1.11-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Hinzugefügte Vorlagenverwaltungs-Cmdlets</li><li>Verbesserungen von Mezzo und Batching für Get-Team Cmdlet</li> <li>Verbesserte Protokollierungs- und Debuggingoption für vorhandene Cmdlets </li> <li>Umgestalten von Richtlinienpaket-Cmdlets</li>|
| Dezember 2020 | [1.1.10-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Updates für das Cmdlet "Neues Team" mit erhöhten Wiederholungen und einer erhöhten Schlafdauer</li>|
| Dezember 2020 | [1.1.9-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Updates für die Skype for Business Online-Integration</li><li>Beheben der doppelten Eingabeaufforderung mit Connect-Microsoft Teams</li>|
| November 2020 | [1.1.8-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Fügt benutzerdefinierte Richtlinienpaket-Cmdlets hinzu</li><li>Korrekturen für die Uploadbefehle für die Zielhierarchie</li>|
| November 2020 | [1.1.7-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Verwendet MSAL für die Authentifizierung & Autorisierung</li><li>Umgestalten von Richtlinienpaket-Cmdlets und Addierung von Gruppenpaketzuordnungen</li><li>Umgestaltende Uploadbefehle für die Zielhierarchie für die Verwendung eines asynchronen Modells</li> <li>Der Benutzer wird während der anfänglichen Authentifizierung zweimal aufgefordert, wenn er den Parameter -credential nicht verwendet. Benutzer können Anmeldeinformationen über den Parameter -credential übergeben, um eine doppelte Eingabeaufforderung zu vermeiden. Dieses Verhalten wird in der nächsten Version behoben.</li> |
| September 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online Connector-Integration</li> |
| September 2020 | [1.1.5-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online Connector-Integration</li> |
| Juli 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Hinzugefügte [Gruppenrichtlinienzuordnungs-Cmdlets](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| Juni 2020 | [1.1.3-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online Connector-Integration<li>Get-Team Optimierungen<li>Verbesserte Zuverlässigkeit</li> |
| Juni 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Vorladen des Cmdlets hinzugefügt<li>.Net Framework-Optimierungen</li>   |
| April 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Signieren von Authenticode und Assembly<li>Hinzugefügte Get-CsPolicyPackage<li>Hinzugefügte Get-CsUserPolicyPackage<li>Hinzugefügte Get-CsUserPolicyPackageRecommendation<li>Hinzugefügte Grant-CsUserPolicyPackage<li>Hinzugefügte New-CsBatchPolicyPackageAssignmentOperation<li>Hinzugefügte Set-TeamArchivedState<li>Hinzugefügte Set-TeamPicture<li>Entfernte Get-TeamHelp</li>  |
| März 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Hinzugefügte New-CsBatchPolicyAssignmentOperation</li> |
| Februar 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team Optimierungen</li>  |

### <a name="cmdlet-availability"></a>Verfügbarkeit von Cmdlet

> [!NOTE]
> Die Liste in der nachstehenden Tabelle enthält nur Cmdlets, die nativ Teil des Teams PowerShell-Moduls sind. Die Teams-Cmdlets im Modul "S[kype for Business Online Connector"](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) werden nicht angezeigt. Da diese Cmdlets jedoch nativ in Teams PowerShell migriert werden, fügen wir sie dieser Tabelle hinzu.

| Cmdlet | Verfügbar in der öffentlichen Vorschau | Verfügbar in GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Ja | **Nein** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Ja | Ja |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Ja | **Nein**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Ja | Ja |
| [Disconnect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Ja | Ja |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Ja | Ja |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | Ja | **Nein** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | Ja | Ja |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Ja | Ja |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Ja | Ja |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Ja | Ja |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Ja | Ja |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Ja | Ja |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | Ja | Ja|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Ja | **Nein** |
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | Ja | Ja |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | Ja | Ja |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Ja | **Nein** |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Ja | Ja |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Ja | Ja |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Ja | Ja |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Ja | Ja |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | Ja | Ja |
| [New-Team](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Ja | Ja |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | Ja | Ja |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Ja | Ja |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Ja | Ja |
| [Remove-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Ja | Ja |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Ja | Ja |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Ja | **Nein** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Ja | Ja |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Ja | **Nein** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | Ja | **Nein**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Ja | Ja |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Ja | **Nein** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Ja | Ja |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Ja | Ja |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Ja | Ja |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Ja | Ja |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Ja | Ja |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Ja | **Nein** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Ja | **Nein** |

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams-Cmdletreferenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdletreferenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
