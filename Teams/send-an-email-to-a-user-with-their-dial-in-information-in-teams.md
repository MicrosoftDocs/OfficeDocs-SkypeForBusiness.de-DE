---
title: Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Senden Sie E-Mails mit Audiokonferenzinformationen an Ihre Benutzer in Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892092"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="2366d-103">Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2366d-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="2366d-104">Manchmal müssen Sie Microsoft Teams-Benutzern ihre Audiokonferenzinformationen senden.</span><span class="sxs-lookup"><span data-stu-id="2366d-104">Sometimes users may need you to send them their dial-in conferencing information.</span></span> <span data-ttu-id="2366d-105">Dazu können Sie unter den Eigenschaften für einen Benutzer auf **Konferenzinformationen per E-Mail senden** klicken.</span><span class="sxs-lookup"><span data-stu-id="2366d-105">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the dial-in properties for a user.</span></span> <span data-ttu-id="2366d-106">Wenn Sie diese E-Mail senden, enthält sie alle Audiokonferenzinformationen, wie zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2366d-106">When you send this email, it will contain all of the dial-in information including:</span></span>
  
- <span data-ttu-id="2366d-107">Die Konferenztelefonnummer oder Dial-in-Telefonnummer für den Benutzer</span><span class="sxs-lookup"><span data-stu-id="2366d-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="2366d-108">Die Konferenzkennung des Benutzers</span><span class="sxs-lookup"><span data-stu-id="2366d-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="2366d-109">Hier ist ein Beispiel für die gesendete E-Mail:</span><span class="sxs-lookup"><span data-stu-id="2366d-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![E-Mail zu einer Dial-in-Konferenz](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="2366d-111">Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="2366d-111">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="2366d-112">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="2366d-112">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="2366d-113">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2366d-113">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="2366d-114">Klicken Sie unter **Audiokonferenz** auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).</span><span class="sxs-lookup"><span data-stu-id="2366d-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="2366d-115">Was sollten Sie sonst über diese E-Mail wissen?</span><span class="sxs-lookup"><span data-stu-id="2366d-115">What else should you know about this email?</span></span>

- <span data-ttu-id="2366d-116">Es gibt mehrere Situationen, in denen E-Mails an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="2366d-116">There are several emails that are set to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="2366d-117">Wenn ihnen eine Lizenz für **Audiokonferenzen** zugewiesen wird</span><span class="sxs-lookup"><span data-stu-id="2366d-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="2366d-118">Wenn Sie die Audiokonferenz-PIN von Benutzern manuell zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="2366d-118">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="2366d-119">Wenn Sie die Konferenzkennung von Benutzern manuell zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="2366d-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="2366d-120">Wenn ihre Lizenz für **Audiokonferenzen** entfernt wird</span><span class="sxs-lookup"><span data-stu-id="2366d-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="2366d-121">Wenn der Audiokonferenzanbieter für Benutzer von Microsoft in einen anderen Anbieter oder in **Keiner** geändert wird</span><span class="sxs-lookup"><span data-stu-id="2366d-121">When the dial-in conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="2366d-122">Wenn der Audiokonferenzanbieter für Benutzer in Microsoft geändert wird</span><span class="sxs-lookup"><span data-stu-id="2366d-122">When the dial-in conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="2366d-123">Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="2366d-123">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the Set-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="2366d-124">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="2366d-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2366d-125">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="2366d-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="2366d-p103">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2366d-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2366d-129">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="2366d-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2366d-130">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2366d-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="2366d-131">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="2366d-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="2366d-132">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2366d-132">Related topics</span></span>

[<span data-ttu-id="2366d-133">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="2366d-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
