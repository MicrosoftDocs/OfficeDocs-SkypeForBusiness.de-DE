---
title: Verwalten von Vorlagen für Teams im Admin Center
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Vorlagen für Teams im Admin Center verwalten.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ef765013541ae740211cc5666da3544f1cd5b528
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125903"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a>Erstellen und Verwalten von Vorlagen für Teams im Admin Center

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Verwalten Sie die Teams-Vorlagen, die Ihren Endbenutzern angezeigt werden, indem Sie Vorlagenrichtlinien im Admin Center erstellen. Innerhalb jeder Vorlagenrichtlinie können Sie festlegen, welche Vorlagen ein- oder ausgeblendet werden sollen.
Weisen Sie verschiedene Benutzer verschiedenen Vorlagenrichtlinien zu, damit Ihre Benutzer nur die teilmenge der angegebenen Teams-Vorlagen anzeigen können.

## <a name="create-template-policies-and-assign-available-templates"></a>Erstellen von Vorlagenrichtlinien und Zuweisen verfügbarer Vorlagen

1. Melden Sie sich beim Teams Admin Center an.

2. Erweitern Sie **die Richtlinien für**  >  **Teams-Vorlagen.**

3. Klicken Sie auf **Hinzufügen**.

    ![Die Vorlagenrichtlinien sind ausgewählt, und "Hinzufügen" ist hervorgehoben.](media/template-policies-1.png)

1. Füllen Sie **im Abschnitt "Vorlagenrichtlinieneinstellungen"** die folgenden Felder aus:

    - Name der Vorlagenrichtlinie

    - Kurzbeschreibung der Vorlagenrichtlinie

2. Wählen Sie in **der Tabelle "Anzeigevorlagen"** die Vorlagen aus, die Sie ausblenden möchten, und wählen Sie "Ausblenden" **aus.**

    ![Die ausgewählten Vorlagen mit hervorgehobener Option "Ausblenden"](media/template-policies-2.png)

    Die Vorlagen, die Sie zum Ausblenden ausgewählt haben, werden in der Tabelle **"Ausgeblendete Vorlagen"** angezeigt.

1. Um bestimmte Vorlagen ein-/aus- en, scrollen Sie zur Tabelle **"Ausgeblendete Vorlagen".**

1. Wählen Sie die Vorlagen aus, die sie ein-/ein- en, und wählen Sie dann **"Anzeigen" aus.**

   ![Die ausgewählten Vorlagen mit hervorgehobener Option "Ausblenden"](media/template-policies-3.png)

   Die ausgewählten Vorlagen werden in der Tabelle mit den **anzeigebaren Vorlagen** angezeigt.
3. Klicken Sie auf **Speichern**.

   Ihre neue Vorlagenrichtlinie wird in der Liste **"Vorlagenrichtlinien"** angezeigt.

## <a name="assign-users-to-the-template-policies"></a>Zuweisen von Benutzern zu den Vorlagenrichtlinien

Benutzer, die einer Richtlinie zugewiesen sind, können nur die anzeigebaren Vorlagen innerhalb dieser Richtlinie anzeigen.

1. Wählen **Sie in "Vorlagenrichtlinien"** eine Richtlinie und dann "Benutzer **verwalten" aus.**

2. Geben Sie die Benutzer ein, die dieser Richtlinie zugewiesen werden soll.

   ![Die ausgewählten Vorlagen mit hervorgehobener Option "Ausblenden"](media/template-policies-4.png)

3. Wählen Sie **"Übernehmen"** aus.

> [!Note]
> Es kann bis zu 24 Stunden dauern, bis die neue Richtlinie für Endbenutzer in Kraft tritt.

## <a name="size-limits-for-template-policies"></a>Größenbeschränkungen für Vorlagenrichtlinien

Sie können maximal 100 Vorlagen pro Richtlinie ausblenden. Die **Schaltfläche "Ausblenden"** ist deaktiviert, wenn die angegebene Richtlinie bereits 100 Vorlagen ausgeblendet hat.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Kann ich Richtlinien für Teamvorlagen Benutzer zu Teamvorlagen zuweisen?**
  
A: Ja, wir unterstützen die Batchzuordnung für die Vorlagenrichtlinie in PowerShell. Der Richtlinientyp für diese Aktion ist "TeamsTemplatePermissionPolicy". [Weitere Informationen](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

**F: Können Richtlinien für Teamvorlagen Gruppen zugewiesen werden?**

A: Derzeit nein. Diese Funktion wird in Zukunft zur Verfügung stehen.

**F: Wird die Vorlage in meine Richtlinien eingeschlossen, wenn eine neue Vorlage erstellt wird?**

A: Alle neuen Vorlagen sind standardmäßig sichtbar. Sie können die Vorlage im Admin Center im Abschnitt "Vorlagenrichtlinien" ausblenden.

**F: Was geschieht, wenn eine Vorlage gelöscht wird?**

A: Gelöschte Vorlagen sind in den Vorlagenrichtlinien nicht mehr vorhanden.

**F: Kann ich einer Vorlagenrichtlinie im Teams Admin Center mehrere Benutzer zuweisen?**

A: Ja.

1. Wechseln Sie im Admin Center zu **"Benutzer".**
1. Wählen Sie in der Liste "Benutzer" die Benutzer aus, die Sie einer bestimmten Vorlagenrichtlinie zuweisen möchten.
1. Wählen Sie "Einstellungen bearbeiten" aus, und ändern Sie das Feld "Vorlagenrichtlinien".
1. Wählen Sie "Übernehmen" aus.
   Weitere Informationen [zum Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams – Microsoft Teams Microsoft \| Docs.](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)

**F: Wie kann ich alle Benutzer anzeigen, die einer bestimmten Richtlinie zugewiesen sind?**

A: Im Admin Center:

1. Wechseln Sie zum Abschnitt **"Benutzer".**
2. Wählen Sie in der Listentabelle "Benutzer" den Filter aus, und filtern Sie nach der Vorlage "Teams".
3. Wählen Sie **"Übernehmen"** aus.

![Die ausgewählten Vorlagen mit hervorgehobener Option "Ausblenden"](media/template-policies-5.png)

**F: Kann ich Vorlagenrichtlinien über PowerShell verwalten?**

A: Nein, dies wird nicht unterstützt.

**F: Gelten Vorlagenrichtlinien für EDU?**

A: Nein, dies wird nicht unterstützt.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teamvorlagen im Admin Center](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [Erstellen einer benutzerdefinierten Teamvorlage](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [Erstellen einer Vorlage aus einem vorhandenen Team](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams – Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies)

- [TeamsTemplatePermissionPolicy](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)