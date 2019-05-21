---
title: Senden einer e-Mail an einen Benutzer mit ihren Audiokonferenzen in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Senden Sie Ihren Benutzern eine e-Mail mit ihren Audiokonferenzinformationen in Skype for Business Online.
ms.openlocfilehash: 14c8bc3eb246cf4ab6ffa0d823ec53fbdc78d189
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302097"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Senden einer e-Mail-Nachricht an einen Benutzer mit den zugehörigen Informationen zu Audiokonferenzen in Skype for Business Online

> [!Note]
> Informationen zum Senden von Audio-Konferenz Informationen an Benutzer in Microsoft Teams finden Sie unter [Senden einer e-Mail an einen Benutzer mit den Audiokonferenzinformationen in Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Manchmal müssen Skype for Business-Benutzer Sie möglicherweise an Ihre Audiokonferenz-Informationen senden. Dazu können Sie das **Skype for Business Admin Center** verwenden und unter den Eigenschaften für einen Benutzer auf **Konferenz Informationen per e-Mail senden** klicken. Wenn Sie diese e-Mail senden, enthält Sie alle Audio-Konferenz Informationen, einschließlich:
  
- Die Konferenztelefon- oder Einwahltelefonnummer für den Benutzer.
    
- Die Konferenz-ID des Benutzers.
    
   
Hier ist ein Beispiel für die gesendete e-Mail:
  
![E-Mail zu einer Dial-In-Konferenz](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer e-Mail mit Audio-Konferenz Informationen an einen Benutzer

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken **** Sie unter Audiokonferenz auf **Konferenz Informationen in einer e-Mail senden**.

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zum **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigations **** Leiste auf Audiokonferenzen.
    
3. Klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus.
    
4. Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.
    
> [!TIP]
> Sie können auch eine e-Mail mit den Einstellungen für die Audiokonferenz an den Benutzer senden, indem Sie die Eigenschaften des **** > Benutzers bearbeiten und dann auf Audiokonferenzen**per e-Mail Konferenz Informationen senden**klicken. 

## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mails wissen?

- Es gibt mehrere e-Mail-Nachrichten, die an Benutzer in Ihrer Organisation gesendet werden, nachdem Sie für Audiokonferenzen aktiviert wurden:
    
  - Wenn Ihnen eine **Audiokonferenz-** Lizenz zugewiesen wurde.
    
  - Wenn Sie die Audiokonferenz-PIN des Benutzers manuell zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn eine **Audiokonferenz-** Lizenz von Ihnen entfernt wird.
    
  - Wenn der Anbieter für Audiokonferenzen für einen Benutzer von Microsoft zu einem anderen Anbieter oder **keiner**geändert wird.
    
  - Wenn der Audiokonferenz-Anbieter für einen Benutzer in Microsoft geändert wird.
    
- Standardmäßig wird der Absender der e-Mails von Office 365, aber Sie können die e-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell und dem Cmdlet " [Satz-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) " ändern. Wenn Sie Änderungen an der e-Mail-Adresse vornehmen möchten, die die e-Mail an Benutzer sendet, müssen Sie Folgendes tun:
    
  - Geben Sie die e-Mail-Adresse im SendEmailFromAddress-Parameter ein.
    
  - Legen Sie den Parameter SendEmailOverride auf Truefest.
    
  - Geben Sie im SendEmailFromDisplayName-Parameter den e-Mail-Anzeigenamen ein.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der festgelegten benutzerdefinierten Absenderadresse gesendet werden. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.
    
    Führen Sie die folgenden Schritte aus, um dem Benutzer eine e-Mail mit den zugehörigen Audiokonferenz Informationen zu senden:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
