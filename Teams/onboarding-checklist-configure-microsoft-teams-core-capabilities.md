---
title: Onboardingcheckliste für das Konfigurieren der grundlegenden Funktionen von Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Führen Sie die Core sowie die Aufgabe Aufgaben und Aktivitäten in der Prüfliste beim Konfigurieren von Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: acaab4de788af1dc84a1cff0908868b1ddd924b4
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304517"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Konfigurieren von Microsoft-Teams Kernfunktionen

| Nein | Aktivität oder Aufgabe | Beschreibung | Abgeschlossen? | Weitere Informationen |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Überprüfen Sie, dass die Umgebung alle Teams erforderlichen Komponenten umfasst. | Teams hängt zum Erstellen einer Lösung für die End-to-End-Zusammenarbeit anderen Plattformen zu ermöglichen. Arbeiten Sie mit Ihrem IT-Teams, um sicherzustellen, dass Sie bereitgestellt und ordnungsgemäß, Exchange, SharePoint Online und OneDrive für Unternehmen konfiguriert haben. | | [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md) |
| 2  | Überprüfen, ob die Teams für den Mandanten aktiviert ist | Teams ist für alle Organisationen in der Standardeinstellung aktiviert. Überprüfen Sie die Seite **Dienste &-add-ins** im Office 365 Admin Center, um sicherzustellen, dass Teams für Ihre Mandanten aktiviert ist, und aktivieren sie bei Bedarf. | | [Microsoft Teams in Ihrer Office 365-Organisation einrichten](office-365-set-up.md) |
| 3  | Konfigurieren von Rollen und Berechtigungen | Teams unterstützen zwei Arten von Rollen: Member und Besitzer. <br/><br/>Nach dem Hinzufügen eines Elements zu einem Team, kann ein Besitzer auch Mitglied der Rolle Besitzer anzubieten. Als bewährte Methode wird empfohlen, dass Sie mindestens zwei Besitzer jedes Team zugewiesen haben. <br/><br/>Standardmäßig kann jeder Benutzer in der Organisation, die ein Postfach in Exchange Online gehostet hat ein Team erstellen. Ein neues Team erstellt ein Benutzer wird die Rolle des Eigentümers für dieses Team automatisch erteilt. <br/><br/>Wenn Sie möchten, können Sie Office 365 Clientgruppen, um nur bestimmte Benutzer neue Teams erstellen lassen konfigurieren. | | [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Office 365-Gruppen und Microsoft Teams](office-365-groups.md) <br/><br/>[Verwalten von Benutzer, die Office 365 Gruppen erstellen können](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Konfigurieren von Einstellungen für Mandanten geltende-Teams | Sie können einige Teams Einstellungen auf der Ebene der Mandant konfigurieren. Benutzer, die für Teams aktiviert werden erben diese Einstellungen von der Mandantenkonfiguration:<ul><li>Allgemein</li><li>E-Mail-Integration</li><li>Apps</li><li>Benutzerdefinierter Cloudspeicher</li><li>Anrufe und Besprechungen</li><li>Messaging</li></ul>| | [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md) |
| 5  | OPTIONAL: Konfigurieren des Zugriffs Gast | Verwenden Sie Gast Access in Teams, um mit Personen außerhalb Ihrer Organisation zusammenarbeiten, indem Sie ihnen Zugriff auf Teams und Kanäle gewähren. Gast Access ist eine Einstellung auf Mandantenebene in Teams. Es ist standardmäßig deaktiviert. <br/>Gast Access Einstellungen aktivieren Sie und konfigurieren Sie Mandanten geltende Gast, wenn Ihre Organisation plant, das Feature zu verwenden. | | [Gastzugriff in Microsoft Teams](guest-access.md) |
| 6  | OPTIONAL: Konfigurieren der Richtlinie zum Benennen Teams | Teams nutzt die naming Richtlinien für Office 365-Gruppen, wenn Benutzer erstellen oder Bearbeiten von Teamnamen. <br/><br/>Standardmäßig werden keine Beschränkungen bei der Benennung angewendet, wenn ein Benutzer ein Team erstellt. <br/><br/>Wenn Sie Regeln für die Namen von Teams erzwingen möchten, konfigurieren Sie Office 365 Gruppen Benennen von Richtlinien, die für Ihre Organisation gelten. Sie können obligatorisch Präfixen und Suffixen festlegen und blockierte Wörter. | | [Planen von Office 365-Gruppen beim Erstellen von Teams in Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Office 365 gruppiert Benennungsrichtlinie](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Konfigurieren von Exchange für die Teams SMTP-Domäne | Teams verwendet zum Senden von Benachrichtigungen an die Teammitglieder die SMTP-Domäne mit Exchange Online – email.teams.microsoft.com – Wenn sie haben hinzugefügt oder entfernt wurde. <br/><br/>Achten Sie darauf, dass diese SMTP-Domäne der Liste der akzeptierten Domänen in Ihrer Exchange-Infrastruktur hinzuzufügen. | | [Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online](smtp-accepted-domain.md) |
| 8  | Konfigurieren Sie und verwalten Sie des Benutzerzugriffs auf Teams | Obwohl dringend empfohlen, dass Sie alle Benutzer für Teams aktivieren, können Sie zulassen oder Sperren des Zugriffs auf Teams auf jeden Benutzer einzeln durch Zuweisen oder Entfernen der Teams-Lizenzvertrags. | | [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md) |
| 9  | Benutzern Lizenzen zuweisen | Zuweisen von Lizenzen für Ihre Benutzer für Funktionen wie Audiokonferenzen Telefonsystem und plant aufrufen | | [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](assign-teams-licenses.md) <br/><br/>[MyAdvisor – Benutzer-Aktivierung Skripts](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_6,5_2_0_3) |
| 10 | Optional: Verwenden von PowerShell zum Verwalten von Teams | Sie können PowerShell-Cmdlets statt der Office 365-Verwaltungskonsole zur Verwaltung und Verwalten von Einstellungen für Teams verwenden. | | [Microsoft-Teams, PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |