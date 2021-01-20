---
title: Richtlinienpakete für Teams für Behörden
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinienpakete für Teams für Ihre Regierungsorganisation verwenden und verwalten.
ms.openlocfilehash: 2841fbf523f49c5784045cc6cf960e846b45aa9b
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909079"
---
# <a name="teams-policy-packages-for-government"></a>Richtlinienpakete für Teams für Behörden

> [!NOTE]
> Richtlinienpakete sind derzeit in Bereitstellungen von Microsoft 365 Government GCC High oder DoD nicht verfügbar.

## <a name="overview"></a>Übersicht

Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Richtlinienpakete vereinfachen und rationalisieren Richtlinien und lassen Sie diese konsistent verwalten. Sie können die Einstellungen der Richtlinien im Paket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, denen dieses Paket zugewiesen ist, die aktualisierten Einstellungen. Sie können Richtlinienpakete über das Microsoft Teams Admin Center oder PowerShell verwalten.

In Richtlinienpaketen werden je nach Paket Vordefinieren von Richtlinien für folgendes definiert:

- Messaging
- Besprechungen
- Anrufe
- Einrichten der App
- Liveereignisse

Teams enthält derzeit die folgenden Richtlinienpakete für Behörden.

|Paketname im Microsoft Teams Admin Center|Am besten geeignet für|Beschreibung |
|---------|---------|---------|
|Public Safety Officer  |Public Safety Officers in Ihrer Regierungsorganisation  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten. |
|Frontline Manager  |Frontline manager in your government organization |Erstellt einen Satz von Richtlinien und wendet diese Einstellungen auf Frontline Manager in Ihrer Organisation an.|
|Mitarbeiter an vorderer Front  |Mitarbeiter an vorder front in Ihrer Regierungsorganisation |Erstellt einen Satz von Richtlinien und wendet diese Einstellungen auf Frontline Workers in Ihrer Organisation an.|

![Screenshot der Richtlinienpakete für das Gesundheitswesen](media/policy-packages-gov.png)

Jede einzelne Richtlinie wird mit dem Namen des Richtlinienpakets bezeichnet, sodass Sie die Mit einem Richtlinienpaket verknüpften Richtlinien leicht erkennen können. Wenn Sie beispielsweise benutzern in Ihrer Organisation das Richtlinienpaket für den öffentlichen Sicherheitsbeauftragte zuweisen, wird für jede Richtlinie im Paket PublicSafety_Officer Richtlinie "PublicSafety_Officer" erstellt.

![Screenshot der Richtlinien im Paket für klinische Mitarbeiter im Gesundheitswesen](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Verwalten von Richtlinienpaketen

### <a name="view"></a>Anzeigen

Sehen Sie sich die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **Richtlinienpakete** aus, dann den gewünschten Paketnamen und schließlich den Namen der Richtlinie.

Überprüfen Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie sie mehr oder weniger restriktiv einstellen müssen, damit sie den Anforderungen Ihrer Organisation entsprechen.

### <a name="customize"></a>Anpassung

Passen Sie die Einstellungen von Richtlinien im Richtlinienpaket ggf. an die Anforderungen Ihrer Organisation an. Alle Änderungen, die Sie an den Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen wird. Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das entsprechende Richtlinienpaket und dann den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie anschließend **Bearbeiten** aus.

Sie können die Einstellungen für Richtlinien in einem Paket auch ändern, nachdem Sie das Richtlinienpaket zugewiesen haben. Weitere Informationen hierzu finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Zuweisen

Weisen Sie das Richtlinienpaket Benutzern zu. Wenn einem Benutzer eine Richtlinie zugewiesen wurde und Sie ihm dann später eine andere Richtlinie zuweisen, hat die neuere Vorrang.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Ein Richtlinienpaket einem oder mehreren Benutzern zuweisen

Um einem oder mehreren Benutzern ein Richtlinienpaket zuzuweisen, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **Richtlinienpakete**, und wählen Sie dann **Benutzer verwalten** aus.  

![Screenshot zur Vorgehensweise zum Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-healthcare-assign.png)

Weitere Informationen hierzu finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).

Wenn einem Benutzer eine Richtlinie zugewiesen wurde und Sie ihm dann später eine andere Richtlinie zuweisen, hat die neuere Vorrang.

#### <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

**Dieses Feature ist derzeit lediglich als private Vorschau verfügbar**

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert. Diese Methode wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, sie eignet sich aber auch für größere Gruppen.

Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einer Gruppe zuweisen](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Ein Richtlinienpaket einer großen Anzahl von Benutzern (Batch) zuweisen

Wenn Sie ein Richtlinienpaket einer großen Anzahl von Benutzern gleichzeitig zuweisen möchten, verwenden Sie hierfür die Richtlinienpaket-Batch-Zuweisung. Verwenden Sie das Cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), um einen Benutzer-Batch und das Richtlinienpaket zu senden, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Sie können Benutzer durch Angabe ihrer Objekt-ID, des UPN, der SIP-Adresse oder der E-Mail-Adresse hinzufügen. Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einem Batch von Benutzern zuweisen](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinienpaketen in Teams](manage-policy-packages.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md) 
