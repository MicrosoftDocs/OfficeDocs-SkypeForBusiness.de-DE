---
title: Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams
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
description: Erfahren Sie, wie Sie die verschiedenen Administratorrollen zum Verwalten von Teams verwenden können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa461f587b2143b1981c3dfc70910572bd4cb004
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925423"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams

Mit Azure Active Directory (Azure AD) können Sie Administratoren festlegen, die unterschiedliche Zugriffsebenen für die Verwaltung von Microsoft Teams benötigen. Administratoren können die gesamte Arbeitsauslastung der Teams verwalten, oder Sie können über Delegierte Berechtigungen zur Behandlung von Problemen mit der Anrufqualität oder zur Verwaltung der Telefon Anforderungen Ihrer Organisation verfügen. 

## <a name="teams-roles-and-capabilities"></a>Rollen und Funktionen von Teams

Es stehen vier Teams-Administratorrollen zur Verfügung: Teams Service Administrator, Teams Communications Administrator, Team Communications Support Specialist und Teams Communications Support Engineer. Sehen Sie sich die folgende Tabelle an, um zu erfahren, welche Aktionen die einzelnen Rollen ausführen können und welche Tools der Administrator in Microsoft Teams Admin Center und PowerShell verwenden kann.



<!-- add Global admin role? -->

| Rolle | Kann diese Aufgaben ausführen. | Kann auf die folgenden Tools zugreifen |
|----- | ------------------ | ------------------------------ |
| Teams-Dienstadministrator | Verwalten des Teams-Diensts sowie verwalten und Erstellen von Office 365-Gruppen | Alles im Microsoft Teams Admin Center und zugehörige PowerShell-Steuerelemente, einschließlich:<ul><li> Verwalten von Besprechungen, einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenz Brücken <sup>1, 3</sup></li><li>Verwalten von VoIP, einschließlich Anruf Richtlinien und Inventar und Zuordnung von Telefonnummern. <sup>1</sup></li><li>Verwalten von Nachrichten, einschließlich Messagingrichtlinien <sup>1, 3</sup></li><li>Verwalten Sie alle organisationsweiten Einstellungen, einschließlich der Föderation, des Teams-Upgrades und der Clienteinstellung für Teams. s<sup>1, 3</sup></li><li>Verwalten Sie die Teams in der Organisation und die zugehörigen Einstellungen, einschließlich der Mitgliedschaft (Gruppenverwaltung, die über PowerShell unterstützt wird, Team Verwaltung im Team Admin Center). <sup>23</sup></li><li>Zeigen Sie die Benutzerprofilseite an, und beheben Sie Probleme mit der Benutzer Anrufqualität mithilfe der erweiterten Problembehandlung-Toolset. <sup>3</sup> </li><li> Greifen Sie auf die Anrufqualität und Zuverlässigkeit von Mandanten auf, überwachen und behandeln Sie Sie mithilfe von Daten, die im CQD-Dashboard (Anrufqualität) angezeigt werden, bis hin zu Benutzern, die von schlechter Anrufqualität betroffen Erstellen Sie neue Berichte, aktualisieren Sie Berichte, und entfernen Sie Sie nach Bedarf. Hochladen und Aktualisieren von CQD-Gebäudedaten</li><li> [Veröffentlichen von apps im Mandanten-App-Katalog des Teams-Clients](https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams)</li></ul> |
| Teams-Kommunikationsadministrator | Verwalten von Anruf-und besprechungsfeatures innerhalb des Teams-Diensts. | Verwalten von Besprechungen, einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenz Brücken <sup>1, 3</sup><br><br> Verwalten von VoIP, einschließlich Anruf Richtlinien und Inventar und Zuordnung von Telefonnummern. <sup>1</sup><br><br> Zeigen Sie die Benutzerprofilseite an, und beheben Sie Probleme mit der Benutzer Anrufqualität mithilfe der erweiterten Problembehandlung-Toolset. <sup>3</sup> <br><br> Zugreifen auf, überwachen und behandeln von Problemen mit der Anrufqualität und-Zuverlässigkeit von Mandanten mithilfe von Daten, die im Dashboard für die Anrufqualität (CQD) verfügbar gemacht werden, bis hin zu Benutzern, die von schlechter Anrufqualität betroffen sind. Erstellen Sie neue Berichte, aktualisieren Sie Berichte, und entfernen Sie Sie nach Bedarf. Hochladen und Aktualisieren von CQD-Gebäudedaten|
| Teams-Kommunikationssupporttechniker | Behandeln von Kommunikationsproblemen in Microsoft Teams mithilfe der **erweiterten** Tools | Zeigen Sie die Benutzerprofilseite an, und beheben Sie Probleme mit der Benutzer Anrufqualität mithilfe der erweiterten Problembehandlung-Toolset. <sup>3</sup> <br><br> Zugreifen auf, überwachen und behandeln von Problemen mit der Anrufqualität und-Zuverlässigkeit von Mandanten mithilfe von Daten, die im Dashboard für die Anrufqualität (CQD) verfügbar gemacht werden, bis hin zu Benutzern, die von schlechter Anrufqualität betroffen sind. |
| Teams Communications-Support Spezialist | Behandeln von Kommunikationsproblemen in Teams mithilfe von **grundlegenden** Tools| Zugriff auf die Benutzerprofilseite für die Problembehandlung von Anrufen in der anrufanalyse. Kann nur Benutzerinformationen für den gesuchten Benutzer anzeigen.<sup>3</sup> <br><br> Zugreifen auf, überwachen und behandeln von Problemen mit der Anrufqualität und-Zuverlässigkeit von Mandanten mithilfe von Daten, die im Anruf Qualitäts Dashboard (CQD) verfügbar gemacht werden.  

