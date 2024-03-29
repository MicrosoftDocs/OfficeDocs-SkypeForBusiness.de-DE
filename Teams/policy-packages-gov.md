---
title: Teams-Richtlinienpakete für Behörden
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Teams-Richtlinienpakete für Ihre Regierungsorganisation verwenden und verwalten.
ms.openlocfilehash: fdaacb8b551c1031d71c522dffdbc4afd9f551a8
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564093"
---
# <a name="teams-policy-packages-for-government"></a>Teams-Richtlinienpakete für Behörden

> [!NOTE]
> Richtlinienpakete sind derzeit in Microsoft 365 Government GCC High- oder DoD-Bereitstellungen nicht verfügbar.

## <a name="overview"></a>Übersicht

Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Richtlinienpakete vereinfachen, rationalisieren und sorgen für Konsistenz bei der Verwaltung von Richtlinien. Sie können die Einstellungen der Richtlinien im Paket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie können Richtlinienpakete mithilfe des Microsoft Teams Admin Centers oder von PowerShell verwalten.

Richtlinienpakete definieren je nach Paket Richtlinien für Folgendes vor:

- Messaging
- Besprechungen
- Anrufe
- App-Setup
- Liveereignisse

Teams enthält derzeit die folgenden Richtlinienpakete für Behörden.

|Paketname im Microsoft Teams Admin Center|Am besten geeignet für|Beschreibung |
|---------|---------|---------|
|Öffentlicher Sicherheitsbeauftragter  |Öffentliche Sicherheitsbeauftragte in Ihrer Regierungsorganisation  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten. |
|Vorgesetzter in Service und Produktion  |Vorgesetzte in Service und Produktion in Ihrer Regierungsorganisation |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Vorgesetzte in Service und Produktion in Ihrer Organisation an.|
|Mitarbeiter in Service und Produktion  |Mitarbeiter in Service und Produktion in Ihrer Regierungsorganisation |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Mitarbeiter in Service und Produktion in Ihrer Organisation an.|

![Screenshot der Richtlinienpakete für das Gesundheitswesen.](media/policy-packages-gov.png)

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, leicht identifizieren können. Wenn Sie z. B. das Richtlinienpaket des öffentlichen Sicherheitsbeauftragten Benutzern in Ihrer Organisation zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen PublicSafety_Officer erstellt.

![Screenshot der Richtlinien im Paket für klinische Mitarbeiter im Gesundheitswesen.](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Verwalten von Richtlinienpaketen

### <a name="view"></a>Anzeigen

Sehen Sie sich die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **Richtlinienpakete** aus, dann den gewünschten Paketnamen und schließlich den Namen der Richtlinie.

Überprüfen Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie sie mehr oder weniger restriktiv einstellen müssen, damit sie den Anforderungen Ihrer Organisation entsprechen.

### <a name="customize"></a>Anpassung

Passen Sie die Einstellungen von Richtlinien im Richtlinienpaket ggf. an die Anforderungen Ihrer Organisation an. Alle Änderungen, die Sie an den Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen wird. Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das entsprechende Richtlinienpaket und dann den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie anschließend **Bearbeiten** aus.

Sie können die Einstellungen für Richtlinien in einem Paket auch ändern, nachdem Sie das Richtlinienpaket zugewiesen haben. Weitere Informationen hierzu finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Zuweisen

Weisen Sie das Richtlinienpaket Benutzern zu. Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie ihm dann später eine andere Richtlinie zuweisen, hat die neuere Vorrang.

> [!NOTE]
> Jeder Benutzer benötigt das Add-On für erweiterte Kommunikation, um eine benutzerdefinierte Richtlinienpaketzuweisung zu erhalten. Weitere Informationen finden Sie unter [Add-On für erweiterte Kommunikation für Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Ein Richtlinienpaket einem oder mehreren Benutzern zuweisen

Um einem oder mehreren Benutzern ein Richtlinienpaket zuzuweisen, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **Richtlinienpakete**, und wählen Sie dann **Benutzer verwalten** aus.  

![Screenshot zur Vorgehensweise zum Zuweisen eines Richtlinienpakets im Admin Center.](media/policy-packages-healthcare-assign.png)

Weitere Informationen hierzu finden Sie unter [Zuweisen eines Richtlinienpakets](assign-policy-packages.md).

Wenn einem Benutzer eine Richtlinie zugewiesen wurde und Sie ihm dann später eine andere Richtlinie zuweisen, hat die neuere Vorrang.

#### <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

**Dieses Feature ist derzeit lediglich als private Vorschau verfügbar**

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert. Diese Methode wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, sie eignet sich aber auch für größere Gruppen.

Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einer Gruppe zuweisen](assign-policy-packages.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Ein Richtlinienpaket einer großen Anzahl von Benutzern (Batch) zuweisen

Wenn Sie ein Richtlinienpaket einer großen Anzahl von Benutzern gleichzeitig zuweisen möchten, verwenden Sie hierfür die Richtlinienpaket-Batch-Zuweisung. Verwenden Sie das Cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), um einen Benutzer-Batch und das Richtlinienpaket zu senden, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Sie können Benutzer durch Angabe ihrer Objekt-ID, des UPN, der SIP-Adresse oder der E-Mail-Adresse hinzufügen. Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einem Batch von Benutzern zuweisen](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinienpaketen in Teams](manage-policy-packages.md)

[Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen](assign-policy-packages.md)
