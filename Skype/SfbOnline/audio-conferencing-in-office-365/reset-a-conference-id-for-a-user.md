---
title: Zurücksetzen einer Konferenz-ID für einen Benutzer in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Informieren Sie sich über die Schritte zum Zurücksetzen der Konferenz-ID eines Benutzers in Skype for Business Online, und rufen Sie Links zu den Update-und Migrationstools für Besprechungen auf. '
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164704"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="1bc61-103">Zurücksetzen einer Konferenz-ID für einen Benutzer in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1bc61-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="1bc61-104">Informationen zum Zurücksetzen des Konferenz-ID in Microsoft Teams, finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="1bc61-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="1bc61-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span><span class="sxs-lookup"><span data-stu-id="1bc61-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1bc61-p102">Wenn es sich bei Ihrem Konferenzanbieter um Microsoft handelt, sind die Konferenz-IDs Ihrer Benutzer nur auf dynamisch eingestellt. Dies kann nicht geändert werden. Konferenz-IDs werden automatisch nur für Skype for Business-Benutzer eingestellt, die für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1bc61-p102">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only. This cannot be changed. Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="1bc61-110">Zurücksetzen der Konferenz-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="1bc61-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="1bc61-111">Klicken Sie im **Skype for Business Admin Center**auf **Audiokonferenz** > -**Benutzer**, wählen Sie einen Benutzer aus, und klicken Sie dann im Bereich "Aktion" unter **Konferenz-ID** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="1bc61-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="1bc61-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span><span class="sxs-lookup"><span data-stu-id="1bc61-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1bc61-p104">Nachdem Sie die Konferenz-ID zurückgesetzt haben, wird eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet. Diese e-Mail wird in vielen Fällen an die primäre e-Mail-Adresse gesendet, deren Microsoft 365-oder Office 365-Postfach. Die e-Mail-Adresse enthält die neue Konferenz-ID, die Standard-Einwahl Telefonnummer (n) und Anweisungen zur Verwendung des Skype for Business-Besprechungs Aktualisierungstools, um vorhandene Besprechungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1bc61-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="1bc61-118">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="1bc61-118">What else should I know?</span></span>

- <span data-ttu-id="1bc61-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span><span class="sxs-lookup"><span data-stu-id="1bc61-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="1bc61-121">Eine Konferenz-ID enthält 7 Ziffern, und Sie können deren Länge im Skype for Business Admin Center oder mithilfe von Windows PowerShell nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="1bc61-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="1bc61-122">Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1bc61-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="1bc61-123">Die Konferenz-ID für einen Benutzer für Audiokonferenzen kann unten im Bereich "Aktion" unter **Audiokonferenzen** angezeigt werden, wenn Sie den Benutzer auf der Seite " **Benutzer** " auswählen.</span><span class="sxs-lookup"><span data-stu-id="1bc61-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="1bc61-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span><span class="sxs-lookup"><span data-stu-id="1bc61-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="1bc61-128">Skype for Business (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="1bc61-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="1bc61-129">Skype for Business Online, Meeting Migration Tool (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="1bc61-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="1bc61-130">Skype for Business Online, Meeting Migration Tool (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="1bc61-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1bc61-131">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="1bc61-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1bc61-p107">Bei Windows PowerShell geht es um die Verwaltung von Benutzern und um die Benutzer, die zugelassen oder nicht zulässig sind. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Die ersten Schritte mit Windows PowerShell finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1bc61-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1bc61-135">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1bc61-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1bc61-136">Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bc61-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- <span data-ttu-id="1bc61-p108">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Weitere Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1bc61-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1bc61-139">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bc61-139">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1bc61-140">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1bc61-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1bc61-141">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1bc61-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="1bc61-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1bc61-142">Related topics</span></span>

[<span data-ttu-id="1bc61-143">Zurücksetzen der Audiokonferenz-PIN</span><span class="sxs-lookup"><span data-stu-id="1bc61-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
