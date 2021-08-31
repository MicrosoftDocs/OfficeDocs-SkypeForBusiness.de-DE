---
title: Teams Richtlinienpakete-Pakete für das Gesundheitswesen
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: medium
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Erfahren Sie, wie Sie Team-Richtlinienpakete für Ihre Gesundheitsorganisation verwenden und verwalten.
ms.openlocfilehash: d71945508055ddc7b6f6661d93e8918879d59d23
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731964"
---
# <a name="teams-policy-packages-for-healthcare"></a>Teams Richtlinienpakete-Pakete für das Gesundheitswesen

## <a name="overview"></a>Übersicht

Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Richtlinienpakete vereinfachen, rationalisieren und sorgen für Konsistenz bei der Verwaltung von Richtlinien. Sie können die Einstellungen der Richtlinien im Paket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie können Richtlinienpakete mithilfe des Microsoft Teams Admin Centers oder von PowerShell verwalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

Richtlinienpakete definieren je nach Paket Richtlinien für Folgendes vor:

- Messaging
- Besprechungen
- Anrufe
- App-Setup
- Liveereignisse

Die Teams umfassen derzeit die folgenden Gesundheitsrichtlinien-Pakete.

|Paketname im Microsoft Teams Admin Center|Am besten geeignet für|Beschreibung |
|---------|---------|---------|
|Klinischer Mitarbeiter im Gesundheitswesen  |Klinische Mitarbeiter in Ihrer Gesundheitsorganisation  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, mit denen klinische Mitarbeiter wie Krankenschwestern, Krankenschwestern, Ärzte und Sozialarbeiter uneingeschränkten Zugriff auf Chat, Anrufe, Schichtmanagement und Besprechungen erhalten. |
|Informationsbeauftragter für das Gesundheitswesen  |Informationsbeauftragter in Ihrer Gesundheitsorganisation |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, mit denen Informationsbeauftragte wie IT-Personal, Informatikpersonal, Finanzpersonal und Compliance-Beauftragte uneingeschränkten Zugriff auf Chat, Anrufe und Besprechungen erhalten.|
|Patientenzimmer im Gesundheitswesen  |Geräte des Patientenzimmers|Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patientenzimmer in Ihrer Gesundheitsorganisation gelten.|

![Screenshot der Pakete für die Gesundheitsrichtlinie](media/policy-packages-healthcare.png)

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, leicht identifizieren können. Wenn Sie beispielsweise Klinikern in Ihrer Organisation das Richtlinienpaket für klinische Mitarbeiter im Gesundheitswesen zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen Healthcare_ClinicalWorker erstellt.

![Screenshot der Richtlinien im Paket für klinische Mitarbeiter im Gesundheitswesen](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Beginnen Sie mit Richtlinienpaketen

Um mit den Richtlinienpaketen für das Gesundheitswesen zu beginnen, wählen Sie im Onboarding-Hub des Microsoft Admin Center die Option **Gesundheitswesen** und anschließend **Richtlinieneinstellungen nach Rolle zuweisen**. Wenn Sie bereit sind, entscheiden Sie, welchen Richtlinienpaketen Sie Personen in Ihrer Organisation zuweisen möchten.

Wählen Sie **Richtliniendetails anzeigen**, um mehr über die spezifischen Richtlinien in einem Paket und ihre jeweiligen Einstellungen zu erfahren. Diese können nach der Zuweisung im Teams Admin Center [angepasst werden](manage-policy-packages.md#customize-policies-in-a-policy-package).

Wählen Sie ein oder mehrere Pakete zum Zuweisen aus und klicken Sie dann auf **Weiter**. Sie können nach Personen suchen und sie dem Richtlinienpaket hinzufügen, das für ihre Rolle am besten geeignet ist. Eine Person kann nicht mehr als einem Richtlinienpaket gleichzeitig zugewiesen werden.

Sobald Sie dem richtigen Richtlinienpaket Personen hinzugefügt haben, schließt **Beenden** Ihre Auswahl ab. Sie können weiterhin Richtlinienpakete im Microsoft Teams Admin Center anpassen und verwalten.

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

![Screenshot zum Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-healthcare-assign.png)

Weitere Informationen hierzu finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).

Wenn einem Benutzer eine Richtlinie zugewiesen wurde und Sie ihm dann später eine andere Richtlinie zuweisen, hat die neuere Vorrang.

#### <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

**Dieses Feature ist derzeit lediglich als private Vorschau verfügbar**

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert. Diese Methode wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, sie eignet sich aber auch für größere Gruppen.

Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einer Gruppe zuweisen](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Ein Richtlinienpaket einer großen Anzahl von Benutzern (Batch) zuweisen

Wenn Sie ein Richtlinienpaket einer großen Anzahl von Benutzern gleichzeitig zuweisen möchten, verwenden Sie hierfür die Richtlinienpaket-Batch-Zuweisung. Verwenden Sie das Cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), um einen Benutzer-Batch und das Richtlinienpaket zu senden, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Sie können Benutzer durch Angabe ihrer Objekt-ID, des UPN, der SIP-Adresse oder der E-Mail-Adresse hinzufügen. Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einem Batch von Benutzern zuweisen](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinienpaketen in Teams](manage-policy-packages.md)

[Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen](assign-policy-packages.md)
