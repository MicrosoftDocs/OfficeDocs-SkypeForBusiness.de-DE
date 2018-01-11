---
title: "Die Audiokonferenz Einstellungen für meine Organisation verwalten"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: "Finden Sie unter Schritte aus, um einem Benutzer, richten Sie ein Drittanbieter-Konferenzanbieter und viele andere Einstellungen für einwahlkonferenzen eine einwahlkonferenzen Lizenz und Konferenz-ID zuweisen. "
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="2271e-103">Die Audiokonferenz Einstellungen für meine Organisation verwalten</span><span class="sxs-lookup"><span data-stu-id="2271e-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="2271e-104">Alle für die Audiokonferenz für Skype für Unternehmen und die Microsoft-Teams, an einem Ort finden Sie unter erleichtert möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="2271e-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="2271e-105">Zuweisen einer Audiokonferenz-Lizenzvertrags</span><span class="sxs-lookup"><span data-stu-id="2271e-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="2271e-106">Sie können nicht mithilfe der **Skype für Business Administrationscenter**Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2271e-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="2271e-107">Sie müssen das Office 365 Administrationscenter verwenden.</span><span class="sxs-lookup"><span data-stu-id="2271e-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="2271e-108">Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="2271e-109">**So weisen eine Lizenz für einen Benutzer**</span><span class="sxs-lookup"><span data-stu-id="2271e-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="2271e-110">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-111">Wechseln Sie im linken Navigationsbereich des **Office 365 Administrationscenter**, **Benutzern** > **aktive Benutzer**, und wählen Sie dann den oder die Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="2271e-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2271e-112">Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie die Dropdownliste **Wählen Sie eine Ansicht** verwenden und klicken Sie dann wählen Sie eine der Optionen oder Ihre eigene Ansicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="2271e-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="2271e-113">Klicken Sie dann auf **Bearbeiten**, **Weiter** zweimal und klicken Sie dann wählen Sie die Lizenz aus, und klicken Sie auf **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="2271e-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="2271e-114">Sie können mehrere Benutzer auch mithilfe von Windows Powershell Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2271e-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="2271e-115">Anweisungen und PowerShell-Skriptbeispiele finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="2271e-116">Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2271e-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="2271e-117">Klicken Sie auf der Seite **Lizenzen** aktivieren Sie **Audiokonferenzen** , und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2271e-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="2271e-118">Weitere Informationen zur Lizenzierung finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="2271e-119">Nachdem Sie die Lizenz zugewiesen haben, kann Microsoft nicht zunächst in der Liste als Audiokonferenzanbieter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2271e-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="2271e-120">In diesem Fall melden Sie sich im Office 365 Administrationscenter, oder drücken Sie STRG + F5, um das Browserfenster zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2271e-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="2271e-121">Weisen Sie eine Konferenz-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="2271e-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="2271e-122">Eine Konferenz-ID wird automatisch zu einem Benutzer zugewiesen, wenn sie für Audiokonferenzen mit Microsoft als Anbieter von Audiokonferenzen festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2271e-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="2271e-123">Die Konferenz-ID zugewiesen werden kann, statische oder dynamische und wird in der besprechungseinladung gesendet, wenn die Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="2271e-123">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="2271e-124">Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder wählen Sie eine, die leicht zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="2271e-124">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember.</span></span> <span data-ttu-id="2271e-125">Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen</span><span class="sxs-lookup"><span data-stu-id="2271e-125">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="2271e-126">So weisen Sie dynamische statt statische Konferenz-IDs, finden Sie unter [Audiokonferenzen mithilfe von dynamischen IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-126">If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="2271e-127">Die Skype für Business-Verwaltungskonsole kann nicht verwendet werden, um eine Konferenz-ID, die einem Benutzer zuweisen, aber Sie können dazu das Windows PowerShell-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="2271e-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="2271e-128">Wenn die Konferenz-ID für einen Benutzer festlegen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2271e-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="2271e-129">Eine Konferenz-ID muss 7 Ziffern enthalten, und Sie ihn in die Skype für Business-Verwaltungskonsole oder mithilfe von Windows PowerShell nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="2271e-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="2271e-130">Finden Sie unter [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) erfahren Sie mehr über das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2271e-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="2271e-131">Nachdem eine neue Konferenz-ID erstellt wurde, kann nicht die alte Konferenz-ID BSSID verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2271e-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="2271e-132">Informieren Sie Benutzer von Plänen ihrer vorhandenen meeting-Einladungen für sicher, dass die neue Konferenz ansetzen, die ID der Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2271e-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="2271e-133">Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="2271e-133">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="2271e-134">Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)und Skype für Online Business [Besprechung Migrationstool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="2271e-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="2271e-135">Finden Sie unter [finden Sie unter, ändern, und setzen Sie eine Konferenz-ID, die einem Benutzer zugewiesenen zurück](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="2271e-136">Ändern des Audiokonferenz-Anbieters von Microsoft mit einem Drittanbieter-Anbieter</span><span class="sxs-lookup"><span data-stu-id="2271e-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="2271e-137">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-138">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-139">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und klicken Sie dann, und wählen Sie den Benutzer, die Sie den Audiokonferenz-Anbieter für ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="2271e-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="2271e-140">Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2271e-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="2271e-141">Wählen Sie auf **der Eigenschaftenseite unter **Anbietername**** den Anbieter von Audiokonferenzen für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2271e-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2271e-142">Wenn Sie mehrere Benutzer ausgewählt haben, können Sie nur Microsoft als Anbieter von Audiokonferenzen oder **keine** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2271e-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="2271e-143">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2271e-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="2271e-144">Aktivieren Sie oder deaktivieren Sie e-Mails senden audiokonferenzbenutzer</span><span class="sxs-lookup"><span data-stu-id="2271e-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="2271e-145">Sie können die Skype für Business Administrationscenter oder mit Windows PowerShell verwenden, aktivieren oder Deaktivieren von e-Mail an Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="2271e-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="2271e-146">**Verwenden die Skype für Business-Verwaltungskonsole**</span><span class="sxs-lookup"><span data-stu-id="2271e-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="2271e-147">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-148">Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="2271e-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="2271e-149">Aktivieren Sie auf der Seite **Microsoft-Brücke Einstellungen** , oder deaktivieren Sie, die **automatisch e-Mails an Benutzer senden, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.</span><span class="sxs-lookup"><span data-stu-id="2271e-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="2271e-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2271e-150">Click **Save**.</span></span>
    
    <span data-ttu-id="2271e-151">Sie können auch den-e-Mails für den Benutzer mit den Einstellungen Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers Audiokonferenzen und sollte und auf **Konferenz Informationen per e-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="2271e-151">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="2271e-152">Die Konferenz-ID und Standardwerte in der Audiokonferenz Telefonnummer ist auf die Besprechung einladen, aber nicht die PIN enthalten.</span><span class="sxs-lookup"><span data-stu-id="2271e-152">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="2271e-153">Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="2271e-154">**Mithilfe von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2271e-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="2271e-155">Sie können auch die Windows PowerShell verwenden und ausführen:</span><span class="sxs-lookup"><span data-stu-id="2271e-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="2271e-156">Das [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie um andere Einstellungen für Ihre Organisation, einschließlich e-Mail zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2271e-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="2271e-157">Ändern von Kontaktinformationen des Absenders in e-Mail-Nachrichten an Benutzer gesendet</span><span class="sxs-lookup"><span data-stu-id="2271e-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="2271e-158">Sie können die e-Mail-Nachricht ändern, die automatisch an Ihre Benutzer, einschließlich der tatsächliche e-Mail-Adresse und den Anzeigenamen der Kontaktinformationen des Absenders gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2271e-158">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="2271e-159">Standardmäßig ist des Absenders der e-Mail Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell und das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="2271e-159">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="2271e-160">Um die e-Mail-Adresse ändern, die die e-Mail-Nachricht an die Benutzer senden, müssen Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="2271e-160">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="2271e-161">Geben Sie die e-Mail-Adresse in der _SendEmailFromAddress_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2271e-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="2271e-162">Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="2271e-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="2271e-163">Den Parameter _SendEmailOverride_ auf _True_festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2271e-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="2271e-164">Sie können die Änderungen an der e-Mail an Benutzer, wie die e-Mail-Adresse, der von die e-Mail gesendet wird oder den Anzeigenamen für die e-Mail-durch Ausführen von vornehmen:</span><span class="sxs-lookup"><span data-stu-id="2271e-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="2271e-165">Wenn Sie die Informationen der e-Mail-Adresse ändern möchten, müssen Sie sicherstellen, dass die eingehenden e-Mail-Adressrichtlinien Ihrer Organisation-e-Mails zulassen, die von der benutzerdefinierten e-Mail-Adresse stammen.</span><span class="sxs-lookup"><span data-stu-id="2271e-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="2271e-166">Das Cmdlet " [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) " können Sie um andere Einstellungen für Ihre Organisation, einschließlich e-Mail zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2271e-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="2271e-167">Finden Sie unter [-e-Mails, die Benutzern beim Ändern ihrer Einstellungen für die Audiokonferenz automatisch gesendet werden](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="2271e-168">Zurücksetzen die Besprechung Konferenz-ID</span><span class="sxs-lookup"><span data-stu-id="2271e-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="2271e-169">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-170">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-171">Wechseln Sie an der **Audiokonferenz**, und klicken Sie im Aktionsbereich unter **Konferenz-ID**der **Skype für Business Administrationscenter**, im Navigationsbereich, klicken Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="2271e-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="2271e-172">In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="2271e-172">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="2271e-173">Eine Konferenz-ID wird automatisch erstellt und eine e-Mail an den Benutzer mit der neuen Konferenz-ID gesendet, wenn Senden von e-Mails an Ihre Benutzer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2271e-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="2271e-174">Es ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2271e-174">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="2271e-175">Nachdem eine neue Konferenz-ID erstellt wurde, kann nicht die alte Konferenz-ID BSSID verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2271e-175">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="2271e-176">Informieren Sie Benutzer von Plänen ihrer vorhandenen meeting-Einladungen für sicher, dass die neue Konferenz ansetzen, die ID der Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2271e-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="2271e-177">Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="2271e-177">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="2271e-178">Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter: [Besprechung Update-Tool für Skype für Unternehmen und Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Meeting-Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047), und [Skype für Unternehmen Online, Besprechung Migrationstool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="2271e-178">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="2271e-179">Finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="2271e-180">Zurücksetzen der PIN eines Organisators einer Konferenz</span><span class="sxs-lookup"><span data-stu-id="2271e-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="2271e-181">Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="2271e-181">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="2271e-182">Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen</span><span class="sxs-lookup"><span data-stu-id="2271e-182">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="2271e-183">Wenn Sie zuweisen dynamische statt statische-Konferenz-IDs, [Audiokonferenzen mithilfe von dynamischen IDs in Ihrer Organisation möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-183">If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="2271e-184">Zwar eine statische Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten und es eine bestimmte Anzahl festgelegt werden soll, oder Ihre Benutzer können nicht merken oder verloren haben ihre Konferenz-ID.</span><span class="sxs-lookup"><span data-stu-id="2271e-184">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="2271e-185">Sie können die Skype für Business Administrationscenter und Windows PowerShell verwenden, anzeigen, ändern und Zurücksetzen ihrer Konferenz-ID.</span><span class="sxs-lookup"><span data-stu-id="2271e-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="2271e-186">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-187">Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="2271e-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="2271e-188">Klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer, dem Sie für die PIN zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="2271e-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="2271e-189">Klicken Sie im Aktionsbereich unter **PIN**, auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="2271e-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="2271e-190">Benutzer erhalten eine e-Mail mit ihrer PIN, wenn sie aktiviert sind, für Audiokonferenzen oder wenn die PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2271e-190">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="2271e-191">Aber wenn Sie automatisch deaktiviert haben Senden von e-Mails, eine PIN zurücksetzen-e-Mail wird nicht gesendet werden und Sie müssen die PIN für den Benutzer manuell veranlassen.</span><span class="sxs-lookup"><span data-stu-id="2271e-191">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="2271e-192">Die PIN-Nummer wird nur einmal angezeigt, nachdem er zurückgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="2271e-192">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="2271e-193">Nachdem sie direkt nach der zurückzusetzende angezeigt wird, wird nicht die PIN nicht mehr auf die Benutzereigenschaften angezeigt; Stattdessen \*\*\* angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2271e-193">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="2271e-194">Finden Sie unter [Audio Conferencing PIN eines Benutzers zurücksetzen](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="2271e-195">Senden Sie eine e-Mail mit Audiokonferenz Informationen zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="2271e-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="2271e-196">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-197">Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="2271e-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="2271e-198">Klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer, dem Sie für die PIN zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="2271e-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="2271e-199">Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="2271e-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2271e-200">Wenn Sie dies tun, wird nicht die Audiokonferenz PIN an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="2271e-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="2271e-201">Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="2271e-202">Festlegen von Audiokonferenzen Standardrufnummer für Besprechungsorganisatoren</span><span class="sxs-lookup"><span data-stu-id="2271e-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="2271e-203">**Festlegen der Audiokonferenz Standardrufnummer für Besprechungsorganisatoren, wenn Sie einen Benutzer für Audiokonferenzen aktivieren**</span><span class="sxs-lookup"><span data-stu-id="2271e-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="2271e-204">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-205">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-206">Wechseln Sie im linken Navigationsbereich zur **Audiokonferenz** > **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="2271e-206">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="2271e-207">Wählen Sie den Benutzer, den Sie für Audiokonferenzen aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2271e-207">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="2271e-208">Klicken Sie im Aktionsbereich in den Eigenschaften des Benutzers auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2271e-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="2271e-209">Verwenden Sie auf der Seite **Eigenschaften** unter **Anbietername**der Dropdown Liste den Anbieter von Audiokonferenzen auswählen.</span><span class="sxs-lookup"><span data-stu-id="2271e-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="2271e-210">Wenn Sie Microsoft als Anbieter von Audiokonferenzen auswählen, können Sie Audiokonferenzen Standardrufnummer aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="2271e-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="2271e-211">Wenn Sie ein Drittanbieter-ACP als der Audiokonferenz-Anbieter auswählen, müssen Sie die gebührenpflichtige manuell eingeben und gegebenenfalls die gebührenfreie Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="2271e-211">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span> <span data-ttu-id="2271e-212">Diese Rufnummern werden die Standardrufnummer.</span><span class="sxs-lookup"><span data-stu-id="2271e-212">These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="2271e-213">Audiokonferenzen Standardrufnummer eines Benutzers ist die Nummer, die auf der besprechungseinladung angezeigt wird, wenn sie eine Besprechung planen.</span><span class="sxs-lookup"><span data-stu-id="2271e-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="2271e-214">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2271e-214">Click **Save**.</span></span> 
    
<span data-ttu-id="2271e-215">Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="2271e-216">**Festlegen der Audiokonferenz Standardrufnummer für Besprechungsorganisatoren, nachdem Sie einen Benutzer für die Audiokonferenz aktiviert haben**</span><span class="sxs-lookup"><span data-stu-id="2271e-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="2271e-217">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-218">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-219">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer werden soll, und klicken Sie auf der Seite Aktion auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2271e-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="2271e-220">Verwenden Sie auf der Seite **Eigenschaften** unter **Anbietername**der Dropdown Liste den Anbieter von Audiokonferenzen auswählen.</span><span class="sxs-lookup"><span data-stu-id="2271e-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="2271e-221">Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet wird, können Sie die Standardrufnummer Audiokonferenzen aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="2271e-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="2271e-222">Wenn der Benutzer ein Drittanbieter-ACP als Anbieter von Audiokonferenzen verwendet wird, müssen Sie die gebührenpflichtige manuell eingeben und gegebenenfalls die gebührenfreie Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="2271e-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="2271e-223">Audiokonferenzen Standardrufnummer eines Benutzers ist die Nummer, die auf der besprechungseinladung angezeigt wird, wenn sie eine Besprechung planen.</span><span class="sxs-lookup"><span data-stu-id="2271e-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="2271e-224">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2271e-224">Click **Save**.</span></span> 
    
<span data-ttu-id="2271e-225">Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="2271e-226">Audiokonferenzen Bridge Einstellungen festlegen</span><span class="sxs-lookup"><span data-stu-id="2271e-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="2271e-227">**Die besprechungsumgebung festgelegt, wenn der Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="2271e-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="2271e-228">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-229">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-230">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="2271e-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="2271e-231">Wählen Sie unter **Erleben Sie die Teilnahme an einer Besprechung**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="2271e-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="2271e-232">**Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden** Diese Option ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="2271e-232">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="2271e-233">Wenn Sie dieses Kontrollkästchen deaktivieren, werden nicht Benutzer, die bereits an der Besprechung standardmäßig benachrichtigt, wenn ein Benutzer eingibt oder die Besprechung verlässt.</span><span class="sxs-lookup"><span data-stu-id="2271e-233">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="2271e-234">Dies kann für einzelne Besprechung von Besprechungen festgelegt werden, wenn ein Benutzer eine Besprechung mit einer Skype für Business oder Microsoft-Teams app Beitritt und diese ändern Sie die Einstellung **Announce Wenn Personen eingeben oder diese verlassen** Skype-Besprechung oder Microsoft-Teams, **Optionen** im Menü des der Besprechung.</span><span class="sxs-lookup"><span data-stu-id="2271e-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="2271e-235">**Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen** Diese Option ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="2271e-235">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="2271e-236">Wenn Sie dieses Kontrollkästchen deaktivieren, werden nicht Anrufer aufgefordert, ihren Namen aufzeichnen müssen, bevor sie an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="2271e-236">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="2271e-237">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2271e-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="2271e-238">Finden Sie unter [ändern die Einstellungen für eine Audiokonferenz-Brücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="2271e-239">**Legen Sie die PIN-Mindestlänge für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="2271e-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="2271e-240">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-241">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-242">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="2271e-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="2271e-243">Klicken Sie unter **Sicherheit**Geben Sie die Anzahl der Ziffern, die Sie für die PIN-Nummer in der Liste der **PIN-Länge** verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2271e-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="2271e-244">Die PIN muss zwischen 4 und 12 Ziffern.</span><span class="sxs-lookup"><span data-stu-id="2271e-244">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="2271e-245">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="2271e-245">The default is 5.</span></span>
    
<span data-ttu-id="2271e-246">Finden Sie unter [ändern die Einstellungen für eine Audiokonferenz-Brücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="2271e-247">**Aktivieren oder Deaktivieren von e-Mail an audio-Benutzer gesendet wird**</span><span class="sxs-lookup"><span data-stu-id="2271e-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="2271e-248">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-249">Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen** , und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="2271e-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="2271e-250">Aktivieren Sie auf der Seite **Microsoft-Brücke Einstellungen** , oder deaktivieren Sie, die **automatisch e-Mails an Benutzer senden, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.</span><span class="sxs-lookup"><span data-stu-id="2271e-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="2271e-251">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2271e-251">Click **Save**.</span></span>
    
    <span data-ttu-id="2271e-252">Sie können auch den e-Mail an den Benutzer mit den Einstellungen für Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers Audiokonferenzen und sollte und auf **Konferenz Informationen per e-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="2271e-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="2271e-253">Wenn Sie dies tun, wird eine e-Mail gesendet werden, die nur enthält Konferenz-ID und Konferenztelefonnummer, doch die PIN nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="2271e-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="2271e-254">Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="2271e-255">Finden Sie unter, und legen Sie die primären und sekundären Sprachen für eine audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="2271e-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="2271e-256">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-257">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-258">In der **Skype für Business Administrationscenter**, im linken Navigationsbereich wechseln Sie zur **Audiokonferenz**, und klicken Sie dann auf **Microsoft-Brücke**.</span><span class="sxs-lookup"><span data-stu-id="2271e-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="2271e-259">Wählen Sie eine Telefonnummer aus der Liste aus, klicken Sie im Aktionsbereich auf **Sprachen festgelegt** , und klicken Sie dann auf der Seite **festlegen Sprachen** auf der Verwendung der Liste der **primären Sprache** , um die vollständige Liste der unterstützten Sprachen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2271e-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="2271e-260">Sie können auch die primären und sekundären Sprachen festlegen, die unterstützt werden, wenn Sie Microsoft als Anbieter von Audiokonferenzen auswählen.</span><span class="sxs-lookup"><span data-stu-id="2271e-260">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="2271e-261">Die Reihenfolge, die Sie in den Listen auswählen ist der gleichen Reihenfolge, in der Sprachen zu den Anrufern dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2271e-261">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="2271e-262">Finden Sie unter [Festlegen von automatischen Telefonzentralen Sprachen für Audiokonferenzen](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="2271e-263">Finden Sie unter Einwahlnummern Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="2271e-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="2271e-264">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-265">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-266">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft-Brücke**.</span><span class="sxs-lookup"><span data-stu-id="2271e-266">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="2271e-267">Hier können Sie:</span><span class="sxs-lookup"><span data-stu-id="2271e-267">Here you can:</span></span>
    
  - <span data-ttu-id="2271e-268">Zeigen Sie die Telefonnummern, die vom Office 365 festgelegt werden, für die Audiokonferenz verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2271e-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="2271e-269">Lesen Sie den Speicherort und der primären und sekundären Sprachen, die von der automatischen Telefonzentrale Audiokonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2271e-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="2271e-270">Wählen Sie die Standardrufnummer, die Benutzern gewährt wird, wenn sie für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="2271e-270">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="2271e-271">Jedoch wird nicht die Standardrufnummer über die audiokonferenzbrücke geändert wird, die Standardrufnummer für vorhandene Benutzer ändern.</span><span class="sxs-lookup"><span data-stu-id="2271e-271">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="2271e-272">Sie können wechseln Sie zur **Audiokonferenz** > **Benutzer** und wählen Sie die Eigenschaften des Benutzers ändern des Standard für einen Benutzer Zahlenformatvorlage wählen Sie eine neue Nummer aus der Liste von Zahlen, die in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2271e-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="2271e-273">Finden Sie unter [finden Sie eine Liste von Audiokonferenzen Zahlen](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="2271e-274">Anzeigen einer Liste der Benutzer, die aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="2271e-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="2271e-275">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="2271e-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2271e-276">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2271e-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2271e-277">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen**> und anschließend **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="2271e-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="2271e-278">Sehen Sie [eine Liste von Benutzern, die für Audiokonferenzen aktiviert sind](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="2271e-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2271e-279">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="2271e-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="2271e-280">Es gibt mehrere Einstellungen, die auf Organisationsebene mithilfe von Windows PowerShell verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="2271e-280">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="2271e-281">Dies vereinfacht die Einstellungen gelten für alle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2271e-281">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="2271e-282">Wenn Sie weitere Hilfe auf jedes Cmdlet erhalten möchten, finden Sie unter [Skype für Business Online Cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="2271e-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="2271e-283">Hier sind die Einstellungen auf Organisationsebene:</span><span class="sxs-lookup"><span data-stu-id="2271e-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="2271e-284">**Eintrag/Exit Benachrichtigungen festlegen** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="2271e-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="2271e-285">**Festlegen von Namen Aufzeichnung** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="2271e-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="2271e-286">**Festlegen der PIN-Länge** Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="2271e-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="2271e-287">**Festlegen von nur Einwahl Besprechungen über ein Telefon** Die standardmäßige _$false_.</span><span class="sxs-lookup"><span data-stu-id="2271e-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="2271e-288">**Festlegen, ob e-Mail an Benutzer senden** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="2271e-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="2271e-289">**Festlegen, ob e-Mail von einem anderen Konto gesendet** Der Standardwert ist _$false_.</span><span class="sxs-lookup"><span data-stu-id="2271e-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="2271e-290">**Festlegen der Absenderadresse auf e-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_an.</span><span class="sxs-lookup"><span data-stu-id="2271e-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="2271e-291">**Festlegen der Anzeigename für die e-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_an.</span><span class="sxs-lookup"><span data-stu-id="2271e-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2271e-292">Möchten Sie wissen, Weitere Informationen zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2271e-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="2271e-293">Windows PowerShell ist alles über das Verwalten von Benutzern und welche Benutzer zugelassen oder Aktionen nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="2271e-293">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2271e-294">Mit Windows PowerShell können Sie eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Office 365 verwalten.</span><span class="sxs-lookup"><span data-stu-id="2271e-294">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="2271e-295">Siehe folgende Themen, um Windows PowerShell zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="2271e-295">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2271e-296">Warum müssen Sie mithilfe von Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2271e-296">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2271e-297">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2271e-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="2271e-298">Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie Einstellungen Änderungen für viele Benutzer gleichzeitig durchführen.</span><span class="sxs-lookup"><span data-stu-id="2271e-298">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="2271e-299">Informationen Sie zu dieser Vorteile in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="2271e-299">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="2271e-300">Eine Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2271e-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="2271e-301">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2271e-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2271e-302">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2271e-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="2271e-p126">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="2271e-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="2271e-305">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2271e-305">Related topics</span></span>

[<span data-ttu-id="2271e-306">Verwalten der Audiokonferenz Einstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="2271e-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="2271e-307">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2271e-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

