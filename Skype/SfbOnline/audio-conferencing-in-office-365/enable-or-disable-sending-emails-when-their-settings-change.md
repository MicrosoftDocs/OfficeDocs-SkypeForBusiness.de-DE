---
title: Aktivieren Sie oder deaktivieren Sie e-Mails senden Wenn Audiokonferenzen Einstellungen in Skype für Business Online ändern.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: a9100de01fc835916af54d08b84dbd03a06ec1d6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370873"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Aktivieren Sie oder deaktivieren Sie e-Mails senden Wenn Audiokonferenzen Einstellungen in Skype für Business Online ändern.

> [!Note]
> Wenn Sie aktivieren oder Deaktivieren der sendenden-e-Mails in Microsoft-Teams möchten, finden Sie unter [Aktivieren oder Deaktivieren der sendenden-e-Mails Wenn Audiokonferenzen Einstellungen in Microsoft-Teams, ändern](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Benutzer werden automatisch per e-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind. Unter Umständen, jedoch, wenn die Anzahl der e-Mails zu reduzieren, die an Skype für Unternehmensbenutzer gesendet werden soll. In diesem Fall können Sie die sendende e-Mail deaktivieren.
  
Wenn Sie e-Mails senden deaktivieren, werden nicht Audiokonferenzen-e-Mails gesendet werden für die Benutzer, einschließlich e-Mails für Benutzer aktiviert oder deaktiviert für Audiokonferenzen, wenn seine PIN zurückgesetzt wurde und die Konferenz-ID und das Standard-Konferenzen ändert sich phone sind .
  
Es folgt ein Beispiel der e-Mails, die an Benutzer gesendet wird, wenn sie für Audiokonferenzen aktiviert sind:
  
![Audio Conferencing-e-Mail](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Wann werden E-Mails an Benutzer gesendet?

- Es gibt mehrere e-Mails, die gesendet werden, um Benutzer in Ihrer Organisation, nachdem sie aktiviert sind für Audiokonferenzen:
    
  - Wenn Ihnen eine **Audiokonferenz** -Lizenz zugewiesen wird.
    
  - Wenn Sie manuell des Benutzers Audiokonferenzen PIN zurücksetzen.
    
  - Wenn Sie die Konferenz-PIN des Benutzers manuell zurücksetzen.
    
  - Wenn die Lizenz **Audiokonferenzen** daraus entfernt wird.
    
  - Wenn der Anbieter von Audiokonferenzen eines Benutzers aus Microsoft in einem anderen Anbieter oder **keiner**geändert wird.
    
  - Wenn der Anbieter von Audiokonferenzen eines Benutzers an Microsoft geändert wird.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Aktivieren oder Deaktivieren von e-Mail an Benutzer gesendet wird

Sie können die an Benutzer gesendeten E-Mails über das Skype for Business Admin Center oder über Windows PowerShell aktivieren oder deaktivieren.

 
![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**
    
1. Klicken Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich auf **Audiokonferenzen**.
    
2. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).
    
3. Klicken Sie auf **Speichern**.
    
    > [!TIP]
    > Sie können e-Mail auch zu einem Benutzer mit den Einstellungen Audiokonferenzen senden, indem Sie **Audiokonferenzen**und sollte > **Benutzer**, den Benutzer auswählen und auf **Konferenz Informationen per e-Mail senden**.  Wenn Sie dies tun, wird eine e-Mail gesendet werden, dass nur Konferenz-ID und Konferenztelefonnummer, aber nicht die PIN enthält.  Weitere Informationen finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**
  
- Führen Sie Folgendes ein, um das Senden von e-Mails zu deaktivieren: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Hilfe mit diesem Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn die automatische e-Mails deaktiviert sind, können Sie immer noch manuell auslösen Senden einer e-Mail mit dem Konferenz-ID und Telefonnummer mithilfe der Skype für Business Administrationscenter. Wenn Sie dies tun, werden nicht die PIN jedoch eingeschlossen werden. Wenn Sie die Audiokonferenz PIN zurücksetzen möchten und Senden von e-Mails ist deaktiviert, müssen Sie ihn auf andere Weise an den Benutzer senden.
    
- Das Senden von E-Mails an Benutzer kann über das Skype for Business Admin Center oder die Windows PowerShell deaktiviert werden.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Diese Cmdlets können Sie sparen Sie Zeit oder dies zu automatisieren.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>See Also

[An Benutzer gesendet wird, wenn Ändern ihrer Einstellungen für die Audiokonferenz-e-Mails](emails-sent-to-users-when-their-settings-change.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md)


