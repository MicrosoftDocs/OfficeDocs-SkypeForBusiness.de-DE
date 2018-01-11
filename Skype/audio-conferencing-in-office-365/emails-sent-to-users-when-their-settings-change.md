---
title: "E-Mails an Benutzer gesendet werden, wenn ihre Einstellungen ändern"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: "Hier erfahren Sie, welche Informationen automatisch gesendet, Benutzern per e-Mail beim Ändern ihrer Einstellungen für einwahlkonferenzen. "
ms.openlocfilehash: a7746018a03a69e429eb8a5df4c68c17f29a97df
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>E-Mails an Benutzer gesendet werden, wenn ihre Einstellungen ändern

E-Mails werden automatisch für Benutzer, die [für die Audiokonferenz aktiviert](set-up-audio-conferencing.md) werden gesendet mithilfe von Microsoft als Anbieter von Audiokonferenzen.
  
Es gibt vier Typen von e-Mails, die an die Benutzer gesendet wird, die für Audiokonferenzen aktiviert sind, werden standardmäßig. Jedoch, wenn zur Begrenzung der Anzahl der e-Mail-Nachrichten an Benutzer gesendet werden soll, können Sie ihn deaktivieren. Audiokonferenzen in Office 365 sendet e-Mails an Ihrer Benutzer per e-Mail, wenn:
  
