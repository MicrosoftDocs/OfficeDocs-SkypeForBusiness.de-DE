---
title: Verwalten von Tags in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
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
ms.openlocfilehash: 6b95dc07954803ea6d15a1ca5bdf6c705ca3e252
ms.sourcegitcommit: 1d24b62f41bce4f8d86d6060291af1267f75a2a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209487"
---
# <a name="manage-tags-in-microsoft-teams"></a>Verwalten von Tags in Microsoft Teams

Mithilfe von Tags in Microsoft Teams können Benutzer mit einer Teilmenge von Personen in einem Team kommunizieren. Tags können einem oder mehreren Teammitgliedern hinzugefügt werden, um auf einfache Weise mit einer bestimmten Gruppe von Personen in Kontakt zu treten. Teambesitzer und -mitglieder können einer Person ein oder mehrere Tags hinzufügen (wenn das Feature für sie aktiviert ist). Die Tags können dann von jedem Teammitglied in @Erwähnungen in Kanalbeiträgen verwendet werden, oder um eine Unterhaltung nur mit den Personen zu starten, denen das entsprechende Tag zugewiesen ist.

> [!NOTE]
> Tags werden in privaten Kanälen noch nicht unterstützt. Tags sind in der US Government Community Cloud (gcc), gcc-höchst-oder Department of Defense (DoD)-Organisationen noch nicht verfügbar.

## <a name="how-tags-work"></a>Funktionsweise von Tags

Ein Tag kann einer Person in einem bestimmten Team hinzugefügt werden. Nachdem ein Tag hinzugefügt wurde, kann es in @Erwähnungen in einem Chat oder in einem beliebigen Standardkanal des Teams verwendet werden. Nachfolgend finden Sie einige Beispiele für die Verwendung von Tags in Teams:

- Ein Verkaufsleiter möchte eine Ankündigung in einem Kanal posten und alle Kassierer benachrichtigen.
- Ein Produktmanager möchte Nachrichten an alle Produktmanager in einem Kanal senden.
- Ein Krankenhausleiter möchte allen Radiologen in einem Kanal eine Nachricht senden.
- Ein Marketingmanager möchte einen Gruppenchat mit allen Designern beginnen.

Wenn Sie mehr erfahren möchten, lesen Sie [Verwenden von Tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

## <a name="manage-tags-for-your-organization"></a>Verwalten von Tags für Ihre Organisation

Als Administrator können Sie im Microsoft Teams Admin Center steuern, wer Tags hinzufügen kann und wie Tags in Ihrer Organisation verwendet werden.

![Screenshot der Einstellungen für das Tagging im Microsoft Teams Admin Center](media/manage-tags-admin-settings.png)

Ein Team kann bis zu 100-Tags haben, bis zu 100 Teammitglieder können einem Tag zugewiesen werden, und einem einzelnen Benutzer können bis zu 25 Tags zugewiesen werden. 

### <a name="set-who-can-add-tags"></a>Festlegen, wer Tags hinzufügen kann

Standardmäßig können Teambesitzer Tags hinzufügen. Sie können diese Einstellung ändern, damit Teambesitzer und Teammitglieder Tags hinzufügen können, oder Sie können Tags für Ihre Organisation deaktivieren.

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.
2. Wählen Sie unter **Tagging** neben **Tagging aktivieren für** eine der folgenden Optionen aus:

    - **Teambesitzer und -mitglieder**: Zulassen, dass Teambesitzer und -mitglieder Tags hinzufügen.
    - **Teambesitzer**: Zulassen, dass Teambesitzer Tags hinzufügen.
    - **Deaktiviert**: Deaktivieren von Tags.

### <a name="configure-tags-settings"></a>Konfigurieren von Tag-Einstellungen

Sie können die folgenden Tag-Einstellungen konfigurieren, um zu steuern, wie Tags in Ihrer Organisation verwendet werden.

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.
2. Legen Sie unter **Tagging** je nach den Anforderungen Ihrer Organisation Folgendes fest.

    - **Teambesitzer kann überschreiben, wer Tags anwenden kann**: Wenn diese Option aktiviert ist, können Teambesitzer zulassen oder verhindern, dass Mitglieder Tags in Teameinstellungen hinzufügen.
    - **Mitglieder können zusätzliche Tags hinzufügen**: Wenn Sie Teammitgliedern erlauben, Tags hinzuzufügen, aktivieren Sie diese Option, damit Teammitglieder andere Tags als die von Ihnen festgelegten empfohlenen Standardtags hinzufügen können. Ist diese Option deaktiviert, können Teammitglieder nur die Standardtags verwenden.
    - **Vorgeschlagene Standardtags**: Hiermit können Sie eine Reihe von Standardtags hinzufügen. Sie können bis zu 25 Tags hinzufügen, und jedes Tag kann maximal 25 Zeichen enthalten. Teambesitzer und -mitglieder können diese Vorschläge verwenden, weitere hinzufügen oder einen neuen Satz von Tags erstellen (wenn das Feature für sie aktiviert ist).

## <a name="manage-tags-settings-for-a-team"></a>Verwalten von Tag-Einstellungen für ein Team

Wenn Sie die Einstellung **Teambesitzer kann überschreiben, wer Tags anwenden kann** im Microsoft Teams Admin Center aktiviert haben, können Teambesitzer festlegen, ob Mitglieder auf Teamebene Tags hinzufügen können. Wechseln Sie dazu auf der Registerkarte **Einstellungen** für ein Team zu **Tags**, und wählen Sie dann aus, wer Tags hinzufügen kann.

![Screenshot der Tag-Einstellung auf Teamebene](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a>Hinzufügen von Tags in Teams

In Teams enthält die Registerkarte **Mitglieder** der Seite "Team verwalten" für ein Team eine Spalte **Tags**. Teambesitzer und -mitglieder können auf **Tags verwalten** neben einem Mitglied klicken, um die Liste der vorgeschlagenen Tags für dieses Mitglied anzuzeigen und der Liste Tags hinzuzufügen (wenn das Feature für sie aktiviert ist).

![Screenshot zum Anwenden von Tags im Teams-Client  ](media/manage-tags-teams.png) 
