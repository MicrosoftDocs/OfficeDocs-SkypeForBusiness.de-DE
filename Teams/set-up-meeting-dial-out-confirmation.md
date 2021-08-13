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
description: Erfahren Sie, wie Sie Teams einrichten, um eine Auswahlbestätigung an fordern, um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn die angerufene Person den Anruf nicht beantworten kann.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f72641742101a84c572335f2416599fccb6c809bdece75eb75c4db6ff95067c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299075"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Einrichten der Bestätigung für das Auswählen von Besprechungen für Ihre Benutzer in Microsoft Teams

Anrufer von Besprechungen und Anrufe an mich sind sehr hilfreiche Methoden zum Einladen von Teilnehmern zur Teilnahme an einer Besprechung und für vorhandene Teilnehmer zur Teilnahme an einer Besprechung über ein herkömmliches Oder Mobiltelefon. Wenn die angerufene Person den Anruf jedoch nicht beantworten kann und der Anruf von einem Voicemailsystem beantwortet wird, ist das Voicemailsystem mit der Besprechung verbunden, und die Teilnehmer können den Anruf anhören, bis er aus der Besprechung entfernt wird.

Um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn eine Auswahl einer Besprechung an eine Telefonnummer gesendet wird und die angerufene Person den Anruf nicht beantworten kann, können Sie Teams einrichten, um eine Bestätigung von der angerufenen Person an fordern, dass sie an der Besprechung teilnehmen kann. Wenn die angerufene Person den Anruf nicht beantworten kann und der Anruf von einem Voicemailsystem beantwortet wird, wird das Voicemailsystem nicht mit der Besprechung verbunden, da es keine Bestätigung für die Teilnahme gibt.

Wenn diese Funktion aktiviert ist, müssen Personen, die einen Anruf erhalten oder mich anrufen, bestätigen, dass sie an der Besprechung teilnehmen möchten, indem sie auf ihrem herkömmlichen Telefon oder Mobiltelefon 1 drücken.

Um diese Funktion für alle Besprechungen in Ihrer Organisation zu aktivieren, legen Sie den Parameter des ```EnableDialOutJoinConfirmation``` [Cmdlets Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) auf . ```true``` Führen Sie dazu den folgenden Befehl aus:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Verwandte Themen

- [Einrichten der Funktion „Rückruf“ für Ihre Benutzer](set-up-the-call-me-feature-for-your-users.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)