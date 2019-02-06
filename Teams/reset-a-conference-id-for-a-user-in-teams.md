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
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie die Schritte zum Zurücksetzen der Konferenzkennung eines Benutzers in Microsoft Teams sowie Links zu Tools, mit denen Sie Besprechungen aktualisieren und migrieren können. '
ms.openlocfilehash: a33ccf71d683fc7ae55011f502eda5182ed40268
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754705"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="40c3d-103">Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40c3d-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="40c3d-104">Eine dynamische Konferenzkennung befindet sich unten in Besprechungseinladungen zusammen mit den Dial-in-Telefonnummern, über die sich Anrufer in die Besprechung einwählen können.</span><span class="sxs-lookup"><span data-stu-id="40c3d-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="40c3d-105">Wenn Benutzer diese Telefonnummer wählen, werden sie von der automatischen Telefonzentrale aufgefordert, diese Konferenzkennung einzugeben, damit sie an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="40c3d-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40c3d-106">Wenn Microsoft Ihr Konferenzanbieter ist, sind die Konferenzkennungen der Benutzer standardmäßig auf „Dynamic Only“ (Nur dynamisch) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="40c3d-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="40c3d-107">Leider gibt es keine Möglichkeit, die Konferenzkennung in eine statische Kennung zu ändern, da dies zurzeit nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="40c3d-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="40c3d-108">Konferenzkennungen werden nur für Microsoft Teams-Benutzer, die für Audiokonferenzen aktiviert sind, automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="40c3d-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="40c3d-109">Zurücksetzen der Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="40c3d-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="40c3d-110">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="40c3d-110">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="40c3d-111">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="40c3d-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="40c3d-112">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="40c3d-112">Click **Edit**.</span></span>

3. <span data-ttu-id="40c3d-113">Klicken Sie unter **Audiokonferenzen** auf **Konferenz-ID zurückgesetzt**.</span><span class="sxs-lookup"><span data-stu-id="40c3d-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="40c3d-114">Klicken Sie auf **Zurücksetzen**, klicken Sie im Fenster **Konferenz-ID zurückgesetzt** .</span><span class="sxs-lookup"><span data-stu-id="40c3d-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="40c3d-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="40c3d-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="40c3d-116">Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="40c3d-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="40c3d-117">Nachdem Sie die Konferenz-ID zurücksetzen, wird eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="40c3d-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="40c3d-118">Diese e-Mail wird an die primäre e-Mail-Adresse in vielen Fällen ihre Office 365-Postfach gesendet.</span><span class="sxs-lookup"><span data-stu-id="40c3d-118">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="40c3d-119">Die e-Mail enthält die neue Konferenz-ID sowie die Zugriffsnummer für Einwahl Telefonnummern für Standard und Informationen zum Aktualisieren vorhandener Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="40c3d-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="40c3d-120">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="40c3d-120">What else should I know?</span></span>

- <span data-ttu-id="40c3d-121">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und die Zugriffsnummer für Einwahl Telefonnummern durch Klicken auf **Konferenz Informationen in e-Mail-Nachricht senden** , für den Benutzer im Abschnitt **Audiokonferenzen** enthält.</span><span class="sxs-lookup"><span data-stu-id="40c3d-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="40c3d-122">Die PIN wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="40c3d-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="40c3d-123">Enthält eine Konferenz-ID 7 Ziffern, und deren Länge kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="40c3d-123">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="40c3d-124">Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="40c3d-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="40c3d-125">Nachdem eine neue Konferenz-ID generiert wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="40c3d-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="40c3d-126">Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="40c3d-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="40c3d-127">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="40c3d-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="40c3d-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="40c3d-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="40c3d-131">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="40c3d-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="40c3d-132">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40c3d-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="40c3d-133">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="40c3d-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="40c3d-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="40c3d-134">Related topics</span></span>

[<span data-ttu-id="40c3d-135">Die Audiokonferenz PIN zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="40c3d-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
