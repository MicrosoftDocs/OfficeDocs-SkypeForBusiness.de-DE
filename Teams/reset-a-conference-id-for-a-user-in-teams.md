---
title: Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
- seo-marvel-mar2020
description: Hier finden Sie die Schritte zum Zurücksetzen der Konferenzkennung eines Benutzers in Microsoft Teams sowie Links zu Tools, mit denen Sie Besprechungen aktualisieren und migrieren können.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662125"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="0a93d-103">Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0a93d-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="0a93d-104">Eine dynamische Konferenzkennung befindet sich unten in Besprechungseinladungen zusammen mit den Dial-in-Telefonnummern, über die sich Anrufer in die Besprechung einwählen können.</span><span class="sxs-lookup"><span data-stu-id="0a93d-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="0a93d-105">Wenn Benutzer diese Telefonnummer wählen, werden sie von der automatischen Telefonzentrale aufgefordert, diese Konferenzkennung einzugeben, damit sie an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="0a93d-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a93d-106">Konferenz-IDs werden automatisch generiert, liegen zwischen 7-9-Ziffern und werden beim Aktivieren von Audiokonferenzen für einen Benutzer eingestellt.</span><span class="sxs-lookup"><span data-stu-id="0a93d-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="0a93d-107">**Statische Konferenz-IDs werden nicht unterstützt.**</span><span class="sxs-lookup"><span data-stu-id="0a93d-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="0a93d-108">Zurücksetzen der Konferenz-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="0a93d-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="0a93d-109">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="0a93d-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0a93d-110">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="0a93d-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0a93d-111">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0a93d-111">Click **Edit**.</span></span>

3. <span data-ttu-id="0a93d-112">Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="0a93d-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="0a93d-113">Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="0a93d-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="0a93d-114">Daraufhin wird automatisch eine neue Konferenzkennung erstellt und per E-Mail an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="0a93d-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="0a93d-115">E-Mails werden standardmäßig an Benutzer gesendet. Dies kann jedoch deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0a93d-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="0a93d-116">Wenn Sie die Konferenzkennung zurückgesetzt haben, wird eine E-Mail mit der neuen Konferenzkennung an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="0a93d-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="0a93d-117">Diese e-Mail wird in vielen Fällen an die primäre e-Mail-Adresse gesendet, deren Microsoft 365-oder Office 365-Postfach.</span><span class="sxs-lookup"><span data-stu-id="0a93d-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="0a93d-118">Die E-Mail enthält die neue Konferenzkennung, die standardmäßigen Dial-in-Telefonnummern und Anweisungen zum Aktualisieren vorhandener Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="0a93d-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="0a93d-119">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="0a93d-119">What else should I know?</span></span>

- <span data-ttu-id="0a93d-120">Sie können dem Benutzer eine E-Mail mit sämtlichen Konferenzinformationen senden, unter anderem mit der Konferenzkennung und den Dial-in-Telefonnummern. Klicken Sie dazu im Abschnitt **Audiokonferenz** für den Benutzer auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).</span><span class="sxs-lookup"><span data-stu-id="0a93d-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="0a93d-121">Die PIN wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="0a93d-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="0a93d-122">Eine 7-9-stellige Konferenz-ID wird vom Teams-Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="0a93d-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="0a93d-123">Sie können deren Länge nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="0a93d-123">You can't change its length.</span></span>
    
- <span data-ttu-id="0a93d-124">Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0a93d-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="0a93d-125">Nachdem eine neue Konferenz-ID generiert wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a93d-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="0a93d-126">Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0a93d-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0a93d-127">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="0a93d-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0a93d-128">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0a93d-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0a93d-129">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0a93d-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0a93d-130">Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0a93d-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0a93d-131">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="0a93d-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0a93d-132">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a93d-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0a93d-133">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0a93d-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0a93d-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0a93d-134">Related topics</span></span>

[<span data-ttu-id="0a93d-135">Zurücksetzen der Audiokonferenz-PIN</span><span class="sxs-lookup"><span data-stu-id="0a93d-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
