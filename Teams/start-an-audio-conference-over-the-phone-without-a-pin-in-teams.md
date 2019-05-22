---
title: Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, wie Sie im Teams Admin Center die Teilnahme anonymer Anrufer an einer Besprechung aktivieren oder deaktivieren. '
ms.openlocfilehash: 246eda17bd9e373a0dcecb4a75aa4f51efc8ae22
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344186"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="b8ec1-103">Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8ec1-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="b8ec1-104">Für Benutzer, die sich in eine Besprechung einwählen, kann es frustrierend sein, im Wartebereich platziert zu werden und Musik zu hören, da der Microsoft Teams-Besprechungsorganisator die Besprechung noch nicht gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="b8ec1-105">Wenn sich ein Besprechungsorganisator in die Besprechung einwählt, benötigt er zum Starten der Besprechung standardmäßig eine PIN.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="b8ec1-106">Sie können dies so einrichten, dass sich jeder in die Besprechung einwählen kann, ohne zur Eingabe einer PIN zum Starten der Besprechung aufgefordert zu werden.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="b8ec1-107">Sie können diese Einstellung für einen einzelnen Benutzer im Admin Center aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="b8ec1-108">Der Besprechungsorganisator benötigt keine PIN, wenn jemand die Besprechung über die Microsoft Teams-App gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="b8ec1-109">Eine PIN ist nur erforderlich, wenn der Besprechungsorganisator per Telefon an der Besprechung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="b8ec1-110">Die PIN für Besprechungen wird an den Audiobenutzer gesendet, wenn ihm die Lizenz für **Audiokonferenzen** zugewiesen und er für Audiokonferenzen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b8ec1-111">Weitere Informationen finden Sie unter [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) und [E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b8ec1-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="b8ec1-112">Aktivieren oder Deaktivieren der Teilnahme anonymer Anrufer an einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="b8ec1-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="b8ec1-113">![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt</span><span class="sxs-lookup"><span data-stu-id="b8ec1-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b8ec1-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="b8ec1-115">Wählen Sie einen Benutzer in der Liste aus, und klicken Sie dann oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="b8ec1-116">Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="b8ec1-117">Aktivieren oder deaktivieren Sie im Bereich **Audiokonferenz** die Option **Unauthenticated callers can be the first person in a meeting** (Nicht authentifizierte Anrufer als erste Teilnehmer an einer Besprechung zulassen).</span><span class="sxs-lookup"><span data-stu-id="b8ec1-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="b8ec1-118">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-118">Click **Save**.</span></span> 

<span data-ttu-id="b8ec1-119">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b8ec1-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="b8ec1-120">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b8ec1-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="b8ec1-121">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="b8ec1-121">What else should you know?</span></span>

- <span data-ttu-id="b8ec1-122">Wenn Sie die PIN zurücksetzen möchten, lesen Sie [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b8ec1-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="b8ec1-123">Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN aktiviert ist, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b8ec1-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="b8ec1-124">Wenn die Besprechung nicht begonnen hat (also noch keine Teilnehmer anwesend sind): Der Anrufer wird gefragt, ob er der Organisator ist. Wenn er dies bejaht, wird er aufgefordert, seine PIN einzugeben. Wenn er die PIN eingegeben hat, wird die Besprechung gestartet, und der Benutzer nimmt teil.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="b8ec1-125">Wenn die Besprechung bereits begonnen hat (also bereits Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt teil.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="b8ec1-126">Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN deaktiviert ist, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b8ec1-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="b8ec1-127">Wenn die Besprechung nicht begonnen hat (also noch keine Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="b8ec1-128">Da die Einstellung für den Organisator deaktiviert ist, beginnt die Besprechung, und der anonyme Anrufer nimmt an der Besprechung teil.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="b8ec1-129">Wenn die Besprechung bereits begonnen hat (also bereits Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt teil.</span><span class="sxs-lookup"><span data-stu-id="b8ec1-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b8ec1-130">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="b8ec1-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b8ec1-p104">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b8ec1-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b8ec1-134">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="b8ec1-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b8ec1-135">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8ec1-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b8ec1-136">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b8ec1-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b8ec1-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b8ec1-137">Related topics</span></span>

[<span data-ttu-id="b8ec1-138">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="b8ec1-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
