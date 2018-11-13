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
ms.openlocfilehash: b63650833c7c844de11ecb833288b6568604f919
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296097"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="7f234-103">Verwalten der Audiokonferenzeinstellungen für meine Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f234-103">Manage the Audio Conferencing settings for my organization in Microsoft Teams</span></span>

<span data-ttu-id="7f234-104">Möglicherweise ist es einfacher für Sie, alle Audiokonferenzeinstellungen für Microsoft Teams an derselben Stelle zu sehen.</span><span class="sxs-lookup"><span data-stu-id="7f234-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="7f234-105">Zuweisen einer Lizenz für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="7f234-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="7f234-106">Sie können mit Microsoft Teams keine Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7f234-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="7f234-107">Dazu müssen Sie das Office 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f234-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="7f234-108">Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="7f234-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="7f234-109">**So weisen Sie eine Lizenz für einen Benutzer zu**</span><span class="sxs-lookup"><span data-stu-id="7f234-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="7f234-110">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="7f234-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7f234-111">Navigieren Sie in der linken Navigationsleiste des **Office 365 Admin Center** zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="7f234-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f234-112">Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f234-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="7f234-113">Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Submit** (Übermitteln).</span><span class="sxs-lookup"><span data-stu-id="7f234-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="7f234-114">Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7f234-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="7f234-p103">Aktivieren Sie auf der Seite **Produktlizenzen** die Option **Audio Conferencing** (Audiokonferenz), und klicken Sie dann auf **Speichern**. Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="7f234-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="7f234-p104">Unter Umständen wird Microsoft nach dem Zuweisen der Lizenz nicht sofort in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall im Office 365 Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7f234-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="7f234-119">Aktivieren oder Deaktivieren der an Audiokonferenzbenutzer gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="7f234-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="7f234-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="7f234-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7f234-121">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="7f234-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7f234-122">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="7f234-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="7f234-123">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.</span><span class="sxs-lookup"><span data-stu-id="7f234-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="7f234-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f234-124">Click **Save**.</span></span>

    
<span data-ttu-id="7f234-125">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7f234-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="7f234-126">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="7f234-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="7f234-127">Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer</span><span class="sxs-lookup"><span data-stu-id="7f234-127">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="7f234-128">Sie können Änderungen an der E-Mail vornehmen, die automatisch an Benutzer gesendet wird. Dazu gehören die tatsächliche E-Mail-Adresse und der Anzeigename in den Kontaktinformationen des Absenders.</span><span class="sxs-lookup"><span data-stu-id="7f234-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="7f234-129">Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="7f234-129">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="7f234-130">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="7f234-130">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="7f234-131">Zurücksetzen der Konferenzkennung der Besprechung</span><span class="sxs-lookup"><span data-stu-id="7f234-131">Reset the meeting conference ID</span></span>

<span data-ttu-id="7f234-132">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7f234-132">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7f234-133">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="7f234-133">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7f234-134">Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="7f234-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="7f234-135">Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="7f234-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="7f234-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="7f234-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="7f234-137">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7f234-137">It's enabled by default.</span></span>

