---
title: Beginnen einer Audio-Konferenz über das Telefon ohne PIN in Microsoft-Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informationen Sie zum Aktivieren oder Deaktivieren der anonyme Anrufern aus teilnehmen an einer Besprechung über das Teams Administrationscenter. '
ms.openlocfilehash: f85cd3e2ae0c1f87810f5b5312ba8bc9dc9d34c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861043"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Beginnen einer Audio-Konferenz über das Telefon ohne PIN in Microsoft-Teams

Es kann für Benutzer frustrierend sein, die sich in in eine Besprechung einwählen gehalten werden, in der Besprechung Wartebereich Musik hören, weil der Organisator der Besprechung Microsoft-Teams, die Besprechung noch nicht gestartet. 
  
Wenn Organisator einer Besprechung die Besprechung standardmäßig in Aufrufe ist eine PIN erforderlich, um eine Besprechung zu starten. Sie können es einrichten, damit alle Benutzer an einer Besprechung einwählen kann und keine Aufforderung des Benutzers für eine PIN, um die Besprechung zu starten. Sie können mithilfe der Verwaltungskonsole zum Aktivieren oder deaktivieren diese Einstellung für einen einzelnen Benutzer.
  
Eine PIN ist nicht für den Organisator der Besprechung erforderlich, wenn eine Person die Besprechung aus der Microsoft-Teams app gestartet wurde. Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den audio-Benutzer gesendet, die **Audiokonferenz** Lizenz zugewiesen werden und für Audiokonferenzen aktiviert sind. Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) und [E-Mails, die Benutzern beim Ändern ihrer Einstellungen für die Audiokonferenz automatisch gesendet werden](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**. 

2. Wählen Sie einen Benutzer in der Liste aus, und klicken Sie dann auf am oberen Rand der Seite **Bearbeiten** . 

3. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.

4. Klicken Sie im Bereich **Audiokonferenzen** aktivieren Sie oder deaktivieren Sie **nicht authentifizierter Anrufer die erste Person in einer Besprechung werden können**.
    
4. Klicken Sie auf **Speichern**. 

**Mithilfe von Windows Powershell**
  
Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn Sie die PIN zurücksetzen möchten, finden Sie unter [Audio Conferencing PIN zurücksetzen](reset-the-audio-conferencing-pin-in-teams.md).
    
- Wenn anonymer Zugriff oder keine erfordern eine PIN an eine Besprechung starten aktiviert ist:
    
  - Wenn die Besprechung noch nicht gestartet (es ist keine Empfänger in der Besprechung noch): ein Anrufer aufgefordert werden, wenn er der Organisator ist; Wenn er Ja angezeigt wird, wird er für seine PIN aufgefordert, und nachdem er die PIN eingibt, die Besprechung wird gestartet, und der Benutzer wird an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits gestartet (eine andere Person ist bereits in der Besprechung): ein Anrufer nicht aufgefordert werden, wenn er der Organisator ist und er nie für die PIN aufgefordert; die Besprechung wurde bereits gestartet, und der Anrufer wird verknüpfen, um.
    
- Wenn anonymer Zugriff oder keine erfordern eine PIN an eine Besprechung starten deaktiviert ist:
    
  - Wenn die Besprechung noch nicht gestartet (es ist keine Empfänger in der Besprechung noch): ein Anrufer nicht aufgefordert, wenn er der Organisator ist und er nie für die PIN aufgefordert werden werden. Da die Einstellung der Organisator der OFF festgelegt ist, die Besprechung wird gestartet, und anonyme Anrufer werden an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits gestartet (eine andere Person ist bereits in der Besprechung): ein Anrufer nicht aufgefordert, wenn er der Organisator ist und er nie für die PIN aufgefordert; die Besprechung bereits gestartet, und der Anrufer wird verknüpfen, um.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [Referenz zu Microsoft-Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Erwerben von Audiokonferenzen in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
