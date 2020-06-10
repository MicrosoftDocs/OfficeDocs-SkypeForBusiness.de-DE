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
ms.openlocfilehash: fbda2d65868d9f4082ae7b3ee835d0560c609e11
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666197"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="8970f-103">Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8970f-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="8970f-104">Eine dynamische Konferenzkennung befindet sich unten in Besprechungseinladungen zusammen mit den Dial-in-Telefonnummern, über die sich Anrufer in die Besprechung einwählen können.</span><span class="sxs-lookup"><span data-stu-id="8970f-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="8970f-105">Wenn Benutzer diese Telefonnummer wählen, werden sie von der automatischen Telefonzentrale aufgefordert, diese Konferenzkennung einzugeben, damit sie an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="8970f-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8970f-106">Wenn Microsoft Ihr Konferenzanbieter ist, sind die Konferenzkennungen der Benutzer standardmäßig auf „Dynamic Only“ (Nur dynamisch) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8970f-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="8970f-107">Leider gibt es keine Möglichkeit, die Konferenzkennung in eine statische Kennung zu ändern, da dies zurzeit nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="8970f-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="8970f-108">Konferenzkennungen werden nur für Microsoft Teams-Benutzer, die für Audiokonferenzen aktiviert sind, automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8970f-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="8970f-109">Zurücksetzen der Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="8970f-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="8970f-110">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="8970f-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8970f-111">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="8970f-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="8970f-112">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8970f-112">Click **Edit**.</span></span>

3. <span data-ttu-id="8970f-113">Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="8970f-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="8970f-114">Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="8970f-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="8970f-115">Eine Konferenz-ID wird automatisch erstellt und eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="8970f-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="8970f-116">Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8970f-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="8970f-117">Nachdem Sie die Konferenz-ID zurückgesetzt haben, wird eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="8970f-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="8970f-118">Diese e-Mail wird in vielen Fällen an die primäre e-Mail-Adresse gesendet, deren Microsoft 365-oder Office 365-Postfach.</span><span class="sxs-lookup"><span data-stu-id="8970f-118">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="8970f-119">Die e-Mail enthält die neue Konferenz-ID, die Standard-Einwahl Telefonnummer (n) und Anweisungen zum Aktualisieren vorhandener Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="8970f-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="8970f-120">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="8970f-120">What else should I know?</span></span>

- <span data-ttu-id="8970f-121">Sie können alle Konferenz Informationen an den Benutzer in einer e-Mail-Nachricht senden, die die Konferenz-ID und Einwahlnummern enthält, indem Sie im Abschnitt **Audiokonferenzen** in e-Mail für den Benutzer auf **Konferenz Informationen senden** klicken.</span><span class="sxs-lookup"><span data-stu-id="8970f-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="8970f-122">Die PIN wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="8970f-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="8970f-123">Eine Konferenz-ID enthält 8 Ziffern, und Sie können deren Länge nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="8970f-123">A conference ID will contain 8 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="8970f-124">Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8970f-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="8970f-125">Nachdem eine neue Konferenz-ID generiert wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="8970f-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="8970f-126">Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8970f-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8970f-127">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="8970f-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="8970f-128">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8970f-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8970f-129">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8970f-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="8970f-130">Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8970f-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8970f-131">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="8970f-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8970f-132">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8970f-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="8970f-133">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="8970f-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="8970f-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8970f-134">Related topics</span></span>

[<span data-ttu-id="8970f-135">Zurücksetzen der Audiokonferenz-PIN</span><span class="sxs-lookup"><span data-stu-id="8970f-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
