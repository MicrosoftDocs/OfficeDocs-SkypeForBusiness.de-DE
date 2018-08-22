---
title: Aktivieren von Benutzern, ihren Namen aufzuzeichnen, beim Beitritt zu einer Besprechung in Skype für Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Informationen Sie zum Aktivieren oder deaktivieren, ob die Benutzer beim Beitritt zu einer Besprechung in Skype für Business Online ihre Namen festhalten können.
ms.openlocfilehash: b920f0cfea6aa607f5bc3ea7c8a53b5668ba02da
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490725"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="3df55-103">Aktivieren von Benutzern, ihren Namen aufzuzeichnen, beim Beitritt zu einer Besprechung in Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="3df55-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="3df55-104">Wenn Sie Benutzern notieren deren Namen im Teams ermöglichen möchten, finden Sie unter [Aktivieren von Benutzern zum Aufzeichnen ihrer namens beim Beitritt zu einer Besprechung in Microsoft-Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span><span class="sxs-lookup"><span data-stu-id="3df55-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="3df55-p101">Bei der Konfiguration von Einwahlkonferenzen in Skype for Business Online erhalten Sie Telefonnummern sowie eine so genannte Einwahl- oder Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen, bei der bzw. denen sich um fest zugeordnete oder gemeinsam genutzte Telefonnummern handeln kann.</span><span class="sxs-lookup"><span data-stu-id="3df55-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="3df55-p102">Die Konferenzbrücke nimmt den Anruf eines Benutzers an, der sich mit einem Telefon in eine Besprechung einwählt. Die Konferenzbrücke nimmt den Anruf an und gibt Sprachansagen einer automatischen Telefonzentrale aus. Je nach den festgelegten Einstellungen gibt sie Benachrichtigungen wieder und fordert Anrufer auf, ihren Namen aufzuzeichnen. Zudem richtet sie die PIN-Sicherheit für die Organisatoren der Besprechung ein. Der Organisator der Besprechung erhält PINs, damit er eine Besprechung starten kann. Sie können in Ihren Einstellungen jedoch festlegen, dass zum Start einer Besprechung keine PIN erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3df55-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="3df55-111">Festlegen, ob Anrufer ihren Namen aufzeichnen sollen</span><span class="sxs-lookup"><span data-stu-id="3df55-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="3df55-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="3df55-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="3df55-113">Unter **Teilnahme an einer Besprechung auftreten**finden Sie unter das Kontrollkästchen **Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden**.</span><span class="sxs-lookup"><span data-stu-id="3df55-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="3df55-p103">**Aktivierte** Anrufer werden aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen. Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3df55-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
  - <span data-ttu-id="3df55-116">**Nicht aktivierte** Anrufer werden nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="3df55-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="3df55-117">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3df55-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3df55-118">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="3df55-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3df55-119">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) nutzen.</span><span class="sxs-lookup"><span data-stu-id="3df55-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="3df55-p104">In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3df55-p104">Windows PowerShell is all about managing users and what users are allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3df55-123">Sechs Gründe für die Verwendung von Windows PowerShell zur Verwaltung von Office 365 </span><span class="sxs-lookup"><span data-stu-id="3df55-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3df55-124">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3df55-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="3df55-p105">Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="3df55-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="3df55-127">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3df55-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3df55-128">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3df55-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3df55-129">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3df55-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="3df55-p106">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="3df55-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3df55-132">See Also</span><span class="sxs-lookup"><span data-stu-id="3df55-132">Related topics</span></span>

[<span data-ttu-id="3df55-133">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="3df55-133">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
