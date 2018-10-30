---
title: Verwenden von Microsoft-Teams, Administratorrollen zum Verwalten von Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
description: Lernen, wie die verschiedenen administrative Rollen zum Verwalten von Teams verwendet.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f70b1035600079d4a4f746fe33fa03c6eab287a7
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838991"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>Verwenden von Microsoft-Teams, Administratorrollen zum Verwalten von Teams

Azure Active Directory (AD Azure) können Sie Administratoren festlegen, die unterschiedliche Zugriffsebenen für die Verwaltung von Microsoft-Teams benötigen. Administratoren können die gesamte Teams Auslastung verwalten, oder sie können delegiert haben Berechtigungen für die Problembehandlung Qualitätsprobleme oder Verwalten von Ihrer Organisation Telefonie benötigten aufrufen. 

## <a name="teams-roles-and-capabilities"></a>Teams Rollen und Funktionen

Es stehen vier Administratorrollen für Teams zur Verfügung: Dienstadministrator Teams, Teams Communications Administrator, Teams Communications Supportspezialisten und Teams Communications Engineer Unterstützung. Überprüfen Sie in der folgenden Tabelle, um zu verstehen, was jede Rolle möglich ist, und die den Administrator tools für Business Admin Center und PowerShell in der Teams und Skype verwenden kann.

<!-- add Global admin role? -->

| Rolle | Können diese Aufgaben | Können die folgenden Tools zugreifen |
|----- | ------------------ | ------------------------------ |
| Teams-Dienstadministrator | Verwalten des Diensts Microsoft-Teams und verwalten und Erstellen von Gruppen für Office 365 | Alles in der Microsoft-Teams & Skype für Business Admin Center und zugehörige PowerShell-Steuerelemente, einschließlich:<br><br> Verwalten von Besprechungen, einschließlich Besprechungsanfragen Richtlinien, Konfigurationen und Konferenz Brücken<sup>1,3</sup><br><br> Verwalten von VoIP, darunter den Aufruf von Richtlinien und den Telefon-Zahl Inventar und Zuweisung<sup>1</sup><br><br> Verwalten von messaging, einschließlich Richtlinien<sup>1,3</sup> messaging<br><br> Verwalten von Einstellungen für alle Org geltende, einschließlich Verbund, Teams Upgrade und Teams Clienteinstellungen<sup>1,3</sup><br><br> Verwalten der Teams in der Organisation sowie die zugehörigen Einstellungen, einschließlich des Mitgliedschaftsanbieters (Gruppenmanagement über PowerShell Teammanagement in der Einführung der Administratorportal unterstützt) <sup>23</sup><br><br> Zeigen Sie Profilseite des Benutzers an und beheben Sie Anrufqualität mit erweiterten Problembehandlung Toolset<sup>3</sup> |
| Teams-Kommunikationsadministrator | Verwalten von Anruf- und Besprechungsfunktionen innerhalb des Microsoft Teams-Diensts | Verwalten von Besprechungen, einschließlich Besprechungsanfragen Richtlinien, Konfigurationen und Konferenz Brücken<sup>1,3</sup><br><br> Verwalten von VoIP, darunter den Aufruf von Richtlinien und den Telefon-Zahl Inventar und Zuweisung<sup>1</sup><br><br> Zeigen Sie Profilseite des Benutzers an und beheben Sie Anrufqualität mit erweiterten Problembehandlung Toolset<sup>1,3</sup> |
| Teams-Kommunikationssupporttechniker | Problembehandlung bei Kommunikationsproblemen in Teams mithilfe von **erweiterten** Tools. | Zugriff auf der Profilseite des Benutzers für die Problembehandlung bei ruft in Analytics aufrufen. Können vollständige Anruf Erfassen von Informationen anzeigen. <sup>3</sup> |
| Teams Communications-Supportspezialisten | Problembehandlung bei Kommunikationsproblemen in Teams mithilfe von **grundlegenden** Tools.| Zugriff auf der Profilseite des Benutzers für die Problembehandlung bei ruft in Analytics aufrufen. Kann nur Benutzerinformationen für den gesuchten Benutzer anzeigen.<sup>3</sup>

<sup>1</sup> [PowerShell - Skype für Business-Modul](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Modul für Microsoft-Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft-Teams und Skype für Business Admin Center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Weitere Informationen zum Verwalten von Microsoft-Teams, die Verwaltungstools finden Sie unter [Verwalten von Microsoft-Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

## <a name="assign-users-to-each-role"></a>Zuweisen von Benutzern zu einzelnen Rollen

Sie können die Benutzer zu diesen Rollen in Azure Active Directory zuweisen. Zuweisen von administrativen Rollen zu einem Benutzer in Azure Active Directory finden Sie unter [Zuweisen eines Benutzers zu Administratorrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Verfügbaren Cmdlets für die einzelnen Rollen

Die meisten PowerShell Tools für diese Administratorrollen live in der Skype für Business PowerShell-Modul, und es ist zu beachten, dass einige der Cmdlets, dass diese Administratorrollen auf Steuerelement zugreifen Einstellungen gemeinsam verwendet, die auch für Skype für Business Online genutzt werden. Um die vollständige Liste der Cmdlets, die derzeit auf einer bestimmten Rolle in der Skype für Business PowerShell-Modul anzuzeigen, gehen Sie folgendermaßen vor:

1. Weisen Sie dieser Rolle zu einem Benutzer zu (und stellen Sie sicher, dass der Benutzer keine anderen Rollen).
2. Verbinden Sie mit der Skype für Business PowerShell-Modul:<br>
   a. $session = neue Csonlinesession<br>
   b. Import-Pssession $session<br>
   c. Verwenden Sie **Get-Modul** , um den Namen der importierten Sitzung identifizieren (einen willkürlich generierten Namen wird sein).<br>
3. Verwendung **Get-Command - Modul** <*Namen von oben*> zum Identifizieren aller verfügbaren Cmdlets

### <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft-Teams, die PowerShell](teams-powershell-overview.md)
- [Microsoft-Teams, PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Weisen Sie Team-Besitzer und Membern im Microsoft-Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

