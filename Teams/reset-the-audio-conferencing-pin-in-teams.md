---
title: Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Hier erhalten Sie Informationen zu PINs und zum Zurücksetzen von PINs in Microsoft Teams. '
ms.openlocfilehash: 9c63df504150dce7ba1d46329fc86a27c75ced8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892954"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="80000-103">Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80000-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="80000-104">Eine PIN ist ein aus Zahlen bestehender Code, der für jeden Microsoft Teams-Benutzer erstellt wird, der für Audiokonferenzen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="80000-104">A PIN is a code made up of numbers that is created for each user who is enabled for dial-in conferencing.</span></span> <span data-ttu-id="80000-105">Besprechungsorganisatoren verwenden Audiokonferenz-PINs, um sich als Besprechungsorganisator auszuweisen und Besprechungen per Telefon zu starten.</span><span class="sxs-lookup"><span data-stu-id="80000-105">Dial-in conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="80000-106">Wenn der Organisator zum Starten einer Besprechung die Microsoft Teams-App verwendet, ist keine PIN erforderlich.</span><span class="sxs-lookup"><span data-stu-id="80000-106">If they use the Skype for Business client to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="80000-107">Wenn Benutzer ihre PIN vergessen und sie nicht in der E-Mail finden, die sie bei ihrer Aktivierung für Audiokonferenzen erhalten haben, kann die PIN von einem Administrator zurückgesetzt werden. Die Benutzer können ihre PIN auch selbst zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="80000-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for dial-in conferencing, an administrator will need to reset their PIN.</span></span>
  
<span data-ttu-id="80000-108">Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer über die Microsoft Teams-App teilnimmt oder wenn der Organisator per Telefon mit seiner PIN teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="80000-108">Meetings can be started when an authenticated user joins using a Skype for Business client or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="80000-109">Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="80000-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="80000-110">Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="80000-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="80000-111">Zurücksetzen der PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="80000-111">Reset a user's PIN</span></span>

1. <span data-ttu-id="80000-112">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="80000-112">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="80000-113">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="80000-113">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="80000-114">Klicken Sie unter **Audiokonferenz** auf **PIN zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="80000-114">Under **Audio Conferencing**, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="80000-115">Einen Benutzer die eigene PIN zurücksetzen lassen</span><span class="sxs-lookup"><span data-stu-id="80000-115">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="80000-116">Bitten Sie den Benutzer, zu [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="80000-116">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="80000-117">Dort muss der Benutzer auf **PIN zurücksetzen** klicken.</span><span class="sxs-lookup"><span data-stu-id="80000-117">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="80000-118">Was sollten Sie sonst über PINs wissen?</span><span class="sxs-lookup"><span data-stu-id="80000-118">What else should you know about PINs?</span></span>

- <span data-ttu-id="80000-119">Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal angezeigt, wenn die PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="80000-119">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="80000-120">Nach dem Zurücksetzen der PIN durch einen Administrator wird die PIN als \*\*\*\*\*\*\*\*\*\*\* dargestellt.</span><span class="sxs-lookup"><span data-stu-id="80000-120">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the Skype for Business admin center and in the results when they use Get-CsCsOnlineDialInConfencingUser in the Windows PowerShell.</span></span>
    
- <span data-ttu-id="80000-121">Das automatische Senden von E-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder ihre PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="80000-121">Automatically sending emails to users is enabled by default and users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset. But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span> <span data-ttu-id="80000-122">Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an die Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="80000-122">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span>
    
- <span data-ttu-id="80000-p105">Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.</span><span class="sxs-lookup"><span data-stu-id="80000-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="80000-125">Die Standardeinstellung sieht vor, dass Besprechungen nicht von anonymen Anrufern gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="80000-125">The default setting isn't to allow a meeting to be started by an anonymous callers.</span></span>
    
- <span data-ttu-id="80000-126">Wenn Sie Benutzer für Audiokonferenzen aktivieren, erhalten diese standardmäßig eine E-Mail mit Konferenzinformationen und ihrer PIN.</span><span class="sxs-lookup"><span data-stu-id="80000-126">When you enable a user for dial-in conferencing, by default they are sent emails that includes conferencing information and their PIN.</span></span> <span data-ttu-id="80000-127">Die Benutzer müssen über ein Office 365-Postfach verfügen, da beim Zurücksetzen ihrer PIN eine neue PIN per E-Mail an die primäre für sie festgelegte SMTP-Adresse (Alias) gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="80000-127">The user must have an Office 365 mailbox because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="80000-128">Beim Einrichten von Audiokonferenzen legen Sie die Ziffern fest, die für die PINs in Ihrer Organisation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="80000-128">When you set up dial-in conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="80000-129">PINs können vier bis zwölf Ziffern enthalten. Standardmäßig werden fünf Ziffern verwendet.</span><span class="sxs-lookup"><span data-stu-id="80000-129">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="80000-130">Wenn Sie die Einstellung für die PIN-Länge ändern, wird die Änderung nur auf neu generierte PINs angewendet und nicht auf PIN-Einstellungen vorhandener Benutzer, die bereits für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="80000-130">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for dial-in conferencing.</span></span> <span data-ttu-id="80000-131">Weitere Informationen finden Sie unter [Festlegen der Länge der PIN für Audiokonferenzbesprechungen](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="80000-131">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)</span></span>
    
- <span data-ttu-id="80000-132">Die E-Mail wird standardmäßig an die in Office 365 festgelegte primäre SMTP-Adresse des Benutzers gesendet.</span><span class="sxs-lookup"><span data-stu-id="80000-132">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="80000-133">Sie können auch eine E-Mail an eine nicht in Office 365 festgelegte Adresse senden, zum Beispiel an eine Hotmail- oder MSN-E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="80000-133">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="80000-134">Sie können die standardmäßige E-Mail-Adresse mithilfe von Windows PowerShell außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="80000-134">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="80000-135">Dies ist hilfreich, wenn die Benutzer kein Exchange-Postfach in Office 365 haben.</span><span class="sxs-lookup"><span data-stu-id="80000-135">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="80000-136">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="80000-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="80000-p109">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="80000-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="80000-140">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="80000-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="80000-141">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80000-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="80000-142">Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="80000-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="80000-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="80000-143">Related topics</span></span>

[<span data-ttu-id="80000-144">Zurücksetzen einer Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="80000-144">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
