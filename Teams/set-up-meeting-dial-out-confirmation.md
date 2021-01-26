---
title: Einrichten der Bestätigung für das Auswählen von Besprechungen für Ihre Benutzer in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Teams so einrichten, dass Eine Auswahlbestätigung angerufen wird, um zu verhindern, dass Voicemailsysteme Verbindungen mit Besprechungen herstellen, wenn die angerufene Person den Anruf nicht beantworten kann.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806145"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Einrichten der Bestätigung für das Auswählen von Besprechungen für Ihre Benutzer in Microsoft Teams

Anrufer in Besprechungen und Anrufe an mich sind sehr hilfreiche Methoden, um Teilnehmer zur Teilnahme an einer Besprechung einzuwählen und vorhandene Teilnehmer über ein herkömmliches Oder Mobiltelefon an einer Besprechung teilnehmen zu lassen. Wenn die angerufene Person den Anruf jedoch nicht beantworten kann und der Anruf von einem Voicemailsystem beantwortet wird, ist das Voicemailsystem mit der Besprechung verbunden, und die Teilnehmer können sich den Anruf anhören, bis er aus der Besprechung entfernt wird.

Um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn eine Auswahl einer Besprechung an eine Telefonnummer gesendet wird und die angerufene Person den Anruf nicht beantworten kann, können Sie Teams so einrichten, dass eine Bestätigung von der angerufenen Person angerufen wird, dass sie an der Besprechung teilnehmen kann. Wenn die angerufene Person den Anruf nicht beantworten kann und der Anruf von einem Voicemailsystem beantwortet wird, wird das Voicemailsystem nicht mit der Besprechung verbunden, da es keine Bestätigung für die Teilnahme bietet.

Wenn diese Funktion aktiviert ist, müssen Personen, die einen Anruf erhalten oder mich anrufen, bestätigen, dass sie an der Besprechung teilnehmen möchten, indem sie auf ihrem herkömmlichen Mobiltelefon oder Mobiltelefon "1" drücken.

Um diese Funktion für alle Besprechungen in Ihrer Organisation zu aktivieren, legen Sie den Parameter des ```EnableDialOutJoinConfirmation``` [Cmdlets "Set-CsOnlineDialInConferencingTenantSettings"](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) auf ". ```true``` Führen Sie dazu den folgenden Befehl aus:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Verwandte Themen

- [Einrichten der Funktion „Rückruf“ für Ihre Benutzer](set-up-the-call-me-feature-for-your-users.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)