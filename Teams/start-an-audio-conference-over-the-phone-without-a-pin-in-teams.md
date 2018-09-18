---
title: Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Hier erfahren Sie, wie Sie im Teams Admin Center die Teilnahme anonymer Anrufer an einer Besprechung aktivieren oder deaktivieren. '
ms.openlocfilehash: c68e3a0bd9992eb53811941113a30e9362c78227
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882999"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="17279-103">Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17279-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="17279-104">Für Benutzer, die sich in eine Besprechung einwählen, kann es frustrierend sein, im Wartebereich platziert zu werden und Musik zu hören, da der Microsoft Teams-Besprechungsorganisator die Besprechung noch nicht gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="17279-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because an organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="17279-105">Wenn sich ein Besprechungsorganisator in die Besprechung einwählt, benötigt er zum Starten der Besprechung standardmäßig eine PIN.</span><span class="sxs-lookup"><span data-stu-id="17279-105">If a meeting organizer calls into their meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="17279-106">Sie können dies so einrichten, dass sich jeder in die Besprechung einwählen kann, ohne zur Eingabe einer PIN zum Starten der Besprechung aufgefordert zu werden.</span><span class="sxs-lookup"><span data-stu-id="17279-106">You can set it up so that anyone can dial in to the meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="17279-107">Sie können diese Einstellung für einen einzelnen Benutzer im Admin Center aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="17279-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="17279-108">Der Besprechungsorganisator benötigt keine PIN, wenn jemand die Besprechung über die Microsoft Teams-App gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="17279-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business client.</span></span> <span data-ttu-id="17279-109">Eine PIN ist nur erforderlich, wenn der Besprechungsorganisator per Telefon an der Besprechung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="17279-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="17279-110">Die PIN für Besprechungen wird an den Audiobenutzer gesendet, wenn ihm die Lizenz für **Audiokonferenzen** zugewiesen und er für Audiokonferenzen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="17279-110">The PIN for meetings is sent to the dial-in user when they are assigned the **Skype for Business PSTN Conferencing** license or are enabled for dial-in conferencing.</span></span> <span data-ttu-id="17279-111">Weitere Informationen finden Sie unter [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) und [E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="17279-111">See,[Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and[Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="17279-112">Aktivieren oder Deaktivieren der Teilnahme anonymer Anrufer an einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="17279-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="17279-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="17279-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="17279-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="17279-114">In the left navigation bar, click **Users**.</span></span> 

2. <span data-ttu-id="17279-115">Wählen Sie einen Benutzer in der Liste aus, und klicken Sie dann oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="17279-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="17279-116">Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="17279-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="17279-117">Aktivieren oder deaktivieren Sie im Bereich **Audiokonferenz** die Option **Unauthenticated callers can be the first person in a meeting** (Nicht authentifizierte Anrufer als erste Teilnehmer an einer Besprechung zulassen).</span><span class="sxs-lookup"><span data-stu-id="17279-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="17279-118">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="17279-118">Click **Save**.</span></span> 

<span data-ttu-id="17279-119">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="17279-119">\*\*\*\* Using Windows PowerShell</span></span>
  
<span data-ttu-id="17279-120">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="17279-120">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="17279-121">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="17279-121">What else should you know?</span></span>

- <span data-ttu-id="17279-122">Wenn Sie die PIN zurücksetzen möchten, lesen Sie [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="17279-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="17279-123">Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN aktiviert ist, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="17279-123">If anonymous access or not requiring a PIN to start a meeting is enabled:</span></span>
    
  - <span data-ttu-id="17279-124">Wenn die Besprechung nicht begonnen hat (also noch keine Teilnehmer anwesend sind): Der Anrufer wird gefragt, ob er der Organisator ist. Wenn er dies bejaht, wird er aufgefordert, seine PIN einzugeben. Wenn er die PIN eingegeben hat, wird die Besprechung gestartet, und der Benutzer nimmt teil.</span><span class="sxs-lookup"><span data-stu-id="17279-124">A caller will be prompted if he's the organizer, if he says yes, he'll be prompted for his PIN after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="17279-125">Wenn die Besprechung bereits begonnen hat (also bereits Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt teil.</span><span class="sxs-lookup"><span data-stu-id="17279-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="17279-126">Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN deaktiviert ist, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="17279-126">If anonymous access or not requiring a PIN to start a meeting is disabled:</span></span>
    
  - <span data-ttu-id="17279-127">Wenn die Besprechung nicht begonnen hat (also noch keine Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben.</span><span class="sxs-lookup"><span data-stu-id="17279-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="17279-128">Da die Einstellung für den Organisator deaktiviert ist, beginnt die Besprechung, und der anonyme Anrufer nimmt an der Besprechung teil.</span><span class="sxs-lookup"><span data-stu-id="17279-128">Because the setting of the organizer is set to off, the meeting will start and the anonymouscallers will join the meeting.</span></span>
    
  - <span data-ttu-id="17279-129">Wenn die Besprechung bereits begonnen hat (also bereits Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt teil.</span><span class="sxs-lookup"><span data-stu-id="17279-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="17279-130">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="17279-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="17279-p104">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17279-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="17279-134">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="17279-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="17279-135">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17279-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="17279-136">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="17279-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="17279-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="17279-137">Related topics</span></span>

[<span data-ttu-id="17279-138">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="17279-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
