---
title: Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
description: Erfahren Sie, wie Sie die Administratorrollen zum Festlegen von Administratoren verwenden, die unterschiedliche Zugriffsebenen zum Verwalten von Teams benötigen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e044a806136330e630eb7f5336a9480f9ebd435
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229041"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams

Mithilfe von Azure Active Directory (Azure AD) können Sie Administratoren festlegen, die unterschiedliche Zugriffsebenen für die Verwaltung von Microsoft Teams benötigen. Administratoren können den gesamten Workload von Teams verwalten oder delegierte Berechtigungen zur Behandlung von Problemen mit der Anrufqualität oder zum Verwalten der Telefoniebedürfnisse Ihrer Organisation besitzen.

## <a name="teams-roles-and-capabilities"></a>Rollen und Funktionen in Teams

Vier Teams-Administratorrollen sind verfügbar: Teams-Dienstadministrator, Teams-Kommunikationsadministrator, Supportfachmann für die Teams-Kommunikation und Supporttechniker für die Teams-Kommunikation. Sehen Sie sich die folgende Tabelle an, um zu verstehen, was jede Rolle ausführen kann und welche Tools der Administrator im Microsoft Teams Admin Center und in PowerShell verwenden kann.

Sie müssen ein Administrator sein, um Ihnen folgen zu können. Die Anweisungen zum Abrufen der Berechtigungen finden Sie in diesem Artikel.

<!-- add Global admin role? -->

| Rolle                                    | kann diese Aufgaben ausführen                                                           | kann auf die folgenden Tools zugreifen                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams-Dienstadministrator             | Verwalten des Teams-Diensts sowie verwalten und Erstellen von Microsoft 365-Gruppen            | Alles im Microsoft Teams Admin Center und zugeordneten PowerShell-Steuerelementen, darunter:<ul><li> Verwalten von Besprechungen einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenzbrücken.<sup>1,3</sup></li><li>Verwalten der VoIP-Funktionen einschließlich Anrufrichtlinien, Telefonnummernbestand und -zuweisung.<sup>1</sup></li><li>Verwalten von Messaging einschließlich Messagingrichtlinien.<sup>1,3</sup></li><li>Verwalten Sie alle organisationsweiten Einstellungen, einschließlich Föderations-, Teams-Upgrade und Clienteinstellungen für Teams. <sup>1, 3</sup></li><li>Verwalten Sie die Teams in der Organisation und die zugehörigen Einstellungen, einschließlich der Mitgliedschaft (Gruppenverwaltung, die über PowerShell unterstützt wird, Team Verwaltung im Team Admin Center). <sup>2, 3</sup></li><li>Verwalten von Teams zertifizierten Geräten und einrichten und Zuweisen von Konfigurationsrichtlinien. <sup>2</sup></li><li>Anzeigen von Benutzerprofilseiten und Ausführen einer Problembehandlung von Problemen mit der Qualität von Benutzeranrufen mithilfe des erweiterten Problembehandlungstoolsets<sup>3</sup> </li><li>Zugreifen auf alle Berichte im Microsoft Teams Admin Center</li><li> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. Erstellen Sie neue Anruf Qualitätsberichte, aktualisieren und entfernen Sie die Anruf Qualitätsberichte nach Bedarf. Hochladen und Aktualisieren von CQD-Gebäudedaten.</li><li> [Veröffentlichen von apps im Mandanten-App-Katalog im Microsoft Teams Admin Center](manage-apps.md)</li></ul> |
| Teams-Kommunikationsadministrator      | Verwalten von Anruf- und Besprechungsfunktionen innerhalb des Microsoft Teams-Diensts.               | Verwalten von Besprechungen einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenzbrücken.<sup>1,3</sup><br><br> Verwalten der VoIP-Funktionen einschließlich Anrufrichtlinien, Telefonnummernbestand und -zuweisung.<sup>1</sup><br><br> Zeigen Sie die Benutzerprofilseite an, und beheben Sie Probleme mit der Benutzer Anrufqualität mit dem Toolset für erweiterte Problembehandlung. <sup>3</sup><br><br>Greifen Sie auf den Bericht Teams PSTN-blockierte Benutzer, PSTN-Minuten Pools und PSTN-Nutzungsbericht im Microsoft Teams Admin Center zu. <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. Erstellen Sie neue Anruf Qualitätsberichte, aktualisieren und entfernen Sie die Anruf Qualitätsberichte nach Bedarf. Hochladen und Aktualisieren von CQD-Gebäudedaten.|
| Supporttechniker für die Teams-Kommunikation   | Ausführen einer Problembehandlung von Kommunikationsproblemen innerhalb von Microsoft Teams unter Verwendung **erweiterter** Tools. | Anzeigen von Benutzerprofilseiten und Ausführen einer Problembehandlung von Problemen mit der Qualität von Benutzeranrufen mithilfe des erweiterten Problembehandlungstoolsets<sup>3</sup> <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie Probleme damit mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden, bis hin zu den von schlechter Anrufqualität betroffenen Benutzern. |
| Supportfachmann für die Teams-Kommunikation | Ausführen einer Problembehandlung von Kommunikationsproblemen innerhalb von Microsoft Teams unter Verwendung **grundlegender** Tools.    | Zugreifen auf Benutzerprofilseiten, um mit der Anrufanalyse eine Problembehandlung von Anrufen durchzuführen. Kann nur Benutzerinformationen für den gesuchten Benutzer anzeigen.<sup>3</sup> <br><br> Greifen Sie auf die Anrufqualität und Zuverlässigkeit des Mandanten zu, überwachen Sie sie und behandeln Sie darauf bezogene Probleme mithilfe von Daten, die im Anrufqualitäts-Dashboard (CQD) angezeigt werden. |

