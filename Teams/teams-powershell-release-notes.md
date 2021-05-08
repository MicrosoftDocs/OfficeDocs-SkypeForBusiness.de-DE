---
title: Microsoft Teams PowerShell-Versionshinweise
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
ms.openlocfilehash: 382d11ba8a2a388b70df5675275f21faae5db37c
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130304"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell-Versionshinweise

Diese Seite enthält das neueste Teams PowerShell-Änderungsprotokoll für allgemeine Verfügbarkeit und öffentliche Preview-Versionen.

## <a name="release-notes"></a>Anmerkungen zu dieser Version

> [!NOTE]
> **-preview** in der folgenden Versionsspalte stellt Updates für Teams PowerShell dar.

| Datum | Version | Updates |
|------- | -------------------- | ------------------------------ |
| April 2021 | [2.3.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.0) | <li>Cmdlet zum Erhalten einer Multi-Geo-Region für Benutzer und Gruppen hinzugefügt</li><li>Korrekturen für die integrierte Windows-Authentifizierung zur Verwendung von -AccountId Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy-Cmdlets sind jetzt verfügbar.</li><li>Aktualisierungen von Eingabeparametern und Ausgabeformaten vieler Befehle</li><li>Behebt ein Problem mit großer Latenz beim Remoteen von Befehlen</li><li>Benutzerdefinierte GA-Paketfeatures</li>|
| April 2021 | [2.2.0-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Korrekturen für die integrierte Windows zur Verwendung von -AccountId Verbinden-MicrosoftTeams.</li><li>Cmdlet hinzugefügt, um Details zu den Benachrichtigungsereignissen für Gesamtänderung anzuzeigen, die an Benutzer gesendet werden können.</li><li>Hinzugefügtes Cmdlet zum Erhalten von Multi-Geo-Regionen für Benutzer und Gruppen.</li><li>Bei der Behandlung von Werten, die an den TeamsEnvironment-Namen übergeben wurden, muss die Zwischen- und Kleinschreibung beachtet werden. Dieses Problem wurde behoben.</li><li>Wichtige Umgestaltung der Remotesitzungsverwaltung innerhalb des Moduls, um Komponententests zu vereinfachen. Für Mandantenadministratoren sollte es keine Funktionsänderung mehr gibt.</li>|
| April 2021 | [2.1.0-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Feste Formatierung von vorhandenen Cmdlets (z. B. Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy und mehr).</li><li>Aktualisierte Parameterliste der Richtlinienverwaltungs-Cmdlets.</li>|
| März 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Verwendet MSAL für die Authentifizierungs- & Autorisierung</li> <li>Connect-MicrosoftTeams ist der Einstiegspunkt für alle Cmdlets.</li><li>New-csOnlineSession ist nicht mehr verfügbar. Es wurde durch Verbinden-MicrosoftTeams ersetzt.</li><li>Enable-csonlinesessionforreconnection ist nicht mehr erforderlich. Das Feature wurde nativ in Teams PowerShell-Modul implementiert.</li> <li>Umgestaltet Richtlinienpaket-Cmdlets und Fügt Gruppenpaketzuordnung hinzu</li><li>Erhebliche Leistungsverbesserungen für Get-Team-Cmdlet</li> <li>Verbesserte Protokollierungs- und Debugoption für vorhandene Cmdlets </li> <li>Hinzugefügte Vorlagenverwaltungs-Cmdlets</li> <li>Veraltete New-CsOnlineSession</li>|
| Februar 2021 | [1.1.11-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Hinzugefügte Vorlagenverwaltungs-Cmdlets</li><li>Mezzo- und Batchverarbeitungsverbesserungen für Get-Team-Cmdlet</li> <li>Verbesserte Protokollierungs- und Debugoption für vorhandene Cmdlets </li> <li>Umgestaltet Richtlinienpaket-Cmdlets</li>|
| Dezember 2020 | [1.1.10-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Updates für das Cmdlet "Neues Team" mit erhöhten Wiederholungen und der Dauer des Ruhezustands</li>|
| Dezember 2020 | [1.1.9-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Updates für Skype for Business Onlineintegration</li><li>Fix für die Duplizieraufforderung mit Connect-Microsoft Teams</li>|
| November 2020 | [1.1.8-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Fügt cmdlets für benutzerdefinierte Richtlinienpakete hinzu.</li><li>Korrekturen für die Uploadbefehle der Zielhierarchie</li>|
| November 2020 | [1.1.7-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Verwendet MSAL für die Authentifizierungs- & Autorisierung</li><li>Umgestaltet Richtlinienpaket-Cmdlets und Fügt Gruppenpaketzuordnung hinzu</li><li>Umgestalten der Zielhierarchie-Uploadbefehle für die Verwendung eines asynchronen Modells</li> <li>Der Benutzer wird während der anfänglichen Authentifizierung zweimal aufgefordert, wenn er den Parameter -credential nicht verwendet. Benutzer können Anmeldeinformationen mithilfe des Parameters -credential übergeben, um doppelte Eingabeaufforderungen zu vermeiden. Dieses Verhalten wird in der nächsten Version behoben.</li> |
| September 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online Connector-Integration</li> |
| September 2020 | [1.1.5-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online Connector-Integration</li> |
| Juli 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Hinzugefügte [Gruppenrichtlinienzuordnungs-Cmdlets](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Juni 2020 | [1.1.3-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online Connector-Integration<li>Get-Team von Optimierungen<li>Höhere Zuverlässigkeit</li> |
| Juni 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Vorabladen des Cmdlets hinzugefügt<li>.Net Framework-Optimierungen</li>   |
| April 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode- und Assemblysignatursignatur<li>Hinzugefügter Get-CsPolicyPackage<li>Hinzugefügter Get-CsUserPolicyPackage<li>Hinzugefügter Get-CsUserPolicyPackageRecommendation<li>Hinzugefügter Grant-CsUserPolicyPackage<li>Hinzugefügter New-CsBatchPolicyPackageAssignmentOperation<li>Hinzugefügter Set-TeamArchivedState<li>Hinzugefügter Set-TeamPicture<li>Entfernte Get-TeamHelp</li>  |
| März 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Hinzugefügter New-CsBatchPolicyAssignmentOperation</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team von Optimierungen</li>  |

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Installieren Teams PowerShell](teams-powershell-install.md)

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)
