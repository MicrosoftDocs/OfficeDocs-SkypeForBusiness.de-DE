---
title: Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: Erfahren Sie, wie Sie mithilfe der Administratorrollen Administratoren benennen, die unterschiedliche Zugriffsebenen zum Verwalten von Teams benötigen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11f771f355b3be7c34dd3715d760c6968bb1f7ea
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874635"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams

Mithilfe von Azure Active Directory (Azure AD) können Sie Administratoren festlegen, die unterschiedliche Zugriffsebenen für die Verwaltung von Microsoft Teams benötigen. Administratoren können den gesamten Workload von Teams verwalten oder delegierte Berechtigungen zur Behandlung von Problemen mit der Anrufqualität oder zum Verwalten der Telefoniebedürfnisse Ihrer Organisation besitzen.

## <a name="teams-roles-and-capabilities"></a>Rollen und Funktionen in Teams

Es stehen mehrere Teams-Administratorrollen zur Verfügung: Teams Service Administrator, Teams Communications Administrator, Teams Communications Support Specialist, Teams Communications Support Engineer und Teams Device Administrator. Sehen Sie sich die folgende Tabelle an, um zu verstehen, was jede Rolle ausführen kann und welche Tools der Administrator im Microsoft Teams Admin Center und in PowerShell verwenden kann.

Damit Sie folgen können, müssen Sie ein Administrator sein. Die Anweisungen zum Abrufen der Berechtigungen finden Sie in diesem Artikel.

<!-- add Global admin role? -->

| Rolle                                    | kann diese Aufgaben ausführen                                                           | kann auf die folgenden Tools zugreifen                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams-Dienstadministrator             | Verwalten Sie den Teams-Dienst, und verwalten und erstellen Sie Microsoft 365-Gruppen.        | Alles im Microsoft Teams Admin Center und zugeordneten PowerShell-Steuerelementen, darunter:<ul><li> Verwalten sie Besprechungen, einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenzbrücken. <sup>1,2</sup></li><li>Verwalten der VoIP-Funktionen einschließlich Anrufrichtlinien, Telefonnummernbestand und -zuweisung.<sup>1</sup></li><li>Verwalten von Nachrichten, einschließlich Messagingrichtlinien. <sup>1,2</sup></li><li>Verwalten Sie alle organisationsweiten Einstellungen, einschließlich Verbund-, Teams-Upgrade- und Teams-Clienteinstellungen. <sup>1,2</sup></li><li>Verwalten Sie die Teams in der Organisation und deren zugehörige Einstellungen, einschließlich der Mitgliedschaft (Gruppenverwaltung, die über PowerShell unterstützt wird, Teamverwaltung im Teams Admin Center). <sup>1,2</sup></li><li>Verwalten Sie von Teams zertifizierte Geräte, und richten Sie Konfigurationsrichtlinien ein und weisen Sie sie zu. <sup>1</sup></li><li>Zeigen Sie die Seite "Benutzerprofil" an, und behandeln Sie Probleme mit der Anrufqualität von Benutzern mit dem toolset für die erweiterte Problembehandlung. <sup>2</sup> </li><li>Zugriff auf alle Berichte im Microsoft Teams Admin Center</li><li> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. Erstellen Sie neue Anrufqualitätsberichte, aktualisieren und entfernen Sie Anrufqualitätsberichte nach Bedarf. Hochladen und Aktualisieren von CQD-Gebäudedaten.</li><li> [Veröffentlichen von Apps im Katalog der Mandanten-App im Microsoft Teams Admin Center](manage-apps.md)</li></ul> |
| Teams-Kommunikationsadministrator      | Verwalten von Anruf- und Besprechungsfunktionen innerhalb des Microsoft Teams-Diensts.               | Verwalten sie Besprechungen, einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenzbrücken. <sup>1,2</sup><br><br> Verwalten der VoIP-Funktionen einschließlich Anrufrichtlinien, Telefonnummernbestand und -zuweisung.<sup>1</sup><br><br> Zeigen Sie die Seite "Benutzerprofil" an, und behandeln Sie Probleme mit der Anrufqualität mit dem toolset für die erweiterte Problembehandlung. <sup>2</sup> <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. Erstellen Sie neue Anrufqualitätsberichte, aktualisieren und entfernen Sie Anrufqualitätsberichte nach Bedarf. Hochladen und Aktualisieren von CQD-Gebäudedaten.|
| Supporttechniker für die Teams-Kommunikation   | Ausführen einer Problembehandlung von Kommunikationsproblemen innerhalb von Microsoft Teams unter Verwendung **erweiterter** Tools. | Zeigen Sie die Seite "Benutzerprofil" an, und behandeln Sie Probleme mit der Anrufqualität von Benutzern mit dem toolset für die erweiterte Problembehandlung. <sup>2</sup> <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. |
| Supportfachmann für die Teams-Kommunikation | Ausführen einer Problembehandlung von Kommunikationsproblemen innerhalb von Microsoft Teams unter Verwendung **grundlegender** Tools.    | Zugreifen auf Benutzerprofilseiten, um mit der Anrufanalyse eine Problembehandlung von Anrufen durchzuführen. Kann nur Benutzerinformationen für den bestimmten Benutzer anzeigen, nach dem gesucht wird. <sup>2</sup> <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie darauf bezogene Probleme mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden. |
| Teamgeräteadministrator              | Verwalten Sie Geräte, die für die Verwendung mit dem Teams-Dienst konfiguriert sind.                    | Verwalten der Gerätekonfiguration und -updates, Überprüfen des Gerätestatus und -status verbundener Peripheriegeräte, Einrichten und Anwenden von Konfigurationsprofilen und Neustarten von Geräten.<p>Die Rolle des Teams-Geräteadministrators bietet keinen Zugriff auf Anrufqualitätsdaten oder Anrufanalysen. Um Daten zur Anrufqualität oder Anrufanalyse anzeigen zu können, muss Ihnen die Rolle des Teams Communications Administrators zugewiesen werden. |

<sup>1</sup> [PowerShell – Microsoft Teams-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/) (Die öffentliche Version 1.1.6 oder höher ist in Skype for Business Online Connector integriert.)<br>
<sup>2</sup> [Microsoft Teams Admin Center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Weitere Informationen zu den Verwaltungstools, die zum Verwalten von Microsoft Teams verfügbar sind, erhalten Sie unter [Verwalten von Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Weitere Informationen zu Beschränkungen, Spezifikationen und anderen Anforderungen, die für Teams gelten, finden Sie unter [Beschränkungen und Spezifikationen für Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Zuweisen von Benutzern zu Rollen

Sie können diesen Rollen in Azure AD Benutzer zuweisen. Um zu erfahren, wie in Azure AD einem Benutzer Administratorrollen zugewiesen werden, lesen Sie [Zuweisen von Administratorrollen zu einem Benutzer in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Für jede Rolle verfügbare Cmdlets

Die meisten PowerShell-Tools für diese Administratorrollen befinden sich im Teams PowerShell-Modul, und es ist wichtig zu beachten, dass einige der Cmdlets, auf die diese Administratorrollen Zugriff haben, freigegebene Einstellungen steuern können, die auch für Skype for Business Online verwendet werden. 

So zeigen Sie die vollständige Liste der Cmdlets an:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [PowerShell für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)
