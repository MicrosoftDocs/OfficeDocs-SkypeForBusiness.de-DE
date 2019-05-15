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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erhalten Sie Informationen zu PINs und zum Zurücksetzen von PINs in Microsoft Teams. '
ms.openlocfilehash: 56ea27ddf535f7ce23d5a25415b0a5921cfb2d6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912303"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="60e5a-103">Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60e5a-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="60e5a-104">Eine PIN ist ein aus Zahlen bestehender Code, der für jeden Microsoft Teams-Benutzer erstellt wird, der für Audiokonferenzen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="60e5a-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="60e5a-105">Besprechungsorganisatoren verwenden Audiokonferenz-PINs, um sich als Besprechungsorganisator auszuweisen und Besprechungen per Telefon zu starten.</span><span class="sxs-lookup"><span data-stu-id="60e5a-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="60e5a-106">Wenn der Organisator zum Starten einer Besprechung die Microsoft Teams-App verwendet, ist keine PIN erforderlich.</span><span class="sxs-lookup"><span data-stu-id="60e5a-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="60e5a-107">Wenn Benutzer ihre PIN vergessen und sie nicht in der E-Mail finden, die sie bei ihrer Aktivierung für Audiokonferenzen erhalten haben, kann die PIN von einem Administrator zurückgesetzt werden. Die Benutzer können ihre PIN auch selbst zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="60e5a-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="60e5a-108">Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer über die Microsoft Teams-App teilnimmt oder wenn der Organisator per Telefon mit seiner PIN teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="60e5a-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="60e5a-109">Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="60e5a-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="60e5a-110">Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="60e5a-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="60e5a-111">Zurücksetzen der PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="60e5a-111">Reset a user's PIN</span></span>

<span data-ttu-id="60e5a-112">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="60e5a-112">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="60e5a-113">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="60e5a-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="60e5a-114">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="60e5a-114">Click **Edit**.</span></span>

3. <span data-ttu-id="60e5a-115">Klicken Sie unter **Audiokonferenzen**klicken Sie auf **PIN zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="60e5a-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="60e5a-116">Klicken Sie auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="60e5a-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="60e5a-117">Ein Benutzer seine PIN zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="60e5a-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="60e5a-118">Bitten Sie den Benutzer, wechseln Sie zur [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span><span class="sxs-lookup"><span data-stu-id="60e5a-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="60e5a-119">Klicken Sie auf **Zurücksetzen PIN**.</span><span class="sxs-lookup"><span data-stu-id="60e5a-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="60e5a-120">Was sollten Sie sonst über PINs wissen?</span><span class="sxs-lookup"><span data-stu-id="60e5a-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="60e5a-121">Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="60e5a-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="60e5a-122">Nachdem die PIN durch einen Administrator zurückgesetzt wird, werden die PIN-Nummer als aufgelistet \*\*\*.</span><span class="sxs-lookup"><span data-stu-id="60e5a-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="60e5a-123">Automatisch Senden von e-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine e-Mail mit ihrer PIN, wenn sie aktiviert sind, für Audiokonferenzen oder wenn die PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="60e5a-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="60e5a-124">Aber wenn Sie automatisch deaktiviert haben Senden von e-Mails, eine PIN zurücksetzen-e-Mail wird nicht an einen Benutzer gesendet werden und Sie müssen die PIN-Informationen für den Benutzer manuell veranlassen.</span><span class="sxs-lookup"><span data-stu-id="60e5a-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="60e5a-p105">Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.</span><span class="sxs-lookup"><span data-stu-id="60e5a-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="60e5a-127">Die Standardeinstellung ist mit eine Besprechung gestartet werden, indem anonyme Anrufer nicht zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="60e5a-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="60e5a-128">Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, werden standardmäßig sie-e-Mails gesendet, die Informationen zur Telefonkonferenz und ihre PIN enthalten.</span><span class="sxs-lookup"><span data-stu-id="60e5a-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="60e5a-129">Der Benutzer muss ein Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN ist eine neue PIN in e-Mails an ihre primäre SMTP-Adresse (Alias) an den Benutzer gesendet wird, die für den Benutzer festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="60e5a-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="60e5a-130">Wenn Sie Audiokonferenzen eingerichtet haben, legen Sie die Ziffern, die für die PINs in Ihrer Organisation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="60e5a-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="60e5a-131">PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet.</span><span class="sxs-lookup"><span data-stu-id="60e5a-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="60e5a-132">Wenn Sie die PIN-Länge-Einstellung ändern, wird diese Einstellung gilt nur für neu generierte PINs und wird nicht angewendet, um die PIN-Einstellung für vorhandene Benutzer, die für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="60e5a-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="60e5a-133">Finden Sie unter [Legen Sie die PIN für Audiokonferenzen Besprechungen](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="60e5a-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="60e5a-134">Die e-Mail standardmäßig wird auf die Office 365 primäre SMTP-Adresse des Benutzers festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="60e5a-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="60e5a-135">Sie können eine e-Mail an eine nicht - Office 365-Adresse wie Hotmail oder MSN e-Mail-Adresse senden.</span><span class="sxs-lookup"><span data-stu-id="60e5a-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="60e5a-136">Mithilfe von Windows PowerShell können Sie die Standard-e-Mail-Adresse außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="60e5a-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="60e5a-137">Dies ist nützlich, wenn der Benutzer nicht über ein Exchange-Postfach in Office 365 verfügen.</span><span class="sxs-lookup"><span data-stu-id="60e5a-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="60e5a-138">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="60e5a-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="60e5a-p109">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60e5a-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="60e5a-142">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="60e5a-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="60e5a-143">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60e5a-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="60e5a-144">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="60e5a-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="60e5a-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="60e5a-145">Related topics</span></span>

[<span data-ttu-id="60e5a-146">Zurücksetzen einer Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="60e5a-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
