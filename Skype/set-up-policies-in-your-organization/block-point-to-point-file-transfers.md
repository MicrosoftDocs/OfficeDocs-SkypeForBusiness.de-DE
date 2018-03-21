---
title: "Point-Block dateiübertragungen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: "In Skype für Business Online haben Sie die Kontrolle über dateiübertragungen Point (P2P) als Teil des vorhandenen konferenzrichtlinieneinstellungen aufgeführt. Jedoch auf diese Weise können oder Blöcke Datei überträgt für Benutzer, unabhängig davon, ob sie Dateien an Benutzer, die innerhalb derselben Organisation sind oder an ein Verbundbenutzer aus einer anderen Organisation übertragen werden. Die folgenden Schritte ausführen, können Sie P2P dateiübertragungen mit verbundorganisationen oder Partnern blockieren."
ms.openlocfilehash: 288bec32d55d9784690d84b8daa205dd33568847
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="3a846-105">Point-Block dateiübertragungen</span><span class="sxs-lookup"><span data-stu-id="3a846-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="3a846-106">In Skype für Business Online haben Sie die Kontrolle über dateiübertragungen Point (P2P) als Teil des vorhandenen konferenzrichtlinieneinstellungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a846-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="3a846-107">Jedoch auf diese Weise können oder Blöcke Datei überträgt für Benutzer, unabhängig davon, ob sie Dateien an Benutzer, die innerhalb derselben Organisation sind oder an ein Verbundbenutzer aus einer anderen Organisation übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="3a846-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="3a846-108">Die folgenden Schritte ausführen, können Sie P2P dateiübertragungen mit verbundorganisationen oder Partnern blockieren.</span><span class="sxs-lookup"><span data-stu-id="3a846-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="3a846-109">Ein sehr häufiges Szenario ist, wenn Sie interne Benutzern, Dateiübertragung Verwendung P2P jedoch blockieren Dateiübertragung mit Verbundpartnern zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a846-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="3a846-110">Für dieses Szenario müssen Sie ausführen:</span><span class="sxs-lookup"><span data-stu-id="3a846-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="3a846-111">Zuweisen einer konferenzrichtlinie mit P2P-Dateiübertragung aktiviert (_EnableP2PFileTransfer_ auf _True_festgelegt) für Benutzer in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="3a846-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="3a846-112">Erstellen einer globalen externen Kommunikation Benutzerrichtlinie blockieren externe P2P-dateiübertragungen (_EnableP2PFileTransfer_ Festlegung auf _"false"_), und weisen Sie es zu einem Benutzer in Ihrer Organisation festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3a846-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="3a846-113">Sie können erfahren Sie mehr über diese Einstellungen [hier](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="3a846-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="3a846-114">Wenn ein Verbundbenutzer außerhalb Ihrer Organisation versucht, eine Datei an einen Benutzer senden, in dem die Richtlinie angewendet wurde, erhalten sie einen **Transfer** -Fehler.</span><span class="sxs-lookup"><span data-stu-id="3a846-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="3a846-115">Und wenn ein Benutzer versucht, eine Datei senden, erhalten sie eine Fehlermeldung **Dateiübertragung ist deaktiviert** .</span><span class="sxs-lookup"><span data-stu-id="3a846-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="3a846-116">Damit dies funktioniert, muss der Benutzer eine unterstützte Version von einer 2016 Klick-und-Los Skype-Geschäfts-app verwenden, die sie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3a846-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="3a846-117">Die folgenden Mindestversion von Skype für Business 2016 Klick-und-Los-Client ist erforderlich:</span><span class="sxs-lookup"><span data-stu-id="3a846-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="3a846-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3a846-118">**Type**</span></span>|<span data-ttu-id="3a846-119">**Veröffentlichungsdatum**</span><span class="sxs-lookup"><span data-stu-id="3a846-119">**Release date**</span></span>|<span data-ttu-id="3a846-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="3a846-120">**Version**</span></span>|<span data-ttu-id="3a846-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="3a846-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3a846-122">Erste Version für aktuellen Kanal</span><span class="sxs-lookup"><span data-stu-id="3a846-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="3a846-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="3a846-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="3a846-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="3a846-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="3a846-125">Version 1611 (Build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="3a846-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="3a846-126">Aktueller Channel</span><span class="sxs-lookup"><span data-stu-id="3a846-126">Current Channel</span></span>  <br/> |<span data-ttu-id="3a846-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="3a846-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="3a846-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="3a846-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="3a846-129">Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="3a846-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="3a846-130">Zurückgestellte DDE-Kanal</span><span class="sxs-lookup"><span data-stu-id="3a846-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="3a846-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="3a846-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="3a846-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="3a846-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="3a846-133">Version 1609 (Build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="3a846-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="3a846-134">Benutzer, die ältere Versionen von Skype für apps für Windows Business oder Macintosh-Clients verwenden weiterhin werden können Dateien übertragen.</span><span class="sxs-lookup"><span data-stu-id="3a846-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="3a846-135">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a846-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="3a846-136">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="3a846-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="3a846-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3a846-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3a846-138">Überprüfen Sie die Version, indem Sie _Get-Host_ im **Windows PowerShell** -Fenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="3a846-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="3a846-p106">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="3a846-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="3a846-p107">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="3a846-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="3a846-145">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="3a846-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="3a846-146">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="3a846-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="3a846-147">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3a846-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3a846-148">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="3a846-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a846-149">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="3a846-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="3a846-150">Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="3a846-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="3a846-151">Deaktivieren von dateiübertragungen für Ihre Organisation P2P</span><span class="sxs-lookup"><span data-stu-id="3a846-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="3a846-152">_EnableP2PFileTransfer_ ist standardmäßig auf globale Richtlinie für die Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a846-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="3a846-153">Wenn es erstellt wurde, wurden die Benutzer die _BposSAllModality_ Richtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3a846-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="3a846-154">Wenn P2P Übertragungen für innerhalb Ihrer Organisation jedoch blockieren externe dateiübertragungen an eine andere Organisation ermöglichen möchten, müssen Sie nur auf globaler Ebene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3a846-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="3a846-155">Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="3a846-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="3a846-156">Deaktivieren von dateiübertragungen für einen Benutzer P2P</span><span class="sxs-lookup"><span data-stu-id="3a846-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="3a846-157">Sie können dies zu einem Benutzer anwenden, indem eine neue Richtlinie erstellen und diesen Benutzer erteilen.</span><span class="sxs-lookup"><span data-stu-id="3a846-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="3a846-158">Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="3a846-158">To do that, run:</span></span> 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3a846-159">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="3a846-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="3a846-p111">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="3a846-p111">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3a846-163">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3a846-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3a846-164">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="3a846-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3a846-p112">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="3a846-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3a846-167">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a846-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3a846-168">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3a846-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3a846-169">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3a846-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="3a846-170">See Also</span><span class="sxs-lookup"><span data-stu-id="3a846-170">Related topics</span></span>
[<span data-ttu-id="3a846-171">Erstellen von benutzerdefinierten externen Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3a846-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="3a846-172">Einrichten von Clientrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="3a846-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="3a846-173">Einrichten von konferenzrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="3a846-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

