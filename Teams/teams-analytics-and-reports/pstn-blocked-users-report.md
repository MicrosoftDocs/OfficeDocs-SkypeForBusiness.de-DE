---
title: Microsoft Teams-Bericht "PSTN-blockierte Benutzer"
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
description: Verwenden Sie den Bericht "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center, um sich einen Überblick über die Team Benutzer Ihrer Organisation zu verschaffen, die für das tätigen von PSTN-anrufen gesperrt sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 511485fa156ba448368809edf54728ada1b80be7
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904907"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams-Bericht "PSTN-blockierte Benutzer"

Der Bericht "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center zeigt die Benutzer in Ihrer Organisation an, die für das tätigen von PSTN-anrufen in Teams gesperrt sind. Sie können weitere Informationen zu den einzelnen blockierten Benutzern anzeigen, einschließlich ihrer zugewiesenen Telefonnummer und dem Grund, warum Sie keine Anrufe tätigen konnten.

## <a name="view-the-pstn-blocked-users-report"></a>Anzeigen des Berichts "PSTN-blockierte Benutzer"

Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analytics & Berichte** > **Nutzungsberichte**. Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **PSTN-blockierte Benutzer**aus, und klicken Sie dann auf **Bericht ausführen**.

![Screenshot des Berichts "PSTN-blockierte Benutzer" im Admin Center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot des Berichts "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center mit nummerierten Beschriftungen")

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