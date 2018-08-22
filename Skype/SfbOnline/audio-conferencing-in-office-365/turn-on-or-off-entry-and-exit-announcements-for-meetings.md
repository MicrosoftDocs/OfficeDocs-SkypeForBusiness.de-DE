---
title: Aktivieren oder Deaktivieren der Eintrag und Beenden von Ansagen für Besprechungen in Skype für Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: d6d1b70713ac0cd7a38f7de9cb84f0acb54cbe30
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490485"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="23b87-103">Aktivieren oder Deaktivieren der Eintrag und Beenden von Ansagen für Besprechungen in Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="23b87-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="23b87-104">Informationen zu zu- und Ansagen im Microsoft-Teams finden Sie unter [Aktivieren oder Deaktivieren von zu- und Ankündigungen für Besprechungen in Microsoft-Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="23b87-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="23b87-105">Wenn Sie Audiokonferenzen in Office 365 einrichten, erhalten Sie eine audiokonferenzbrücke.</span><span class="sxs-lookup"><span data-stu-id="23b87-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="23b87-106">Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, mit denen Personen einen Skype für Business Besprechung anrufen.</span><span class="sxs-lookup"><span data-stu-id="23b87-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="23b87-107">Die Konferenzbrücke beantwortet einen Anruf für einen Benutzer, die in einer Besprechung mit einem Telefon einwählt.</span><span class="sxs-lookup"><span data-stu-id="23b87-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="23b87-108">Bitten Sie die Konferenzbrücke den Anrufer mit Ansagen aus einer Live Meeting-Telefonzentrale beantwortet, und klicken Sie dann je nach Ihrer Einstellungen kann wiedergeben Benachrichtigungen, Anrufer dokumentieren Sie ihren Namen, und richten Sie die PIN-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="23b87-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="23b87-109">Eine PIN zu einem Skype für Business Besprechungsorganisator angegeben wird, und es ermöglicht es ihnen, eine Besprechung starten, wenn die Besprechung mithilfe der Skype für Geschäfts-app gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="23b87-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="23b87-110">Sie können, jedoch festlegen, sodass eine PIN erforderlich ist, um eine Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="23b87-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="23b87-111">Festlegen von Optionen für die Besprechungsteilnahme</span><span class="sxs-lookup"><span data-stu-id="23b87-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="23b87-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="23b87-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="23b87-113">Unter **Erleben Sie die Teilnahme an einer Besprechung**de- **Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden**.</span><span class="sxs-lookup"><span data-stu-id="23b87-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="23b87-114">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="23b87-114">This is selected by default.</span></span> <span data-ttu-id="23b87-115">Wenn Sie ihn deaktivieren, werden nicht Benutzer, die bereits an der Besprechung benachrichtigt, wenn ein Benutzer eingibt oder die Besprechung verlässt.</span><span class="sxs-lookup"><span data-stu-id="23b87-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="23b87-116">Wählen Sie unter **Entry/Exit Ankündigung Typ** **Namen oder Rufnummern** oder **Töne**.</span><span class="sxs-lookup"><span data-stu-id="23b87-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="23b87-117">Überprüfen Sie, oder deaktivieren Sie **Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen**.</span><span class="sxs-lookup"><span data-stu-id="23b87-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="23b87-118">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="23b87-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="23b87-119">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="23b87-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="23b87-120">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) nutzen.</span><span class="sxs-lookup"><span data-stu-id="23b87-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="23b87-p104">In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="23b87-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="23b87-124">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="23b87-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="23b87-125">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23b87-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="23b87-126">Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie Einstellungen Änderungen für viele Benutzer gleichzeitig durchführen.</span><span class="sxs-lookup"><span data-stu-id="23b87-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="23b87-127">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="23b87-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="23b87-128">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="23b87-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="23b87-129">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="23b87-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="23b87-130">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="23b87-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="23b87-p106">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="23b87-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="23b87-133">See Also</span><span class="sxs-lookup"><span data-stu-id="23b87-133">Related topics</span></span>

[<span data-ttu-id="23b87-134">Allgemeine Fragen zu Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="23b87-134">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
