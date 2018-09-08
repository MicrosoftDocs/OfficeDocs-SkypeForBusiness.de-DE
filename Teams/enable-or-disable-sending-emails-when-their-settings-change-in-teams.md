---
title: Aktivieren Sie oder deaktivieren Sie e-Mails senden, wenn Audiokonferenzen Einstellungen in Microsoft-Teams, ändern
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
description: 'Informationen Sie zum Aktivieren oder Deaktivieren von Skype Senden von e-Mails an Benutzer, wenn die Einstellungen wie Pin ändert oder Konferenzen Zahl ändert sich der Standard in Microsoft-Teams. '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892502"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="7539f-103">Aktivieren Sie oder deaktivieren Sie e-Mails senden, wenn Audiokonferenzen Einstellungen in Microsoft-Teams, ändern</span><span class="sxs-lookup"><span data-stu-id="7539f-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="7539f-104">Benutzer werden automatisch per e-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7539f-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="7539f-105">Unter Umständen, jedoch, wenn die Anzahl der e-Mails zu reduzieren, die Microsoft-Teams, Benutzern gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7539f-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="7539f-106">In diesem Fall können Sie die sendende e-Mail deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7539f-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="7539f-107">Wenn Sie e-Mails senden deaktivieren, werden nicht Audiokonferenzen-e-Mails gesendet werden für die Benutzer, einschließlich e-Mails für Benutzer aktiviert oder deaktiviert für Audiokonferenzen, wenn seine PIN zurückgesetzt wurde und die Konferenz-ID und das Standard-Konferenzen ändert sich phone sind .</span><span class="sxs-lookup"><span data-stu-id="7539f-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="7539f-108">Es folgt ein Beispiel der e-Mails, die an Benutzer gesendet wird, wenn sie für Audiokonferenzen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="7539f-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Audio Conferencing-e-Mail](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="7539f-110">Wann werden E-Mails an Benutzer gesendet?</span><span class="sxs-lookup"><span data-stu-id="7539f-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="7539f-111">Es gibt mehrere e-Mails, die gesendet werden, um Benutzer in Ihrer Organisation, nachdem sie aktiviert sind für Audiokonferenzen:</span><span class="sxs-lookup"><span data-stu-id="7539f-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="7539f-112">Wenn Ihnen eine **Audiokonferenz** -Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7539f-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="7539f-113">Wenn Sie manuell des Benutzers Audiokonferenzen PIN zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="7539f-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="7539f-114">Wenn Sie die Konferenz-PIN des Benutzers manuell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="7539f-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="7539f-115">Wenn die Lizenz **Audiokonferenzen** daraus entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="7539f-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="7539f-116">Wenn der Anbieter von Audiokonferenzen eines Benutzers aus Microsoft in einem anderen Anbieter oder **keiner**geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7539f-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="7539f-117">Wenn der Anbieter von Audiokonferenzen eines Benutzers an Microsoft geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7539f-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="7539f-118">Aktivieren oder Deaktivieren von e-Mail an Benutzer gesendet wird</span><span class="sxs-lookup"><span data-stu-id="7539f-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="7539f-119">Sie können die Microsoft-Teams oder mit Windows PowerShell verwenden, aktivieren oder Deaktivieren von e-Mail an Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="7539f-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="7539f-120">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7539f-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="7539f-121">Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**.</span><span class="sxs-lookup"><span data-stu-id="7539f-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7539f-122">Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="7539f-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="7539f-123">Klicken Sie im Bereich **Bridge-Einstellungen** aktivieren oder Deaktivieren von **Benutzern Wenn Ändern ihrer Einstellungen für die Zugriffsnummer für Einwahl-e-Mails automatisch gesendet**.</span><span class="sxs-lookup"><span data-stu-id="7539f-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="7539f-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7539f-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="7539f-125">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7539f-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="7539f-126">Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7539f-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7539f-127">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="7539f-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7539f-p102">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7539f-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7539f-131">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="7539f-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7539f-132">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7539f-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="7539f-133">Weitere Informationen zu Windows PowerShell finden Sie in der [Referenz zu Microsoft-Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7539f-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="7539f-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7539f-134">Related topics</span></span>

[<span data-ttu-id="7539f-135">An Benutzer gesendet wird, wenn Ändern ihrer Einstellungen für die Audiokonferenz-e-Mails</span><span class="sxs-lookup"><span data-stu-id="7539f-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="7539f-136">Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="7539f-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


