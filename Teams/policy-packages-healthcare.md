---
title: Teams-Richtlinien Pakete für Healthcare
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Hier erfahren Sie, wie Sie Teams-Richtlinien Pakete für Ihre Gesundheitsorganisation verwenden und verwalten.
ms.openlocfilehash: 6c14cc82a7e2e16780eb50c04064955aad4e4eb7
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790647"
---
# <a name="teams-policy-packages-for-healthcare"></a>Teams-Richtlinien Pakete für Healthcare

## <a name="overview"></a>Übersicht

Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen. Richtlinienpakete vereinfachen und rationalisieren Richtlinien und lassen Sie diese konsistent verwalten. Sie können die Einstellungen der Richtlinien im Paket entsprechend den Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie können Richtlinien Pakete mit dem Microsoft Teams Admin Center oder mit PowerShell verwalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

Richtlinien Pakete definieren für die folgenden Richtlinien je nach Paket:

- Messaging
- Besprechungen
- Anrufe
- App-Setup
- Liveereignisse

Teams umfasst derzeit die folgenden Gesundheitsrichtlinien Pakete.

|Paket Name im Microsoft Teams Admin Center|Am besten geeignet für|Beschreibung |
|---------|---------|---------|
|Klinischer Mitarbeiter im Gesundheitswesen  |Klinische Mitarbeiter in Ihrer Gesundheitsorganisation  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die klinischen Mitarbeitern wie registrierten Krankenschwestern, Krankenschwestern, Ärzten und Sozialarbeitern vollen Zugriff auf Chats, Anrufe, Schicht Verwaltung und Besprechungen ermöglichen. |
|Healthcare Information Worker  |Information Worker in Ihrer Gesundheitsorganisation |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Worker wie IT-Personal, Informatik Personal, Finanz Personal und Compliance Officer, vollständigen Zugriff auf Chats, Anrufe und Besprechungen bereitstellen.|
|Patientenzimmer im Gesundheitswesen  |Patientenraum Geräte|Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patienten Räume in Ihrer Gesundheitsorganisation gelten.|

![Screenshot der Gesundheitsrichtlinien Pakete](media/policy-packages-healthcare.png)

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können. Wenn Sie beispielsweise dem Klinikpersonal in Ihrer Organisation das Clinical Worker-Richtlinienpaket für medizinische Versorgung zuweisen, wird eine Richtlinie mit dem Namen Healthcare_ClinicalWorker für jede Richtlinie im Paket erstellt.

![Screenshot der Richtlinien im Healthcare Clinical Worker-Paket](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Erste Schritte mit Richtlinien Paketen

Um Ihnen den Einstieg in die Gesundheitsrichtlinien Pakete zu verschaffen, wählen Sie im Microsoft Admin Center-Onboarding-Hub **Healthcare Basics** aus, und wählen Sie dann **Richtlinieneinstellungen nach Rolle zuweisen** aus. Wenn Sie bereit für die ersten Schritte sind, entscheiden Sie, welchen Richtlinien Paketen Sie Personen in Ihrer Organisation zuweisen möchten.

Wählen Sie **Richtliniendetails anzeigen** aus, um weitere Informationen zu den spezifischen Richtlinien in einem Paket und den jeweiligen Einstellungen zu erhalten. Diese können nach der Zuweisung im Team Admin Center [angepasst werden](manage-policy-packages.md#customize-policies-in-a-policy-package) .

Wählen Sie ein oder mehrere Pakete aus, die Sie zuweisen möchten, und klicken Sie dann auf **weiter** . Sie können dem Richtlinienpaket, das sich am besten für ihre Rolle eignet, nach Personen suchen und Sie hinzufügen. Eine Person kann nicht mehr als einem Richtlinienpaket gleichzeitig zugewiesen werden.

Nachdem Sie dem richtigen Richtlinienpaket Personen hinzugefügt haben, **fertigt Finish** Ihre Auswahl. Sie können weiterhin Richtlinien Pakete im Microsoft Teams Admin Center anpassen und verwalten.

## <a name="manage-policy-packages"></a>Verwalten von Richtlinienpaketen

### <a name="view"></a>Ansicht

Zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen. Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers **Richtlinien Pakete** aus, wählen Sie den Paketnamen aus, und wählen Sie dann den Richtliniennamen aus.

Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.

### <a name="customize"></a>Anpassen

Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket nach Bedarf an die Anforderungen Ihrer Organisation an. Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist. Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das Richtlinienpaket aus, wählen Sie den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** aus.

Beachten Sie, dass Sie auch die Einstellungen von Richtlinien in einem Paket ändern können, nachdem Sie das Richtlinienpaket zugewiesen haben. Weitere Informationen finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Zuweisen

Weisen Sie das Richtlinienpaket Benutzern zu. Wenn Sie einem oder mehreren Benutzern ein Richtlinienpaket zuweisen möchten, klicken Sie auf **Benutzer verwalten** . Sie können auch [PowerShell verwenden](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) , um einem Richtlinienpaket große Batches von Benutzern zuzuweisen. 

Eine schrittweise Anleitung zum Zuweisen eines Richtlinienpakets mit dem Microsoft Teams Admin Center oder PowerShell finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).

![Screenshot: Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-healthcare-assign.png)

Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie später eine andere Richtlinie zuweisen, hat die letzte Aufgabe Vorrang.

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinienpaketen in Teams](manage-policy-packages.md)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
