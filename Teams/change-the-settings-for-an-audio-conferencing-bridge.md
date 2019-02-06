---
title: Ändern der Einstellungen für eine Audiokonferenzbrücke
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie die Schritte, die Sie Einstellungen für eine Konferenzbrücke ändern, mit der Aufforderung Anrufer und Namen und Pins für Besprechungsorganisatoren sammeln, wenn sie nicht Skype für apps Business oder Microsoft-Teams verwenden, müssen. '
ms.openlocfilehash: c6e4a0e04b1e63e02dd477e1c1d2e70cc7234052
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754720"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="4eca1-103">Ändern der Einstellungen für eine Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="4eca1-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="4eca1-p101">Beim Einrichten von Audiokonferenzen in Office 365 erhalten Sie von einer sogenannten Audiokonferenzbrücke Telefonnummern für Ihre Benutzer. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern umfassen. Diese Telefonnummern werden verwendet, wenn Anrufer sich in eine Besprechung einwählen. Die Telefonnummer ist am Ende der Skype for Business- oder Microsoft Teams-Besprechungseinladung zu finden.</span><span class="sxs-lookup"><span data-stu-id="4eca1-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="4eca1-p102">Die Konferenzbrücke nimmt den Anruf an und gibt Sprachanweisungen einer automatischen Telefonzentrale aus. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben, Anrufer auffordern, ihren Namen aufzuzeichnen, und die PIN-Einstellungen steuern. Besprechungsorganisatoren erhalten PINs, damit sie eine Besprechung starten können, wenn sie keine Skype for Business- oder Microsoft Teams-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="4eca1-p102">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4eca1-p103">Der Besprechungsorganisator benötigt nur dann eine PIN, wenn die Besprechung nicht bereits von einem Benutzer einer Skype for Business- oder Microsoft Teams-App gestartet wurde. Wenn sich alle Teilnehmer in die Besprechung einwählen, benötigt der Besprechungsorganisator die PIN zum Starten der Besprechung.</span><span class="sxs-lookup"><span data-stu-id="4eca1-p103">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="4eca1-113">Verwenden das Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="4eca1-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4eca1-114">Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenzbrücken**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="4eca1-115">Klicken Sie am oberen Rand der Seite **Konferenzbrücken** **Bridge-Einstellungen**auf.</span><span class="sxs-lookup"><span data-stu-id="4eca1-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="4eca1-116">Klicken Sie im Bereich **Bridge Einstellungen** auswählen:</span><span class="sxs-lookup"><span data-stu-id="4eca1-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="4eca1-117">**Meeting-Eintrag, und beenden Sie Benachrichtigungen** Wenn Sie diese Option aktivieren, werden nicht Benutzer, die bereits an der Besprechung benachrichtigt, wenn jemand Beitritt oder die Besprechung verlässt.</span><span class="sxs-lookup"><span data-stu-id="4eca1-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="4eca1-118">Wenn Sie **Meeting Beitritts- und Benachrichtigungen**aktivieren, können Sie diese Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="4eca1-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="4eca1-119">**Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="4eca1-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="4eca1-120">**Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="4eca1-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="4eca1-121">**Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen** Wenn Sie diese Option aktivieren, werden nicht Anrufer aufgefordert, ihren Namen aufzeichnen müssen, bevor sie an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="4eca1-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="4eca1-122">Um die PIN-Mindestlänge für Besprechungen festzulegen, wählen Sie die Anzahl der Nachkommastellen für die PIN-Nummer in der Liste der **PIN-Länge** gewünschte.</span><span class="sxs-lookup"><span data-stu-id="4eca1-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="4eca1-123">Um anzugeben, ob e-Mail an die Benutzer senden, aktivieren oder deaktivieren **für Benutzer-e-Mails automatisch gesendet, wenn die Konfiguration ihrer Audiokonferenzen ändert**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="4eca1-124">Weitere Informationen finden Sie unter [-e-Mails automatisch gesendet, um Benutzer beim Ändern ihrer Einstellungen für die Audiokonferenz im Microsoft-Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) oder [Benutzern beim Ändern ihrer Einstellungen für die in Skype für Business Online gesendete E-Mails](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .</span><span class="sxs-lookup"><span data-stu-id="4eca1-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="4eca1-125">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-125">Click **Save**.</span></span> 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](media/sfb-logo-30x30.png)  <span data-ttu-id="4eca1-127">Verwenden des Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="4eca1-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="4eca1-128">**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="4eca1-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="4eca1-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="4eca1-130">Wählen Sie auf der Seite **Einstellungen von Microsoft Bridge** unter **Besprechungsteilnahme** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4eca1-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="4eca1-p105">**Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="4eca1-p105">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="4eca1-133">Bei Auswahl von **Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren** können Sie diese Optionen in der Liste **Entry/exit announcement type** (Typ der Benachrichtigung bei Zu- oder Abgang) auswählen:</span><span class="sxs-lookup"><span data-stu-id="4eca1-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="4eca1-134">**Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="4eca1-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="4eca1-135">**Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="4eca1-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="4eca1-p106">**Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="4eca1-p106">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="4eca1-138">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="4eca1-139">**Festlegen der Länge der PIN für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="4eca1-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="4eca1-140">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4eca1-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="4eca1-141">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="4eca1-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="4eca1-143">Geben Sie auf der Seite **Einstellungen von Microsoft Bridge** unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4eca1-144">Die PIN muss aus 4 bis 12 Ziffern bestehen.</span><span class="sxs-lookup"><span data-stu-id="4eca1-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="4eca1-145">**Auswählen, ob E-Mails an Ihre Benutzer gesendet werden sollen**</span><span class="sxs-lookup"><span data-stu-id="4eca1-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="4eca1-146">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="4eca1-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="4eca1-147">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="4eca1-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="4eca1-149">Klicken Sie auf der Seite **Microsoft-Brücke Einstellungen** aktivieren Sie oder deaktivieren Sie **automatisch für Benutzer-e-Mails gesendet, wenn sich ihre Einwahlinformationen ändert**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4eca1-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="4eca1-150">Weitere Informationen finden Sie unter [-e-Mails automatisch gesendet, um Benutzer beim Ändern ihrer Einstellungen für die Audiokonferenz im Microsoft-Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) oder [Benutzern beim Ändern ihrer Einstellungen für die in Skype für Business Online gesendete E-Mails](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .</span><span class="sxs-lookup"><span data-stu-id="4eca1-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4eca1-151">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="4eca1-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4eca1-152">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) nutzen.</span><span class="sxs-lookup"><span data-stu-id="4eca1-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="4eca1-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4eca1-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4eca1-156">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="4eca1-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4eca1-157">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eca1-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4eca1-p108">Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="4eca1-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="4eca1-160">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4eca1-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4eca1-161">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4eca1-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4eca1-162">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4eca1-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4eca1-p109">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="4eca1-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4eca1-165">See Also</span><span class="sxs-lookup"><span data-stu-id="4eca1-165">Related topics</span></span>

[<span data-ttu-id="4eca1-166">Einrichten von Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="4eca1-166">Set up Audio Conferencing</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