<sup>1</sup> [PowerShell – Modul für Skype for Business](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell – Modul für Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft Teams Admin Center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Weitere Informationen zu den Verwaltungstools, die zum Verwalten von Microsoft Teams verfügbar sind, erhalten Sie unter [Verwalten von Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Weitere Informationen zu Beschränkungen, Spezifikationen und anderen Anforderungen, die für Teams gelten, finden Sie unter [Beschränkungen und Spezifikationen für Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Zuweisen von Benutzern zu Rollen

Sie können diesen Rollen in Azure AD Benutzer zuweisen. Um zu erfahren, wie in Azure AD einem Benutzer Administratorrollen zugewiesen werden, lesen Sie [Zuweisen von Administratorrollen zu einem Benutzer in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Für jede Rolle verfügbare Cmdlets

Die meisten PowerShell-Tools für diese Administratorrollen sind im Skype for Business PowerShell-Modul enthalten, und es ist wichtig zu beachten, dass einige Cmdlets, auf die diese Administratorrollen zugreifen können, freigegebene Einstellungen kontrollieren, die auch für Skype for Business Online verwendet werden. Die Skype for Business-Administratorrolle hat auch Zugriff auf alle Cmdlets im Skype for Business PowerShell-Modul.

Führen Sie die folgenden Schritte aus, um die vollständige Liste der Cmdlets anzuzeigen, die derzeit für eine vorgegebene Rolle im Skype for Business PowerShell-Modul verfügbar sind:

1. Weisen Sie eine solche Rolle einem Benutzer zu (und stellen Sie sicher, dass der Benutzer keine anderen Rollen hat).
2. Herstellen einer Verbindung mit dem Skype for Business PowerShell-Modul:<br>
   a. $session = new-csonlinesession<br>
   b. Import-pssession $session<br>
   c. Verwenden Sie **Get-Module**, um den Namen der importierten Sitzung zu identifizieren (der Name wird zufällig generiert).<br>
3. Verwenden Sie **Get-Command-Module** <*name from above*>, um alle verfügbaren Cmdlets zu identifizieren.

### <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [PowerShell für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

