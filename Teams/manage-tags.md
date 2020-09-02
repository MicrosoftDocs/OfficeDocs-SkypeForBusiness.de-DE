---
title: Verwalten von Tags in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie die Verwendung von Tags in Microsoft Teams in Ihrer Organisation verwalten können.
ms.openlocfilehash: 9295d03aecb6c0bc6a4f667214869fe698d4eaab
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324014"
---
# <a name="manage-tags-in-microsoft-teams"></a>Verwalten von Tags in Microsoft Teams

> [!NOTE]
> Eines der in diesem Artikel behandelten Features, **Tagging per Schicht**, wurde noch nicht veröffentlicht. Es wurde angekündigt, und es wird bald kommen.Wenn Sie ein Administrator sind, können Sie herausfinden, wann dieses Feature im Nachrichtencenter veröffentlicht wird (im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)). Weitere Informationen zu bevorstehenden Features von Teams finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Übersicht

Mithilfe von Tags in Microsoft Teams können Benutzer schnell und einfach mit einer Teilmenge von Personen in einem Team verbunden werden. Sie können benutzerdefinierte Kategorien erstellen und zuweisen, um Personen anhand von Attributen wie Rolle, Projekt, Qualifikation oder Standort zu kategorisieren. Oder, Kategorien können basierend auf Ihren Plan-und Schicht Informationen in der [App Schichten](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) automatisch Personen zugewiesen werden (in Kürze verfügbar). Nachdem ein Tag einem oder mehreren Teammitgliedern hinzugefügt wurde, kann es in @Mentions von jeder Person im Team in einem Kanal Beitrag verwendet werden oder eine Unterhaltung mit nur den Personen beginnen, denen diese Kategorie zugewiesen ist.

Wie bereits erwähnt, gibt es zwei Arten von Tags in Teams.

