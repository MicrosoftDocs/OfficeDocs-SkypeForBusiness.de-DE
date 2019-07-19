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
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 4e4308eab334b37d32cbd53d047ba5fd077a1cad
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792737"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="cf44e-103">Einrichten der PIN-Länge für Audiokonferenz-Besprechungen in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cf44e-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="cf44e-104">Informationen zum Festlegen der PIN-Länge in Microsoft Teams finden Sie unter [Festlegen der PIN-Länge für Audiokonferenz-Besprechungen in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="cf44e-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="cf44e-105">Wenn Sie Audiokonferenzen für Skype for Business einrichten, erhalten Sie eine Audiokonferenz-Brücke.</span><span class="sxs-lookup"><span data-stu-id="cf44e-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="cf44e-106">Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen.</span><span class="sxs-lookup"><span data-stu-id="cf44e-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="cf44e-107">Die von Ihnen festgelegte Telefonnummer wird in die Besprechungseinladungen für die Skype for Business-App aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="cf44e-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="cf44e-108">Die Audiokonferenz-Brücke beantwortet einen Anruf für Personen, die sich per Telefon in eine Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="cf44e-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="cf44e-109">Sie beantwortet den Anrufer mit Sprachansagen von einer automatischen Telefonzentrale und kann dann – je nach Ihren Einstellungen – Benachrichtigungen abspielen und Anrufer bitten, deren Namen aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="cf44e-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="cf44e-110">Mit den **Microsoft Bridge-Einstellungen** können Sie die Einstellungen für Besprechungs Benachrichtigungen und die Besprechungsteilnahme ändern und die Länge der Pins festlegen, die von Besprechungsorganisatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf44e-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="cf44e-111">Besprechungsorganisatoren verwenden Pins zum Starten von Besprechungen, wenn Sie nicht mit der Skype for Business-APP an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="cf44e-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="cf44e-112">Konfigurieren der PIN-Länge</span><span class="sxs-lookup"><span data-stu-id="cf44e-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="cf44e-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="cf44e-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="cf44e-114">Wählen Sie unter **Sicherheits** > -**PIN-Länge**die gewünschte Anzahl der Ziffern für die PIN aus, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cf44e-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cf44e-p103">Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="cf44e-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="cf44e-119">Möchten Sie mehr über die PIN-Einstellungen erfahren?</span><span class="sxs-lookup"><span data-stu-id="cf44e-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="cf44e-120">Pins können von 4 bis 12 Ziffern sein; der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="cf44e-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="cf44e-121">PINs können nur Zahlen umfassen.</span><span class="sxs-lookup"><span data-stu-id="cf44e-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="cf44e-122">Buchstaben und Sonderzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="cf44e-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="cf44e-123">Eine PIN ist nur für den Besprechungsorganisator erforderlich, wenn ein Skype for Business-Benutzer die Besprechung noch nicht gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="cf44e-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="cf44e-124">Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.</span><span class="sxs-lookup"><span data-stu-id="cf44e-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="cf44e-p106">Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="cf44e-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cf44e-127">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="cf44e-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="cf44e-128">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) nutzen.</span><span class="sxs-lookup"><span data-stu-id="cf44e-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="cf44e-129">So stellen Sie die Anzahl der Ziffern in der PIN auf 8 Ziffern ein:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="cf44e-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="cf44e-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf44e-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cf44e-133">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="cf44e-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="cf44e-134">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf44e-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="cf44e-135">Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Änderungen an den Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cf44e-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="cf44e-136">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="cf44e-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="cf44e-137">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cf44e-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="cf44e-138">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cf44e-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="cf44e-139">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cf44e-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="cf44e-140">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cf44e-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="cf44e-p109">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="cf44e-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf44e-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf44e-143">See also</span></span>

[<span data-ttu-id="cf44e-144">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="cf44e-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
