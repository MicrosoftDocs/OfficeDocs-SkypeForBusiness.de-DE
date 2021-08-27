---
title: Prüfliste für onboarding – Grundlegende Funktionen konfigurieren – Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Folgen Sie den grundlegenden Aufgaben und Aktivitäten in dieser Checkliste, wenn Sie Teams für Ihre Organisation konfigurieren.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e721979303a9132a214d797e0a1887d2e0a691b5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582209"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Konfigurieren Microsoft Teams Kernfunktionen

| Nein | Aktivität oder Aufgabe | Beschreibung | Abgeschlossen? | Weitere Informationen |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Überprüfen, ob Ihre Umgebung alle erforderlichen Teams umfasst | Teams ist von anderen Plattformen abhängig, um eine End-to-End-Zusammenarbeitslösung zu erstellen. Arbeiten Sie mit Ihren IT-Teams zusammen, um sicherzustellen, dass Sie Exchange, SharePoint Online und OneDrive for Business. | | [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md) |
| 2  | Überprüfen, Teams für den Mandanten aktiviert ist | Teams ist standardmäßig für alle Organisationen aktiviert. Überprüfen Sie **die Seite & Dienste und Add-Ins** im Microsoft 365 Admin Center, um zu überprüfen, ob Teams für Ihre Organisation aktiviert ist, und aktivieren Sie es bei Bedarf. | | [Einrichten einer Microsoft Teams in Microsoft 365 oder Office 365](office-365-set-up.md) |
| 3  | Konfigurieren von Rollen und Berechtigungen | Teams unterstützen zwei Arten von Rollen: Mitglied und Besitzer. <br/><br/>Nachdem ein Mitglied zu einem Team hinzugefügt wurde, kann ein Besitzer ein Mitglied auch zur Rolle "Besitzer" ernennen. Als bewährte Methode empfehlen wir, jedem Team mindestens zwei Besitzer zugewiesen zu haben. <br/><br/>Standardmäßig kann jeder in der Organisation, der auf einem Postfach gehostet ist, Exchange Online ein Team erstellen. Einem Benutzer, der ein neues Team erstellt, wird automatisch die Rolle "Besitzer" für dieses Team erteilt. <br/><br/>Bei Bedarf können Sie die Gruppeneinstellungen Microsoft 365, damit nur bestimmte Benutzer neue Teams erstellen können. | | [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365 von Gruppen und Microsoft Teams](office-365-groups.md) <br/><br/>[Verwalten, wer Gruppen erstellen Microsoft 365 kann](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Konfigurieren mandantenweite Teams Einstellungen | Sie können einige Teams auf Mandantenebene konfigurieren. Benutzer, die für aktiviert sind, Teams Einstellungen von der Mandantenkonfiguration erben:<ul><li>Allgemein</li><li>E-Mail-Integration</li><li>Apps</li><li>Benutzerdefinierter Cloudspeicher</li><li>Anrufe und Besprechungen</li><li>Messaging</li></ul>| | [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md) |
| 5  | OPTIONAL: Konfigurieren des Gastzugriffs | Sie verwenden Gastzugriff in Teams für die Zusammenarbeit mit Personen außerhalb Ihrer Organisation, indem Sie diesen Zugriff auf Teams und Kanäle gewähren. Der Gastzugriff ist eine Einstellung auf Mandantenebene in Teams. Diese Option ist standardmäßig deaktiviert. <br/>Aktivieren Sie den Gastzugriff, und konfigurieren Sie mandantenweite Gasteinstellungen, wenn Ihre Organisation die Verwendung dieses Features plant. | | [Gastzugriff in Microsoft Teams](guest-access.md) |
| 6  | OPTIONAL: Konfigurieren Teams Benennungsrichtlinie | Teams verwendet die Benennungsrichtlinien für Microsoft 365 Gruppen, wenn Benutzer Teamnamen erstellen oder bearbeiten. <br/><br/>Standardmäßig werden beim Erstellen eines Teams durch einen Benutzer keine Beschränkungen für die Namensgebung angewendet. <br/><br/>Wenn Sie Regeln für Teams-Namen erzwingen müssen, konfigurieren Microsoft 365 Benennungsrichtlinien für Gruppen, die für Ihre Organisation gelten. Sie können obligatorische Präfixe und Suffixe sowie blockierte Wörter festlegen. | | [Planen Sie Microsoft 365 Gruppen beim Erstellen von Teams in Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Microsoft 365 Benennungsrichtlinie für Gruppen](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Konfigurieren Exchange für die TEAMS SMTP-Domäne | Teams verwendet Exchange Online, um Benachrichtigungen mithilfe der SMTP-Domäne (email.teams.microsoft.com) an Teammitglieder zu senden, wenn diese hinzugefügt oder entfernt wurden. <br/><br/>Achten Sie darauf, dass Sie diese SMTP-Domäne der Liste der akzeptierten Domänen in Ihrer Exchange hinzufügen. | | [Erstellen von Listen sicherer Absender in Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Konfigurieren und Verwalten des Benutzerzugriffs auf Teams | Obwohl es dringend empfohlen wird, alle Benutzer für Teams zu aktivieren, können Sie den Zugriff auf Teams pro Benutzer zulassen oder nicht zulassen, indem Sie die Teams-Produktlizenz zuweisen oder entfernen. | | [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md) |
| 9  | Zuweisen von Lizenzen zu Benutzern | Weisen Sie Ihren Benutzern Lizenzen für Funktionen wie Audiokonferenzen, Telefonsystem und Anrufpläne zu. | | [Zuweisen Microsoft Teams Add-On-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Optional: Verwenden Sie PowerShell zum Verwalten Teams | Sie können PowerShell-Cmdlets anstelle der Einstellungen Microsoft 365 Admin Center verwalten und Teams verwalten. | | [PowerShell für Microsoft Teams](/powershell/module/teams/?view=teams-ps) |