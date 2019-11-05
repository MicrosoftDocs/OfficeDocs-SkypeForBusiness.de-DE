---
title: Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teambesitzer- und Mitgliederrollen sowie Berechtigungen (einschließlich Berechtigungen zum Erstellen von Teams) in Microsoft Teams zuweisen.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56aa75a85544373047b9ef8a888478103cdf1fd1
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968066"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

In Microsoft Teams gibt es zwei Benutzerrollen: **Besitzer** und **Mitglied**. Standardmäßig wird für einen Benutzer, der ein neues Team erstellt, der Besitzer Status gewährt. Darüber hinaus können Besitzer und Mitglieder über Moderatorfunktionen für einen Kanal verfügen (sofern die Moderation eingerichtet wurde). Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden Berechtigungen geerbt.

Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds.


|                                   | Teambesitzer | Teammitglied |
|-----------------------------------|------------|-------------|
|          **Team erstellen**          |    Ja<sup>1</sup>     |     Nein      |
|          **Team verlassen**           |    Ja     |     Ja     |
|  **Teamnamen/Teambeschreibung bearbeiten**   |    Ja     |     Nein      |
|          **Team löschen**          |    Ja     |     Nein      |
|          **Standardkanal hinzufügen**          |    Ja     |    Ja<sup>2</sup>|
| **Bearbeiten des Standardkanal namens/der Beschreibung** |    Ja     |    Ja<sup>2</sup>|
|        **Standardkanal löschen**         |    Ja     |    Ja<sup>2</sup>|
|          ***Privaten Kanal hinzufügen**          |    Ja     |    Ja<sup>2</sup>|
| ***Namen/Beschreibung des privaten Kanals bearbeiten** |    Nein     |    n/v|
|        ***Privaten Kanal löschen**         |    Ja     |    Nein|
|          **Hinzufügen von Mitgliedern**          |  Ja<sup>3</sup>   |     Nein<sup>4</sup>    |
|          **Hinzufügen von Mitgliedern anfordern**          |  Nicht zutreffend   |     Ja<sup>5</sup>     |
|           **Registerkarten hinzufügen**            |    Ja     |    Ja<sup>2</sup>|
|        **Connectors hinzufügen**         |    Ja     |    Ja<sup>2</sup>|
|           **Bots hinzufügen**            |    Ja     |    Ja<sup>2</sup>|

<sup>1</sup> Teambesitzer können Teams erstellen, es sei denn, sie wurden davon ausgeschlossen. [Berechtigungen zum Erstellen von Teams](#permissions-to-create-teams) unten.<br>
<sup>2</sup> ein Besitzer kann diese Elemente auf Teamebene deaktivieren, sodass Mitglieder keinen Zugriff darauf haben.<br>
<sup>3</sup> Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied in den Besitzerstatus höherstufen. Es ist auch möglich, dass ein Besitzer seinen eigenen Status zu einem Mitglied tiefer stuft.<br>
<sup>4</sup> Teammitglieder können andere Mitglieder zu einem öffentlichen Team hinzufügen.<br>
<sup>5</sup> Während ein Teammitglied Mitglieder nicht direkt zu einem privaten Team hinzufügen kann, kann es das Hinzufügen einer anderen Person zu einem Team anfordern, in dem es bereits Mitglied ist. Wenn ein Mitglied das Hinzufügen einer anderen Person zu einem Team anfordert, erhalten Teambesitzer eine Benachrichtigung über eine ausstehende Anforderung, die sie annehmen oder ablehnen können.

* Weitere Informationen zu Berechtigungen für private Kanäle finden Sie unter [private Kanäle in Teams](private-channels.md).

> [!NOTE]
> Besitzer können die Besitzer anderer Mitglieder in der Option " **Teams anzeigen** " erstellen. Ein Team kann maximal 100 Besitzer haben. Wir empfehlen, dass Sie mindestens ein paar Besitzer haben, die Ihnen bei der Verwaltung des Teams helfen. Dadurch werden auch verwaiste Gruppen verhindert, wenn ein einziger Besitzer Ihre Organisation verlässt. Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Moderatoren Funktionen

Zusätzlich zu anderen Funktionen können Teambesitzer und Mitglieder über Moderatorfunktionen für einen Kanal verfügen (sofern die Moderation für ein Team aktiviert ist). Moderatoren können neue Beiträge in einem Kanal starten und Steuern, ob Teammitglieder auf vorhandene Kanal Nachrichten antworten können. Sie können auch steuern, ob Bots und Konnektoren Kanal Nachrichten senden können.

Moderatorfunktionen werden auf Kanalebene zugewiesen. Team Besitzer verfügen standardmäßig über Moderatoren Funktionen. Teammitglieder haben die Moderatorfunktionen standardmäßig deaktiviert, aber ein Teambesitzer kann einem Teammitglied Moderatorfunktionen für einen Kanal zuweisen. Moderatoren in einem Kanal können andere Moderatoren in diesem Kanal hinzufügen und entfernen.

Weitere Informationen zu den Funktionen von Moderatoren finden Sie unter [Einrichten und Verwalten der Kanal Moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Zuweisen einer Benutzerrolle

Wenn Sie eine Benutzerrolle zuweisen möchten, wählen Sie in Teams den Namen des Teams aus, und klicken Sie auf **Weitere Optionen** > **Team verwalten**. Auf der Registerkarte **Mitglieder** können Sie Mitglieder hinzufügen und Besitzer und Moderatoren auswählen (sofern Sie über ausreichende Berechtigungen verfügen). Weitere Informationen finden Sie unter [Ändern von Team Einstellungen in Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).

## <a name="permissions-to-create-teams"></a>Berechtigungen zum Erstellen von Teams

Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigung zum Erstellen von Office 365-Gruppen und damit zum Erstellen eines Teams in Microsoft Teams. Sie können dies genauer steuern und die Erstellung neuer Teams und damit die Erstellung neuer Office 365-Gruppen einschränken, indem Sie die Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Benutzern delegieren. Anweisungen finden Sie unter [Verwalten von Personen, die Office 365-Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Entscheidungspunkt         |Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?         |
| ![Ein Symbol, das die nächsten Schritte darstellt](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Nächste Schritte         |Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann         |
