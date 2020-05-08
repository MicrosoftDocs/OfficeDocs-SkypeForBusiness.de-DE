---
title: Einrichten der PIN-Länge für Audiokonferenz-Besprechungen in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Lernen Sie die Parameter für die Länge und die Anforderungen einer PIN kennen, und erfahren Sie, wie Sie die Länge für Besprechungen in Skype for Business festzulegen.
ms.openlocfilehash: 9e1be77b18c5b416d220ce5d7432562888ce5752
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164534"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="fd0da-103">Einrichten der PIN-Länge für Audiokonferenz-Besprechungen in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fd0da-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="fd0da-104">Informationen zum Festlegen der PIN-Länge in Microsoft Teams finden Sie unter [Festlegen der PIN-Länge für Audiokonferenz-Besprechungen in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="fd0da-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="fd0da-105">Wenn Sie Audiokonferenzen für Skype for Business einrichten, erhalten Sie eine Audiokonferenz-Brücke.</span><span class="sxs-lookup"><span data-stu-id="fd0da-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="fd0da-106">Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen.</span><span class="sxs-lookup"><span data-stu-id="fd0da-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="fd0da-107">Die von Ihnen festgelegte Telefonnummer wird in die Besprechungseinladungen für die Skype for Business-App aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="fd0da-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="fd0da-108">Die Audiokonferenzbrücke nimmt Anrufe von Benutzern an, die sich über ein Telefon in eine Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="fd0da-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="fd0da-109">Sie beantwortet den Anrufer mit Sprachansagen von einer automatischen Telefonzentrale und kann dann – je nach Ihren Einstellungen – Benachrichtigungen abspielen und Anrufer bitten, deren Namen aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="fd0da-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="fd0da-110">Mit den **Microsoft Bridge-Einstellungen** können Sie die Einstellungen für Besprechungs Benachrichtigungen und die Besprechungsteilnahme ändern und die Länge der Pins festlegen, die von Besprechungsorganisatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd0da-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="fd0da-111">Besprechungsorganisatoren verwenden Pins zum Starten von Besprechungen, wenn Sie nicht mit der Skype for Business-APP an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="fd0da-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="fd0da-112">Konfigurieren der PIN-Länge</span><span class="sxs-lookup"><span data-stu-id="fd0da-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="fd0da-113">Wechseln Sie im **Skype for Business Admin Center**in der linken Navigationsleiste zu **Audiokonferenz** > -**Einstellungen für Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="fd0da-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="fd0da-114">Wählen Sie unter **Sicherheits** > -**PIN-Länge**die gewünschte Anzahl der Ziffern für die PIN aus, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fd0da-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fd0da-p103">Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="fd0da-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="fd0da-119">Möchten Sie mehr über die PIN-Einstellungen erfahren?</span><span class="sxs-lookup"><span data-stu-id="fd0da-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="fd0da-120">Pins können von 4 bis 12 Ziffern sein; der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="fd0da-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="fd0da-121">PINs können nur Zahlen umfassen.</span><span class="sxs-lookup"><span data-stu-id="fd0da-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="fd0da-122">Buchstaben und Sonderzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="fd0da-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="fd0da-123">Eine PIN ist nur für den Besprechungsorganisator erforderlich, wenn ein Skype for Business-Benutzer die Besprechung noch nicht gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="fd0da-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="fd0da-124">Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.</span><span class="sxs-lookup"><span data-stu-id="fd0da-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="fd0da-p106">Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="fd0da-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="fd0da-127">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="fd0da-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="fd0da-128">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) nutzen.</span><span class="sxs-lookup"><span data-stu-id="fd0da-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="fd0da-129">So stellen Sie die Anzahl der Ziffern in der PIN auf 8 Ziffern ein:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="fd0da-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="fd0da-130">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fd0da-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fd0da-131">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fd0da-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="fd0da-132">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fd0da-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fd0da-133">Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd0da-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="fd0da-134">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd0da-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="fd0da-135">Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Änderungen an den Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="fd0da-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="fd0da-136">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fd0da-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="fd0da-137">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fd0da-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="fd0da-138">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fd0da-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="fd0da-139">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fd0da-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="fd0da-140">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fd0da-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="fd0da-p109">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="fd0da-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fd0da-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd0da-143">See also</span></span>

[<span data-ttu-id="fd0da-144">Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="fd0da-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
