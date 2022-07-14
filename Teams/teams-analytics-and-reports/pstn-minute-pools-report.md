---
title: Bericht über PSTN-Minutenpools in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: So verwenden Sie den Bericht "Teams PSTN-Minutenpools" im Microsoft Teams Admin Center, um die in Ihrer Organisation verbrauchten Minuten im aktuellen Monat anzuzeigen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3aafc45cebab24f5524a4d3120dd0c03083d0c6c
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794353"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Bericht über PSTN-Minutenpools in Microsoft Teams

Der Bericht "Teams-PSTN-Minutenpools" im Microsoft Teams Admin Center bietet Ihnen einen Überblick über die Audiokonferenz- und Anrufaktivitäten in Ihrer Organisation, indem Ihnen die Anzahl der Minuten angezeigt wird, die während des aktuellen Monats verbraucht wurden. Sie können eine Aufschlüsselung der Aktivitäten anzeigen, einschließlich der Lizenz, die für Anrufe verwendet wird, der gesamt verfügbaren Minuten, der verwendeten Minuten und der Lizenznutzung nach Standort.

## <a name="view-the-pstn-minute-pools-report"></a>Anzeigen des PSTN-Minutenpoolberichts

Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"Analyse" & Berichte** > **"Nutzungsberichte"**. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht**" **die Pools "PSTN-Minute" und "SMS(Vorschau)"** aus, und klicken Sie dann auf **"Bericht ausführen"**.

![Screenshot des Teams-PSTN-Minutenpoolberichts im Admin Center.](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot des Teams-Berichts &quot;PSTN-Minutenpools&quot; im Microsoft Teams Admin Center mit nummerierten Legenden")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum für die Generierung. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**2**   |Klicken Sie auf eine Funktion (Lizenz), um die Aktivität für diese Funktion anzuzeigen. |
|**3**   |Die X-Achse ist Land oder Region. Die Y-Achse ist die Anzahl von Minuten. <br>Zeigen Sie mit der Maus auf einen Balken im Diagramm, um die Aktivität für diese Verwendungsposition anzuzeigen.  |
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf **"Nicht verwendet**", " **Inländische Benutzer"**, **"Keine Daten**" oder " **International"** , um nur die jeweils zugehörigen Informationen anzuzeigen. |
|**5**   |In der Tabelle finden Sie eine Aufschlüsselung der Minutenpools nach Funktion und Verwendungsort. <ul><li>**Land oder Region** ist der Verwendungsort. </li><li>**Die Funktionsbeschreibung** ist die Beschreibung der Lizenz, die für den Anruf verwendet wird.  Zu den Funktionsbeschreibungen, die in diesem Bericht angezeigt werden können, gehören: <ul><li>Anrufplan für Inland und Ausland (1200 Minuten)</li><li>Anrufplan für Inland und Ausland (3000 Minuten)</li><li>Anrufplan für Inland und Ausland (600 Minuten für Auslandsanrufe)</li></ul></li><br><li>**"Gesamtminuten"** ist die Gesamtanzahl der verfügbaren Minuten für den Monat.</li><li>**In Minuten wird** die Anzahl der minuten pro Monat verwendet.</li> <li>**Verfügbare Minuten** ist die Anzahl der verbleibenden Minuten für den Monat.</li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Zu den angezeigten Lizenzen gehören:<ul><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6** – Anrufplan für Inland (240 Minuten Anrufplan)</li><li>**MCOMEETADD**: Audiokonferenz</li></ul></li> </ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**7**   |Wählen Sie **"Vollbild"** aus, um den Bericht im Vollbildmodus anzuzeigen.|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
