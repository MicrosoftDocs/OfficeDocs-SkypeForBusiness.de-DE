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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, welche Informationen automatisch per E-Mail an Benutzer gesendet werden, wenn ihre Einstellungen für Einwahlkonferenzen in Skype for Business Online geändert werden. '
ms.openlocfilehash: 3f37ca23a33131f66b9a2251087ac24ed9220c91
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854651"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="9b79c-103">An Benutzer gesendete E-Mails, wenn ihre Einstellungen in Skype for Business Online geändert werden</span><span class="sxs-lookup"><span data-stu-id="9b79c-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="9b79c-104">Wenn Sie in Microsoft-Teams nach automatischen E-Mail-Informationen suchen, erhalten Sie weitere Informationen unter [Benutzer gesendete E-Mails, wenn ihre Einstellungen in Microsoft-Teams geändert werden](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="9b79c-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="9b79c-105">E-Mails werden automatisch an Benutzer gesendet, die [für die Audiokonferenz aktiviert](set-up-audio-conferencing.md) und Microsoft als Anbieter von Audiokonferenzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b79c-105">Emails will be automatically sent to users who are [Set up Audio Conferencing for Skype for Business and Microsoft Teams](set-up-audio-conferencing.md) using Microsoft as the dial-in conferencing provider.</span></span>
  
<span data-ttu-id="9b79c-106">Standardmäßig gibt es vier Arten von E-Mails, die an Benutzer gesendet werden, die für die Audiokonferenz aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9b79c-106">By default, there are four types of email that will be sent to your users who are enabled for dial-in conferencing.</span></span> <span data-ttu-id="9b79c-107">Wenn Sie die Anzahl von E-Mails, die an die Benutzer gesendet werden, einschränken möchten, können Sie diese Einstellung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9b79c-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="9b79c-108">Audiokonferenzen in Office 365 sendet in den folgenden Fällen E-Mails an Benutzer:</span><span class="sxs-lookup"><span data-stu-id="9b79c-108">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="9b79c-109">**Den Benutzern wird eine Lizenz für Audiokonferenzen zugewiesen oder ein Benutzer wechselt zu Microsoft als Audiokonferenzanbieter.**</span><span class="sxs-lookup"><span data-stu-id="9b79c-109">**A Skype for Business PSTN Conferencing license is assigned to them or when you are changing the dial-in conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="9b79c-110">Diese E-Mail enthält die Konferenz-ID, die Standardkonferenz für Besprechungen, die PIN für die Audiokonferenz für den Benutzer sowie Anweisungen und den Link zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b79c-110">This email includes the conference ID, the default conference phone number for the meetings, the dial-in conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="9b79c-111">Siehe [Zuweisen von Skype for Business-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Zuweisen von Microsoft als Audiokonferenzanbieter](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="9b79c-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b79c-112">Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf.</span><span class="sxs-lookup"><span data-stu-id="9b79c-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="9b79c-113">Sie können [dynamische IDs für Audiokonferenzen in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten.</span><span class="sxs-lookup"><span data-stu-id="9b79c-113">You can set up [Using dial-in conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="9b79c-114">So kann diese E-Mail aussehen:</span><span class="sxs-lookup"><span data-stu-id="9b79c-114">Here is an example of this email:</span></span>
    
     ![Skype for Business – Lizenz überprüfen](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="9b79c-116">Weitere Informationen zur Skype for Business-Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="9b79c-116">You can find out more about Skype for Business licensing by seeing [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="9b79c-117">**Sich die Konferenz-ID oder die Standardtelefonnummer eines Benutzers ändert.**</span><span class="sxs-lookup"><span data-stu-id="9b79c-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="9b79c-118">Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b79c-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="9b79c-119">Die E-Mail enthält jedoch nicht die PIN des Benutzers für Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="9b79c-119">But this email doesn't include the user's dial-in conferencing PIN.</span></span> <span data-ttu-id="9b79c-120">Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9b79c-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b79c-121">Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf.</span><span class="sxs-lookup"><span data-stu-id="9b79c-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="9b79c-122">Sie können [dynamische IDs für Audiokonferenzen in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten.</span><span class="sxs-lookup"><span data-stu-id="9b79c-122">You can set up [Using dial-in conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="9b79c-123">So kann diese E-Mail aussehen:</span><span class="sxs-lookup"><span data-stu-id="9b79c-123">Here is an example of this email:</span></span>
    
     ![Die Informationen für Dial-In-Konferenzen wurden geändert.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="9b79c-125">**Die Audiokonferenz-PIN eines Benutzers wurde zurückgesetzt.**</span><span class="sxs-lookup"><span data-stu-id="9b79c-125">**The dial-in conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="9b79c-126">Diese E-Mail enthält die Audiokonferenz-PIN des Organisators, die vorhandene Konferenz-ID und die Standardkonferenznummer für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9b79c-126">This email contains the organizer's dial-in conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="9b79c-127">Weitere Informationen finden Sie unter [Zurücksetzen Audiokonferenz-PIN](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="9b79c-127">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b79c-128">Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf.</span><span class="sxs-lookup"><span data-stu-id="9b79c-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="9b79c-129">Sie können [dynamische IDs für Audiokonferenzen in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md)einrichten.</span><span class="sxs-lookup"><span data-stu-id="9b79c-129">You can set up [Using dial-in conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="9b79c-130">So kann diese E-Mail aussehen:</span><span class="sxs-lookup"><span data-stu-id="9b79c-130">Here is an example of this email:</span></span>
    
     ![Die PIN für die Dial-In-Konferenz wurde geändert.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="9b79c-132">**Entweder, wenn die Lizenz eines Benutzers entfernt wird, oder wenn statt Microsoft ein anderer Audiokonferenzanbieter oder gar kein Anbieter verwendet wird.**</span><span class="sxs-lookup"><span data-stu-id="9b79c-132">**A user's license is removed or when their dial-in conferencing provider changes from Microsoft to other provider or None**</span></span>
    
    <span data-ttu-id="9b79c-133">Dies geschieht, wenn die **Audiokonferenz** -Lizenz eines Benutzers entfernt wird, oder wenn der Audiokonferenzanbieter eines Benutzers nicht mehr Microsoft, sondern ein Drittanbieter für Audiokonferenzen ist oder wenn für den Anbieter die Option **Ohne** festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="9b79c-133">This happens when the **Skype for Business PSTN Conferencing** license is removed from a user or when changing the dial-in conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**. This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove dial-in conferencing specific information, such as the default conference phone number or conference ID.</span></span> <span data-ttu-id="9b79c-134">Diese E-Mail enthält Anweisungen und Informationen für den Benutzer, um mithilfe des Skype for Business Online Meeting Update Tools spezifische Informationen für Audiokonferenzen, wie die Standardkonferenznummer oder die Konferenz-ID, zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9b79c-134">This happens when the Skype for Business PSTN Conferencing license is removed from a user or when changing the dial-in conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to None. This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove dial-in conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="9b79c-135">Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="9b79c-135">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="9b79c-136">So kann diese E-Mail aussehen:</span><span class="sxs-lookup"><span data-stu-id="9b79c-136">Here is an example of this email:</span></span>
    
     !["Dial-In-Konferenzen" ist deaktiviert.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="9b79c-138">Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden</span><span class="sxs-lookup"><span data-stu-id="9b79c-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="9b79c-139">Sie können die E-Mail-Nachricht ändern, die automatisch an Benutzer gesendet wird. Zu den zu ändernden Optionen gehören die E-Mail-Adresse und der Anzeigename, der in der Kontaktinformation *From* enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="9b79c-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="9b79c-140">Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell und des Cmdlets [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) ändern.</span><span class="sxs-lookup"><span data-stu-id="9b79c-140">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="9b79c-141">So ändern Sie die E-Mail-Adresse, die als Absender von E-Mail-Nachrichten an Benutzer verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="9b79c-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="9b79c-142">Die E-Mail-Adresse in den Parameter  _SendEmailFromAddress_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="9b79c-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="9b79c-143">Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="9b79c-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="9b79c-144">Legen Sie den Parameter _SendEmailOverride_ auf _True_fest.</span><span class="sxs-lookup"><span data-stu-id="9b79c-144">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="9b79c-145">Sie können Änderungen an der E-Mail vornehmen, die an Benutzer gesendet wird. Zum Beispiel können Sie die Absender-E-Mail-Adresse und den Anzeigenamen der E-Mail ändern. Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9b79c-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="9b79c-146">Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihrer Umgebung für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b79c-146">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="9b79c-147">Wenn Sie die Kontaktinformationen *From* außer Kraft setzen möchten, sollten Sie sicherstellen, dass die E-Mails ordnungsgemäß an Benutzer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b79c-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="9b79c-148">Hierzu können Sie dies mit einem Benutzer in Ihrer Organisation testen.</span><span class="sxs-lookup"><span data-stu-id="9b79c-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="9b79c-149">Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.</span><span class="sxs-lookup"><span data-stu-id="9b79c-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="9b79c-150">Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?</span><span class="sxs-lookup"><span data-stu-id="9b79c-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="9b79c-151">Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9b79c-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="9b79c-152">In diesem Fall werden die Konferenz-ID, die Audiokonferenznummer und, noch wichtiger, auch die Audiokonferenz-PIN nicht an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="9b79c-152">If this is the case, the conference ID, default conferencing phone number and more importantly, their dial-in conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="9b79c-153">Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.</span><span class="sxs-lookup"><span data-stu-id="9b79c-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="9b79c-154">Standardmäßig werden E-Mails an Ihre Benutzer gesendet. Wenn Sie nicht möchten, dass Ihre Benutzer E-Mails für Audiokonferenzen erhalten, können Sie das Skype for Business Admin Center oder Windows PowerShell nutzen.</span><span class="sxs-lookup"><span data-stu-id="9b79c-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for dial-in conferencing use can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="9b79c-155">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="9b79c-155">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="9b79c-156">Gehen Sie in der linken Navigationsleiste auf **Skype for Business Admin Center** und dann zu **Audiokonferenzen** > **Einstellungen für Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="9b79c-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="9b79c-157">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen für Microsoft Bridge** die Option **Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden**.</span><span class="sxs-lookup"><span data-stu-id="9b79c-157">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="9b79c-158">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9b79c-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="9b79c-159">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9b79c-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="9b79c-160">Führen Sie das Folgende aus, um das Senden von E-Mails an alle Benutzer zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="9b79c-160">Run the following to disable sending all of your users email:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

<span data-ttu-id="9b79c-161">Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.</span><span class="sxs-lookup"><span data-stu-id="9b79c-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="9b79c-162">Was sollten Sie sonst über diese E-Mails wissen?</span><span class="sxs-lookup"><span data-stu-id="9b79c-162">What else should you know about this email?</span></span>

- <span data-ttu-id="9b79c-163">Weitere Informationen zur Aktivierung und Deaktivierung automatisch verschickter E-Mails an Ihre Benutzer finden Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="9b79c-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="9b79c-164">Es kann vorkommen, dass Benutzer ihre Audioinformationen verlieren. Sie müssen dann die gesamten Audioinformationen an den Benutzer senden können.</span><span class="sxs-lookup"><span data-stu-id="9b79c-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="9b79c-165">Dazu können Sie im Skype for Business Admin Center unter den Audiokonferenzeigenschaften für einen Benutzer auf **Konferenzinformationen per E-Mail senden** klicken.</span><span class="sxs-lookup"><span data-stu-id="9b79c-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the dial-in properties for a user.</span></span> <span data-ttu-id="9b79c-166">Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="9b79c-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="9b79c-167">Diese Informationen enthalten jedoch nicht die Audiokonferenz-PIN.</span><span class="sxs-lookup"><span data-stu-id="9b79c-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="9b79c-168">Hier ist ein Beispiel für eine E-Mail, die an die Benutzer gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="9b79c-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![E-Mail zu einer Dial-In-Konferenz](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9b79c-170">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="9b79c-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9b79c-171">Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell und des Cmdlets [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) ändern.</span><span class="sxs-lookup"><span data-stu-id="9b79c-171">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="9b79c-p113">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9b79c-p113">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9b79c-175">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="9b79c-175">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9b79c-176">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b79c-176">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="9b79c-p114">Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="9b79c-p114">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="9b79c-179">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9b79c-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9b79c-180">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9b79c-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9b79c-181">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9b79c-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="9b79c-p115">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="9b79c-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9b79c-184">See Also</span><span class="sxs-lookup"><span data-stu-id="9b79c-184">Related topics</span></span>

[<span data-ttu-id="9b79c-185">Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern</span><span class="sxs-lookup"><span data-stu-id="9b79c-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="9b79c-186">Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="9b79c-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
