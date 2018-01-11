---
title: "Einrichten von Clientrichtlinien für Ihre Organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern."
ms.openlocfilehash: 2d76f1037e595419caf5059a563e441c521abd81
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="bd8f4-103">Einrichten von Clientrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="bd8f4-103">Set up client policies for your organization</span></span>

<span data-ttu-id="bd8f4-104">Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="bd8f4-105">Richtlinie Clienteinstellungen auf die Uhrzeit der Erstellung eine Richtlinie konfiguriert werden können, oder kann, verwenden Sie das Cmdlet **Set-CsClientPolicy** zum Ändern der Einstellungen einer vorhandenen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="bd8f4-106">Festlegen Ihrer Clientrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bd8f4-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="bd8f4-107">Für alle Clientrichtlinieneinstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="bd8f4-108">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd8f4-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="bd8f4-109">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="bd8f4-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="bd8f4-110">Um sicherzustellen, dass Sie Version 3.0 oder höher ausgeführt werden: **Im Menü Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bd8f4-111">Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="bd8f4-p101">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="bd8f4-p102">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="bd8f4-118">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd8f4-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="bd8f4-119">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="bd8f4-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="bd8f4-120">Über das **Startmenü** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bd8f4-121">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd8f4-122">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="bd8f4-123">Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd8f4-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="bd8f4-124">Deaktivieren von Emoticons und Anwesenheitsbenachrichtigungen und Verhindern der Speicherung von Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="bd8f4-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="bd8f4-125">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-125">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  <span data-ttu-id="bd8f4-126">Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bd8f4-127">Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  <span data-ttu-id="bd8f4-128">Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="bd8f4-129">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das Cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) , die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) verwenden, um die Einstellungen für die Benutzer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="bd8f4-130">Aktivieren von klickbaren URLs oder Hyperlinks in Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="bd8f4-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="bd8f4-131">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-131">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  <span data-ttu-id="bd8f4-132">Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bd8f4-133">Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  <span data-ttu-id="bd8f4-134">Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="bd8f4-135">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das Cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) , die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) verwenden, um die Einstellungen für die Benutzer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="bd8f4-136">Verhindern der Anzeige der letzten Kontakte</span><span class="sxs-lookup"><span data-stu-id="bd8f4-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="bd8f4-137">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-137">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  <span data-ttu-id="bd8f4-138">Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="bd8f4-139">Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-139">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  <span data-ttu-id="bd8f4-140">Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="bd8f4-141">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das Cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) , die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) verwenden, um die Einstellungen für die Benutzer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="bd8f4-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bd8f4-142">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="bd8f4-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="bd8f4-p103">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-p103">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd8f4-146">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bd8f4-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bd8f4-147">Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365</span><span class="sxs-lookup"><span data-stu-id="bd8f4-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bd8f4-p104">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="bd8f4-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bd8f4-150">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd8f4-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bd8f4-151">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bd8f4-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bd8f4-152">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bd8f4-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bd8f4-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bd8f4-153">Related topics</span></span>
[<span data-ttu-id="bd8f4-154">Erstellen von benutzerdefinierten externe Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bd8f4-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="bd8f4-155">Datenblöcke Point-Datei übertragen</span><span class="sxs-lookup"><span data-stu-id="bd8f4-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="bd8f4-156">Einrichten von konferenzrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="bd8f4-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
