---
title: Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, wie Sie die von Skype an Benutzer gesendeten E-Mails bei Änderungen an Einstellungen wie zum Beispiel PINs oder standardmäßigen Konferenztelefonnummern in Microsoft Teams aktivieren oder deaktivieren. '
ms.openlocfilehash: 2c082410f7acf000473e001f46587025edd6e9c7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015541"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="e4668-103">Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4668-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="e4668-104">Benutzer werden automatisch per e-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e4668-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="e4668-105">Unter Umständen, jedoch, wenn die Anzahl der e-Mails zu reduzieren, die Microsoft-Teams, Benutzern gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4668-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="e4668-106">In diesem Fall können Sie die sendende e-Mail deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e4668-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="e4668-107">Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails zu Audiokonferenzen an die Benutzer gesendet. Dazu zählen auch E-Mails, die normalerweise gesendet werden, wenn Benutzer für Audiokonferenzen aktiviert oder deaktiviert werden, wenn ihre PIN zurückgesetzt wird oder wenn sich die Konferenzkennung und die standardmäßige Konferenztelefonnummer ändern.</span><span class="sxs-lookup"><span data-stu-id="e4668-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="e4668-108">Hier ist ein Beispiel für eine E-Mail, die beim Aktivieren von Benutzern für Audiokonferenzen an die Benutzer gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="e4668-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![E-Mails zu Audiokonferenzen](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="e4668-110">Wann werden E-Mails an Benutzer gesendet?</span><span class="sxs-lookup"><span data-stu-id="e4668-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="e4668-111">Es gibt mehrere Situationen, in denen E-Mails an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="e4668-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="e4668-112">Wenn ihnen eine Lizenz für **Audiokonferenzen** zugewiesen wird</span><span class="sxs-lookup"><span data-stu-id="e4668-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="e4668-113">Wenn Sie die Audiokonferenz-PIN von Benutzern manuell zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="e4668-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="e4668-114">Wenn Sie die Konferenzkennung von Benutzern manuell zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="e4668-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="e4668-115">Wenn ihre Lizenz für **Audiokonferenzen** entfernt wird</span><span class="sxs-lookup"><span data-stu-id="e4668-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="e4668-116">Wenn der Audiokonferenzanbieter für Benutzer von Microsoft in einen anderen Anbieter oder in **Keiner** geändert wird</span><span class="sxs-lookup"><span data-stu-id="e4668-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="e4668-117">Wenn der Audiokonferenzanbieter für Benutzer in Microsoft geändert wird</span><span class="sxs-lookup"><span data-stu-id="e4668-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="e4668-118">Aktivieren oder Deaktivieren der an Benutzer gesendeten E-Mails</span><span class="sxs-lookup"><span data-stu-id="e4668-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="e4668-119">Sie können die an Benutzer gesendeten E-Mails über Microsoft Teams oder über Windows PowerShell aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e4668-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="e4668-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="e4668-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="e4668-121">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="e4668-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="e4668-122">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="e4668-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="e4668-123">Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.</span><span class="sxs-lookup"><span data-stu-id="e4668-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="e4668-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e4668-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="e4668-125">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e4668-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="e4668-126">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="e4668-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e4668-127">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="e4668-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e4668-p102">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e4668-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e4668-131">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="e4668-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e4668-132">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4668-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e4668-133">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="e4668-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="e4668-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e4668-134">Related topics</span></span>

[<span data-ttu-id="e4668-135">E-Mails, die an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern</span><span class="sxs-lookup"><span data-stu-id="e4668-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="e4668-136">Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="e4668-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


