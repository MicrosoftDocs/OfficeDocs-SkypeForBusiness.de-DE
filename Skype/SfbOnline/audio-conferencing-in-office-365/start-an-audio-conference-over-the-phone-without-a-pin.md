---
title: Starten einer Audiokonferenz über das Telefon ohne PIN in Skype for Business Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie anonyme Anrufer über das Skype for Business Admin Center oder mithilfe eines PowerShell-Skripts an einer Besprechung aktivieren oder deaktivieren können. '
ms.openlocfilehash: 6eb62e2a2a295644185b3f0e6fd424749dc5bf56
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111941"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Starten einer Audiokonferenz über das Telefon ohne PIN in Skype for Business Online

> [!Note]
> Informationen zum Starten einer Audiokonferenz ohne PIN in Microsoft Teams finden Sie unter Starten einer Audiokonferenz über das Telefon ohne [PIN in Microsoft Teams.](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)

Es kann frustrierend sein, wenn Benutzer, die sich in eine Besprechung einwählen, im Wartebereich der Besprechung Musik hören, weil der Skype for Business-Besprechungsorganisator die Besprechung noch nicht gestartet hat. 
  
Wenn sich ein Besprechungsorganisator bei der Besprechung ein aufruft, ist standardmäßig eine PIN erforderlich, um eine Besprechung zu starten. Sie können sie so einrichten, dass jeder sich zu einer Besprechung einwählen kann und nicht aufgefordert wird, eine PIN zum Starten der Besprechung zu erhalten. Sie können diese Einstellung für einen einzelnen Benutzer im Skype for Business Admin Center aktivieren oder deaktivieren.
  
Eine PIN ist für den Besprechungsorganisator nicht erforderlich, wenn jemand die Besprechung über die Skype for Business-App gestartet hat. Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den Audiobenutzer gesendet, wenn ihm die Lizenz für **Audiokonferenzen** zugewiesen wurde und für Audiokonferenzen aktiviert ist. Weitere Informationen finden Sie unter Senden einer E-Mail an einen Benutzer mit seinen [Audiokonferenzinformationen](send-an-email-to-a-user-with-their-dial-in-information.md) und E-Mails, die automatisch an Benutzer gesendet werden, wenn sich die Einstellungen für [Audiokonferenzen ändern.](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung
    
1. Wechseln Sie **im Skype for Business Admin Center** in der linken Navigation zu **Audiokonferenzbenutzer**  >  . 
    
2. Wählen Sie in der Liste den Benutzer aus, und klicken Sie im Aktionsbereich auf **Bearbeiten.** 
    
3. Wählen Oder löschen Sie auf der Eigenschaftenseite des Benutzers unter Besprechungsoptionen die Option Nicht authentifizierte Anrufer zulassen, die ersten Personen **in einer Besprechung zu sein. Andern falls nicht, wartet er im Wartebereich, bis ein authentifizierter Benutzer beitritt.**
    
4. Klicken Sie auf **Speichern**. 


    
 **Verwenden von Windows Powershell**
  
- Führen Sie Folgendes aus: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn Sie die PIN zurücksetzen möchten, lesen [Sie Zurücksetzen der PIN für Audiokonferenzen.](reset-the-audio-conferencing-pin.md)
    
- Wenn der anonyme Zugriff deaktiviert ist oder keine PIN zum Starten einer Besprechung erforderlich ist:
    
  - Wenn die Besprechung noch nicht begonnen hat (es ist noch niemand in der Besprechung): Ein Anrufer wird aufgefordert, wenn er der Organisator ist. Wenn er "Ja" sagt, wird er zur Eingabe seiner PIN aufgefordert, und nach eingabe der PIN wird die Besprechung gestartet, und der Benutzer wird an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits begonnen hat (eine andere Person ist bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird nie zur PIN aufgefordert. die Besprechung ist bereits gestartet, und der Anrufer wird ihr beitreten.
    
- Wenn anonymer Zugriff aktiviert ist oder keine PIN zum Starten einer Besprechung erforderlich ist:
    
  - Wenn die Besprechung noch nicht begonnen hat (es gibt noch niemand in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird nie zur PIN aufgefordert. Da die Einstellung des Organisators deaktiviert ist, wird die Besprechung gestartet, und die anonymen Anrufer nehmen an der Besprechung teil.
    
  - Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird nie zur PIN aufgefordert. Die Besprechung wurde bereits gestartet, und der Anrufer wird an der Besprechung teilnehmen.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang für mehrere Benutzer zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) nutzen.
    
- In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)