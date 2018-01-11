---
title: "Einrichten von Konferenzrichtlinien für Ihre Organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Konferenzen sind ein wichtiger Bestandteil von Skype for Business Online: In Konferenzen können Gruppen von Benutzern gemeinsam online Folien und Videos anzeigen, Anwendungen freigeben, Dateien austauschen und anderweitig kommunizieren und zusammenarbeiten."
ms.openlocfilehash: 6ccfdd3e5153a7b22d26fb492690da0e476fe9ee
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="2d5b9-103">Einrichten von Konferenzrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="2d5b9-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="2d5b9-104">Konferenzen sind ein wichtiger Bestandteil von Skype for Business Online: In Konferenzen können Gruppen von Benutzern gemeinsam online Folien und Videos anzeigen, Anwendungen freigeben, Dateien austauschen und anderweitig kommunizieren und zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="2d5b9-p101">Wichtig ist dabei, dass Sie die Kontrolle über Konferenzen und Konferenzeinstellungen behalten. In manchen Fällen liegen möglicherweise Sicherheitsbedenken vor: Standardmäßig können alle, das heißt auch nicht authentifizierte Benutzer, an Besprechungen teilnehmen und die in diesen Besprechungen verteilten Folien oder Handzettel speichern. Darüber hinaus sind manchmal auch rechtliche Bedenken möglich. So können beispielsweise die Besprechungsteilnehmer standardmäßig Anmerkungen zu freigegebenen Inhalten hinzufügen. Diese Anmerkungen werden jedoch nicht gespeichert, wenn die Besprechung archiviert wird. Wenn Ihre Organisation Aufzeichnungen der gesamten elektronischen Kommunikation aufbewahren muss, sollten Sie Anmerkungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="2d5b9-p102">In Skype for Business Online werden Konferenzen mithilfe von Konferenzrichtlinien verwaltet. Konferenzrichtlinien bestimmen die Merkmale und Funktionen, die in einer Konferenz verwendet werden können. Dazu gehört die Frage, ob die Konferenz IP-Audio und -Video für die maximal mögliche Teilnehmeranzahl in einer Besprechung enthalten kann. Konferenzrichtlinien können auf globaler Ebene oder auf Benutzerebene konfiguriert werden. Dadurch können Administratoren sehr flexibel entscheiden, welche Funktionen welchen Benutzern zur Verfügung gestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="2d5b9-114">Richtlinieneinstellungen können Sie bei der Erstellung einer Richtlinie konfigurieren. Alternativ können Sie das **Set-CsConferencingPolicy** -Cmdlet verwenden, um die Einstellungen einer vorhandenen Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="2d5b9-115">Festlegen Ihrer Konferenzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2d5b9-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="2d5b9-116">Für alle Konferenzrichtlinieneinstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="2d5b9-117">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d5b9-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="2d5b9-118">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="2d5b9-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="2d5b9-119">Um sicherzustellen, dass Sie Version 3.0 oder höher ausgeführt werden: **Im Menü Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="2d5b9-120">Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="2d5b9-p103">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="2d5b9-p104">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="2d5b9-127">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d5b9-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="2d5b9-128">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="2d5b9-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="2d5b9-129">Über das **Startmenü** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="2d5b9-130">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2d5b9-131">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="2d5b9-132">Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d5b9-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="2d5b9-133">Blockieren von Dateiübertragung und Desktopfreigabe in Besprechungen</span><span class="sxs-lookup"><span data-stu-id="2d5b9-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="2d5b9-134">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-134">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```
  <span data-ttu-id="2d5b9-135">Weitere Informationen finden Sie im [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2d5b9-136">Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-136">To grant the new policy you created to all users in your organization, run:</span></span>
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```
  <span data-ttu-id="2d5b9-137">Weitere Informationen finden Sie im [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="2d5b9-138">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)-Cmdlet die Einstellungen auf die Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="2d5b9-139">Blockieren der Aufzeichnung von Konferenzen und Verhindern von anonymen Besprechungsteilnehmern</span><span class="sxs-lookup"><span data-stu-id="2d5b9-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="2d5b9-140">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-140">To create a new policy for these settings, run:</span></span> 
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```
<span data-ttu-id="2d5b9-141">Weitere Informationen finden Sie im [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2d5b9-142">Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-142">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```
<span data-ttu-id="2d5b9-143">Weitere Informationen finden Sie im [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="2d5b9-144">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) -Cmdlet, die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) -Cmdlet verwenden, um die Einstellungen für die Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="2d5b9-145">Blockieren der Aufzeichnung von Besprechungen durch anonyme Teilnehmer und der Speicherung von Besprechungsinhalten durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="2d5b9-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="2d5b9-146">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-146">To create a new policy for these settings, run:</span></span>  
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```
<span data-ttu-id="2d5b9-147">Weitere Informationen finden Sie im [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="2d5b9-148">Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

<span data-ttu-id="2d5b9-149">Weitere Informationen finden Sie im [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="2d5b9-150">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)-Cmdlet die Einstellungen auf die Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="2d5b9-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2d5b9-151">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="2d5b9-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="2d5b9-p105">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2d5b9-155">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2d5b9-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="2d5b9-156">Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365</span><span class="sxs-lookup"><span data-stu-id="2d5b9-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="2d5b9-p106">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="2d5b9-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="2d5b9-159">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d5b9-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="2d5b9-160">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2d5b9-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2d5b9-161">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2d5b9-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="2d5b9-162">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2d5b9-162">Related topics</span></span>
[<span data-ttu-id="2d5b9-163">Erstellen von benutzerdefinierten externe Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2d5b9-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="2d5b9-164">Datenblöcke Point-Datei übertragen</span><span class="sxs-lookup"><span data-stu-id="2d5b9-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="2d5b9-165">Einrichten von Clientrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="2d5b9-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)