- **Auf diese oder beim Ändern des Anbieters von Audiokonferenzen an Microsoft, wird eine Audiokonferenz-Lizenz zugewiesen.**
    
     Diese e-Mail enthält die Konferenz-ID, die Konferenz Standardrufnummer für Besprechungen, die Audiokonferenz PIN für den Benutzer und die die Skype für Business Online Besprechung Update Tool verwenden, mit dem Aktualisieren vorhandener Besprechungen für, Anweisungen und Link der Benutzer. Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Microsoft als Anbieter von Audiokonferenzen zuweisen](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz IDs aktiviert wurde, haben alle eines Benutzers Besprechungen, die sie planen eindeutige Konferenz-IDs. Sie können die [dynamische Audiokonferenzen-IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten. 
  
    Es folgt ein Beispiel für diese e-Mail:
    
     ![Skype für Unternehmen Lizenz überprüfen](../images/audio-conferencing-user-enabled.png)
  
    Sie können Skype erkunden für Business Lizenzierung von [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)sehen.
    
- **Die Konferenz-ID oder Standard Konferenztelefonnummer eines Benutzers ändert.**
    
    Diese e-Mail enthält die Konferenz-ID, Standardrufnummer Konferenz, und die Anweisungen und Link, um die Skype für Business Online Besprechung aktualisieren Tools verwenden, die zum Aktualisieren von vorhandener Besprechungen des Benutzers verwendet wird. Aber diese e-Mails nicht des Benutzers Audiokonferenzen PIN enthalten. Finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz IDs aktiviert wurde, haben alle eines Benutzers Besprechungen, die sie planen eindeutige Konferenz-IDs. Sie können die [dynamische Audiokonferenzen-IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten. 
  
    Es folgt ein Beispiel für diese e-Mail:
    
     ![Einwahlkonferenzen Info wurde geändert.](../images/audio-conferencing-info-change.png)
  
- **Die PIN eines Benutzers-Audiokonferenzen wird zurückgesetzt.**
    
    Diese e-Mail enthält der Organisator Audiokonferenzen PIN, die vorhandene Konferenz-ID und die Standardrufnummer Konferenz für den Benutzer. Finden Sie unter [Audio Conferencing PIN eines Benutzers zurücksetzen](reset-the-audio-conferencing-pin-for-a-user.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz IDs aktiviert wurde, haben alle eines Benutzers Besprechungen, die sie planen eindeutige Konferenz-IDs. Sie können die [dynamische Audiokonferenzen-IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten. 
  
    Es folgt ein Beispiel für diese e-Mail:
    
     ![Einwahlkonferenzen geändert PIN.](../images/audio-conferencing-pin-has-changed.png)
  
- **Lizenz des Benutzers entfernt wird oder wenn Audiokonferenzen ändert von Microsoft in anderen Anbieter oder keiner.**
    
    Dies geschieht, wenn die **Audiokonferenz** -Lizenz eines Benutzers oder beim Ändern des Anbieters von Audiokonferenzen eines Benutzers von Microsoft an einen Drittanbieter-Audiokonferenzen oder entfernt wird, wenn den Anbieter auf **keine**festlegen. Diese e-Mail enthält die Informationen für den Benutzer mit der Skype für Business Online Besprechung Update Tool Audiokonferenzen bestimmte Informationen wie die Standard Konferenz Telefon Nummer oder Konferenz-ID entfernt und Anweisungen
    
    Finden Sie unter [zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc) oder [dritte als Anbieter von Audiokonferenzen zuweisen](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
    Es folgt ein Beispiel für diese e-Mail:
    
     ![Einwahlkonferenzen ist deaktiviert.](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Ändern Sie die e-Mail-Nachrichten, die an sie gesendet werden

Sie können die e-Mail-Nachricht ändern, die automatisch gesendet wird, um Benutzer, einschließlich der e-Mail-Adresse und den Anzeigenamen, der in die Kontaktinformationen *aus* enthalten ist. Standardmäßig werden des Absenders der e-Mail von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell und das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Um die e-Mail-Adresse ändern, die die e-Mail-Nachricht an die Benutzer senden, müssen Sie folgende Aktionen ausführen:
  
- Die E-Mail-Adresse in den Parameter  _SendEmailFromAddress_ eingeben.
    
- Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.
    
- Den Parameter _SendEmailOverride_ auf _True_festgelegt.
    
Sie können die Änderungen an der e-Mail an Benutzer, wie die e-Mail-Adresse, der von die e-Mail gesendet wird und den Anzeigenamen für die e-Mails, die durch Ausführen von vornehmen:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Wenn Sie die Informationen der e-Mail-Adresse ändern möchten, müssen Sie sicherstellen, dass die eingehenden e-Mail-Adressrichtlinien Ihrer Umgebung-e-Mails zulassen, die die benutzerdefinierten angegeben von-Adresse stammen. Wenn Sie die Kontaktinformationen *aus* außer Kraft setzen möchten, sollten Sie sicherstellen, dass die e-Mails ordnungsgemäß an Benutzer gesendet werden. Hierzu können Sie dies mit einem Benutzer in Ihrer Organisation zu testen.
  
Das Cmdlet " [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) " können Sie um andere Einstellungen für Ihre Organisation, einschließlich e-Mail zu verwalten.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Was geschieht, wenn keine e-Mail an sie gesendet werden sollen?

Wenn Sie senden-e-Mails für Benutzer deaktivieren, wird nicht e-Mail gesendet werden, auch wenn ein Benutzer eine Lizenz zugewiesen wird. In diesem Fall die Konferenz-ID default Conferencing Telefonnummer und wichtiger, ihre PIN-Audiokonferenzen wird nicht an den Benutzer gesendet werden. In diesem Fall müssen Sie den Benutzer durch eine separate e-Mail senden oder telefonisch mitteilen.
  
In der Standardeinstellung e-Mails an Ihre Benutzer gesendet, aber wenn Sie zu empfangen von e-Mail für Audiokonferenzen verhindern möchten, können Sie die Skype Business-Verwaltungskonsole oder Windows PowerShell. 
  
 **Verwenden die Skype für Business-Verwaltungskonsole**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.
    
4. Klicken Sie auf der Seite **Einstellungen für Microsoft-Brücke** de- **automatisch e-Mails an Benutzer senden, wenn Ändern ihrer Einstellungen für die Audiokonferenz**. 
    
5. Klicken Sie auf **Speichern**. 
    
 **Mithilfe von Windows PowerShell**
  
1. Führen Sie Folgendes ein, um das Senden von e-Mails an alle Benutzer zu deaktivieren:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Das Cmdlet " [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) " können Sie um andere Einstellungen für Ihre Organisation, einschließlich e-Mail zu verwalten.
  
## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mails wissen?

- Weitere auf aktivieren, und Senden von e-Mails automatisch an Ihre Benutzer deaktivieren finden Sie unter [Aktivieren oder deaktivieren Sie e-Mails senden, wenn Audiokonferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Manchmal Benutzer verlieren ihre Zugriffsinformationen enthalten, und Sie müssen sie alle ihre Audioinformationen senden können. Sie können diese Schritte durchführen, indem Sie mithilfe der Skype für Business Administrationscenter und Audiokonferenzen Eigenschaften für einen Benutzer auf **Konferenz Informationen per e-Mail senden** . Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md). Diese Informationen enthalten jedoch nicht die Audiokonferenz PIN.
    
    Es folgt ein Beispiel für diese e-Mail, die an sie gesendet wird:
    
     ![E-Mail zu einer Dial-In-Konferenz](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Standardmäßig werden des Absenders der e-Mail von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell und das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell ist alles über das Verwalten von Benutzern und welche Benutzer zugelassen oder Aktionen nicht zulässig sind. Mit Windows PowerShell können Sie eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Office 365 verwalten. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen. Informationen Sie zu dieser Vorteile in den folgenden Themen: 
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Aktivieren Sie oder deaktivieren Sie e-Mails senden, wenn Audiokonferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Senden einer e-Mails an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md)

