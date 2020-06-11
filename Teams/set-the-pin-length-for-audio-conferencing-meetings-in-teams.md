---
title: Festlegen der Länge der PIN für Audiokonferenzbesprechungen
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Lernen Sie die Parameter für die Länge und die Anforderungen einer PIN kennen, und erfahren Sie, wie Sie die Länge für Besprechungen in Microsoft Teams festzulegen.
ms.openlocfilehash: 7fab4d42846dd5289f3255710684b75fe6fb07bc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691101"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="8ef37-103">Festlegen der Länge der PIN für Audiokonferenzbesprechungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ef37-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="8ef37-104">Beim Einrichten von Audiokonferenzen für Microsoft Teams erhalten Sie eine Audiokonferenzbrücke.</span><span class="sxs-lookup"><span data-stu-id="8ef37-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="8ef37-105">Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen.</span><span class="sxs-lookup"><span data-stu-id="8ef37-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="8ef37-106">Die Telefonnummer, die Sie festlegen, wird in den Besprechungseinladungen für die Microsoft Teams-App angegeben.</span><span class="sxs-lookup"><span data-stu-id="8ef37-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="8ef37-107">Die Audiokonferenzbrücke nimmt Anrufe von Benutzern an, die sich über ein Telefon in eine Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="8ef37-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="8ef37-108">Sie gibt für den Anrufer Sprachanweisungen einer automatischen Konferenzzentrale aus. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben und Anrufer auffordern, ihren Namen aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="8ef37-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="8ef37-109">Unter **Einstellungen von Microsoft Bridge** können Sie die Einstellungen für Besprechungsbenachrichtigungen und die Besprechungsteilnahme ändern und die Länge der von Besprechungsorganisatoren verwendeten PINs festlegen.</span><span class="sxs-lookup"><span data-stu-id="8ef37-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="8ef37-110">Besprechungsorganisatoren verwenden PINs zum Starten von Besprechungen, wenn sie nicht über die Microsoft Teams-App an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="8ef37-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="8ef37-111">Festlegen der PIN-Länge</span><span class="sxs-lookup"><span data-stu-id="8ef37-111">Setting the PIN length</span></span>

<span data-ttu-id="8ef37-112">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="8ef37-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8ef37-113">Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).</span><span class="sxs-lookup"><span data-stu-id="8ef37-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="8ef37-114">Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).</span><span class="sxs-lookup"><span data-stu-id="8ef37-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="8ef37-115">Wählen Sie im Bereich **Brücken Einstellungen** unter **PIN-Länge**die gewünschte Anzahl der Ziffern für die PIN aus.</span><span class="sxs-lookup"><span data-stu-id="8ef37-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="8ef37-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8ef37-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="8ef37-p103">Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8ef37-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="8ef37-121">Möchten Sie mehr über die PIN-Einstellungen erfahren?</span><span class="sxs-lookup"><span data-stu-id="8ef37-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="8ef37-122">Pins können von 4 bis 12 Ziffern sein; der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="8ef37-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="8ef37-123">PINs können nur Zahlen umfassen.</span><span class="sxs-lookup"><span data-stu-id="8ef37-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="8ef37-124">Buchstaben und Sonderzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8ef37-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="8ef37-125">Eine PIN ist nur für den Besprechungsorganisator erforderlich, wenn ein Microsoft Teams-Benutzer die Besprechung noch nicht gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="8ef37-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="8ef37-126">Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.</span><span class="sxs-lookup"><span data-stu-id="8ef37-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="8ef37-p106">Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="8ef37-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8ef37-129">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="8ef37-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="8ef37-130">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8ef37-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8ef37-131">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe einer zentralen Verwaltungsstelle verwalten, die Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8ef37-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="8ef37-132">Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8ef37-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8ef37-133">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="8ef37-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8ef37-134">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ef37-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="8ef37-135">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="8ef37-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="8ef37-136">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8ef37-136">Related topics</span></span>

[<span data-ttu-id="8ef37-137">Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="8ef37-137">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
