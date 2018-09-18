---
title: E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, welche Informationen automatisch per E-Mail an Benutzer gesendet werden, wenn sich ihre Dial-in-Konferenzeinstellungen in Microsoft Teams ändern. '
ms.openlocfilehash: f351f7a1107c3f52ddc2c9f60b7cd79feb31388c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890062"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="1addb-103">E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern</span><span class="sxs-lookup"><span data-stu-id="1addb-103">If you're looking for automatic email information in Microsoft Teams, see Emails sent to users when their settings change in Microsoft Teams.</span></span>

<span data-ttu-id="1addb-104">E-Mails werden automatisch an Benutzer gesendet, die [für Audiokonferenzen aktiviert](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) sind und Microsoft als Audiokonferenzanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="1addb-104">Emails will be automatically sent to users who are [Set up Audio Conferencing for Skype for Business and Microsoft Teams](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) using Microsoft as the dial-in conferencing provider.</span></span>
  
<span data-ttu-id="1addb-105">Standardmäßig gibt es vier Arten von E-Mails, die an die für Audiokonferenzen aktivierten Benutzer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1addb-105">By default, there are four types of email that will be sent to your users who are enabled for dial-in conferencing.</span></span> <span data-ttu-id="1addb-106">Wenn Sie die Anzahl der an die Benutzer gesendeten E-Mails begrenzen möchten, können Sie die E-Mails deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1addb-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="1addb-107">Audiokonferenzen in Office 365 sendet in den folgenden Fällen E-Mails an Benutzer:</span><span class="sxs-lookup"><span data-stu-id="1addb-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="1addb-108">**Den Benutzern wird eine Lizenz für Audiokonferenzen zugewiesen, oder Sie ändern den Audiokonferenzanbieter in Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="1addb-108">**A Skype for Business PSTN Conferencing license is assigned to them or when you are changing the dial-in conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="1addb-109">Diese E-Mail enthält die Konferenzkennung, die standardmäßige Konferenztelefonnummer für die Besprechungen, die Audiokonferenz-PIN für den Benutzer sowie Anweisungen und den Link zum Besprechungsaktualisierungstool für Skype for Business Online, das zum Aktualisieren vorhandener Besprechungen für den Benutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1addb-109">This email includes the conference ID, the default conference phone number for the meetings, the dial-in conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="1addb-110">Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Zuweisen von Microsoft als Audiokonferenzanbieter](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="1addb-110">See [Assign Skype for Business licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1addb-111">Wenn Ihre Organisation für dynamische Konferenzkennungen aktiviert wurde, weisen alle von einem Benutzer geplanten Besprechungen eindeutige Konferenzkennungen auf.</span><span class="sxs-lookup"><span data-stu-id="1addb-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="1addb-112">Sie können [dynamische Audiokonferenzkennungen in Ihrer Organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user) einrichten.</span><span class="sxs-lookup"><span data-stu-id="1addb-112">You can set up [Using dial-in conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 
  
    <span data-ttu-id="1addb-113">Hier ist ein Beispiel für diese E-Mail:</span><span class="sxs-lookup"><span data-stu-id="1addb-113">Here is an example of this email:</span></span>
    
     ![Bestätigung der Skype for Business-Lizenz](media/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="1addb-115">Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="1addb-115">You can find out more about Skype for Business licensing by seeing [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
- <span data-ttu-id="1addb-116">**Die Konferenzkennung oder die standardmäßige Konferenztelefonnummer eines Benutzers wird geändert.**</span><span class="sxs-lookup"><span data-stu-id="1addb-116">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="1addb-117">Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1addb-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="1addb-118">Sie enthält jedoch nicht die Audiokonferenz-PIN des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1addb-118">But this email doesn't include the user's dial-in conferencing PIN.</span></span> <span data-ttu-id="1addb-119">Siehe [Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1addb-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
    <span data-ttu-id="1addb-120">Hier ist ein Beispiel für diese E-Mail:</span><span class="sxs-lookup"><span data-stu-id="1addb-120">Here is an example of this email:</span></span>
    
     ![Die Dial-in-Konferenzinformationen wurden geändert.](media/audio-conferencing-info-change.png)
  
- <span data-ttu-id="1addb-122">**Die Audiokonferenz-PIN eines Benutzers wird zurückgesetzt.**</span><span class="sxs-lookup"><span data-stu-id="1addb-122">**The dial-in conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="1addb-123">Diese E-Mail enthält die Audiokonferenz-PIN des Organisators, die vorhandene Konferenzkennung und die standardmäßige Konferenztelefonnummer für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1addb-123">This email contains the organizer's dial-in conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="1addb-124">Siehe [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1addb-124">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
  
    <span data-ttu-id="1addb-125">Hier ist ein Beispiel für diese E-Mail:</span><span class="sxs-lookup"><span data-stu-id="1addb-125">Here is an example of this email:</span></span>
    
     ![Die PIN für Dial-in-Konferenzen wurde geändert.](media/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="1addb-127">**Die Lizenz eines Benutzers wird entfernt, oder der Audiokonferenzanbieter wird von Microsoft in einen anderen Anbieter oder in „Keiner“ geändert.**</span><span class="sxs-lookup"><span data-stu-id="1addb-127">**A user's license is removed or when their dial-in conferencing provider changes from Microsoft to other provider or None**</span></span>
    
    <span data-ttu-id="1addb-128">Dies geschieht, wenn die Lizenz für **Audiokonferenzen** von einem Benutzer entfernt wird, wenn der Audiokonferenzanbieter eines Benutzers von Microsoft in einen Drittanbieter für Audiokonferenzen geändert wird oder wenn der Anbieter auf **Keiner** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1addb-128">This happens when the **Skype for Business PSTN Conferencing** license is removed from a user or when changing the dial-in conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**. This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove dial-in conferencing specific information, such as the default conference phone number or conference ID.</span></span> <span data-ttu-id="1addb-129">Diese E-Mail enthält Anweisungen und Informationen für den Benutzer, damit er mit dem Besprechungsaktualisierungstool für Skype for Business Online spezifische Informationen für Audiokonferenzen wie beispielsweise die standardmäßige Konferenztelefonnummer oder die Konferenzkennung entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="1addb-129">This happens when the Skype for Business PSTN Conferencing license is removed from a user or when changing the dial-in conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to None. This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove dial-in conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="1addb-130">Siehe [Zuweisen von Lizenzen zu Benutzern in Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="1addb-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="1addb-131">Hier ist ein Beispiel für diese E-Mail:</span><span class="sxs-lookup"><span data-stu-id="1addb-131">Here is an example of this email:</span></span>
    
     !["Dial-In-Konferenzen" ist deaktiviert.](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="1addb-133">Vornehmen von Änderungen an den gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="1addb-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="1addb-134">Sie können die E-Mail-Nachricht ändern, die automatisch an Benutzer gesendet wird. Zu den zu ändernden Optionen gehören die E-Mail-Adresse und der Anzeigename, der in der Kontaktinformation *From* enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1addb-134">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="1addb-135">Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="1addb-135">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the Set-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="1addb-136">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="1addb-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="1addb-137">Wie gehen Sie vor, wenn keine E-Mails an die Benutzer gesendet werden sollen?</span><span class="sxs-lookup"><span data-stu-id="1addb-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="1addb-138">Wenn Sie das Senden von E-Mails an die Benutzer deaktivieren, werden auch dann keine E-Mails gesendet, wenn Benutzern eine Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1addb-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="1addb-139">In diesem Fall werden die Konferenzkennung, die standardmäßige Konferenztelefonnummer und vor allem die Audiokonferenz-PIN nicht an die Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="1addb-139">If this is the case, the conference ID, default conferencing phone number and more importantly, their dial-in conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="1addb-140">Dann müssen Sie die Benutzer informieren, indem Sie ihnen eine separate E-Mail senden oder sie anrufen.</span><span class="sxs-lookup"><span data-stu-id="1addb-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="1addb-141">Standardmäßig werden E-Mails an die Benutzer gesendet. Wenn Sie nicht möchten, dass die Benutzer E-Mails für Audiokonferenzen erhalten, können Sie Microsoft Teams oder Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="1addb-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for dial-in conferencing use can use the Skype for Business admin center or Windows PowerShell.</span></span> 

<span data-ttu-id="1addb-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="1addb-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="1addb-143">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="1addb-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="1addb-144">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="1addb-144">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="1addb-145">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.</span><span class="sxs-lookup"><span data-stu-id="1addb-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="1addb-146">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1addb-146">Click **Save**.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="1addb-147">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1addb-147">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="1addb-148">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="1addb-148">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1addb-149">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="1addb-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="1addb-150">Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="1addb-150">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the Set-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> 

<span data-ttu-id="1addb-p109">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1addb-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1addb-154">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="1addb-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1addb-155">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1addb-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="1addb-156">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="1addb-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
  
## <a name="related-topics"></a><span data-ttu-id="1addb-157">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1addb-157">Related topics</span></span>

[<span data-ttu-id="1addb-158">Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="1addb-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[<span data-ttu-id="1addb-159">Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="1addb-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
