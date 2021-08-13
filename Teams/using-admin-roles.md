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
description: Hier erfahren Sie, wie Sie mithilfe der Administratorrollen Administratoren benennen, die unterschiedliche Zugriffsebenen zum Verwalten Ihrer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7032a27c5d6686d282d3b73f7d08edf0dac0d29a52c1e219cda908c412d42bd2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321057"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams

Mithilfe von Azure Active Directory (Azure AD) können Sie Administratoren festlegen, die unterschiedliche Zugriffsebenen für die Verwaltung von Microsoft Teams benötigen. Administratoren können den gesamten Workload von Teams verwalten oder delegierte Berechtigungen zur Behandlung von Problemen mit der Anrufqualität oder zum Verwalten der Telefoniebedürfnisse Ihrer Organisation besitzen.

## <a name="teams-roles-and-capabilities"></a>Rollen und Funktionen in Teams

Es stehen mehrere Teams Administratorrollen zur Verfügung: Teams-Administrator, Teams-Kommunikationsadministrator, Teams-Experte für Kommunikationsunterstützung, Teams-Kommunikationssupporttechniker und Teams Geräteadministrator. Sehen Sie sich die folgende Tabelle an, um zu verstehen, was jede Rolle ausführen kann und welche Tools der Administrator im Microsoft Teams Admin Center und in PowerShell verwenden kann.

Um dies nacheringen zu können, müssen Sie ein Administrator sein. Anweisungen zum Abrufen der Berechtigungen finden Sie in diesem Artikel.

<!-- add Global admin role? -->

| Rolle                                    | kann diese Aufgaben ausführen                                                           | kann auf die folgenden Tools zugreifen                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams-Administrator             | Verwalten Sie Teams Dienst, und verwalten und erstellen sie Microsoft 365 Gruppen.        | Alles im Microsoft Teams Admin Center und zugeordneten PowerShell-Steuerelementen, darunter:<ul><li> Verwalten Sie Besprechungen, einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenzbrücken. <sup>1.2</sup></li><li>Verwalten Sie Sprachanrufe, einschließlich Anrufrichtlinien und Inventar und Zuweisung von Telefonnummern. <sup>1;3</sup></li><li>Verwalten Sie Messaging, einschließlich Messagingrichtlinien. <sup>1.2</sup></li><li>Verwalten Sie alle organisationsweiten Einstellungen, einschließlich Verbund-, Teams-Upgrade- und Teams-Clienteinstellungen. <sup>1.2</sup></li><li>Verwalten Sie die Teams in der Organisation und deren zugehörige Einstellungen, einschließlich der Mitgliedschaft (Gruppenverwaltung, die über PowerShell unterstützt wird, Teamverwaltung im Teams Admin Center). <sup>1.2</sup></li><li>Verwalten Teams zertifizierten Geräten und Einrichten und Zuweisen von Konfigurationsrichtlinien. <sup>1</sup></li><li>Zeigen Sie die Benutzerprofilseite an, und behandeln Sie Probleme mit der Anrufqualität mit den erweiterten Problembehandlungstools. <sup>2</sup> </li><li>Zugreifen auf alle Berichte im Microsoft Teams Admin Center</li><li> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. Erstellen Sie neue Berichte zur Anrufqualität, aktualisieren und entfernen Sie Berichte zur Anrufqualität nach Bedarf. Hochladen und Aktualisieren von CQD-Gebäudedaten.</li><li> [Veröffentlichen von Apps im Mandanten-App-Katalog im Microsoft Teams Admin Center](manage-apps.md)</li></ul> |
| Teams-Kommunikationsadministrator      | Verwalten von Anruf- und Besprechungsfunktionen innerhalb des Microsoft Teams-Diensts.               | Verwalten Sie Besprechungen, einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenzbrücken. <sup>1.2</sup><br><br> Verwalten Sie Sprachanrufe, einschließlich Anrufrichtlinien und Inventar und Zuweisung von Telefonnummern. <sup>1;3</sup><br><br> Zeigen Sie die Benutzerprofilseite an, und behandeln Sie Probleme mit der Anrufqualität von Benutzern mit dem erweiterten Toolset für die Problembehandlung. <sup>2</sup> <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. Erstellen Sie neue Berichte zur Anrufqualität, aktualisieren und entfernen Sie Berichte zur Anrufqualität nach Bedarf. Hochladen und Aktualisieren von CQD-Gebäudedaten.|
| Supporttechniker für die Teams-Kommunikation   | Ausführen einer Problembehandlung von Kommunikationsproblemen innerhalb von Microsoft Teams unter Verwendung **erweiterter** Tools. | Zeigen Sie die Benutzerprofilseite an, und behandeln Sie Probleme mit der Anrufqualität mit den erweiterten Problembehandlungstools. <sup>2</sup> <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. |
| Supportfachmann für die Teams-Kommunikation | Ausführen einer Problembehandlung von Kommunikationsproblemen innerhalb von Microsoft Teams unter Verwendung **grundlegender** Tools.    | Zugreifen auf Benutzerprofilseiten, um mit der Anrufanalyse eine Problembehandlung von Anrufen durchzuführen. Kann nur Benutzerinformationen für den bestimmten gesuchten Benutzer anzeigen. <sup>2</sup> <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie darauf bezogene Probleme mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden. |
| Teams Geräteadministrator              | Verwalten Sie Geräte, die für die Verwendung mit dem Dienst Teams sind.                    | Verwalten Sie Gerätekonfiguration und -updates, überprüfen Sie den Gerätestatus und -status von verbundenen Peripheriegeräten, richten Sie Konfigurationsprofile ein, und wenden Sie diese an, und starten Sie Geräte neu.<p>Die Teams"Geräteadministrator" bietet keinen Zugriff auf Daten zur Anrufqualität oder Anrufanalyse. Um Daten zur Anrufqualität oder die Anrufanalyse anzeigen zu können, muss Ihnen die Rolle Teams Kommunikationsadministrator zugewiesen sein. |

<sup>1</sup> [PowerShell – Microsoft Teams-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/) (Die Public Release 1.1.6 oder höher ist in Skype for Business Online Connector integriert.)<br>
<sup>2</sup> [Microsoft Teams Admin Center](./manage-teams-skypeforbusiness-admin-center.md) 
 <sup>3</sup> Teams administrator account must have a valid Teams license.
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Weitere Informationen zu den Verwaltungstools, die zum Verwalten von Microsoft Teams verfügbar sind, erhalten Sie unter [Verwalten von Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md).

Weitere Informationen zu Beschränkungen, Spezifikationen und anderen Anforderungen, die für Teams gelten, finden Sie unter [Beschränkungen und Spezifikationen für Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Zuweisen von Benutzern zu Rollen

Sie können diesen Rollen in Azure AD Benutzer zuweisen. Um zu erfahren, wie in Azure AD einem Benutzer Administratorrollen zugewiesen werden, lesen Sie [Zuweisen von Administratorrollen zu einem Benutzer in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Für jede Rolle verfügbare Cmdlets

Die meisten PowerShell-Tools für diese Administratorrollen befinden sich im Teams PowerShell-Modul, und es ist wichtig zu beachten, dass einige cmdlets, auf die diese Administratorrollen zugreifen können, um freigegebene Einstellungen zu steuern, die auch für Skype for Business Online verwendet werden. 

So zeigen Sie die vollständige Liste der Cmdlets an:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [PowerShell für Microsoft Teams](/powershell/module/teams/?view=teams-ps)
- [Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](./assign-roles-permissions.md)
