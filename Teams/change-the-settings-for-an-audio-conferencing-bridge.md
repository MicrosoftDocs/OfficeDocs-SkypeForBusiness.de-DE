---
title: Ändern der Einstellungen für eine Audiokonferenzbrücke
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Führen Sie die Schritte aus, die Sie zum Ändern der Einstellungen für eine Konferenzbrücke benötigen, mit der Anrufer aufgefordert und Namen und Pins für Besprechungsorganisatoren gesammelt werden, wenn Sie keine Skype for Business-oder Microsoft Teams-Apps verwenden. '
ms.openlocfilehash: d77d614b0b9e41d5948c3f9f9322df168a452bec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283441"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="b57ea-103">Ändern der Einstellungen für eine Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="b57ea-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="b57ea-p101">Beim Einrichten von Audiokonferenzen in Office 365 erhalten Sie von einer sogenannten Audiokonferenzbrücke Telefonnummern für Ihre Benutzer. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern umfassen. Diese Telefonnummern werden verwendet, wenn Anrufer sich in eine Besprechung einwählen. Die Telefonnummer ist am Ende der Skype for Business- oder Microsoft Teams-Besprechungseinladung zu finden.</span><span class="sxs-lookup"><span data-stu-id="b57ea-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="b57ea-p102">Die Konferenzbrücke nimmt den Anruf an und gibt Sprachanweisungen einer automatischen Telefonzentrale aus. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben, Anrufer auffordern, ihren Namen aufzuzeichnen, und die PIN-Einstellungen steuern. Besprechungsorganisatoren erhalten PINs, damit sie eine Besprechung starten können, wenn sie keine Skype for Business- oder Microsoft Teams-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="b57ea-p102">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="b57ea-p103">Der Besprechungsorganisator benötigt nur dann eine PIN, wenn die Besprechung nicht bereits von einem Benutzer einer Skype for Business- oder Microsoft Teams-App gestartet wurde. Wenn sich alle Teilnehmer in die Besprechung einwählen, benötigt der Besprechungsorganisator die PIN zum Starten der Besprechung.</span><span class="sxs-lookup"><span data-stu-id="b57ea-p103">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Teams-Logo-30x30. png](media/teams-logo-30x30.png) <span data-ttu-id="b57ea-113">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="b57ea-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b57ea-114">Wechseln Sie in der linken Navigationsleiste zu **Besprechungen** > **Konferenz Brücken**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="b57ea-115">Klicken Sie oben auf der Seite **Konferenz Brücken** auf **Brücken Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="b57ea-116">Wählen Sie im Bereich **Bridge Settings** die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b57ea-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="b57ea-117">**Besprechungs-und Exit-Benachrichtigungen** Wenn Sie diese Option deaktivieren, werden Benutzer, die der Besprechung bereits beigetreten sind, nicht benachrichtigt, wenn jemand die Besprechung eingibt oder verlässt.</span><span class="sxs-lookup"><span data-stu-id="b57ea-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="b57ea-118">Wenn Sie Besprechungs- **und Beendigungs Benachrichtigungen**aktivieren, können Sie die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="b57ea-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="b57ea-119">**Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b57ea-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="b57ea-120">**Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b57ea-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="b57ea-121">**Bitten Sie die Anrufer, Ihren Namen aufzuzeichnen, bevor Sie der Besprechung beitreten** . Wenn Sie diese Option deaktivieren, werden Anrufer nicht aufgefordert, Ihren Namen aufzuzeichnen, bevor Sie an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="b57ea-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="b57ea-122">Wenn Sie die PIN-Länge für Besprechungen festlegen möchten, wählen Sie die Anzahl der Ziffern für die PIN in der Liste **PIN-Länge** aus.</span><span class="sxs-lookup"><span data-stu-id="b57ea-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="b57ea-123">Wenn Sie angeben möchten, ob e-Mails an Ihre Benutzer gesendet werden sollen, aktivieren oder deaktivieren Sie **automatisch e-Mails an Benutzer senden, wenn sich Ihre Audiokonferenz-Konfiguration ändert**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="b57ea-124">Weitere Informationen finden Sie unter [e-Mails, die automatisch an Benutzer gesendet werden, wenn sich Ihre audiokonferenzeinstellungen in Microsoft Teams ändern](emails-sent-to-users-when-their-settings-change-in-teams.md) oder [e-Mails an Benutzer gesendet werden, wenn sich Ihre Einstellungen in Skype for Business Online ändern](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .</span><span class="sxs-lookup"><span data-stu-id="b57ea-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="b57ea-125">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-125">Click **Save**.</span></span> 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](media/sfb-logo-30x30.png)  <span data-ttu-id="b57ea-127">Verwenden des Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="b57ea-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="b57ea-128">**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="b57ea-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="b57ea-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="b57ea-130">Wählen Sie auf der Seite **Einstellungen von Microsoft Bridge** unter **Besprechungsteilnahme** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="b57ea-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="b57ea-p105">**Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="b57ea-p105">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="b57ea-133">Bei Auswahl von **Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren** können Sie diese Optionen in der Liste **Entry/exit announcement type** (Typ der Benachrichtigung bei Zu- oder Abgang) auswählen:</span><span class="sxs-lookup"><span data-stu-id="b57ea-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="b57ea-134">**Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b57ea-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="b57ea-135">**Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b57ea-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="b57ea-p106">**Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="b57ea-p106">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="b57ea-138">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="b57ea-139">**Festlegen der Länge der PIN für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="b57ea-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="b57ea-140">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="b57ea-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="b57ea-141">Wechseln Sie zum **Microsoft 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="b57ea-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="b57ea-143">Geben Sie auf der Seite **Einstellungen von Microsoft Bridge** unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b57ea-144">Die PIN muss aus 4 bis 12 Ziffern bestehen.</span><span class="sxs-lookup"><span data-stu-id="b57ea-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="b57ea-145">**Auswählen, ob E-Mails an Ihre Benutzer gesendet werden sollen**</span><span class="sxs-lookup"><span data-stu-id="b57ea-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="b57ea-146">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="b57ea-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="b57ea-147">Wechseln Sie zum **Microsoft 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="b57ea-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="b57ea-149">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** **automatisch e-Mails an Benutzer senden, wenn sich Ihre Einwahlinformationen ändern**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b57ea-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="b57ea-150">Weitere Informationen finden Sie unter [e-Mails, die automatisch an Benutzer gesendet werden, wenn sich Ihre audiokonferenzeinstellungen in Microsoft Teams ändern](emails-sent-to-users-when-their-settings-change-in-teams.md) oder [e-Mails an Benutzer gesendet werden, wenn sich Ihre Einstellungen in Skype for Business Online ändern](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .</span><span class="sxs-lookup"><span data-stu-id="b57ea-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b57ea-151">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="b57ea-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b57ea-152">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) nutzen.</span><span class="sxs-lookup"><span data-stu-id="b57ea-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="b57ea-p107">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b57ea-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b57ea-156">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="b57ea-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b57ea-157">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b57ea-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="b57ea-158">Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b57ea-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b57ea-159">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="b57ea-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="b57ea-160">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b57ea-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b57ea-161">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b57ea-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b57ea-162">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b57ea-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="b57ea-p109">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="b57ea-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b57ea-165">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b57ea-165">Related topics</span></span>

[<span data-ttu-id="b57ea-166">Einrichten von Audiokonferenzen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b57ea-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="b57ea-167">Einrichten von Audiokonferenzen für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b57ea-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
