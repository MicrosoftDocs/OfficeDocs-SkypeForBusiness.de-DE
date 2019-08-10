---
title: Verwalten von Teams im Admin Center für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Hier erfahren Sie, wie Sie Ihre Teams im Microsoft Teams Admin Center anzeigen oder aktualisieren.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b8937827cb5e3fa80e9ebae93d9958be2cf0f38
ms.sourcegitcommit: 8a8c71aea5bd2420b110619607ef0715136578ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2019
ms.locfileid: "36286233"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Verwalten von Teams im Admin Center für Microsoft Teams
==========================================

## <a name="overview"></a>Übersicht

Als Administrator müssen Sie möglicherweise die Teams anzeigen oder aktualisieren, die Ihre Organisation für die Zusammenarbeit eingerichtet hat, oder Sie müssen möglicherweise Behebungsaktionen wie das Zuweisen von Besitzern für besitzerlos ausgeführte Teams ausführen. Sie können die in Ihrer Organisation verwendeten Teams sowohl über das PowerShell-Modul von Microsoft Teams als auch über das Microsoft Teams Admin Center verwalten. Wenn Sie die vollständigen Verwaltungsfunktionen mithilfe dieser beiden Toolsets verwenden möchten, müssen Sie sicherstellen, dass Ihnen eine der folgenden Rollen zugewiesen ist:

- Globaler Administrator
- Teams-Dienstadministrator

Weitere Informationen zu Administratorrollen in Teams finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md), und Sie können weitere Informationen zur Verwendung der PowerShell-Cmdlets für die Verwaltung von Teams in der [Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)finden.

Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams im Microsoft Teams Admin Center.

## <a name="teams-overview-grid"></a>Übersicht über Teams

Verwaltungstools für Teams befinden sich im Microsoft Teams Admin Center unter dem Knoten **Teams** . (Wählen Sie im Admin Center **Teams** > **Manage Teams**aus.) Jedes Team wird von einer Office 365-Gruppe unterstützt, und dieser Knoten bietet eine Ansicht von Gruppen, die in Ihrer Organisation in Microsoft Teams aktiviert wurden.

![Screenshot des Rasters ' Teams-Übersicht '](media/manage-teams-in-modern-portal-grid.png)  

Im Raster werden die folgenden Eigenschaften angezeigt:

- **Teamname**
- **Kanäle** – die Anzahl aller Kanäle im Team, einschließlich des Standard Kanals für allgemein.
- **Team Mitglieder** – eine Anzahl von Gesamt Benutzern, einschließlich Besitzern, Gästen und Mitgliedern Ihres Mandanten.
- **Besitzer** – eine Anzahl von Besitzern für dieses Team.
- **Gäste** – eine Anzahl von Azure Active Directory-Gastbenutzern, die Mitglieder dieses Teams sind.
- **Datenschutz** – die Sichtbarkeit/der Zugriff auf die Gruppe "Backing Office 365".
- **Status** – der archivierte oder aktive Status für dieses Team. Weitere Informationen zum Archivieren von Teams finden Sie unter [archivieren oder Wiederherstellen eines](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)Teams.
- **Beschreibung** – die Beschreibung der Gruppe "Backing Office 365".
- **Klassifizierung** : die Klassifizierung (falls in Ihrer Organisation verwendet), die der Gruppe "Backing Office 365" zugewiesen ist. Weitere Informationen zu Klassifizierungen finden Sie unter [Erstellen von Klassifizierungen für Office-Gruppen in Ihrer Organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **Gruppen** -Nr – die eindeutige Gruppen-Nr der Sicherungs-Office 365-Gruppe.

> [!NOTE]
> Wenn nicht alle diese Eigenschaften im Raster angezeigt werden, klicken Sie auf das Symbol **Spalten bearbeiten** . Im Bereich **Spalten bearbeiten** können Sie die Umschalter verwenden, um Spalten im Raster zu aktivieren oder zu deaktivieren. Wenn Sie fertig sind, klicken Sie auf über **nehmen**.

### <a name="add"></a>Hinzufügen

Wenn Sie ein neues Team hinzufügen möchten, klicken Sie auf **Hinzufügen**. Geben Sie im Bereich **Neues Team hinzufügen** dem Team einen Namen und eine Beschreibung, legen Sie fest, ob es sich um ein privates oder öffentliches Team machen soll, und legen Sie die Klassifizierung fest.

### <a name="edit"></a>Bearbeiten

Wenn Sie Gruppen-und Team spezifische Einstellungen bearbeiten möchten, wählen Sie das Team aus, indem Sie links neben dem Teamnamen klicken, und wählen Sie dann **Bearbeiten**aus.

### <a name="archive"></a>Archiv

Sie können ein Team archivieren. Durch die Archivierung eines Teams wird das Team in Teams in den schreibgeschützten Modus versetzt. Als Administrator können Sie Teams im Namen Ihrer Organisation im Admin Center archivieren und aufteilen. 

### <a name="delete"></a>Löschen

Das Löschen eines Teams ist ein Soft-Delete des Teams und der entsprechenden Office 365-Gruppe. Wenn Sie ein versehentlich gelöschtes Team wiederherstellen möchten, folgen Sie den Anweisungen unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).

