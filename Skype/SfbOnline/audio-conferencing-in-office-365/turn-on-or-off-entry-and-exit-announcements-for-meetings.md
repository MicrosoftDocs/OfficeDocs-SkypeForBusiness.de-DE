---
title: Ein- und Ausschalten von Ein- und Ausstiegsankündigungen für Besprechungen in Skype for Business Online
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
description: 'Erfahren Sie, wie Sie Ein- und Ausstiegsankündigungen in einer Skype for Business Online-Besprechung mit dem Skype for Business Admin Center ein- und ausschalten können. '
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779035"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="3f837-103">Ein- und Ausschalten von Ein- und Ausstiegsankündigungen für Besprechungen in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f837-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="3f837-104">Informationen zu Ein- und Ausstiegsankündigungen in Microsoft Teams finden Sie unter [Ein- und Ausstiegsankündigungen für Besprechungen in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="3f837-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="3f837-105">Wenn Sie Audiokonferenzen in Office 365 einrichten, erhalten Sie eine Audiokonferenzbrücke.</span><span class="sxs-lookup"><span data-stu-id="3f837-105">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="3f837-106">Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, mit denen Personen eine Skype for Business-Besprechung anrufen.</span><span class="sxs-lookup"><span data-stu-id="3f837-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="3f837-107">Die Konferenzbrücke beantwortet einen Anruf für einen Benutzer, der mit einem Telefon in eine Besprechung einwählt.</span><span class="sxs-lookup"><span data-stu-id="3f837-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="3f837-108">Die Konferenzbrücke antwortet dem Anrufer mit Sprachansagen einer automatischen Telefonzentrale und kann dann, abhängig von Ihren Einstellungen, Benachrichtigungen abspielen, Anrufer auffordern, ihren Namen aufzuzeichnen und die PIN-Sicherheit einrichten.</span><span class="sxs-lookup"><span data-stu-id="3f837-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="3f837-109">Einem Organisator von Skype for Business-Besprechungen wird eine PIN zugewiesen, die es ihm ermöglicht, eine Besprechung zu starten, wenn er die Besprechung nicht mit der Skype for Business-Anwendung starten kann.</span><span class="sxs-lookup"><span data-stu-id="3f837-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="3f837-110">Sie können jedoch festlegen, dass eine PIN nicht erforderlich ist, um eine Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="3f837-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="3f837-111">Festlegen von Optionen für die Besprechungsteilnahme</span><span class="sxs-lookup"><span data-stu-id="3f837-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="3f837-112">in der linken Navigation des **Skype for Business Admin Center**, wechseln Sie zu **Audiokonferenz** > **Microsoft Bridge-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="3f837-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="3f837-113">Unter **Besprechungsteilnahme erfahren** wählen oder löschen Sie **Aktivieren von Benachrichtigungen zum Ein- und Ausstieg bei Besprechungen**.</span><span class="sxs-lookup"><span data-stu-id="3f837-113">Under Meeting join experience  Enable meeting entry and exit notifications to be turned on</span></span> <span data-ttu-id="3f837-114">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3f837-114">This is selected by default.</span></span> <span data-ttu-id="3f837-115">Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="3f837-115">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="3f837-116">Unter **Einstieg/Ausstieg-Ansagetyp** wählen Sie **Namen oder Telefonnummern** oder **Töne**.</span><span class="sxs-lookup"><span data-stu-id="3f837-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="3f837-117">Aktivieren oder deaktivieren Sie **Anrufer bitten, ihren Namen aufzuzeichnen, bevor sie dem Meeting beitreten**.</span><span class="sxs-lookup"><span data-stu-id="3f837-117">Ask callers to record their name before joining the meeting</span></span>
    
5. <span data-ttu-id="3f837-118">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3f837-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3f837-119">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="3f837-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3f837-120">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) nutzen.</span><span class="sxs-lookup"><span data-stu-id="3f837-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="3f837-p104">In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f837-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3f837-124">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="3f837-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3f837-125">Optimale Möglichkeiten zur Verwaltung von Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f837-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="3f837-126">Windows PowerShell bietet viele Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität gegenüber der ausschließlichen Verwendung des Office 365 Admin Center, beispielsweise wenn Sie Einstellungen für viele Benutzer gleichzeitig ändern.</span><span class="sxs-lookup"><span data-stu-id="3f837-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> <span data-ttu-id="3f837-127">Erfahren Sie mehr über diese Vorteile in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="3f837-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="3f837-128">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f837-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3f837-129">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f837-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3f837-130">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f837-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="3f837-p106">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="3f837-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3f837-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3f837-133">Related topics</span></span>

[<span data-ttu-id="3f837-134">Allgemeine Fragen zur Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="3f837-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
