---
title: Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll im Microsoft Teams Admin Center
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Richtlinien Zuordnungs Aktivitäten im Aktivitätsprotokoll im Microsoft Teams Admin Center anzeigen.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374293"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll

Wenn Sie Benutzern im Microsoft Teams Admin Center Richtlinien zuweisen, können Sie den Status dieser Richtlinienzuweisungen im Aktivitätsprotokoll anzeigen. Das Aktivitätsprotokoll zeigt Richtlinienzuweisungen für Stapel von mehr als 20 Benutzern über das Microsoft Teams Admin Center der letzten 30 Tage. Beachten Sie, dass im Aktivitätsprotokoll keine Richtlinienpaket Zuweisungen, Richtlinienzuweisungen für Batches mit weniger als 20 Benutzern über das Microsoft Teams Admin Center oder Richtlinienzuweisungen über PowerShell angezeigt werden.

![Screenshot der Seite "Aktivitätsprotokoll"](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Anzeigen Ihrer Richtlinien Zuordnungs Aktivitäten im Aktivitätsprotokoll

So zeigen Sie Ihre Richtlinienzuweisungen im Aktivitätsprotokoll an:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Dashboard**, und wählen Sie dann unter **Aktivitätsprotokoll**die Option **Details anzeigen**aus.
2. Sie können alle Richtlinienzuweisungen anzeigen oder die Liste nach Status filtern, um nur Zuordnungen anzuzeigen, die **nicht gestartet**, **in Bearbeitung**oder **abgeschlossen**sind. Für jede Aufgabe werden die folgenden Informationen angezeigt:
    - **Name**: der Name der Richtlinienzuordnung. Klicken Sie auf den Link, um weitere Details anzuzeigen. Dies umfasst die Anzahl der Benutzer, denen die Richtlinie zugewiesen wurde, und die Anzahl der Aufgaben, die abgeschlossen, in Bearbeitung und nicht gestartet wurden. Außerdem sehen Sie die Liste der Benutzer im Batch sowie den Status und das Ergebnis für jeden Benutzer. Nachfolgend ein Beispiel:

        ![Screenshot des](media/activity-log-policy-assignment-detail.png)

    - Über **mittelt**: Datum und Uhrzeit, an dem die Richtlinienzuweisung übermittelt wurde.
    - **Fertigstellungszeit**: Datum und Uhrzeit, zu der die Richtlinien Aufgabe abgeschlossen wurde.
    - **Auswirkung auf**: Anzahl der Benutzer im Batch.
    - **Gesamtstatus**: Status der Richtlinienzuordnung.

> [!NOTE]
> Sie können auch auf der Seite " **Benutzer** " auf das Aktivitätsprotokoll gelangen. Nachdem Sie auf über **nehmen** klicken, um eine Massen Richtlinienzuweisung zu übermitteln, wird oben auf der Seite ein Banner angezeigt. Klicken Sie im Banner auf den Link **Aktivitätsprotokoll** .

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern](assign-policies.md)
