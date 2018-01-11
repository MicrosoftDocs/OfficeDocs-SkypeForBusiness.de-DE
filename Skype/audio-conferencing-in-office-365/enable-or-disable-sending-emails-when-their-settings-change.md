---
title: "Aktivieren Sie oder deaktivieren Sie e-Mails senden, beim Ändern ihrer Einstellungen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4efabf42f7253d89b37282103a3046cf7b2b0d26
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern

Benutzer werden automatisch per e-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind. Unter Umständen, jedoch zur Reduzierung der Anzahl der e-Mails, die an Skype für Geschäfts- und Microsoft-Teams, Benutzer gesendet werden soll. In diesem Fall können Sie die sendende e-Mail deaktivieren.
  
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

Sie können die Skype für Business Administrationscenter oder mit Windows PowerShell verwenden, aktivieren oder Deaktivieren von e-Mail an Benutzer gesendet.
  
 **Verwenden die Skype für Business-Verwaltungskonsole**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen**, und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.
    
3. Aktivieren Sie auf der Seite **Microsoft-Brücke Einstellungen** , oder deaktivieren Sie, die **automatisch e-Mails an Benutzer senden, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.
    
4. Klicken Sie auf **Speichern**.
    
    > [!TIP]
    > Sie können e-Mail auch zu einem Benutzer mit den Einstellungen Audiokonferenzen senden, indem Sie **Audiokonferenzen**und sollte > **Benutzer**, den Benutzer auswählen und auf **Konferenz Informationen per e-Mail senden**.  Wenn Sie dies tun, wird eine e-Mail gesendet werden, dass nur Konferenz-ID und Konferenztelefonnummer, aber nicht die PIN enthält.  Weitere Informationen finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
 **Mithilfe von Windows PowerShell**
  
- Führen Sie Folgendes ein, um das Senden von e-Mails zu deaktivieren: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Hilfe mit diesem Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn die automatische e-Mails deaktiviert sind, können Sie immer noch manuell auslösen Senden einer e-Mail mit dem Konferenz-ID und Telefonnummer mithilfe der Skype für Business Administrationscenter. Wenn Sie dies tun, werden nicht die PIN jedoch eingeschlossen werden. Wenn Sie die Audiokonferenz PIN zurücksetzen möchten und Senden von e-Mails ist deaktiviert, müssen Sie ihn auf andere Weise an den Benutzer senden.
    
- In der Standardeinstellung der Absender der e-Mail-Nachrichten werden von Office 365, aber ändern Sie die e-Mail-Adresse und Anzeigename mithilfe von Windows PowerShell und auch das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) verwenden.
    
    > [!NOTE]
    >  Wenn Sie die Informationen der e-Mail-Adresse ändern möchten, müssen Sie sicherstellen, dass die eingehenden e-Mail-Adressrichtlinien Ihrer Umgebung-e-Mails zulassen, die die benutzerdefinierten angegeben von-Adresse stammen.
  
  - Die E-Mail-Adresse in den Parameter  _SendEmailFromAddress_ eingeben.
    
  - Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.
    
  - Den Parameter _SendEmailOverride_ auf _True_festgelegt.
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- Das Senden von E-Mails an Benutzer kann über das Skype for Business Admin Center oder die Windows PowerShell deaktiviert werden.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Diese Cmdlets können Sie sparen Sie Zeit oder dies zu automatisieren.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell ist alles über das Verwalten von Benutzern und welche Benutzer zugelassen oder Aktionen nicht zulässig sind. Mit Windows PowerShell können Sie eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Office 365 verwalten. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen. Informationen Sie zu dieser Vorteile in den folgenden Themen: 
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[An Benutzer gesendet wird, wenn Ändern ihrer Einstellungen für die Audiokonferenz-e-Mails](emails-sent-to-users-when-their-settings-change.md)

[Senden einer e-Mails an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md)

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)

