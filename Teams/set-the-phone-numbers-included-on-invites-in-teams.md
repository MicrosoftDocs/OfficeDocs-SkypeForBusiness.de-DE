---
title: Festlegen der in Einladungen enthaltenen Telefonnummern
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: Führen Sie die folgenden Schritte aus, um eine Standardtelefonnummer für Anrufer zu erstellen und an einer Microsoft Teams-Besprechung teilzunehmen.
ms.openlocfilehash: bd8ca4729a991582588f09e8c230e57983cd1a87
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021763"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="8a0c9-103">Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="8a0c9-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="8a0c9-104">Audiokonferenzen in Microsoft 365 und Office 365 ermöglichen es Benutzern in Ihrer Organisation, Microsoft Teams-Besprechungen zu erstellen und Benutzern dann das Einwählen in diese Besprechungen mithilfe eines Telefons zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="8a0c9-p101">Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-p101">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a0c9-107">Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="8a0c9-108">Die anfängliche Zuweisung von Telefonnummern, die in der Besprechung enthalten sind, lädt für neue Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="8a0c9-109">Die Telefonnummern, die in der Besprechungseinladung enthalten sind, werden von Benutzern, die für Audiokonferenzen aktiviert sind, durch die standardmäßige Konferenzgebühren pflichtige Telefonnummer und die Einstellungen des standardmäßigen Konferenzgebühren freien Telefonnummern-Benutzers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="8a0c9-110">Jede Einstellung gibt an, welche gebührenpflichtige und gebührenfreie Nummer in der Besprechungseinladung eines bestimmten Benutzers enthalten sein wird.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="8a0c9-111">Wie bereits erwähnt, enthält jede Besprechungseinladung eine gebührenpflichtige Nummer, eine optionale gebührenfreie Nummer und einen Link, der die vollständige Liste aller Einwahl Telefonnummern öffnet, die für die Teilnahme an einer bestimmten Besprechung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="8a0c9-112">Für einen neuen Benutzer werden die standardmäßigen Konferenzgebühren Nummern basierend auf dem Verwendungs Speicherort zugewiesen, der in der Microsoft 365-Verwaltungskonsole des Benutzers festgelegt ist, wenn der Benutzer für den Audiokonferenzdienst aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="8a0c9-113">Wenn sich in der Konferenzbrücke eine gebührenpflichtige Nummer befindet, die dem Land des Benutzers entspricht, wird diese Nummer automatisch als Standardgebühren Nummer des Benutzers zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="8a0c9-114">Wenn es keinen gibt, wird die Nummer, die als standardmäßige gebührenpflichtige Nummer der Konferenzbrücke definiert ist, als die standardmäßige gebührenpflichtige Nummer des Benutzers zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="8a0c9-115">Sobald der Benutzer für den Audiokonferenzdienst aktiviert ist, können die standardmäßigen gebührenpflichtigen und gebührenfreien Telefonnummern des Benutzers vom mandantenadministrator jederzeit von den anfänglichen Werten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="8a0c9-116">Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für Besprechungsorganisatoren oder-Benutzer</span><span class="sxs-lookup"><span data-stu-id="8a0c9-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="8a0c9-117">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="8a0c9-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="8a0c9-118">Sie müssen ein Administrator sein, um diese Änderungen vornehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-118">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="8a0c9-119">Melden Sie sich beim Microsoft Teams Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-119">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="8a0c9-120">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-120">In the left navigation, click **Users**.</span></span>

    ![Zeigt das Auswählen von Benutzern im Microsoft Teams Admin Center](media/Admin-users.png)

3. <span data-ttu-id="8a0c9-122">Klicken Sie in der Liste der verfügbaren Benutzer auf den Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-122">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="8a0c9-123">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-123">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Klicken Sie neben Audiokonferenzen auf Bearbeiten.](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="8a0c9-125">Verwenden Sie die Felder **gebührenpflichtige** Nummer oder **gebührenfreie Nummer** , um die Nummern für den Benutzer einzugeben.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-125">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8a0c9-126">Wenn Sie die Einstellungen für die Audiokonferenz eines Benutzers ändern, müssen wiederkehrende und zukünftige Microsoft Teams-Besprechungen aktualisiert und an die Teilnehmer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-126">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="8a0c9-127">Wollen Sie Windows PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="8a0c9-127">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="8a0c9-128">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8a0c9-129">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe einer zentralen Verwaltungsstelle verwalten, die Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="8a0c9-130">Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8a0c9-131">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="8a0c9-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8a0c9-132">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a0c9-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="8a0c9-133">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="8a0c9-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="8a0c9-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8a0c9-134">Related topics</span></span>

[<span data-ttu-id="8a0c9-135">Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="8a0c9-135">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="8a0c9-136">Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="8a0c9-136">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
