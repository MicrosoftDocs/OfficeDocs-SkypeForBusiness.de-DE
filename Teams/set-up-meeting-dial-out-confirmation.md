---
title: Einrichten der Besprechungsauswahlbestätigung für Ihre Benutzer in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Teams so einrichten, dass eine Bestätigung für die Einwahl angefordert wird, um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn die angerufene Person den Anruf nicht annehmen kann.
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271560"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Einrichten der Besprechungsauswahlbestätigung für Ihre Benutzer in Microsoft Teams

Besprechungswähl- und Anrufanrufe sind nützliche Möglichkeiten, um Teilnehmer zur Teilnahme an einer Besprechung einzuladen, und für vorhandene Teilnehmer, an einer Besprechung mit einem herkömmlichen oder Mobiltelefon teilzunehmen. Wenn die angerufene Person den Anruf jedoch nicht annehmen kann und der Anruf von einem Voicemailsystem angenommen wird, ist das Voicemailsystem mit der Besprechung verbunden. Teilnehmer können sie anhören, bis sie aus der Besprechung entfernt wurde.

Um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn eine Besprechungsauswahl an eine Telefonnummer gesendet wird und die angerufene Person den Anruf nicht annehmen kann, können Sie Teams einrichten, um eine Bestätigung der angerufenen Person anzufordern, damit sie an der Besprechung teilnehmen kann. Wenn die angerufene Person den Anruf nicht annehmen kann und der Anruf von einem Voicemailsystem angenommen wird, wird das Voicemailsystem nicht mit der Besprechung verbunden, da es keine Bestätigung für die Teilnahme an der Besprechung liefert.

Wenn diese Funktion aktiviert ist, müssen Personen, die eine Ausgehendkeit oder einen Anruf erhalten, bestätigen, dass sie an der Besprechung teilnehmen möchten, indem sie entweder 1 auf ihrem herkömmlichen Oder Mobiltelefon drücken oder "Ok" sagen. Die Bestätigung verhindert, dass die Voicemailnachricht des Benutzers an der Besprechung teilnimmt.

Um diese Funktion für alle Besprechungen in Ihrer Organisation zu aktivieren, legen Sie den ```EnableDialOutJoinConfirmation``` Parameter des Cmdlets ["Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) " auf ```true```" fest. Führen Sie den folgenden Befehl aus, um diesen Parameter festzulegen:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Verwandte Themen

- [Einrichten der Funktion „Rückruf“ für Ihre Benutzer](set-up-the-call-me-feature-for-your-users.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
