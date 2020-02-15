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
description: Erfahren Sie, wie Sie in Microsoft Teams die Verwendung von Tags in Ihrer Organisation verwalten können.
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034504"
---
# <a name="manage-tags-in-microsoft-teams"></a>Verwalten von Tags in Microsoft Teams

> [!NOTE]
> Diese Funktion wird im Microsoft Teams Admin Center noch nicht angezeigt? Sie wird zurzeit bereitgestellt und ist möglicherweise noch nicht in Ihrer Organisation verfügbar. Schauen Sie sich die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)an, um über die bevorstehenden Teams-Features auf dem Laufenden zu bleiben.

Mithilfe von Tags in Microsoft Teams können Benutzer mit einer Teilmenge von Personen in einem Team kommunizieren. Tags können einem oder mehreren Teammitgliedern hinzugefügt werden, um problemlos eine Verbindung mit der richtigen Teilmenge der Personen herzustellen. Team Besitzer und-Mitglieder (wenn das Feature für Sie aktiviert ist) können einer Person eine oder mehrere Kategorien hinzufügen. Die Tags können dann in @Mentions von jeder Person im Team in einem Kanal Beitrag verwendet werden, um nur mit Personen zu kommunizieren, denen diese Kategorie zugewiesen ist.

> [!NOTE]
> Tags werden in privaten Kanälen noch nicht unterstützt.

## <a name="how-tags-work"></a>Funktionsweise von Tags

Eine Kategorie kann einer Person in einem bestimmten Team hinzugefügt werden. Nachdem eine Kategorie hinzugefügt wurde, kann Sie in @Mentions in einem beliebigen Standardkanal des Teams verwendet werden. Nachfolgend finden Sie einige Beispiele für die Verwendung von Tags in Teams:

- Ein Store Manager möchte eine Ankündigung in einem Kanal Posten und alle Kassierer benachrichtigen.
- Ein Group Product Manager möchte alle Produktmanager in einem Kanal Nachrichten.
- Ein Krankenhaus Administrator möchte eine Nachricht an alle Radiologen in einem Kanal senden.

Weitere Informationen finden Sie [unter Verwenden von Tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

## <a name="manage-tags-for-your-organization"></a>Verwalten von Tags für Ihre Organisation

Als Administrator können Sie steuern, wer Kategorien hinzufügen kann und wie Tags in Ihrer Organisation im Microsoft Teams Admin Center verwendet werden.

![Screenshot der Kennzeichnungs Einstellungen im Microsoft Teams Admin Center](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a>Bestimmen, wer Kategorien hinzufügen kann

Standardmäßig können Teambesitzer Kategorien hinzufügen. Sie können diese Einstellung ändern, um Teambesitzern und Teammitgliedern das Hinzufügen von Kategorien zu ermöglichen, oder Sie können Kategorien für Ihre Organisation deaktivieren.

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **organisationsweite Einstellungen** > **Teams Einstellungen**.
2. Wählen Sie unter **Tagging**neben **Tagging ist aktiviert für**eine der folgenden Optionen aus:

    - **Teambesitzer und Mitglieder**: zulassen, dass Teambesitzer und Mitgliederkategorien hinzufügen.
    - **Teambesitzer**: zulassen, dass Teambesitzer Kategorien hinzufügen.
    - **Deaktiviert**: Deaktivieren von Tags

### <a name="configure-tags-settings"></a>Konfigurieren von Tags-Einstellungen

Sie können die folgenden Tags-Einstellungen konfigurieren, um zu steuern, wie Transponder in Ihrer Organisation verwendet werden.

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **organisationsweite Einstellungen** > **Teams Einstellungen**.
2. Setzen Sie unter **Tagging**die folgenden Optionen, abhängig von den Anforderungen Ihrer Organisation.

    - **Der Teambesitzer kann überschreiben, wer Tags anwenden kann**: Wenn dies aktiviert ist, können Teambesitzer Mitgliedern das Hinzufügen von Kategorien in Team Einstellungen erlauben oder verbieten.
    - **Mitglieder können weitere Kategorien hinzufügen**: Wenn Sie Teammitgliedern das Hinzufügen von Kategorien gestatten, aktivieren Sie diese Option, damit die Teammitglieder andere Tags als die von Ihnen festgelegten vorgeschlagenen Standardkategorien hinzufügen können. Wenn diese Option deaktiviert ist, können Teammitglieder nur die Standardkategorien verwenden.
    - **Vorgeschlagene Standardtags**: Hier können Sie eine Reihe von Standardkategorien hinzufügen. Sie können bis zu 25 Kategorien hinzufügen, und jede Kategorie kann maximal 25 Zeichen enthalten. Team Besitzer und-Mitglieder (wenn das Feature für Sie aktiviert ist) können diese Vorschläge verwenden, Ihnen hinzufügen oder einen neuen Satz von Tags erstellen.

## <a name="manage-tags-settings-for-a-team"></a>Verwalten von Kategorien Einstellungen für ein Team

Wenn Sie den Teambesitzer aktiviert haben, können Sie festlegen, wer Tags im Microsoft Teams Admin Center **anwenden kann** , können Teambesitzer festlegen, ob Mitgliederkategorien auf Teamebene hinzufügen können. Wechseln Sie dazu auf der Registerkarte **Einstellungen** für ein Team zu **Tags**, und wählen Sie dann aus, wer Kategorien hinzufügen kann.

![Screenshot der Einstellung "Tags" auf Teamebene](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a>Hinzufügen von Kategorien in Teams

In Teams umfasst die Registerkarte **Mitglieder** der Seite Team verwalten für ein Team eine Spalte **Kategorien** . Team Besitzer und-Mitglieder (wenn das Feature für Sie aktiviert ist) können auf Tags neben einem Mitglied **Verwalten** klicken, um die Liste der vorgeschlagenen Kategorien für dieses Mitglied anzuzeigen und der Liste Kategorien hinzuzufügen.

![Screenshot zum Anwenden von Tags im Teams-Client ](media/manage-tags-teams.png) 
