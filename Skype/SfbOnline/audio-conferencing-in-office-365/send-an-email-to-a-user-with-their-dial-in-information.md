---
title: Senden einer E-Mail an einen Benutzer mit seinen Audiokonferenzen in Skype for Business Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Senden Sie Ihren Benutzern eine E-Mail mit ihren Audiokonferenzinformationen in Skype for Business Online.
ms.openlocfilehash: f070353069c937a62935e1cc570ebae6c0e981db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109992"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Senden einer E-Mail an einen Benutzer mit seinen Audiokonferenzinformationen in Skype for Business Online

> [!Note]
> Informationen zum Senden von Audiokonferenzinformationen an Benutzer in Microsoft Teams finden Sie unter Senden einer E-Mail an einen Benutzer mit seinen [Audiokonferenzinformationen in Microsoft Teasms.](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)

Manchmal müssen Skype for Business-Benutzer ihnen möglicherweise ihre Audiokonferenzinformationen senden. Dazu verwenden Sie das Skype for Business Admin  **Center** und klicken unter den Eigenschaften für einen Benutzer auf Konferenzinformationen per E-Mail senden. Wenn Sie diese E-Mail senden, enthält sie alle Audiokonferenzinformationen, einschließlich:
  
- Die Konferenztelefon- oder Einwahltelefonnummer für den Benutzer.
    
- Die Konferenz-ID des Benutzers.
    
   
Hier ist ein Beispiel für die gesendete E-Mail:
  
![E-Mail zu einer Dial-In-Konferenz](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten.**

3. Klicken **Sie unter Audiokonferenzen** auf **Konferenzinformationen per E-Mail senden.**

1. Melden Sie sich mit Ihrem Arbeits-, Schul- oder Schulkonto an.
    
2. Wechseln Sie zum Admin Center > **Skype for Business,** und klicken Sie in der linken Navigation auf **Audiokonferenzen.**
    
3. Klicken **Sie auf Benutzer**, und wählen Sie dann den Benutzer aus.
    
4. Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.
    
> [!TIP]
> Sie können dem Benutzer auch E-Mails mit den Einstellungen für Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers bearbeiten und dann auf **Audiokonferenzen** klicken, um Konferenzinformationen per E-Mail  >  **zu senden.** 

## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mails wissen?

- Es gibt mehrere E-Mails, die an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:
    
  - Wenn ihnen **eine** Lizenz für Audiokonferenzen zugewiesen ist.
    
  - Wenn Sie die PIN für Audiokonferenzen des Benutzers manuell zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn eine **Lizenz für Audiokonferenzen** entfernt wird.
    
  - Wenn der Audiokonferenzanbieter für einen Benutzer von Microsoft zu einem anderen Anbieter oder None **geändert wird.**
    
  - Wenn der Audiokonferenzanbieter für einen Benutzer in Microsoft geändert wird.
    
- Standardmäßig stammt der Absender der E-Mails aus Microsoft 365 oder Office 365, Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell und dem [Cmdlet Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) ändern. Um Änderungen an der E-Mail-Adresse vorzunehmen, die die E-Mail an Benutzer sendet, müssen Sie:
    
  - Geben Sie die E-Mail-Adresse im Parameter SendEmailFromAddress ein.
    
  - Legen Sie den Parameter SendEmailOverride auf Truefest.
    
  - Geben Sie den Anzeigenamen der E-Mail im Parameter SendEmailFromDisplayName ein.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der festgelegten benutzerdefinierten Absenderadresse gesendet werden. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) nutzen.
    
    Führen Sie folgendes aus, um eine E-Mail mit ihren Audiokonferenzinformationen an den Benutzer zu senden:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)