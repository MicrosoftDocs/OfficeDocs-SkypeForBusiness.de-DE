---
title: Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teambesitzer- und Mitgliederrollen sowie Berechtigungen (einschließlich Berechtigungen zum Erstellen von Teams) in Microsoft Teams zuweisen.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4887cb129242473da46a611c4f873e79384e5e32
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460340"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

In Microsoft-Teams, es gibt zwei Benutzerrollen: **Besitzer** und **Member**. Standardmäßig wird ein neues Team erstellt ein Benutzer den Status eines Besitzers erteilt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden Berechtigungen vererbt.

Die folgende Tabelle zeigt den Unterschied Berechtigungen zwischen einer Besitzer und Mitglied.


|                                   | Teambesitzer | Teammitglied |
|-----------------------------------|------------|-------------|
|          **Team erstellen**          |    Ja,<sup>1</sup>     |     Nein      |
|          **Team verlassen**           |    Ja     |     Ja     |
|  **Teamnamen/Teambeschreibung bearbeiten**   |    Ja     |     Nein      |
|          **Team löschen**          |    Ja     |     Nein      |
|          **Kanal hinzufügen**          |    Ja     |    Ja,<sup>2</sup>|
| **Kanalnamen/Kanalbeschreibung bearbeiten** |    Ja     |    Ja,<sup>2</sup>|
|        **Kanal löschen**         |    Ja     |    Ja,<sup>2</sup>|
|          **Mitglieder hinzufügen**          |  Ja,<sup>3</sup>   |     Nein      |
|           **Registerkarten hinzufügen**            |    Ja     |    Ja,<sup>2</sup>|
|        **Connectors hinzufügen**         |    Ja     |    Ja,<sup>2</sup>|
|           **Bots hinzufügen**            |    Ja     |    Ja,<sup>2</sup>|

<sup>1</sup> Team Besitzer können Teams erstellen, es sei denn, sie haben aus auf diese Weise eingeschränkt wurde. Siehe "Berechtigungen zum Erstellen von Teams" weiter unten.
>
<sup>2</sup> dieser Elemente können mithilfe eines Besitzers auf einer Teamebene deaktiviert werden in diesem Fall würde die Mitglieder nicht darauf zugreifen können.

<sup>3</sup> nach dem Hinzufügen eines Elements zu einem Team, kann ein Besitzers auch Mitglied, um den Status eines Besitzers heraufgestuft werden. Es ist außerdem möglich, dass Besitzer zu stufende Websites ihren eigenen Status auf einen Member.



> [!NOTE]
> Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen. Ein Team kann maximal 100 Besitzer haben. Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt. Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Berechtigungen zum Erstellen von Teams
---------------------------

Standardmäßig haben alle Benutzer mit einem Postfach in Exchange Online Berechtigungen zum Erstellen von Office 365-Gruppen und daher ein Team in Microsoft-Teams. Sie können haben eine genauere Kontrolle und die Erstellung des neuen Teams und somit die Erstellung des neuen Office 365-Gruppen nach Gruppe erstellen und Verwaltungsrechte an eine Gruppe von Benutzern delegieren einschränken. Anweisungen finden Sie unter [verwalten, die Office 365 Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Entscheidungspunktsymbol](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Entscheidungspunkt         |Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?         |
| ![Symbol für „Nächste Schritte“](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Nächste Schritte         |Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann         |
