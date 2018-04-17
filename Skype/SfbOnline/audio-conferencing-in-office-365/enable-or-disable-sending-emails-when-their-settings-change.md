---
title: Enable or disable sending emails when their settings change
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4138ed08ef05cc1947131dab22d5470e52eda6c5
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern

Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user. In such cases, you can disable sending email.
  
If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.
  
Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:
  
![Audio Conferencing email](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Wann werden E-Mails an Benutzer gesendet?

- There are several emails that are sent to users in your organization after they are enabled for audio conferencing:
    
  - When an **Audio Conferencing** license is assigned to them.
    
  - When you manually reset the user's audio conferencing PIN.
    
  - Wenn Sie die Konferenz-PIN des Benutzers manuell zurücksetzen.
    
  - When the **Audio Conferencing** license is removed from them.
    
  - When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.
    
  - When the audio conferencing provider of a user is changed to Microsoft.
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Enable or disable email from being sent to users

You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.

**Using the Microsoft Teams and Skype for Business Admin Center**
1. In the left navigation, go to **Meetings** > **Conference Bridges**. 

2. At the top of the **Conference Bridges** page, click **Bridge Settings**. 

3. In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.

4. Klicken Sie auf **Anwenden**.
  
**Verwenden des Skype for Business Admin Center**
    
1. In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.
    
2. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).
    
3. Klicken Sie auf **Speichern**.
    
    > [!TIP]
    > You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.
  
**Verwenden von Windows PowerShell**
  
- Run the following to disable sending emails: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.
    
- Das Senden von E-Mails an Benutzer kann über das Skype for Business Admin Center oder die Windows PowerShell deaktiviert werden.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- You can use these cmdlets to save time or automate this.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>See Also

[Emails sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md)


