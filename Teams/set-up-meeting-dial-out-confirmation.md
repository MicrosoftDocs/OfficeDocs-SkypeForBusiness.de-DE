---
title: Einrichten der Einwahlbestätigung für Besprechungen für Ihre Benutzer in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Teams so einrichten, dass eine Auswahlbestätigung angerufen wird, um zu verhindern, dass Voicemailsysteme verbindungen zu Besprechungen herstellen, wenn die angerufene Person den Anruf nicht beantworten kann.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117093"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Einrichten der Besprechungs-Einwahlbestätigung für Ihre Benutzer in Microsoft Teams

Besprechungswähl- und Anrufanrufe sind sehr hilfreiche Möglichkeiten, um Teilnehmer zur Teilnahme an einer Besprechung einzulästen und vorhandene Teilnehmer über ein herkömmliches Oder Mobiltelefon an einer Besprechung zu teilnehmen. Wenn die angerufene Person den Anruf jedoch nicht beantworten kann und der Anruf von einem Voicemailsystem beantwortet wird, ist das Voicemailsystem mit der Besprechung verbunden, und die Teilnehmer können ihn hören, bis er aus der Besprechung entfernt wird.

Um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn eine Besprechungswählnummer an eine Telefonnummer gesendet wird und die angerufene Person den Anruf nicht beantworten kann, können Sie Teams so einrichten, dass eine Bestätigung von der angerufenen Person für die Teilnahme an der Besprechung anberaumt wird. Wenn die angerufene Person den Anruf nicht beantworten kann und der Anruf von einem Voicemailsystem beantwortet wird, wird das Voicemailsystem nicht mit der Besprechung verbunden, da es keine Bestätigung für die Teilnahme an der Besprechung bietet.

Wenn diese Funktion aktiviert ist, müssen Personen, die eine Abwahl oder einen Anruf erhalten, bestätigen, dass sie an der Besprechung teilnehmen möchten, indem sie 1 auf ihrem herkömmlichen Mobiltelefon oder Mobiltelefon drücken.

Um diese Funktion für alle Besprechungen in Ihrer Organisation zu aktivieren, legen Sie den Parameter des ```EnableDialOutJoinConfirmation``` [Cmdlets Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) auf . ```true``` Führen Sie dazu den folgenden Befehl aus:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Verwandte Themen

- [Einrichten der Funktion „Rückruf“ für Ihre Benutzer](set-up-the-call-me-feature-for-your-users.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)