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
ms.openlocfilehash: bed015c92e197c1ee2dc1b48e495eee98445e3f0
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "25019044"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="1558c-103">Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1558c-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="1558c-104">Eine dynamische Konferenz-ID ist enthalten am unteren Rand Besprechungsanfragen zusammen mit der Zugriffsnummer für Einwahl Telefonnummern, die von Anrufern zu einer Besprechung Anrufen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1558c-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="1558c-105">Wenn der Benutzer die Telefonnummer wählt, wird die automatische Telefonzentrale für die Besprechung bitten Sie den Anrufer an diese Konferenz-ID eingeben, damit sie an der Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="1558c-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1558c-106">Wenn Ihr Konferenzanbieter Microsoft ist, sind die Konferenz-IDs Ihrer Benutzer standardmäßig auf "Nur dynamisch" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="1558c-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="1558c-107">Leider besteht keine Möglichkeit, ändern es statisch sein, wie dies nun ist nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1558c-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="1558c-108">Konferenz-IDs werden für Benutzer mit Microsoft-Teams für Audiokonferenzen nur automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1558c-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="1558c-109">Zurücksetzen der Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="1558c-109">Resetting the conference ID for a user</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="1558c-111">Verwenden des Microsoft-Teams und Skype for Business-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="1558c-111">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="1558c-112">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="1558c-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="1558c-113">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1558c-113">Click **Edit**.</span></span>

3. <span data-ttu-id="1558c-114">Klicken Sie unter **Audiokonferenzen** auf **Konferenz-ID zurückgesetzt**.</span><span class="sxs-lookup"><span data-stu-id="1558c-114">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="1558c-115">Klicken Sie auf **Zurücksetzen**, klicken Sie im Fenster **Konferenz-ID zurückgesetzt** .</span><span class="sxs-lookup"><span data-stu-id="1558c-115">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="1558c-116">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="1558c-116">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="1558c-117">Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="1558c-117">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="1558c-118">Nachdem Sie die Konferenz-ID zurücksetzen, wird eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="1558c-118">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="1558c-119">Diese e-Mail wird an die primäre e-Mail-Adresse in vielen Fällen ihre Office 365-Postfach gesendet.</span><span class="sxs-lookup"><span data-stu-id="1558c-119">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="1558c-120">Die e-Mail enthält die neue Konferenz-ID sowie die Zugriffsnummer für Einwahl Telefonnummern für Standard und Informationen zum Aktualisieren vorhandener Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="1558c-120">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="1558c-121">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="1558c-121">What else should I know?</span></span>

- <span data-ttu-id="1558c-122">Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und die Zugriffsnummer für Einwahl Telefonnummern durch Klicken auf **Konferenz Informationen in e-Mail-Nachricht senden** , für den Benutzer im Abschnitt **Audiokonferenzen** enthält.</span><span class="sxs-lookup"><span data-stu-id="1558c-122">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="1558c-123">Die PIN wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="1558c-123">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="1558c-124">Enthält eine Konferenz-ID 7 Ziffern, und deren Länge kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1558c-124">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="1558c-125">Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1558c-125">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="1558c-126">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="1558c-126">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="1558c-127">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="1558c-127">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1558c-128">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="1558c-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="1558c-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1558c-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1558c-132">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="1558c-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1558c-133">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1558c-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="1558c-134">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="1558c-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="1558c-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1558c-135">Related topics</span></span>

[<span data-ttu-id="1558c-136">Die Audiokonferenz PIN zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="1558c-136">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
