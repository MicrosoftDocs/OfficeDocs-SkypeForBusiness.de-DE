---
title: Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
ms.reviewer: islubin
description: Hier erfahren Sie, mit den verschiedenen Administratorrollen Teams verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62b8de5d5e96177476ef07a8a91566d9757364d1
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542511"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams

Azure Active Directory (AD Azure) können Sie Administratoren festlegen, die unterschiedliche Zugriffsebenen für die Verwaltung von Microsoft-Teams benötigen. Administratoren können die gesamte Teams Auslastung verwalten, oder sie können delegiert haben Berechtigungen für die Problembehandlung Qualitätsprobleme oder Verwalten von Ihrer Organisation Telefonie benötigten aufrufen. 

## <a name="teams-roles-and-capabilities"></a>Teams Rollen und Funktionen

Es stehen vier Administratorrollen für Teams zur Verfügung: Dienstadministrator Teams, Teams Communications Administrator, Teams Communications Supportspezialisten und Teams Communications Engineer Unterstützung. Überprüfen Sie die Tabelle, um zu verstehen, was jede Rolle möglich ist, und die den Administrator tools in der Microsoft-Teams-Verwaltungskonsole und PowerShell verwenden kann.

<!-- add Global admin role? -->

| Rolle | Können diese Aufgaben | Können die folgenden Tools zugreifen |
|----- | ------------------ | ------------------------------ |
| Teams-Dienstadministrator | Verwalten des Diensts Microsoft-Teams und verwalten und Erstellen von Gruppen für Office 365 | Alles in der Microsoft-Teams-Verwaltungskonsole und die zugehörigen PowerShell-Steuerelemente, einschließlich:<br><br> Verwalten von Besprechungen, einschließlich Besprechungsanfragen Richtlinien, Konfigurationen und Konferenz Brücken<sup>1,3</sup><br><br> Verwalten von VoIP, darunter den Aufruf von Richtlinien und den Telefon-Zahl Inventar und Zuweisung<sup>1</sup><br><br> Verwalten von messaging, einschließlich Richtlinien<sup>1,3</sup> messaging<br><br> Verwalten von Einstellungen für alle Org geltende, einschließlich Verbund, Teams Upgrade und Teams Clienteinstellungen<sup>1,3</sup><br><br> Verwalten der Teams in der Organisation sowie die zugehörigen Einstellungen, einschließlich des Mitgliedschaftsanbieters (Gruppenmanagement über PowerShell Teammanagement in der Einführung der Administratorportal unterstützt) <sup>23</sup><br><br> Zeigen Sie Profilseite des Benutzers an und beheben Sie Anrufqualität mit erweiterten Problembehandlung Toolset<sup>3</sup> <br><br> Und die Überwachung und Problembehandlung bei Mandanten Anruf in anrufen Quality Dashboard (CQD) verfügbar machen, die Qualität und Zuverlässigkeit von Daten. Neue Berichte erstellen, aktualisieren und Berichte wie gewünscht zu entfernen. Hochladen und Aktualisieren von CQD Daten erstellen |
| Teams-Kommunikationsadministrator | Verwalten von Anruf- und Besprechungsfunktionen innerhalb des Microsoft Teams-Diensts | Verwalten von Besprechungen, einschließlich Besprechungsanfragen Richtlinien, Konfigurationen und Konferenz Brücken<sup>1,3</sup><br><br> Verwalten von VoIP, darunter den Aufruf von Richtlinien und den Telefon-Zahl Inventar und Zuweisung<sup>1</sup><br><br> Zeigen Sie Profilseite des Benutzers an und beheben Sie Anrufqualität mit erweiterten Problembehandlung Toolset<sup>3</sup> |
| Teams-Kommunikationssupporttechniker | Problembehandlung bei Kommunikationsproblemen in Teams mithilfe von **erweiterten** Tools. | Zeigen Sie Profilseite des Benutzers an und beheben Sie Anrufqualität mit erweiterten Problembehandlung Toolset<sup>3</sup> |
| Teams Communications-Supportspezialisten | Problembehandlung bei Kommunikationsproblemen in Teams mithilfe von **grundlegenden** Tools.| Zugriff auf der Profilseite des Benutzers für die Problembehandlung bei ruft in Analytics aufrufen. Kann nur Benutzerinformationen für den gesuchten Benutzer anzeigen.<sup>3</sup>

<sup>1</sup> [PowerShell - Skype für Business-Modul](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Modul für Microsoft-Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [-Verwaltungskonsole Microsoft-Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
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
3. Verwendung **Get-Command - Modul** <> zum Identifizieren aller verfügbaren Cmdlets*Namen von oben*

### <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft-Teams, die PowerShell](teams-powershell-overview.md)
- [Microsoft-Teams, PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

