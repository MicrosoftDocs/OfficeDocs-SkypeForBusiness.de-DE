---
title: Verwalten der Audiokonferenzeinstellungen für meine Organisation in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie Informationen zu den Schritten, mit denen Sie in Microsoft Teams einem Benutzer eine Lizenz für Dial-in-Konferenzen und eine Konferenzkennung zuweisen, sowie zu vielen anderen Einstellungen für Dial-in-Konferenzen. '
ms.openlocfilehash: 40a6dd3e545e913a134ae7bac80b5ec3085dc96a
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015333"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="45a52-103">Verwalten der Audiokonferenzeinstellungen für meine Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45a52-103">Manage the Audio Conferencing settings for my organization in Microsoft Teams</span></span>

<span data-ttu-id="45a52-104">Möglicherweise ist es einfacher für Sie, alle Audiokonferenzeinstellungen für Microsoft Teams an derselben Stelle zu sehen.</span><span class="sxs-lookup"><span data-stu-id="45a52-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="45a52-105">Zuweisen einer Lizenz für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="45a52-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="45a52-106">Sie können keine Lizenzen von Teams zuweisen.</span><span class="sxs-lookup"><span data-stu-id="45a52-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="45a52-107">Sie müssen das Office 365 Administrationscenter verwenden.</span><span class="sxs-lookup"><span data-stu-id="45a52-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="45a52-108">Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="45a52-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="45a52-109">**So weisen Sie eine Lizenz für einen Benutzer zu**</span><span class="sxs-lookup"><span data-stu-id="45a52-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="45a52-110">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="45a52-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="45a52-111">Navigieren Sie in der linken Navigationsleiste des **Office 365 Admin Center** zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="45a52-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45a52-112">Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="45a52-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="45a52-113">Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**.</span><span class="sxs-lookup"><span data-stu-id="45a52-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="45a52-114">Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45a52-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="45a52-p103">Aktivieren Sie auf der Seite **Produktlizenzen** die Option **Audio Conferencing** (Audiokonferenz), und klicken Sie dann auf **Speichern**. Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="45a52-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="45a52-p104">Unter Umständen wird Microsoft nach dem Zuweisen der Lizenz nicht sofort in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall im Office 365 Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="45a52-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="45a52-119">Aktivieren oder Deaktivieren der an Audiokonferenzbenutzer gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="45a52-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="45a52-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="45a52-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="45a52-121">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="45a52-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="45a52-122">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="45a52-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="45a52-123">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.</span><span class="sxs-lookup"><span data-stu-id="45a52-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="45a52-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45a52-124">Click **Save**.</span></span>

    
<span data-ttu-id="45a52-125">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="45a52-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="45a52-126">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="45a52-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="45a52-127">Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer</span><span class="sxs-lookup"><span data-stu-id="45a52-127">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="45a52-128">Sie können die e-Mail-Nachricht ändern, die automatisch an Ihre Benutzer, einschließlich der tatsächliche e-Mail-Adresse und den Anzeigenamen der Kontaktinformationen des Absenders gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="45a52-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="45a52-129">In der Standardeinstellung der Absender der e-Mail ist Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45a52-129">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="45a52-130">Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="45a52-130">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="45a52-131">Zurücksetzen der Konferenzkennung der Besprechung</span><span class="sxs-lookup"><span data-stu-id="45a52-131">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="45a52-132">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="45a52-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="45a52-133">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45a52-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="45a52-134">Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="45a52-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="45a52-135">In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="45a52-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="45a52-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="45a52-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="45a52-137">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="45a52-137">It's enabled by default.</span></span>

