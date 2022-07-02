---
title: Verwalten von Teamvorlagen im Admin Center
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informationen zum Verwalten von Teamvorlagen im Admin Center
ms.openlocfilehash: 9f2044f059414f9afe1ff335f8204cd26861164b
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605904"
---
# <a name="manage-team-templates-in-the-admin-center"></a>Verwalten von Teamvorlagen im Admin Center

Verwalten Sie die Teamvorlagen, die Ihren Endbenutzern angezeigt werden, indem Sie Vorlagenrichtlinien im Admin Center erstellen. Innerhalb jeder Vorlagenrichtlinie können Sie festlegen, welche Vorlagen angezeigt oder ausgeblendet werden.
Weisen Sie verschiedenen Vorlagenrichtlinien unterschiedliche Benutzer zu, sodass Ihre Benutzer nur die Teilmenge der angegebenen Teamvorlagen anzeigen.

Schauen Sie sich dieses kurze Video an, um zu erfahren, wie Vorlagenrichtlinien verwaltet werden.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-templates-policies-and-assign-available-templates"></a>Erstellen von Vorlagenrichtlinien und Zuweisen verfügbarer Vorlagen

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Wechseln Sie zu **Den Richtlinien für Teams-Vorlagen** > .

3. Choose **Add**.

    ![Die Vorlagenrichtlinien sind ausgewählt, und "Hinzufügen" ist hervorgehoben.](media/template-policies-1.png)

1. Geben Sie der Richtlinie einen Namen, und fügen Sie eine kurze Beschreibung hinzu.

2. Wählen Sie in der Liste der **sichtbaren Vorlagen** die Vorlagen aus, die Sie ausblenden möchten, und wählen Sie dann " **Ausblenden" aus**.

    ![Die ausgewählten Vorlagen mit hervorgehobenem Ausblenden.](media/template-policies-2.png)

    Sie können die Vorlagen, die Sie ausblenden möchten, in der Liste **"Ausgeblendete Vorlagen** " anzeigen.

1. Um bestimmte Vorlagen einzublenden, wechseln Sie zur Liste **"Ausgeblendete Vorlagen** ".

2. Wählen Sie die einzublendenden Vorlagen und dann " **Anzeigen"** aus.

   ![Die ausgewählten Vorlagen, die nicht ausgeblendet sind.](media/template-policies-3.png)

   Die ausgewählten Vorlagen werden in der Liste der **sichtbaren Vorlagen** angezeigt.
3. Klicken Sie auf **Speichern**.

   Ihre neue Vorlagenrichtlinie wird in der Liste der **Vorlagenrichtlinien** angezeigt.

## <a name="assign-templates-policies-to-users"></a>Zuweisen von Vorlagenrichtlinien zu Benutzern

Sie können eine Vorlagenrichtlinie direkt benutzern zuweisen, entweder einzeln oder im Großen und Ganzen über eine Batchzuordnung. Beachten Sie, dass es bis zu 24 Stunden dauern kann, bis Ihre neue Richtlinie für Ihre Benutzer wirksam wird.

> [!Note]
> Derzeit wird das Zuweisen von Vorlagenrichtlinien zu Benutzern basierend auf der Gruppenmitgliedschaft, z. B. allen Benutzern in einer Sicherheitsgruppe, nicht unterstützt. Diese Funktion wird in Zukunft verfügbar sein.

Eine Übersicht über die Methoden zum Zuweisen von Richtlinien in Teams finden [Sie unter Zuweisen von Richtlinien in Teams](policy-assignment-overview.md).

### <a name="assign-a-templates-policy-to-individual-users"></a>Zuweisen einer Vorlagenrichtlinie zu einzelnen Benutzern

