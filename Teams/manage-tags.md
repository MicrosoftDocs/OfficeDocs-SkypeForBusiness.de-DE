---
title: Verwalten von Tags in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie die Verwendung von Tags in Microsoft Teams in Ihrer Organisation verwalten können.
ms.openlocfilehash: bdb4fcbdd4c4d197dcdc778b9c15130071ad37fc
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267950"
---
# <a name="manage-tags-in-microsoft-teams"></a>Verwalten von Tags in Microsoft Teams

## <a name="overview"></a>Übersicht

Mithilfe von Tags in Microsoft Teams können Benutzer mit einer begrenzten Anzahl von Personen in einem Team kommunizieren. Sie können benutzerdefinierte Tags erstellen und zuweisen, um Personen basierend auf Attributen wie Rolle, Projekt, Fertigkeiten oder Standort zu kategorisieren. Tags können Personen auch automatisch basierend auf ihren Zeitplan- und Schichtinformationen in der [Schichten-App](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) zugewiesen werden. Nachdem ein Tag einem oder mehreren Teammitgliedern hinzugefügt wurde, kann es in @mentions von jeder Person im Team in einem Kanalbeitrag verwendet werden oder um nur die Personen zu benachrichtigen, denen dieses Tag einer Unterhaltung zugewiesen ist.

Wie bereits zuvor erwähnt, gibt es in Microsoft Teams zwei Arten von Tags.

- **Benutzerdefinierte Tags**: Teambesitzer und Teammitglieder können (wenn das Feature für sie aktiviert ist) manuell Tags erstellen und sie Personen zuweisen. Beispielsweise erreicht ein Tag "Designer" oder "Radiologe" diese Gruppen von Personen in einem Team, ohne deren Namen eingeben zu müssen.
- **Tagging nach Schicht:** Mit diesem Feature werden Personen automatisch Tags zugewiesen, die ihren Plan- und Schicht-Gruppennamen in der [Schichten-App](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Microsoft Teams entsprechen. Beispielsweise erreicht das Tag "EngineerOnCall" alle Techniker, die in Schichten geplant sind, um zu dem Zeitpunkt zu arbeiten, zu dem das Tag in einem Chat- oder Kanalbeitrag verwendet wird. Mit "Tagging nach Schicht" ist es in Microsoft Teams nicht mehr notwendig, die Namen der Mitarbeiter im Schichtdienst kennen, wenn Benutzer Informationen schnell weitergeben müssen.

> [!NOTE]
> Tags werden in privaten oder freigegebenen Kanälen nicht unterstützt.

## <a name="how-tags-work"></a>Funktionsweise von Tags

Ein Tag kann einer Person in einem bestimmten Team manuell oder automatisch hinzugefügt werden. Es kann dann in @Erwähnungen in der **An**-Zeile in einem Chat oder einem Beitrag in einem beliebigen Standardkanal des Teams verwendet werden. Hier sind einige Beispiele dafür, wie Tags in Teams verwendet werden können:

- Ein Verkaufsleiter postet eine Ankündigung in einem Kanal, um alle Kassierer zu benachrichtigen.
- Ein Krankenhausleiter sendet allen Radiologen in einem Kanal eine Nachricht.
- Ein Marketingmanager beginnt einen Gruppenchat mit allen Designern.

Wenn ein Tag in einer Kanalunterhaltung @erwähnt wird, werden die dem Tag zugeordneten Teammitglieder genauso so wie bei herkömmlichen @Erwähnungen darüber benachrichtigt.

## <a name="manage-custom-tags-for-your-organization"></a>Verwalten benutzerdefinierter Tags für Ihre Organisation

Als Administrator können Sie im Microsoft Teams Admin Center steuern, wie Tags in Ihrer Organisation verwendet werden können. Beachten Sie, dass Sie PowerShell nicht zum Verwalten von Tags verwenden können.

:::image type="content" source="media/manage-tags-admin-settings.png" alt-text="Screenshot der Taggingeinstellungen im Microsoft Teams Admin Center.":::

Einem Team können bis zu 100 Tags zugeordnet werden, einem Tag können bis zu 100 Teammitglieder zugeordnet werden, und einem einzelnen Benutzer können bis zu 25 Tags zugewiesen werden.

### <a name="set-who-can-add-custom-tags"></a>Festlegen, wer benutzerdefinierte Tags hinzufügen kann

Standardmäßig können Teambesitzer benutzerdefinierte Tags hinzufügen. Sie können diese Einstellung ändern, um Teambesitzern und Teammitgliedern das Erstellen, Bearbeiten, Löschen und Verwalten von Tags zu ermöglichen, oder Sie können Tags für Ihre Organisation deaktivieren.

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf " **Teams** \> **Teams-Einstellungen"**.

2. Wählen Sie unter **Tagging** neben **Tags werden verwaltet von** eine der folgenden Optionen aus:

    - **Teambesitzer und -mitglieder**: Teambesitzern und -mitgliedern das Verwalten von Tags gestatten.
    - **Teambesitzer**: Teambesitzern das Verwalten von Tags gestatten.
    - **Deaktiviert**: Tags deaktivieren.

### <a name="configure-custom-tags-settings"></a>Einstellungen für benutzerdefinierte Tags festlegen

Sie können die folgenden Tag-Einstellungen festlegen, um zu steuern, wie benutzerdefinierte Tags in Ihrer Organisation verwendet werden.

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf " **Teams** \> **Teams-Einstellungen"**.

2. Legen Sie unter **Tagging** je nach den Anforderungen Ihrer Organisation Folgendes fest.

    - **Teambesitzer können überschreiben, wer Tags verwalten kann**: Wenn Sie diese Einstellung aktivieren, können Teambesitzer festlegen, ob Teammitglieder Tags innerhalb eines Teams erstellen und verwalten können, und der Wert für die **Tags werden verwaltet von**-Einstellung ist der Standardwert für jedes Team. Wenn Sie diese Einstellung deaktivieren, werden die **Kategorien verwaltet, indem** die Einstellung nicht pro Team geändert werden kann.
    - **Vorgeschlagene Standardtags**: Hiermit können Sie eine Reihe von Standardtags hinzufügen. Sie können bis zu 25 Tags hinzufügen, und jedes Tag kann maximal 25 Zeichen enthalten. Teambesitzer und -mitglieder können diese Vorschläge verwenden, weitere hinzufügen oder einen neuen Satz von Tags erstellen (wenn das Feature für sie aktiviert ist).
    - **Erstellen benutzerdefinierter Tags zulassen**: Aktivieren Sie diese Einstellung, damit andere Tags als die vorgeschlagenen Standardtags hinzugefügt werden können, die Sie festgelegt haben. Ist diese Option deaktiviert, können Teammitglieder nur die Standardtags verwenden. Wenn Sie dies deaktivieren, fügen Sie mindestens ein Standardtag hinzu.

## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Tags in Microsoft Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

[Verwalten der "Schichten"-App für Ihre Organisation in Microsoft Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

["Schichten" – Hilfedokumentation](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
