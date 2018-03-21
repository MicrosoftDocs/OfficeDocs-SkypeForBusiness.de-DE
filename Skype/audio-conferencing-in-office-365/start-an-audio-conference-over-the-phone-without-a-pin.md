---
title: "Beginnen einer Audio-Konferenz über das Telefon ohne PIN"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 57e1e209180cb5811556cdd29a5d45a77302eb22
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="c95d0-103">Beginnen einer Audio-Konferenz über das Telefon ohne PIN</span><span class="sxs-lookup"><span data-stu-id="c95d0-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="c95d0-104">Es kann für Benutzer frustrierend sein, die sich in in eine Besprechung einwählen gehalten werden, in der Besprechung Wartebereich Musik hören, weil die Skype für Business oder Microsoft-Teams Organisator die Besprechung noch nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="c95d0-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="c95d0-105">Wenn Organisator einer Besprechung die Besprechung standardmäßig in Aufrufe ist eine PIN erforderlich, um eine Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="c95d0-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="c95d0-106">Sie können es einrichten, damit alle Benutzer an einer Besprechung einwählen kann und keine Aufforderung des Benutzers für eine PIN, um die Besprechung zu starten.</span><span class="sxs-lookup"><span data-stu-id="c95d0-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="c95d0-107">Sie können diese Einstellung für einen einzelnen Benutzer im Skype for Business Admin Center aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c95d0-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="c95d0-108">Eine PIN ist nicht für den Organisator der Besprechung erforderlich, wenn eine Person die Besprechung aus einem Skype für Business oder Microsoft-Teams app gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="c95d0-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="c95d0-109">Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="c95d0-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="c95d0-110">Die PIN für Besprechungen wird an den audio-Benutzer gesendet, die **Audiokonferenz** Lizenz zugewiesen werden und für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c95d0-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="c95d0-111">Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md) und [E-Mails, die Benutzern beim Ändern ihrer Einstellungen für die Audiokonferenz automatisch gesendet werden](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="c95d0-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="c95d0-112">Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="c95d0-112">Enable or disable anonymous callers from joining a meeting</span></span>

1. <span data-ttu-id="c95d0-113">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="c95d0-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c95d0-114">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c95d0-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c95d0-115">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="c95d0-115">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
4. <span data-ttu-id="c95d0-116">Klicken Sie in der Liste Wählen Sie den Benutzer aus, und klicken Sie im Bereich Aktion auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c95d0-116">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
5. <span data-ttu-id="c95d0-117">Eigenschaftenseite des Benutzers unter **Besprechungsoptionen**aktivieren oder Deaktivieren von **zulassen, die nicht authentifizierte Anrufer, um die ersten Personen in einer Besprechung werden. Wenn nicht, klicken Sie dann sie im Wartebereich wartet, bis ein authentifizierter Benutzer Beitritt**.</span><span class="sxs-lookup"><span data-stu-id="c95d0-117">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
6. <span data-ttu-id="c95d0-118">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c95d0-118">Click **Save**.</span></span> 
    
 <span data-ttu-id="c95d0-119">**Aktivieren oder Deaktivieren der anonyme Anrufern für alle Ihre Benutzer Besprechungen mithilfe von Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="c95d0-119">**To enable or disable anonymous callers to all of your user's meetings using Windows Powershell**</span></span>
  
- <span data-ttu-id="c95d0-120">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c95d0-120">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="c95d0-121">Was sollten Sie noch wissen?</span><span class="sxs-lookup"><span data-stu-id="c95d0-121">What else should you know?</span></span>

- <span data-ttu-id="c95d0-122">Informationen zum Zurücksetzen der PIN finden Sie unter [Zurücksetzen der Einwahlkonferenz-PIN für einen Benutzer](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c95d0-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
- <span data-ttu-id="c95d0-123">Wenn anonymer Zugriff oder keine erfordern eine PIN an eine Besprechung starten aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="c95d0-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="c95d0-124">Wenn die Besprechung noch nicht gestartet (es ist keine Empfänger in der Besprechung noch): ein Anrufer aufgefordert werden, wenn er der Organisator ist; Wenn er Ja angezeigt wird, wird er für seine PIN aufgefordert, und nachdem er die PIN eingibt, die Besprechung wird gestartet, und der Benutzer wird an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="c95d0-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="c95d0-125">Wenn die Besprechung bereits gestartet (eine andere Person ist bereits in der Besprechung): ein Anrufer nicht aufgefordert werden, wenn er der Organisator ist und er nie für die PIN aufgefordert; die Besprechung wurde bereits gestartet, und der Anrufer wird verknüpfen, um.</span><span class="sxs-lookup"><span data-stu-id="c95d0-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="c95d0-126">Wenn anonymer Zugriff oder keine erfordern eine PIN an eine Besprechung starten deaktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="c95d0-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="c95d0-127">Wenn die Besprechung noch nicht gestartet (es ist keine Empfänger in der Besprechung noch): ein Anrufer nicht aufgefordert, wenn er der Organisator ist und er nie für die PIN aufgefordert werden werden.</span><span class="sxs-lookup"><span data-stu-id="c95d0-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="c95d0-128">Da die Einstellung der Organisator der OFF festgelegt ist, die Besprechung wird gestartet, und anonyme Anrufer werden an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="c95d0-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="c95d0-129">Wenn die Besprechung bereits gestartet (eine andere Person ist bereits in der Besprechung): ein Anrufer nicht aufgefordert, wenn er der Organisator ist und er nie für die PIN aufgefordert; die Besprechung bereits gestartet, und der Anrufer wird verknüpfen, um.</span><span class="sxs-lookup"><span data-stu-id="c95d0-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c95d0-130">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="c95d0-130">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c95d0-131">Um Zeit zu sparen bzw. den Vorgang für mehrere Benutzer zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.</span><span class="sxs-lookup"><span data-stu-id="c95d0-131">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="c95d0-p104">In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c95d0-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c95d0-135">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="c95d0-135">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c95d0-136">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c95d0-136">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c95d0-p105">Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="c95d0-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c95d0-139">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c95d0-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="c95d0-140">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c95d0-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c95d0-141">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c95d0-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c95d0-p106">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="c95d0-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c95d0-144">See Also</span><span class="sxs-lookup"><span data-stu-id="c95d0-144">Related topics</span></span>

[<span data-ttu-id="c95d0-145">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c95d0-145">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
