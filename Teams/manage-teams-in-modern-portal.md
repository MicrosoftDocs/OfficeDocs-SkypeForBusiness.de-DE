---
title: Verwalten von Teams im Admin Center für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Informationen Sie zum Anzeigen oder aktualisieren Ihren Teams bei der in der Verwaltungskonsole von Microsoft-Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202740"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Verwalten von Teams im Admin Center für Microsoft Teams
==========================================


## <a name="overview"></a>Übersicht

Als IT-Administrator müssen Sie anzeigen oder Aktualisieren der Teams, die Ihre Organisation für die Zusammenarbeit, oder Sie eingerichtet wurde möglicherweise Remediation-Aktionen wie dem Zuweisen der Besitzer für eigentümerloser Teams ausführen müssen. Sie können die in Ihrer Organisation über die Microsoft-Teams PowerShell-Modul und das Microsoft-Teams, Administrationscenter verwendeten Teams verwalten. Für vollständige Administration diese zwei Toolsets verwenden sollten Sie sicherstellen, dass Sie eine der folgenden Rollen zugewiesen werden:

- Globaler Administrator
- Teams-Dienstadministrator

Weitere Informationen finden Sie Informationen zu Administratorrollen Teams in [Administratorrollen für Microsoft-Teams, verwenden Sie zum Verwalten von Teams](using-admin-roles.md), und Lesen Sie dazu, wie Sie die PowerShell-Cmdlets zum Verwalten von Teams in der [Microsoft-Teams, Cmdlet-Referenz zu](https://docs.microsoft.com/powershell/teams/?view=teams-ps)verwenden.  

Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams in der Verwaltungskonsole von Microsoft-Teams.

## <a name="teams-overview-grid"></a>Teams Übersichtsraster

Verwaltungstools für Teams sind unter dem Knoten **Teams** in der Verwaltungskonsole von Microsoft-Teams. (Wählen Sie in der Verwaltungskonsole **Teams** > **Verwalten Teams**.) Jedes Team wird von einer Office 365-Gruppe, und dieser Knoten bietet einen Überblick über die Gruppen, die Microsoft-Teams in Ihrer Organisation aktiviert wurden.

![Teams Übersichtsraster](media/manage-teams-in-modern-portal-image1.png)  

Das Raster zeigt die folgenden Eigenschaften:

- **Teamname**
- **Kanäle** - Anzahl alle Kanäle in Teams, einschließlich des allgemeinen Standard-Kanals.
- **Benutzer** : Anzahl der Benutzer insgesamt, einschließlich Besitzer, Gäste und Mitglieder von Ihrem Mandanten.
- **Besitzer** - Anzahl der Besitzer für dieses Team.
- **Gäste** - Anzahl von Azure Active Directory B2B Gastbenutzern, die Mitglieder dieser Gruppe sind.
- **Private** - die Sichtbarkeit/AccessType der Gruppe der unterstützenden Office 365.
- **Status** – die archiviert oder den Status "aktiv" für dieses Team.  Weitere Informationen zur Archivierung von Teams in der [Archivierung oder Wiederherstellung ein Team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **GroupID** - die eindeutige GroupID der Gruppe der unterstützenden Office 365
- **Klassifizierung** - Klassifizierung (Wenn in Ihrer Organisation verwendet wird) Sicherung Office 365-Gruppe zugewiesen.  Erfahren Sie mehr über Klassifikationen unter [Klassifikationen für Office-Gruppen in Ihrer Organisation zu erstellen](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **Beschreibung** : die Beschreibung für die Sicherung Office 365-Gruppe festlegen

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
- **Team Privacy** - öffentliche oder private
- **Team Klassifizierung** -, die auf Ihrer Office 365 Gruppe Klassifikationen
- **Einstellungen für Team Members** - select Team Member Einstellungen

## <a name="other-supported-changes-to-teams"></a>Andere unterstützten Änderungen an teams

- **Löschen** : Löschen ein Team ist eine Soft-Löschung des Teams und der entsprechenden Office 365-Gruppe.  Um eine versehentlich gelöschte Team wiederherzustellen, befolgen Sie die Anweisungen unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).
- **Archiv** - Archivierung ein Team versetzt das Team in den schreibgeschützten Modus innerhalb von Microsoft-Teams.  Sie können als Administrator archivieren und entpackt Teams im Namen Ihrer Organisation über die Administratorportal.


Die Änderungen, die Sie ein Team stellen angemeldet sind. Wenn Sie Clientgruppen (Ändern der Name, Beschreibung, Foto, private, Klassifizierung oder Teammitglieder) ändern, werden diese Änderungen an Sie über die Pipeline Audit Ergebnisarray als Attribut zugewiesen werden. Falls Sie Aktionen für Teams-spezifischen Einstellungen ausführen, werden die Änderungen nachverfolgt und Ergebnisarray als Attribut zugewiesen, die Sie im Allgemeinen Kanal des Teams.

## <a name="troubleshooting"></a>Problembehandlung

**Problem: Teams fehlende aus dem Team Übersichtsraster**

Wenn Sie das Microsoft-Teams, Administrationscenter eingeben, fehlen unter der Option **Teams** einige Ihrer Teams aus der Liste im Raster Übersicht Teams.

**Ursache**: Dieses Problem tritt auf, wenn das Team falsch (oder noch nicht) vom System ein Profil erstellt wurde die eine fehlende-Eigenschaft erkannt werden führen können.

**Lösung: Legen Sie die-Eigenschaft manuell auf den richtigen Wert über MS Graph**

Ersetzen Sie mit dem Cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** **{Groupid}** in der Abfrage für die tatsächliche GroupId bezieht, die Sie über die Exchange Online Powershell abrufen können, wie das Attribut "**ExternalDirectoryObjectId**".

1. Access- [Diagramm-Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. Melden Sie sich bei Diagramm Explorer im linken Menü auf

3. Ändern der Abfragezeile an: PATCH > v1. 0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. Fügen Sie den folgenden Wert auf den Text der Anforderung: {"ResourceProvisioningOptions": ["Team"]}

5. Führen Sie die Abfrage, auf der oberen rechten.

6. Bestätigen Sie, dass das Team in der Verwaltungskonsole von Microsoft-Teams - ordnungsgemäß angezeigt Team (Übersicht)


## <a name="learn-more"></a>Weitere Informationen

[Cmdlet-Referenz zu Microsoft-Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Administratorrollen in Microsoft-Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

