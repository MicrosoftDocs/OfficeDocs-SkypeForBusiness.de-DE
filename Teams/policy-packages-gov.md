---
title: Teams-Richtlinien Pakete für Behörden
author: lanachin
ms.author: v-lanac
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
description: Hier erfahren Sie, wie Sie Teamrichtlinien Pakete für Ihre Regierungsorganisation verwenden und verwalten.
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804023"
---
# <a name="teams-policy-packages-for-government"></a>Teams-Richtlinien Pakete für Behörden

> [!NOTE]
> Richtlinien Pakete sind derzeit in den Microsoft 365 Government gcc-oder DoD-Bereitstellungen nicht verfügbar.

## <a name="overview"></a>Übersicht

Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen. Richtlinienpakete vereinfachen und rationalisieren Richtlinien und lassen Sie diese konsistent verwalten. Sie können die Einstellungen der Richtlinien im Paket entsprechend den Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie können Richtlinien Pakete mit dem Microsoft Teams Admin Center oder mit PowerShell verwalten.

Richtlinien Pakete definieren für die folgenden Richtlinien je nach Paket:

- Messaging
- Besprechungen
- Anrufe
- App-Setup
- Liveereignisse

Teams umfasst derzeit die folgenden Richtlinien Pakete für Behörden.

|Paket Name im Microsoft Teams Admin Center|Am besten geeignet für|Beschreibung |
|---------|---------|---------|
|Beauftragter für öffentliche Sicherheit  |Beauftragte für öffentliche Sicherheit in ihrer Regierungsorganisation  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten. |
|First-Manager  |First-Manager in ihrer Regierungsorganisation |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf First-Manager in Ihrer Organisation an.|
|First-Worker  |Erste Arbeitskräfte in ihrer Regierungsorganisation |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Mitarbeiter in Ihrer Organisation in erster Linie an.|

![Screenshot der Gesundheitsrichtlinien Pakete](media/policy-packages-gov.png)

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können. Wenn Sie beispielsweise Benutzern in Ihrer Organisation das Richtlinienpaket für das öffentliche Sicherheitsbeauftragte zuweisen, wird eine Richtlinie mit dem Namen PublicSafety_Officer für jede Richtlinie im Paket erstellt.

![Screenshot der Richtlinien im Healthcare Clinical Worker-Paket](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Verwalten von Richtlinienpaketen

### <a name="view"></a>Ansicht

Zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen. Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers **Richtlinien Pakete**aus, wählen Sie den Paketnamen aus, und wählen Sie dann den Richtliniennamen aus.

Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.

### <a name="customize"></a>Anpassen

Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket nach Bedarf an die Anforderungen Ihrer Organisation an. Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist. Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das Richtlinienpaket aus, wählen Sie den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten**aus.

Beachten Sie, dass Sie auch die Einstellungen von Richtlinien in einem Paket ändern können, nachdem Sie das Richtlinienpaket zugewiesen haben. Weitere Informationen finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Zuweisen

Weisen Sie das Richtlinienpaket Benutzern zu. Wenn Sie einem oder mehreren Benutzern ein Richtlinienpaket zuweisen möchten, klicken Sie auf **Benutzer verwalten**. Sie können auch [PowerShell verwenden](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) , um einem Richtlinienpaket große Batches von Benutzern zuzuweisen. 

Eine schrittweise Anleitung zum Zuweisen eines Richtlinienpakets mit dem Microsoft Teams Admin Center oder PowerShell finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).

![Screenshot: Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-gov-assign.png)

Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie später eine andere Richtlinie zuweisen, hat die letzte Aufgabe Vorrang.

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinienpaketen in Teams](manage-policy-packages.md)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md) 
