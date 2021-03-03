---
title: Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll im Microsoft Teams Admin Center
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Richtlinienzuweisungsaktivitäten im Aktivitätsprotokoll im Microsoft Teams Admin Center anzeigen.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821315"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll

Wenn Sie Benutzern im Microsoft Teams Admin Center Richtlinien zuweisen, können Sie den Status dieser Richtlinienzuweisungen im Aktivitätsprotokoll anzeigen. Im Aktivitätsprotokoll werden Richtlinienzuweisungen zu Gruppen von mehr als 20 Benutzern aus den letzten 30 Tagen über das Microsoft Teams Admin Center angezeigt. Beachten Sie, dass im Aktivitätsprotokoll über das Microsoft Teams Admin Center keine Richtlinienpaketzuweisungen, keine Richtlinienzuweisungen für Gruppen von weniger als 20 Benutzern oder keine Richtlinienzuweisungen über PowerShell angezeigt werden.

![Screenshot der Seite "Aktivitätsprotokoll"](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungsaktivitäten im Aktivitätsprotokoll

So zeigen Sie Ihre Richtlinienzuweisungen im Aktivitätsprotokoll an:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zum **Dashboard,** und wählen Sie dann unter **"Aktivitätsprotokoll"** die Option **"Details anzeigen" aus.**
2. Sie können alle Richtlinienzuweisungen anzeigen oder die Liste nach Status filtern, um nur Die Aufgaben "Nicht begonnen", **"In** Bearbeitung" oder **"Abgeschlossen" angezeigt zu werden.** Zu jeder Aufgabe werden die folgenden Informationen zu sehen:
    - **Name:** Der Name der Richtlinienzuordnung. Klicken Sie auf den Link, um weitere Details anzuzeigen. Dies umfasst die Anzahl der Benutzer, denen die Richtlinie zugewiesen wurde, sowie die Anzahl der abgeschlossenen, in Bearbeitung und nicht begonnenen Aufgaben. Außerdem werden die Liste der Benutzer im Batch sowie der Status und das Ergebnis für jeden Benutzer angezeigt. Nachfolgend ein Beispiel:

        ![Screenshot der](media/activity-log-policy-assignment-detail.png)

    - **Übermittelt:** Datum und Uhrzeit der Richtlinienzuweisung.
    - **Abschlusszeit:** Datum und Uhrzeit der Richtlinienzuweisung.
    - **Auswirkungen auf:** Anzahl der Benutzer im Batch.
    - **Gesamtstatus:** Status der Richtlinienzuweisung.

> [!NOTE]
> Sie können auch über die Seite "Benutzer" zum **Aktivitätsprotokoll** gelangen. Nachdem Sie auf **"Übernehmen"** geklickt haben, um eine Massenrichtlinienzuweisung zu übermitteln, wird oben auf der Seite ein Banner angezeigt. Klicken Sie **im Banner auf** den Link "Aktivitätsprotokoll".

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern](assign-policies.md)
