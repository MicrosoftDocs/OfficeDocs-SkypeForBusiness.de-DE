---
title: Verwalten von Tags in Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie die Verwendung von Tags in Microsoft Teams in Ihrer Organisation verwalten können.
ms.openlocfilehash: 6d5ec8407dd413b2850603ad1eb7c6424e1d483d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856382"
---
# <a name="manage-tags-in-microsoft-teams"></a>Verwalten von Tags in Microsoft Teams

## <a name="overview"></a>Übersicht

Mithilfe von Tags in Microsoft Teams können Benutzer mit einer begrenzten Anzahl von Personen in einem Team kommunizieren. Sie können benutzerdefinierte Tags erstellen und zuweisen, um Personen basierend auf Attributen wie Rolle, Projekt, Fertigkeiten oder Standort zu kategorisieren. Tags können Personen auch automatisch basierend auf ihren Zeitplan- und Schichtinformationen in der [Schichten-App](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) zugewiesen werden. Nachdem ein Tag zu einem oder mehreren Teammitgliedern hinzugefügt wurde, kann es von allen Teammitgliedern in @Erwähnungen in Kanalbeiträgen oder zum Starten einer Unterhaltung verwendet werden, um nur mit den Personen zu kommunizieren, denen das entsprechende Tag zugewiesen wurde.

Wie bereits zuvor erwähnt, gibt es in Microsoft Teams zwei Arten von Tags.

