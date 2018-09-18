---
title: Anzeigen, Ändern und Zurücksetzen einer Konferenzkennung, die einem Benutzer zugewiesen ist, in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Hier erfahren Sie, wie Sie einem Benutzer in Microsoft Teams eine Konferenzkennung zuweisen und welche Parameter Sie für die Konferenzkennung verwenden sollten. '
ms.openlocfilehash: d0ee177fbbe286cc68c45e1c41f391b52c44291e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892033"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="d0f15-103">Anzeigen und Zurücksetzen einer Konferenzkennung, die einem Benutzer zugewiesen ist, in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0f15-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

<span data-ttu-id="d0f15-104">Eine Konferenzkennung wird Microsoft Teams-Benutzern automatisch zugewiesen, wenn sie für Audiokonferenzen in Office 365 eingerichtet werden und Microsoft als Audiokonferenzanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0f15-104">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="d0f15-105">Die zugewiesene Konferenzkennung wird in der Besprechungseinladung gesendet, wenn die Besprechung geplant wird.</span><span class="sxs-lookup"><span data-stu-id="d0f15-105">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="d0f15-106">Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d0f15-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="d0f15-107">Obwohl Konferenzkennungen automatisch generiert und Benutzern zugewiesen werden, kann es vorkommen, dass Benutzer diese Nummer nicht verwenden möchten und Sie daher eine bestimmte Nummer festlegen müssen. Es ist auch möglich, dass Benutzer ihre Konferenzkennung vergessen oder verloren haben.</span><span class="sxs-lookup"><span data-stu-id="d0f15-107">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="d0f15-108">Sie können die Konferenzkennung im Microsoft Teams Admin Center oder mit Windows PowerShell anzeigen, ändern und zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="d0f15-108">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="d0f15-109">Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält.</span><span class="sxs-lookup"><span data-stu-id="d0f15-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="d0f15-110">Weitere Informationen zum Zurücksetzen einer Konferenz-Organisator-PIN, [finden Sie hier](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d0f15-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="d0f15-111">Anzeigen und Zurücksetzen der Konferenz-IDs</span><span class="sxs-lookup"><span data-stu-id="d0f15-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="d0f15-112">So zeigen Sie die Konferenzkennung an</span><span class="sxs-lookup"><span data-stu-id="d0f15-112">To reset the meeting conference ID</span></span>

<span data-ttu-id="d0f15-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="d0f15-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="d0f15-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="d0f15-114">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="d0f15-115">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d0f15-115">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="d0f15-116">Suchen Sie unter **Audiokonferenz** in **Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="d0f15-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d0f15-117">Sie können dem Benutzer eine E-Mail mit sämtlichen Konferenzinformationen senden, unter anderem mit der Konferenzkennung und den Audiotelefonnummern. Klicken Sie dazu auf den Link **Send conference info in email** (Konferenzinformationen per E-Mail senden).</span><span class="sxs-lookup"><span data-stu-id="d0f15-117">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>
  
<span data-ttu-id="d0f15-118">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d0f15-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="d0f15-119">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d0f15-119">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="d0f15-120">So setzen Sie die Konferenzkennung zurück</span><span class="sxs-lookup"><span data-stu-id="d0f15-120">To reset the meeting conference ID</span></span>

<span data-ttu-id="d0f15-121">Sie können eine Konferenzkennung für einen Benutzer zurücksetzen, beispielsweise wenn der Benutzer sie vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="d0f15-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="d0f15-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="d0f15-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="d0f15-123">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="d0f15-123">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="d0f15-124">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d0f15-124">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="d0f15-125">Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="d0f15-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="d0f15-126">Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="d0f15-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="d0f15-127">Daraufhin wird automatisch eine neue Konferenzkennung erstellt und per E-Mail an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="d0f15-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="d0f15-128">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d0f15-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="d0f15-129">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d0f15-129">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="d0f15-130">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="d0f15-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="d0f15-131">Wenn eine neue Konferenzkennung erstellt oder eine Konferenzkennung zurückgesetzt wurde, können Anrufer die alte Konferenzkennung nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0f15-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="d0f15-132">Benachrichtigen Sie die Benutzer, dass sie vorhandene Besprechungseinladungen neu planen müssen, um sicherzustellen, dass die neue Konferenzkennung zu den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d0f15-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="d0f15-133">Die Länge der Konferenzkennung muss der Ziffernanzahl entsprechen, die in der Audiokonferenzbrücke festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d0f15-133">The conference ID must meet the length in digits set on the dial-in conferencing bridge.</span></span> <span data-ttu-id="d0f15-134">Konferenzkennungen dürfen keine Buchstaben und Sonderzeichen, sondern nur Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d0f15-134">You can't use Alphabetic and special characters in conference IDs only numbers can be used.</span></span>
    
- <span data-ttu-id="d0f15-135">Die Konferenzkennung für alle Audiokonferenzbenutzer besteht standardmäßig aus sieben Ziffern. Die Anzahl der Ziffern kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d0f15-135">The conference ID for all of your dial-in conferencing users will be 7 digits by default. And the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d0f15-136">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="d0f15-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d0f15-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d0f15-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d0f15-140">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="d0f15-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d0f15-141">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0f15-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d0f15-142">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d0f15-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d0f15-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d0f15-143">Related topics</span></span>

[<span data-ttu-id="d0f15-144">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="d0f15-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

