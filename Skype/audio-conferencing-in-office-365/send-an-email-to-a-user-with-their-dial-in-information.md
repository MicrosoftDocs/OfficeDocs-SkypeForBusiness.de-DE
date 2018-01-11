---
title: Senden einer e-Mails an einen Benutzer mit ihren Einwahlinformationen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Senden Sie Ihre Benutzer eine e-Mail mit ihren Audiokonferenzinformationen.
ms.openlocfilehash: cb7aaa956b6a679b918603e2aef2ff15ff04a779
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer

Manchmal Skype für Business oder Microsoft-Teams, Benutzer benötigen Sie möglicherweise dies ihre Informationen Audiokonferenzen veranlassen. Sie können diese Schritte durchführen, indem Sie mithilfe der **Skype für Business Administrationscenter** und unter den Eigenschaften für einen Benutzer auf **Konferenz Informationen per e-Mail senden** . Wenn Sie diese e-Mail senden, enthält sie alle Audiokonferenzinformationen, einschließlich:
  
- Die Konferenztelefon- oder Einwahltelefonnummer für den Benutzer.
    
- Die Konferenz-ID des Benutzers.
    
    > [!NOTE]
    > Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist. Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen Wenn Sie zuweisen dynamische statt statische Konferenz-IDs, [Wechseln Sie hier möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
Es folgt ein Beispiel der e-Mail, die gesendet wird:
  
![E-Mail zu einer Dial-In-Konferenz](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden Sie eine e-Mail mit Audiokonferenzinformationen an einen Benutzer

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen**, und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.
    
3. Klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus.
    
4. Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.
    
> [!TIP]
> Sie können e-Mail auch für den Benutzer mit den Einstellungen Audiokonferenzen senden, indem die Eigenschaften des Benutzers bearbeiten und dann auf **Audiokonferenzen** > **Konferenz Informationen per e-Mail senden**. 
  
## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mails wissen?

- Es gibt mehrere e-Mails, die gesendet werden, um Benutzer in Ihrer Organisation, nachdem sie aktiviert sind für Audiokonferenzen:
    
  - Wenn Ihnen eine **Audiokonferenz** -Lizenz zugewiesen wird.
    
  - Wenn Sie manuell des Benutzers Audiokonferenzen PIN zurücksetzen.
    
  - Wenn Sie die Konferenz-PIN des Benutzers manuell zurücksetzen.
    
  - Wenn eine **Audiokonferenz** Lizenz daraus entfernt wird.
    
  - Wenn der Anbieter von Audiokonferenzen für einen Benutzer von Microsoft auf einen anderen Anbieter oder **None**geändert wird.
    
  - Wenn der Anbieter von Audiokonferenzen für einen Benutzer an Microsoft geändert wird.
    
- Standardmäßig der Absender der e-Mail-Nachrichten werden von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen mithilfe von Windows PowerShell und das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Um die e-Mail-Adresse ändern, die die e-Mail an Benutzer senden, müssen Sie folgende Aktionen ausführen:
    
  - Geben Sie die e-Mail-Adresse in der SendEmailFromAddress-Parameter.
    
  - Den SendEmailOverride-Parameter auf "true" festlegen.
    
  - Geben Sie den e-Mail-Anzeigenamen im SendEmailFromDisplayName-Parameter.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der festgelegten benutzerdefinierten Absenderadresse gesendet werden. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.
    
    Um eine e-Mail an den Benutzer mit ihren Audiokonferenzinformationen senden möchten, führen Sie folgenden Befehl:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen. Informationen Sie zu dieser Vorteile in den folgenden Themen: 
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)
