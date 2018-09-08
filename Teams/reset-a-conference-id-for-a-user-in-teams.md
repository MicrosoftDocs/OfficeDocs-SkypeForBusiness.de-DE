---
title: Zurücksetzen einer Konferenz-ID für einen Benutzer in Microsoft-Teams
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
description: 'Hier erfahren Sie die Schritte zum eines Benutzers Zurücksetzen des meeting-Konferenz-ID in der Microsoft-Teams sowie Get links auf meeting Update und Migration Tools. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887852"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="d251c-103">Zurücksetzen einer Konferenz-ID für einen Benutzer in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="d251c-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="d251c-104">Eine dynamische Konferenz-ID ist enthalten am unteren Rand Besprechungsanfragen zusammen mit der Zugriffsnummer für Einwahl Telefonnummern, die von Anrufern zu einer Besprechung Anrufen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d251c-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="d251c-105">Wenn der Benutzer die Telefonnummer wählt, wird die automatische Telefonzentrale für die Besprechung bitten Sie den Anrufer an diese Konferenz-ID eingeben, damit sie an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="d251c-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d251c-106">Wenn Ihr Konferenzanbieter Microsoft ist, sind die Konferenz-IDs Ihrer Benutzer standardmäßig auf "Nur dynamisch" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="d251c-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="d251c-107">Leider besteht keine Möglichkeit, ändern es statisch sein, wie dies nun ist nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d251c-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="d251c-108">Konferenz-IDs werden für Benutzer mit Microsoft-Teams für Audiokonferenzen nur automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d251c-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="d251c-109">Zurücksetzen der Konferenz-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d251c-109">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="d251c-110">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="d251c-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d251c-111">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d251c-111">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="d251c-112">Klicken Sie unter **Audiokonferenzen** auf **Konferenz-ID zurückgesetzt**.</span><span class="sxs-lookup"><span data-stu-id="d251c-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="d251c-113">Klicken Sie auf **Zurücksetzen**, klicken Sie im Fenster **Konferenz-ID zurückgesetzt** .</span><span class="sxs-lookup"><span data-stu-id="d251c-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="d251c-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="d251c-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="d251c-115">Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d251c-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="d251c-116">Nachdem Sie die Konferenz-ID zurücksetzen, wird eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="d251c-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="d251c-117">Diese e-Mail wird an die primäre e-Mail-Adresse in vielen Fällen ihre Office 365-Postfach gesendet.</span><span class="sxs-lookup"><span data-stu-id="d251c-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="d251c-118">Die e-Mail enthält die neue Konferenz-ID sowie die Zugriffsnummer für Einwahl Telefonnummern für Standard und Informationen zum Aktualisieren vorhandener Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="d251c-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="d251c-119">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="d251c-119">What else should I know?</span></span>

- <span data-ttu-id="d251c-120">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und die Zugriffsnummer für Einwahl Telefonnummern durch Klicken auf **Konferenz Informationen in e-Mail-Nachricht senden** , für den Benutzer im Abschnitt **Audiokonferenzen** enthält.</span><span class="sxs-lookup"><span data-stu-id="d251c-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="d251c-121">Die PIN wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="d251c-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="d251c-122">Enthält eine Konferenz-ID 7 Ziffern, und deren Länge kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d251c-122">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="d251c-123">Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d251c-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="d251c-124">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="d251c-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="d251c-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="d251c-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d251c-126">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="d251c-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d251c-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d251c-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d251c-130">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="d251c-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d251c-131">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d251c-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d251c-132">Weitere Informationen zu Windows PowerShell finden Sie in der [Referenz zu Microsoft-Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d251c-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d251c-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d251c-133">Related topics</span></span>

[<span data-ttu-id="d251c-134">Die Audiokonferenz PIN zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="d251c-134">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
