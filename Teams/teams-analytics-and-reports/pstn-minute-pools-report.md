---
title: Microsoft Teams Bericht über PSTN-Minutenpools
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Verwenden des Berichts Teams PSTN-Minutenpools im Microsoft Teams Admin Center zum Anzeigen der in Ihrer Organisation verbrauchten Minuten während des aktuellen Monats
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6e1d87ac58c6f5916a393e9e85351be12bdd7ae2ba0cd62f467b44b418470f6b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316621"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams Bericht über PSTN-Minutenpools

Der Bericht Teams PSTN-Minutenpools im Microsoft Teams Admin Center bietet Ihnen eine Übersicht über Audiokonferenz- und Anrufaktivitäten in Ihrer Organisation, indem Ihnen die Anzahl der Minuten angezeigt wird, die während des aktuellen Monats verbraucht wurden. Sie können eine Aufschlüsselung der Aktivität sehen, einschließlich der für Anrufe verwendeten Lizenz, der gesamten verfügbaren Minuten, der Nutzung in Minuten und der Lizenznutzung nach Standort.

## <a name="view-the-pstn-minute-pools-report"></a>Anzeigen des Berichts für PSTN-Minutenpools

Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Center auf **Analyseberichte &**  >  **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **PSTN-Minutenpools** aus, und klicken Sie dann **auf Bericht ausführen.**

![Screenshot des Berichts Teams PSTN-Minutenpools im Admin Center](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot des Berichts Teams PSTN-Minutenpools im Microsoft Teams Admin Center mit nummerierten Anrufen")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat das Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**2**   |Klicken Sie auf eine Funktion (Lizenz), um die Aktivität für diese Funktion anzeigen. |
|**3**   |Die X-Achse ist Land oder Region. Die Y-Achse hat eine Anzahl von Minuten. <br>Zeigen Sie mit der Maus auf einen Balken im Diagramm, um die Aktivität für diese Verwendungsposition zu sehen.  |
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf **Nicht verwendet**, **Inlandsbenutzer**, **Keine Daten** oder **International** , um nur die jeweils zugehörigen Informationen zu sehen. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Minutenpools nach Funktion und Verwendungsort. <ul><li>**Land oder Region** ist der Verwendungsstandort. </li><li>**Funktionsbeschreibung** ist die Beschreibung der für den Anruf verwendeten Lizenz.  Zu den Funktionsbeschreibungen, die in diesem Bericht möglicherweise verwendet werden, gehören: <ul><li>Anrufplan für Inlands- und Auslandsrufe (1.200 Minuten für Inland)</li><li>Anrufplan für In- und Ausland (3.000 Minuten für Inland)</li><li>Anrufplan für Inlands- und Auslandsrufe (600 Minuten im Ausland)</li></ul></li><br><li>**Gesamtminuten** ist die Gesamtzahl der für den Monat verfügbaren Minuten.</li><li>**Verwendete Minuten** ist die Anzahl der Minuten, die jeden Monat verwendet werden.</li> <li>**Verfügbare Minuten** ist die Anzahl der verbleibenden Minuten für den Monat.</li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Zu den angezeigten Lizenzen gehören:<ul><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6–** Plan für Inlandsrufe (Anrufplan mit 240 Min.)</li><li>**MCOMEETADD**: Audiokonferenz</li></ul></li> </ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**7**   |Wählen **Sie Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen.|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
