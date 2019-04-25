---
title: Zurücksetzen der Audiokonferenz PIN in Skype für Business Online
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
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, was Sie Drehbezugspunkten wissen sollten und wie diese in Skype für Business Online zurückzusetzen. '
ms.openlocfilehash: 257f59f59d4fc86c91aa5496fe3db42573269065
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229251"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="f5d9e-103">Zurücksetzen der Audiokonferenz PIN in Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="f5d9e-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="f5d9e-104">Informationen zum Zurücksetzen von Audio Conferencing PINs in Microsoft-Teams, finden Sie unter [PIN Audio Conferencing in Microsoft-Teams, Zurücksetzen](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f5d9e-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="f5d9e-105">Eine PIN ist ein Code bestehend aus Zahlen, die für jeden Skype für Geschäftsbenutzer erstellt werden, die für Audiokonferenzen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="f5d9e-106">Audiokonferenzen PINs von Besprechungsorganisatoren dienen zum Identifizieren, sie der Organisator der Besprechung sind und ermöglicht es ihnen, eine Besprechung über das Telefon zu starten.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="f5d9e-107">Wenn sie die Skype für Geschäfts-app verwenden, um die Besprechung zu starten, ist eine PIN nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="f5d9e-108">Wenn Benutzer ihre PIN vergessen, und sie können nicht gefunden werden in der e-Mail, die an sie gesendet wurde, wenn sie für die Audiokonferenz aktiviert wurden, ein Administrator kann ihre PIN zurücksetzen, oder sie können ihre eigenen PIN zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="f5d9e-109">Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer Beitritt mithilfe der Skype-Geschäfts-app oder wenn der Organisator mit seinem PIN über das Telefon Beitritt.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="f5d9e-110">Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="f5d9e-111">Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="f5d9e-112">Zurücksetzen der PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="f5d9e-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="f5d9e-113">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f5d9e-114">Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen**, und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-114">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="f5d9e-115">Klicken Sie auf **Benutzer**, wählen Sie den Benutzer, dem Sie für die PIN zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="f5d9e-116">Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="f5d9e-117">Ein Benutzer seine PIN zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="f5d9e-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="f5d9e-118">Ein Benutzer kann eine PIN zurücksetzen, mithilfe der Option **PIN zurücksetzen** auf der Seite **Einwahlkonferenzen** .</span><span class="sxs-lookup"><span data-stu-id="f5d9e-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="f5d9e-119">Auf dieser Seite kann auf drei Arten zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="f5d9e-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="f5d9e-120">Wechseln Sie in einem Browser zu [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span><span class="sxs-lookup"><span data-stu-id="f5d9e-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="f5d9e-121">In Skype für Unternehmen, klicken Sie auf den Pfeil **Menü anzeigen** neben **Optionen**, und klicken Sie dann auf **Extras** > **Konferenz Einwähleinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="f5d9e-122">Klicken Sie in Skype für Unternehmen auf **Optionen**, klicken Sie im linken Menü auf **Anrufweiterleitung** und in den Abschnitt **Weitere Einstellungen aufrufen,** klicken Sie dann auf **Bearbeiten von online-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="f5d9e-123">Was sollten Sie sonst über PINs wissen?</span><span class="sxs-lookup"><span data-stu-id="f5d9e-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="f5d9e-124">Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="f5d9e-125">Nachdem die PIN durch einen Administrator zurückgesetzt wird, werden die PIN-Nummer als aufgelistet \*\*\* in der **Skype für Business-Verwaltungskonsole** und in den Ergebnissen, wenn sie Get-CsCsOnlineDialInConfencingUser in Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="f5d9e-126">Automatisch Senden von e-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine e-Mail mit ihrer PIN, wenn sie aktiviert sind, für Audiokonferenzen oder wenn die PIN zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="f5d9e-127">Aber wenn Sie automatisch deaktiviert haben Senden von e-Mails, eine PIN zurücksetzen-e-Mail wird nicht an einen Benutzer gesendet werden und Sie müssen die PIN-Informationen für den Benutzer manuell veranlassen.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="f5d9e-p106">Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="f5d9e-130">Die Standardeinstellung ist mit eine Besprechung gestartet werden, indem anonyme Anrufer nicht zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="f5d9e-131">Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, werden standardmäßig sie-e-Mails gesendet, die Informationen zur Telefonkonferenz und ihre PIN enthalten.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="f5d9e-132">Der Benutzer muss ein Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN ist eine neue PIN in e-Mails an ihre primäre SMTP-Adresse (Alias) an den Benutzer gesendet wird, die für den Benutzer festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-132">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="f5d9e-133">Wenn Sie Audiokonferenzen eingerichtet haben, legen Sie die Ziffern, die für die PINs in Ihrer Organisation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="f5d9e-134">PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="f5d9e-135">Wenn Sie die PIN-Länge-Einstellung ändern, wird diese Einstellung gilt nur für neu generierte PINs und wird nicht angewendet, um die PIN-Einstellung für vorhandene Benutzer, die für Audiokonferenzen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="f5d9e-136">Finden Sie unter [Legen Sie die PIN für Audiokonferenzen Besprechungen](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="f5d9e-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="f5d9e-137">Die e-Mail standardmäßig wird auf die Office 365 primäre SMTP-Adresse des Benutzers festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-137">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="f5d9e-138">Sie können eine e-Mail an eine nicht - Office 365-Adresse wie Hotmail oder MSN e-Mail-Adresse senden.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-138">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="f5d9e-139">Mithilfe von Windows PowerShell können Sie die Standard-e-Mail-Adresse außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="f5d9e-140">Dies ist nützlich, wenn der Benutzer nicht über ein Exchange-Postfach in Office 365 verfügen.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-140">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="f5d9e-141">Um die Standard-Benutzer-Adresse zu überschreiben, die e-Mail-Nachricht gesendet wird, kann den Administrator des Mandanten verwenden Sie das folgende Cmdlet: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendenEMail - SendEmailToAddress "u@hotmail.com".</span><span class="sxs-lookup"><span data-stu-id="f5d9e-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="f5d9e-142">Der SendenEMail-Parameter ist erforderlich, die e-Mail-Adresse des Benutzers außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f5d9e-143">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="f5d9e-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f5d9e-144">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="f5d9e-145">Sie können die PIN für Amos Marble konfigurieren, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="f5d9e-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="f5d9e-p111">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f5d9e-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f5d9e-149">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="f5d9e-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f5d9e-150">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5d9e-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="f5d9e-p112">Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="f5d9e-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f5d9e-153">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f5d9e-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="f5d9e-154">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f5d9e-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f5d9e-155">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f5d9e-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="f5d9e-p113">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f5d9e-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f5d9e-158">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f5d9e-158">Related topics</span></span>

[<span data-ttu-id="f5d9e-159">Zurücksetzen einer Konferenzkennung für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="f5d9e-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
