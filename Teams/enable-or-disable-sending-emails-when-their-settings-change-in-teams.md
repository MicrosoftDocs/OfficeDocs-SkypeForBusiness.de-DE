---
title: Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Hier erfahren Sie, wie Sie die von Skype an Benutzer gesendeten E-Mails bei Änderungen an Einstellungen wie zum Beispiel PINs oder standardmäßigen Konferenztelefonnummern in Microsoft Teams aktivieren oder deaktivieren. '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892502"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="9dce5-103">Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9dce5-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="9dce5-104">Benutzer werden automatisch per E-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="9dce5-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="9dce5-105">Es kann jedoch Fälle geben, in denen Sie die Anzahl der an Microsoft Teams-Benutzer gesendeten E-Mails reduzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9dce5-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="9dce5-106">In diesen Fällen können Sie das Senden von E-Mails deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9dce5-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="9dce5-107">Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails zu Audiokonferenzen an die Benutzer gesendet. Dazu zählen auch E-Mails, die normalerweise gesendet werden, wenn Benutzer für Audiokonferenzen aktiviert oder deaktiviert werden, wenn ihre PIN zurückgesetzt wird oder wenn sich die Konferenzkennung und die standardmäßige Konferenztelefonnummer ändern.</span><span class="sxs-lookup"><span data-stu-id="9dce5-107">If you disable sending emails, all dial-in conferencing emails won't be sent to your users including emails for when users are enabled or disabled for dial-in conferencing, when their PIN is reset, when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="9dce5-108">Hier ist ein Beispiel für eine E-Mail, die beim Aktivieren von Benutzern für Audiokonferenzen an die Benutzer gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="9dce5-108">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![E-Mails zu Audiokonferenzen](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="9dce5-110">Wann werden E-Mails an Benutzer gesendet?</span><span class="sxs-lookup"><span data-stu-id="9dce5-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="9dce5-111">Es gibt mehrere Situationen, in denen E-Mails an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="9dce5-111">There are several emails that are set to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="9dce5-112">Wenn ihnen eine Lizenz für **Audiokonferenzen** zugewiesen wird</span><span class="sxs-lookup"><span data-stu-id="9dce5-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="9dce5-113">Wenn Sie die Audiokonferenz-PIN von Benutzern manuell zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="9dce5-113">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="9dce5-114">Wenn Sie die Konferenzkennung von Benutzern manuell zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="9dce5-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="9dce5-115">Wenn ihre Lizenz für **Audiokonferenzen** entfernt wird</span><span class="sxs-lookup"><span data-stu-id="9dce5-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="9dce5-116">Wenn der Audiokonferenzanbieter für Benutzer von Microsoft in einen anderen Anbieter oder in **Keiner** geändert wird</span><span class="sxs-lookup"><span data-stu-id="9dce5-116">When the dial-in conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="9dce5-117">Wenn der Audiokonferenzanbieter für Benutzer in Microsoft geändert wird</span><span class="sxs-lookup"><span data-stu-id="9dce5-117">When the dial-in conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="9dce5-118">Aktivieren oder Deaktivieren der an Benutzer gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="9dce5-118">Enable or disable email from being sent to audio users</span></span>

<span data-ttu-id="9dce5-119">Sie können die an Benutzer gesendeten E-Mails über Microsoft Teams oder über Windows PowerShell aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9dce5-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="9dce5-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="9dce5-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>
1. <span data-ttu-id="9dce5-121">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="9dce5-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9dce5-122">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="9dce5-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="9dce5-123">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.</span><span class="sxs-lookup"><span data-stu-id="9dce5-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="9dce5-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9dce5-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="9dce5-125">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9dce5-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="9dce5-126">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9dce5-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9dce5-127">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="9dce5-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9dce5-p102">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9dce5-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9dce5-131">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="9dce5-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9dce5-132">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dce5-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9dce5-133">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9dce5-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="9dce5-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9dce5-134">Related topics</span></span>

[<span data-ttu-id="9dce5-135">E-Mails, die an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern</span><span class="sxs-lookup"><span data-stu-id="9dce5-135">Emails sent to users when their settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="9dce5-136">Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="9dce5-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


