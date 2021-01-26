---
title: Bericht zu Microsoft Teams PSTN-Minutenpools
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
description: Verwenden des Berichts "Teams PSTN-Minutenpools" im Microsoft Teams Admin Center zum Anzeigen der in Ihrer Organisation verbrauchten Minuten während des aktuellen Monats
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8df0c1201f963a1c00742532f80089b523ca79aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809345"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Bericht zu Microsoft Teams PSTN-Minutenpools

Der Bericht "Teams PSTN-Minutenpools" im Microsoft Teams Admin Center bietet Ihnen eine Übersicht über audio conferencing and calling activity in your organization, indem die Anzahl der Minuten angezeigt wird, die während des aktuellen Monats verbraucht wurden. Sie können eine Aufschlüsselung der Aktivität einschließlich der für Anrufe verwendeten Lizenz, der anzahl verfügbarer Minuten, verwendeter Minuten und der Lizenznutzung nach Standort sehen.

## <a name="view-the-pstn-minute-pools-report"></a>Anzeigen des Berichts "PSTN-Minutenpools"

Klicken Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers auf "Analysefunktionen&   >  **Verwendungsberichte.** Wählen Sie **auf der Registerkarte "Berichte anzeigen"** unter **"Bericht"** die Option **"PSTN-Minutenpools"** aus, und klicken Sie dann auf **"Bericht ausführen".**

![Screenshot des Berichts "Teams PSTN-Minutenpools" im Admin Center](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot des Berichts "Teams PSTN-Minutenpools" im Microsoft Teams Admin Center mit nummerierten Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**2**   |Klicken Sie auf eine Funktion (Lizenz), um die Aktivität für diese Funktion anzeigen. |
|**3**   |Die X-Achse ist Das Land oder die Region. Die Y-Achse ist die Anzahl der Minuten. <br>Zeigen Sie mit der Maus auf einen Balken im Diagramm, um die Aktivität für diese Verwendungsposition zu sehen.  |
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf **"Nicht verwendet",**"Inlandsbenutzer", "Keine Daten" oder **"International",** um nur die jeweils zugehörigen Informationen zu sehen. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Minutenpools nach Funktion und Verwendungsstandort. <ul><li>**Das Land oder die Region** ist der Verwendungsstandort. </li><li>**Funktionsbeschreibung** ist die Beschreibung der für den Anruf verwendeten Lizenz.  Zu den Funktionsbeschreibungen in diesem Bericht gehören: <ul><li>Anrufplan für Inland und Ausland (1.200 Minuten für Inland)</li><li>Anrufplan für Inland und Ausland (3000 Minuten für Inland)</li><li>Anrufplan für Inlands- und Auslandsrufe (600 Auslandsminuten)</li></ul></li><br><li>**Die Gesamtzahl der** Minuten, die für den Monat zur Verfügung stehen.</li><li>**Die anzahl der** minuten, die jeden Monat verwendet werden</li> <li>**"Verfügbare Minuten"** ist die Anzahl der Minuten, die für den Monat noch übrig sind.</li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Zu den angezeigten Lizenzen gehören:<ul><li>**MCOPSTNPP**: Guthaben für Kommunikationen</li><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6** – Plan für Inlandsrufe (Anrufplan für 240 Minuten)</li><li>**MCOMEETADD**: Audiokonferenz</li><li>**MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung</li></ul></li> </ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**7**   |Wählen **Sie "Vollbild"** aus, um den Bericht im Vollbildmodus anzuzeigen.|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)