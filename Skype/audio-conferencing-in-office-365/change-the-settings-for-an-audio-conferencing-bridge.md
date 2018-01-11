---
title: "Ändern der Einstellungen für eine Audiokonferenz-Brücke"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Hier finden Sie die Schritte, die Sie Einstellungen für eine Microsoft-Einwahl Konferenzbrücke ändern, mit der Aufforderung Anrufer und Namen und Pins für Besprechungsorganisatoren sammeln, wenn sie nicht Skype für Business Clients verwenden, müssen. "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="bd82e-103">Ändern der Einstellungen für eine Audiokonferenz-Brücke</span><span class="sxs-lookup"><span data-stu-id="bd82e-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="bd82e-104">Wenn Sie Audiokonferenzen in Office 365 einrichten, erhalten Sie Telefonnummern für Ihre Benutzer von was eine audiokonferenzbrücke aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bd82e-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="bd82e-105">Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten.</span><span class="sxs-lookup"><span data-stu-id="bd82e-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="bd82e-106">Diese Rufnummern werden verwendet, wenn Anrufer in einer Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="bd82e-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="bd82e-107">Die Telefonnummer ist am unteren Rand der Skype für Business oder Microsoft-Teams Besprechung einladen enthalten.</span><span class="sxs-lookup"><span data-stu-id="bd82e-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="bd82e-108">Die Konferenzbrücke beantwortet eines Anrufs und zeigt den Anrufer Ansagen mithilfe einer Besprechung Auto attendant, und klicken Sie dann je nach Ihrer Einstellungen wiedergeben Benachrichtigungen, bitten Sie ihren Namen aufzeichnen Anrufer, und kann die PIN-Einstellungen steuern.</span><span class="sxs-lookup"><span data-stu-id="bd82e-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="bd82e-109">Stifte, Besprechungsorganisatoren zugewiesen sind, können an eine Besprechung starten werden beim werden nicht mithilfe einer Skype für Business oder Microsoft-Teams, app.</span><span class="sxs-lookup"><span data-stu-id="bd82e-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="bd82e-110">Ändern der Einstellungen für eine audiokonferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="bd82e-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="bd82e-111">**Richten Sie die besprechungsumgebung, wenn Anrufer an einer Besprechung teilnehmen**</span><span class="sxs-lookup"><span data-stu-id="bd82e-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="bd82e-112">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="bd82e-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bd82e-113">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bd82e-114">Navigieren Sie in der **Skype für Business-Verwaltungskonsole**im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="bd82e-115">Wählen Sie auf der Seite **Microsoft-Brücke-Einstellungen** unter **Erleben Sie die Teilnahme an einer Besprechung**:</span><span class="sxs-lookup"><span data-stu-id="bd82e-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="bd82e-116">**Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden** Diese Option ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="bd82e-116">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="bd82e-117">Wenn Sie das Kontrollkästchen deaktivieren, werden nicht Benutzer, die bereits an der Besprechung benachrichtigt, wenn ein Benutzer eingibt oder die Besprechung verlässt.</span><span class="sxs-lookup"><span data-stu-id="bd82e-117">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="bd82e-118">Bei der Auswahl von **Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden**, können Sie diese Optionen aus der Liste **Entry/Exit Ankündigung** auswählen:</span><span class="sxs-lookup"><span data-stu-id="bd82e-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="bd82e-119">**Namen oder Telefonnummern** Wenn der Benutzer in einer Besprechung einwählen, wird beim Beitritt zu es ihre Telefonnummer wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="bd82e-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="bd82e-120">**Töne** Wenn der Benutzer in einer Besprechung einwählen, wird beim Beitritt zu es ein audio Ton wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="bd82e-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd82e-121">Unter Verwendung von **Tone** Dateityp Ankündigung ist als Vorschaufeature derzeit für alle Kunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bd82e-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="bd82e-122">**Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen** Diese Option ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="bd82e-122">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="bd82e-123">Wenn Sie das Kontrollkästchen deaktivieren, werden nicht Anrufer aufgefordert, ihren Namen aufzeichnen müssen, bevor sie an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="bd82e-123">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="bd82e-124">Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="bd82e-125">**Legen Sie die PIN-Mindestlänge für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="bd82e-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="bd82e-126">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="bd82e-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bd82e-127">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bd82e-128">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="bd82e-129">Geben Sie auf der Seite **Microsoft-Brücke-Einstellungen** unter **Sicherheit**die Anzahl der Ziffern, die Sie für die PIN-Nummer in der Liste der **PIN-Länge** verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bd82e-130">Die PIN muss zwischen 4 und 12 Ziffern.</span><span class="sxs-lookup"><span data-stu-id="bd82e-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="bd82e-131">**Wählen Sie, ob das Senden von e-Mails an Ihre Benutzer**</span><span class="sxs-lookup"><span data-stu-id="bd82e-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="bd82e-132">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="bd82e-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bd82e-133">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bd82e-134">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="bd82e-135">Klicken Sie auf der Seite **Microsoft-Brücke Einstellungen** aktivieren Sie oder deaktivieren Sie **automatisch für Benutzer-e-Mails gesendet, wenn die Konfiguration ihrer Audiokonferenzen ändert**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bd82e-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="bd82e-136">Weitere Informationen finden Sie unter [e-Mails werden automatisch für Benutzer, wenn Ändern ihrer Einstellungen für die Audiokonferenz gesendet](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="bd82e-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bd82e-137">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="bd82e-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bd82e-138">Um Zeit sparen oder diesen Prozess automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd82e-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="bd82e-139">Windows PowerShell ist alles über das Verwalten von Benutzern und welche Benutzer zugelassen oder Aktionen nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="bd82e-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bd82e-140">Mit Windows PowerShell können Sie eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Office 365 verwalten.</span><span class="sxs-lookup"><span data-stu-id="bd82e-140">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="bd82e-141">Siehe folgende Themen, um Windows PowerShell zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="bd82e-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd82e-142">Warum müssen Sie mithilfe von Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd82e-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bd82e-143">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd82e-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="bd82e-144">Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen.</span><span class="sxs-lookup"><span data-stu-id="bd82e-144">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bd82e-145">Informationen Sie zu dieser Vorteile in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="bd82e-145">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="bd82e-146">Eine Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bd82e-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bd82e-147">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bd82e-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bd82e-148">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bd82e-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="bd82e-p107">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="bd82e-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bd82e-151">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bd82e-151">Related topics</span></span>

[<span data-ttu-id="bd82e-152">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd82e-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

