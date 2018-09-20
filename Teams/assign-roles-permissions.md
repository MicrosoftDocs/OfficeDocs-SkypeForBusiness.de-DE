---
title: Weisen Sie Team-Besitzer und Membern im Microsoft-Teams
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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2fd9f611d616f368973ced432e886bf4ba9d8f5
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021810"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Weisen Sie Team-Besitzer und Membern im Microsoft-Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

In Microsoft-Teams, es gibt zwei Benutzerrollen: **Besitzer** und **Member**. Standardmäßig wird ein neues Team erstellt ein Benutzer den Status eines Besitzers erteilt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden Berechtigungen vererbt.

Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds:

|  |Teambesitzer  |Teammitglied  |
|---------|---------|---------|
|**Team erstellen**     |Ja        |Nein         |
|**Team verlassen**     |Ja         |Ja         |
|**Teamnamen/Teambeschreibung bearbeiten**      |Ja         |Nein         |
|**Team löschen**      |Ja         |Nein         |
|**Kanal hinzufügen**      |Ja         |Ja*         |
|**Kanalnamen/Kanalbeschreibung bearbeiten**      |Ja         |Ja*         |
|**Kanal löschen**      |Ja         |Ja*         |
|**Mitglieder hinzufügen**      |Ja**         |Nein         |
|**Registerkarten hinzufügen**      |Ja         |Ja*         |
|**Connectors hinzufügen**      |Ja         |Ja*         |
|**Bots hinzufügen**      |Ja         |Ja*         |
\*Diese Elemente können mithilfe eines Besitzers auf einer Teamebene deaktiviert werden in diesem Fall würde die Mitglieder nicht darauf zugreifen können.

\*\*Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied zum Status eines Besitzers hochstufen. Ein Besitzer kann auch seinen eigenen Status zu dem eines Mitglieds herabstufen.



> [!NOTE]
> Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen. Ein Team kann maximal 100 Besitzer haben. Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt. Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Berechtigungen zum Erstellen von Teams
---------------------------

Standardmäßig haben alle Benutzer mit einem Postfach in Exchange Online Berechtigungen zum Erstellen von Office 365-Gruppen und daher ein Team in Microsoft-Teams. Sie können haben eine genauere Kontrolle und die Erstellung des neuen Teams und somit die Erstellung des neuen Office 365-Gruppen nach Gruppe erstellen und Verwaltungsrechte an eine Gruppe von Benutzern delegieren einschränken. Anweisungen finden Sie unter [verwalten, die Office 365 Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Entscheidungspunktsymbol](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Entscheidungspunkt         |Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?         |
| ![Symbol für „Nächste Schritte“](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Nächste Schritte         |Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann         |
