---
title: Microsoft Teams PSTN-Minuten Pools-Bericht
author: LanaChin
ms.author: v-lanac
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
description: Erfahren Sie, wie Sie den Bericht "PSTN-Minuten Pools für Teams" im Microsoft Teams Admin Center verwenden, um die Anzahl der Minuten anzuzeigen, die während des aktuellen Monats innerhalb Ihrer Organisation verbraucht werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fa9b8f4a676c1e937fed02eabc0e7cd4acd5325
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827323"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams PSTN-Minuten Pools-Bericht

Der Bericht "PSTN-Minuten Pools für Teams" im Microsoft Teams Admin Center bietet Ihnen einen Überblick über Audiokonferenzen und Anrufaktivitäten in Ihrer Organisation, indem Sie die Anzahl der Minuten anzeigen, die im aktuellen Monat verbraucht wurden. Sie können eine Aufschlüsselung der Aktivitäten einschließlich der für Anrufe verwendeten Lizenz, der verfügbaren Minuten, der verwendeten Minuten und der Lizenzverwendung nach Standort sehen.

## <a name="view-the-report"></a>Anzeigen des Berichts

Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analytics #a0 Berichte** > **Nutzungsberichte**. Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **PSTN-Minuten Pools**aus, und klicken Sie dann auf **Bericht ausführen**.

![Screenshot des Berichts "PSTN-Minuten Pools für Teams" im Admin Center](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot des Berichts "PSTN-Minuten Pools für Teams" im Microsoft Teams Admin Center mit nummerierten Beschriftungen")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum, zu dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**2**   |Klicken Sie auf eine Funktion (Lizenz), um die Aktivitäten für diese Funktion anzuzeigen. |
|**3**   |Die X-Achse ist "Land" oder "Region". Die Y-Achse ist die Anzahl von Minuten. <br>Zeigen Sie mit der Maus auf einen Balken im Diagramm, um die Aktivität für diesen Verwendungs Speicherort anzuzeigen.  |
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf nicht **verwendete**, **inländische Benutzer**, **keine Daten**oder **internationale** , um nur die Informationen anzuzeigen, die sich auf die einzelnen Personen beziehen. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Minuten Pools nach Funktion und Verwendungsstandort. <ul><li>**Land oder Region** ist der Verwendungsstandort. </li><li>**Beschreibung der Funktion** ist die Beschreibung der für den Anruf verwendeten Lizenz.  Zu den Funktionsbeschreibungen, die in diesem Bericht möglicherweise angezeigt werden, gehören: <ul><li>Plan für Inlands-und Auslandsanrufe (1200 Inlands Minuten)</li><li>Plan für Inlands-und Auslandsanrufe (3000 Inlands Minuten)</li><li>Plan für Inlands-und Auslandsanrufe (600-Auslands Minuten)</li></ul></li><br><li>**Gesamt** Anzahl der Minuten ist die Gesamtzahl der Minuten, die für den Monat zur Verfügung stehen.</li><li>**Verwendete Minuten** ist die Anzahl der pro Monat verwendeten Minuten.</li> <li>**Verfügbare Minuten** ist die Anzahl der verbleibenden Minuten für den Monat.</li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Die Lizenzen, die Ihnen möglicherweise angezeigt werden, sind:<ul><li>**MCOPSTNPP**: Guthaben für Kommunikationen</li><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6** -Domestic Calling Plan (240 min Calling Plan)</li><li>**MCOMEETADD**: Audiokonferenz</li><li>**MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung</li></ul></li> </ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**7**   |Wählen Sie **Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen.|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)