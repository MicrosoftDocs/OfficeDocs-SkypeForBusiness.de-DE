---
title: Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teambesitzer- und Mitgliederrollen sowie Berechtigungen (einschließlich Berechtigungen zum Erstellen von Teams) in Microsoft Teams zuweisen.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 666a623f955cd10fd4ad3e0983ccff83c9725a6b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586731"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams"></a>Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams

In Microsoft Teams gibt es zwei Benutzerrollen: **Besitzer** und **Mitglied**. Standardmäßig wird einem Benutzer, der ein neues Team erstellt, der Status "Besitzer" zugewiesen. Besitzern und Mitgliedern können außerdem Moderatorfunktionen für einen bestimmten Kanal zugeordnet werden (sofern die Moderation eingerichtet wurde). Wenn ein Team aus einer bestehenden Microsoft 365-Gruppe erstellt wird, werden die entsprechenden Berechtigungen vererbt.

Die folgende Tabelle zeigt den Unterschied zwischen den Berechtigungen eines Besitzers und eines Mitglieds.


|    Aufgabe                               | Teambesitzer | Teammitglied |
|-----------------------------------|------------|-------------|
|          **Team erstellen**          |    Ja<sup>1</sup>     |     Nein      |
|          **Team verlassen**           |    Ja     |     Ja     |
|  **Teamnamen/Teambeschreibung bearbeiten**   |    Ja     |     Nein      |
|          **Team löschen**          |    Ja     |     Nein      |
|          **Standardkanal hinzufügen**          |    Ja     |    Ja<sup>2</sup>|
| **Kanalnamen/Kanalbeschreibung bearbeiten** |    Ja     |    Ja<sup>2</sup>|
|        **Standardkanal löschen**         |    Ja     |    Ja<sup>2</sup>|
|          ***Privaten Kanal hinzufügen**          |    Ja     |    Ja<sup>2</sup>|
| ***Namen/Beschreibung des privaten Kanals bearbeiten** |    Nein     |    Nicht zutreffend|
|        ***Privaten Kanal löschen**         |    Ja     |    Nein|
|          **Hinzufügen von Mitgliedern**          |  Ja<sup>3</sup>   |     Nein<sup>4</sup>    |
|          **Hinzufügen von Mitgliedern anfordern**          |  Nicht zutreffend   |     Ja<sup>5</sup>     |
|           **Apps hinzufügen**            |    Ja     |    Ja<sup>2</sup>|

<sup>1</sup> Teambesitzer können Teams erstellen, es sei denn, sie wurden davon ausgeschlossen. Siehe [Berechtigungen zum Erstellen von Teams](#permissions-to-create-teams) weiter unten.<br>
<sup>2</sup> Diese Elemente können von einem Besitzer auf Teamebene deaktiviert werden. In diesem Fall können Mitglieder nicht darauf zugreifen.<br>
<sup>3</sup> Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied in den Besitzerstatus höherstufen. Es ist auch möglich, dass ein Besitzer seinen eigenen Status zu einem Mitglied tiefer stuft.<br>
<sup>4</sup> Teammitglieder können andere Mitglieder zu einem öffentlichen Team hinzufügen.<br>
<sup>5</sup> Während ein Teammitglied Mitglieder nicht direkt zu einem privaten Team hinzufügen kann, kann es das Hinzufügen einer anderen Person zu einem Team anfordern, in dem es bereits Mitglied ist. Wenn ein Mitglied das Hinzufügen einer anderen Person zu einem Team anfordert, erhalten Teambesitzer eine Benachrichtigung über eine ausstehende Anforderung, die sie annehmen oder ablehnen können.

* Weitere Informationen zu Berechtigungen für private Kanäle finden Sie unter [Private Kanäle in Teams](private-channels.md).

> [!NOTE]
> Besitzer können in der Option **View Teams** (Teams anzeigen) andere Mitglieder zu Besitzern ernennen. Ein Team kann bis zu 100 Besitzer haben. Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt. Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Moderatorfunktionen

Besitzern und Mitgliedern können neben anderen Funktionen auch Moderatorfunktionen für einen bestimmten Kanal zugeordnet werden (sofern die Moderation für ein Team aktiviert wurde). Moderatoren können neue Beiträge in einem Kanal starten und steuern, ob Teammitglieder auf vorhandene Kanalnachrichten antworten können. Sie können auch steuern, ob Bots und Konnektoren Kanalnachrichten senden können.

Moderatorfunktionen werden auf Kanalebene zugewiesen. Teambesitzer verfügen standardmäßig über Moderatorfunktionen. Bei Teammitgliedern ist die Funktion "Moderatoren" standardmäßig deaktiviert, ein Teambesitzer kann einem Teammitglied jedoch Moderatorfunktionen für einen Kanal zuweisen. Moderatoren können weitere Moderatoren innerhalb eines ihnen zugewiesenen Kanals hinzufügen und entfernen.

Weitere Informationen über Moderatorfunktionen finden Sie unter [Einrichten und Verwalten der Kanalmoderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Zuweisen einer Benutzerrolle

Um eine Benutzerrolle zuzuweisen, wählen Sie in Teams den Teamnamen aus und klicken Sie dann auf **Weitere Optionen** > **Team verwalten**. Auf der Registerkarte **Mitglieder** können Sie Mitglieder hinzufügen sowie Besitzer und Moderatoren auswählen (sofern Sie über ausreichende Berechtigungen verfügen). Weitere Informationen finden Sie unter [Ändern der Teameinstellungen in Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).

## <a name="permissions-to-create-teams"></a>Berechtigungen zum Erstellen von Teams

Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigung zum Erstellen von Microsoft 365-Gruppen und damit zum Erstellen eines Teams in Microsoft Teams. Sie können dies genauer steuern sowie die Erstellung neuer Teams und damit die Erstellung neuer Microsoft 365-Gruppen einschränken, indem Sie die Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Benutzern delegieren. Entsprechende Anweisungen finden Sie unter [Verwalten von Personen, die Microsoft 365-Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).
