---
title: Anzeigen, ändern und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen ist
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie einem Benutzer in Skype for Business Online eine Konferenz-ID zuweisen und was die Konferenz-IDs-Parameter sein sollten. '
ms.openlocfilehash: 65a27315898ec0673d68842e7d5249cbad2d7298
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793004"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="66466-103">Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="66466-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="66466-104">Informationen zu Benutzer Konferenz-IDs in Microsoft Teams finden Sie unter [anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams zugewiesen](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)ist.</span><span class="sxs-lookup"><span data-stu-id="66466-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="66466-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="66466-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="66466-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="66466-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="66466-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="66466-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="66466-112">Anzeigen und Zurücksetzen der Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="66466-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="66466-113">So zeigen Sie die Konferenz-ID an</span><span class="sxs-lookup"><span data-stu-id="66466-113">To view the conference ID</span></span>

<span data-ttu-id="66466-114">![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="66466-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="66466-115">Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="66466-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="66466-116">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="66466-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="66466-117">Wechseln Sie zum Admin Center #a0 **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="66466-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="66466-118">Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer aus, der die Konferenz-ID benötigt.</span><span class="sxs-lookup"><span data-stu-id="66466-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="66466-119">Sehen Sie auf der Aktions-Seie unter **Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="66466-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="66466-120">Sie können alle Konferenz Informationen an den Benutzer in einer e-Mail senden, die die Konferenz-ID und die audiorufnummern enthält, indem Sie auf den Link **Konferenz Informationen per e-Mail senden** klicken, nachdem Sie den Benutzer auf der Seite **Benutzer** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="66466-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="66466-121">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="66466-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="66466-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="66466-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="66466-124">So setzen Sie die Konferenz-ID zurück</span><span class="sxs-lookup"><span data-stu-id="66466-124">To reset the conference ID</span></span>

<span data-ttu-id="66466-125">Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="66466-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="66466-126">![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="66466-126">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="66466-127">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="66466-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="66466-128">Wechseln Sie zum Admin Center #a0 **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="66466-128">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="66466-129">Klicken Sie **im Skype for Business Admin Center**> **-Audiokonferenz** > -**Benutzer**im Bereich "Aktion" unter **Konferenz-ID**auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="66466-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="66466-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="66466-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="66466-132">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="66466-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="66466-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="66466-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="66466-135">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="66466-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="66466-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="66466-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="66466-140">Weitere Informationen zum Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="66466-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="66466-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span><span class="sxs-lookup"><span data-stu-id="66466-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="66466-143">Die Konferenz-ID für alle Audiokonferenz-Benutzer ist standardmäßig 7 Ziffern, und die Anzahl der Ziffern kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="66466-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="66466-144">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="66466-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="66466-p109">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="66466-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="66466-148">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="66466-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="66466-149">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="66466-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="66466-150">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="66466-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="66466-151">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="66466-151">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="66466-152">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66466-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="66466-153">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="66466-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="66466-154">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="66466-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="66466-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="66466-155">Related topics</span></span>

[<span data-ttu-id="66466-156">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="66466-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

