---
title: Prüfliste für das Onboarding – Konfigurieren der grundlegenden Funktionen – Microsoft Teams
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
ms.openlocfilehash: a2987b507b9fa149ad874b1035a753586c05b23d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802305"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Konfigurieren der Kernfunktionen von Microsoft Teams

| Nein | Aktivität oder Aufgabe | Beschreibung | Abgeschlossen? | Weitere Informationen |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Überprüfen, ob Ihre Umgebung alle Voraussetzungen für Teams umfasst | Teams hängt von anderen Plattformen ab, um eine End-to-End-Zusammenarbeitslösung zu erstellen. Arbeiten Sie mit Ihren #A0 zusammen, um sicherzustellen, dass Sie Exchange, SharePoint Online und OneDrive for Business bereitgestellt und ordnungsgemäß konfiguriert haben. | | [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md) |
| 2  | Überprüfen, ob Teams für den Mandanten aktiviert ist | Teams ist für alle Organisationen standardmäßig aktiviert. Überprüfen Sie im Microsoft 365 Admin Center die Seite "Dienste **&-Add-Ins",** um zu überprüfen, ob Teams für Ihre Organisation aktiviert ist, und aktivieren Sie es bei Bedarf. | | [Einrichten von Microsoft Teams in Microsoft 365 oder Office 365](office-365-set-up.md) |
| 3  | Konfigurieren von Rollen und Berechtigungen | Teams unterstützt zwei Arten von Rollen: Mitglied und Besitzer. <br/><br/>Nachdem ein Mitglied zu einem Team hinzugefügt wurde, kann ein Besitzer ein Mitglied auch in die Rolle "Besitzer" bewerben. Als bewährte Methode empfehlen wir, jedem Team mindestens zwei Besitzer zugewiesen zu haben. <br/><br/>Standardmäßig kann jeder in der Organisation, der über ein auf Exchange Online gehostetes Postfach verfügt, ein Team erstellen. Einem Benutzer, der ein neues Team erstellt, wird automatisch die Rolle "Besitzer" für dieses Team erteilt. <br/><br/>Bei Bedarf können Sie Microsoft 365-Gruppeneinstellungen so konfigurieren, dass nur bestimmte Benutzer neue Teams erstellen können. | | [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365-Gruppen und Microsoft Teams](office-365-groups.md) <br/><br/>[Verwalten, wer Microsoft 365-Gruppen erstellen kann](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Konfigurieren mandantenweiter Teams-Einstellungen | Sie können einige Teams-Einstellungen auf Mandantenebene konfigurieren. Benutzer, die für Teams aktiviert sind, erben diese Einstellungen von der Mandantenkonfiguration:<ul><li>Allgemein</li><li>E-Mail-Integration</li><li>Apps</li><li>Benutzerdefinierter Cloudspeicher</li><li>Anrufe und Besprechungen</li><li>Messaging</li></ul>| | [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md) |
| 5  | OPTIONAL: Konfigurieren des Gastzugriffs | Sie verwenden Gastzugriff in Teams, um mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem Sie diesen Zugriff auf Teams und Kanäle gewähren. Der Gastzugriff ist eine Einstellung auf Mandantenebene in Teams. Diese Option ist standardmäßig deaktiviert. <br/>Aktivieren Sie den Gastzugriff, und konfigurieren Sie mandantenweite Gasteinstellungen, wenn Ihre Organisation die Verwendung dieses Features plant. | | [Gastzugriff in Microsoft Teams](guest-access.md) |
| 6  | OPTIONAL: Konfigurieren der Benennungsrichtlinie für Teams | Teams nutzt die Benennungsrichtlinien für Microsoft 365-Gruppen, wenn Benutzer Teamnamen erstellen oder bearbeiten. <br/><br/>Standardmäßig gelten keine Benennungseinschränkungen, wenn ein Benutzer ein Team erstellt. <br/><br/>Wenn Sie Regeln für Teamnamen erzwingen müssen, konfigurieren Sie Benennungsrichtlinien für Microsoft 365-Gruppen, die für Ihre Organisation gelten. Sie können obligatorische Präfixe und Suffixe festlegen und blockierte Wörter angeben. | | [Planen von Microsoft 365-Gruppen beim Erstellen von Teams in Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Benennungsrichtlinie für Microsoft 365-Gruppen](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Konfigurieren von Exchange für die Teams -SMTP-Domäne | Teams verwendet Exchange Online zum Senden von Benachrichtigungen an Teammitglieder mithilfe der SMTP-Domäne – email.teams.microsoft.com –, wenn sie hinzugefügt oder entfernt wurden. <br/><br/>Achten Sie darauf, diese "SMTP"-Domäne der Liste akzeptierter Domänen in Ihrer Exchange-Infrastruktur hinzuzufügen. | | [Erstellen von Listen sicherer Absender in Exchange](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Konfigurieren und Verwalten des Benutzerzugriffs auf Teams | Obwohl es dringend empfohlen wird, alle Benutzer für Teams zu aktivieren, können Sie den Zugriff auf Teams pro Benutzer zulassen oder nicht zulassen, indem Sie die Produktlizenz für Teams zuweisen oder entfernen. | | [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md) |
| 9  | Zuweisen von Lizenzen zu Benutzern | Weisen Sie Ihren Benutzern Lizenzen für Funktionen wie Audiokonferenzen, Telefonsystem und Anrufpläne zu. | | [Zuweisen von Microsoft Teams-Add-On-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Optional: Verwenden von PowerShell zum Verwalten von Teams | Sie können anstelle des Microsoft 365 Admin Centers die Microsoft 365-Cmdlets zum Verwalten und Verwalten von Microsoft Teams-Einstellungen verwenden. | | [PowerShell für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
