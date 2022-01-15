---
title: Starten Sie Audiokonferenz per Telefon ohne PIN in Teams
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
description: 'Erfahren Sie, wie Sie die Teilnahme anonymer Anrufer an einer Besprechung über Teams Admin Center aktivieren oder deaktivieren. '
ms.openlocfilehash: 2937ebc2c8ddec830c6eb130fc5824ed8273a9d3
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055705"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams

Es kann für Benutzer, die sich in eine Besprechung einwählen, frustrierend sein, wenn sie im Wartebereich der Besprechung Musik hören, da der Microsoft Teams-Besprechungsorganisator die Besprechung noch nicht gestartet hat.
  
Wenn sich ein Besprechungsorganisator in die Besprechung ein anruft, ist zum Starten einer Besprechung standardmäßig eine PIN erforderlich. Sie können einrichten, dass sich jeder in eine Besprechung einwählen kann und nicht zur Eingabe einer PIN zum Starten der Besprechung aufgefordert wird. Sie können diese Einstellung im Admin Center für einen einzelnen Benutzer aktivieren oder deaktivieren.
  
Der Besprechungsorganisator benötigt keine PIN, wenn jemand die Besprechung über die App Microsoft Teams hat. Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den Audiobenutzer gesendet, wenn ihm die Lizenz für **Audiokonferenzen** zugewiesen ist und er für Audiokonferenzen aktiviert ist. Weitere Informationen finden Sie unter Senden einer E-Mail mit den Informationen zur [Audiokonferenz](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) an einen Benutzer und E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre [Audiokonferenzeinstellungen ändern.](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**.

2. Wählen Sie einen Benutzer in der Liste aus, und klicken Sie **dann** oben auf der Seite auf Bearbeiten.

3. Klicken Sie **neben Audiokonferenz** auf **Bearbeiten**.

4. Im **Bereich Audiokonferenz können** Einwahlanrufer als erste Person an einer Besprechung **aktiviert oder deaktiviert werden.**

5. Klicken Sie auf **Anwenden**.

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell

Weitere Informationen Microsoft Teams Sie in der [PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Informationen zum Zurücksetzen der PIN finden Sie unter Zurücksetzen der [Audiokonferenz-PIN.](reset-the-audio-conferencing-pin-in-teams.md)

- Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN deaktiviert ist:

  - Wenn die Besprechung noch nicht begonnen hat (es gibt noch niemand in der Besprechung): Ein Anrufer wird aufgefordert, ob er der Organisator ist. Wenn er ja sagt, wird er zur Eingabe seiner PIN aufgefordert. Nach Eingabe der PIN beginnt die Besprechung, und der Benutzer wird an der Besprechung teilnehmen.

  - Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird auch nicht zur Eingabe der PIN aufgefordert. Die Besprechung ist bereits gestartet, und der Anrufer wird ihr beitreten.

- Wenn der anonyme Zugriff aktiviert ist oder zum Starten einer Besprechung keine PIN erforderlich ist:

  - Wenn die Besprechung noch nicht begonnen hat (es gibt noch niemand in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird auch nicht zur Eingabe der PIN aufgefordert. Da die Einstellung für den Organisator deaktiviert ist, beginnt die Besprechung und die anonymen Anrufer nehmen an der Besprechung teil.

  - Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird auch nicht zur Eingabe der PIN aufgefordert. Die Besprechung ist bereits gestartet, und der Anrufer wird ihr beitreten.

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
