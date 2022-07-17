---
title: Teams-Richtlinienpakete für Mitarbeiter in Service und Produktion
ms.author: v-lanachin
author: LanaChin
manager: samanro
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: high
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft 365 for frontline workers
description: Erfahren Sie, wie Sie Teams-Richtlinienpakete für Mitarbeiter in Service und Produktion in Ihrer Organisation verwenden und verwalten.
ms.openlocfilehash: 20f0f926a50a56140bab8d20c9c663e0020ac3c0
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819574"
---
# <a name="teams-policy-packages-for-frontline-workers"></a>Teams-Richtlinienpakete für Mitarbeiter in Service und Produktion

## <a name="overview"></a>Übersicht

Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Richtlinienpakete vereinfachen, rationalisieren und sorgen für Konsistenz bei der Verwaltung von Richtlinien.

Sie können die Einstellungen der Richtlinien im Paket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie können Richtlinienpakete mithilfe des Microsoft Teams Admin Centers oder von PowerShell verwalten.

Richtlinienpakete definieren je nach Paket Richtlinien für Folgendes vor:

- Messaging
- Besprechungen
- Anrufe
- App-Setup
- Liveereignisse

Teams enthält die Richtlinienpakete **Vorgesetzter in Service und Produktion** und **Mitarbeiter in Service und Produktion**.

|Paketname im Microsoft Teams Admin Center|Beschreibung |
|---------|---------|
|**Vorgesetzter in Service und Produktion** |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Frontline-Manager in Ihrem Unternehmen an. |
|**Mitarbeiter in Service und Produktion**  |Erstellt einen Satz von Richtlinien und wendet diese Einstellungen auf Mitarbeiter in Ihrem Unternehmen an.|

:::image type="content" source="media/policy-packages-flw.png" alt-text="Screenshot der Frontline-Richtlinienpakete" lightbox="media/policy-packages-flw.png":::

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, leicht identifizieren können. Wenn Sie beispielsweise das Richtlinienpaket Frontline-Manager den Filialleitern in Ihrer Organisation zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen Frontline_Manager erstellt.

:::image type="content" source="media/policy-packages-flw-frontline-manager.png" alt-text="Screenshot der Richtlinien im Frontline-Manager-Richtlinienpaket" lightbox="media/policy-packages-flw-frontline-manager.png":::

## <a name="manage-policy-packages"></a>Verwalten von Richtlinienpaketen

### <a name="view"></a>Anzeigen

Sehen Sie sich die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen. Gehen Sie in der linken Navigation des Microsoft Teams-Verwaltungscenters zu **Richtlinienpakete**, wählen Sie den Paketnamen und dann den Richtliniennamen aus.

Überprüfen Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie sie mehr oder weniger restriktiv einstellen müssen, damit sie den Anforderungen Ihrer Organisation entsprechen.

### <a name="customize"></a>Anpassung

Passen Sie die Einstellungen von Richtlinien im Richtlinienpaket ggf. an die Anforderungen Ihrer Organisation an. Alle Änderungen, die Sie an den Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen wird. Um die Einstellungen einer Richtlinie in einem Richtlinienpaket zu bearbeiten, gehen Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Richtlinienpakete**, wählen Sie das Richtlinienpaket aus, wählen Sie den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** aus.

Sie können die Einstellungen für Richtlinien in einem Paket auch ändern, nachdem Sie das Richtlinienpaket zugewiesen haben. Weitere Informationen hierzu finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Zuweisen

Weisen Sie das Richtlinienpaket Benutzern zu. Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie ihm dann später eine andere Richtlinie zuweisen, hat die neuere Vorrang.

> [!NOTE]
> Jeder Benutzer benötigt das Add-On für erweiterte Kommunikation, um eine benutzerdefinierte Richtlinienpaketzuweisung zu erhalten. Weitere Informationen finden Sie unter [Add-On für erweiterte Kommunikation für Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Ein Richtlinienpaket einem oder mehreren Benutzern zuweisen

Um einem oder mehreren Benutzern ein Richtlinienpaket zuzuweisen, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **Richtlinienpakete**, und wählen Sie dann **Benutzer verwalten** aus.  

:::image type="content" source="media/policy-packages-flw-frontline-manager-assign.png" alt-text="Screenshot: Zuweisen eines Richtlinienpakets zu einem Benutzer im Teams Admin Center." lightbox="media/policy-packages-flw-frontline-manager-assign.png":::

Weitere Informationen finden Sie unter [Zuweisen von Richtlinienpaketen zu Benutzern](assign-policy-packages.md#assign-a-policy-package-to-users).

#### <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

Mit der Zuweisung von Richtlinienpaketen zu Gruppen können Sie einer Gruppe von Benutzern mehrere Richtlinien zuweisen, z. B. eine Sicherheitsgruppe oder Verteilerliste. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert. Diese Methode wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, sie eignet sich aber auch für größere Gruppen.

Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einer Gruppe zuweisen](assign-policy-packages.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Ein Richtlinienpaket einer großen Anzahl von Benutzern (Batch) zuweisen

Wenn Sie ein Richtlinienpaket einer großen Anzahl von Benutzern gleichzeitig zuweisen möchten, verwenden Sie hierfür die Richtlinienpaket-Batch-Zuweisung. Verwenden Sie das Cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), um einen Benutzer-Batch und das Richtlinienpaket zu senden, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Sie können Benutzer anhand ihrer Objekt-ID oder SIP-Adresse (Session Initiation Protocol) angeben. Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einem Batch von Benutzern zuweisen](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Richtlinienpaketen in Teams](manage-policy-packages.md)
- [Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen](assign-policy-packages.md)
