---
title: Microsoft Teams PstN-Bericht über blockierte Benutzer
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: Verwenden Sie den Bericht "PstN-blockierte Benutzer" im Microsoft Teams Admin Center, um einen Überblick über die Teams-Benutzer In Ihrer Organisation zu erhalten, die für das Anrufen über das Festnetz gesperrt sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a89e7ead560e3782d7120884a047110118d2ecd0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840687"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams PstN-Bericht über blockierte Benutzer

Im Bericht PSTN-blockierte Benutzer im Microsoft Teams Admin Center werden die Benutzer in Ihrer Organisation, die für das Anrufen über das Festnetz gesperrt sind, in Teams. Sie können weitere Informationen zu jedem blockierten Benutzer anzeigen, einschließlich der zugewiesenen Telefonnummer und des Grunds, warum er für das Anrufen gesperrt wurde.

## <a name="view-the-pstn-blocked-users-report"></a>Anzeigen des Berichts "PstN-Bericht über blockierte Benutzer"

Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Center auf **Analyseberichte &**  >  **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **PSTN-blockierte Benutzer** aus, und klicken Sie dann auf Bericht **ausführen.**

![Screenshot des Berichts "PstN-Bericht über blockierte Benutzer" im Admin Center.](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot des Berichts &quot;PstN-blockierte Benutzer&quot; im Microsoft Teams Admin Center mit nummerierten Anrufen")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat das Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**2**   |Die X-Achse ist das Datum. Die Y-Achse gibt die Anzahl der Benutzer an. <br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Anzahl der an diesem Datum blockierten Benutzer zu sehen. |
|**3**   |Die Tabelle enthält eine Aufschlüsselung aller Benutzer, die für das Erstellen von PSTN-Anrufen gesperrt sind.  Es zeigt alle Benutzer an, denen Telefonsystem Audiokonferenz zugewiesen sind, und enthält weitere Informationen zu jedem Benutzer. <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. </li> <li>**Telefon** ist die Nummer, die dem Benutzer zugewiesen wurde.</li> <li>**Blockierter Grund** ist der Grund, warum der Benutzer für das Anrufen gesperrt wurde.</li><li>**Die blockierte** Aktion teilt Ihnen mit, ob der Benutzer in einem Anruf über das Festnetz blockiert oder die Blockierung aufgehoben Teams.</li> <li>**Blockierte Uhrzeit** ist das Datum und die Uhrzeit (UTC), zu dem der Benutzer für das Anrufen gesperrt wurde.</li></li> </ul>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**4**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**5**   |Wählen **Sie Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen.|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)