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
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Bevor die Personen in Ihrer Organisation Skype-Live Konferenz verwenden können, müssen Sie Sie aktivieren. Dazu müssen Sie wissen, wie Sie Windows PowerShell verwenden. Wenn Sie Windows PowerShell nicht kennen, sollten Sie einen Microsoft-Partner anheuern, um diesen Schritt für Sie durchführen zu können.
ms.openlocfilehash: 20d3671beb608413c5d0d61f599f65a47b55732d
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753430"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="e4600-105">Aktivieren von Skype-Livekonferenz</span><span class="sxs-lookup"><span data-stu-id="e4600-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4600-106">Das Microsoft Teams Admin Center hat das Skype for Business Admin Center (Legacy Portal) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e4600-106">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="e4600-107">Alle Einstellungen für die Verwaltung von Skype for Business sind jetzt im Team Admin Center.</span><span class="sxs-lookup"><span data-stu-id="e4600-107">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="e4600-108">Sie müssen der [Azure AD-Administratorrolle](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) des globalen Administrators oder des Skype for Business-Administrators zugewiesen sein, um Skype for Business-Funktionen im Team Admin Center verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="e4600-108">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="e4600-109">Weitere Informationen finden Sie unter [Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="e4600-109">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="e4600-110">Bevor die Personen in Ihrer Organisation Skype-Live Konferenz verwenden können, müssen Sie Sie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e4600-110">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="e4600-111">Dazu müssen Sie wissen, wie Sie Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4600-111">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="e4600-112">Wenn Sie keine Erfahrungen mit Windows PowerShell haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.</span><span class="sxs-lookup"><span data-stu-id="e4600-112">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="e4600-113">Aktivieren von Skype-Livekonferenz im Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="e4600-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="e4600-114">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="e4600-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="e4600-115">Registrieren Sie sich mit ihrem globalen Administratorkonto oder dem Skype for Business-Administratorkonto unter [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="e4600-115">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="e4600-116">Wechseln Sie im Admin Center zu **Admin Center**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="e4600-116">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="e4600-117">Wechseln Sie im **Team Admin Center**zu **Legacy Portal**  >  **Online Besprechungen**  >  **Broadcast meetings**, und wählen Sie dann Skype-Live **Konferenz aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e4600-117">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="e4600-118">Aktivieren von Skype-Livekonferenz mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4600-118">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="e4600-119">Überprüfen Sie, ob Sie Version 3.0 oder höher von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="e4600-119">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="e4600-120">So überprüfen Sie, ob Sie Version 3.0 oder höher benutzen: **Startmenü** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e4600-120">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="e4600-121">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="e4600-121">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="e4600-122">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="e4600-122">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="e4600-123">Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="e4600-123">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="e4600-124">Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="e4600-124">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="e4600-p105">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="e4600-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="e4600-128">Wählen Sie im **Startmenü**die Option **Windows PowerShell**aus.</span><span class="sxs-lookup"><span data-stu-id="e4600-128">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="e4600-129">Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Ihrem Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="e4600-129">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="e4600-130">Bestätigen Sie Ihre aktuelle Skype-Livekonferenz-Konfiguration, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="e4600-130">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="e4600-131">Überprüfen Sie, ob der Parameter  _EnableBroadcastMeeting_ auf `False` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4600-131">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="e4600-133">Aktivieren Sie Skype-Livekonferenz für Ihr Unternehmen, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="e4600-133">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="e4600-134">Sie können überprüfen, ob die Einstellung aktiviert ist, indem Sie erneut ausgeführt wird  `Get-CsBroadcastMeetingConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="e4600-134">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="e4600-136">Nach der Änderung kann es bis zu einer Stunde dauern, bis sie im Skype-Livekonferenz-Portal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e4600-136">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="e4600-p106">Ihre Benutzer können jetzt Livekonferenzen mit anderen Benutzern in Ihrem Unternehmen durchführen. Um Ihre Benutzer bei der Durchführung zu unterstützen, verweisen Sie sie auf [Was ist eine Skype-Livekonferenz?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="e4600-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="e4600-139">Konfigurieren Ihres Netzwerks zur Durchführung von Livekonferenzen mit externen Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="e4600-139">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="e4600-140">Wenn Sie über eine Firewall verfügen und Konferenzen mit Personen außerhalb Ihres Unternehmens (die nicht zum Unternehmensverbund gehören) durchführen möchten, müssen Sie Ihr Netzwerk unter Befolgung dieser Anweisungen konfigurieren: [Einrichten Ihres Netzwerks für Skype-Livekonferenz](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="e4600-140">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="e4600-141">Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.</span><span class="sxs-lookup"><span data-stu-id="e4600-141">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="e4600-142">Um diesen Schritt zu überspringen und stattdessen Ihrem Verbund ein anderes Unternehmen hinzuzufügen, führen Sie die Schritte unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) aus.</span><span class="sxs-lookup"><span data-stu-id="e4600-142">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="e4600-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e4600-143">Related topics</span></span>

[<span data-ttu-id="e4600-144">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e4600-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="e4600-145">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e4600-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