- **Benutzerdefinierte Tags**: Teambesitzer und Teammitglieder (wenn das Feature für Sie aktiviert ist) können Personen manuell Kategorien erstellen und zuweisen. Beispielsweise erreicht eine Kategorie "Designer" oder "Radiologen" diese Gruppen von Personen in einem Team, ohne ihre Namen eingeben zu müssen.
- **Tagging nach Schicht** (in Kürze verfügbar): mit dieser Funktion werden Personen automatisch Kategorien zugewiesen, die ihren Plan-und Schicht Gruppennamen in der [App Schichten](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams abgleichen. Beispielsweise erreicht das Tag "EngineerOnCall" alle Ingenieure, die in Schichten zum Zeitpunkt der Verwendung des Tags in einem Chat oder Kanal Beitrag geplant sind. Mit der Kennzeichnung nach Schicht nimmt Teams die Vermutungen auf, dass Sie den Namen von Mitarbeitern in einem Schicht wissen, wenn Benutzerinformationen schnell weiterleiten müssen. Das Tagging nach Schicht kann auch von wichtigen Workforce-Management-Systemen wie JDA, Kronos und AMiON unter Berücksichtigung durch die Integration in Schichten in Teams gesichert werden. Weitere Informationen zum Einrichten dieses Features finden Sie unter [Einrichten von Tagging nach Schicht](#set-up-tagging-by-shift-coming-soon).

> [!NOTE]
> Tags werden in privaten Kanälen noch nicht unterstützt. Tags sind in der US Government Community Cloud (gcc), gcc-höchst-oder Department of Defense (DoD)-Organisationen noch nicht verfügbar.

## <a name="how-tags-work"></a>Funktionsweise von Tags

Eine Kategorie kann einer Person in einem bestimmten Team manuell hinzugefügt oder automatisch zugewiesen werden. Sie kann dann in @Mentions in der Zeile " **an** " in einem Chat oder in einem Beitrag in einem beliebigen Standardkanal des Teams verwendet werden. Nachfolgend finden Sie einige Beispiele für die Verwendung von Tags in Teams:

- Ein Store Manager sendet eine Ankündigung an einen Kanal, um alle Kassierer zu benachrichtigen.
- Ein Krankenhaus Administrator sendet eine Nachricht an alle Radiologen in einem Kanal.
- Ein Marketing Manager startet einen Gruppen-Chat mit allen Designern.
- Eine Krankenschwester sendet eine Nachricht an alle Anruf Kardiologen. (in Kürze verfügbar)
- Ein Systemingenieur Bucht eine Ankündigung an einen Kanal, um alle Ingenieure in einem Schicht Feld zu benachrichtigen. (in Kürze verfügbar)

Wenn ein Tag in einer Kanal Unterhaltung @mentioned wird, werden Teammitglieder, die dem Tag zugeordnet sind, ebenso wie alle anderen @mention benachrichtigt.

## <a name="manage-custom-tags-for-your-organization"></a>Verwalten von benutzerdefinierten Tags für Ihre Organisation

Als Administrator können Sie steuern, wie Transponder in Ihrer Organisation im Microsoft Teams Admin Center verwendet werden.

![Screenshot der Einstellungen für das Tagging im Microsoft Teams Admin Center](media/manage-tags-admin-settings.png)

Ein Team kann bis zu 100-Tags haben, bis zu 100 Teammitglieder können einem Tag zugewiesen werden, und einem einzelnen Benutzer können bis zu 25 Tags zugewiesen werden. 

### <a name="set-who-can-add-custom-tags"></a>Bestimmen, wer benutzerdefinierte Kategorien hinzufügen kann

Standardmäßig können Teambesitzer benutzerdefinierte Kategorien hinzufügen. Sie können diese Einstellung ändern, um Teambesitzern und Teammitgliedern das Erstellen, bearbeiten, löschen und Verwalten von Tags zu ermöglichen, oder Sie können Kategorien für Ihre Organisation deaktivieren.

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.
2. Wählen Sie unter **Tagging**neben **Kategorien werden verwaltet von**eine der folgenden Optionen aus:

    - **Teambesitzer und Mitglieder**: zulassen, dass Teambesitzer und Mitgliederkategorien verwalten können.
    - **Teambesitzer**: zulassen, dass Teambesitzer Kategorien verwalten können.
    - **Deaktiviert**: Deaktivieren von Tags.

### <a name="configure-custom-tags-settings"></a>Konfigurieren von benutzerdefinierten Tags-Einstellungen

Sie können die folgenden Tags-Einstellungen konfigurieren, um zu steuern, wie benutzerdefinierte Tags in Ihrer Organisation verwendet werden.

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.
2. Legen Sie unter **Tagging** je nach den Anforderungen Ihrer Organisation Folgendes fest.

    - **Zulassen, dass Teambesitzer überschreiben, wer Tags verwalten kann**: Wenn Sie diese Einstellung aktivieren, können Teambesitzer festlegen, ob Teammitglieder Tags innerhalb eines Teams erstellen und verwalten können, und der Wert der **Tags wird verwaltet, indem** die Einstellung der Standardwert für die einzelnen Teams ist. Wenn Sie diese Einstellung deaktivieren, werden die **Tags verwaltet, indem** die Einstellung nicht pro Team geändert werden kann.
    - **Vorgeschlagene Standardtags**: Hiermit können Sie eine Reihe von Standardtags hinzufügen. Sie können bis zu 25 Tags hinzufügen, und jedes Tag kann maximal 25 Zeichen enthalten. Teambesitzer und -mitglieder können diese Vorschläge verwenden, weitere hinzufügen oder einen neuen Satz von Tags erstellen (wenn das Feature für sie aktiviert ist).
    - **Erstellen benutzerdefinierter Tags**: Aktivieren Sie diese Einstellung, damit Personen andere Tags als die von Ihnen festgelegten vorgeschlagenen Standardkategorien hinzufügen können. Wenn diese Option deaktiviert ist, können die Benutzer nur die vorgeschlagenen Standardkategorien verwenden. Wenn Sie diese Option deaktivieren, stellen Sie sicher, dass Sie eine oder mehrere Standardkategorien hinzufügen.

## <a name="manage-custom-tags-settings-for-a-team"></a>Verwalten von benutzerdefinierten Kategorien Einstellungen für ein Team

Wenn Sie die Einstellung zulassen, dass **Teambesitzer überschreiben können, wer Tags** im Microsoft Teams Admin Center verwalten kann, können Teambesitzer festlegen, ob Mitgliederkategorien auf Team Ebene hinzufügen können. Wechseln Sie dazu auf der Registerkarte **Einstellungen** für ein Team zu **Tags**, und wählen Sie dann aus, wer Tags hinzufügen kann.

![Screenshot der Tag-Einstellung auf Teamebene](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Verwenden von Kategorien

Hier erfahren Sie, wie Sie benutzerdefinierte Kategorien hinzufügen und wie Sie das Tagging per Schicht einrichten (wenn Sie die app "Schichten" in Microsoft Teams verwenden). Wenn Sie mehr erfahren möchten, lesen Sie [Verwenden von Tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Erstellen und Zuweisen von benutzerdefinierten Tags

Wenn Sie benutzerdefinierte Tags erstellen und zuweisen möchten, wählen Sie auf der linken Seite der APP **Teams** aus, und suchen Sie dann Ihr Team in der Liste. Wählen Sie **Weitere Optionen**aus, und wählen Sie dann **Kategorien verwalten**aus. Hier können Sie Kategorien erstellen und Sie Personen in Ihrem Team zuweisen.

![Screenshot zum Anwenden von Tags im Teams-Client  ](media/manage-tags-teams.png)

Entfernen Sie zum Löschen einer Kategorie alle Teammitglieder, die dem Tag zugeordnet sind.

### <a name="set-up-tagging-by-shift-coming-soon"></a>Einrichten von Tagging nach Schicht (in Kürze verfügbar)

1. Wechseln Sie in Microsoft Teams zur [App Schichten](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Erstellen Sie [Schicht Gruppen](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) , und benennen Sie Sie nach einem Attribut wie einer Rolle. Beispiel: EngineerOnCall. Der Name der Schichtgruppe ist der Name der Kategorie.
3. [Füllen Sie einen Zeitplan aus](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) , indem Sie den Mitgliedern ihrer Teams Schichten zuweisen. Wenn Sie fertig sind, wählen Sie in der oberen rechten Ecke der APP Schichten die Option **für Team freigeben**aus.
4. Warten Sie 15 Minuten, bis die geplanten Schichten den taggingdienst gefüllt haben.
5. Verwenden Sie das Tag, an dem Sie Tags in Teams verwenden.

Durch Tagging nach Schicht können Ihre Benutzer die Personen, die sich in Echtzeit bewegen, in Echtzeit erreichen. Benachrichtigungen werden nur an Personen gesendet, die zu dem Zeitpunkt, zu dem ein Tag zum Starten eines Chats oder in einem Kanal Beitrag verwendet wird, auf Schicht sind.

## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Verwalten der Schichten-App für Ihre Organisation in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Hilfedokumentation zu Schichten](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
