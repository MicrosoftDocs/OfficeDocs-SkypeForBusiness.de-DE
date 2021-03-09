---
title: Verwalten von Teams-Vorlagen im Admin Center
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
description: Erfahren Sie, wie Sie Teams-Vorlagen im Admin Center verwalten.
ms.openlocfilehash: df734d175d521b5be3ef81bf9dd8a95d749812e2
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569011"
---
# <a name="manage-team-templates-in-the-admin-center"></a>Verwalten von Teamvorlagen im Admin Center

Verwalten Sie die Teams-Vorlagen, die Ihren Endbenutzern angezeigt werden, indem Sie Vorlagenrichtlinien im Admin Center erstellen. Innerhalb jeder Vorlagenrichtlinie können Sie festlegen, welche Vorlagen angezeigt oder ausgeblendet werden.
Weisen Sie verschiedenen Vorlagenrichtlinien unterschiedliche Benutzer zu, damit ihre Benutzer nur die teilmenge der angegebenen Teams-Vorlagen anzeigen.

## <a name="create-template-policies-and-assign-available-templates"></a>Erstellen von Vorlagenrichtlinien und Zuweisen verfügbarer Vorlagen

1. Melden Sie sich beim Teams Admin Center an.

2. Erweitern **Sie Richtlinien für**  >  **Teams-Vorlagen.**

3. Klicken Sie auf **Hinzufügen**.

    ![Die Vorlagenrichtlinien sind ausgewählt, und Hinzufügen ist hervorgehoben.](media/template-policies-1.png)

1. Füllen Sie **im Abschnitt Vorlagenrichtlinieneinstellungen** die folgenden Felder aus:

    - Vorlagenrichtlinienname

    - Kurzbeschreibung "Vorlagenrichtlinie"

2. Wählen Sie **in der Tabelle** Ansichtsvorlagen die Vorlagen aus, die Sie ausblenden möchten, und wählen Sie Ausblenden **aus.**

    ![Die ausgewählten Vorlagen mit hervorgehobener Ausblendeung](media/template-policies-2.png)

    Sie können die Vorlagen sehen, die Sie ausgewählt haben, um sie in der Tabelle **Ausgeblendete Vorlagen** auszublenden.

1. Wenn Sie bestimmte Vorlagen ein-/ausdingen, scrollen Sie zur **Tabelle Ausgeblendete** Vorlagen.

1. Wählen Sie die Vorlagen aus, die ein-/aus- und dann **Anzeigen aus.**

   ![Die ausgewählten Vorlagen, die nicht ausgeblendet sind](media/template-policies-3.png)

   Die ausgewählten Vorlagen werden in der Tabelle **"Anzeigebare Vorlagen"** angezeigt.
3. Klicken Sie auf **Speichern**.

   Ihre neue Vorlagenrichtlinie wird in der Liste **Vorlagenrichtlinien** angezeigt.

## <a name="assign-users-to-the-template-policies"></a>Zuweisen von Benutzern zu den Vorlagenrichtlinien

Benutzer, die einer Richtlinie zugewiesen sind, können nur die angezeigten Vorlagen innerhalb dieser Richtlinie anzeigen.

1. Wählen **Sie unter Vorlagenrichtlinien** eine Richtlinie und dann **Benutzer verwalten aus.**

2. Geben Sie die Benutzer ein, die dieser Richtlinie zugewiesen werden.

   ![Zuweisen von Benutzern zu einer Vorlagenrichtlinie](media/template-policies-4.png)

3. Wählen Sie **Übernehmen aus.**

> [!Note]
> Es kann bis zu 24 Stunden dauern, bis ihre neue Richtlinie für Endbenutzer wirksam wird.

## <a name="size-limits-for-template-policies"></a>Größenbeschränkungen für Vorlagenrichtlinien

Sie können maximal 100 Vorlagen pro Richtlinie ausblenden. Die **Schaltfläche** Ausblenden ist deaktiviert, wenn die angegebene Richtlinie bereits 100 Vorlagen ausgeblendet hat.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Kann ich Teamvorlagenrichtlinien Benutzer batchweise zuweisen?**
  
A: Ja, wir unterstützen die Batchzuordnung für die Vorlagenrichtlinie in PowerShell. Der Richtlinientyp für diese Aktion ist TeamsTemplatePermissionPolicy. [Weitere Informationen](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

**F: Können Gruppen Teamvorlagenrichtlinien zugewiesen werden?**

A: Derzeit nein. Diese Funktionalität wird in Zukunft verfügbar sein.

**F: Wenn eine neue Vorlage erstellt wird, wird die Vorlage in meine Richtlinien einbezogen?**

A: Alle neuen Vorlagen sind standardmäßig sichtbar. Sie können die Vorlage im Admin Center im Abschnitt Vorlagenrichtlinien ausblenden.

**F: Was geschieht, wenn eine Vorlage gelöscht wird?**

A: Alle gelöschten Vorlagen sind in den Vorlagenrichtlinien nicht mehr vorhanden.

**F: Kann ich einer Vorlagenrichtlinie im Teams Admin Center mehrere Benutzer zuweisen?**

A: Ja.

1. Wechseln Sie im Admin Center zu **Benutzer**.
1. Wählen Sie in der Listentabelle Benutzer die Benutzer aus, die Sie einer bestimmten Vorlagenrichtlinie zuweisen möchten.
1. Wählen Sie Einstellungen bearbeiten aus, und ändern Sie das Feld Vorlagenrichtlinien.
1. Wählen Sie Übernehmen aus.
   Weitere [Informationen: Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams – Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).

**F: Wie kann ich alle Benutzer anzeigen, die einer bestimmten Richtlinie zugewiesen sind?**

A: Im Admin Center:

1. Wechseln Sie zum **Abschnitt Benutzer.**
2. Wählen Sie den Filter in der Listentabelle Benutzer aus, und filtern Sie nach der Vorlagenrichtlinie für Teams.
3. Wählen Sie **Übernehmen aus.**

![Ausgewählte Vorlagenrichtlinie und Anzeigen von Benutzern](media/template-policies-5.png)

**F: Kann ich Vorlagenrichtlinien über PowerShell verwalten?**

A: Nein, das Verwalten von Vorlagen in PowerShell wird nicht unterstützt.

**F: Gelten Vorlagenrichtlinien für EDU?**

A: Nein, Vorlagenrichtlinien für EDU werden nicht unterstützt.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teamvorlagen im Admin Center](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [Erstellen einer benutzerdefinierten Teamvorlage](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [Erstellen einer Vorlage aus einem vorhandenen Team](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams – Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies)

- [Batch zuweisen von Benutzern zu einer Richtlinie](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
