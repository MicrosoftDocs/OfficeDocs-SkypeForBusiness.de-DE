---
title: Microsoft Teams PowerShell-Anmerkungen zu dieser Version
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
description: Informieren Sie sich über die neuesten Änderungen in der PowerShell von Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41aa6cdf05901756bb2bcd13dbb8b9ad2cedabf6
ms.sourcegitcommit: a6c7a0cdbedf6cf32213d7636da52db71b4bac3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48937744"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell-Anmerkungen zu dieser Version

Auf dieser Seite finden Sie das aktuelle PowerShell-Änderungsprotokoll von Teams für die allgemeine Verfügbarkeit und öffentliche Preview-Versionen.

## <a name="release-notes"></a>Anmerkungen zu dieser Version

> [!NOTE]
> **-Preview** in der Spalte "Version" steht für Updates für Teams PowerShell Public Preview.

| Datum | Version | Updates |
|------- | -------------------- | ------------------------------ |
| November 2020 | [1.1.7 – Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Verwendet MSAL für die Authentifizierung & Autorisierung</li><li>Cmdlets für Umgestaltungs Richtlinien Pakete und Hinzufügen einer Gruppen Paket Zuweisung</li><li>Upload-Befehle für Umgestaltungs-Targeting-Hierarchie zum Verwenden eines asynchronen Modells</li> <li>Der Benutzer wird während der anfänglichen Authentifizierung zweimal aufgefordert, wenn er den Parameter-Credential nicht verwendet. Benutzer können Anmeldeinformationen mit dem Parameter-Credential übergeben, um eine doppelte Aufforderung zu vermeiden. Dieses Verhalten wird in der nächsten Version behoben.</li> |
| September 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Integration von Skype for Business Online Connector</li> |
| September 2020 | [1.1.5 – Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integration von Skype for Business Online Connector</li> |
| Juli 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>[Cmdlets für Gruppenrichtlinien Zuweisung](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group) hinzugefügt</li> |
| Juni 2020 | [1.1.3 – Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integration von Skype for Business Online Connector<li>Get-Team Optimierungen<li>Erhöhte Zuverlässigkeit</li> |
| Juni 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Hinzugefügtes Cmdlet-Vorabladen<li>.NET Framework-Optimierungen</li>   |
| April 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode-und Assembly-Signierung<li>Get-CsPolicyPackage hinzugefügt<li>Get-CsUserPolicyPackage hinzugefügt<li>Get-CsUserPolicyPackageRecommendation hinzugefügt<li>Grant-CsUserPolicyPackage hinzugefügt<li>New-CsBatchPolicyPackageAssignmentOperation hinzugefügt<li>Set-TeamArchivedState hinzugefügt<li>Set-TeamPicture hinzugefügt<li>Get-TeamHelp entfernt</li>  |
| März 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>New-CsBatchPolicyAssignmentOperation hinzugefügt</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team Optimierungen</li>  |

### <a name="cmdlet-availability"></a>Verfügbarkeit des Cmdlets

> [!NOTE]
> Die Liste in der folgenden Tabelle enthält nur Cmdlets, die nativ Teil des Teams PowerShell-Moduls sind. Die Teams-Cmdlets im S[KYPE for Business Online-Connector-Modul](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) werden nicht angezeigt. Da diese Cmdlets jedoch nativ in Teams PowerShell migriert werden, werden wir Sie dieser Tabelle hinzufügen.

| Cmdlet | In der öffentlichen Vorschau verfügbar | Verfügbar in GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Ja | **Nein** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Ja | Ja |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Ja | **Nein**|
| [Connect-Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Ja | Ja |
| [Trennen-Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Ja | Ja |
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
| [Neu – CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Ja | Ja |
| [Neu – CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Ja | Ja |
| [Neu – CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Ja | Ja |
| [Neu – CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | Ja | Ja |
| [Neues Team](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Ja | Ja |
| [Neu – TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | Ja | Ja |
| [Neu – TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Ja | Ja |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Ja | Ja |
| [Remove-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Ja | Ja |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Ja | Ja |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Ja | **Nein** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Ja | Ja |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Ja | **Nein** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | Ja | **Nein**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Ja | Ja |
| [Satz-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Ja | **Nein** |
| [Team einrichten](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Ja | Ja |
| [Satz-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Ja | Ja |
| [Satz-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Ja | Ja |
| [Satz-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Ja | Ja |
| [Satz-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Ja | Ja |
| [Satz-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Ja | **Nein** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Ja | **Nein** |

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit PowerShell von Teams](teams-powershell-managing-teams.md)

[Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
