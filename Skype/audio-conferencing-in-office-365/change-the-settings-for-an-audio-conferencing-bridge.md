---
title: "Ändern der Einstellungen für eine Audiokonferenzbrücke"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: 'Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that''s used to prompt callers and gather names and pins for meeting organizers when they''re not using Skype for Business clients. '
ms.openlocfilehash: f37af15b4ab66eb5765cccbdba63b3bb6bb14597
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="14c6f-103">Ändern der Einstellungen für eine Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="14c6f-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="14c6f-p101">Beim Einrichten von Audiokonferenzen in Office 365 erhalten Sie von einer sogenannten Audiokonferenzbrücke Telefonnummern für Ihre Benutzer. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern umfassen. Diese Telefonnummern werden verwendet, wenn Anrufer sich in eine Besprechung einwählen. Die Telefonnummer ist am Ende der Skype for Business- oder Microsoft Teams-Besprechungseinladung zu finden.</span><span class="sxs-lookup"><span data-stu-id="14c6f-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="14c6f-p102">Die Konferenzbrücke nimmt den Anruf an und gibt Sprachanweisungen einer automatischen Telefonzentrale aus. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben, Anrufer auffordern, ihren Namen aufzuzeichnen, und die PIN-Einstellungen steuern. Besprechungsorganisatoren erhalten PINs, damit sie eine Besprechung starten können, wenn sie keine Skype for Business- oder Microsoft Teams-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="14c6f-p102">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="14c6f-110">Ändern der Einstellungen für eine Audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="14c6f-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="14c6f-111">**Festlegen des Besprechungsverhaltens, wenn Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="14c6f-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="14c6f-112">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="14c6f-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="14c6f-113">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="14c6f-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="14c6f-115">Wählen Sie auf der Seite **Einstellungen von Microsoft Bridge** unter **Besprechungsteilnahme** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="14c6f-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="14c6f-p103">**Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.</span><span class="sxs-lookup"><span data-stu-id="14c6f-p103">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="14c6f-118">Bei Auswahl von **Benachrichtigungen beim Betreten oder Verlassen einer Besprechung aktivieren** können Sie diese Optionen in der Liste **Entry/exit announcement type** (Typ der Benachrichtigung bei Zu- oder Abgang) auswählen:</span><span class="sxs-lookup"><span data-stu-id="14c6f-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="14c6f-119">**Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="14c6f-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="14c6f-120">**Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="14c6f-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14c6f-121">Die Verwendung des Ankündigungstyps **Ton** ist zurzeit für alle Kunden als Vorschaufunktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="14c6f-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="14c6f-p104">**Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**: Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="14c6f-p104">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="14c6f-124">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="14c6f-125">**Festlegen der Länge der PIN für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="14c6f-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="14c6f-126">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="14c6f-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="14c6f-127">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="14c6f-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="14c6f-129">Geben Sie auf der Seite **Einstellungen von Microsoft Bridge** unter **Sicherheit** in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="14c6f-130">Die PIN muss aus 4 bis 12 Ziffern bestehen.</span><span class="sxs-lookup"><span data-stu-id="14c6f-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="14c6f-131">**Auswählen, ob E-Mails an Ihre Benutzer gesendet werden sollen**</span><span class="sxs-lookup"><span data-stu-id="14c6f-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="14c6f-132">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="14c6f-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="14c6f-133">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="14c6f-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="14c6f-135">Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Automatically send emails to users if their audio conferencing configuration changes** (Automatisch E-Mails an Benutzer senden, wenn sich ihre Audiokonferenzkonfiguration ändert), und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14c6f-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="14c6f-136">Weitere Informationen finden Sie unter [e-Mails werden automatisch für Benutzer, wenn Ändern ihrer Einstellungen für die Audiokonferenz gesendet](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="14c6f-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="14c6f-137">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="14c6f-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="14c6f-138">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) nutzen.</span><span class="sxs-lookup"><span data-stu-id="14c6f-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="14c6f-p105">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="14c6f-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="14c6f-142">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="14c6f-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="14c6f-143">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14c6f-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="14c6f-p106">Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="14c6f-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="14c6f-146">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="14c6f-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="14c6f-147">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="14c6f-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="14c6f-148">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="14c6f-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="14c6f-p107">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="14c6f-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="14c6f-151">See Also</span><span class="sxs-lookup"><span data-stu-id="14c6f-151">Related topics</span></span>

[<span data-ttu-id="14c6f-152">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14c6f-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

