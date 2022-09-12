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
ms.openlocfilehash: 9c2da438d3f88a172759ec13672aec663ae6add9
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647429"
---
# <a name="manage-tags-in-microsoft-teams"></a>Verwalten von Tags in Microsoft Teams

Mithilfe von Tags in Microsoft Teams können Benutzer mit einer begrenzten Anzahl von Personen in einem Team kommunizieren. Sie können benutzerdefinierte Tags erstellen und zuweisen, um Personen basierend auf Attributen wie Rolle, Projekt, Fertigkeiten oder Standort zu kategorisieren. Tags können Personen auch automatisch basierend auf ihren Zeitplan- und Schichtinformationen in der [Schichten-App](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6) zugewiesen werden. Nachdem ein Tag einem oder mehreren Teammitgliedern hinzugefügt wurde, kann es in @mentions von jeder Person im Team in einem Kanalbeitrag verwendet werden, um nur die Personen zu benachrichtigen, denen dieses Tag einer Unterhaltung zugewiesen ist.

Wie bereits zuvor erwähnt, gibt es in Microsoft Teams zwei Arten von Tags.

- **Benutzerdefinierte Tags**: Teambesitzer und Teammitglieder (wenn sie über die Berechtigungen verfügen) können Tags manuell erstellen und Personen zuweisen. Beispielsweise erreicht ein Tag "Designer" oder "Radiologe" diese Gruppen von Personen in einem Team, ohne deren Namen eingeben zu müssen.
- **Tagging nach Schicht:** Mit diesem Feature werden Personen automatisch Tags zugewiesen, die ihren Plan- und Schicht-Gruppennamen in der [Schichten-App](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_usetags) in Microsoft Teams entsprechen. Beispielsweise erreicht das Tag "EngineerOnCall" alle Techniker, die in Schichten geplant sind, um zu dem Zeitpunkt zu arbeiten, zu dem das Tag in einem Chat- oder Kanalbeitrag verwendet wird. Mit "Tagging nach Schicht" ist es in Microsoft Teams nicht mehr notwendig, die Namen der Mitarbeiter im Schichtdienst kennen, wenn Benutzer Informationen schnell weitergeben müssen.

> [!NOTE]
> Tags werden in privaten oder freigegebenen Kanälen nicht unterstützt.

## <a name="how-tags-work"></a>Funktionsweise von Tags

Ein Tag kann manuell hinzugefügt (benutzerdefiniertes Tag) oder automatisch einer Person in einem bestimmten Team zugewiesen werden (durch Einrichten von Schichten in der Schichten-App). Das Tag kann dann in @mentions in der **An-Zeile** in einem Chat oder in einem Beitrag in einem beliebigen Standardkanal des Teams verwendet werden. Hier sind einige Beispiele dafür, wie Tags in Teams verwendet werden können:

- Ein Verkaufsleiter postet eine Ankündigung in einem Kanal, um alle Kassierer zu benachrichtigen.
- Ein Krankenhausleiter sendet allen Radiologen in einem Kanal eine Nachricht.
- Ein Marketingmanager beginnt einen Gruppenchat mit allen Designern.
- Eine Pflegekraft sendet eine Nachricht an alle Kardiologen im Bereitschaftsdienst.
- Ein Systemtechniker postet eine Ankündigung in einem Kanal, um alle diensthabenden Techniker zu benachrichtigen.

Wenn ein Tag in einer Kanalunterhaltung @erwähnt wird, werden die dem Tag zugeordneten Teammitglieder genauso so wie bei herkömmlichen @Erwähnungen darüber benachrichtigt.

## <a name="manage-tags-for-your-organization"></a>Verwalten von Tags für Ihre Organisation

Als Administrator können Sie im Microsoft Teams Admin Center steuern, wie Tags in Ihrer Organisation verwendet werden können. Beachten Sie, dass Sie PowerShell nicht zum Verwalten von Tags verwenden können.

:::image type="content" source="media/manage-tags-admin-settings-shifts.png" alt-text="Screenshot der Taggingeinstellungen im Microsoft Teams Admin Center.":::

Ein Team kann bis zu 100 Tags, bis zu 200 Teammitglieder einem Tag und bis zu 25 Tags im selben Team einem einzelnen Benutzer zugewiesen werden.

### <a name="set-who-can-manage-tags"></a>Festlegen, wer Tags verwalten kann

Standardmäßig können Teambesitzer Tags erstellen, bearbeiten und löschen. Sie können die Einstellung " **Wer kann Tags verwalten** " ändern, um Teambesitzern und Teammitgliedern das Verwalten von Tags zu ermöglichen, oder Sie können Tags für Ihre Organisation deaktivieren.

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf " **Teams** \> **Teams-Einstellungen"**.

2. Wählen Sie unter **"Tagging**" neben **"Wer kann Tags verwalten**" eine der folgenden Optionen aus:

    - **Teambesitzer und -mitglieder**: Teambesitzern und -mitgliedern das Verwalten von Tags gestatten.
    - **Teambesitzer**: Teambesitzern das Verwalten von Tags gestatten.
    - **Nicht aktiviert**: Deaktivieren Sie Tags.

### <a name="configure-tagging-settings"></a>Konfigurieren von Taggingeinstellungen

Sie können die folgenden Tag-Einstellungen konfigurieren, um zu steuern, wie Tags in Ihrer Organisation verwendet werden.

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf " **Teams** \> **Teams-Einstellungen"**.

2. Legen Sie unter **Tagging** je nach den Anforderungen Ihrer Organisation Folgendes fest.

    - **Teambesitzer können ändern, wer Tags verwalten kann**: Wenn Sie diese Einstellung aktivieren, können Teambesitzer festlegen, ob Teammitglieder Tags innerhalb eines Teams erstellen und verwalten können, und der Wert der Einstellung **"Wer kann Tags verwalten** " ist der Standardwert für jedes Team. Wenn Sie diese Einstellung deaktivieren, kann die Einstellung " **Wer kann Tags verwalten** " nicht pro Team geändert werden.
    - **Vorgeschlagene Tags**: Verwenden Sie diese Option, um eine Reihe von Standardtags hinzuzufügen. Sie können bis zu 25 Tags hinzufügen, und jedes Tag kann maximal 25 Zeichen enthalten. Teambesitzer und -mitglieder können diese Vorschläge verwenden, weitere hinzufügen oder einen neuen Satz von Tags erstellen (wenn das Feature für sie aktiviert ist).
    - **Benutzerdefinierte Tags**: Aktivieren Sie diese Einstellung, damit andere Tags als die von Ihnen festgelegten vorgeschlagenen Standardtags hinzugefügt werden können. Ist diese Option deaktiviert, können Teammitglieder nur die Standardtags verwenden. Wenn Sie dies deaktivieren, fügen Sie mindestens ein Standardtag hinzu.
    - **Schichten-App kann Tags anwenden**: Aktivieren Sie diese Einstellung, damit die Schichten-App Personen, die in Echtzeit im Schichtbetrieb sind, automatisch Tags zuweisen kann. Diese Tags stimmen mit dem Zeitplan und dem Gruppennamen eines Benutzers in Schichten überein. Benachrichtigungen werden nur an Personen gesendet, die zu dem Zeitpunkt, zu dem das Tag in einem Chat oder Kanalbeitrag verwendet wird, im Schichtbetrieb sind.

## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Tags in Microsoft Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

[Verwalten der Schichten-App](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

["Schichten" – Hilfedokumentation](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
