---
title: Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
author: LolaJacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die gesetzliche Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams unter Verwendung des Security & Compliance Center festlegen können und welche Datenanforderungen für eine gesetzliche Aufbewahrung notwendig sind.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0526ed2d5b0aa48ab7229c8fa40dbb13413c3139
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833465"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
==================================================

Um die gesetzliche Aufbewahrung für einen Benutzer oder ein Team festzulegen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). Wenn Sie einen neuen Anwendungsfall erstellen, wird die Option zum Aufbewahren von Postfächern und Sites angezeigt.

> [!NOTE]
> Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).

> [!NOTE]
> Die Unterstützung für die rechtliche Aufbewahrung privater Kanal Nachrichten steht in Kürze zur Verfügung. Der rechtliche Halt von Dateien, die in privaten Kanälen freigegeben werden, wird unterstützt.

> [!IMPORTANT]
> Wenn ein Benutzer oder eine Gruppe in Wartestellung gesetzt wird, bleiben alle Nachrichten-Kopien erhalten. Beispiel: Clay hat eine Nachricht in einem Kanal gepostet und die Nachricht dann verändert. In einem Aufbewahrungsszenario werden beide Kopien der Nachricht beibehalten. Ohne die gesetzliche Aufbewahrungspflicht wird nur die aktuelle Nachricht beibehalten.

In der Abbildung unten sehen Sie eine Untersuchung im Zusammenhang mit Clay. Clay ist ein Mitglied des Makler-Händler-Teams.

Wenn für alle Kanäle, über die Clay Maklerpläne diskutiert haben könnte, eine gesetzliche Aufbewahrungspflicht festgelegt ist, stellen Sie sicher, dass die SharePoint-Site des Teams zur Siteliste „Gesetzliche Aufbewahrungspflicht“ sowie zu Clays OneDrive for Business-Site hinzugefügt wird.

![Screenshot des Dialogfelds „Neuen Fallspeicher erstellen“](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

Zusammenfassung: Verwenden Sie die Tabelle unten, um zu verstehen, für welche Daten basierend auf den Datenanforderungen eine gesetzliche Aufbewahrungspflicht besteht.

|Szenario  |Was muss aufbewahrt werden  |
|---------|---------|
|**Private Microsoft Teams-Chats**     |Benutzerpostfächer         |
|**Microsoft Teams-Kanalchats**    |Für das Team verwendete Gruppenpostfach         |
|**Microsoft Teams-Inhalt (z. B. Wiki, Dateien)**     |Vom Team verwendete SharePoint-Site         |
|**Privater Inhalt**     |OneDrive for Business-Site des Benutzers         |