Sie können das Teams Admin Center oder PowerShell verwenden, um einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig eine Vorlagenrichtlinie zuzuweisen. Weitere Informationen finden Sie unter [Zuweisen einer Richtlinie zu einzelnen Benutzern](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

### <a name="assign-a-templates-policy-to-a-batch-of-users"></a>Zuweisen einer Vorlagenrichtlinie zu einer Gruppe von Benutzern

Sie können PowerShell verwenden, um großen Gruppen von Benutzern gleichzeitig eine Vorlagenrichtlinie zuzuweisen. Verwenden Sie dazu das Cmdlet ["New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) " zusammen mit "TeamsTemplatePermissionPolicy ```PolicyType``` ", um eine Reihe von Benutzern und die Vorlagenrichtlinie zu übermitteln, die Sie zuweisen möchten. Zum Beispiel: 

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das Cmdlet ["Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) " verwenden, um den Fortschritt und Status der Zuordnungen in einem Batch nachzuverfolgen.

Weitere Informationen finden Sie unter [Zuweisen einer Richtlinie zu einer Gruppe von Benutzern mitHilfe von PowerShell](assign-policies-users-and-groups.md#use-powershell-method).

## <a name="size-limits-for-templates-policies"></a>Größenbeschränkungen für Vorlagenrichtlinien

Sie können maximal 100 Vorlagen pro Richtlinie ausblenden. Die Schaltfläche " **Ausblenden** " ist deaktiviert, wenn in der angegebenen Richtlinie bereits 100 Vorlagen ausgeblendet sind.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Wenn eine neue Vorlage erstellt wird, wird die Vorlage in meine Richtlinien einbezogen?**

A: Alle neuen Vorlagen sind standardmäßig sichtbar. Sie können die Vorlage im Admin Center im Abschnitt Vorlagenrichtlinien ausblenden.

**F: Was geschieht, wenn eine Vorlage gelöscht wird?**

Antwort: Alle gelöschten Vorlagen sind in keiner Vorlagenrichtlinien mehr vorhanden.

**F: Kann ich mehrere Benutzer einer Vorlagenrichtlinie im Teams Admin Center zuweisen?**

A: Ja.

1. Wechseln Sie im Teams Admin Center zu **"Benutzer** > **verwalten"**.
1. Wählen Sie in der Liste der Benutzer die Benutzer aus, die Sie der Vorlagenrichtlinie zuweisen möchten.
1. Wählen Sie **"Einstellungen bearbeiten"** und dann unter **"Vorlagenrichtlinie**" die Richtlinie aus, die Sie zuweisen möchten.
1. Wählen Sie **"Übernehmen" aus**.

Weitere Informationen finden Sie unter [Zuweisen einer Richtlinie zu einzelnen Benutzern](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

**F: Gewusst wie alle Benutzer anzeigen, die einer bestimmten Richtlinie zugewiesen sind?**

A: Im Teams Admin Center:

1. Wechseln Sie zu **"Benutzer** > **verwalten"**.
2. Wählen Sie **"Filter**" aus, legen Sie einen Filter für die Vorlagenrichtlinie fest, und wählen Sie dann **"Übernehmen"** aus.

    ![Die ausgewählte Vorlagenrichtlinie und die Benutzer anzeigen.](media/template-policies-5.png)

**F: Kann ich Vorlagenrichtlinien über PowerShell verwalten?**

A: Nein, das Verwalten von Vorlagenrichtlinien in PowerShell wird nicht unterstützt. Sie können PowerShell jedoch verwenden, um Benutzern [Vorlagenrichtlinien zuzuweisen](#assign-templates-policies-to-users) .

**F: Gelten Vorlagenrichtlinien für EDU?**

Antwort: Nein, Vorlagenrichtlinien für EDU werden nicht unterstützt.

## <a name="related-articles"></a>Verwandte Artikel

- [Erste Schritte mit Teamvorlagen im Admin Center](./get-started-with-teams-templates-in-the-admin-console.md)

- [Erstellen einer benutzerdefinierten Teamvorlage](./create-a-team-template.md)

- [Erstellen einer Vorlage aus einem vorhandenen Team](./create-template-from-existing-team.md)

- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](./create-template-from-existing-template.md)

- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams – Microsoft Teams \| Microsoft-Dokumentation](./policy-assignment-overview.md)

- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