- **Benutzerdefinierte Tags**: Teambesitzer und Teammitglieder können (wenn das Feature für sie aktiviert ist) manuell Tags erstellen und sie Personen zuweisen. Beispielsweise erreicht man mit einem "Designer"- oder "Radiologe"-Tag die entsprechende Personengruppe, ohne die jeweiligen Namen eingeben zu müssen.
- **Tagging nach Schicht:** Mit diesem Feature werden Personen automatisch Tags zugewiesen, die ihren Plan- und Schicht-Gruppennamen in der [Schichten-App](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Microsoft Teams entsprechen. Beispielsweise erreicht das Tag "DiensthabenderTechniker" alle Techniker, die laut Schichten-App zu dem Zeitpunkt, zu dem das Tag in einem Chat oder Kanalbeitrag verwendet wird, für die Arbeit eingeteilt sind. Mit "Tagging nach Schicht" ist es in Microsoft Teams nicht mehr notwendig, die Namen der Mitarbeiter im Schichtdienst kennen, wenn Benutzer Informationen schnell weitergeben müssen. "Tagging nach Schicht" kann auch durch große Personalverwaltungssysteme wie JDA, Kronos und AMiON unterstützt werden durch die Kopplung mit "Schichten" in Microsoft Teams. Weitere Informationen zum Einrichten dieses Features finden Sie unter [Einrichten von "Tagging nach Schicht"](#set-up-tagging-by-shift).

> [!NOTE]
> Tags werden in privaten Kanälen noch nicht unterstützt. Tags sind in Organisationen des US-Verteidigungsministeriums (Department of Defense, DoD) nicht verfügbar. 

## <a name="how-tags-work"></a>Funktionsweise von Tags

Ein Tag kann einer Person in einem bestimmten Team manuell oder automatisch hinzugefügt werden. Es kann dann in @Erwähnungen in der **An**-Zeile in einem Chat oder einem Beitrag in einem beliebigen Standardkanal des Teams verwendet werden. Nachfolgend finden Sie einige Beispiele für die Verwendung von Tags in Microsoft Teams:

- Ein Verkaufsleiter postet eine Ankündigung in einem Kanal, um alle Kassierer zu benachrichtigen.
- Ein Krankenhausleiter sendet allen Radiologen in einem Kanal eine Nachricht.
- Ein Marketingmanager beginnt einen Gruppenchat mit allen Designern.
- Eine Pflegekraft sendet eine Nachricht an alle Kardiologen im Bereitschaftsdienst. (In Kürze verfügbar)
- Ein Systemtechniker postet eine Ankündigung in einem Kanal, um alle diensthabenden Techniker zu benachrichtigen. (In Kürze verfügbar)

Wenn ein Tag in einer Kanalunterhaltung @erwähnt wird, werden die dem Tag zugeordneten Teammitglieder genauso so wie bei herkömmlichen @Erwähnungen darüber benachrichtigt.

## <a name="manage-custom-tags-for-your-organization"></a>Verwalten benutzerdefinierter Tags für Ihre Organisation

Als Administrator können Sie im Microsoft Teams Admin Center steuern, wie Tags in Ihrer Organisation verwendet werden können. Derzeit können Sie PowerShell nicht zum Verwalten von Tags verwenden.

![Screenshot der Taggingeinstellungen im Microsoft Teams Admin Center.](media/manage-tags-admin-settings.png)

Einem Team können bis zu 100 Tags zugeordnet werden, einem Tag können bis zu 100 Teammitglieder zugeordnet werden, und einem einzelnen Benutzer können bis zu 25 Tags zugewiesen werden. 

### <a name="set-who-can-add-custom-tags"></a>Festlegen, wer benutzerdefinierte Tags hinzufügen kann

Standardmäßig können Teambesitzer benutzerdefinierte Tags hinzufügen. Sie können diese Einstellung so ändern, dass Teambesitzer und Teammitglieder Tags erstellen, bearbeiten, löschen und verwalten können, oder Sie können Tags für Ihre Organisation deaktivieren.

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Microsoft Teams-Einstellungen**.
2. Wählen Sie unter **Tagging** neben **Tags werden verwaltet von** eine der folgenden Optionen aus:

    - **Teambesitzer und -mitglieder**: Teambesitzern und -mitgliedern das Verwalten von Tags gestatten.
    - **Teambesitzer**: Teambesitzern das Verwalten von Tags gestatten.
    - **Deaktiviert**: Tags deaktivieren.

### <a name="configure-custom-tags-settings"></a>Einstellungen für benutzerdefinierte Tags festlegen

Sie können die folgenden Tag-Einstellungen festlegen, um zu steuern, wie benutzerdefinierte Tags in Ihrer Organisation verwendet werden.

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.
2. Legen Sie unter **Tagging** je nach den Anforderungen Ihrer Organisation Folgendes fest.

    - **Teambesitzer können überschreiben, wer Tags verwalten kann**: Wenn Sie diese Einstellung aktivieren, können Teambesitzer festlegen, ob Teammitglieder Tags innerhalb eines Teams erstellen und verwalten können, und der Wert für die **Tags werden verwaltet von**-Einstellung ist der Standardwert für jedes Team. Wenn Sie diese Einstellung deaktivieren, kann die Einstellung **Tags werden verwalteten von** nicht pro Team geändert werden.
    - **Vorgeschlagene Standardtags**: Hiermit können Sie eine Reihe von Standardtags hinzufügen. Sie können bis zu 25 Tags hinzufügen, und jedes Tag kann maximal 25 Zeichen enthalten. Teambesitzer und -mitglieder können diese Vorschläge verwenden, weitere hinzufügen oder einen neuen Satz von Tags erstellen (wenn das Feature für sie aktiviert ist).
    - **Erstellen benutzerdefinierter Tags zulassen**: Aktivieren Sie diese Einstellung, damit andere Tags als die vorgeschlagenen Standardtags hinzugefügt werden können, die Sie festgelegt haben. Ist diese Option deaktiviert, können Teammitglieder nur die Standardtags verwenden. Wenn Sie dies deaktivieren, fügen Sie mindestens ein Standardtag hinzu.

## <a name="manage-custom-tags-settings-for-a-team"></a>Einstellungen für benutzerdefinierte Tags für ein Team verwalten

Wenn Sie im Microsoft Teams Admin Center die Einstellung **Teambesitzer können überschreiben, wer Tags verwalten kann** aktiviert haben, können Teambesitzer festlegen, ob Mitglieder auf Teamebene Tags hinzufügen können. Wechseln Sie dazu auf der Registerkarte **Einstellungen** für ein Team zu **Tags**, und wählen Sie dann aus, wer Tags hinzufügen kann.

![Screenshot der Tags-Einstellung auf Teamebene](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Verwenden von Tags

Hier erfahren Sie, wie Sie benutzerdefinierte Tags hinzufügen können und wie "Tagging nach Schicht" eingerichtet wird (wenn Sie die "Schichten"-App in Microsoft Teams verwenden). Wenn Sie mehr erfahren möchten, lesen Sie [Verwenden von Tags in Microsoft Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Erstellen und Zuweisen benutzerdefinierter Tags

Um benutzerdefinierte Tags zu erstellen und zu zuweisen, wählen Sie **Teams** auf der linken Seite der App aus, und suchen Sie dann das gewünschte Team in der Liste. Wählen Sie **˙˙˙ "Weitere Optionen"** und dann **Tags verwalten** aus. Hier können Sie Tags erstellen und sie Personen in Ihrem Team zuweisen.

![Screenshot zum Anwenden von Tags im Client Teams Client.](media/manage-tags-teams.png)

Um ein Tag zu löschen, wählen Sie **˙˙˙ "Weitere Optionen"** neben dem Tag und dann **Tag löschen** aus.

### <a name="set-up-tagging-by-shift"></a>Einrichten von "Tagging nach Schicht"

"Tagging nach Schicht" ermöglicht es Ihren Benutzern, diensthabende Mitarbeiter in Echtzeit zu erreichen. Teams weist Benutzern automatisch Tags zu, die ihrem Zeitplan und dem Namen der Schichtgruppe aus der App „Schichten“ entsprechen, wodurch das dynamische rollenbasierte Versenden von Nachrichten ermöglicht wird. Benachrichtigungen werden nur an die Personen gesendet, die sich im Schichtdienst befinden, wenn ein Tag zum Starten eines Chats oder in einem Kanalbeitrag verwendet wird. 

1. Wechseln Sie in Microsoft Teams zur [Schichten](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)-App.
2. Erstellen Sie [Schicht-Gruppen](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup), und benennen Sie diese nach einem Attribut wie z. B. einer Rolle. Beispiel: "DiensthabenderTechniker". Der Name der Schicht-Gruppe entspricht dem Namen des Tags.
3. [Erstellen Sie einen Zeitplan](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea), indem Sie Mitgliedern Ihrer Teams Schichten zuweisen. Wenn Sie fertig sind, wählen Sie in der oberen rechten Ecke in der "Schichten"-App die Option **Für ein Team freigeben** aus.
4. Warten Sie 15 Minuten, bis die geplanten Schichten in den Taggingdienst gespeist wurden.
5. Verwenden Sie das Tag überall dort, wo Sie in Microsoft Teams Tags verwenden.

## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Tags in Microsoft Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

[Verwalten der "Schichten"-App für Ihre Organisation in Microsoft Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

["Schichten" – Hilfedokumentation](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
