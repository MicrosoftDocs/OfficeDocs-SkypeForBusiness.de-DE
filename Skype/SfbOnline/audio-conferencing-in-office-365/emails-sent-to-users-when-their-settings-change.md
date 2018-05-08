---
title: E-Mails an Benutzer gesendet werden, wenn ihre Einstellungen ändern
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. '
ms.openlocfilehash: 47225eff4d7d8bd091b2b7ba9d795c600cbd4b0e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>E-Mails an Benutzer gesendet werden, wenn ihre Einstellungen ändern

E-Mails werden automatisch für Benutzer, die [für die Audiokonferenz aktiviert](set-up-audio-conferencing.md) werden gesendet mithilfe von Microsoft als Anbieter von Audiokonferenzen.
  
Es gibt vier Typen von e-Mails, die an die Benutzer gesendet wird, die für Audiokonferenzen aktiviert sind, werden standardmäßig. Wenn Sie die Anzahl von E-Mails, die an die Benutzer gesendet werden, einschränken möchten, können Sie diese Einstellung deaktivieren. Audiokonferenzen in Office 365 sendet e-Mails an Ihrer Benutzer per e-Mail, wenn:
  
- **Auf diese oder beim Ändern des Anbieters von Audiokonferenzen an Microsoft, wird eine Audiokonferenz-Lizenz zugewiesen.**
    
     Diese e-Mail enthält die Konferenz-ID, die Konferenz Standardrufnummer für Besprechungen, die Audiokonferenz PIN für den Benutzer und die die Skype für Business Online Besprechung Update Tool verwenden, mit dem Aktualisieren vorhandener Besprechungen für, Anweisungen und Link der Benutzer. Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Microsoft als Anbieter von Audiokonferenzen zuweisen](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können die [dynamische Audiokonferenzen-IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten. 
  
    So kann diese E-Mail aussehen:
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    Weitere Informationen zur Skype for Business-Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md),
    
- **Sich die Konferenz-ID oder die Standardtelefonnummer eines Benutzers ändert.**
    
    Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird. Aber diese e-Mails nicht des Benutzers Audiokonferenzen PIN enthalten. Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können die [dynamische Audiokonferenzen-IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten. 
  
    So kann diese E-Mail aussehen:
    
     ![Die Informationen für Dial-In-Konferenzen wurden geändert.](../images/audio-conferencing-info-change.png)
  
- **Die PIN eines Benutzers-Audiokonferenzen wird zurückgesetzt.**
    
    Diese e-Mail enthält der Organisator Audiokonferenzen PIN, die vorhandene Konferenz-ID und die Standardrufnummer Konferenz für den Benutzer. Finden Sie unter [der Audiokonferenz PIN zurücksetzen](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können die [dynamische Audiokonferenzen-IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten. 
  
    So kann diese E-Mail aussehen:
    
     ![Die PIN für die Dial-In-Konferenz wurde geändert.](../images/audio-conferencing-pin-has-changed.png)
  
- **Lizenz des Benutzers entfernt wird oder wenn Audiokonferenzen ändert von Microsoft in anderen Anbieter oder keiner.**
    
    Dies geschieht, wenn die **Audiokonferenz** -Lizenz eines Benutzers oder beim Ändern des Anbieters von Audiokonferenzen eines Benutzers von Microsoft an einen Drittanbieter-Audiokonferenzen oder entfernt wird, wenn den Anbieter auf **keine**festlegen. Diese e-Mail enthält die Informationen für den Benutzer mit der Skype für Business Online Besprechung Update Tool Audiokonferenzen bestimmte Informationen wie die Standard Konferenz Telefon Nummer oder Konferenz-ID entfernt und Anweisungen
    
    Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    So kann diese E-Mail aussehen:
    
     !["Dial-In-Konferenzen" ist deaktiviert.](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden

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
  
Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?

Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird. In diesem Fall die Konferenz-ID default Conferencing Telefonnummer und wichtiger, ihre PIN-Audiokonferenzen wird nicht an den Benutzer gesendet werden. Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.
  
In der Standardeinstellung e-Mails an Ihre Benutzer gesendet, aber wenn Sie zu den Empfang von e-Mails für Audiokonferenzen verhindern möchten, können Sie Microsoft-Teams, die Skype Business-Verwaltungskonsole oder Windows PowerShell. 

![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**. 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Klicken Sie im Bereich **Bridge-Einstellungen** aktivieren oder Deaktivieren von **Benutzern Wenn Ändern ihrer Einstellungen für die Zugriffsnummer für Einwahl-e-Mails automatisch gesendet**.

4. Klicken Sie auf **Speichern**.
  
![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png)  **mithilfe der Skype für Business Administrationscenter**
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. Klicken Sie auf der Seite **Einstellungen für Microsoft-Brücke** de- **automatisch e-Mails an Benutzer senden, wenn Ändern ihrer Einstellungen für die Audiokonferenz**. 
    
3. Klicken Sie auf **Speichern**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Verwenden von Windows PowerShell**
  
1. Führen Sie das Folgende aus, um das Senden von E-Mails an alle Benutzer zu deaktivieren:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.
  
## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mails wissen?

- Weitere Informationen zur Aktivierung und Deaktivierung automatisch verschickter E-Mails an Ihre Benutzer finden Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Manchmal Benutzer verlieren ihre Zugriffsinformationen enthalten, und Sie müssen sie alle ihre Audioinformationen senden können. Sie können diese Schritte durchführen, indem Sie mithilfe der Skype für Business Administrationscenter und Audiokonferenzen Eigenschaften für einen Benutzer auf **Konferenz Informationen per e-Mail senden** . [Verwenden von Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md) Diese Informationen enthalten jedoch nicht die Audiokonferenz PIN.
    
    Hier ist ein Beispiel für eine E-Mail, die an die Benutzer gesendet wird:
    
     ![E-Mail zu einer Dial-In-Konferenz](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Standardmäßig werden des Absenders der e-Mail von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell und das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
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

[Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md)
