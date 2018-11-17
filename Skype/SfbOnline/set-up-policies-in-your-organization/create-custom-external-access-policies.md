---
title: Erstellen von benutzerdefinierten externen Zugriffsrichtlinien
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype for Business Online allows you to create additional external access policies. Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.
ms.openlocfilehash: a822e09875bbef1fcd1472ac988a32cadfaf5850
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561696"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="1d2b5-104">Erstellen von benutzerdefinierten externen Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1d2b5-104">Create custom external access policies</span></span>

<span data-ttu-id="1d2b5-p102">Skype for Business Online allows you to create additional external access policies. Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios. These are:</span><span class="sxs-lookup"><span data-stu-id="1d2b5-p102">Skype for Business Online allows you to create additional external access policies. Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios. These are:</span></span>
  
- <span data-ttu-id="1d2b5-108">No Federated oder Skype Consumer Zugriff (_Tag: NoFederationAndPIC_)</span><span class="sxs-lookup"><span data-stu-id="1d2b5-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="1d2b5-109">Nur Federated Zugriff (_Tag: FederationOnly_)</span><span class="sxs-lookup"><span data-stu-id="1d2b5-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="1d2b5-110">Federated und Consumer Zugriff (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="1d2b5-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="1d2b5-p103">Custom external policies allow you to create additional polices that aren't covered by the settings above. When the policy was created, you would be required to set all required parameters and you couldn't alter them later. Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings. Custom external access policies follow the same syntax as client, mobility, and conferencing policies. You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d2b5-p103">Custom external policies allow you to create additional polices that aren't covered by the settings above. When the policy was created, you would be required to set all required parameters and you couldn't alter them later. Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings. Custom external access policies follow the same syntax as client, mobility, and conferencing policies. You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="1d2b5-p104">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it. The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span><span class="sxs-lookup"><span data-stu-id="1d2b5-p104">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it. The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="1d2b5-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1d2b5-118">**Type**</span></span>|<span data-ttu-id="1d2b5-119">**Veröffentlichungsdatum**</span><span class="sxs-lookup"><span data-stu-id="1d2b5-119">**Release date**</span></span>|<span data-ttu-id="1d2b5-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="1d2b5-120">**Version**</span></span>|<span data-ttu-id="1d2b5-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="1d2b5-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d2b5-122">Erste Freigabe für den aktuellen Kanal</span><span class="sxs-lookup"><span data-stu-id="1d2b5-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="1d2b5-123">17.11.2016</span><span class="sxs-lookup"><span data-stu-id="1d2b5-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="1d2b5-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="1d2b5-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="1d2b5-125">Version 1611 (Build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="1d2b5-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="1d2b5-126">Aktueller Kanal</span><span class="sxs-lookup"><span data-stu-id="1d2b5-126">Current Channel</span></span>  <br/> |<span data-ttu-id="1d2b5-127">06.12.2016</span><span class="sxs-lookup"><span data-stu-id="1d2b5-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="1d2b5-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="1d2b5-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="1d2b5-129">Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="1d2b5-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="1d2b5-130">Verzögerter Kanal</span><span class="sxs-lookup"><span data-stu-id="1d2b5-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="1d2b5-131">22.02.2017</span><span class="sxs-lookup"><span data-stu-id="1d2b5-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="1d2b5-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="1d2b5-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="1d2b5-133">Version 1609 (Build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="1d2b5-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="1d2b5-134">Benutzer, die ältere Versionen von Windows-Apps für Skype for Business verwenden oder Mac-Kunden können weiterhin Dateien übertragen.</span><span class="sxs-lookup"><span data-stu-id="1d2b5-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="1d2b5-135">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d2b5-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="1d2b5-136">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="1d2b5-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="1d2b5-137">Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1d2b5-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1d2b5-138">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="1d2b5-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="1d2b5-p105">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="1d2b5-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="1d2b5-p106">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="1d2b5-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="1d2b5-145">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d2b5-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="1d2b5-146">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="1d2b5-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="1d2b5-147">Vom **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1d2b5-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1d2b5-148">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="1d2b5-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1d2b5-149">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="1d2b5-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="1d2b5-150">Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder das [Einrichten des Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1d2b5-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="1d2b5-151">Erstellen einer benutzerdefinierten Richtlinie für den externen Zugriff eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="1d2b5-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="1d2b5-152">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="1d2b5-152">To do this, run:</span></span>
  
> 
>   ```
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1d2b5-153">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="1d2b5-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1d2b5-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="1d2b5-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1d2b5-157">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1d2b5-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1d2b5-158">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="1d2b5-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1d2b5-p108">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1d2b5-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1d2b5-161">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d2b5-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1d2b5-162">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1d2b5-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1d2b5-163">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1d2b5-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="1d2b5-164">See Also</span><span class="sxs-lookup"><span data-stu-id="1d2b5-164">Related topics</span></span>
[<span data-ttu-id="1d2b5-165">Datenblöcke Point-Datei übertragen</span><span class="sxs-lookup"><span data-stu-id="1d2b5-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="1d2b5-166">Einrichten von Clientrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="1d2b5-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="1d2b5-167">Einrichten von konferenzrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="1d2b5-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 