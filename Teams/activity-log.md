---
title: Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll im Microsoft Teams Admin Center
ms.author: mabond
author: mkbond007
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
ms.openlocfilehash: e8243d60a2aca31a8b9158b922126c7c80a486eb
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562214"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll

Wenn Sie Benutzern im Microsoft Teams Admin Center Richtlinien zuweisen, können Sie den Status dieser Richtlinienzuweisungen im Aktivitätsprotokoll anzeigen. Das Aktivitätsprotokoll zeigt Richtlinienzuweisungen zu Batches von mehr als 20 Benutzern über das Microsoft Teams Admin Center aus den letzten 30 Tagen an. Beachten Sie, dass im Aktivitätsprotokoll keine Richtlinienpaketzuweisungen, Richtlinienzuweisungen zu Batches von weniger als 20 Benutzern über das Microsoft Teams Admin Center oder Richtlinienzuweisungen über PowerShell angezeigt werden.

![Screenshot der Seite "Aktivitätsprotokoll".](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungsaktivitäten im Aktivitätsprotokoll

So zeigen Sie Ihre Richtlinienzuweisungen im Aktivitätsprotokoll an:

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **"Start**", und wählen Sie dann unter **"Aktivitätsprotokoll**" die Option " **Details anzeigen"** aus.
2. Sie können alle Richtlinienzuweisungen anzeigen oder die Liste nach Status filtern, um nur Zuordnungen anzuzeigen, die **nicht gestartet**, **in Bearbeitung** oder **abgeschlossen** sind. Zu jeder Aufgabe werden die folgenden Informationen angezeigt:
    - **Name**: Der Name der Richtlinienzuweisung. Klicken Sie auf den Link, um weitere Details anzuzeigen. Dies umfasst die Anzahl der Benutzer, der die Richtlinie zugewiesen wurde, und die Anzahl der abgeschlossenen Aufgaben, die ausgeführt und nicht gestartet wurden. Außerdem werden die Liste der Benutzer im Batch sowie der Status und das Ergebnis für jeden Benutzer angezeigt. Nachfolgend ein Beispiel:

        ![Screenshot des Screenshots.](media/activity-log-policy-assignment-detail.png)

    - **Übermittelt**: Datum und Uhrzeit der Übermittlung der Richtlinienzuweisung.
    - **Abschlusszeit**: Datum und Uhrzeit, zu dem die Richtlinienzuweisung abgeschlossen wurde.
    - **Auswirkung auf**: Anzahl der Benutzer im Batch.
    - **Gesamtstatus**: Status der Richtlinienzuweisung.

> [!NOTE]
> Sie können auch über die Seite **"Benutzer** " zum Aktivitätsprotokoll gelangen. Nachdem Sie auf **"Übernehmen"** geklickt haben, um eine Massenrichtlinienzuweisung zu übermitteln, wird oben auf der Seite ein Banner angezeigt. Klicken Sie im Banner auf den Link " **Aktivitätsprotokoll** ".

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern](policy-assignment-overview.md)
