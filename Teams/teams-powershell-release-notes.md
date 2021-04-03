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
ms.openlocfilehash: 80e6225302cb733c37ba1720d95d8d8f1a220831
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506691"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Versionshinweise zu Microsoft Teams PowerShell

Diese Seite enthält das neueste Änderungsprotokoll von Teams PowerShell sowohl für allgemeine Verfügbarkeit als auch für Public Preview-Versionen.

## <a name="release-notes"></a>Versionshinweise

> [!NOTE]
> **-preview** in der folgenden Versionsspalte stellt Updates für die öffentliche Vorschau von Teams PowerShell dar.

| Datum | Version | Updates |
|------- | -------------------- | ------------------------------ |
| April 2021 | [2.1.0-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Die Formatierung vorhandener Cmdlets wurde behoben (z. B. Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy und vieles mehr).</li><li>Aktualisierte Parameterliste der Richtlinienverwaltungs-Cmdlets.</li>|
| März 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Verwendet MSAL für die Authentifizierung & Autorisierung</li> <li>Connect-MicrosoftTeams ist der Einstiegspunkt für alle Cmdlets.</li><li>New-csOnlineSession ist nicht mehr verfügbar. Es wurde durch Connect-MicrosoftTeams ersetzt.</li><li>Enable-csonlinesessionforreconnection ist nicht mehr erforderlich. Das Feature wurde nativ im Teams PowerShell-Modul implementiert.</li> <li>Umgestalten von Richtlinienpaket-Cmdlets und Addierung von Gruppenpaketzuordnungen</li><li>Erhebliche Leistungsverbesserungen für Get-Team Cmdlet</li> <li>Verbesserte Protokollierungs- und Debuggingoption für vorhandene Cmdlets </li> <li>Hinzugefügte Vorlagenverwaltungs-Cmdlets</li> <li>Veraltete New-CsOnlineSession</li>|
| Februar 2021 | [1.1.11-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Hinzugefügte Vorlagenverwaltungs-Cmdlets</li><li>Verbesserungen von Mezzo und Batching für Get-Team Cmdlet</li> <li>Verbesserte Protokollierungs- und Debuggingoption für vorhandene Cmdlets </li> <li>Umgestalten von Richtlinienpaket-Cmdlets</li>|
| Dezember 2020 | [1.1.10-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Updates für das Cmdlet "Neues Team" mit erhöhten Wiederholungen und einer erhöhten Schlafdauer</li>|
| Dezember 2020 | [1.1.9-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Updates für die Skype for Business Online-Integration</li><li>Beheben der doppelten Eingabeaufforderung mit Connect-Microsoft Teams</li>|
| November 2020 | [1.1.8-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Fügt benutzerdefinierte Richtlinienpaket-Cmdlets hinzu</li><li>Korrekturen für die Uploadbefehle für die Zielhierarchie</li>|
| November 2020 | [1.1.7-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Verwendet MSAL für die Authentifizierung & Autorisierung</li><li>Umgestalten von Richtlinienpaket-Cmdlets und Addierung von Gruppenpaketzuordnungen</li><li>Umgestaltende Uploadbefehle für die Zielhierarchie für die Verwendung eines asynchronen Modells</li> <li>Der Benutzer wird während der anfänglichen Authentifizierung zweimal aufgefordert, wenn er den Parameter -credential nicht verwendet. Benutzer können Anmeldeinformationen über den Parameter -credential übergeben, um eine doppelte Eingabeaufforderung zu vermeiden. Dieses Verhalten wird in der nächsten Version behoben.</li> |
| September 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online Connector-Integration</li> |
| September 2020 | [1.1.5-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online Connector-Integration</li> |
| Juli 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Hinzugefügte [Gruppenrichtlinienzuordnungs-Cmdlets](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Juni 2020 | [1.1.3-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online Connector-Integration<li>Get-Team Optimierungen<li>Verbesserte Zuverlässigkeit</li> |
| Juni 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Vorladen des Cmdlets hinzugefügt<li>.Net Framework-Optimierungen</li>   |
| April 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Signieren von Authenticode und Assembly<li>Hinzugefügte Get-CsPolicyPackage<li>Hinzugefügte Get-CsUserPolicyPackage<li>Hinzugefügte Get-CsUserPolicyPackageRecommendation<li>Hinzugefügte Grant-CsUserPolicyPackage<li>Hinzugefügte New-CsBatchPolicyPackageAssignmentOperation<li>Hinzugefügte Set-TeamArchivedState<li>Hinzugefügte Set-TeamPicture<li>Entfernte Get-TeamHelp</li>  |
| März 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Hinzugefügte New-CsBatchPolicyAssignmentOperation</li> |
| Februar 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team Optimierungen</li>  |

### <a name="cmdlet-availability"></a>Verfügbarkeit von Cmdlet

> [!NOTE]
> Die Liste in der nachstehenden Tabelle enthält nur Cmdlets, die nativ Teil des Teams PowerShell-Moduls sind. Die Teams-Cmdlets im Modul "S[kype for Business Online Connector"](/powershell/skype/intro?view=skype-ps) werden nicht angezeigt. Da diese Cmdlets jedoch nativ in Teams PowerShell migriert werden, fügen wir sie dieser Tabelle hinzu.

| Cmdlet | Verfügbar in der öffentlichen Vorschau | Verfügbar in GA |
| -| -- | --|
| [Add-TeamChannelUser](/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Ja | **Nein** |
| [Add-TeamUser](/powershell/module/teams/add-teamuser?view=teams-ps) | Ja | Ja |
| [Add-TeamsAppInstallation](/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Ja | **Nein**|
| [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Ja | Ja |
| [Disconnect-MicrosoftTeams](/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Ja | Ja |
| [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Ja | Ja |
| [Get-CsGroupPolicyAssignmentOperation](/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | Ja | **Nein** |
| [Get-CsOnlinePowerShellEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | Ja | Ja |
| [Get-CsPolicyPackage](/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Ja | Ja |
| [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Ja | Ja |
| [Get-CsUserPolicyPackage](/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Ja | Ja |
| [Get-CsUserPolicyPackageRecommendation](/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Ja | Ja |
| [Get-Team](/powershell/module/teams/get-team?view=teams-ps) | Ja | Ja |
| [Get-TeamChannel](/powershell/module/teams/get-teamchannel?view=teams-ps) | Ja | Ja|
| [Get-TeamChannelUser](/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Ja | **Nein** |
| [Get-TeamUser](/powershell/module/teams/get-teamuser?view=teams-ps) | Ja | Ja |
| [Get-TeamsApp](/powershell/module/teams/get-teamsapp?view=teams-ps) | Ja | Ja |
| [Get-TeamsAppInstallation](/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Ja | **Nein** |
| [Grant-CsUserPolicyPackage](/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Ja | Ja |
| [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Ja | Ja |
| [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Ja | Ja |
| [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Ja | Ja |
| [New-CsOnlineSession](/powershell/module/skype/new-csonlinesession?view=skype-ps) | Ja | Ja |
| [New-Team](/powershell/module/teams/new-team?view=teams-ps) | Ja | Ja |
| [New-TeamChannel](/powershell/module/teams/new-teamchannel?view=teams-ps) | Ja | Ja |
| [New-TeamsApp](/powershell/module/teams/new-teamsapp?view=teams-ps) | Ja | Ja |
| [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Ja | Ja |
| [Remove-Team](/powershell/module/teams/remove-team?view=teams-ps) | Ja | Ja |
| [Remove-TeamChannel](/powershell/module/teams/remove-teamchannel?view=teams-ps) | Ja | Ja |
| [Remove-TeamChannelUser](/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Ja | **Nein** |
| [Remove-TeamsApp](/powershell/module/teams/remove-teamsapp?view=teams-ps) | Ja | Ja |
| [Remove-TeamsAppInstallation](/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Ja | **Nein** |
| [Remove-TeamTargetingHierarchy](./set-up-your-team-hierarchy.md#remove-your-hierarchy) | Ja | **Nein**|
| [Remove-TeamUser](/powershell/module/teams/remove-teamuser?view=teams-ps) | Ja | Ja |
| [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Ja | **Nein** |
| [Set-Team](/powershell/module/teams/set-team?view=teams-ps) | Ja | Ja |
| [Set-TeamArchivedState](/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Ja | Ja |
| [Set-TeamChannel](/powershell/module/teams/set-teamchannel?view=teams-ps) | Ja | Ja |
| [Set-TeamPicture](/powershell/module/teams/set-teampicture?view=teams-ps) | Ja | Ja |
| [Set-TeamsApp](/powershell/module/teams/set-teamapp?view=teams-ps) | Ja | Ja |
| [Set-TeamTargetingHierarchy](/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Ja | **Nein** |
| [Update-TeamsAppInstallation](/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Ja | **Nein** |
| [Enable-CsOnlineSessionForReconnection](/skypeforbusiness/set-up-your-computer-for-windows-powershell/diagnose-problems-with-the-skype-for-business-online-connector) | **Nein** | **Nein** |


## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams-Cmdletreferenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdletreferenz](/powershell/skype/intro?view=skype-ps)
