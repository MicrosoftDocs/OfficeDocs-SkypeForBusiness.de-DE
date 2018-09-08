---
title: Beginnen einer Audio-Konferenz über das Telefon ohne PIN in Microsoft-Teams
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
description: 'Informationen Sie zum Aktivieren oder Deaktivieren der anonyme Anrufern aus teilnehmen an einer Besprechung über das Teams Administrationscenter. '
ms.openlocfilehash: c68e3a0bd9992eb53811941113a30e9362c78227
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882999"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="0a53f-103">Beginnen einer Audio-Konferenz über das Telefon ohne PIN in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="0a53f-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="0a53f-104">Es kann für Benutzer frustrierend sein, die sich in in eine Besprechung einwählen gehalten werden, in der Besprechung Wartebereich Musik hören, weil der Organisator der Besprechung Microsoft-Teams, die Besprechung noch nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="0a53f-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="0a53f-105">Wenn Organisator einer Besprechung die Besprechung standardmäßig in Aufrufe ist eine PIN erforderlich, um eine Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0a53f-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="0a53f-106">Sie können es einrichten, damit alle Benutzer an einer Besprechung einwählen kann und keine Aufforderung des Benutzers für eine PIN, um die Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0a53f-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="0a53f-107">Sie können mithilfe der Verwaltungskonsole zum Aktivieren oder deaktivieren diese Einstellung für einen einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0a53f-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="0a53f-108">Eine PIN ist nicht für den Organisator der Besprechung erforderlich, wenn eine Person die Besprechung aus der Microsoft-Teams app gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="0a53f-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="0a53f-109">Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="0a53f-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="0a53f-110">Die PIN für Besprechungen wird an den audio-Benutzer gesendet, die **Audiokonferenz** Lizenz zugewiesen werden und für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="0a53f-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="0a53f-111">Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) und [E-Mails, die Benutzern beim Ändern ihrer Einstellungen für die Audiokonferenz automatisch gesendet werden](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0a53f-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="0a53f-112">Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="0a53f-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="0a53f-113">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="0a53f-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="0a53f-114">Klicken Sie im linken Navigationsbereich auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="0a53f-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="0a53f-115">Wählen Sie einen Benutzer in der Liste aus, und klicken Sie dann auf am oberen Rand der Seite **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="0a53f-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="0a53f-116">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0a53f-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="0a53f-117">Klicken Sie im Bereich **Audiokonferenzen** aktivieren Sie oder deaktivieren Sie **nicht authentifizierter Anrufer die erste Person in einer Besprechung werden können**.</span><span class="sxs-lookup"><span data-stu-id="0a53f-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="0a53f-118">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0a53f-118">Click **Save**.</span></span> 

<span data-ttu-id="0a53f-119">**Mithilfe von Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="0a53f-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="0a53f-120">Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="0a53f-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="0a53f-121">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="0a53f-121">What else should you know?</span></span>

- <span data-ttu-id="0a53f-122">Wenn Sie die PIN zurücksetzen möchten, finden Sie unter [Audio Conferencing PIN zurücksetzen](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0a53f-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="0a53f-123">Wenn anonymer Zugriff oder keine erfordern eine PIN an eine Besprechung starten aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="0a53f-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="0a53f-124">Wenn die Besprechung noch nicht gestartet (es ist keine Empfänger in der Besprechung noch): ein Anrufer aufgefordert werden, wenn er der Organisator ist; Wenn er Ja angezeigt wird, wird er für seine PIN aufgefordert, und nachdem er die PIN eingibt, die Besprechung wird gestartet, und der Benutzer wird an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="0a53f-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="0a53f-125">Wenn die Besprechung bereits gestartet (eine andere Person ist bereits in der Besprechung): ein Anrufer nicht aufgefordert werden, wenn er der Organisator ist und er nie für die PIN aufgefordert; die Besprechung wurde bereits gestartet, und der Anrufer wird verknüpfen, um.</span><span class="sxs-lookup"><span data-stu-id="0a53f-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="0a53f-126">Wenn anonymer Zugriff oder keine erfordern eine PIN an eine Besprechung starten deaktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="0a53f-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="0a53f-127">Wenn die Besprechung noch nicht gestartet (es ist keine Empfänger in der Besprechung noch): ein Anrufer nicht aufgefordert, wenn er der Organisator ist und er nie für die PIN aufgefordert werden werden.</span><span class="sxs-lookup"><span data-stu-id="0a53f-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="0a53f-128">Da die Einstellung der Organisator der OFF festgelegt ist, die Besprechung wird gestartet, und anonyme Anrufer werden an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="0a53f-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="0a53f-129">Wenn die Besprechung bereits gestartet (eine andere Person ist bereits in der Besprechung): ein Anrufer nicht aufgefordert, wenn er der Organisator ist und er nie für die PIN aufgefordert; die Besprechung bereits gestartet, und der Anrufer wird verknüpfen, um.</span><span class="sxs-lookup"><span data-stu-id="0a53f-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0a53f-130">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="0a53f-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0a53f-p104">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0a53f-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0a53f-134">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="0a53f-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0a53f-135">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a53f-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0a53f-136">Weitere Informationen zu Windows PowerShell finden Sie in der [Referenz zu Microsoft-Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="0a53f-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0a53f-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0a53f-137">Related topics</span></span>

[<span data-ttu-id="0a53f-138">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="0a53f-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
