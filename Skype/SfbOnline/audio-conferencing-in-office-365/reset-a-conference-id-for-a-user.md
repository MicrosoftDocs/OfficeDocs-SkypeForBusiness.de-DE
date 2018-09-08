---
title: Eine Konferenz-ID für einen Benutzer in Skype für Business Online zurücksetzen
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie die Schritte ein Benutzers Zurücksetzen des meeting-Konferenz-ID in Skype für Business Online sowie Get links auf meeting Update und Migration Tools. '
ms.openlocfilehash: d569dfb015db5cea79c57233ba455adfd90a3182
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887545"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="fef56-103">Eine Konferenz-ID für einen Benutzer in Skype für Business Online zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="fef56-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="fef56-104">Informationen zum Zurücksetzen des Konferenz-ID in Microsoft Teams, finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="fef56-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="fef56-105">Eine dynamische Konferenz-ID ist enthalten am unteren Rand Besprechungsanfragen zusammen mit der Zugriffsnummer für Einwahl Telefonnummern, die von Anrufern zu einer Besprechung Anrufen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fef56-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="fef56-106">Wenn der Benutzer die Telefonnummer wählt, wird die automatische Telefonzentrale für die Besprechung bitten Sie den Anrufer an diese Konferenz-ID eingeben, damit sie an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="fef56-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fef56-107">Wenn Ihr Konferenzanbieter Microsoft ist, sind die Konferenz-IDs Ihrer Benutzer standardmäßig auf "Nur dynamisch" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="fef56-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="fef56-108">Leider gibt es keine Möglichkeit, es im Skype for Business Admin Center zu ändern oder Windows PowerShell zu verwenden, damit es statisch wird, da dies nun nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="fef56-108">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="fef56-109">Konferenz-IDs werden automatisch nur für Skype for Business-Benutzer festgelegt, die für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="fef56-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="fef56-110">Zurücksetzen der Konferenz-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="fef56-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="fef56-111">Klicken Sie in der **Skype für Business Administrationscenter**auf **Audiokonferenzen** > **Benutzer**, wählen einen Benutzer aus, und klicken Sie dann im Aktionsbereich unter **Konferenz-ID** **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="fef56-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="fef56-112">In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fef56-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="fef56-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="fef56-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="fef56-114">Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fef56-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fef56-p104">Nach dem Zurücksetzen der Konferenz-ID wird die neue Konferenz-ID per E-Mail an den Benutzer geschickt. Diese E-Mail wird an die Haupt-E-Mail-Adresse geschickt. Dabei handelt es sich oftmals um das Office 365-Postfach. Die E-Mail umfasst die neue Konferenz-ID, die Standardeinwahlnummer(n) und Anweisungen, wie bestehende Besprechungen mithilfe des Skype for Business Meeting Update Tool aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="fef56-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="fef56-118">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="fef56-118">What else should I know?</span></span>

- <span data-ttu-id="fef56-119">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und die Zugriffsnummer für Einwahl Telefonnummern enthält, indem Sie für den Benutzer im Aktionsbereich auf **Konferenz Informationen per e-Mail senden** .</span><span class="sxs-lookup"><span data-stu-id="fef56-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="fef56-120">Die PIN wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef56-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="fef56-121">Enthält eine Konferenz-ID 7 Ziffern, und deren Länge in der Skype für Business-Verwaltungskonsole oder mithilfe von Windows PowerShell können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fef56-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="fef56-122">Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fef56-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="fef56-123">Wenn Sie den Benutzer auf der Seite **Benutzer** auswählen, kann die Konferenz-ID für einen Benutzer für Audiokonferenzen am unteren Rand der Aktionsbereich unter **Audiokonferenzen** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fef56-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="fef56-124">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="fef56-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="fef56-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="fef56-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="fef56-126">Die Benutzer können Skype für Business Besprechung Tool um vorhandenen Besprechungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fef56-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="fef56-127">Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="fef56-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="fef56-128">Skype for Business (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="fef56-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="fef56-129">Skype for Business Online, Meeting Migration Tool (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="fef56-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="fef56-130">Skype for Business Online, Meeting Migration Tool (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="fef56-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="fef56-131">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="fef56-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="fef56-p107">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fef56-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fef56-135">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fef56-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="fef56-136">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="fef56-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="fef56-p108">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fef56-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="fef56-139">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fef56-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="fef56-140">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fef56-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="fef56-141">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fef56-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="fef56-142">See Also</span><span class="sxs-lookup"><span data-stu-id="fef56-142">Related topics</span></span>

[<span data-ttu-id="fef56-143">Die Audiokonferenz PIN zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="fef56-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