<span data-ttu-id="7f234-138">Siehe [Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="7f234-139">Zurücksetzen der PIN eines Konferenzorganisators</span><span class="sxs-lookup"><span data-stu-id="7f234-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="7f234-140">Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen</span><span class="sxs-lookup"><span data-stu-id="7f234-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="7f234-141">Obwohl Konferenzkennungen automatisch generiert und Benutzern zugewiesen werden, kann es vorkommen, dass Benutzer diese Nummer nicht verwenden möchten und Sie daher eine bestimmte Nummer festlegen müssen. Es ist auch möglich, dass Benutzer ihre Konferenzkennung vergessen oder verloren haben.</span><span class="sxs-lookup"><span data-stu-id="7f234-141">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="7f234-142">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7f234-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7f234-143">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="7f234-143">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7f234-144">Klicken Sie unter **Audiokonferenz** auf **PIN zurücksetzen**, und klicken Sie dann auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="7f234-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="7f234-p108">Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird \*\*\*\*\* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f234-p108">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="7f234-149">Siehe [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-149">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="7f234-150">Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="7f234-150">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="7f234-151">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7f234-151">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7f234-152">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="7f234-152">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7f234-153">Klicken Sie unter **Audiokonferenz** auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).</span><span class="sxs-lookup"><span data-stu-id="7f234-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="7f234-154">Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="7f234-154">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="7f234-155">Siehe [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="7f234-156">Festlegen der in Einladungen enthaltenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="7f234-156">Set the phone numbers included on invites</span></span>

<span data-ttu-id="7f234-157">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7f234-157">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7f234-158">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="7f234-158">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7f234-159">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7f234-159">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="7f234-160">Klicken Sie im Bereich **Audiokonferenzen** können Sie die **gebührenpflichtige Telefonnummer** festlegen und, falls zulässig, die **gebührenfreie Telefonnummer**.</span><span class="sxs-lookup"><span data-stu-id="7f234-160">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="7f234-161">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f234-161">Click **Save**.</span></span>
    
<span data-ttu-id="7f234-162">Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-162">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="7f234-163">Auswählen von Audiokonferenzen Brücke</span><span class="sxs-lookup"><span data-stu-id="7f234-163">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="7f234-164">**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="7f234-164">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="7f234-165">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7f234-165">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7f234-166">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="7f234-166">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7f234-167">Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="7f234-167">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="7f234-168">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).</span><span class="sxs-lookup"><span data-stu-id="7f234-168">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="7f234-169">Dies ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7f234-169">This is enabled by default.</span></span> <span data-ttu-id="7f234-170">Wenn Sie diese Option deaktivieren, werden nicht Benutzer, die bereits an der Besprechung standardmäßig benachrichtigt, wenn jemand Beitritt oder die Besprechung verlässt.</span><span class="sxs-lookup"><span data-stu-id="7f234-170">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="7f234-171">Wählen Sie unter **Entry/Exit Ankündigung Typ** **Töne** oder **Namen, oder Rufnummern**.</span><span class="sxs-lookup"><span data-stu-id="7f234-171">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="7f234-172">Wenn Sie den **Namen oder die Telefonnummern**auswählen, können Sie auch auswählen, aktivieren oder Deaktivieren von **Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen**.</span><span class="sxs-lookup"><span data-stu-id="7f234-172">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="7f234-173">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f234-173">Click **Save**.</span></span>

    
<span data-ttu-id="7f234-174">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-174">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="7f234-175">**Festlegen der Länge der PIN für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="7f234-175">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="7f234-176">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="7f234-176">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7f234-177">Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="7f234-177">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="7f234-178">Klicken Sie im Bereich **Einstellungen Bridge** Geben Sie die Anzahl der Ziffern, die Sie für die PIN-Nummer in der Liste der **PIN-Länge** verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f234-178">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="7f234-p110">Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.</span><span class="sxs-lookup"><span data-stu-id="7f234-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="7f234-181">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-181">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="7f234-182">**Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**</span><span class="sxs-lookup"><span data-stu-id="7f234-182">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="7f234-183">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="7f234-183">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7f234-184">Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="7f234-184">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="7f234-185">Klicken Sie im Bereich **Bridge-Einstellungen** aktivieren oder deaktivieren **für Benutzer-e-Mails automatisch gesendet, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.</span><span class="sxs-lookup"><span data-stu-id="7f234-185">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="7f234-186">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f234-186">Click **Save**.</span></span> 
 
    <span data-ttu-id="7f234-187">Sie können auch den e-Mail an den Benutzer mit den Einstellungen für Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers Audiokonferenzen und sollte und auf **Konferenz Informationen in e-Mail-Nachricht senden**.</span><span class="sxs-lookup"><span data-stu-id="7f234-187">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="7f234-188">Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.</span><span class="sxs-lookup"><span data-stu-id="7f234-188">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="7f234-189">Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-189">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="7f234-190">Finden Sie unter, und legen Sie die primären (Standard) und die sekundären Sprachen (alternative) auf eine audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="7f234-190">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="7f234-191">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7f234-191">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7f234-192">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="7f234-192">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7f234-193">Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7f234-193">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="7f234-194">Wählen Sie die Sprachen, die Sie unter **Default Language** und **(optional) alternative Sprachen**werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f234-194">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="7f234-195">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f234-195">Click **Save**.</span></span>


<span data-ttu-id="7f234-196">Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-196">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="7f234-197">Anzeigen von Einwahlnummern für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="7f234-197">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="7f234-198">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7f234-198">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7f234-199">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="7f234-199">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7f234-200">Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7f234-200">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="7f234-201">Hier können Sie:</span><span class="sxs-lookup"><span data-stu-id="7f234-201">Here you can:</span></span>
    
   - <span data-ttu-id="7f234-202">Zeigen Sie die Telefonnummern an, die von Office 365 zur Verwendung für Audiokonferenzen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7f234-202">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="7f234-203">Schauen Sie den Speicherort und die primäre Sprache, die von der automatischen Telefonzentrale Audiokonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f234-203">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="7f234-204">Finden Sie unter [finden Sie eine Liste von Audiokonferenzen Zahlen](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-204">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7f234-205">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="7f234-205">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7f234-p112">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7f234-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7f234-209">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="7f234-209">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7f234-210">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f234-210">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="7f234-211">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="7f234-211">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="7f234-212">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7f234-212">Related topics</span></span>

[<span data-ttu-id="7f234-213">Verwalten der Audiokonferenzeinstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="7f234-213">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


