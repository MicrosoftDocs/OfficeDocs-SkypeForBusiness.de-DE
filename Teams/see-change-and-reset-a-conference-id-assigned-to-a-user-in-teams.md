---
title: Anzeigen, ändern und Zurücksetzen der Konferenz-ID eines Benutzers
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einem Benutzer in Microsoft Teams eine Konferenz-ID zuweisen und was die Konferenz-IDs-Parameter sein sollten.
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691151"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="4ad08-103">Anzeigen und Zurücksetzen einer Konferenzkennung, die einem Benutzer zugewiesen ist, in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ad08-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="4ad08-104">Eine Konferenz-ID wird einem Microsoft Teams-Benutzer automatisch zugewiesen, wenn Sie in Microsoft 365 oder Office 365 für Audiokonferenzen eingerichtet sind, und Microsoft als Anbieter von Audiokonferenzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ad08-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="4ad08-105">Die zugewiesene Konferenzkennung wird in der Besprechungseinladung gesendet, wenn die Besprechung geplant wird.</span><span class="sxs-lookup"><span data-stu-id="4ad08-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="4ad08-106">Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4ad08-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="4ad08-107">Obwohl Konferenzkennungen automatisch generiert und Benutzern zugewiesen werden, kann es vorkommen, dass Benutzer diese Nummer nicht verwenden möchten und Sie daher eine bestimmte Nummer festlegen müssen. Es ist auch möglich, dass Benutzer ihre Konferenzkennung vergessen oder verloren haben.</span><span class="sxs-lookup"><span data-stu-id="4ad08-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="4ad08-108">Sie können die Konferenzkennung im Microsoft Teams Admin Center oder mit Windows PowerShell anzeigen, ändern und zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="4ad08-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="4ad08-109">Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält.</span><span class="sxs-lookup"><span data-stu-id="4ad08-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="4ad08-110">Weitere Informationen zum Zurücksetzen der PIN eines Konferenz Organisators finden Sie unter [Zurücksetzen einer Konferenz-ID für einen Benutzer in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="4ad08-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="4ad08-111">Anzeigen und Zurücksetzen der Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="4ad08-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="4ad08-112">So zeigen Sie die Konferenzkennung an</span><span class="sxs-lookup"><span data-stu-id="4ad08-112">To view the conference ID</span></span>

<span data-ttu-id="4ad08-113">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="4ad08-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ad08-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4ad08-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4ad08-115">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4ad08-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4ad08-116">Suchen Sie unter **Audiokonferenz** in **Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="4ad08-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4ad08-117">Sie können dem Benutzer eine E-Mail mit sämtlichen Konferenzinformationen senden, unter anderem mit der Konferenzkennung und den Audiotelefonnummern. Klicken Sie dazu auf den Link **Send conference info in email** (Konferenzinformationen per E-Mail senden).</span><span class="sxs-lookup"><span data-stu-id="4ad08-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="4ad08-118">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4ad08-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4ad08-119">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4ad08-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="4ad08-120">So setzen Sie die Konferenzkennung zurück</span><span class="sxs-lookup"><span data-stu-id="4ad08-120">To reset the conference ID</span></span>

<span data-ttu-id="4ad08-121">Sie können eine Konferenzkennung für einen Benutzer zurücksetzen, beispielsweise wenn der Benutzer sie vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="4ad08-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="4ad08-122">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="4ad08-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4ad08-123">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4ad08-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4ad08-124">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4ad08-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4ad08-125">Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4ad08-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="4ad08-126">Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4ad08-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="4ad08-127">Daraufhin wird automatisch eine neue Konferenzkennung erstellt und per E-Mail an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="4ad08-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="4ad08-128">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4ad08-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4ad08-129">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4ad08-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="4ad08-130">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="4ad08-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="4ad08-131">Wenn eine neue Konferenzkennung erstellt oder eine Konferenzkennung zurückgesetzt wurde, können Anrufer die alte Konferenzkennung nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ad08-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4ad08-132">Benachrichtigen Sie die Benutzer, dass sie vorhandene Besprechungseinladungen neu planen müssen, um sicherzustellen, dass die neue Konferenzkennung zu den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4ad08-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="4ad08-133">Die Länge der Konferenzkennung muss der Ziffernanzahl entsprechen, die in der Audiokonferenzbrücke festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4ad08-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="4ad08-134">Konferenzkennungen dürfen keine Buchstaben und Sonderzeichen, sondern nur Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4ad08-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4ad08-135">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="4ad08-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4ad08-136">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4ad08-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4ad08-137">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe einer zentralen Verwaltungsstelle verwalten, die Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4ad08-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4ad08-138">Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4ad08-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4ad08-139">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="4ad08-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4ad08-140">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ad08-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4ad08-141">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4ad08-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4ad08-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4ad08-142">Related topics</span></span>

[<span data-ttu-id="4ad08-143">Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="4ad08-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
