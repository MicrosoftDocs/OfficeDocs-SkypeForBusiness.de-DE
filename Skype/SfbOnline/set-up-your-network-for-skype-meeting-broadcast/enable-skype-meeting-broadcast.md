---
title: Aktivieren von Skype-Livekonferenz
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Bevor die Personen in Ihrer Organisation Skype-Live Konferenz verwenden können, müssen Sie Sie aktivieren. Dazu müssen Sie wissen, wie Sie Windows PowerShell verwenden. Wenn Sie keine Erfahrungen mit Windows PowerShell haben, sollten Sie möglicherweise einen Microsoft-Partner für diese Aufgabe heranziehen.
ms.openlocfilehash: f1a672bc8d3b0ce957a32691270293551e1a1409
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494035"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="4dc8e-105">Aktivieren von Skype-Livekonferenz</span><span class="sxs-lookup"><span data-stu-id="4dc8e-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="4dc8e-106">Bevor die Personen in Ihrer Organisation Skype-Live Konferenz verwenden können, müssen Sie Sie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="4dc8e-107">Dazu müssen Sie wissen, wie Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="4dc8e-108">Wenn Sie keine Erfahrungen mit Windows PowerShell haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="4dc8e-109">Aktivieren von Skype-Livekonferenz im Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="4dc8e-109">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="4dc8e-110">![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="4dc8e-110">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="4dc8e-111">Melden Sie sich mit dem Konto Globaler Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-111">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="4dc8e-112">Navigieren Sie im „Office 365 Admin Center" zu **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-112">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="4dc8e-113">Wechseln Sie im **Skype for Business Admin Center**zu Besprechungen für **Online Besprechungen** > \*\*\*\*, und wählen Sie dann Skype-Live **Konferenz aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-113">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="4dc8e-114">Aktivieren von Skype-Livekonferenz mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dc8e-114">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="4dc8e-115">Überprüfen Sie, ob Sie Version 3.0 oder höher von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-115">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="4dc8e-116">So überprüfen Sie, ob Sie Version 3.0 oder höher benutzen: **Startmenü** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-116">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="4dc8e-117">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-117">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="4dc8e-p103">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="4dc8e-p104">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="4dc8e-124">Wählen Sie im **Startmenü**die Option **Windows PowerShell**aus.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-124">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="4dc8e-125">Stellen Sie im **Windows PowerShell**-Fenster eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4dc8e-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="4dc8e-126">Bestätigen Sie Ihre aktuelle Skype-Livekonferenz-Konfiguration, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4dc8e-126">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="4dc8e-127">Überprüfen Sie, ob der Parameter  _EnableBroadcastMeeting_ auf `False` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-127">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="4dc8e-129">Aktivieren Sie Skype-Livekonferenz für Ihr Unternehmen, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4dc8e-129">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="4dc8e-130">Sie können überprüfen, ob die Einstellung aktiviert ist `Get-CsBroadcastMeetingConfiguration` , indem Sie erneut ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-130">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="4dc8e-132">Nach der Änderung kann es bis zu einer Stunde dauern, bis sie im Skype-Livekonferenz-Portal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-132">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="4dc8e-p105">Ihre Benutzer können jetzt Livekonferenzen mit anderen Benutzern in Ihrem Unternehmen durchführen. Um Ihre Benutzer bei der Durchführung zu unterstützen, verweisen Sie sie auf [Was ist eine Skype-Livekonferenz?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="4dc8e-p105">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="4dc8e-135">Konfigurieren Ihres Netzwerks zur Durchführung von Livekonferenzen mit externen Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="4dc8e-135">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="4dc8e-136">Wenn Sie über eine Firewall verfügen und Konferenzen mit Personen außerhalb Ihres Unternehmens (die nicht zum Unternehmensverbund gehören) durchführen möchten, müssen Sie Ihr Netzwerk unter Befolgung dieser Anweisungen konfigurieren: [Einrichten Ihres Netzwerks für Skype-Livekonferenz](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="4dc8e-136">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="4dc8e-137">Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-137">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="4dc8e-138">Um diesen Schritt zu überspringen und stattdessen Ihrem Verbund ein anderes Unternehmen hinzuzufügen, führen Sie die Schritte unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) aus.</span><span class="sxs-lookup"><span data-stu-id="4dc8e-138">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="4dc8e-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4dc8e-139">Related topics</span></span>

[<span data-ttu-id="4dc8e-140">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4dc8e-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="4dc8e-141">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4dc8e-141">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 