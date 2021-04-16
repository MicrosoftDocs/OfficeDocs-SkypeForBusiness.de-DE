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
ms.openlocfilehash: 9687dcdca15507caad0c52ef13feb2c12fb61e9a
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768338"
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

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams-Cmdletreferenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdletreferenz](/powershell/skype/intro?view=skype-ps)
