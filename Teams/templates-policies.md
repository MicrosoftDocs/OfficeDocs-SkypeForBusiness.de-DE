---
title: Verwalten Teams Vorlagen im Admin Center
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
description: Erfahren Sie, wie Sie Teams Vorlagen im Admin Center verwalten.
ms.openlocfilehash: db28d1fa3c84210c3f1e2d80e74a59252f922258
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093925"
---
# <a name="manage-teams-templates-in-the-admin-center"></a>Verwalten Teams Vorlagen im Admin Center

Verwalten Sie Teams Vorlagen, die Endbenutzer sehen, indem Sie Vorlagenrichtlinien im Admin Center erstellen. Innerhalb jeder Vorlagenrichtlinie können Sie festlegen, welche Vorlagen ein- oder ausgeblendet werden sollen.
Weisen Sie verschiedene Benutzer verschiedenen Vorlagenrichtlinien zu, damit Ihre Benutzer nur die Teilmenge Teams Vorlagen anzeigen können.

In diesem kurzen Video erfahren Sie, wie Sie Vorlagenrichtlinien verwalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a>Erstellen von Vorlagenrichtlinien und Zuweisen verfügbarer Vorlagen

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Erweitern **Teams**  >  **Richtlinien für Vorlagen**.

3. Klicken Sie auf **Hinzufügen**.

    ![Die Vorlagenrichtlinien sind ausgewählt, und Hinzufügen ist hervorgehoben.](media/template-policies-1.png)

1. Füllen Sie **im Abschnitt Einstellungen** Vorlagenrichtlinien die folgenden Felder aus:

    - Name der Vorlagenrichtlinie

    - Kurzbeschreibung der Vorlagenrichtlinie

2. Wählen Sie in **der Tabelle Ansichtsvorlagen** die Vorlagen aus, die Sie ausblenden möchten, und wählen Sie ausblenden **aus.**

    ![Die ausgewählten Vorlagen mit hervorgehobener Option 'Ausblenden'](media/template-policies-2.png)

    Die Vorlagen, die Sie ausgewählt haben, um sie in der Tabelle Ausgeblendete Vorlagen **auszublenden, werden** angezeigt.

1. Wenn Sie bestimmte Vorlagen ein-/ein- en wieder ein- en, scrollen Sie zur **Tabelle Ausgeblendete** Vorlagen.

2. Wählen Sie die Vorlagen aus, die Sie ein- oder auswählen, und wählen Sie dann **Anzeigen aus.**

   ![Die ausgewählten, nicht ausgeblendeten Vorlagen](media/template-policies-3.png)

   Die ausgewählten Vorlagen werden in der Tabelle mit den **anzeigebaren Vorlagen** angezeigt.
3. Klicken Sie auf **Speichern**.

   Ihre neue Vorlagenrichtlinie wird in der Liste **Vorlagenrichtlinien** angezeigt.

## <a name="assign-users-to-the-template-policies"></a>Zuweisen von Benutzern zu den Vorlagenrichtlinien

Benutzer, die einer Richtlinie zugewiesen sind, können nur die anzeigebaren Vorlagen innerhalb dieser Richtlinie anzeigen.

1. Wählen **Sie in Vorlagenrichtlinien** eine Richtlinie aus, und wählen Sie dann **Benutzer verwalten aus.**

2. Geben Sie die Benutzer ein, die dieser Richtlinie zugewiesen werden soll.

   ![Zuweisen von Benutzern zu einer Vorlagenrichtlinie](media/template-policies-4.png)

3. Wählen Sie **Übernehmen aus.**

> [!Note]
> Es kann bis zu 24 Stunden dauern, bis die neue Richtlinie für Endbenutzer wirksam wird.

## <a name="size-limits-for-template-policies"></a>Größenbeschränkungen für Vorlagenrichtlinien

Sie können maximal 100 Vorlagen pro Richtlinie ausblenden. Die **Schaltfläche** Ausblenden ist deaktiviert, wenn die angegebene Richtlinie bereits 100 Vorlagen ausgeblendet hat.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Kann ich Benutzer richtlinien für Teamvorlagen in Batch zuweisen?**
  
A: Ja, wir unterstützen die Batchzuordnung für Vorlagenrichtlinien in PowerShell. Der Richtlinientyp für diese Aktion ist TeamsTemplatePermissionPolicy. [Weitere Informationen](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

**F: Können Gruppen Richtlinien für Teamvorlagen zugewiesen werden?**

A: Derzeit nein. Diese Funktionalität wird in Zukunft zur Verfügung stehen.

**F: Wird eine neue Vorlage erstellt, wird sie in meine Richtlinien eingeschlossen?**

A: Alle neuen Vorlagen sind standardmäßig sichtbar. Sie können die Vorlage im Admin Center im Abschnitt Vorlagenrichtlinien ausblenden.

**F: Was geschieht, wenn eine Vorlage gelöscht wird?**

A: Gelöschte Vorlagen sind in den Vorlagenrichtlinien nicht mehr vorhanden.

**F: Kann ich einer Vorlagenrichtlinie im Teams mehrere Benutzer zuweisen?**

A: Ja.

1. Wechseln Sie im Admin Center zu **Benutzer**.
1. Wählen Sie in der Liste Benutzer die Benutzer aus, die Sie einer bestimmten Vorlagenrichtlinie zuweisen möchten.
1. Wählen Sie Einstellungen bearbeiten aus, und ändern Sie das Feld Richtlinien für Vorlagen.
1. Wählen Sie Übernehmen aus.
   Weitere Informationen finden Sie unter Zuweisen von Richtlinien zu Microsoft Teams [– Microsoft Teams \| Microsoft Docs.](./assign-policies.md#assign-a-policy-to-a-batch-of-users)

**F: Wie kann ich alle Benutzer anzeigen, die einer bestimmten Richtlinie zugewiesen wurden?**

A: Im Admin Center:

1. Wechseln Sie zum **Abschnitt** Benutzer.
2. Wählen Sie den Filter in der Liste Benutzer aus, und filtern Sie nach der Teams-Vorlagenrichtlinie.
3. Wählen Sie **Übernehmen aus.**

![Ausgewählte Vorlagenrichtlinie und Anzeigen von Benutzern](media/template-policies-5.png)

**F: Kann ich Vorlagenrichtlinien über PowerShell verwalten?**

A: Nein, das Verwalten von Vorlagen in PowerShell wird nicht unterstützt.

**F: Gelten Vorlagenrichtlinien für EDU?**

A: Nein, Vorlagenrichtlinien für EDU werden nicht unterstützt.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teamvorlagen im Admin Center](./get-started-with-teams-templates-in-the-admin-console.md)

- [Erstellen einer benutzerdefinierten Teamvorlage](./create-a-team-template.md)

- [Erstellen einer Vorlage aus einem vorhandenen Team](./create-template-from-existing-team.md)

- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](./create-template-from-existing-template.md)

- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams – Microsoft Teams \| Microsoft Docs](./assign-policies.md)

- [Batch zum Zuweisen von Benutzern zu einer Richtlinie](/powershell/module/teams/new-csbatchpolicyassignmentoperation)