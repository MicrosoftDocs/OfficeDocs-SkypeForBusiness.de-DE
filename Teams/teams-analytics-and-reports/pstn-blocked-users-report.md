---
title: Microsoft Teams PSTN-Bericht "Blockierte Benutzer"
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
description: Verwenden Sie den Bericht "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center, um einen Überblick über die Teams-Benutzer Ihrer Organisation zu erhalten, die am Tätigen von PSTN-Anrufen gehindigt sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d689d2696a20f51e232a581d45032d55da6deb6d
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794143"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams PSTN-Bericht "Blockierte Benutzer"

Der Bericht "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center zeigt Ihnen die Benutzer in Ihrer Organisation, die am Tätigen von PSTN-Anrufen in Teams gehindigt sind. Sie können weitere Informationen zu jedem blockierten Benutzer anzeigen, einschließlich der zugewiesenen Telefonnummer und des Grunds, warum er für anrufe gesperrt wurde.

## <a name="view-the-pstn-blocked-users-report"></a>Anzeigen des PSTN-Berichts für blockierte Benutzer

Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"Analyse" & Berichte** > **"Nutzungsberichte"**. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht**" die Option " **PSTN blockierte Benutzer**" aus, und klicken Sie dann auf **"Bericht ausführen"**.

![Screenshot des Berichts "PSTN-Blockierte Benutzer" im Admin Center.](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot des PSTN-Berichts &quot;Blockierte Benutzer&quot; im Microsoft Teams Admin Center mit nummerierten Legenden")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum für die Generierung. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**2**   |Die X-Achse ist das Datum. Die Y-Achse ist die Anzahl der Benutzer. <br>Zeigen Sie mit der Maus auf den Punkt an einem bestimmten Datum, um die Anzahl der Benutzer anzuzeigen, die an diesem Datum blockiert wurden. |
|**3**   |Die Tabelle enthält eine Aufschlüsselung aller Benutzer, die am Tätigen von PSTN-Anrufen gehindigt sind.  Es zeigt alle Benutzer, denen Telefonsystem oder Audiokonferenzen zugewiesen sind, und bietet Ihnen weitere Informationen zu jedem Benutzer. <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. </li> <li>**Telefon** ist die Nummer, die dem Benutzer zugewiesen ist.</li> <li>**Blockierter Grund** ist der Grund, warum der Benutzer daran gehindigt wird, Anrufe zu tätigen.</li><li>Die **blockierte Aktion** teilt Ihnen mit, ob der Benutzer blockiert oder für PSTN-Anrufe in Teams gesperrt ist.</li> <li>**Die blockierte Uhrzeit** ist das Datum und die Uhrzeit (UTC), an denen der Benutzer an Anrufen gehindert wurde.</li></li> </ul>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**4**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**5**   |Wählen Sie **"Vollbild"** aus, um den Bericht im Vollbildmodus anzuzeigen.|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)