<sup>1</sup> [PowerShell – Skype for Business-Modul](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell – Microsoft Teams-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft Teams Admin Center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Weitere Informationen zu den für die Verwaltung von Microsoft Teams verfügbaren Verwaltungstools finden Sie unter [Verwalten von Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Weitere Informationen zu Grenzwerten, Spezifikationen und anderen Anforderungen, die für Teams gelten, finden Sie unter [Grenzwerte und Spezifikationen für Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Zuweisen von Benutzern zu jeder Rolle

Sie können diesen Rollen in Azure AD Benutzer zuweisen. Informationen zum Zuweisen von Administratorrollen zu einem Benutzer in Azure AD finden Sie unter [Zuweisen eines Benutzers zu Administratorrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Für jede Rolle verfügbare Cmdlets

Die meisten PowerShell-Tools für diese Administratorrollen sind im Skype for Business PowerShell-Modul enthalten, und es ist wichtig zu beachten, dass einige Cmdlets, für die diese Administratorrollen verfügbar sind, Zugriff auf die Steuerung freigegebener Einstellungen haben, die auch für Skype for Business Online verwendet werden. Die Skype for Business-Administratorrolle hat auch Zugriff auf alle Cmdlets des Skype for Business PowerShell-Moduls.

Führen Sie die folgenden Schritte aus, um die vollständige Liste der derzeit für eine bestimmte Rolle verfügbaren Cmdlets im Skype for Business PowerShell-Modul anzuzeigen:

1. Weisen Sie diese Rolle einem Benutzer zu (und stellen Sie sicher, dass der Benutzer keine anderen Rollen hat).
2. Stellen Sie eine Verbindung mit dem Skype for Business PowerShell-Modul her:<br>
   a. $Session = neu-csonlinesession<br>
   b. Importieren-PSSession $Session<br>
   c. Verwenden **Sie "Get-Module** ", um den Namen der importierten Sitzung zu identifizieren (Dies ist ein zufällig generierter Name).<br>
3. Verwenden Sie den Namen des **Befehls Moduls** <*von oben*>, um alle verfügbaren Cmdlets zu identifizieren.

### <a name="related-topics"></a>Verwandte Themen

- [Microsoft Teams PowerShell-Übersicht](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

