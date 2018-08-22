---
title: Aktivieren Sie oder deaktivieren Sie e-Mails senden Wenn Audiokonferenzen Einstellungen in Skype für Business Online ändern.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4d52603fb0d2701cbebd58644cd002dbc94baf89
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490585"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="32db2-103">Aktivieren Sie oder deaktivieren Sie e-Mails senden Wenn Audiokonferenzen Einstellungen in Skype für Business Online ändern.</span><span class="sxs-lookup"><span data-stu-id="32db2-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="32db2-104">Wenn Sie aktivieren oder Deaktivieren der sendenden-e-Mails in Microsoft-Teams möchten, finden Sie unter [Aktivieren oder Deaktivieren der sendenden-e-Mails Wenn Audiokonferenzen Einstellungen in Microsoft-Teams, ändern](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="32db2-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="32db2-105">Benutzer werden automatisch per e-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="32db2-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="32db2-106">Unter Umständen, jedoch, wenn die Anzahl der e-Mails zu reduzieren, die an Skype für Unternehmensbenutzer gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="32db2-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="32db2-107">In diesem Fall können Sie die sendende e-Mail deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="32db2-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="32db2-108">Wenn Sie e-Mails senden deaktivieren, werden nicht Audiokonferenzen-e-Mails gesendet werden für die Benutzer, einschließlich e-Mails für Benutzer aktiviert oder deaktiviert für Audiokonferenzen, wenn seine PIN zurückgesetzt wurde und die Konferenz-ID und das Standard-Konferenzen ändert sich phone sind .</span><span class="sxs-lookup"><span data-stu-id="32db2-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="32db2-109">Es folgt ein Beispiel der e-Mails, die an Benutzer gesendet wird, wenn sie für Audiokonferenzen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="32db2-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Audio Conferencing-e-Mail](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="32db2-111">Wann werden E-Mails an Benutzer gesendet?</span><span class="sxs-lookup"><span data-stu-id="32db2-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="32db2-112">Es gibt mehrere e-Mails, die gesendet werden, um Benutzer in Ihrer Organisation, nachdem sie aktiviert sind für Audiokonferenzen:</span><span class="sxs-lookup"><span data-stu-id="32db2-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="32db2-113">Wenn Ihnen eine **Audiokonferenz** -Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="32db2-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="32db2-114">Wenn Sie manuell des Benutzers Audiokonferenzen PIN zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="32db2-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="32db2-115">Wenn Sie die Konferenz-PIN des Benutzers manuell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="32db2-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="32db2-116">Wenn die Lizenz **Audiokonferenzen** daraus entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="32db2-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="32db2-117">Wenn der Anbieter von Audiokonferenzen eines Benutzers aus Microsoft in einem anderen Anbieter oder **keiner**geändert wird.</span><span class="sxs-lookup"><span data-stu-id="32db2-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="32db2-118">Wenn der Anbieter von Audiokonferenzen eines Benutzers an Microsoft geändert wird.</span><span class="sxs-lookup"><span data-stu-id="32db2-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="32db2-119">Aktivieren oder Deaktivieren von e-Mail an Benutzer gesendet wird</span><span class="sxs-lookup"><span data-stu-id="32db2-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="32db2-120">Sie können die an Benutzer gesendeten E-Mails über das Skype for Business Admin Center oder über Windows PowerShell aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="32db2-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="32db2-121">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="32db2-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="32db2-122">Klicken Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich auf **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="32db2-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="32db2-123">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).</span><span class="sxs-lookup"><span data-stu-id="32db2-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="32db2-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="32db2-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="32db2-125">Sie können e-Mail auch zu einem Benutzer mit den Einstellungen Audiokonferenzen senden, indem Sie **Audiokonferenzen**und sollte > **Benutzer**, den Benutzer auswählen und auf **Konferenz Informationen per e-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="32db2-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="32db2-126">Wenn Sie dies tun, wird eine e-Mail gesendet werden, dass nur Konferenz-ID und Konferenztelefonnummer, aber nicht die PIN enthält.</span><span class="sxs-lookup"><span data-stu-id="32db2-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="32db2-127">Weitere Informationen finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="32db2-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="32db2-128">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="32db2-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="32db2-129">Führen Sie Folgendes ein, um das Senden von e-Mails zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="32db2-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="32db2-130">Hilfe mit diesem Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="32db2-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="32db2-131">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="32db2-131">What else should you know?</span></span>

- <span data-ttu-id="32db2-132">Wenn die automatische e-Mails deaktiviert sind, können Sie immer noch manuell auslösen Senden einer e-Mail mit dem Konferenz-ID und Telefonnummer mithilfe der Skype für Business Administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="32db2-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="32db2-133">Wenn Sie dies tun, werden nicht die PIN jedoch eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="32db2-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="32db2-134">Wenn Sie die Audiokonferenz PIN zurücksetzen möchten und Senden von e-Mails ist deaktiviert, müssen Sie ihn auf andere Weise an den Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="32db2-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="32db2-135">Das Senden von E-Mails an Benutzer kann über das Skype for Business Admin Center oder die Windows PowerShell deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="32db2-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="32db2-136">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="32db2-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="32db2-137">Diese Cmdlets können Sie sparen Sie Zeit oder dies zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="32db2-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="32db2-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="32db2-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="32db2-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="32db2-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="32db2-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="32db2-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="32db2-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="32db2-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="32db2-p104">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="32db2-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="32db2-145">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="32db2-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="32db2-146">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32db2-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="32db2-p105">Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="32db2-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="32db2-149">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="32db2-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="32db2-150">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="32db2-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="32db2-151">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="32db2-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="32db2-p106">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="32db2-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="32db2-154">See Also</span><span class="sxs-lookup"><span data-stu-id="32db2-154">Related topics</span></span>

[<span data-ttu-id="32db2-155">An Benutzer gesendet wird, wenn Ändern ihrer Einstellungen für die Audiokonferenz-e-Mails</span><span class="sxs-lookup"><span data-stu-id="32db2-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="32db2-156">Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="32db2-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


