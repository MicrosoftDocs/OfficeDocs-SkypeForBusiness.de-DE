---
title: Starten einer Audiokonferenz per Telefon ohne PIN in Skype for Business Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: af62ed29ed2bbe835ab811651152b231a85caaf8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302770"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="f4d0a-103">Starten einer Audiokonferenz per Telefon ohne PIN in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4d0a-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="f4d0a-104">Informationen zum Starten einer Audiokonferenz ohne PIN in Microsoft Teams finden Sie unter [Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f4d0a-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="f4d0a-105">Es ist möglicherweise frustrierend, dass Benutzer, die sich in eine Besprechung einwählen, in der Besprechungslobby abgehalten werden, um Musik zu hören, da der Skype for Business-Besprechungsorganisator die Besprechung noch nicht gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="f4d0a-106">Wenn ein Besprechungsorganisator in die Besprechung einruft, ist standardmäßig eine PIN erforderlich, um eine Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="f4d0a-107">Sie können es so einrichten, dass sich jeder in eine Besprechung einwählen kann und nicht zur Eingabe einer PIN aufgefordert wird, um die Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="f4d0a-108">Sie können diese Einstellung für einen einzelnen Benutzer im Skype for Business Admin Center aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="f4d0a-109">Eine PIN ist für den Besprechungsorganisator nicht erforderlich, wenn eine andere Person die Besprechung über die Skype for Business-App gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="f4d0a-110">Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="f4d0a-111">Die PIN für Besprechungen wird an den audiobenutzer gesendet, wenn Ihnen die **Audiokonferenz** -Lizenz zugewiesen wurde und für Audiokonferenzen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="f4d0a-112">Weitere Informationen finden Sie unter [Senden einer e-Mail-Nachricht an einen Benutzer mit ihren](send-an-email-to-a-user-with-their-dial-in-information.md) Audiokonferenzinformationen und [e-Mails, die automatisch an Benutzer gesendet werden, wenn sich Ihre audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="f4d0a-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="f4d0a-113">Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="f4d0a-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="f4d0a-114">Wechseln Sie im **Skype for Business Admin Center**im linken Navigationsbereich zu Audiokonferenz \*\*\*\* > -**Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="f4d0a-115">Wählen Sie in der Liste den Benutzer aus, und klicken Sie im Bereich "Aktion" auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="f4d0a-116">Aktivieren oder deaktivieren Sie auf der Eigenschaftenseite des Benutzers unter **Besprechungsoptionen**die Option zulassen, dass **nicht authentifizierte Anrufer die ersten Personen in einer Besprechung sind. Wenn dies nicht der Fall ist, werden Sie in der Lobby warten, bis ein authentifizierter Benutzer Beitritt**.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="f4d0a-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="f4d0a-118">**Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f4d0a-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="f4d0a-119">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="f4d0a-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="f4d0a-120">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="f4d0a-120">What else should you know?</span></span>

- <span data-ttu-id="f4d0a-121">Wenn Sie die PIN zurücksetzen möchten, lesen Sie [Zurücksetzen der Audiokonferenz-Pin](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="f4d0a-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="f4d0a-122">Wenn der anonyme Zugriff oder das Starten einer Besprechung keine PIN erfordert, ist aktiviert:</span><span class="sxs-lookup"><span data-stu-id="f4d0a-122">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="f4d0a-123">Wenn die Besprechung noch nicht begonnen hat (es ist noch niemand in der Besprechung vorhanden): ein Anrufer wird aufgefordert, wenn er der Organisator ist; Wenn er "Ja" sagt, wird er aufgefordert, seine PIN einzugeben, und nachdem er die PIN angegeben hat, wird die Besprechung gestartet, und der Benutzer wird an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="f4d0a-124">Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): ein Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nie zur Eingabe der PIN aufgefordert; die Besprechung wurde bereits gestartet, und der Anrufer wird teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="f4d0a-125">Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN nicht erforderlich ist, ist deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="f4d0a-125">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="f4d0a-126">Wenn die Besprechung noch nicht begonnen hat (es ist noch niemand in der Besprechung vorhanden): ein Anrufer wird nicht dazu aufgefordert, wenn er der Organisator ist, und wird nie zur Eingabe der PIN aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="f4d0a-127">Da die Einstellung für Organizer auf aus festgelegt ist, wird die Besprechung gestartet, und die anonymen Anrufer werden an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="f4d0a-128">Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): ein Anrufer wird nicht dazu aufgefordert, wenn Sie der Organisator ist, und Sie wird nie zur Eingabe der PIN aufgefordert; die Besprechung wurde bereits gestartet, und der Anrufer wird teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f4d0a-129">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="f4d0a-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f4d0a-130">Um Zeit zu sparen bzw. den Vorgang für mehrere Benutzer zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="f4d0a-p104">In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f4d0a-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f4d0a-134">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="f4d0a-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f4d0a-135">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4d0a-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="f4d0a-p105">Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="f4d0a-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="f4d0a-138">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4d0a-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="f4d0a-139">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4d0a-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f4d0a-140">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4d0a-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="f4d0a-p106">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f4d0a-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f4d0a-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f4d0a-143">Related topics</span></span>

[<span data-ttu-id="f4d0a-144">Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365</span><span class="sxs-lookup"><span data-stu-id="f4d0a-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
