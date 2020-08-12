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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie einem Benutzer in Skype for Business Online eine Konferenz-ID zuweisen und was die Konferenz-IDs-Parameter sein sollten. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643605"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="1975c-103">Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="1975c-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="1975c-104">Informationen zu Benutzer Konferenz-IDs in Microsoft Teams finden Sie unter [anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams zugewiesen](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)ist.</span><span class="sxs-lookup"><span data-stu-id="1975c-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="1975c-p101">Eine Konferenz-ID wird einem Skype for Business-Benutzer automatisch zugewiesen, wenn Sie in Microsoft 365 oder Office 365 für Audiokonferenzen eingerichtet sind, und Microsoft als Anbieter von Audiokonferenzen verwenden. Die zugewiesene Konferenz-ID wird in der Besprechungseinladung gesendet, wenn die Besprechung geplant ist. Jeder Besprechung, die ein Benutzer plant, erhält eine eindeutige Konferenz-ID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1975c-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="1975c-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="1975c-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="1975c-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="1975c-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="1975c-112">Anzeigen und Zurücksetzen der Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="1975c-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="1975c-113">So zeigen Sie die Konferenz-ID an</span><span class="sxs-lookup"><span data-stu-id="1975c-113">To view the conference ID</span></span>

<span data-ttu-id="1975c-114">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="1975c-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="1975c-115">Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="1975c-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="1975c-116">Mit Ihrem Firmen-oder Schulkonto anmelden</span><span class="sxs-lookup"><span data-stu-id="1975c-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="1975c-117">Wechseln Sie zum Admin Center > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1975c-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="1975c-118">Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer aus, der die Konferenz-ID benötigt.</span><span class="sxs-lookup"><span data-stu-id="1975c-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="1975c-119">Sehen Sie auf der Aktions-Seie unter **Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="1975c-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1975c-120">Sie können alle Konferenz Informationen an den Benutzer in einer e-Mail senden, die die Konferenz-ID und die audiorufnummern enthält, indem Sie auf den Link **Konferenz Informationen per e-Mail senden** klicken, nachdem Sie den Benutzer auf der Seite **Benutzer** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="1975c-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="1975c-121">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1975c-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="1975c-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="1975c-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="1975c-124">Weitere Informationen zum Cmdlet finden Sie unter [Get-csonlinedialinconferencinguser zeigt](https://go.microsoft.com/fwlink/?LinkId=617693 ) .</span><span class="sxs-lookup"><span data-stu-id="1975c-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="1975c-125">So setzen Sie die Konferenz-ID zurück</span><span class="sxs-lookup"><span data-stu-id="1975c-125">To reset the conference ID</span></span>

<span data-ttu-id="1975c-126">Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="1975c-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="1975c-127">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="1975c-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="1975c-128">Mit Ihrem Firmen-oder Schulkonto anmelden</span><span class="sxs-lookup"><span data-stu-id="1975c-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="1975c-129">Wechseln Sie zum Admin Center > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1975c-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="1975c-130">Klicken Sie im **Skype for Business Admin Center** >  **-Audiokonferenz-**  >  **Benutzer**im Bereich "Aktion" unter **Konferenz-ID**auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="1975c-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="1975c-131">Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="1975c-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="1975c-132">Eine Konferenz-ID wird automatisch erstellt und eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="1975c-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="1975c-133">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1975c-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="1975c-134">Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="1975c-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="1975c-135">Führen Sie dazu die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="1975c-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="1975c-136">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="1975c-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="1975c-137">Nach dem Erstellen einer neuen Konferenz-ID oder eines Zurücksetzens wird die alte Konferenz-ID nicht von den Anrufern verwendet.</span><span class="sxs-lookup"><span data-stu-id="1975c-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="1975c-138">Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1975c-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="1975c-139">Die Benutzer können das Skype for Business-Besprechungs Migrations Tool verwenden, um Ihre vorhandenen Besprechungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1975c-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="1975c-140">Informationen zum herunterladen, installieren und Ausführen des Tools finden Sie unter: [Update Tool für Besprechungen für Skype for Business und lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)und [Skype for Business Online, Meeting Migration Tool (32-Bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="1975c-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="1975c-141">Weitere Informationen zum Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="1975c-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="1975c-142">Die Konferenz-ID muss die für die Audiokonferenz-Brücke eingestellte Länge in Ziffern erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1975c-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="1975c-143">In Konferenz-IDs können keine alphabetischen oder Sonderzeichen verwendet werden. Es können nur Zahlen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1975c-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="1975c-144">Die Konferenz-ID für alle Audiokonferenz-Benutzer ist standardmäßig 9 Ziffern, und die Anzahl der Ziffern kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1975c-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1975c-145">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="1975c-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1975c-146">Bei Windows PowerShell geht es um die Verwaltung von Benutzern und um die Benutzer, die zugelassen oder nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="1975c-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1975c-147">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1975c-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1975c-148">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1975c-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="1975c-149">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1975c-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="1975c-150">Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1975c-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="1975c-151">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="1975c-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1975c-152">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1975c-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="1975c-153">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1975c-153">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="1975c-154">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1975c-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="1975c-155">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1975c-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="1975c-156">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1975c-156">Related topics</span></span>

[<span data-ttu-id="1975c-157">Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="1975c-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

