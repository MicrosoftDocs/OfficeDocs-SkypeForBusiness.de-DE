---
title: Einrichten der Bestätigung für das Auswählen von Besprechungen für Ihre Benutzer in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Teams einrichten, um eine Auswahlbestätigung an fordern, um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn die angerufene Person den Anruf nicht beantworten kann.
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9db8d3882ea7d05b1bc3600682c0c803040b4c10
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055655"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Einrichten der Bestätigung für das Auswählen von Besprechungen für Ihre Benutzer in Microsoft Teams

Anrufer von Besprechungen und Anrufe an mich sind nützliche Möglichkeiten, um Teilnehmer zur Teilnahme an einer Besprechung einzuwählen, sowie für vorhandene Teilnehmer, die über ein herkömmliches Oder Mobiltelefon an einer Besprechung teilnehmen können. Wenn die angerufene Person den Anruf jedoch nicht beantworten kann und der Anruf von einem Voicemailsystem beantwortet wird, ist das Voicemailsystem mit der Besprechung verbunden. Die Teilnehmer können sie anhören, bis sie aus der Besprechung entfernt werden.

Um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn eine Auswahl einer Besprechung an eine Telefonnummer gesendet wird und die angerufene Person den Anruf nicht beantworten kann, können Sie Teams einrichten, um eine Bestätigung von der angerufenen Person an fordern, dass sie an der Besprechung teilnehmen kann. Wenn die angerufene Person den Anruf nicht beantworten kann und der Anruf von einem Voicemailsystem beantwortet wird, wird das Voicemailsystem nicht mit der Besprechung verbunden, da es keine Bestätigung für die Teilnahme gibt.

Wenn diese Funktion aktiviert ist, müssen Personen, die einen Anruf erhalten oder mich anrufen, bestätigen, dass sie an der Besprechung teilnehmen möchten, indem sie entweder auf ihrem herkömmlichen Oder Mobiltelefon 1 drücken oder "Okay" sagen.

Um diese Funktion für alle Besprechungen in Ihrer Organisation zu aktivieren, legen Sie den Parameter des ```EnableDialOutJoinConfirmation``` [Cmdlets Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) auf . ```true``` Führen Sie zum Festlegen dieses Parameters den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Verwandte Themen

- [Einrichten der Funktion „Rückruf“ für Ihre Benutzer](set-up-the-call-me-feature-for-your-users.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
