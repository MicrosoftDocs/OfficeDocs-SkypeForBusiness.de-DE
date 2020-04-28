---
title: Checkliste für Onboarding – Konfigurieren von Kernfunktionen – Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Befolgen Sie die grundlegenden Aufgaben und Aktivitäten in dieser Checkliste, wenn Sie Teams für Ihre Organisation konfigurieren.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69874e9d75cea1377b0aae110b5e1b3ce681d84f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903900"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Konfigurieren der Kernfunktionen von Microsoft Teams

| Nein | Aktivität oder Aufgabe | Beschreibung | Abgeschlossen? | Weitere Informationen |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Überprüfen, ob Ihre Umgebung alle Voraussetzungen für Teams umfasst | Teams hängt von anderen Plattformen ab, um eine End-to-End-Zusammenarbeitslösung zu erstellen. Arbeiten Sie mit Ihren IT-Teams zusammen, um sicherzustellen, dass Sie Exchange, SharePoint Online und OneDrive for Business bereitgestellt und ordnungsgemäß konfiguriert haben. | | [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md) |
| 2  | Überprüfen, ob Teams für den Mandanten aktiviert sind | Teams ist standardmäßig für alle Organisationen aktiviert. Überprüfen Sie die Seite **Dienste & Add-ins** im Microsoft 365 Admin Center, um zu überprüfen, ob Teams für Ihren Mandanten aktiviert sind, und aktivieren Sie es bei Bedarf. | | [Einrichten von Microsoft Teams in Ihrem Microsoft 365 oder Office 365](office-365-set-up.md) |
| 3  | Konfigurieren von Rollen und Berechtigungen | Teams unterstützen zwei Arten von Rollen: Mitglied und Besitzer. <br/><br/>Nachdem ein Mitglied zu einem Team hinzugefügt wurde, kann ein Besitzer auch ein Mitglied zur Rolle des Besitzers heraufstufen. Als bewährte Methode empfehlen wir, dass jedem Team mindestens zwei Besitzer zugewiesen sind. <br/><br/>Standardmäßig können alle Personen in der Organisation, die über ein auf Exchange Online gehostetes Postfach verfügen, ein Team erstellen. Ein Benutzer, der ein neues Team erstellt, erhält automatisch die Rolle des Besitzers für dieses Team. <br/><br/>Bei Bedarf können Sie die Office 365-Gruppeneinstellungen so konfigurieren, dass nur bestimmte Benutzer neue Teams erstellen können. | | [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365-Gruppen und Microsoft Teams](office-365-groups.md) <br/><br/>[Verwalten von Personen, die Microsoft 365-Gruppen erstellen können](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Konfigurieren von Mandanten weiten Einstellungen für Teams | Sie können einige Teams-Einstellungen auf Mandantenebene konfigurieren. Benutzer, die für Teams aktiviert sind, erben diese Einstellungen aus der Mandanten Konfiguration:<ul><li>Allgemein</li><li>E-Mail-Integration</li><li>Apps</li><li>Benutzerdefinierter Cloudspeicher</li><li>Anrufe und Besprechungen</li><li>Messaging</li></ul>| | [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md) |
| 5  | Optional: Konfigurieren des Gastzugriffs | Sie verwenden Gastzugriff in Teams, um mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem Sie Ihnen Zugriff auf Teams und Kanäle gewähren. Gastzugriff ist eine Einstellung auf Mandantenebene in Teams. Diese Option ist standardmäßig deaktiviert. <br/>Aktivieren Sie den Gastzugriff, und konfigurieren Sie Mandantenweite Gasteinstellungen, wenn Ihre Organisation die Verwendung dieses Features plant. | | [Gastzugriff in Microsoft Teams](guest-access.md) |
| 6  | Optional: Konfigurieren der Benennungsrichtlinie für Teams | Teams nutzt die Namensgebungsrichtlinien für Microsoft 365-Gruppen, wenn Benutzer Team Namen erstellen oder bearbeiten. <br/><br/>Standardmäßig werden keine Namenseinschränkungen angewendet, wenn ein Benutzer ein Team erstellt. <br/><br/>Wenn Sie Regeln für die Namen von Teams erzwingen müssen, konfigurieren Sie die Namensgebungsrichtlinien für Microsoft 365-Gruppen, die für Ihre Organisation gelten. Sie können obligatorische Präfixe und Suffixe festlegen und blockierte Wörter angeben. | | [Planen von Microsoft 365-Gruppen beim Erstellen von Teams in Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Benennungsrichtlinie für Microsoft 365-Gruppen](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Konfigurieren von Exchange für die SMTP-Domäne "Teams" | Teams verwendet Exchange Online zum Senden von Benachrichtigungen an Teammitglieder mithilfe der SMTP-Domäne – Email.Teams.Microsoft.com – Wenn Sie hinzugefügt oder entfernt wurden. <br/><br/>Stellen Sie sicher, dass diese SMTP-Domäne der Liste der akzeptierten Domänen in Ihrer Exchange-Infrastruktur hinzugefügt wird. | | [Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online](smtp-accepted-domain.md) |
| 8  | Konfigurieren und Verwalten des Benutzerzugriffs auf Teams | Obwohl wir dringend empfehlen, alle Benutzer für Teams zu aktivieren, können Sie den Zugriff auf Teams pro Benutzer zulassen oder verbieten, indem Sie die Produktlizenz für Teams zuweisen oder entfernen. | | [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md) |
| 9  | Zuweisen von Lizenzen zu Benutzern | Zuweisen von Lizenzen zu Ihren Benutzern für Funktionen wie Audiokonferenzen, Telefon System und Anrufpläne | | [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](assign-teams-licenses.md)|
| 10 | Optional: Verwenden von PowerShell zum Verwalten von Teams | Sie können anstelle des Microsoft 365 admin Centers PowerShell-Cmdlets verwenden, um die Einstellungen für Teams zu verwalten und zu verwalten. | | [PowerShell für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
