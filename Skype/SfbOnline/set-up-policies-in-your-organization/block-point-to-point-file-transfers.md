---
title: Blockieren von Punkt-zu-Punkt-Dateiübertragungen
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: In Skype for Business Online haben Sie die Möglichkeit, Punkt-zu-Punkt-Dateiübertragungen (P2P) als Teil der vorhandenen konferenzrichtlinieneinstellungen zu steuern. Auf diese Weise können jedoch Dateiübertragungen für Benutzer blockiert werden, unabhängig davon, ob Sie Dateien an einen Benutzer übertragen, der sich in derselben Organisation oder einem Verbundbenutzer aus einer anderen Organisation befindet. Führen Sie die folgenden Schritte aus, um P2P-Dateiübertragungen mit Verbundorganisationen oder-Partnern zu blockieren.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814634"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="4eaa2-105">Blockieren von Punkt-zu-Punkt-Dateiübertragungen</span><span class="sxs-lookup"><span data-stu-id="4eaa2-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="4eaa2-106">In Skype for Business Online haben Sie die Möglichkeit, Punkt-zu-Punkt-Dateiübertragungen (P2P) als Teil der vorhandenen konferenzrichtlinieneinstellungen zu steuern.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="4eaa2-107">Auf diese Weise können jedoch Dateiübertragungen für Benutzer blockiert werden, unabhängig davon, ob Sie Dateien an einen Benutzer übertragen, der sich in derselben Organisation oder einem Verbundbenutzer aus einer anderen Organisation befindet.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="4eaa2-108">Führen Sie die folgenden Schritte aus, um P2P-Dateiübertragungen mit Verbundorganisationen oder-Partnern zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="4eaa2-109">Ein sehr häufiges Szenario ist, wenn Sie internen Benutzern die Verwendung der P2P-Dateiübertragung gestatten, aber die Dateiübertragung mit Verbundpartnern blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="4eaa2-110">Für dieses Szenario müssten Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="4eaa2-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="4eaa2-111">Weisen Sie den Benutzern in Ihrer Organisation eine konferenzrichtlinie mit aktivierter P2P-Dateiübertragung (_EnableP2PFileTransfer_ festgelegt auf " _true_") zu.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="4eaa2-112">Erstellen Sie eine globale Richtlinie für externe Benutzerkommunikation, um externe P2P-Dateiübertragungen zu blockieren (_EnableP2PFileTransfer_ auf " _false_" festgelegt), und weisen Sie Sie einem Benutzer in Ihrer Organisation zu.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="4eaa2-113">Weitere Informationen zu diesen Einstellungen finden Sie [hier](https://technet.microsoft.com/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="4eaa2-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="4eaa2-114">Wenn ein Verbundbenutzer außerhalb Ihrer Organisation versucht, eine Datei an einen Benutzer zu senden, auf den die Richtlinie angewendet wurde, wird der Fehler " **Übertragung fehlgeschlagen** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="4eaa2-115">Und wenn ein Benutzer versucht, eine Datei zu senden, wird der Fehler " **Dateiübertragung ist deaktiviert** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="4eaa2-116">Damit dies funktioniert, muss der Benutzer eine unterstützte Version einer 2016-Klick-und-Los-Skype for Business-App verwenden, die ihn unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="4eaa2-117">Die folgende Mindestversion von Skype for Business 2016 Klick-und-Los-Client ist erforderlich:</span><span class="sxs-lookup"><span data-stu-id="4eaa2-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="4eaa2-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4eaa2-118">**Type**</span></span>|<span data-ttu-id="4eaa2-119">**Veröffentlichungsdatum**</span><span class="sxs-lookup"><span data-stu-id="4eaa2-119">**Release date**</span></span>|<span data-ttu-id="4eaa2-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="4eaa2-120">**Version**</span></span>|<span data-ttu-id="4eaa2-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="4eaa2-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4eaa2-122">First Release für aktuellen Kanal</span><span class="sxs-lookup"><span data-stu-id="4eaa2-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="4eaa2-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="4eaa2-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="4eaa2-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="4eaa2-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="4eaa2-125">Version 1611 (Build 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="4eaa2-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="4eaa2-126">Aktueller Kanal</span><span class="sxs-lookup"><span data-stu-id="4eaa2-126">Current Channel</span></span>  <br/> |<span data-ttu-id="4eaa2-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="4eaa2-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="4eaa2-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="4eaa2-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="4eaa2-129">Version 1611 (Build 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="4eaa2-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="4eaa2-130">Verzögerter Kanal</span><span class="sxs-lookup"><span data-stu-id="4eaa2-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="4eaa2-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="4eaa2-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="4eaa2-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="4eaa2-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="4eaa2-133">Version 1609 (Build 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="4eaa2-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="4eaa2-134">Benutzer, die ältere Versionen von Skype for Business-Windows-Apps oder Mac-Clients verwenden, können weiterhin Dateien übertragen.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="4eaa2-135">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eaa2-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="4eaa2-136">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="4eaa2-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="4eaa2-137">Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="4eaa2-138">Überprüfen Sie die Version, indem Sie im **Windows PowerShell** _-Fenster Get-Host_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="4eaa2-139">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="4eaa2-140">Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="4eaa2-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="4eaa2-141">Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="4eaa2-142">Außerdem müssen Sie das Windows PowerShell-Modul für Teams installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="4eaa2-143">Wenn Sie weitere Informationen benötigen, lesen Sie [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="4eaa2-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="4eaa2-144">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="4eaa2-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="4eaa2-145">Vom **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="4eaa2-146">Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Ihrem Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4eaa2-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="4eaa2-147">Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="4eaa2-148">Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="4eaa2-149">Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4eaa2-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="4eaa2-150">Deaktivieren von P2P-Dateiübertragungen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4eaa2-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="4eaa2-151">Standardmäßig ist _EnableP2PFileTransfer_ in der globalen Richtlinie der Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="4eaa2-152">Bei der Erstellung wurden den Benutzern die _BposSAllModality_ -Richtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="4eaa2-153">Um P2P-Übertragungen innerhalb Ihrer Organisation zu ermöglichen, aber externe Dateiübertragungen an eine andere Organisation zu blockieren, müssen Sie Sie nur auf globaler Ebene ändern.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="4eaa2-154">Führen Sie dazu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4eaa2-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="4eaa2-155">Deaktivieren von P2P-Dateiübertragungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="4eaa2-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="4eaa2-156">Sie können dies auf einen Benutzer anwenden, indem Sie eine neue Richtlinie erstellen und diesem Benutzer erteilen.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="4eaa2-157">Führen Sie dazu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4eaa2-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4eaa2-158">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="4eaa2-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4eaa2-159">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4eaa2-160">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4eaa2-161">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4eaa2-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4eaa2-162">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4eaa2-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4eaa2-163">Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eaa2-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4eaa2-164">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4eaa2-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4eaa2-165">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4eaa2-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4eaa2-166">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eaa2-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4eaa2-167">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4eaa2-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4eaa2-168">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4eaa2-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4eaa2-169">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4eaa2-169">Related topics</span></span>
[<span data-ttu-id="4eaa2-170">Erstellen von benutzerdefinierten externen Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4eaa2-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="4eaa2-171">Einrichten von Clientrichtlinien für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4eaa2-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="4eaa2-172">Einrichten von Konferenzrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="4eaa2-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
