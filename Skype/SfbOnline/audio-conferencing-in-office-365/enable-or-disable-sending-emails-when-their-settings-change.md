---
title: Aktivieren oder Deaktivieren des Sendens von E-Mails, wenn sich die Einstellungen für Audiokonferenzen in Skype for Business Online ändern
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie Skype beim Senden von E-Mails an Benutzer aktivieren oder deaktivieren, wenn sich Einstellungen wie Anheften oder die Standardkonferenznummer ändern. '
ms.openlocfilehash: 6b9e67d8c87b023409b7934a944f298487f91289
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114251"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Aktivieren oder Deaktivieren des Sendens von E-Mails, wenn sich die Einstellungen für Audiokonferenzen in Skype for Business Online ändern

> [!Note]
> Wenn Sie das Senden von E-Mails in Microsoft Teams aktivieren oder deaktivieren möchten, lesen Sie Aktivieren oder Deaktivieren des Sendens von E-Mails, wenn sich die Einstellungen für [Audiokonferenzen in Microsoft Teams ändern.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)

Benutzer werden automatisch per E-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind. Es kann jedoch zu Zeiten kommen, in denen Sie die Anzahl der E-Mails verringern möchten, die an Skype for Business-Benutzer gesendet werden. In solchen Fällen können Sie das Senden von E-Mails deaktivieren.
  
Wenn Sie das Senden von E-Mails deaktivieren, werden Audiokonferenz-E-Mails nicht an Ihre Benutzer gesendet, einschließlich E-Mails, wenn Benutzer für Audiokonferenzen aktiviert oder deaktiviert sind, wenn ihre PIN zurückgesetzt wird und wenn sich die Konferenz-ID und die Standardtelefonnummer für Konferenzen ändern.
  
Hier ist ein Beispiel für die E-Mail, die an Benutzer gesendet wird, wenn sie für Audiokonferenzen aktiviert sind:
  
![E-Mail für Audiokonferenzen](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Wann werden E-Mails an Benutzer gesendet?

- Es gibt mehrere E-Mails, die an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:
    
  - Wenn ihnen **eine** Lizenz für Audiokonferenzen zugewiesen ist.
    
  - Wenn Sie die PIN für Audiokonferenzen des Benutzers manuell zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn die **Lizenz für Audiokonferenzen** entfernt wird.
    
  - Wenn der Audiokonferenzanbieter eines Benutzers von Microsoft zu einem anderen Anbieter oder None **geändert wird.**
    
  - Wenn der Audiokonferenzanbieter eines Benutzers in Microsoft geändert wird.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Aktivieren oder Deaktivieren des Sendens von E-Mails an Benutzer

Sie können das Skype for Business Admin Center oder Windows PowerShell verwenden, um an Benutzer gesendete E-Mails zu aktivieren oder zu deaktivieren.

 
![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**
    
1. Klicken Sie **im Skype for Business Admin Center** im linken Navigationsbereich auf **Audiokonferenzen.**
    
2. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).
    
3. Klicken Sie auf **Speichern**.
    
    > [!TIP]
    > Sie können auch E-Mails mit den Einstellungen für Audiokonferenzen an einen Benutzer senden, indem Sie zu **Audiokonferenzbenutzer** gehen, den Benutzer auswählen und auf Konferenzinformationen per  >  E-Mail **senden klicken.**  Wenn Sie dies tun, wird eine E-Mail gesendet, die nur konferenz-ID und Konferenztelefonnummer, aber nicht die PIN enthält.  Weitere Informationen finden Sie unter Senden einer [E-Mail](send-an-email-to-a-user-with-their-dial-in-information.md) an einen Benutzer mit seinen Audiokonferenzinformationen.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**
  
- Führen Sie die folgenden Schritte aus, um das Senden von E-Mails zu deaktivieren: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Hilfe zu diesem Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).
    
## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn automatische E-Mails deaktiviert sind, können Sie weiterhin manuell das Senden einer E-Mail mit der Konferenz-ID und telefonnummer über das Skype for Business Admin Center auslösen. Wenn Sie dies tun, wird die PIN jedoch nicht einbezogen. Wenn Sie die PIN für Audiokonferenzen zurücksetzen möchten und das Senden von E-Mails deaktiviert ist, müssen Sie sie auf andere Weise an den Benutzer senden.
    
- Das Senden von E-Mails an Benutzer kann über das Skype for Business Admin Center oder die Windows PowerShell deaktiviert werden.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Sie können diese Cmdlets verwenden, um Zeit zu sparen oder dies zu automatisieren.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen für Audiokonferenzen ändern](emails-sent-to-users-when-their-settings-change.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md)