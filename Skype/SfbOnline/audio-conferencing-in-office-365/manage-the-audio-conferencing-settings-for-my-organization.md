---
title: Verwalten der Einstellungen von Audio Conferencing für meine Organisation in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'Finden Sie unter Skype for Business Online Schritte, um einem Benutzer eine Einwahlkonferenz-Lizenz, eine Konferenz-ID und viele andere Einstellungen für Einwahlkonferenzen zuzuweisen. '
ms.openlocfilehash: d8fc38929e059d0c8fdaf0babec5f8b6fb72856a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255728"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="4f7b2-103">Verwalten der Einstellungen von Audio Conferencing für meine Organisation in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f7b2-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="4f7b2-104">Wenn Sie in Microsoft Teams diese Einstellungen verwalten möchten, sehen Sie[Verwalten der Einstellungen für Audio Conferencing für meine Organisation im Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="4f7b2-105">Möglicherweise ist es einfacher für Sie, alle Einstellungen für Audio Conferencing für Skype for Business und Microsoft Teams an einer einzigen Stelle zu sehen.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="4f7b2-106">Zuweisen einer Lizenz für Audio Conferencing</span><span class="sxs-lookup"><span data-stu-id="4f7b2-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="4f7b2-107">Sie können mithilfe des **Skype for Business Administrationscenters**keine Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-107">You can't assign licenses using the **Skype for Business admin center**, you must use the Office 365 admin center.</span></span> <span data-ttu-id="4f7b2-108">Sie müssen das Office 365 Administrationscenter verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-108">You also can use the Office 365 admin center.</span></span> <span data-ttu-id="4f7b2-109">Sehen Sie[Zuweisen von Lizenzen für Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="4f7b2-110">**So weisen Sie eine Lizenz für einen Benutzer zu**</span><span class="sxs-lookup"><span data-stu-id="4f7b2-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="4f7b2-111">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-112">Navigieren Sie in der linken Navigationsleiste des **Office 365 Admin Center** zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-112">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f7b2-113">Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="4f7b2-114">Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="4f7b2-115">Mit Windows PowerShell können Sie auch mehreren Benutzern Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="4f7b2-116">Anleitungen und PowerShell-Beispielskripts finden Sie unter [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-116">For for instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="4f7b2-117">Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="4f7b2-118">KLicken Sie auf der Seite **Produktlizenzen** auf **Audio Conferencing** und dann klicken Sie auf **Save**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see Skype for Business and Microsoft Teams add-on licensing.</span></span> <span data-ttu-id="4f7b2-119">Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4f7b2-p104">Unter Umständen wird Microsoft nach dem Zuweisen der Lizenz nicht sofort in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall im Office 365 Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="4f7b2-122">Aktivieren oder Deaktivieren der an Benutzer von Audio Conferencing gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="4f7b2-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="4f7b2-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admincenters**</span><span class="sxs-lookup"><span data-stu-id="4f7b2-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="4f7b2-124">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-125">Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="4f7b2-126">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="4f7b2-127">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-127">Click **Save**.</span></span>

    <span data-ttu-id="4f7b2-p105">Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften für den Benutzer, und klicken Sie auf **Konferenzinformationen per E-Mail senden**. Die Konferenzkennung und die Standardtelefonnummer für die Audiokonferenz sind in der Besprechungseinladung enthalten, die PIN jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="4f7b2-130">Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="4f7b2-131">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4f7b2-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="4f7b2-132">Sie können auch Windows PowerShell verwenden und Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4f7b2-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="4f7b2-133">Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="4f7b2-134">Ändern der Kontaktinformationen des Absenders in E-Mails an Benutzer</span><span class="sxs-lookup"><span data-stu-id="4f7b2-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="4f7b2-p106">Sie können die E-Mail, die automatisch an Ihre Benutzer gesendet wird, ändern, unter anderem die E-Mail-Adresse und den Anzeigenamen der Kontaktinformationen des Absenders. Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell und dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) ändern. Um Änderungen an der E-Mail-Adresse vorzunehmen, über die die E-Mail an die Benutzer gesendet wird, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="4f7b2-138">Die E-Mail-Adresse in den Parameter_SendEmailFromAddress_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-138">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="4f7b2-139">Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="4f7b2-140">Legen Sie den Parameter _SendEmailOverride_ auf _True_fest.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="4f7b2-141">Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="4f7b2-142">Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="4f7b2-143">Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="4f7b2-144">Weitere Informationen finden Sie unter [E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Einstellungen für Audio Conferencing ändern](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-144">See [Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="4f7b2-145">Setzen Sie die Meeting-Konferenz-ID zurück</span><span class="sxs-lookup"><span data-stu-id="4f7b2-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="4f7b2-146">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-147">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4f7b2-148">Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center**zu **Audio conferencing** (Audiokonferenz), und klicken Sie im Aktionsbereich unter **Konferenzkennung** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="4f7b2-p107">Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Ja**. Daraufhin wird automatisch eine neue Konferenzkennung generiert und per E-Mail an den Benutzer gesendet, wenn das Senden von E-Mails an Ihre Benutzer aktiviert ist. Standardmäßig ist dies aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="4f7b2-152">Nachdem eine neue Konferenz-ID erstellt wurde, kann die alte Konferenz-ID von Anrufern nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4f7b2-153">Informieren Sie Benutzer von Plänen deren vorhandene Meeting-Einladungen neu zu planen, um sicher zu gehen, dass die neue Konferenz-ID der Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="4f7b2-154">Die Benutzer können das Skype for Business Meeting-Migrationstool für ihre vorhandenen Meetings aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-154">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="4f7b2-155">Informationen zum Herunterladen, installieren und ausführen des Skype for Business Meeting-Updatetools finden Sie unter: [Meeting-Updatetool für Skype for Business und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting-Migrationstool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), und  [Skype for Business Online, Meeting-Migrationstool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-155">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

<span data-ttu-id="4f7b2-156">Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="4f7b2-157">Zurücksetzen der PIN eines Konferenz-Organisators</span><span class="sxs-lookup"><span data-stu-id="4f7b2-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="4f7b2-158">Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen</span><span class="sxs-lookup"><span data-stu-id="4f7b2-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="4f7b2-159">Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es jedoch geschehen, dass ein Benutzer diese nicht verwenden und sie durch eine bestimmte Zahl ersetzen möchte, oder Ihr Benutzer kann sich seine Konferenz-ID nicht merken oder hat sie verloren.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-159">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="4f7b2-160">Sie können das Skype for Business Administrationscenter und Windows PowerShell verwenden, um die Konferenz-ID für solche Benutzer anzuzeigen, zu ändern oder zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="4f7b2-161">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-162">Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="4f7b2-163">Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="4f7b2-164">Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="4f7b2-p110">Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird \*\*\*\*\* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="4f7b2-169">See [Zurücksetzen der PIN für Audio Conferencing](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-169">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="4f7b2-170">Senden einer E-Mail mit den Informationen zum Audio Conferencing an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="4f7b2-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="4f7b2-171">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-172">Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="4f7b2-173">Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, dessen PIN Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="4f7b2-174">Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f7b2-175">Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="4f7b2-176">Siehe[Senden einer E-Mail zu einem Benutzer mit seinen Informationen zum Audio Conferencing](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="4f7b2-177">Festlegen der in Einladungen enthaltenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="4f7b2-177">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="4f7b2-178">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-179">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4f7b2-180">|||UNTRANSLATED_CONTENT_START|||In the left navigation, go to **Audio conferencing** > **Users**.|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="4f7b2-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="4f7b2-181">Wählen Sie den Benutzer, den Sie für Audio Conferencing aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-181">Select the user that you want to enable for dial-in conferencing.</span></span>

4. <span data-ttu-id="4f7b2-182">Im Aktionsbereich können Sie die **gebührenpflichtige Telefonnummer** festlegen und, falls zulässig, die **gebührenfreie Telefonnummer**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="4f7b2-183">Klicken Sie auf **Save**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-183">Click **Save**.</span></span>

<span data-ttu-id="4f7b2-184">|||UNTRANSLATED_CONTENT_START|||See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="4f7b2-184">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md)</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="4f7b2-185">Bridge-Einstellungen für Audio Conferencing auswählen</span><span class="sxs-lookup"><span data-stu-id="4f7b2-185">Setting audio conferencing bridge settings</span></span>

<span data-ttu-id="4f7b2-186">**Legen Sie die Meeting-Erfahrung fest, wenn Anrufer einem Meeting beitreten**</span><span class="sxs-lookup"><span data-stu-id="4f7b2-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="4f7b2-187">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-188">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4f7b2-189">Gehen Sie in der linken Navigationsleiste zu **Skype for Business Admin Center**und dann zu **Audio Conferencing** > **Microsoft Bridge Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="4f7b2-190">Wählen Sie unter **Besprechungsteilnahme** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4f7b2-190">Under **Meeting join experience**, select the following actions:</span></span>

  - <span data-ttu-id="4f7b2-p112">**Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits standardmäßig an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="4f7b2-193">Dies kann auf einer Meeting-zu-Meeting Basis festgelegt werden, wenn ein Benutzer, der eine Skype for Business-App benutzt einem Meeting beitritt und dann die Einstellung **Ankündigen wenn Personen Eintreten oder Verlassen** im Skype Meeting **Optionen** Menü des Meetings ändern.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business client and they modify the **Announce when people enter or leave** setting in the Skype Meeting Options menu of the meeting.</span></span>

  - <span data-ttu-id="4f7b2-p113">**Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="4f7b2-196">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-196">After you make your changes, click **Save**.</span></span>

<span data-ttu-id="4f7b2-197">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-197">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

 <span data-ttu-id="4f7b2-198">**Festlegen der Länge der PIN für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="4f7b2-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="4f7b2-199">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-200">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4f7b2-201">Gehen Sie in der linken Navigationsleiste zu **Skype for Business Admin Center**und dann zu **Audio Conferencing** > **Microsoft Bridge Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="4f7b2-202">Geben Sie unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="4f7b2-p114">Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

<span data-ttu-id="4f7b2-205">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-205">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

 <span data-ttu-id="4f7b2-206">**Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**</span><span class="sxs-lookup"><span data-stu-id="4f7b2-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="4f7b2-207">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-208">Navigieren Sie zu **Office 365 Admin Center** > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing** (Audiokonferenz).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="4f7b2-209">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if any of the audio conferencing configuration changes** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="4f7b2-210">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-210">Click **Save**.</span></span>

    <span data-ttu-id="4f7b2-211">Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften des Benutzers, und klicken Sie auf **Konferenzinformationen per E-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="4f7b2-212">Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="4f7b2-213">Siehe[Senden einer E-Mail zu einem Benutzer mit seinen Informationen zum Audio Conferencing](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="4f7b2-214">Anzeigen und Festlegen der primären (Standard) und sekundären (alternativen) Sprachen auf einer Audio Conferencing Bridge</span><span class="sxs-lookup"><span data-stu-id="4f7b2-214">See and set the primary and secondary languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="4f7b2-215">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-216">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4f7b2-217">Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie dann auf **Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="4f7b2-218">Wählen Sie eine Telefonnummer aus der Liste aus, klicken Sie im Aktionsbereich auf **Sprachen festlegen** und dann auf der Seite **Sprachen festlegen** auf die Liste **Primäre Sprache**. In dieser Liste werden alle unterstützten Sprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="4f7b2-p115">Außerdem können Sie die primären und sekundären Sprachen festlegen, die unterstützt werden, wenn Sie Microsoft als Audiokonferenzanbieter auswählen. Die Reihenfolge, in der Sie Ihre Auswahl in den Dropdownlisten treffen, entspricht der Reihenfolge, in der die Sprachen Anrufern genannt werden.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="4f7b2-221">Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="4f7b2-222">Anzeigen von Einwahlnummern für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="4f7b2-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="4f7b2-223">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-224">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4f7b2-225">|||UNTRANSLATED_CONTENT_START|||In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="4f7b2-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="4f7b2-226">Hier können Sie:</span><span class="sxs-lookup"><span data-stu-id="4f7b2-226">Here you can:</span></span>

  - <span data-ttu-id="4f7b2-227">Die Telefonnummern anzeigen, die von Office 365 zur Verwendung für Audio Conferencing festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

  - <span data-ttu-id="4f7b2-228">Zeigen Sie den Standort sowie die primären und sekundären Sprachen an, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

  - <span data-ttu-id="4f7b2-p117">Wählen Sie die Standardtelefonnummer aus, die Benutzer erhalten, wenn sie für Audiokonferenzen aktiviert werden. Wenn jedoch die Standardtelefonnummer für die Audiokonferenzbrücke geändert wird, ändert sich die Standardtelefonnummer für vorhandene Benutzer nicht.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="4f7b2-231">Sie können zu **Audio Conferencing** > **Benutzer** gehen und die Eigenschaften des Benutzers wählen, um die Standardnummer für einen Benutzer zu ändern, indem Sie eine neue Nummer aus der Liste von Nummern wählen, die in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-231">You can go to **Dial-in conferencing** > **Dial-in users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="4f7b2-232">Siehe [Anzeigen einer Liste mit Telefonnummern für Audio Conferencing](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-232">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md)</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="4f7b2-233">Hier finden Sie eine Liste der Benutzer, die aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="4f7b2-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="4f7b2-234">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4f7b2-235">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4f7b2-236">Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz) und dann zu **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="4f7b2-237">Siehe [Anzeigen einer Liste der Benutzer, die für Einwahlkonferenzen aktiviert sind](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4f7b2-238">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="4f7b2-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="4f7b2-239">Es gibt mehrere Einstellungen, die auf Organisationsebene mithilfe von Windows PowerShell verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-239">There are several settings that you can manage settings at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="4f7b2-240">Dies macht es einfach, Einstellungen für alle Benutzer zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-240">This makes it easy to make these settings and have them apply to all of your users.</span></span>

<span data-ttu-id="4f7b2-241">Weitere Hilfe für jedes Cmdlet, erhalten Sie unter [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="4f7b2-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="4f7b2-242">Hier sind die Einstellungen auf Organisationsebene:</span><span class="sxs-lookup"><span data-stu-id="4f7b2-242">Here are the organization level settings:</span></span>

- <span data-ttu-id="4f7b2-243">**Einstellung Eintrag/Exit Benachrichtigungen** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="4f7b2-244">**Einstellung von Namen-Aufzeichnung** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="4f7b2-245">**Einstellung der PIN-Länge** Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="4f7b2-246">**Einstellung von nur Einwahl-Meetings über ein Telefon** Standard ist _$false_.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="4f7b2-247">**Festlegen, ob E-Mails an Benutzer gesendet werden** Der Standardwert ist _$true_.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="4f7b2-248">**Festlegen, ob E-Mail von einem anderen Konto gesendet wird** Der Standardwert ist _$false_.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="4f7b2-249">**Festlegen der Absenderadresse auf E-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="4f7b2-250">**Festlegen des Anzeigenamens für die E-Mail, die an Benutzer gesendet wird** Der Standardwert ist _$null_.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4f7b2-251">Möchten Sie mehr über Windows PowerShell erfahren</span><span class="sxs-lookup"><span data-stu-id="4f7b2-251">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="4f7b2-p119">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="4f7b2-255">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="4f7b2-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="4f7b2-256">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f7b2-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="4f7b2-p120">Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="4f7b2-259">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f7b2-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="4f7b2-260">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f7b2-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="4f7b2-261">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f7b2-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="4f7b2-p121">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="4f7b2-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="4f7b2-264">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4f7b2-264">Related topics</span></span>

[<span data-ttu-id="4f7b2-265">Verwalten der Einstellungen für Audio Conferencing für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="4f7b2-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


