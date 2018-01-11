---
title: "Einrichten von Richtlinien für mobile Geräte für Ihre Organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Sie können einrichten, wie Benutzer über die Skype for Business-App auf mobilen Geräten Verbindungen mit Skype for Business Online herstellen. Ein Beispiel hierfür wäre eine Funktion, mit der Benutzer auf ihrem Mobiltelefon Telefonanrufe tätigen und empfangen können und dazu ihre geschäftliche Rufnummer anstelle ihrer Mobiltelefonnummer verwenden können. Mit Mobilitätsrichtlinien können Sie auch festlegen, dass Anrufe nur über WLAN-Verbindungen getätigt oder empfangen werden können."
ms.openlocfilehash: 0772091e33043ed9ce5019b5c26ec8857d158260
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="85074-104">Einrichten von Richtlinien für mobile Geräte für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="85074-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="85074-p102">Sie können einrichten, wie Benutzer über die Skype for Business-App auf mobilen Geräten Verbindungen mit Skype for Business Online herstellen. Ein Beispiel hierfür wäre eine Funktion, mit der Benutzer auf ihrem Mobiltelefon Telefonanrufe tätigen und empfangen können und dazu ihre geschäftliche Rufnummer anstelle ihrer Mobiltelefonnummer verwenden können. Mit Mobilitätsrichtlinien können Sie auch festlegen, dass Anrufe nur über WLAN-Verbindungen getätigt oder empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="85074-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="85074-107">Richtlinieneinstellungen für mobile Geräte können Sie bei der Erstellung einer Richtlinie konfigurieren. Alternativ können Sie das **Set-CsMobilityPolicy** -Cmdlet verwenden, um die Einstellungen einer vorhandenen Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="85074-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="85074-108">Festlegen Ihrer Richtlinien für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="85074-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="85074-109">Für alle Richtlinieneinstellungen für mobile Geräte in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="85074-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="85074-110">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85074-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="85074-111">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="85074-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="85074-112">Um sicherzustellen, dass Sie Version 3.0 oder höher ausgeführt werden: **Im Menü Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="85074-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="85074-113">Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="85074-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="85074-p103">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="85074-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="85074-p104">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="85074-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="85074-120">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="85074-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="85074-121">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="85074-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="85074-122">Über das **Startmenü** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="85074-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="85074-123">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="85074-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85074-124">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="85074-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="85074-125">Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="85074-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="85074-126">Festlegen einer WLAN-Verbindung als erforderlich für Video für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="85074-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="85074-127">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85074-127">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  <span data-ttu-id="85074-128">Weitere Informationen finden Sie im [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85074-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="85074-129">Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85074-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  <span data-ttu-id="85074-130">Weitere Informationen finden Sie im [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85074-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="85074-131">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)-Cmdlet die Einstellung auf die Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="85074-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="85074-132">Verhindern, dass ein Benutzer die Skype for Business-App verwendet</span><span class="sxs-lookup"><span data-stu-id="85074-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="85074-133">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85074-133">To create a new policy for these settings, run:</span></span>
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  <span data-ttu-id="85074-134">Weitere Informationen finden Sie im [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85074-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="85074-135">Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85074-135">To grant the new policy you created to Amos Marble, run:</span></span>  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  <span data-ttu-id="85074-136">Weitere Informationen finden Sie im [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85074-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="85074-137">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das Cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) , die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) -Cmdlet verwenden, um die Einstellung für die Benutzer zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="85074-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="85074-138">Verhindern, dass ein Benutzer Voice over IP-Anrufe über ein mobiles Gerät tätigt</span><span class="sxs-lookup"><span data-stu-id="85074-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="85074-139">Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85074-139">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  <span data-ttu-id="85074-140">Weitere Informationen finden Sie im [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85074-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="85074-141">Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85074-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  <span data-ttu-id="85074-142">Weitere Informationen finden Sie im [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="85074-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="85074-143">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)-Cmdlet die Einstellung auf die Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="85074-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="85074-144">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="85074-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="85074-p105">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="85074-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="85074-148">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85074-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="85074-149">Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365</span><span class="sxs-lookup"><span data-stu-id="85074-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="85074-p106">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="85074-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="85074-152">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85074-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="85074-153">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85074-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="85074-154">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85074-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="85074-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="85074-155">Related topics</span></span>
[<span data-ttu-id="85074-156">Erstellen von benutzerdefinierten externe Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="85074-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="85074-157">Datenblöcke Point-Datei übertragen</span><span class="sxs-lookup"><span data-stu-id="85074-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="85074-158">Einrichten von Clientrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="85074-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="85074-159">Einrichten von konferenzrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="85074-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

