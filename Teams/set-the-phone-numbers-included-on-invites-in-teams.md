---
title: Festlegen des Telefons, die Zahlen enthalten auf invites in Microsoft-Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Rufen Sie die Schritte zum Erstellen einer Standardrufnummer für Anrufer teilnehmen an einer Besprechung Microsoft-Teams. '
ms.openlocfilehash: be873d6419e74027c3db9a157c82379836a7a463
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021850"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="0016a-103">Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="0016a-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="0016a-104">Audiokonferenzen in Office 365 ermöglicht Benutzern in Ihrer Organisation zum Erstellen von Microsoft-Teams, Besprechungen, und klicken Sie dann zulassen, dass Benutzer in diesen treffen mit einem Telefon einwählen.</span><span class="sxs-lookup"><span data-stu-id="0016a-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="0016a-105">In Office 365 verfügen Sie über die Möglichkeit, eine audiokonferenzbrücke von Microsoft oder einem Drittanbieter-audiokonferenzbrücke, die von einem Provider genehmigte Audiokonferenzen (ACP) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0016a-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="0016a-p102">Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0016a-p102">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0016a-108">Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="0016a-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="0016a-109">Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="0016a-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="0016a-110">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="0016a-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Zeigt das Auswählen von Benutzern im Admin Center für Microsoft Teams und Skype for Business.](media/teamsselectusers.png)

2. <span data-ttu-id="0016a-112">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0016a-112">At the top of the page, click **Edit**.</span></span>

    ![Klicken Sie im Admin Center für Microsoft Teams und Skype for Business auf „Bearbeiten“.](media/teamsedituser.png)

3. <span data-ttu-id="0016a-114">Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0016a-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Klicken Sie neben „Audiokonferenz“ auf „Bearbeiten“.](media/teamseditaudioconf.png)

4. <span data-ttu-id="0016a-116">Verwenden Sie die Felder **Gebührenpflichtige Nummer** und **Gebührenfreie Nummer**, um die Nummern für den Benutzer einzugeben.</span><span class="sxs-lookup"><span data-stu-id="0016a-116">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="0016a-117">Wenn Sie die Audiokonferenzeinstellungen eines Benutzers ändern, müssen Besprechungsserien und zukünftige Microsoft Teams-Besprechungen aktualisiert und an die Teilnehmer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0016a-117">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="0016a-118">Möchten Sie Windows PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="0016a-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="0016a-p103">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0016a-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0016a-122">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="0016a-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0016a-123">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0016a-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0016a-124">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0016a-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="0016a-125">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0016a-125">Related topics</span></span>

[<span data-ttu-id="0016a-126">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="0016a-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
