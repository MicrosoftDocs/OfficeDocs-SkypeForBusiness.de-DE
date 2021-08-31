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
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58df214ec15153abcee4275f42c6ae6208b5d4b1
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731244"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll

Wenn Sie den Benutzern im Microsoft Teams Admin Center Richtlinien zuweisen, können Sie den Status dieser Richtlinienzuweisungen im Aktivitätsprotokoll anzeigen. Im Aktivitätsprotokoll werden Richtlinienzuweisungen für Batches von mehr als 20 Benutzern im Microsoft Teams Admin Center der letzten 30 Tage angezeigt. Beachten Sie, dass im Aktivitätsprotokoll über das Microsoft Teams Admin Center keine Richtlinienpaketzuweisungen, keine Richtlinienzuweisungen für Batches von weniger als 20 Benutzern oder keine Richtlinienzuweisungen über PowerShell angezeigt werden.

![Screenshot der Seite "Aktivitätsprotokoll"](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungsaktivitäten im Aktivitätsprotokoll

So zeigen Sie Ihre Richtlinienzuweisungen im Aktivitätsprotokoll an:

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams **Admin Center** zu Dashboard , und wählen Sie dann unter Aktivitätsprotokoll die Option Details anzeigen **aus.** 
2. Sie können alle Richtlinienzuweisungen anzeigen oder die Liste nach Status filtern, um nur Die Aufgaben "Nicht **gestartet",** **"In Bearbeitung"** oder **"Abgeschlossen" angezeigt zu werden.** Zu jeder Aufgabe werden die folgenden Informationen zu sehen:
    - **Name:** Der Name der Richtlinienzuweisung. Klicken Sie auf den Link, um weitere Details anzuzeigen. Dies umfasst die Anzahl der Benutzer, denen die Richtlinie zugewiesen wurde, sowie die Anzahl der abgeschlossenen, in Bearbeitung und nicht begonnenen Zuordnungen. Außerdem sehen Sie die Liste der Benutzer im Batch sowie den Status und das Ergebnis für jeden Benutzer. Nachfolgend ein Beispiel:

        ![Screenshot der](media/activity-log-policy-assignment-detail.png)

    - **Übermittelt:** Datum und Uhrzeit der Richtlinienzuweisung.
    - **Fertigstellungszeit:** Datum und Uhrzeit der Richtlinienzuweisung.
    - **Auswirkungen auf**: Anzahl der Benutzer im Batch.
    - **Gesamtstatus:** Status der Richtlinienzuweisung.

> [!NOTE]
> Sie können das Aktivitätsprotokoll auch über die Seite **Benutzer** öffnen. Nachdem Sie auf **Übernehmen geklickt** haben, um eine Massenrichtlinienzuweisung zu übermitteln, wird oben auf der Seite ein Banner angezeigt. Klicken Sie **im Banner** auf den Link Aktivitätsprotokoll.

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern](assign-policies.md)
