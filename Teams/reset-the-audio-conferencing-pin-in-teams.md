---
title: Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Hier erhalten Sie Informationen zu PINs und zum Zurücksetzen von PINs in Microsoft Teams. '
ms.openlocfilehash: 92f0fcf0b5a5e8afe0615b54b08f0fa407c4a969
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838225"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="4dd15-103">Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4dd15-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="4dd15-104">Eine PIN ist ein aus Zahlen bestehender Code, der für jeden Microsoft Teams-Benutzer erstellt wird, der für Audiokonferenzen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4dd15-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="4dd15-105">Besprechungsorganisatoren verwenden Audiokonferenz-PINs, um sich als Besprechungsorganisator auszuweisen und Besprechungen per Telefon zu starten.</span><span class="sxs-lookup"><span data-stu-id="4dd15-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="4dd15-106">Wenn der Organisator zum Starten einer Besprechung die Microsoft Teams-App verwendet, ist keine PIN erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dd15-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="4dd15-107">Wenn Benutzer ihre PIN vergessen und sie nicht in der E-Mail finden, die sie bei ihrer Aktivierung für Audiokonferenzen erhalten haben, kann die PIN von einem Administrator zurückgesetzt werden. Die Benutzer können ihre PIN auch selbst zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="4dd15-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="4dd15-108">Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer über die Microsoft Teams-App teilnimmt oder wenn der Organisator per Telefon mit seiner PIN teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="4dd15-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="4dd15-109">Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="4dd15-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="4dd15-110">Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="4dd15-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="4dd15-111">Zurücksetzen der PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="4dd15-111">Reset a user's PIN</span></span>

<span data-ttu-id="4dd15-112">![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt</span><span class="sxs-lookup"><span data-stu-id="4dd15-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4dd15-113">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4dd15-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4dd15-114">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4dd15-114">Click **Edit**.</span></span>

3. <span data-ttu-id="4dd15-115">Klicken Sie unter **Audiokonferenzen**auf **PIN zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4dd15-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="4dd15-116">Klicken Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4dd15-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="4dd15-117">Festlegen, dass ein Benutzer seine eigene Pin zurücksetzt</span><span class="sxs-lookup"><span data-stu-id="4dd15-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="4dd15-118">Lassen Sie [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)den Benutzer wechseln.</span><span class="sxs-lookup"><span data-stu-id="4dd15-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="4dd15-119">Klicken Sie auf **PIN zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="4dd15-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="4dd15-120">Was sollten Sie sonst über PINs wissen?</span><span class="sxs-lookup"><span data-stu-id="4dd15-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="4dd15-121">Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="4dd15-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="4dd15-122">Nachdem die PIN von einem Administrator zurückgesetzt wurde, wird die PIN als \* \* \* \* \* \* \* \* \* \* \* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4dd15-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="4dd15-123">Das automatische Senden von e-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine e-Mail mit ihrer PIN, wenn Sie für Audiokonferenzen aktiviert sind oder wenn die PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="4dd15-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="4dd15-124">Wenn Sie jedoch das automatische Senden von e-Mails deaktiviert haben, wird eine e-Mail mit Pin-Reset nicht an einen Benutzer gesendet, und Sie müssen die PIN-Informationen manuell an den Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="4dd15-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="4dd15-p105">Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.</span><span class="sxs-lookup"><span data-stu-id="4dd15-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="4dd15-127">Die Standardeinstellung ist, dass eine Besprechung nicht von anonymen Anrufern gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4dd15-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="4dd15-128">Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, werden standardmäßig e-Mail-Nachrichten gesendet, die Konferenz Informationen und Ihre PIN enthalten.</span><span class="sxs-lookup"><span data-stu-id="4dd15-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="4dd15-129">Der Benutzer muss über ein Office 365-Postfach verfügen, denn wenn eine PIN zurückgesetzt wird, wird eine neue PIN an den Benutzer in einer e-Mail an die primäre SMTP-Adresse (Alias) gesendet, die für den Benutzer festgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="4dd15-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="4dd15-130">Wenn Sie Audiokonferenzen einrichten, legen Sie die Ziffern fest, die für die Pins in Ihrer Organisation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4dd15-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="4dd15-131">PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet.</span><span class="sxs-lookup"><span data-stu-id="4dd15-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="4dd15-132">Wenn Sie die Einstellung für die PIN-Länge ändern, wird die Einstellung nur auf neu generierte Pins angewendet und nicht auf die PIN-Einstellung für vorhandene Benutzer angewendet, die für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4dd15-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="4dd15-133">Informationen finden Sie unter [Festlegung der Länge der PIN für Audiokonferenz-Besprechungen](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4dd15-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="4dd15-134">Die e-Mail-Adresse wird standardmäßig auf die primäre SMTP-Adresse von Office 365 des Benutzers eingestellt.</span><span class="sxs-lookup"><span data-stu-id="4dd15-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="4dd15-135">Sie können eine e-Mail an eine nicht-Office 365-Adresse wie eine Hotmail-oder MSN-e-Mail-Adresse senden.</span><span class="sxs-lookup"><span data-stu-id="4dd15-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="4dd15-136">Sie können die Standard-e-Mail-Adresse mithilfe von Windows PowerShell außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="4dd15-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="4dd15-137">Dies ist hilfreich, wenn die Benutzer kein Exchange-Postfach in Office 365 haben.</span><span class="sxs-lookup"><span data-stu-id="4dd15-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4dd15-138">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="4dd15-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4dd15-p109">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4dd15-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4dd15-142">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="4dd15-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4dd15-143">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dd15-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4dd15-144">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4dd15-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4dd15-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4dd15-145">Related topics</span></span>

[<span data-ttu-id="4dd15-146">Zurücksetzen einer Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="4dd15-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
