---
title: Einrichten einer Konferenz-ID für einen Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 6cc73876d188f1ae00ec267e14af4771ded7b957
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="68a88-103">Einrichten einer Konferenz-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="68a88-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="68a88-104">Wenn Ihr Unternehmen noch nicht für dynamische Konferenz IDs aktiviert wurde, wird eine statische Konferenz-ID automatisch erstellt, wenn ein Skype für Benutzer Business oder Microsoft-Teams für Microsoft als Anbieter von Audiokonferenzen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="68a88-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="68a88-105">Diese Konferenz-ID ist enthalten am unteren Rand Besprechungsanfragen zusammen mit der Zugriffsnummer für Einwahl Telefonnummern, die von Anrufern zu einer Besprechung Anrufen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="68a88-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="68a88-106">Wenn der Benutzer die Telefonnummer wählt, wird die automatische Telefonzentrale für die Besprechung bitten Sie den Anrufer an diese Konferenz-ID eingeben, damit sie an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="68a88-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68a88-107">Ist Ihr Konferenzanbieter Microsoft, werden Ihrer Benutzer Konferenz-IDs auf dynamische nur in der Standardeinstellung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="68a88-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="68a88-108">Leider werden Sie kann nicht in der Skype für Business-Verwaltungskonsole oder mithilfe von Windows Powershell geändert.</span><span class="sxs-lookup"><span data-stu-id="68a88-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="68a88-109">Sie müssen Microsoft-Supportmitarbeiter kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="68a88-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="68a88-110">Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="68a88-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="68a88-111">Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen</span><span class="sxs-lookup"><span data-stu-id="68a88-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="68a88-112">Wenn Sie zuweisen dynamische statt statische Konferenz-IDs, [Wechseln Sie hier möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="68a88-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="68a88-113">Konferenz-IDs werden nur für Skype für Geschäfts- und Microsoft-Teams für Audiokonferenzen aktivierte Benutzer nur automatisch festgelegt als Anbieter von Audiokonferenzen mithilfe von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68a88-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="68a88-114">Wenn Sie müssen eine Konferenz-ID für einen Benutzer zurückgesetzt werden, die einen Drittanbieter-Audiokonferenzen (ACP) verwendet wird, müssen Sie eine Konferenz-ID manuell auf der Eigenschaftenseite für den Benutzer eingeben.</span><span class="sxs-lookup"><span data-stu-id="68a88-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="68a88-115">Zurücksetzen der Konferenz-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="68a88-115">Resetting the conference ID for a user</span></span>

<span data-ttu-id="68a88-116">**Verwenden des Microsoft-Teams und Skype for Business-Verwaltungskonsole**</span><span class="sxs-lookup"><span data-stu-id="68a88-116">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="68a88-117">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="68a88-117">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="68a88-118">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="68a88-118">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="68a88-119">Klicken Sie auf das Menü neben **Konferenz Brücken**, und klicken Sie dann auf **Zurücksetzen Konferenz-Id** in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="68a88-119">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="68a88-120">Klicken Sie im Fenster **Konferenz-Id zurücksetzen** klicken Sie auf **Ok**.</span><span class="sxs-lookup"><span data-stu-id="68a88-120">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="68a88-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="68a88-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="68a88-122">Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="68a88-122">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="68a88-123">**Verwenden des Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="68a88-123">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="68a88-124">Klicken Sie in der **Skype für Business Administrationscenter**auf **Audiokonferenzen** > **Benutzer**, wählen einen Benutzer aus, und klicken Sie dann im Aktionsbereich unter **Konferenz-ID** **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="68a88-124">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="68a88-125">In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="68a88-125">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="68a88-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="68a88-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="68a88-127">Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="68a88-127">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="68a88-p107">Nach dem Zurücksetzen der Konferenz-ID wird die neue Konferenz-ID per E-Mail an den Benutzer geschickt. Diese E-Mail wird an die Haupt-E-Mail-Adresse geschickt. Dabei handelt es sich oftmals um das Office 365-Postfach. Die E-Mail umfasst die neue Konferenz-ID, die Standardeinwahlnummer(n) und Anweisungen, wie bestehende Besprechungen mithilfe des Skype for Business Meeting Update Tool aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="68a88-p107">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="68a88-131">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="68a88-131">What else should I know?</span></span>

- <span data-ttu-id="68a88-132">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und die Zugriffsnummer für Einwahl Telefonnummern enthält, indem Sie für den Benutzer im Aktionsbereich auf **Konferenz Informationen per e-Mail senden** .</span><span class="sxs-lookup"><span data-stu-id="68a88-132">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="68a88-133">Die PIN senden nicht.</span><span class="sxs-lookup"><span data-stu-id="68a88-133">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="68a88-134">Enthält eine Konferenz-ID 7 Ziffern, und deren Länge in der Skype für Business-Verwaltungskonsole oder mithilfe von Windows PowerShell können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="68a88-134">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="68a88-135">Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="68a88-135">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="68a88-136">Wenn Sie den Benutzer auf der Seite **Benutzer** auswählen, kann die Konferenz-ID für einen Benutzer für Audiokonferenzen am unteren Rand der Aktionsbereich unter **Audiokonferenzen** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="68a88-136">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="68a88-137">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="68a88-137">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="68a88-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="68a88-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="68a88-139">Die Benutzer können Skype für Business Besprechung Tool um vorhandenen Besprechungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="68a88-139">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="68a88-140">Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="68a88-140">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="68a88-141">Skype for Business (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="68a88-141">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="68a88-142">Skype for Business Online, Meeting Migration Tool (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="68a88-142">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="68a88-143">Skype for Business Online, Meeting Migration Tool (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="68a88-143">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="68a88-144">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="68a88-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="68a88-p110">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="68a88-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="68a88-148">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="68a88-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="68a88-149">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="68a88-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="68a88-p111">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="68a88-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="68a88-152">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="68a88-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="68a88-153">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="68a88-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="68a88-154">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="68a88-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="68a88-155">See Also</span><span class="sxs-lookup"><span data-stu-id="68a88-155">Related topics</span></span>

[<span data-ttu-id="68a88-156">Zurücksetzen der Audiokonferenz-PIN für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="68a88-156">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
