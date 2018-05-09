---
title: Anzeigen, Bearbeiten und Zurücksetzen einer Konferenz-ID, die einem Nutzer zugewiesen wurde
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 73c5d3cc95b7967cd9d6eaae83a14e19143e431b
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="8c243-103">Anzeigen und eine Konferenz-ID, die einem Benutzer zugewiesenen zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="8c243-103">View and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="8c243-104">Eine Konferenz-ID wird automatisch auf einen Skype für Business oder Microsoft-Teams, Benutzer zugewiesen, für Audiokonferenzen in Office 365 einrichten und Verwenden von Microsoft als Anbieter von Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="8c243-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="8c243-105">Die Konferenz-ID zugewiesen wird in der besprechungseinladung gesendet, wenn die Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="8c243-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="8c243-106">Jede Besprechung, die ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen</span><span class="sxs-lookup"><span data-stu-id="8c243-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="8c243-107">Zwar eine Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten, und es eine bestimmte Anzahl festgelegt werden soll, oder wenn Ihre Benutzer können nicht merken oder ihre Konferenz-ID. verloren haben</span><span class="sxs-lookup"><span data-stu-id="8c243-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="8c243-108">Sie können die **Skype für Business Administrationscenter** und Windows PowerShell verwenden, anzeigen, ändern und Zurücksetzen ihrer Konferenz-ID.</span><span class="sxs-lookup"><span data-stu-id="8c243-108">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="8c243-109">Dem Benutzer mit der Konferenz-ID und die Telefonnummern der Standard-Audiokonferenzen wird eine e-Mail gesendet werden, oder wenn Sie die Konferenz-ID zurücksetzen eine e-Mail gesendet wird, die die Konferenz-ID, aber nicht mit einer PIN enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="8c243-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="8c243-110">Weitere Informationen zum Zurücksetzen einer Konferenzorganisator PIN, [Wechseln Sie hier](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="8c243-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span> 
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="8c243-111">Anzeigen und Zurücksetzen der Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="8c243-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="8c243-112">So zeigen Sie die Konferenz-ID an.</span><span class="sxs-lookup"><span data-stu-id="8c243-112">To view the conference ID</span></span>

<span data-ttu-id="8c243-113">![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="8c243-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="8c243-114">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="8c243-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="8c243-115">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8c243-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="8c243-116">Suchen Sie unter **Audiokonferenzen**klicken Sie unter **Konferenz-ID**ein.</span><span class="sxs-lookup"><span data-stu-id="8c243-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8c243-117">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und audio Telefonnummern enthält durch Klicken auf den Link **Konferenz Informationen in e-Mail-Nachricht senden** .</span><span class="sxs-lookup"><span data-stu-id="8c243-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="8c243-118">Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c243-118">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="8c243-119">Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="8c243-119">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


<span data-ttu-id="8c243-120">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="8c243-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="8c243-121">Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="8c243-121">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="8c243-122">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="8c243-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8c243-123">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="8c243-123">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8c243-124">In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, den Benutzer auswählen, muss die Konferenz-ID.</span><span class="sxs-lookup"><span data-stu-id="8c243-124">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="8c243-125">Suchen Sie auf der Seite Aktion unter **Konferenz-ID**ein.</span><span class="sxs-lookup"><span data-stu-id="8c243-125">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8c243-126">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und audio Telefonnummern durch Klicken auf den Link **Konferenz Informationen per e-Mail senden** , nachdem Sie den Benutzer auf der Seite **Benutzer** auswählen enthält.</span><span class="sxs-lookup"><span data-stu-id="8c243-126">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="8c243-127">Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c243-127">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="8c243-128">Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="8c243-128">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="8c243-129">So setzen Sie die Konferenz-ID zurück.</span><span class="sxs-lookup"><span data-stu-id="8c243-129">To reset the conference ID</span></span>

<span data-ttu-id="8c243-130">Sie können eine Konferenz-ID für einen Benutzer zurücksetzen "If"; beispielsweise, wenn sie es vergessen.</span><span class="sxs-lookup"><span data-stu-id="8c243-130">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
<span data-ttu-id="8c243-131">![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="8c243-131">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="8c243-132">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="8c243-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="8c243-133">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8c243-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="8c243-134">Klicken Sie unter **Audiokonferenzen**auf **Konferenz-ID zurückgesetzt**.</span><span class="sxs-lookup"><span data-stu-id="8c243-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="8c243-135">Klicken Sie auf **Zurücksetzen**, klicken Sie im Fenster **Konferenz-ID zurückgesetzt** .</span><span class="sxs-lookup"><span data-stu-id="8c243-135">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="8c243-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="8c243-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="8c243-137">Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="8c243-137">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="8c243-138">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="8c243-138">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

<span data-ttu-id="8c243-139">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="8c243-139">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="8c243-140">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="8c243-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8c243-141">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="8c243-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8c243-142">In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, klicken Sie im Aktionsbereich unter **Konferenz-ID**, klicken Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="8c243-142">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="8c243-143">In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8c243-143">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="8c243-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="8c243-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="8c243-145">Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="8c243-145">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="8c243-146">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="8c243-146">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="8c243-147">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="8c243-147">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="8c243-148">Nachdem eine neue Konferenz-ID erstellt wird oder eine zurückgesetzt wird, kann nicht die alte Konferenz-ID BSSID verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c243-148">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="8c243-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="8c243-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="8c243-150">Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="8c243-150">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="8c243-151">Informationen zum Herunterladen, installieren und Ausführen des Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)und [Skype für Online Business Besprechung Migration Tool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="8c243-151">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="8c243-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8c243-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="8c243-153">Die Konferenz-ID muss die Länge in Ziffern legen Sie für die audiokonferenzbrücke erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8c243-153">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="8c243-154">Sie können nicht alphabetische oder Sonderzeichen im Konferenz-IDs verwenden. nur Zahlen können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c243-154">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="8c243-155">Die Konferenz-ID für alle Ihre audiokonferenzbenutzer werden standardmäßig 7 Ziffern, und die Anzahl der Nachkommastellen kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8c243-155">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8c243-156">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="8c243-156">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8c243-p112">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8c243-p112">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8c243-160">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8c243-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8c243-161">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="8c243-161">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="8c243-p113">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8c243-p113">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="8c243-164">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c243-164">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="8c243-165">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8c243-165">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8c243-166">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8c243-166">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="8c243-167">See Also</span><span class="sxs-lookup"><span data-stu-id="8c243-167">Related topics</span></span>

[<span data-ttu-id="8c243-168">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c243-168">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

