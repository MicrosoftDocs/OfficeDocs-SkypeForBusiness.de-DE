---
title: Einrichten von Besprechungs Dial-Out – Bestätigung für Ihre Benutzer in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teams einrichten, um eine Auswahl Bestätigung anzufordern, um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn die angerufene Person den Anruf nicht annehmen kann.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339473"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Einrichten der Anruf Bestätigung für Besprechungen für Ihre Benutzer in Microsoft Teams

Die Wahlmöglichkeiten für Besprechungen und Anrufe an mich sind sehr hilfreich, um Teilnehmer zur Teilnahme an einer Besprechung einzuladen sowie für vorhandene Teilnehmer, die über ein herkömmliches oder Mobiltelefon an einer Besprechung teilnehmen. Wenn die angerufene Person jedoch nicht in der Lage ist, den Anruf zu beantworten, und der Anruf von einem Voicemailsystem beantwortet wird, ist das Voicemailsystem mit der Besprechung verbunden, und die Teilnehmer können Sie anhören, bis Sie aus der Besprechung entfernt werden.

Um zu verhindern, dass Voicemailsysteme mit Besprechungen verbunden werden, wenn eine Anruf Abwahl an eine Telefonnummer gesendet wird und die angerufene Person den Anruf nicht annehmen kann, können Sie Teams so einrichten, dass Sie eine Bestätigung der angerufenen Person anfordern, um an der Besprechung teilzunehmen. Wenn die angerufene Person den Anruf nicht annehmen kann und der Anruf von einem Voicemailsystem beantwortet wird, wird das Voicemailsystem nicht mit der Besprechung verbunden, da es keine Bestätigung zur Teilnahme an ihm bietet.

Wenn diese Funktion aktiviert ist, müssen Personen, die einen Anruf oder Anruf annehmen, bestätigen, dass Sie an der Besprechung teilnehmen möchten, indem Sie auf Ihrem traditionellen oder mobilen Telefon 1 drücken.

Wenn Sie diese Funktion für alle Besprechungen in Ihrer Organisation aktivieren möchten ```EnableDialOutJoinConfirmation``` , setzen Sie den Parameter des Cmdlets ```true```" [Satz-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) " auf. Führen Sie dazu den folgenden Befehl aus:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Verwandte Themen

- [Einrichten der Funktion „Rückruf“ für Ihre Benutzer](set-up-the-call-me-feature-for-your-users.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)