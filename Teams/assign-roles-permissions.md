---
title: Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
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
ms.openlocfilehash: 9bcc0db65555d367f3af139be22e37690248b8e0
ms.sourcegitcommit: 4fb1c691f0f84d47e215c9c1775da9bdba875f61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "35253703"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

In Microsoft Teams gibt es zwei Benutzerrollen: **Besitzer** und **Mitglied**. Standardmäßig wird für einen Benutzer, der ein neues Team erstellt, der Besitzer Status gewährt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden Berechtigungen geerbt.

Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds.


|                                   | Teambesitzer | Teammitglied |
|-----------------------------------|------------|-------------|
|          **Team erstellen**          |    Ja<sup>1</sup>     |     Nein      |
|          **Team verlassen**           |    Ja     |     Ja     |
|  **Teamnamen/Teambeschreibung bearbeiten**   |    Ja     |     Nein      |
|          **Team löschen**          |    Ja     |     Nein      |
|          **Kanal hinzufügen**          |    Ja     |    Ja<sup>2</sup>|
| **Kanalnamen/Kanalbeschreibung bearbeiten** |    Ja     |    Ja<sup>2</sup>|
|        **Delete channel**         |    Ja     |    Ja<sup>2</sup>|
|          **Hinzufügen von Mitgliedern**          |  Ja<sup>3</sup>   |     Nein<sup>4</sup>    |
|          **Hinzufügen von Mitgliedern anfordern**          |  Nicht zutreffend   |     Ja<sup>5</sup>     |
|           **Registerkarten hinzufügen**            |    Ja     |    Ja<sup>2</sup>|
|        **Connectors hinzufügen**         |    Ja     |    Ja<sup>2</sup>|
|           **Bots hinzufügen**            |    Ja     |    Ja<sup>2</sup>|

<sup>1</sup> Teambesitzer können Teams erstellen, es sei denn, sie wurden davon ausgeschlossen. Weitere Informationen finden Sie unter [Berechtigungen zum Erstellen von Teams](#permissions-to-create-teams) .<br>
<sup>2</sup> Diese Elemente können von einem Besitzer auf Teamebene deaktiviert werden. In diesem Fall können Mitglieder nicht darauf zugreifen.<br>
<sup>3</sup> Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied in den Besitzerstatus höherstufen. Es ist auch möglich, dass ein Besitzer seinen eigenen Status zu einem Mitglied tiefer stuft.<br>
<sup>4</sup> Teammitglieder können andere Mitglieder zu einem öffentlichen Team hinzufügen.<br>
<sup>5</sup> Während ein Teammitglied Mitglieder nicht direkt zu einem privaten Team hinzufügen kann, kann es das Hinzufügen einer anderen Person zu einem Team anfordern, in dem es bereits Mitglied ist. Wenn ein Mitglied das Hinzufügen einer anderen Person zu einem Team anfordert, erhalten Teambesitzer eine Benachrichtigung über eine ausstehende Anforderung, die sie annehmen oder ablehnen können.

> [!NOTE]
> Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen. Ein Team kann maximal 100 Besitzer haben. Es wird empfohlen, mindestens ein paar Besitzer zur Verfügung zu haben, um das Team zu verwalten. Dadurch werden auch verwaiste Gruppen verhindert, wenn der einzige Besitzer Ihre Organisation verlässt. Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

<a name="permissions-to-create-teams"></a>Berechtigungen zum Erstellen von Teams
---------------------------

Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigung zum Erstellen von Office 365-Gruppen und damit zum Erstellen eines Teams in Microsoft Teams. Sie können dies genauer steuern und die Erstellung neuer Teams und damit die Erstellung neuer Office 365-Gruppen einschränken, indem Sie die Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Benutzern delegieren. Anweisungen finden Sie unter [Verwalten von Personen, die Office 365-Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Entscheidungspunkt         |Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?         |
| ![Ein Symbol, das die nächsten Schritte darstellt](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Nächste Schritte         |Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann         |
