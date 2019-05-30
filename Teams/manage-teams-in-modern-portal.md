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
description: Hier erfahren Sie, wie Sie Ihre Teams im Microsoft Teams Admin Center anzeigen oder aktualisieren.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548270"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Verwalten von Teams im Admin Center für Microsoft Teams
==========================================


## <a name="overview"></a>Übersicht

Als IT-Administrator müssen Sie möglicherweise die Teams anzeigen oder aktualisieren, die Ihre Organisation für die Zusammenarbeit eingerichtet hat, oder Sie müssen möglicherweise Behebungsaktionen wie das Zuweisen von Besitzern für besitzerlos ausgeführte Teams ausführen. Sie können die in Ihrer Organisation verwendeten Teams sowohl über das PowerShell-Modul von Microsoft Teams als auch über das Microsoft Teams Admin Center verwalten. Wenn Sie die vollständigen Verwaltungsfunktionen mithilfe dieser beiden Toolsets verwenden möchten, müssen Sie sicherstellen, dass Ihnen eine der folgenden Rollen zugewiesen ist:

- Globaler Administrator
- Teams-Dienstadministrator

Weitere Informationen zu Administratorrollen in Teams finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md), und Sie können weitere Informationen zur Verwendung der PowerShell-Cmdlets für die Verwaltung von Teams in der [Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)finden.  

Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams im Microsoft Teams Admin Center.

## <a name="teams-overview-grid"></a>Übersicht über Teams

Verwaltungstools für Teams befinden sich im Microsoft Teams Admin Center unter dem Knoten **Teams** . (Wählen Sie im Admin Center **Teams** > **Manage Teams**aus.) Jedes Team wird von einer Office 365-Gruppe unterstützt, und dieser Knoten bietet eine Ansicht von Gruppen, die in Ihrer Organisation in Microsoft Teams aktiviert wurden.

![Screenshot des Rasters ' Teams-Übersicht '](media/manage-teams-in-modern-portal-image1.png)  

Im Raster werden die folgenden Eigenschaften angezeigt:

