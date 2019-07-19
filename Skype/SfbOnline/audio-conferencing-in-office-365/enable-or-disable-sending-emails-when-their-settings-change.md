---
title: Aktivieren oder Deaktivieren des Sendens von e-Mails, wenn sich die Einstellungen für Audiokonferenzen in Skype for Business Online ändern
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 28da70d829972a7b9d3659290652c2482d409364
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792328"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Aktivieren oder Deaktivieren des Sendens von e-Mails, wenn sich die Einstellungen für Audiokonferenzen in Skype for Business Online ändern

> [!Note]
> Wenn Sie das Senden von e-Mails in Microsoft Teams aktivieren oder deaktivieren möchten, lesen Sie [Aktivieren oder Deaktivieren des Sendens von e-Mails, wenn sich die Einstellungen für Audiokonferenz in Microsoft Teams ändern](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Benutzer werden automatisch per e-Mail benachrichtigt, wenn Sie für Audiokonferenzen aktiviert sind. Es kann jedoch vorkommen, dass Sie die Anzahl der e-Mails verringern möchten, die an Skype for Business-Benutzer gesendet werden. In solchen Fällen können Sie das Senden von e-Mails deaktivieren.
  
Wenn Sie das Senden von e-Mails deaktivieren, werden keine Audiokonferenz-e-Mails an Ihre Benutzer gesendet, einschließlich e-Mails, wenn Benutzer für Audiokonferenzen aktiviert oder deaktiviert werden, wenn die PIN zurückgesetzt wird und die Konferenz-ID und die standardmäßige Konferenztelefonnummer geändert werden. .
  
Im folgenden finden Sie ein Beispiel für die e-Mail, die an Benutzer gesendet wird, wenn Sie für Audiokonferenzen aktiviert sind:
  
![E-Mail-Konferenz](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Wann werden E-Mails an Benutzer gesendet?

- Es gibt mehrere e-Mail-Nachrichten, die an Benutzer in Ihrer Organisation gesendet werden, nachdem Sie für Audiokonferenzen aktiviert wurden:
    
  - Wenn Ihnen eine **Audiokonferenz-** Lizenz zugewiesen wurde.
    
  - Wenn Sie die Audiokonferenz-PIN des Benutzers manuell zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn die **Audiokonferenz-** Lizenz von Ihnen entfernt wurde.
    
  - Wenn der Anbieter von Audiokonferenzen eines Benutzers von Microsoft auf einen anderen Anbieter oder **keinen**geändert wird.
    
  - Wenn der Audiokonferenz-Anbieter eines Benutzers zu Microsoft geändert wird.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Aktivieren oder Deaktivieren des Sendens von e-Mails an Benutzer

Sie können das Skype for Business Admin Center oder Windows PowerShell verwenden, um e-Mails zu aktivieren oder zu deaktivieren, die an Benutzer gesendet werden.

 
![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**
    
1. Klicken Sie im **Skype for Business Admin Center**im linken Navigationsbereich auf Audiokonferenzen. ****
    
2. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).
    
3. Klicken Sie auf **Speichern**.
    
    > [!TIP]
    > Sie können auch eine e-Mail mit den Einstellungen für Audiokonferenzen an einen Benutzer senden, **** > indem Sie zu Audiokonferenz-**Benutzer**wechseln, den Benutzer auswählen und auf **Konferenz Informationen per e-Mail senden**klicken.  Wenn Sie dies tun, wird eine e-Mail gesendet, die nur Konferenz-ID und Konferenztelefonnummer enthält, aber nicht die PIN.  Weitere Informationen finden Sie unter [Senden einer e-Mail-Nachricht an einen Benutzer mit den zugehörigen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md) zur Audiokonferenz.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**
  
- Führen Sie die folgenden Schritte aus, um das Senden von e-Mails zu deaktivieren: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Hilfe zu diesem Cmdlet finden Sie unter [Satz-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn automatische e-Mail-Nachrichten deaktiviert sind, können Sie mit dem Skype for Business Admin Center das Senden einer e-Mail mit der Konferenz-ID und der Telefonnummer manuell auslösen. Wenn Sie dies jedoch tun, wird die PIN nicht berücksichtigt. Wenn Sie die PIN für die Audiokonferenz zurücksetzen möchten und e-Mails nicht mehr gesendet werden sollen, müssen Sie Sie auf eine andere Weise an den Benutzer senden.
    
- Das Senden von E-Mails an Benutzer kann über das Skype for Business Admin Center oder die Windows PowerShell deaktiviert werden.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Sie können diese Cmdlets verwenden, um Zeit zu sparen oder diese zu automatisieren.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Learn about these advantages in the following topics: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[E-Mails, die an Benutzer gesendet werden, wenn sich Ihre audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md)


