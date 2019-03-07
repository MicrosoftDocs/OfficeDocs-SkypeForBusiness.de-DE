---
title: Verwalten der Audiokonferenz-Einstellungen für Ihre Organisation in Microsoft Teams.
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
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie Informationen zu den Schritten, mit denen Sie in Microsoft Teams einem Benutzer eine Lizenz für Dial-in-Konferenzen und eine Konferenzkennung zuweisen, sowie zu vielen anderen Einstellungen für Dial-in-Konferenzen. '
ms.openlocfilehash: 201da13370852b6506fe7aa32f695d973bcc637a
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463892"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="4ac8b-103">Verwalten der Audiokonferenz-Einstellungen für Ihre Organisation in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="4ac8b-104">Möglicherweise ist es einfacher für Sie, alle Audiokonferenzeinstellungen für Microsoft Teams an derselben Stelle zu sehen.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="4ac8b-105">Zuweisen einer Lizenz für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="4ac8b-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="4ac8b-106">Sie können mit Microsoft Teams keine Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="4ac8b-107">Dazu müssen Sie das Office 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="4ac8b-108">Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-108">See [Assign Skype for Business and Microsoft Teams licenses](assign-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="4ac8b-109">**So weisen Sie eine Lizenz für einen Benutzer zu**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="4ac8b-110">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="4ac8b-111">Navigieren Sie in der linken Navigationsleiste des **Office 365 Admin Center** zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ac8b-112">Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="4ac8b-113">Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Submit** (Übermitteln).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="4ac8b-114">Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="4ac8b-115">Klicken Sie auf der Seite **Lizenzen** aktivieren Sie **Audiokonferenzen** , und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="4ac8b-116">Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-116">For more on licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ac8b-p104">Unter Umständen wird Microsoft nach dem Zuweisen der Lizenz nicht sofort in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall im Office 365 Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="4ac8b-119">Aktivieren oder Deaktivieren der an Audiokonferenzbenutzer gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="4ac8b-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="4ac8b-120">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ac8b-121">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4ac8b-122">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="4ac8b-123">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="4ac8b-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-124">Click **Save**.</span></span>

    
<span data-ttu-id="4ac8b-125">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="4ac8b-126">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="4ac8b-127">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="4ac8b-128">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-128">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ac8b-129">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4ac8b-130">Klicken Sie unter **Audiokonferenzen**auf **Konferenz-ID zurückgesetzt**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="4ac8b-131">In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="4ac8b-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="4ac8b-133">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-133">It's enabled by default.</span></span>

