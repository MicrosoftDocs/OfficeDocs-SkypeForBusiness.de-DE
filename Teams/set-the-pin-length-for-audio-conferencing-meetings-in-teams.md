---
title: Festlegen der Länge der PIN für Audiokonferenzbesprechungen in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Hier erhalten Sie Informationen zu den Parametern für die PIN-Länge und die Anforderungen an PINs. Außerdem erfahren Sie, wie Sie die Länge für Besprechungen in Microsoft Teams festlegen.
ms.openlocfilehash: 8e0be3a904f4172aa0f92c1632ad37992a36ab5f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296426"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="99828-103">Festlegen der Länge der PIN für Audiokonferenzbesprechungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="99828-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="99828-104">Beim Einrichten von Audiokonferenzen für Microsoft Teams erhalten Sie eine Audiokonferenzbrücke.</span><span class="sxs-lookup"><span data-stu-id="99828-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="99828-105">Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen.</span><span class="sxs-lookup"><span data-stu-id="99828-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="99828-106">Die Telefonnummer, die Sie festlegen, wird in den Besprechungseinladungen für die Microsoft Teams-App angegeben.</span><span class="sxs-lookup"><span data-stu-id="99828-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="99828-107">Die Audiokonferenzbrücke nimmt Anrufe von Benutzern an, die sich über ein Telefon in eine Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="99828-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="99828-108">Sie gibt für den Anrufer Sprachanweisungen einer automatischen Konferenzzentrale aus. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben und Anrufer auffordern, ihren Namen aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="99828-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="99828-109">Unter **Einstellungen von Microsoft Bridge** können Sie die Einstellungen für Besprechungsbenachrichtigungen und die Besprechungsteilnahme ändern und die Länge der von Besprechungsorganisatoren verwendeten PINs festlegen.</span><span class="sxs-lookup"><span data-stu-id="99828-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="99828-110">Besprechungsorganisatoren verwenden PINs zum Starten von Besprechungen, wenn sie nicht über die Microsoft Teams-App an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="99828-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="99828-111">Festlegen der PIN-Länge</span><span class="sxs-lookup"><span data-stu-id="99828-111">Setting the PIN length</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="99828-113">Verwenden des Microsoft-Teams und Skype for Business-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="99828-113">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="99828-114">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="99828-114">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="99828-115">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="99828-115">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="99828-116">Wählen Sie im Bereich **Bridge Einstellungen** unter **PIN-Mindestlänge**die Anzahl der Ziffern, die Sie für die PIN verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="99828-116">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="99828-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="99828-117">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="99828-p103">Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="99828-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="99828-122">Möchten Sie weitere Informationen zu PIN-Einstellungen wissen?</span><span class="sxs-lookup"><span data-stu-id="99828-122">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="99828-123">PINs können von 4 bis 12 Ziffern annehmen. Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="99828-123">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="99828-124">PINs können nur Zahlen umfassen.</span><span class="sxs-lookup"><span data-stu-id="99828-124">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="99828-125">Buchstaben und Sonderzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="99828-125">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="99828-126">Eine PIN ist nur für Organisator der Besprechung erforderlich, wenn ein Benutzer Microsoft-Teams, die Besprechung noch nicht bereits gestartet.</span><span class="sxs-lookup"><span data-stu-id="99828-126">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="99828-127">Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.</span><span class="sxs-lookup"><span data-stu-id="99828-127">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="99828-p106">Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="99828-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="99828-130">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="99828-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="99828-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="99828-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="99828-134">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="99828-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="99828-135">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99828-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="99828-136">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="99828-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="99828-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="99828-137">Related topics</span></span>

[<span data-ttu-id="99828-138">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="99828-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
