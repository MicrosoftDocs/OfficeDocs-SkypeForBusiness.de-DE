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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, welche Informationen automatisch per E-Mail an Benutzer gesendet werden, wenn sich deren Einstellungen für Einwahlkonferenzen in Skype for Business Online ändern. '
ms.openlocfilehash: cb456b9345d8dce1aa7a1d619371f8a2f65eab36
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011949"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>An Benutzer gesendete E-Mails, wenn ihre Einstellungen in Skype for Business Online geändert werden

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Wenn Sie in Microsoft-Teams nach automatischen E-Mail-Informationen suchen, erhalten Sie weitere Informationen unter [Benutzer gesendete E-Mails, wenn ihre Einstellungen in Microsoft-Teams geändert werden](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

E-Mails werden automatisch an Benutzer gesendet, die für [Audiokonferenzen](set-up-audio-conferencing.md) aktiviert sind und Microsoft als Audiokonferenzanbieter verwenden.
  
Standardmäßig gibt es vier Arten von E-Mails, die an die Benutzer gesendet werden, die für Audiokonferenzen aktiviert sind. Wenn Sie die Anzahl von E-Mails, die an die Benutzer gesendet werden, einschränken möchten, können Sie diese Einstellung deaktivieren. Audiokonferenzen in Microsoft 365 oder Office 365 E-Mails an die E-Mail-Adresse Ihrer Benutzer senden, wenn:
  
- **Ihnen wird eine Lizenz für Audiokonferenzen zugewiesen, oder Sie ändern den Audiokonferenzanbieter zu Microsoft.**
    
     Diese E-Mail enthält die Konferenz-ID, die Standardeinwahlnummer für Besprechungen, die PIN für Audiokonferenzen für den Benutzer sowie Anweisungen und den Link zur Verwendung des Skype for Business Online Meeting Update Tool, das zum Aktualisieren vorhandener Besprechungen für den Benutzer verwendet wird. Siehe [Zuweisen von Skype for Business-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Zuweisen von Microsoft als Audiokonferenzanbieter](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können dynamische [IDs für Audiokonferenzen in Ihrer Organisation einrichten.](./reset-a-conference-id-for-a-user.md) 
  
    So kann diese E-Mail aussehen:
    
     ![Skype for Business Lizenz überprüfen.](../images/audio-conferencing-user-enabled.png)
  
    Weitere Informationen zur Lizenzierung von Lizenzen Skype for Business Sie unter [Skype for Business-Add-On-Lizenzierung.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
    
- **Sich die Konferenz-ID oder die Standardtelefonnummer eines Benutzers ändert.**
    
    Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird. Diese E-Mail enthält jedoch nicht die PIN für Audiokonferenzen des Benutzers. Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können dynamische [IDs für Audiokonferenzen in Ihrer Organisation einrichten.](./reset-a-conference-id-for-a-user.md) 
  
    So kann diese E-Mail aussehen:
    
     ![Die Informationen für Dial-In-Konferenzen wurden geändert.](../images/audio-conferencing-info-change.png)
  
- **Die AUDIOKONFERENZ-PIN eines Benutzers wird zurückgesetzt.**
    
    Diese E-Mail enthält die AUDIOKONFERENZ-PIN des Organisators, die vorhandene Konferenz-ID und die Standardeinwahlnummer für den Benutzer. Weitere [Informationen finden Sie unter Zurücksetzen der Audiokonferenz-PIN.](reset-the-audio-conferencing-pin.md)
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können dynamische [IDs für Audiokonferenzen in Ihrer Organisation einrichten.](./reset-a-conference-id-for-a-user.md) 
  
    So kann diese E-Mail aussehen:
    
     ![Die PIN für die Dial-In-Konferenz wurde geändert.](../images/audio-conferencing-pin-has-changed.png)
  
- **Die Lizenz eines Benutzers wird entfernt, oder wenn der Audiokonferenzanbieter von Microsoft zu einem anderen Anbieter oder zu Keine wechselt.**
    
    Dies geschieht, wenn die Lizenz für **Audiokonferenzen** von einem Benutzer entfernt wird, der Audiokonferenzanbieter eines Benutzers von Microsoft auf einen Drittanbieter für Audiokonferenzen geändert wird oder wenn der Anbieter auf Kein geändert **wird.** Diese E-Mail enthält Anweisungen und Informationen für den Benutzer, mit dem Skype for Business Online Meeting Update Tool spezielle Informationen für Audiokonferenzen zu entfernen, z. B. die Standardeinwahlnummer oder die Konferenz-ID.
    
    Weitere [Informationen finden Sie unter Zuweisen oder Entfernen von Microsoft 365 Apps for Business.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)
    
    So kann diese E-Mail aussehen:
    
     !["Dial-In-Konferenzen" ist deaktiviert.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden

Sie können die E-Mail-Nachricht ändern, die automatisch an Benutzer gesendet wird. Zu den zu ändernden Optionen gehören die E-Mail-Adresse und der Anzeigename, der in der Kontaktinformation *From* enthalten ist. Standardmäßig stammt der Absender der E-Mails aus Microsoft 365 oder Office 365. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell und dem [Cmdlet Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) ändern. So ändern Sie die E-Mail-Adresse, die als Absender von E-Mail-Nachrichten an Benutzer verwendet wird:
  
- Die E-Mail-Adresse in den Parameter  _SendEmailFromAddress_ eingeben.
    
- Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.
    
- Legen Sie _den Parameter SendEmailOverride_ auf _True ._
    
Sie können Änderungen an der an Benutzer gesendeten E-Mail vornehmen, z. B. an der E-Mail-Adresse, von der die E-Mail gesendet wird, und am Anzeigenamen der E-Mail, indem Sie wie folgt ausführen:
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihrer Umgebung für eingehende E-Mails E-Mails zulassen, die von der benutzerdefinierten Von-Adresse stammen. Wenn Sie die Kontaktinformationen *From* außer Kraft setzen möchten, sollten Sie sicherstellen, dass die E-Mails ordnungsgemäß an Benutzer gesendet werden. Hierzu können Sie dies mit einem Benutzer in Ihrer Organisation testen.
  
Sie können das [Cmdlet Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) verwenden, um andere Einstellungen für Ihre Organisation zu verwalten, einschließlich E-Mail.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?

Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird. In diesem Fall werden die Konferenz-ID, die Standardtelefonnummer für Konferenzen und, noch wichtiger, die PIN für Audiokonferenzen nicht an den Benutzer gesendet. Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.
  
Standardmäßig werden E-Mails an Ihre Benutzer gesendet. Wenn Sie jedoch verhindern möchten, dass diese E-Mails für Audiokonferenzen erhalten, können Sie das Skype for Business Admin Center oder die Windows PowerShell. 
 
![Ein Symbol mit dem Skype for Business Logo.](../images/sfb-logo-30x30.png)  **Verwenden des Skype for Business Admin Centers**
    
1. Navigieren Sie **Skype for Business linken** Navigationsbereich im Admin Center zu **Audio conferencing**  >  **Microsoft Bridge-Einstellungen**.
    
2. Aktivieren oder deaktivieren **Sie auf der** Seite Einstellungen von Microsoft Bridge die Option Automatisches Senden von E-Mails an Benutzer, wenn sich **deren Audiokonferenzeinstellungen ändern.** 
    
3. Klicken Sie auf **Speichern**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Verwenden von Windows PowerShell**
  
1. Führen Sie das Folgende aus, um das Senden von E-Mails an alle Benutzer zu deaktivieren:
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

Sie können das [Cmdlet Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) verwenden, um andere Einstellungen für Ihre Organisation zu verwalten, einschließlich E-Mail.
  
## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mails wissen?

- Weitere Informationen zur Aktivierung und Deaktivierung automatisch verschickter E-Mails an Ihre Benutzer finden Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Es kann vorkommen, dass Benutzer ihre Audioinformationen verlieren. Sie müssen dann die gesamten Audioinformationen an den Benutzer senden können. Dazu klicken Sie im Skype for Business Admin Center unter  den Audiokonferenzeigenschaften für einen Benutzer auf Konferenzinformationen per E-Mail senden. Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md). Diese Informationen enthalten jedoch nicht die Audiokonferenz-PIN.
    
    Hier ist ein Beispiel für eine E-Mail, die an die Benutzer gesendet wird:
    
     ![E-Mail für Einwahlkonferenzen.](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Standardmäßig stammt der Absender der E-Mails aus Microsoft 365 oder Office 365. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell und dem [Cmdlet Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) ändern.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Herunterladen und Installieren des Teams PowerShell-Moduls][HILFE](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)(/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md)
