---
title: Starten der Audiokonferenz per Telefon ohne PIN in Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Erfahren Sie, wie Sie anonyme Anrufer daran hindern, über das Teams Admin Center an einer Besprechung teilnehmen zu können. '
ms.openlocfilehash: a858c95527d09e24004d025787bee52c0de84705
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641946"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams

Es kann für Benutzer, die sich in eine Besprechung einwählen, frustrierend sein, wenn sie im Wartebereich der Besprechung Musik hören, da der Besprechungsorganisator von Microsoft Teams die Besprechung noch nicht gestartet hat.
  
Wenn sich ein Besprechungsorganisator in die Besprechung einberuft, ist standardmäßig eine PIN erforderlich, um eine Besprechung zu starten. Sie können es so einrichten, dass sich jeder in eine Besprechung einwählen kann und nicht zur Eingabe einer PIN aufgefordert wird, um die Besprechung zu starten. Sie können das Admin Center verwenden, um diese Einstellung für einen einzelnen Benutzer zu aktivieren oder zu deaktivieren.
  
Eine PIN ist für den Besprechungsorganisator nicht erforderlich, wenn jemand die Besprechung über die Microsoft Teams-App gestartet hat. Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den Audiobenutzer gesendet, wenn ihm die **Lizenz für Audiokonferenzen** zugewiesen und für Audiokonferenzen aktiviert ist. Siehe ["Senden einer E-Mail an einen Benutzer mit audiokonferenzinformationen](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) und [E-Mails, die automatisch an Benutzer gesendet werden, wenn sich die Audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich auf **"Benutzer"**.

2. Wählen Sie einen Benutzer in der Liste aus, und klicken Sie dann oben auf der Seite auf **"Bearbeiten** ".

3. Klicken Sie neben **Audiokonferenzen** auf **"Bearbeiten"**.

4. Aktivieren oder  Deaktivieren von **Einwahlanrufern im Audiokonferenzbereich kann die erste Person in einer Besprechung sein**.

5. Klicken Sie auf **Anwenden**.

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](/powershell/module/teams/?view=teams-ps) .

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn Sie die PIN zurücksetzen möchten, lesen Sie ["Zurücksetzen der Audiokonferenz-PIN"](reset-the-audio-conferencing-pin-in-teams.md).

- Wenn anonymer Zugriff oder keine PIN zum Starten einer Besprechung erforderlich ist, ist Folgendes deaktiviert:

  - Wenn die Besprechung noch nicht begonnen hat (es ist noch niemand in der Besprechung): Ein Anrufer wird aufgefordert, wenn er der Organisator ist; Wenn er "Ja" sagt, wird er zur Eingabe seiner PIN aufgefordert, und nachdem er die PIN eingibt, wird die Besprechung gestartet, und der Benutzer nimmt an der Besprechung teil.

  - Wenn die Besprechung bereits begonnen hat (eine andere Person ist bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird nie zur Eingabe der PIN aufgefordert. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt an der Besprechung teil.

- Wenn anonymer Zugriff oder keine PIN zum Starten einer Besprechung erforderlich ist, ist Folgendes aktiviert:

  - Wenn die Besprechung noch nicht begonnen hat (es ist noch niemand in der Besprechung): Ein Anrufer wird nicht gefragt, ob sie der Organisator ist, und sie wird nie zur Eingabe der PIN aufgefordert. Da die Einstellung des Organisators deaktiviert ist, wird die Besprechung gestartet, und die anonymen Anrufer nehmen an der Besprechung teil.

  - Wenn die Besprechung bereits gestartet wurde (eine andere Person ist bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird nie zur Eingabe der PIN aufgefordert. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt an der Besprechung teil.

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Methoden zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen von Audiokonferenzen in Microsoft 365 für Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
