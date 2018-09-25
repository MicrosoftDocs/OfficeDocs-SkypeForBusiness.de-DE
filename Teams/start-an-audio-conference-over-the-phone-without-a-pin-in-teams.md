---
title: Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service:
- -msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, wie Sie im Teams Admin Center die Teilnahme anonymer Anrufer an einer Besprechung aktivieren oder deaktivieren. '
ms.openlocfilehash: 4aec566b165385a111162641f233cd1b1e3027f4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014107"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams

Für Benutzer, die sich in eine Besprechung einwählen, kann es frustrierend sein, im Wartebereich platziert zu werden und Musik zu hören, da der Microsoft Teams-Besprechungsorganisator die Besprechung noch nicht gestartet hat. 
  
Wenn Organisator einer Besprechung die Besprechung standardmäßig in Aufrufe ist eine PIN erforderlich, um eine Besprechung zu starten. Sie können es einrichten, damit alle Benutzer an einer Besprechung einwählen kann und keine Aufforderung des Benutzers für eine PIN, um die Besprechung zu starten. Sie können mithilfe der Verwaltungskonsole zum Aktivieren oder deaktivieren diese Einstellung für einen einzelnen Benutzer.
  
Eine PIN ist nicht für den Organisator der Besprechung erforderlich, wenn eine Person die Besprechung aus der Microsoft-Teams app gestartet wurde. Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den audio-Benutzer gesendet, die **Audiokonferenz** Lizenz zugewiesen werden und für Audiokonferenzen aktiviert sind. Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) und [E-Mails, die Benutzern beim Ändern ihrer Einstellungen für die Audiokonferenz automatisch gesendet werden](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren der Teilnahme anonymer Anrufer an einer Besprechung

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**. 

2. Wählen Sie einen Benutzer in der Liste aus, und klicken Sie dann oben auf der Seite auf **Bearbeiten**. 

3. Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.

4. Aktivieren oder deaktivieren Sie im Bereich **Audiokonferenz** die Option **Unauthenticated callers can be the first person in a meeting** (Nicht authentifizierte Anrufer als erste Teilnehmer an einer Besprechung zulassen).
    
4. Klicken Sie auf **Speichern**. 

**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn Sie die PIN zurücksetzen möchten, lesen Sie [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).
    
- Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN aktiviert ist, gilt Folgendes:
    
  - Wenn die Besprechung nicht begonnen hat (also noch keine Teilnehmer anwesend sind): Der Anrufer wird gefragt, ob er der Organisator ist. Wenn er dies bejaht, wird er aufgefordert, seine PIN einzugeben. Wenn er die PIN eingegeben hat, wird die Besprechung gestartet, und der Benutzer nimmt teil.
    
  - Wenn die Besprechung bereits begonnen hat (also bereits Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt teil.
    
- Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN deaktiviert ist, gilt Folgendes:
    
  - Wenn die Besprechung noch nicht gestartet (es ist keine Empfänger in der Besprechung noch): ein Anrufer nicht aufgefordert, wenn er der Organisator ist und er nie für die PIN aufgefordert werden werden. Da die Einstellung der Organisator der OFF festgelegt ist, die Besprechung wird gestartet, und anonyme Anrufer werden an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits begonnen hat (also bereits Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt teil.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
