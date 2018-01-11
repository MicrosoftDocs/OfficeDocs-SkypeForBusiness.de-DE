---
title: "Skype-Besprechung Übertragung aktivieren"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Bevor die Personen in Ihrer Organisation Skype Besprechung übertragen verwenden können, müssen Sie ihn aktivieren. Zu diesem Zweck müssen Sie wissen, wie Sie mithilfe von Windows PowerShell. Wenn Sie Windows PowerShell nicht kennen, können Sie Einstellen von Microsoft-Partner können Sie diesen Schritt übergehen."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="c96f8-105">Skype-Besprechung Übertragung aktivieren</span><span class="sxs-lookup"><span data-stu-id="c96f8-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="c96f8-106">Bevor die Personen in Ihrer Organisation Skype Besprechung übertragen verwenden können, müssen Sie ihn aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c96f8-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="c96f8-107">Zu diesem Zweck müssen Sie wissen, wie Sie mithilfe von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c96f8-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="c96f8-108">Wenn Sie Windows PowerShell nicht kennen, können Sie Einstellen von einem [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) können Sie diesen Schritt übergehen.</span><span class="sxs-lookup"><span data-stu-id="c96f8-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c96f8-109">Skype-Besprechung Übertragung ist standardmäßig deaktiviert, da die Verteilung von Media-Inhalten einer broadcast Besprechung des Microsoft Azure Content Delivery Network (CDN) verwendet, um sehr hohe Skalierung auf Tausende von Personen, die einen Broadcast ansehen zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c96f8-109">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast.</span></span> <span data-ttu-id="c96f8-110">Die aufgeteilte Medieninhalte über das CDN übergeben wird verschlüsselt, und der CDN-Cache verfügt über eine begrenzte Lebensdauer.</span><span class="sxs-lookup"><span data-stu-id="c96f8-110">The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime.</span></span> <span data-ttu-id="c96f8-111">Darüber hinaus kann die Azure CDN-Komponente nicht noch alle Elemente der wortstammerkennung aus der EU-Datenschutzrichtlinie der EU-Modellklauseln entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c96f8-111">Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive.</span></span> <span data-ttu-id="c96f8-112">Aktivieren Sie dieses Feature, bestätigen Sie diesen Hinweis.</span><span class="sxs-lookup"><span data-stu-id="c96f8-112">By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="c96f8-113">Aktivieren Sie Skype Besprechung übertragen mithilfe der Skype für Business Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="c96f8-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="c96f8-114">Melden Sie sich mit Ihrem globalen Office 365-Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.</span><span class="sxs-lookup"><span data-stu-id="c96f8-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="c96f8-115">Wechseln Sie in das Office 365 Admin Center zu **Admin zentriert** > **Skype für Unternehmen**.</span><span class="sxs-lookup"><span data-stu-id="c96f8-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c96f8-116">Wechseln Sie in der **Skype für Business Administrationscenter**zu **onlinebesprechungen** > **Besprechungen übertragen**, und wählen Sie dann **Aktivieren Skype Besprechung übertragen**.</span><span class="sxs-lookup"><span data-stu-id="c96f8-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="c96f8-117">Aktivieren von Skype Besprechung übertragen von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c96f8-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="c96f8-118">Stellen Sie sicher, dass Sie Version 3.0 oder höher von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c96f8-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="c96f8-119">Um sicherzustellen, dass Sie Version 3.0 oder höher ausgeführt werden: **Im Menü Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c96f8-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c96f8-120">Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.</span><span class="sxs-lookup"><span data-stu-id="c96f8-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="c96f8-p104">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c96f8-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="c96f8-p105">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c96f8-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="c96f8-127">Wählen Sie im **Menü Start**wählen Sie **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c96f8-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="c96f8-128">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="c96f8-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="c96f8-129">Bestätigen Sie die aktuelle Konfiguration Skype Besprechung übertragen werden durch ausführen:</span><span class="sxs-lookup"><span data-stu-id="c96f8-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="c96f8-130">Stellen Sie sicher, dass der Parameter _EnableBroadcastMeeting_ , um festgelegt ist `False`.</span><span class="sxs-lookup"><span data-stu-id="c96f8-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype Besprechung übertragen aktivieren Organisation-Cmdlet.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="c96f8-132">Aktivieren Sie Skype Besprechung übertragen für Ihre Organisation durch ausführen:</span><span class="sxs-lookup"><span data-stu-id="c96f8-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="c96f8-133">Sie können überprüfen, ob die Einstellung aktiviert ist, durch Ausführen von `Get-CsBroadcastMeetingConfiguration` erneut.</span><span class="sxs-lookup"><span data-stu-id="c96f8-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype-Besprechung Übertragung aktivieren Organisation-Cmdlet.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="c96f8-135">Nachdem Sie die Änderung vornehmen, kann es bis zu einer Stunde dauern, bis im Portal Skype Besprechung übertragen wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="c96f8-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="c96f8-136">Die Benutzer können jetzt broadcast Besprechungen mit anderen Benutzern in Ihrem Unternehmen halten.</span><span class="sxs-lookup"><span data-stu-id="c96f8-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="c96f8-137">Um diese Schritte zu erhalten, zeigen sie auf [Was ist eine Skype Besprechung übertragen?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="c96f8-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="c96f8-138">Konfigurieren des Netzwerks, um Besprechungen mit externen Teilnehmern senden</span><span class="sxs-lookup"><span data-stu-id="c96f8-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="c96f8-139">Wenn eine Firewall, und Sie halten Übertragungen mit Personen außerhalb Ihres Unternehmens (, die keiner verbundgeschäftspartner sind) möchten, müssen Sie Ihr Netzwerk anhand der folgenden Schritte konfigurieren: [Richten Sie Ihr Netzwerk für Skype Besprechung übertragen werden](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="c96f8-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="c96f8-140">Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.</span><span class="sxs-lookup"><span data-stu-id="c96f8-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="c96f8-141">Wenn Sie diesen Schritt überspringen und stattdessen ein anderes Unternehmen, Ihre Verbund hinzufügen, finden Sie unter [wenden Sie sich an externe Skype für Unternehmensbenutzer durch Benutzer zulassen](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="c96f8-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="c96f8-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c96f8-142">Related topics</span></span>

[<span data-ttu-id="c96f8-143">Eine Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c96f8-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="c96f8-144">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c96f8-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

