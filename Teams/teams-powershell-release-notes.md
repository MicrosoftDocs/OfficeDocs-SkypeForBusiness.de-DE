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
ms.openlocfilehash: e3fbffcf36e05aab945833bcf6a09e097d6c0c39
ms.sourcegitcommit: 2e1d97a3181fe12be43a0641039dca6077863f44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2021
ms.locfileid: "58380449"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell-Versionshinweise

Diese Seite enthält das neueste Teams PowerShell-Änderungsprotokoll für allgemeine Verfügbarkeit und public Preview-Versionen.

## <a name="release-notes"></a>Anmerkungen zu dieser Version

> [!NOTE]
> **-preview** in der folgenden Versionsspalte stellt Updates für Teams PowerShell dar.

| Datum | Version | Updates |
|------- | -------------------- | ------------------------------ |
| August 2021 | [2.5.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.0) |<li>Updates für die AccessToken-Anmeldung mit Verbinden-MicrosoftTeams.</li><li>Korrekturen für die interaktive Anmeldung von Connect-MicrosoftTeams in Cloudshell.</li><li>Verbesserungen am New-Team-Cmdlets für Teamerstellungsszenarien.</li><li>TeamsUnassignedNumberTreatment-Cmdlets sind jetzt verfügbar.</li><li>Get-CsCsOnlineDialInConferencingBridge und Set-CsOnlineDialInConferencingBridge.</li><li>Gibt modernisierte Versionen von Get-CsTenant Get-CsOnlineUser (nur mit dem Parameter -identity) frei.</li>|
| Juli 2021 | [2.4.1-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>Gewähren Sie jetzt cmdlets Änderungen.</li><li>Neue Voice-bezogene Cmdlets werden veröffentlicht.</li><li>Entfernen der Authentifizierung mit Fingerabdrück für -Cs*-Cmdlets</li><li>Protokollierungskorrektur zum Protokollieren von Dateien aller Cmdlets.</li><li>Behebt Probleme mit *TeamChannelUser-Cmdlets.</li>|
| Juni 2021 | [2.4.0-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>Nur Vorschauversion von modernisierten Versionen von Get-CsTenant, Get-CsOnlineUser (nur mit dem Parameter -identity), Get-CsOnlineDialInConferencingLanguagesSupported und Import-CsOnlineAudioFile.</li><li>Bei modernen Versionen von Get-CsOnlineDialInConferencingLanguagesSupported und Import-CsOnlineAudioFile wird erwartet, dass sie ihren Remoting-Gegenstücken ähnlich bzw. gleich funktionieren.</li><li>Moderne Versionen von Get-CsTenant und Get-CsOnlineUser (bei der Ausführung mit dem Parameter -identity) geben keine veralteten Eigenschaften aus.</li><li>Moderne Versionen von Get-CsTenant und Get-CsOnlineUser (bei Der Ausführung mit dem Parameter -identity) haben im Vergleich zu den Remoting counter-Teilen einige Formatierungsänderungen.</li><li>Releases [Set \| \| Grant New \| \| Remove]-CsTeamsAudioConferencingPolicy-Cmdlets.</li><li>Gibt Get-CsOnlineAudioFile- und Remove-CsOnlineAudioFile-Cmdlets frei.</li><li>Set-TeamTargetingHierarchy, Remove-TeamTargetingHierarchy, Get-TeamTargetingHierarchyStatus sind jetzt für GCC verfügbar.</li><li>Behebt den Endpunkt, der vom Befehl Get-TeamTargetingHierarchyStatus wird.</li>|
| Mai 2021 | [2.3.2-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>Unterstützung für die AccessToken-Anmeldung mit Verbinden-MicrosoftTeams. -AccessTokens-Parameter wurde hinzugefügt, der das Array des Tokens akzeptiert. MSGraph und Teams Ressourcentoken sind erforderlich, wenn sie den Parameter AccessTokens verwenden.</li><li>Die Parameter "AadAccessToken" und "MsAccessToken" wurden entfernt.</li>|
| Mai 2021 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>Aktualisieren Sie von . NETCore 2.1 bis 3.1</li><li>Cmdlet zum Erhalten einer Multi-Geo-Region für Benutzer und Gruppen hinzugefügt</li><li>Korrekturen für die integrierte Windows-Authentifizierung zur Verwendung von -AccountId Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy-Cmdlets sind jetzt verfügbar.</li><li>Aktualisierungen von Eingabeparametern und Ausgabeformaten vieler Befehle</li><li>Behebt ein Problem mit großer Latenz beim Remoteen von Befehlen</li><li>Benutzerdefinierte GA-Paketfeatures</li>|
| April 2021 | [2.2.0-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Korrekturen für die integrierte Windows zur Verwendung von -AccountId mit Verbinden-MicrosoftTeams.</li><li>Cmdlet hinzugefügt, um Details zu den Benachrichtigungsereignissen für Gesamtänderung anzuzeigen, die an Benutzer gesendet werden können.</li><li>Cmdlet zum Erhalten einer Multi-Geo-Region für Benutzer und Gruppen hinzugefügt.</li><li>Bei der Behandlung von Werten, die an den TeamsEnvironment-Namen übergeben wurden, muss die Zwischen- und Kleinschreibung beachtet werden. Dieses Problem wurde behoben.</li><li>Wichtige Umgestaltung der Remotesitzungsverwaltung innerhalb des Moduls, um Komponententests zu vereinfachen. Für Mandantenadministratoren sollte es keine Funktionsänderung mehr gibt.</li>|
| April 2021 | [2.1.0-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Die Ausgabeformatierung einiger Remoting-Cmdlets (z. B. Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy und mehr) wurde korrigiert.</li><li>Aktualisierte Parameterliste der Richtlinienverwaltungs-Cmdlets.</li>|
| März 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Verwendet MSAL für die Authentifizierungs- & Autorisierung</li> <li>Connect-MicrosoftTeams ist der Einstiegspunkt für alle Cmdlets.</li><li>New-csOnlineSession ist nicht mehr verfügbar. Es wurde durch Verbinden-MicrosoftTeams ersetzt.</li><li>Enable-csonlinesessionforreconnection ist nicht mehr erforderlich. Das Feature wurde nativ in Teams PowerShell-Modul implementiert.</li> <li>Umgestaltet Richtlinienpaket-Cmdlets und Fügt Gruppenpaketzuordnung hinzu</li><li>Erhebliche Leistungsverbesserungen für Get-Team-Cmdlet</li> <li>Verbesserte Protokollierungs- und Debugoption für vorhandene Cmdlets </li> <li>Hinzugefügte Vorlagenverwaltungs-Cmdlets</li> <li>Veraltete New-CsOnlineSession</li>|
| Februar 2021 | [1.1.11-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Hinzugefügte Vorlagenverwaltungs-Cmdlets</li><li>Mezzo- und Batchverarbeitungsverbesserungen für Get-Team-Cmdlet</li> <li>Verbesserte Protokollierungs- und Debugoption für vorhandene Cmdlets </li> <li>Umgestaltet Richtlinienpaket-Cmdlets</li>|
| Dezember 2020 | [1.1.10-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Updates für das Cmdlet "Neues Team" mit erhöhten Wiederholungen und der Dauer des Ruhezustands</li>|
| Dezember 2020 | [1.1.9-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Updates für Skype for Business Onlineintegration</li><li>Fix für die Duplizieraufforderung mit Connect-Microsoft Teams</li>|
| November 2020 | [1.1.8-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Fügt cmdlets für benutzerdefinierte Richtlinienpakete hinzu.</li><li>Korrekturen für die Uploadbefehle der Zielhierarchie</li>|
| November 2020 | [1.1.7-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Verwendet MSAL für die Authentifizierungs- & Autorisierung</li><li>Umgestaltet Richtlinienpaket-Cmdlets und Fügt Gruppenpaketzuordnung hinzu</li><li>Umgestalten der Zielhierarchie-Uploadbefehle für die Verwendung eines asynchronen Modells</li> <li>Der Benutzer wird während der anfänglichen Authentifizierung zweimal aufgefordert, wenn er den Parameter -credential nicht verwendet. Benutzer können Anmeldeinformationen mithilfe des Parameters -credential übergeben, um doppelte Eingabeaufforderungen zu vermeiden. Dieses Verhalten wird in der nächsten Version behoben.</li> |
| September 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online Connector-Integration</li> |
| September 2020 | [1.1.5-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online Connector-Integration</li> |
| Juli 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Hinzugefügte [Gruppenrichtlinienzuordnungs-Cmdlets](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Juni 2020 | [1.1.3-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online Connector-Integration<li>Get-Team Optimierungen<li>Höhere Zuverlässigkeit</li> |
| Juni 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Vorabladen des Cmdlets hinzugefügt<li>.Net Framework-Optimierungen</li>   |
| April 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode- und Assemblysignatursignatur<li>Hinzugefügte Get-CsPolicyPackage<li>Hinzugefügte Get-CsUserPolicyPackage<li>Hinzugefügte Get-CsUserPolicyPackageRecommendation<li>Hinzugefügte Grant-CsUserPolicyPackage<li>Hinzugefügte New-CsBatchPolicyPackageAssignmentOperation<li>Hinzugefügte Set-TeamArchivedState<li>Hinzugefügte Set-TeamPicture<li>Entfernte Get-TeamHelp</li>  |
| März 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Hinzugefügte New-CsBatchPolicyAssignmentOperation</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team Optimierungen</li>  |

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Installieren Teams PowerShell](teams-powershell-install.md)

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)