- **Teamname**
- **Kanäle** – die Anzahl aller Kanäle im Team, einschließlich des Standard Kanals für allgemein.
- **Benutzer** – die Anzahl der Gesamtbenutzer, einschließlich Besitzern, Gästen und Mitgliedern Ihres Mandanten.
- **Besitzer** – eine Anzahl von Besitzern für dieses Team.
- **Gäste** – eine Anzahl von Azure Active Directory-Gastbenutzern, die Mitglieder dieses Teams sind.
- **Datenschutz** – die Sichtbarkeit/der Zugriff auf die Gruppe "Backing Office 365".
- **Status** – der archivierte oder aktive Status für dieses Team.  Weitere Informationen finden Sie unter Archivieren von Teams [oder Wiederherstellen eines](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)Teams.
- **Gruppen** -Nr – die eindeutige Gruppen-Nr der Backing Office 365-Gruppe
- **Klassifizierung** : die Klassifizierung (falls in Ihrer Organisation verwendet), die der Gruppe "Backing Office 365" zugewiesen ist.  Weitere Informationen zu Klassifizierungen finden Sie unter [Erstellen von Klassifizierungen für Office-Gruppen in Ihrer Organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **Beschreibung** – die Beschreibung für die Backing Office 365-Gruppe

### <a name="search"></a>Suche

Die Suche unterstützt derzeit die Zeichenfolge "beginnt mit" **** und durchsucht das Feld Teamname.

### <a name="edit"></a>Bearbeiten

Sie können Gruppen-und Team spezifische Einstellungen bearbeiten, indem Sie ein Team aus dem Raster auswählen und dann die Schaltfläche " **Bearbeiten** " auswählen.

![Screenshot der Optionen für "Team bearbeiten"](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Team Profil

Durch Klicken auf den Teamnamen können Sie zur Seite "Teamprofil" eines beliebigen Teams aus dem Hauptübersicht-Raster "Teams" navigieren. Auf der Seite Teamprofil werden die Mitglieder, Besitzer und Gäste angezeigt, die dem Team (und der zugehörigen Office 365-Gruppe) sowie den Kanälen und Einstellungen des Teams angehören. Auf der Seite Teamprofil können Sie Folgendes ausführen:

- Mitglieder und Besitzer hinzufügen oder entfernen.
- Hinzufügen oder Entfernen von Kanälen (Beachten Sie, dass Sie den Kanal "Allgemein" nicht entfernen können).
- Aktualisieren Sie die Team-und Gruppeneinstellungen.
 
![Screenshot eines Beispiel Team Profils](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Vornehmen von Änderungen an Teams

Sie können die folgenden Elemente eines Teams ändern:
- **Benutzer im Team** – Sie können Mitglieder hinzufügen oder entfernen sowie Besitzer herauf-oder herunterstufen.
- **Kanäle** – Sie können neue Kanäle hinzufügen oder vorhandene Kanäle entfernen.  Sie können den Standardkanal "Allgemein" nicht löschen, und nach der Erstellung können Sie nur den Kanalnamen, nicht die Beschreibung, bearbeiten.
- **Teamname**
- **Team Beschreibung**
- **Team Datenschutz** – öffentlich oder privat
- **Team Klassifizierung** – unter dem Namen Ihrer Office 365-Gruppen Klassifizierungen
- **Einstellungen für Teammitglieder** – wählen Sie die Einstellungen für Teammitglieder aus.

## <a name="other-supported-changes-to-teams"></a>Weitere unterstützte Änderungen an Teams

- **Löschen** – das Löschen eines Teams ist ein Soft-Delete des Teams und der entsprechenden Office 365-Gruppe.  Wenn Sie ein versehentlich gelöschtes Team wiederherstellen möchten, folgen Sie den Anweisungen unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).
- **Archiv** -Archivierung ein Team versetzt das Team in Microsoft Teams in den schreibgeschützten Modus.  Als Administrator können Sie Teams im Namen Ihrer Organisation über das Administratorportal archivieren und aufteilen.


Die Änderungen, die Sie an einem Team vornehmen, werden protokolliert. Wenn Sie Gruppeneinstellungen ändern (Name, Beschreibung, Foto, Datenschutz, Klassifikation oder Teammitglieder ändern), werden Ihnen diese Änderungen über die Audit-Pipeline zugeschrieben. Wenn Sie Aktionen für Teams-spezifische Einstellungen durchführen, werden Ihre Änderungen nachverfolgt und Ihnen im allgemeinen Kanal des Teams zugeordnet.

## <a name="troubleshooting"></a>Problembehandlung

**Problem: fehlende Teams im Team Übersicht-Raster**

Wenn Sie das Microsoft Teams Admin Center aufrufen, fehlen einige ihrer Teams unter der Option **Teams** in der Liste im Team Übersicht-Raster.

**Ursache**: dieses Problem tritt auf, wenn das Team fälschlicherweise (oder noch nicht) vom System profiliert wurde, was zu einer fehlenden Eigenschaft führen kann, damit es erkannt wird.

**Lösung: Manuelles Festlegen der Eigenschaft auf den richtigen Wert über MS Graph**

Ersetzen Sie **{Gruppen** -Nr} in der Abfrage für die eigentliche fragliche Gruppen-Nr, die Sie über die Exchange Online-PowerShell mit dem Cmdlet **"[Get-Unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** als "**ExternalDirectoryObjectId**"-Attribut abrufen können.

1. Access- [Diagramm-Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. Anmelden beim Diagramm-Explorer im linken Menü

3. Ändern Sie die Abfragezeile in: Patch > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. Fügen Sie den folgenden Wert für den Anforderungstext hinzu: {"resourceProvisioningOptions": ["Team"]}

5. Führen Sie die Abfrage oben rechts aus.

6. Bestätigen, dass das Team im Microsoft Teams Admin Center richtig angezeigt wird – Team Übersicht


## <a name="learn-more"></a>Weitere Informationen

[Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Administratorrollen in Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

