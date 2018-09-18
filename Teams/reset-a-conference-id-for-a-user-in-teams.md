---
title: Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Hier finden Sie die Schritte zum Zurücksetzen der Konferenzkennung eines Benutzers in Microsoft Teams sowie Links zu Tools, mit denen Sie Besprechungen aktualisieren und migrieren können. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887852"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="22c4b-103">Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22c4b-103">For information about resetting conference ID in Microsoft Teams, see Reset a conference ID for a user in Microsoft Teams.</span></span>

<span data-ttu-id="22c4b-104">Eine dynamische Konferenzkennung befindet sich unten in Besprechungseinladungen zusammen mit den Dial-in-Telefonnummern, über die sich Anrufer in die Besprechung einwählen können.</span><span class="sxs-lookup"><span data-stu-id="22c4b-104">This conference ID is included at the bottom of Skype for Business Online meeting invitations along with the dial-in phone numbers that can be used by callers to call into a meeting.</span></span> <span data-ttu-id="22c4b-105">Wenn Benutzer diese Telefonnummer wählen, werden sie von der automatischen Telefonzentrale aufgefordert, diese Konferenzkennung einzugeben, damit sie an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="22c4b-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to input this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="22c4b-106">Wenn Microsoft Ihr Konferenzanbieter ist, sind die Konferenzkennungen der Benutzer standardmäßig auf „Dynamic Only“ (Nur dynamisch) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="22c4b-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="22c4b-107">Leider gibt es keine Möglichkeit, die Konferenzkennung in eine statische Kennung zu ändern, da dies zurzeit nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="22c4b-107">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="22c4b-108">Konferenzkennungen werden nur für Microsoft Teams-Benutzer, die für Audiokonferenzen aktiviert sind, automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="22c4b-108">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="22c4b-109">Zurücksetzen der Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="22c4b-109">Resetting the meeting conference ID for a user</span></span>

1. <span data-ttu-id="22c4b-110">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="22c4b-110">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="22c4b-111">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="22c4b-111">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="22c4b-112">Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="22c4b-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="22c4b-113">Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="22c4b-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="22c4b-114">Daraufhin wird automatisch eine neue Konferenzkennung erstellt und per E-Mail an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="22c4b-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="22c4b-115">E-Mails werden standardmäßig an Benutzer gesendet. Dies kann jedoch deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="22c4b-115">By default, emails are sent to users, but it can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="22c4b-116">Wenn Sie die Konferenzkennung zurückgesetzt haben, wird eine E-Mail mit der neuen Konferenzkennung an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="22c4b-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="22c4b-117">Diese E-Mail wird an die primäre E-Mail-Adresse gesendet, das heißt in vielen Fällen an das Office 365-Postfach des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="22c4b-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="22c4b-118">Die E-Mail enthält die neue Konferenzkennung, die standardmäßigen Dial-in-Telefonnummern und Anweisungen zum Aktualisieren vorhandener Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="22c4b-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="22c4b-119">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="22c4b-119">What else should I know?</span></span>

- <span data-ttu-id="22c4b-120">Sie können dem Benutzer eine E-Mail mit sämtlichen Konferenzinformationen senden, unter anderem mit der Konferenzkennung und den Dial-in-Telefonnummern. Klicken Sie dazu im Abschnitt **Audiokonferenz** für den Benutzer auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).</span><span class="sxs-lookup"><span data-stu-id="22c4b-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span> <span data-ttu-id="22c4b-121">Die PIN wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="22c4b-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="22c4b-122">Eine Konferenzkennung umfasst sieben Ziffern. Die Länge kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="22c4b-122">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="22c4b-123">Nach dem Zurücksetzen wird die neue Konferenzkennung unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="22c4b-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="22c4b-124">Wenn eine neue Konferenzkennung erstellt wurde, können Anrufer die alte Konferenzkennung nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="22c4b-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="22c4b-125">Benachrichtigen Sie die Benutzer, dass sie vorhandene Besprechungseinladungen neu planen müssen, um sicherzustellen, dass die neue Konferenzkennung zu den Einladungen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="22c4b-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="22c4b-126">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="22c4b-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="22c4b-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="22c4b-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="22c4b-130">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="22c4b-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="22c4b-131">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22c4b-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="22c4b-132">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="22c4b-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="22c4b-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="22c4b-133">Related topics</span></span>

<span data-ttu-id="22c4b-134">[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="22c4b-134">[](reset-the-audio-conferencing-pin-in-teams.md)Reset the Audio Conferencing PIN for a user</span></span>
