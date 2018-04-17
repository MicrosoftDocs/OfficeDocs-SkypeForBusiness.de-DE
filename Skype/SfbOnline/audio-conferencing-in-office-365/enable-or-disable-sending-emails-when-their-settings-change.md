---
title: Enable or disable sending emails when their settings change
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4138ed08ef05cc1947131dab22d5470e52eda6c5
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="97f73-103">Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern</span><span class="sxs-lookup"><span data-stu-id="97f73-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="97f73-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="97f73-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="97f73-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span><span class="sxs-lookup"><span data-stu-id="97f73-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="97f73-106">In such cases, you can disable sending email.</span><span class="sxs-lookup"><span data-stu-id="97f73-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="97f73-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span><span class="sxs-lookup"><span data-stu-id="97f73-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="97f73-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span><span class="sxs-lookup"><span data-stu-id="97f73-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Audio Conferencing email](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="97f73-110">Wann werden E-Mails an Benutzer gesendet?</span><span class="sxs-lookup"><span data-stu-id="97f73-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="97f73-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span><span class="sxs-lookup"><span data-stu-id="97f73-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="97f73-112">When an **Audio Conferencing** license is assigned to them.</span><span class="sxs-lookup"><span data-stu-id="97f73-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="97f73-113">When you manually reset the user's audio conferencing PIN.</span><span class="sxs-lookup"><span data-stu-id="97f73-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="97f73-114">Wenn Sie die Konferenz-PIN des Benutzers manuell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="97f73-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="97f73-115">When the **Audio Conferencing** license is removed from them.</span><span class="sxs-lookup"><span data-stu-id="97f73-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="97f73-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span><span class="sxs-lookup"><span data-stu-id="97f73-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="97f73-117">When the audio conferencing provider of a user is changed to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="97f73-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="97f73-118">Enable or disable email from being sent to users</span><span class="sxs-lookup"><span data-stu-id="97f73-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="97f73-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span><span class="sxs-lookup"><span data-stu-id="97f73-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="97f73-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="97f73-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="97f73-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span><span class="sxs-lookup"><span data-stu-id="97f73-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="97f73-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span><span class="sxs-lookup"><span data-stu-id="97f73-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="97f73-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span><span class="sxs-lookup"><span data-stu-id="97f73-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="97f73-124">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="97f73-124">Click **Apply**.</span></span>
  
<span data-ttu-id="97f73-125">**Verwenden des Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="97f73-125">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="97f73-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span><span class="sxs-lookup"><span data-stu-id="97f73-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="97f73-127">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).</span><span class="sxs-lookup"><span data-stu-id="97f73-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="97f73-128">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="97f73-128">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="97f73-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span><span class="sxs-lookup"><span data-stu-id="97f73-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="97f73-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="97f73-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="97f73-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="97f73-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
<span data-ttu-id="97f73-132">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="97f73-132">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="97f73-133">Run the following to disable sending emails:</span><span class="sxs-lookup"><span data-stu-id="97f73-133">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="97f73-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="97f73-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="97f73-135">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="97f73-135">What else should you know?</span></span>

- <span data-ttu-id="97f73-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span><span class="sxs-lookup"><span data-stu-id="97f73-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="97f73-137">However, if you do this, the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="97f73-137">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="97f73-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span><span class="sxs-lookup"><span data-stu-id="97f73-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="97f73-139">Das Senden von E-Mails an Benutzer kann über das Skype for Business Admin Center oder die Windows PowerShell deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="97f73-139">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="97f73-140">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="97f73-140">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="97f73-141">You can use these cmdlets to save time or automate this.</span><span class="sxs-lookup"><span data-stu-id="97f73-141">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="97f73-142">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="97f73-142">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="97f73-143">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="97f73-143">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="97f73-144">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="97f73-144">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="97f73-145">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="97f73-145">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="97f73-p104">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="97f73-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="97f73-149">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="97f73-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="97f73-150">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="97f73-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="97f73-p105">Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="97f73-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="97f73-153">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="97f73-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="97f73-154">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="97f73-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="97f73-155">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="97f73-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="97f73-p106">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="97f73-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="97f73-158">See Also</span><span class="sxs-lookup"><span data-stu-id="97f73-158">Related topics</span></span>

[<span data-ttu-id="97f73-159">Emails sent to users when their Audio Conferencing settings change</span><span class="sxs-lookup"><span data-stu-id="97f73-159">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="97f73-160">Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="97f73-160">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