### <a name="search"></a>Suche

Die Suche unterstützt derzeit die Zeichenfolge "beginnt mit" **** und durchsucht das Feld Teamname.

## <a name="team-profile"></a>Team Profil

Durch Klicken auf den Teamnamen können Sie zur Seite "Teamprofil" eines beliebigen Teams aus dem Hauptübersicht-Raster "Teams" navigieren. Auf der Seite "Teamprofil" werden die Mitglieder, Besitzer und Gäste angezeigt, die zum Team gehören (und die Gruppe "Backing Office 365") sowie die Kanäle und Einstellungen des Teams. Auf der Seite Teamprofil können Sie Folgendes ausführen:

- Mitglieder und Besitzer hinzufügen oder entfernen.
- Hinzufügen oder Entfernen von Kanälen (Beachten Sie, dass Sie den Kanal "Allgemein" nicht entfernen können).
- Ändern Sie die Team-und Gruppeneinstellungen.
 
![Screenshot eines Beispiel Team Profils](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Vornehmen von Änderungen an Teams

Auf der Profilseite des Teams können Sie die folgenden Elemente eines Teams ändern:

- **Mitglieder** – Mitglieder hinzufügen oder entfernen sowie Besitzer höher-oder tiefer stufen.
- **Kanäle** – fügen Sie neue Kanäle hinzu, und bearbeiten oder entfernen Sie vorhandene Kanäle. Beachten Sie, dass Sie den standardmäßigen allgemeinen Kanal nicht löschen können.
- **Teamname**
- **Beschreibung**
- **Privatsphäre** – legen Sie fest, ob das Team öffentlich oder privat ist.
- **Klassifizierung** – Dies wird durch Ihre Office 365-Gruppen Klassifizierungen unter sichert. Wählen Sie **vertraulich**, **hoch vertraulich**oder **Allgemein**aus.
- **Konversations Einstellungen** – legen Sie fest, ob Mitglieder gesendete Nachrichten bearbeiten und löschen können.
- **Kanaleinstellungen** – legen Sie fest, ob Mitglieder neue Kanäle erstellen und vorhandene bearbeiten sowie Tabstopps, Connectors und apps hinzufügen, bearbeiten und entfernen können.

Die Änderungen, die Sie an einem Team vornehmen, werden protokolliert. Wenn Sie Gruppeneinstellungen ändern (Name, Beschreibung, Foto, Datenschutz, Klassifikation oder Teammitglieder ändern), werden Ihnen die Änderungen über die Überwachungs Pipeline zugeschrieben. Wenn Sie Aktionen für Teams-spezifische Einstellungen durchführen, werden Ihre Änderungen nachverfolgt und Ihnen im allgemeinen Kanal des Teams zugeordnet.

## <a name="troubleshooting"></a>Problembehandlung

**Problem: fehlende Teams im Team Übersicht-Raster**

Einige ihrer Teams fehlen in der Liste der Teams im Team Übersicht-Raster.

**Ursache**: dieses Problem tritt auf, wenn das Team fälschlicherweise (oder noch nicht) vom System profiliert wurde, was zu einer fehlenden Eigenschaft führen kann, damit es erkannt wird.

**Lösung: Manuelles Festlegen der Eigenschaft auf den richtigen Wert über MS Graph**

Ersetzen Sie **{Gruppen** -Nr} in der Abfrage für die eigentliche fragliche Gruppen-Nr, die Sie über die Exchange Online-PowerShell mit dem Cmdlet **"[Get-Unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** als "**ExternalDirectoryObjectId**"-Attribut abrufen können.

1. Access- [Diagramm-Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer).

2. Anmelden beim Diagramm-Explorer im linken Menü

3. Ändern Sie die Abfragezeile in: Patch #a0 v 1.0 https://graph.microsoft.com/v1.0/groups/{groupid}#a1.

4. Fügen Sie im Anforderungstext den folgenden Wert hinzu: {"resourceProvisioningOptions": ["Team"]}.

5. Führen Sie die Abfrage oben rechts aus.

6. Bestätigen Sie, dass das Team im Microsoft Teams Admin Center-Team Übersicht richtig angezeigt wird.

## <a name="learn-more"></a>Weitere Informationen

- [Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [Verwenden von Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md)
- [Planen der Lebenszyklusverwaltung in Microsoft Teams](plan-teams-lifecycle.md)