<span data-ttu-id="45a52-138">Siehe [Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="45a52-139">Zurücksetzen der PIN eines Konferenzorganisators</span><span class="sxs-lookup"><span data-stu-id="45a52-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="45a52-140">Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen</span><span class="sxs-lookup"><span data-stu-id="45a52-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="45a52-141">Zwar eine Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten und es eine bestimmte Anzahl festgelegt werden soll, oder Ihre Benutzer können nicht merken oder verloren haben ihre Konferenz-ID.</span><span class="sxs-lookup"><span data-stu-id="45a52-141">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

1. <span data-ttu-id="45a52-142">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="45a52-142">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="45a52-143">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45a52-143">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="45a52-144">Klicken Sie unter **Audiokonferenz** auf **PIN zurücksetzen**, und klicken Sie dann auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="45a52-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
    
<span data-ttu-id="45a52-p108">Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird \*\*\*\*\* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45a52-p108">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="45a52-149">Siehe [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-149">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="45a52-150">Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="45a52-150">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="45a52-151">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="45a52-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="45a52-152">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45a52-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="45a52-153">Klicken Sie unter **Audiokonferenz** auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).</span><span class="sxs-lookup"><span data-stu-id="45a52-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="45a52-154">Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="45a52-154">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

  
<span data-ttu-id="45a52-155">Siehe [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="45a52-156">Festlegen der in Einladungen enthaltenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="45a52-156">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="45a52-157">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="45a52-157">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="45a52-158">Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45a52-158">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="45a52-159">Im Bereich **Audiokonferenz** können Sie die **Gebührenpflichtige Nummer** und, wenn dies zulässig ist, die **Gebührenfreie Nummer** festlegen.</span><span class="sxs-lookup"><span data-stu-id="45a52-159">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="45a52-160">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45a52-160">Click **Save**.</span></span>
    
<span data-ttu-id="45a52-161">Siehe [Festlegen der in Einladungen enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-161">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="45a52-162">Auswählen von Einstellungen für die Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="45a52-162">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="45a52-163">**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="45a52-163">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="45a52-164">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="45a52-164">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="45a52-165">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="45a52-165">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="45a52-166">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).</span><span class="sxs-lookup"><span data-stu-id="45a52-166">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="45a52-167">Dies ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="45a52-167">This is enabled by default.</span></span> <span data-ttu-id="45a52-168">Wenn Sie diese Option deaktivieren, werden nicht Benutzer, die bereits an der Besprechung standardmäßig benachrichtigt, wenn jemand Beitritt oder die Besprechung verlässt.</span><span class="sxs-lookup"><span data-stu-id="45a52-168">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="45a52-169">Wählen Sie unter **Entry/exit announcement type** (Typ der Ankündigung für Zu- und Abgänge) die Option **Tones** (Töne) oder **Namen oder Telefonnummern** aus.</span><span class="sxs-lookup"><span data-stu-id="45a52-169">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="45a52-170">Wenn Sie **Namen oder Telefonnummern** ausgewählt haben, können Sie auch die Option **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen** aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="45a52-170">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="45a52-171">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45a52-171">Click **Save**.</span></span>

    
<span data-ttu-id="45a52-172">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="45a52-173">**Festlegen der Länge der PIN für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="45a52-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="45a52-174">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="45a52-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="45a52-175">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="45a52-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="45a52-176">Geben Sie auf der Seite **Bridge settings** (Brückeneinstellungen) in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45a52-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="45a52-p110">Die PIN muss aus vier bis zwölf Ziffern bestehen. Standardmäßig werden fünf Ziffern verwendet.</span><span class="sxs-lookup"><span data-stu-id="45a52-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="45a52-179">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="45a52-180">**Aktivieren oder Deaktivieren der an Audiobenutzer gesendeten E-Mails**</span><span class="sxs-lookup"><span data-stu-id="45a52-180">**Enable or disable email from being sent to audio users**</span></span>


1. <span data-ttu-id="45a52-181">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="45a52-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="45a52-182">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="45a52-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="45a52-183">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Automatically send emails to users if their audio conferencing settings change** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).</span><span class="sxs-lookup"><span data-stu-id="45a52-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="45a52-184">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45a52-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="45a52-185">Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften des Benutzers, und klicken Sie auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).</span><span class="sxs-lookup"><span data-stu-id="45a52-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="45a52-186">Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.</span><span class="sxs-lookup"><span data-stu-id="45a52-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="45a52-187">Siehe [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="45a52-188">Anzeigen und Festlegen der primären Sprache (Standardsprache) und der sekundären Sprachen (alternativen Sprachen) für eine Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="45a52-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="45a52-189">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="45a52-189">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="45a52-190">Wählen Sie in der Liste eine Telefonnummer aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45a52-190">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="45a52-191">Wählen Sie unter **Default language** (Standardsprache) und **Alternate languages (optional)** (Alternative Sprachen (optional)) die gewünschten Sprachen aus.</span><span class="sxs-lookup"><span data-stu-id="45a52-191">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="45a52-192">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45a52-192">Click **Save**.</span></span>


<span data-ttu-id="45a52-193">Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-193">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="45a52-194">Anzeigen von Einwahlnummern für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="45a52-194">See audio conferencing dial-in numbers</span></span>


1. <span data-ttu-id="45a52-195">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="45a52-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="45a52-196">Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45a52-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="45a52-197">Hier können Sie:</span><span class="sxs-lookup"><span data-stu-id="45a52-197">Here you can:</span></span>
    
  - <span data-ttu-id="45a52-198">Zeigen Sie die Telefonnummern an, die von Office 365 zur Verwendung für Audiokonferenzen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="45a52-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="45a52-199">Schauen Sie den Speicherort und die primäre Sprache, die von der automatischen Telefonzentrale Audiokonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45a52-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="45a52-200">Finden Sie unter [finden Sie eine Liste von Audiokonferenzen Zahlen](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="45a52-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="45a52-201">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="45a52-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="45a52-p112">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="45a52-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="45a52-205">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="45a52-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="45a52-206">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="45a52-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="45a52-207">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="45a52-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="45a52-208">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="45a52-208">Related topics</span></span>

[<span data-ttu-id="45a52-209">Verwalten der Audiokonferenzeinstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="45a52-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


