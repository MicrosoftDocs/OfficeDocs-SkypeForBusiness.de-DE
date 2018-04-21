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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 42aa17866c286c5d57fa3cd4962ecf6a16e2438a
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="e5282-103">Anzeigen, Bearbeiten und Zurücksetzen einer Konferenz-ID, die einem Nutzer zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="e5282-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="e5282-104">Eine Konferenz-ID wird automatisch auf einen Skype für Business oder Microsoft-Teams, Benutzer zugewiesen, für Audiokonferenzen in Office 365 einrichten und Verwenden von Microsoft als Anbieter von Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="e5282-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="e5282-105">Die Konferenz-ID zugewiesen werden kann, statische oder dynamische und wird in der besprechungseinladung gesendet, wenn die Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="e5282-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="e5282-106">Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="e5282-106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="e5282-107">Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen</span><span class="sxs-lookup"><span data-stu-id="e5282-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="e5282-108">Wenn Sie zuweisen dynamische statt statische Konferenz-IDs, [Wechseln Sie hier möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e5282-108">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="e5282-109">Zwar eine statische Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten, und es eine bestimmte Anzahl festgelegt werden soll, oder wenn Ihre Benutzer können nicht merken oder ihre Konferenz-ID. verloren haben</span><span class="sxs-lookup"><span data-stu-id="e5282-109">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="e5282-110">Sie können die **Skype für Business Administrationscenter** und Windows PowerShell verwenden, anzeigen, ändern und Zurücksetzen ihrer Konferenz-ID.</span><span class="sxs-lookup"><span data-stu-id="e5282-110">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="e5282-111">Dem Benutzer mit der Konferenz-ID und die Telefonnummern der Standard-Audiokonferenzen wird eine e-Mail gesendet werden, oder wenn Sie die Konferenz-ID zurücksetzen eine e-Mail gesendet wird, die die Konferenz-ID, aber nicht mit einer PIN enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="e5282-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="e5282-112">Anzeigen und Ändern der Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="e5282-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="e5282-113">So zeigen Sie die Konferenz-ID an.</span><span class="sxs-lookup"><span data-stu-id="e5282-113">To view the conference ID</span></span>

<span data-ttu-id="e5282-114">Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="e5282-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="e5282-115">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="e5282-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e5282-116">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="e5282-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="e5282-117">In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, den Benutzer auswählen, muss die Konferenz-ID.</span><span class="sxs-lookup"><span data-stu-id="e5282-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="e5282-118">Suchen Sie auf der Seite Aktion unter **Konferenz-ID**ein.</span><span class="sxs-lookup"><span data-stu-id="e5282-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e5282-119">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und audio Telefonnummern durch Klicken auf den Link **Konferenz Informationen per e-Mail senden** , nachdem Sie den Benutzer auf der Seite **Benutzer** auswählen enthält.</span><span class="sxs-lookup"><span data-stu-id="e5282-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="e5282-120">Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5282-120">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="e5282-121">Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e5282-121">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="e5282-122">Finden Sie unter [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) erfahren Sie mehr über das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5282-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="e5282-123">Zuweisen oder ändern die Konferenz-ID</span><span class="sxs-lookup"><span data-stu-id="e5282-123">To assign or change the conference ID</span></span>

<span data-ttu-id="e5282-124">Sie können zuweisen oder eine Konferenz-ID für einen Benutzer ändern, wenn Sie beispielsweise eine Person eine Konferenz-ID möchte, die leicht zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="e5282-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e5282-125">Die Skype für Business-Verwaltungskonsole kann nicht verwendet werden, so bearbeiten Sie eine Konferenz-ID, die automatisch erstellt wurde, aber Sie können Windows PowerShell verwenden, bearbeiten oder ändern eine Konferenz-ID, die Sie festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="e5282-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="e5282-126">Zum Bearbeiten oder ändern die Konferenz-ID für einen Benutzer, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e5282-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="e5282-127">Eine Konferenzkennung muss sieben Ziffern umfassen. Sie kann nicht im Skype for Business Admin Center oder mit Windows PowerShell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e5282-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="e5282-128">So setzen Sie die Konferenz-ID zurück.</span><span class="sxs-lookup"><span data-stu-id="e5282-128">To reset the conference ID</span></span>

<span data-ttu-id="e5282-129">Sie können eine Konferenz-ID für einen Benutzer zurücksetzen "If"; beispielsweise, wenn sie es vergessen.</span><span class="sxs-lookup"><span data-stu-id="e5282-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="e5282-130">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="e5282-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e5282-131">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="e5282-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="e5282-132">In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, klicken Sie im Aktionsbereich unter **Konferenz-ID**, klicken Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="e5282-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="e5282-133">In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e5282-133">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="e5282-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="e5282-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="e5282-135">Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="e5282-135">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="e5282-136">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e5282-136">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="e5282-137">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="e5282-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="e5282-138">Nachdem eine neue Konferenz-ID erstellt wird oder eine zurückgesetzt wird, kann nicht die alte Konferenz-ID BSSID verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5282-138">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="e5282-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="e5282-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="e5282-140">Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="e5282-140">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="e5282-141">Informationen zum Herunterladen, installieren und Ausführen des Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)und [Skype für Online Business Besprechung Migration Tool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="e5282-141">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="e5282-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5282-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="e5282-143">Die Konferenz-ID muss die Länge in Ziffern legen Sie für die audiokonferenzbrücke erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e5282-143">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="e5282-144">Sie können nicht alphabetische oder Sonderzeichen im Konferenz-IDs verwenden. nur Zahlen können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5282-144">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="e5282-145">Die Konferenz-ID für alle Ihre audiokonferenzbenutzer werden standardmäßig 7 Ziffern, und die Anzahl der Nachkommastellen kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e5282-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e5282-146">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="e5282-146">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e5282-p109">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e5282-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e5282-150">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e5282-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e5282-151">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="e5282-151">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="e5282-p110">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e5282-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e5282-154">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5282-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="e5282-155">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e5282-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e5282-156">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e5282-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="e5282-157">See Also</span><span class="sxs-lookup"><span data-stu-id="e5282-157">Related topics</span></span>

[<span data-ttu-id="e5282-158">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="e5282-158">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

