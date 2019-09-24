---
title: Microsoft Teams-Bericht "PSTN-blockierte Benutzer"
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Hier erfahren Sie, wie Sie den Bericht "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center verwenden, um sich einen Überblick über die Team Benutzer in Ihrer Organisation zu verschaffen, die keine PSTN-Anrufe tätigen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d7bfff166eec388247b65760c3338cb892984f3
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131677"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams-Bericht "PSTN-blockierte Benutzer"

Der Bericht "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center zeigt die Benutzer in Ihrer Organisation an, die für das tätigen von PSTN-anrufen in Teams gesperrt sind. Sie können weitere Informationen zu den einzelnen blockierten Benutzern anzeigen, einschließlich ihrer zugewiesenen Telefonnummer und dem Grund, warum Sie keine Anrufe tätigen konnten.

## <a name="view-the-report"></a>Anzeigen des Berichts

Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analytics #a0 Berichte** > **Nutzungsberichte**. Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **PSTN-blockierte Benutzer**aus, und klicken Sie dann auf **Bericht ausführen**.

![Screenshot des Berichts "PSTN-blockierte Benutzer" im Admin Center] (../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot des Berichts \"PSTN-blockierte Benutzer\" im Microsoft Teams Admin Center mit nummerierten Beschriftungen")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht hat ein Datum, zu dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**2**   |Die X-Achse ist das Datum. Bei der Y-Achse handelt es sich um die Anzahl der Benutzer. <br>Zeigen Sie auf den Punkt an einem bestimmten Datum, um zu sehen, wie viele Benutzer an diesem Datum blockiert sind. |
|**3**   |Die Tabelle enthält eine Aufschlüsselung aller Benutzer, die keine PSTN-Anrufe tätigen können.  Sie zeigt alle Benutzer an, denen Telefon System-oder Audiokonferenzen zugewiesen sind, und gibt Ihnen weitere Informationen zu den einzelnen Benutzern. <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. </li> <li>**Telefon** ist die Nummer, die dem Benutzer zugewiesen ist.</li> <li>**Blockierter Grund** ist der Grund dafür, dass der Benutzer keine Anrufe tätigen kann.</li><li>**Blockierte Aktion** zeigt an, ob der Benutzer blockiert oder freigegeben wurde, um in Teams PSTN-Anrufe zu tätigen.</li> <li>**Blockierte Zeit** ist das Datum und die Uhrzeit (UTC), an dem der Benutzer für das tätigen von Anrufen gesperrt wurde.</li></li> </ul>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**4**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**5**   |Wählen Sie **Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen.|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)