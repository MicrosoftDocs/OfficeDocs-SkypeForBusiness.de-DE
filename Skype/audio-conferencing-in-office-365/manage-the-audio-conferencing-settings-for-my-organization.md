---
title: "Verwalten der Audiokonferenzeinstellungen für meine Organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: 6fb10654c5845fb5524264219e642cd0a250e860
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="eb1d4-103">Verwalten der Audiokonferenzeinstellungen für meine Organisation</span><span class="sxs-lookup"><span data-stu-id="eb1d4-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="eb1d4-104">Möglicherweise ist es einfacher für Sie, alle Audiokonferenzeinstellungen für Skype for Business und Microsoft Teams an derselben Stelle zu sehen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="eb1d4-105">Zuweisen einer Lizenz für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="eb1d4-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="eb1d4-p101">Sie können Lizenzen nicht über das **Skype for Business Admin Center**zuweisen. Sie müssen das Office 365 Admin Center verwenden. Weitere Informationen finden Sie unter [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="eb1d4-109">**So weisen Sie eine Lizenz für einen Benutzer zu**</span><span class="sxs-lookup"><span data-stu-id="eb1d4-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="eb1d4-110">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-111">Navigieren Sie in der linken Navigationsleiste des **Office 365 Admin Center** zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb1d4-p102">Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**. Mit Windows PowerShell können Sie auch mehreren Benutzern Lizenzen zuweisen. Anleitungen und PowerShell-Beispielskripts finden Sie unter [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="eb1d4-116">Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="eb1d4-p103">Aktivieren Sie auf der Seite **Produktlizenzen** die Option **Audio Conferencing** (Audiokonferenz), und klicken Sie dann auf **Speichern**. Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb1d4-p104">Unter Umständen wird Microsoft nach dem Zuweisen der Lizenz nicht sofort in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall im Office 365 Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="eb1d4-121">Zuweisen einer Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="eb1d4-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="eb1d4-p105">Wenn Sie für einen Benutzer Audiokonferenzen einrichten und Microsoft der Audiokonferenzanbieter ist, wird dem Benutzer automatisch eine Konferenzkennung zugewiesen. Die zugewiesene Konferenzkennung kann statisch oder dynamisch sein und wird in der Einladung zur geplanten Besprechung gesendet.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p105">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider. The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="eb1d4-124">Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder wählen Sie eine, die leicht zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-124">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember.</span></span> <span data-ttu-id="eb1d4-125">Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen</span><span class="sxs-lookup"><span data-stu-id="eb1d4-125">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="eb1d4-126">So weisen Sie dynamische statt statische Konferenz-IDs, finden Sie unter [Audiokonferenzen mithilfe von dynamischen IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-126">If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="eb1d4-127">Führen Sie zum Einrichten einer Konferenz-ID für einen Benutzer Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="eb1d4-128">Führen Sie zum Einrichten einer Konferenz-ID für einen Benutzer Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="eb1d4-129">Eine Konferenzkennung muss sieben Ziffern umfassen. Sie kann nicht im Skype for Business Admin Center oder mit Windows PowerShell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="eb1d4-130">Weitere Informationen zum Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="eb1d4-131">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="eb1d4-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="eb1d4-133">Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-133">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="eb1d4-134">Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)und Skype für Online Business [Besprechung Migrationstool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="eb1d4-135">Siehe [Anzeigen, Bearbeiten und Zurücksetzen einer Konferenz-ID, die einem Nutzer zugewiesen wurde](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="eb1d4-136">Ändern des Audiokonferenzanbieters von Microsoft in einen Drittanbieter</span><span class="sxs-lookup"><span data-stu-id="eb1d4-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="eb1d4-137">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-138">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-139">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und klicken Sie dann, und wählen Sie den Benutzer, die Sie den Audiokonferenz-Anbieter für ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="eb1d4-140">Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="eb1d4-141">Wählen Sie auf der Seite **Eigenschaften** unter **Anbietername** den Audiokonferenzanbieter für den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb1d4-142">Wenn Sie mehrere Benutzer ausgewählt haben, können Sie nur Microsoft oder **Kein** als Audiokonferenzanbieter auswählen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="eb1d4-143">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="eb1d4-144">Aktivieren oder Deaktivieren der an Audiokonferenzbenutzer gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="eb1d4-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="eb1d4-145">Sie können die an Benutzer gesendeten E-Mails über das Skype for Business Admin Center oder über Windows PowerShell aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="eb1d4-146">**Verwenden des Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="eb1d4-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="eb1d4-147">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-148">Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="eb1d4-149">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="eb1d4-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-150">Click **Save**.</span></span>
    
    <span data-ttu-id="eb1d4-p108">Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften für den Benutzer, und klicken Sie auf **Konferenzinformationen per E-Mail senden**. Die Konferenzkennung und die Standardtelefonnummer für die Audiokonferenz sind in der Besprechungseinladung enthalten, die PIN jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p108">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="eb1d4-153">Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="eb1d4-154">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="eb1d4-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="eb1d4-155">Sie können auch Windows PowerShell verwenden und Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="eb1d4-156">Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="eb1d4-157">Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer</span><span class="sxs-lookup"><span data-stu-id="eb1d4-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="eb1d4-p109">Sie können die E-Mail, die automatisch an Ihre Benutzer gesendet wird, ändern, unter anderem die E-Mail-Adresse und den Anzeigenamen der Kontaktinformationen des Absenders. Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell und dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) ändern. Um Änderungen an der E-Mail-Adresse vorzunehmen, über die die E-Mail an die Benutzer gesendet wird, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p109">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="eb1d4-161">Geben Sie die e-Mail-Adresse in der _SendEmailFromAddress_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="eb1d4-162">Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="eb1d4-163">Den Parameter _SendEmailOverride_ auf _True_festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="eb1d4-164">Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="eb1d4-165">Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="eb1d4-166">Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="eb1d4-167">Finden Sie unter [-e-Mails, die Benutzern beim Ändern ihrer Einstellungen für die Audiokonferenz automatisch gesendet werden](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="eb1d4-168">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="eb1d4-169">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-170">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-171">Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center**zu **Audio conferencing** (Audiokonferenz), und klicken Sie im Aktionsbereich unter **Konferenzkennung** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="eb1d4-p110">Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Ja**. Daraufhin wird automatisch eine neue Konferenzkennung generiert und per E-Mail an den Benutzer gesendet, wenn das Senden von E-Mails an Ihre Benutzer aktiviert ist. Standardmäßig ist dies aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p110">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="eb1d4-175">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-175">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="eb1d4-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="eb1d4-177">Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-177">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="eb1d4-178">Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter: [Besprechung Update-Tool für Skype für Unternehmen und Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Meeting-Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047), und [Skype für Unternehmen Online, Besprechung Migrationstool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-178">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="eb1d4-179">Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="eb1d4-180">Zurücksetzen der PIN eines Organisators einer Konferenz</span><span class="sxs-lookup"><span data-stu-id="eb1d4-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="eb1d4-181">Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-181">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="eb1d4-182">Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen</span><span class="sxs-lookup"><span data-stu-id="eb1d4-182">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="eb1d4-183">Wenn Sie zuweisen dynamische statt statische-Konferenz-IDs, [Audiokonferenzen mithilfe von dynamischen IDs in Ihrer Organisation möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-183">If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="eb1d4-p113">Obwohl statische Konferenzkennungen automatisch generiert und Benutzern zugewiesen werden, kann es vorkommen, dass Benutzer diese Nummer nicht verwenden möchten und Sie daher eine bestimmte Nummer festlegen müssen. Wenn Benutzer eine leichter zu merkende Konferenzkennung wünschen oder ihre Kennung vergessen oder verloren haben, können Sie sie im Skype for Business Admin Center und mit Windows PowerShell anzeigen, ändern und zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p113">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="eb1d4-186">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-187">Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="eb1d4-188">Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="eb1d4-189">Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="eb1d4-p114">Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird \*\*\*\*\* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p114">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="eb1d4-194">Siehe [Zurücksetzen der Einwahlkonferenz-PIN für einen Benutzer](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="eb1d4-195">Senden einer E-Mail mit den Informationen zur Audiokonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="eb1d4-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="eb1d4-196">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-197">Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="eb1d4-198">Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="eb1d4-199">Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb1d4-200">Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="eb1d4-201">Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="eb1d4-202">Festlegen der Standardtelefonnummer für Audiokonferenzen für Besprechungsorganisatoren</span><span class="sxs-lookup"><span data-stu-id="eb1d4-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="eb1d4-203">**So legen Sie die Standardtelefonnummer für Audiokonferenzen für Besprechungsorganisatoren fest, wenn Sie einen Benutzer für Audiokonferenzen aktivieren**</span><span class="sxs-lookup"><span data-stu-id="eb1d4-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="eb1d4-204">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-205">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-206">Wechseln Sie im linken Navigationsbereich zur **Audiokonferenz** > **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-206">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="eb1d4-207">Wählen Sie den Benutzer, den Sie für Audiokonferenzen aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-207">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="eb1d4-208">Klicken Sie im Aktionsbereich in den Eigenschaften des Benutzers auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="eb1d4-209">Wählen Sie auf der Seite **Eigenschaften** unter **Anbietername** in der Dropdownliste den Audiokonferenzanbieter aus.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="eb1d4-210">Wenn Sie Microsoft als Audiokonferenzanbieter auswählen, können Sie die Standardtelefonnummer für Audiokonferenzen aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="eb1d4-p116">Wenn Sie einen Drittanbieter-ACP als Audiokonferenzanbieter auswählen, müssen Sie die gebührenpflichtige und gegebenenfalls die gebührenfreie Telefonnummer manuell eingeben. Bei diesen Telefonnummern handelt es sich um die Standardtelefonnummer.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p116">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number. These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="eb1d4-213">Die Standardtelefonnummer für Audiokonferenzen eines Benutzers ist die Nummer, die beim Planen einer Besprechung in der Besprechungseinladung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="eb1d4-214">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-214">Click **Save**.</span></span> 
    
<span data-ttu-id="eb1d4-215">Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="eb1d4-216">**So legen Sie die Standardtelefonnummer für Audiokonferenzen für Besprechungsorganisatoren fest, nachdem Sie einen Benutzer für Audiokonferenzen aktiviert haben**</span><span class="sxs-lookup"><span data-stu-id="eb1d4-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="eb1d4-217">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-218">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-219">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer werden soll, und klicken Sie auf der Seite Aktion auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="eb1d4-220">Wählen Sie auf der Seite **Eigenschaften** unter **Anbietername** in der Dropdownliste den Audiokonferenzanbieter aus.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="eb1d4-221">Wenn der Benutzer Microsoft als Audiokonferenzanbieter verwendet, können Sie die Standardtelefonnummer für Audiokonferenzen aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="eb1d4-222">Wenn der Benutzer einen Drittanbieter-ACP als Audiokonferenzanbieter verwendet, müssen Sie die gebührenpflichtige und gegebenenfalls die gebührenfreie Telefonnummer manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="eb1d4-223">Die Standardtelefonnummer für Audiokonferenzen eines Benutzers ist die Nummer, die beim Planen einer Besprechung in der Besprechungseinladung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="eb1d4-224">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-224">Click **Save**.</span></span> 
    
<span data-ttu-id="eb1d4-225">Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="eb1d4-226">Festlegen von Einstellungen für die Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="eb1d4-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="eb1d4-227">**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="eb1d4-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="eb1d4-228">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-229">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="eb1d4-231">Wählen Sie unter **Besprechungsteilnahme** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="eb1d4-p117">**Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits standardmäßig an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="eb1d4-234">Dies kann für jede Besprechung individuell festgelegt werden, wenn Benutzer über eine Skype for Business- oder Microsoft Teams-App an der Besprechung teilnehmen. Ändern Sie dazu in der Skype-Besprechungs-App oder der Microsoft Teams-App im Menü **Optionen** für die Besprechung die Einstellung **Zu- und Abgang von Personen ankündigen**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="eb1d4-p118">**Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p118">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="eb1d4-237">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="eb1d4-238">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="eb1d4-239">**Festlegen der Länge der PIN für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="eb1d4-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="eb1d4-240">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-241">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="eb1d4-243">Geben Sie unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="eb1d4-p119">Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p119">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="eb1d4-246">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="eb1d4-247">**Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**</span><span class="sxs-lookup"><span data-stu-id="eb1d4-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="eb1d4-248">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-249">Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="eb1d4-250">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="eb1d4-251">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-251">Click **Save**.</span></span>
    
    <span data-ttu-id="eb1d4-252">Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften des Benutzers, und klicken Sie auf **Konferenzinformationen per E-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="eb1d4-253">Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="eb1d4-254">Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="eb1d4-255">Anzeigen und Festlegen der primären und sekundären Sprachen für eine Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="eb1d4-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="eb1d4-256">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-257">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-258">Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie dann auf **Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="eb1d4-259">Wählen Sie eine Telefonnummer aus der Liste aus, klicken Sie im Aktionsbereich auf **Sprachen festlegen** und dann auf der Seite **Sprachen festlegen** auf die Liste **Primäre Sprache**. In dieser Liste werden alle unterstützten Sprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="eb1d4-p120">Außerdem können Sie die primären und sekundären Sprachen festlegen, die unterstützt werden, wenn Sie Microsoft als Audiokonferenzanbieter auswählen. Die Reihenfolge, in der Sie Ihre Auswahl in den Dropdownlisten treffen, entspricht der Reihenfolge, in der die Sprachen Anrufern genannt werden.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p120">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="eb1d4-262">Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="eb1d4-263">Anzeigen von Einwahlnummern für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="eb1d4-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="eb1d4-264">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-265">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-266">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft-Brücke**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-266">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="eb1d4-267">Hier können Sie:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-267">Here you can:</span></span>
    
  - <span data-ttu-id="eb1d4-268">Zeigen Sie die Telefonnummern an, die von Office 365 zur Verwendung für Audiokonferenzen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="eb1d4-269">Zeigen Sie den Standort sowie die primären und sekundären Sprachen an, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="eb1d4-p122">Wählen Sie die Standardtelefonnummer aus, die Benutzer erhalten, wenn sie für Audiokonferenzen aktiviert werden. Wenn jedoch die Standardtelefonnummer für die Audiokonferenzbrücke geändert wird, ändert sich die Standardtelefonnummer für vorhandene Benutzer nicht.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p122">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="eb1d4-272">Sie können wechseln Sie zur **Audiokonferenz** > **Benutzer** und wählen Sie die Eigenschaften des Benutzers ändern des Standard für einen Benutzer Zahlenformatvorlage wählen Sie eine neue Nummer aus der Liste von Zahlen, die in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="eb1d4-273">Finden Sie unter [finden Sie eine Liste von Audiokonferenzen Zahlen](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="eb1d4-274">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="eb1d4-275">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eb1d4-276">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eb1d4-277">Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz) und dann zu **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="eb1d4-278">Siehe [Anzeigen einer Liste der Benutzer, die für Einwahlkonferenzen aktiviert sind](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d4-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="eb1d4-279">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="eb1d4-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="eb1d4-280">Es gibt mehrere Einstellungen, die auf Organisationsebene mithilfe von Windows PowerShell verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-280">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="eb1d4-281">Dies vereinfacht die Einstellungen gelten für alle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-281">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="eb1d4-282">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="eb1d4-283">Hier sind die Einstellungen auf Organisationsebene:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="eb1d4-284">**Eintrag/Exit Benachrichtigungen festlegen** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="eb1d4-285">**Festlegen von Namen Aufzeichnung** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="eb1d4-286">**Festlegen der PIN-Länge** Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="eb1d4-287">**Festlegen von nur Einwahl Besprechungen über ein Telefon** Die standardmäßige _$false_.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="eb1d4-288">**Festlegen, ob e-Mail an Benutzer senden** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="eb1d4-289">**Festlegen, ob e-Mail von einem anderen Konto gesendet** Der Standardwert ist _$false_.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="eb1d4-290">**Festlegen der Absenderadresse auf e-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="eb1d4-291">**Festlegen der Anzeigename für die e-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_an.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="eb1d4-292">Möchten Sie wissen, Weitere Informationen zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb1d4-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="eb1d4-p124">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p124">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eb1d4-296">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="eb1d4-296">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="eb1d4-297">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb1d4-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="eb1d4-p125">Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="eb1d4-300">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eb1d4-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="eb1d4-301">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eb1d4-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="eb1d4-302">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eb1d4-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="eb1d4-p126">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="eb1d4-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="eb1d4-305">See Also</span><span class="sxs-lookup"><span data-stu-id="eb1d4-305">Related topics</span></span>

[<span data-ttu-id="eb1d4-306">Verwalten der Audiokonferenzeinstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="eb1d4-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="eb1d4-307">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eb1d4-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

