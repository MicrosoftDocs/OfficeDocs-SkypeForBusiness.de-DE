---
title: An Benutzer gesendete E-Mails, wenn ihre Einstellungen in Skype for Business Online geändert werden
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Informieren Sie sich, welche Informationen automatisch per e-Mail an Benutzer gesendet werden, wenn sich die Einstellungen für Einwahlkonferenzen in Skype for Business Online ändern. '
ms.openlocfilehash: 167b083c1cc212a6d301b0cfb2012ef9d639727d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707230"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>An Benutzer gesendete E-Mails, wenn ihre Einstellungen in Skype for Business Online geändert werden

> [!Note]
> Wenn Sie in Microsoft-Teams nach automatischen E-Mail-Informationen suchen, erhalten Sie weitere Informationen unter [Benutzer gesendete E-Mails, wenn ihre Einstellungen in Microsoft-Teams geändert werden](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

E-Mail-Nachrichten werden automatisch an Benutzer gesendet, die [für Audiokonferenzen](set-up-audio-conferencing.md) mit Microsoft als Anbieter von Audiokonferenzen aktiviert sind.
  
By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing. However, if you want to limit the number of emails sent to users, you can turn it off. Audio Conferencing in Office 365 will send email to your users' email when:
  
- **Ihnen wird eine Lizenz für Audiokonferenzen zugewiesen, oder wenn Sie den Anbieter für Audiokonferenzen zu Microsoft ändern.**
    
     This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs. You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    So kann diese E-Mail aussehen:
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    Weitere Informationen zur Lizenzierung von Skype for Business finden Sie unter [Skype for Business-Add-on-Lizenzierung](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Sich die Konferenz-ID oder die Standardtelefonnummer eines Benutzers ändert.**
    
    This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user. But this email doesn't include the user's audio conferencing PIN. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs. You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    So kann diese E-Mail aussehen:
    
     ![Die Informationen für Dial-In-Konferenzen wurden geändert.](../images/audio-conferencing-info-change.png)
  
- **Die Audiokonferenz-PIN eines Benutzers wird zurückgesetzt.**
    
    This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user. See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs. You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    So kann diese E-Mail aussehen:
    
     ![Die PIN für die Dial-In-Konferenz wurde geändert.](../images/audio-conferencing-pin-has-changed.png)
  
- **Die Lizenz eines Benutzers wird entfernt, oder der Audiokonferenz-Anbieter wechselt von Microsoft zu einem anderen Anbieter oder keiner.**
    
    This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**. This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.
    
    Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    So kann diese E-Mail aussehen:
    
     !["Dial-In-Konferenzen" ist deaktiviert.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden

You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information. By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:
  
- Die E-Mail-Adresse in den Parameter  _SendEmailFromAddress_ eingeben.
    
- Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.
    
- Setzen Sie den _SendEmailOverride_ -Parameter auf _true_.
    
Sie können Änderungen an der e-Mail vornehmen, die an Benutzer gesendet wird, beispielsweise die e-Mail-Adresse, von der die e-Mail gesendet wird, und den Anzeigenamen für die e-Mail, indem Sie Folgendes ausführen:
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address. If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users. You can do this by testing this with one user in your organization.
  
Sie können das Cmdlet " [Satz-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) " verwenden, um andere Einstellungen für Ihre Organisation, einschließlich e-Mail, zu verwalten.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?

When you disable sending emails to users, email won't be sent even when a user gets assigned a license. In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user. When this happens, you must tell the user by sending them a separate email or by calling them.
  
Standardmäßig werden e-Mails an Ihre Benutzer gesendet, aber wenn Sie verhindern möchten, dass Sie e-Mails für Audiokonferenzen empfangen, können Sie das Skype for Business Admin Center oder die Windows PowerShell verwenden. 
 
![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png)Logo**im Skype for Business Admin Center**  
    
1. Wechseln Sie im **Skype for Business Admin Center**in der linken Navigationsleiste zu **Audiokonferenz** > -**Einstellungen für Microsoft Bridge**.
    
2. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** **automatisch e-Mails an Benutzer senden, wenn sich Ihre audiokonferenzeinstellungen ändern**. 
    
3. Klicken Sie auf **Speichern**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Verwenden von Windows PowerShell**
  
1. Führen Sie das Folgende aus, um das Senden von E-Mails an alle Benutzer zu deaktivieren:
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

Sie können das Cmdlet " [Satz-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) " verwenden, um andere Einstellungen für Ihre Organisation, einschließlich e-Mail, zu verwalten.
  
## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mails wissen?

- Weitere Informationen zur Aktivierung und Deaktivierung automatisch verschickter E-Mails an Ihre Benutzer finden Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Sometimes users lose their audio information and you need to be able to send them all of their audio information to them. You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md). However, this information doesn't include the audio conferencing PIN.
    
    Hier ist ein Beispiel für eine E-Mail, die an die Benutzer gesendet wird:
    
     ![E-Mail zu einer Dial-In-Konferenz](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Standardmäßig wird der Absender der e-Mails von Office 365, aber Sie können die e-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell und dem Cmdlet " [CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) " ändern.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Weitere Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md)
