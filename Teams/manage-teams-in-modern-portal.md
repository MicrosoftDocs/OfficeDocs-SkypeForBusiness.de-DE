---
title: Verwalten von Teams in der Microsoft-Teams & Skype für Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Informationen Sie zum Anzeigen oder aktualisieren Ihren Teams im Microsoft-Teams & Skype für Business Admin Center.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8d517ce7f2fb614a22c45fcf63d59a7d46b606f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295023"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>Verwalten von Teams in der Microsoft-Teams & Skype für Business Admin Center
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>Übersicht

Als IT-Administrator müssen Sie anzeigen oder Aktualisieren der Teams, die Ihre Organisation für die Zusammenarbeit, oder Sie eingerichtet wurde möglicherweise Remediation-Aktionen wie dem Zuweisen der Besitzer für eigentümerloser Teams ausführen müssen. Sie können die in Ihrer Organisation über die Microsoft-Teams PowerShell-Modul und an den Microsoft-Teams & die Skype für Business Admin Center verwendeten Teams verwalten. Für vollständige Administration diese zwei Toolsets verwenden sollten Sie sicherstellen, dass Sie eine der folgenden Rollen zugewiesen werden:

- Globaler Administrator
- Teams-Dienstadministrator

Weitere Informationen finden Sie Informationen zu Administratorrollen in Microsoft-Teams, [hier](using-admin-roles.md)und weitere zur Verwendung der PowerShell-Cmdlets zum Verwalten von Teams in der [Microsoft-Teams, Cmdlet-Referenz](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).  

Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams in der Microsoft-Teams & Skype für Business Admin Center.

## <a name="teams-overview-grid"></a>Teams Übersichtsraster

Verwaltungstools für Teams sind unter dem Knoten **Teams** im Microsoft-Teams & Skype für Business Admin Center. (Wählen Sie in der Verwaltungskonsole **Teams** > **Verwalten Teams**.) Jedes Team wird von einer Office 365-Gruppe, und dieser Knoten bietet eine Übersicht über alle Gruppen, die Microsoft-Teams in Ihrer Organisation aktiviert wurden.

![Teams Übersichtsraster](media/manage-teams-in-modern-portal-image1.png)  

Das Raster zeigt die folgenden Eigenschaften:

- **Teamname**
- **Kanäle** - Anzahl alle Kanäle in Teams, einschließlich des allgemeinen Standard-Kanals.
- **Benutzer** : Anzahl der Benutzer insgesamt, einschließlich Besitzer, Gäste und Mitglieder von Ihrem Mandanten.
- **Besitzer** - Anzahl der Besitzer für dieses Team.
- **Gäste** - Anzahl von Azure Active Directory B2B Gastbenutzern, die Mitglieder dieser Gruppe sind.
- **Private** - die AccessType der Gruppe der unterstützenden Office 365.

### <a name="search"></a>Suche

Suche derzeit unterstützt die Zeichenfolge "Beginnt mit" und das Feld **Teamname** durchsucht.

### <a name="edit"></a>Bearbeiten

Sie können Gruppe und Team-spezifischen Einstellungen bearbeiten, indem Sie ein Team aus dem Raster auswählen auswählen und dann auf die Schaltfläche **Bearbeiten** .

![Team bearbeiten](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Team-Profil

Sie können der Profilseite Team von jedem Team aus dem Hauptfenster Teams Übersichtsraster, indem Sie auf den Teamnamen navigieren. Die Team Profilseite zeigt die Mitglieder, Besitzer und Gäste, die an das Team gehören (und dessen sichern O365 Gruppe), sowie des Teams Kanäle und Einstellungen. Auf der Profilseite Team können Sie folgende Aktionen ausführen:

- Hinzufügen oder Entfernen von Mitgliedern und Besitzern.
- Hinzufügen oder Entfernen von Kanäle (Beachten Sie, dass den allgemeinen Channel nicht entfernt werden können).
- Aktualisieren von Teams und -Einstellungen.
 
![Team-Profil](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Das Ändern von teams

Sie können die folgenden Elemente eines Teams ändern:
- **Benutzer im Team** : Sie können hinzufügen oder Entfernen von Mitgliedern, und herauf- oder herabstufen Besitzer
- **Kanäle** : Sie können neue Kanäle hinzufügen oder Entfernen von vorhandenen Kanäle.  Sie den Standardwert "Allgemein" DDE-Kanal kann nicht gelöscht werden, und Sie nach der Erstellung Channel Name, nicht Beschreibung kann nur bearbeiten.
- **Teamname**
- **Team Beschreibung**
- **Team Foto**
- **Team Privacy** - öffentliche oder private
- **Team Klassifizierung** -, die auf Ihrer Office 365 Gruppe Klassifikationen
- **Einstellungen für Team Members** - select Team Member Einstellungen


Die Änderungen, die Sie ein Team stellen angemeldet sind. Wenn Sie Clientgruppen (Ändern der Name, Beschreibung, Foto, private, Klassifizierung oder Teammitglieder) ändern, werden diese Änderungen an Sie über die Pipeline Audit Ergebnisarray als Attribut zugewiesen werden. Falls Sie Aktionen für Teams-spezifischen Einstellungen ausführen, werden die Änderungen nachverfolgt und Ergebnisarray als Attribut zugewiesen, die Sie im Allgemeinen Kanal des Teams.


## <a name="learn-more"></a>Weitere Informationen

[Cmdlet-Referenz zu Microsoft-Teams](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[Administratorrollen in Microsoft-Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