<span data-ttu-id="4ac8b-134">Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="4ac8b-135">Zurücksetzen der PIN eines Organisators einer Konferenz</span><span class="sxs-lookup"><span data-stu-id="4ac8b-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="4ac8b-136">Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen</span><span class="sxs-lookup"><span data-stu-id="4ac8b-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="4ac8b-137">Zwar eine Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten und es eine bestimmte Anzahl festgelegt werden soll, oder Ihre Benutzer können nicht merken oder verloren haben ihre Konferenz-ID.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="4ac8b-138">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-138">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ac8b-139">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4ac8b-140">Klicken Sie unter **Audiokonferenzen**klicken Sie auf **Zurücksetzen PIN**und klicken Sie dann auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="4ac8b-p107">Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird \*\*\*\*\* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-p107">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="4ac8b-145">Finden Sie unter [der Audiokonferenz PIN zurücksetzen](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="4ac8b-146">Senden einer E-Mail mit den Informationen zur Audiokonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="4ac8b-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="4ac8b-147">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-147">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ac8b-148">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4ac8b-149">Klicken Sie unter **Audiokonferenzen**auf **Konferenz Informationen in e-Mail-Nachricht senden**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="4ac8b-150">Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="4ac8b-151">Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="4ac8b-152">Festlegen der in Einladungen enthaltenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="4ac8b-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="4ac8b-153">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-153">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ac8b-154">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4ac8b-155">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="4ac8b-156">Klicken Sie im Bereich **Audiokonferenzen** können Sie die **gebührenpflichtige Telefonnummer** festlegen und, falls zulässig, die **gebührenfreie Telefonnummer**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="4ac8b-157">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-157">Click **Save**.</span></span>
    
<span data-ttu-id="4ac8b-158">Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="4ac8b-159">Auswählen von Audiokonferenzen Brücke</span><span class="sxs-lookup"><span data-stu-id="4ac8b-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="4ac8b-160">**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="4ac8b-161">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-161">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ac8b-162">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4ac8b-163">Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="4ac8b-164">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="4ac8b-165">Dies ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-165">This is enabled by default.</span></span> <span data-ttu-id="4ac8b-166">Wenn Sie diese Option deaktivieren, werden nicht Benutzer, die bereits an der Besprechung standardmäßig benachrichtigt, wenn jemand Beitritt oder die Besprechung verlässt.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="4ac8b-167">Wählen Sie unter **Entry/Exit Ankündigung Typ** **Töne** oder **Namen, oder Rufnummern**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="4ac8b-168">Wenn Sie den **Namen oder die Telefonnummern**auswählen, können Sie auch auswählen, aktivieren oder Deaktivieren von **Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="4ac8b-169">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-169">Click **Save**.</span></span>

    
<span data-ttu-id="4ac8b-170">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-170">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="4ac8b-171">**Festlegen der Länge der PIN für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-171">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="4ac8b-172">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-172">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4ac8b-173">Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-173">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="4ac8b-174">Klicken Sie im Bereich **Einstellungen Bridge** Geben Sie die Anzahl der Ziffern, die Sie für die PIN-Nummer in der Liste der **PIN-Länge** verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-174">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="4ac8b-p109">Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-p109">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="4ac8b-177">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-177">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="4ac8b-178">**Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-178">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="4ac8b-179">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-179">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4ac8b-180">Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-180">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="4ac8b-181">Klicken Sie im Bereich **Bridge-Einstellungen** aktivieren oder deaktivieren **für Benutzer-e-Mails automatisch gesendet, wenn Ändern ihrer Einstellungen für die Audiokonferenz**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-181">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="4ac8b-182">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-182">Click **Save**.</span></span> 
 
    <span data-ttu-id="4ac8b-183">Sie können auch den e-Mail an den Benutzer mit den Einstellungen für Audiokonferenzen senden, indem Sie die Eigenschaften des Benutzers Audiokonferenzen und sollte und auf **Konferenz Informationen in e-Mail-Nachricht senden**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-183">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="4ac8b-184">Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-184">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="4ac8b-185">Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="4ac8b-186">Finden Sie unter, und legen Sie die primären (Standard) und die sekundären Sprachen (alternative) auf eine audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="4ac8b-186">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="4ac8b-187">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-187">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ac8b-188">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-188">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4ac8b-189">Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-189">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="4ac8b-190">Wählen Sie die Sprachen, die Sie unter **Default Language** und **(optional) alternative Sprachen**werden soll.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-190">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="4ac8b-191">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-191">Click **Save**.</span></span>


<span data-ttu-id="4ac8b-192">Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="4ac8b-193">Anzeigen von Einwahlnummern für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="4ac8b-193">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="4ac8b-194">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="4ac8b-194">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ac8b-195">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4ac8b-196">Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="4ac8b-197">Hier können Sie:</span><span class="sxs-lookup"><span data-stu-id="4ac8b-197">Here you can:</span></span>
    
   - <span data-ttu-id="4ac8b-198">Zeigen Sie die Telefonnummern an, die von Office 365 zur Verwendung für Audiokonferenzen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="4ac8b-199">Schauen Sie den Speicherort und die primäre Sprache, die von der automatischen Telefonzentrale Audiokonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4ac8b-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="4ac8b-200">Finden Sie unter [finden Sie eine Liste von Audiokonferenzen Zahlen](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4ac8b-201">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="4ac8b-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4ac8b-p111">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4ac8b-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4ac8b-205">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="4ac8b-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4ac8b-206">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ac8b-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4ac8b-207">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4ac8b-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="4ac8b-208">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4ac8b-208">Related topics</span></span>

[<span data-ttu-id="4ac8b-209">Verwalten der Audiokonferenzeinstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="4ac8b-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


