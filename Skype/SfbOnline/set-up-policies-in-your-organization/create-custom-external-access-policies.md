---
title: Erstellen von benutzerdefinierten externen Zugriffsrichtlinien
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype ermöglicht Ihnen die Erstellung von externen Zugriffs-Richtlinien. Nicht so wie bei Conferencing-Richtlinien, bei denen Sie mehrere Kombinationen haben können, gibt es hier drei vordefinierte Richtlinien für den externen Zugriff, die die meisten Szenarien abdecken.
ms.openlocfilehash: e166aa9af162fd6432c8932d5842ea0fd00a36b3
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568312"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="5f206-104">Erstellen von benutzerdefinierten externen Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5f206-104">Create custom external access policies</span></span>

<span data-ttu-id="5f206-105">Skype ermöglicht Ihnen die Erstellung von externen Zugriffs-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="5f206-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="5f206-106">Nicht so wie bei Conferencing-Richtlinien, bei denen Sie mehrere Kombinationen haben können, gibt es hier drei vordefinierte Richtlinien für den externen Zugriff, die die meisten Szenarien abdecken.</span><span class="sxs-lookup"><span data-stu-id="5f206-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="5f206-107">Diese sind:</span><span class="sxs-lookup"><span data-stu-id="5f206-107">These devices are supported.</span></span>
  
- <span data-ttu-id="5f206-108">No Federated oder Skype Consumer Zugriff (_Tag: NoFederationAndPIC_)</span><span class="sxs-lookup"><span data-stu-id="5f206-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="5f206-109">Nur Federated Zugriff (_Tag: FederationOnly_)</span><span class="sxs-lookup"><span data-stu-id="5f206-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="5f206-110">Federated und Consumer Zugriff (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="5f206-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="5f206-111">Richtlinien für den benutzerdefinierten externen Zugriff ermöglichen Ihnen, zusätzliche Richtlinien zu schaffen, die von den oben genannten Einstellungen nicht abgedeckt sind.</span><span class="sxs-lookup"><span data-stu-id="5f206-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="5f206-112">Wenn die Richtlinie erstellt wurde, werden Sie aufgefortert, alle erforderlichen Parameter einzustellen, die Sie später jedoch nicht mehr ändern können.</span><span class="sxs-lookup"><span data-stu-id="5f206-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="5f206-113">Die Erstellung neuer benutzerdefinierter Richtlinien ermöglicht Ihnen, Funktionen wie Skype Consumer Zugriff zu steuern oder eine Richtlinie zum Deaktivieren von Audio/Video aus der öffentlichen Cloud - dies war nicht von den Voreinstellungen abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="5f206-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="5f206-114">Benutzerdefinierte externe Zugriffsrichtlinien führen derselben Syntax wie die Client-, Mobilitäts- und Conferencing-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="5f206-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="5f206-115">Weitere Informationen zu diesen Einsellungen finden Sie [hier](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f206-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="5f206-116">Damit dies funktioniert, muss der Benutzer eine unterstützte Version von 2016 der App Click-to-Run für Skype for Business verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f206-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="5f206-117">Die folgende Minimalversion von Skype for Business 2016 Click-to-Run ist erforderlich:</span><span class="sxs-lookup"><span data-stu-id="5f206-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="5f206-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="5f206-118">**Type**</span></span>|<span data-ttu-id="5f206-119">**Veröffentlichungsdatum**</span><span class="sxs-lookup"><span data-stu-id="5f206-119">**Release date**</span></span>|<span data-ttu-id="5f206-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="5f206-120">**Version**</span></span>|<span data-ttu-id="5f206-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="5f206-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f206-122">Erste Freigabe für den aktuellen Kanal</span><span class="sxs-lookup"><span data-stu-id="5f206-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="5f206-123">17.11.2016</span><span class="sxs-lookup"><span data-stu-id="5f206-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="5f206-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="5f206-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="5f206-125">Version 1611 (Build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="5f206-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="5f206-126">Aktueller Kanal</span><span class="sxs-lookup"><span data-stu-id="5f206-126">Current Channel</span></span>  <br/> |<span data-ttu-id="5f206-127">06.12.2016</span><span class="sxs-lookup"><span data-stu-id="5f206-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="5f206-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="5f206-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="5f206-129">Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="5f206-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="5f206-130">Verzögerter Kanal</span><span class="sxs-lookup"><span data-stu-id="5f206-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="5f206-131">22.02.2017</span><span class="sxs-lookup"><span data-stu-id="5f206-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="5f206-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="5f206-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="5f206-133">Version 1609 (Build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="5f206-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="5f206-134">Benutzer, die ältere Versionen von Windows-Apps für Skype for Business verwenden oder Mac-Kunden können weiterhin Dateien übertragen.</span><span class="sxs-lookup"><span data-stu-id="5f206-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="5f206-135">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f206-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="5f206-136">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="5f206-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="5f206-137">Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5f206-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5f206-138">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="5f206-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="5f206-p105">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="5f206-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="5f206-p106">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="5f206-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="5f206-145">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f206-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="5f206-146">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="5f206-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="5f206-147">Vom **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5f206-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5f206-148">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="5f206-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f206-149">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="5f206-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="5f206-150">Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder[Herstellen der Verbindung zu Skype for Business Online mit Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f206-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="5f206-151">Erstellen einer benutzerdefinierten Richtlinie für den externen Zugriff eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="5f206-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="5f206-152">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="5f206-152">To do this, run the following command:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5f206-153">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="5f206-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5f206-154">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5f206-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5f206-155">Mit Windows PowerShell können Sie Office 365 und Skype for Business Online über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen, wenn Sie viele Dinge zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="5f206-155">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5f206-156">Siehe folgende Themen, um Windows PowerShell zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="5f206-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5f206-157">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5f206-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5f206-158">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="5f206-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5f206-p108">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="5f206-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5f206-161">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f206-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5f206-162">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5f206-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5f206-163">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5f206-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="5f206-164">See Also</span><span class="sxs-lookup"><span data-stu-id="5f206-164">Related topics</span></span>
[<span data-ttu-id="5f206-165">Blockieren von Punkt-zu-Punkt-Dateiübertragungen</span><span class="sxs-lookup"><span data-stu-id="5f206-165">Block Point-to-Point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="5f206-166">Einrichten von Clientrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="5f206-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="5f206-167">Einrichten von Conferencing-Richtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="5f206-167">Set up conferencing policies for your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 