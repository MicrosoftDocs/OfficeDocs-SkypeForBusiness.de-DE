---
title: Checkliste für das Onboarding – Konfigurieren von Kernfunktionen – Microsoft Teams
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
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c28f33cb8d3c3823f74deb8f6540a39482f68b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098031"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Konfigurieren von Microsoft Teams-Kernfunktionen

| Nein | Aktivität oder Aufgabe | Beschreibung | Abgeschlossen? | Weitere Informationen |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Überprüfen, ob Ihre Umgebung alle Voraussetzungen für Teams umfasst | Teams hängt von anderen Plattformen ab, um eine end-to-end-Lösung für die Zusammenarbeit zu erstellen. Arbeiten Sie mit Ihren #A0 zusammen, um sicherzustellen, dass Sie Exchange, SharePoint Online und OneDrive for Business bereitgestellt und ordnungsgemäß konfiguriert haben. | | [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md) |
| 2  | Überprüfen, ob Teams für den Mandanten aktiviert ist | Teams ist standardmäßig für alle Organisationen aktiviert. Überprüfen Sie die Seite **Dienste &-Add-Ins** im Microsoft 365 Admin Center, um zu überprüfen, ob Teams für Ihre Organisation aktiviert ist, und aktivieren Sie es bei Bedarf. | | [Einrichten von Microsoft Teams in Microsoft 365 oder Office 365](office-365-set-up.md) |
| 3  | Konfigurieren von Rollen und Berechtigungen | Teams unterstützt zwei Arten von Rollen: Mitglied und Besitzer. <br/><br/>Nachdem ein Mitglied zu einem Team hinzugefügt wurde, kann ein Besitzer ein Mitglied auch zur Rolle "Besitzer" bewerben. Als bewährte Methode empfehlen wir, jedem Team mindestens zwei Besitzer zugewiesen zu haben. <br/><br/>Standardmäßig kann jeder in der Organisation, der über ein postfach verfügt, das auf Exchange Online gehostet wird, ein Team erstellen. Einem Benutzer, der ein neues Team erstellt, wird automatisch die Rolle "Besitzer" für dieses Team gewährt. <br/><br/>Bei Bedarf können Sie Microsoft 365-Gruppeneinstellungen so konfigurieren, dass nur bestimmte Benutzer neue Teams erstellen können. | | [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365-Gruppen und Microsoft Teams](office-365-groups.md) <br/><br/>[Verwalten, wer Microsoft 365-Gruppen erstellen kann](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Konfigurieren von mandantenweiten Teams-Einstellungen | Sie können einige Teams-Einstellungen auf Mandantenebene konfigurieren. Benutzer, die für Teams aktiviert sind, erben diese Einstellungen von der Mandantenkonfiguration:<ul><li>Allgemein</li><li>E-Mail-Integration</li><li>Apps</li><li>Benutzerdefinierter Cloudspeicher</li><li>Anrufe und Besprechungen</li><li>Messaging</li></ul>| | [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md) |
| 5  | OPTIONAL: Konfigurieren des Gastzugriffs | Sie verwenden Gastzugriff in Teams, um mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem Sie ihnen Zugriff auf Teams und Kanäle gewähren. Der Gastzugriff ist eine Einstellung auf Mandantenebene in Teams. Diese Option ist standardmäßig deaktiviert. <br/>Aktivieren Sie den Gastzugriff, und konfigurieren Sie mandantenweite Gasteinstellungen, wenn Ihre Organisation plant, dieses Feature zu verwenden. | | [Gastzugriff in Microsoft Teams](guest-access.md) |
| 6  | OPTIONAL: Konfigurieren der Benennungsrichtlinie für Teams | Teams verwendet die Benennungsrichtlinien für Microsoft 365-Gruppen, wenn Benutzer Teamnamen erstellen oder bearbeiten. <br/><br/>Standardmäßig werden keine Benennungseinschränkungen angewendet, wenn ein Benutzer ein Team erstellt. <br/><br/>Wenn Sie Regeln für Teamnamen erzwingen müssen, konfigurieren Sie Benennungsrichtlinien für Microsoft 365-Gruppen, die für Ihre Organisation gelten. Sie können obligatorische Präfixe und Suffixe festlegen und blockierte Wörter angeben. | | [Planen von Microsoft 365-Gruppen beim Erstellen von Teams in Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Benennungsrichtlinie für Microsoft 365-Gruppen](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Konfigurieren von Exchange für die Domäne "Teams SMTP" | Teams verwendet Exchange Online, um Benachrichtigungen mithilfe der SMTP-Domäne – email.teams.microsoft.com – an Teammitglieder zu senden, wenn sie hinzugefügt oder entfernt wurden. <br/><br/>Fügen Sie diese SMTP-Domäne der Liste der akzeptierten Domänen in Ihrer Exchange-Infrastruktur hinzu. | | [Erstellen von Listen sicherer Absender in Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Konfigurieren und Verwalten des Benutzerzugriffs auf Teams | Obwohl wir dringend empfehlen, dass Sie alle Benutzer für Teams aktivieren, können Sie den Zugriff auf Teams pro Benutzer zulassen oder vernennen, indem Sie die Produktlizenz für Teams zuweisen oder entfernen. | | [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md) |
| 9  | Zuweisen von Lizenzen zu Benutzern | Zuweisen von Lizenzen zu Ihren Benutzern für Features wie Audiokonferenzen, Telefonsystem und Anrufpläne | | [Zuweisen von Microsoft Teams-Add-On-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Optional: Verwenden von PowerShell zum Verwalten von Teams | Sie können PowerShell-Cmdlets anstelle des Microsoft 365 Admin Centers zum Verwalten und Verwalten von Teams-Einstellungen verwenden. | | [PowerShell für Microsoft Teams](/powershell/module/teams/?view=teams-ps) |