---
title: Verbinden von netzwerkregionen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Sie können die Verbindungen zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) konfigurieren. '
ms.openlocfilehash: 4ea6ddcc72d2cadea32608288d1db93ba8505aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884684"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="ae239-103">Verknüpfen von Netzwerkregionen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ae239-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="ae239-104">Sie können die Verbindungen zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae239-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="ae239-105">Verwenden Sie in den Abschnitten in diesem Artikel, um Newtwork Informationen zu netzwerkregionenverbindungen anzeigen oder konfigurieren oder Löschen von Netwrok Region Verknüpfungen.</span><span class="sxs-lookup"><span data-stu-id="ae239-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="ae239-106">Informationen zu netzwerkregionenverbindungen anzeigen</span><span class="sxs-lookup"><span data-stu-id="ae239-106">View network region link information</span></span> 

<span data-ttu-id="ae239-107">Sie können zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) Links anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae239-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="ae239-108">Regionen in einem Netzwerk sind über Netzwerkkonnektivität (WAN) physischen WAN verknüpft.</span><span class="sxs-lookup"><span data-stu-id="ae239-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="ae239-109">Sie können die Skype Business Server-Systemsteuerung verwenden, um einer vorhandenen Verknüpfung zwischen zwei netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae239-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ae239-110">So zeigen Sie eine netzwerkregionenverbindung in Skype Business Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="ae239-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ae239-111">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ae239-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae239-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae239-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ae239-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="ae239-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="ae239-114">Klicken Sie auf der Seite **Regionenverbindung** auf die regionenverbindung, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae239-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="ae239-115">Sie können nur Informationen zu einer regionenverbindung zu einem Zeitpunkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae239-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="ae239-116">Wählen Sie im Menü **Bearbeiten** die **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ae239-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ae239-117">Anzeigen von Informationen zu netzwerkregionenverbindungen mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="ae239-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ae239-118">Sie können mithilfe von Windows PowerShell und das Cmdlet **Get-CsNetworkRegionLink** netzwerkregionenverbindungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae239-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="ae239-119">Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ae239-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="ae239-120">Informationen zu netzwerkregionenverbindungen anzeigen</span><span class="sxs-lookup"><span data-stu-id="ae239-120">To view network region link information</span></span>

  - <span data-ttu-id="ae239-121">Um Informationen über alle netzwerkregionenverbindungen anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="ae239-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="ae239-122">Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="ae239-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="ae239-123">Weitere Informationen hierzu finden Sie unter [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="ae239-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="ae239-124">Konfigurieren von netzwerkregionenverbindungen</span><span class="sxs-lookup"><span data-stu-id="ae239-124">Configure network region links</span></span> 

<span data-ttu-id="ae239-125">Sie können die Verbindungen zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae239-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="ae239-126">Regionen in einem Netzwerk sind über Netzwerkkonnektivität (WAN) physischen WAN verknüpft.</span><span class="sxs-lookup"><span data-stu-id="ae239-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="ae239-127">Die Skype Business Server-Systemsteuerung können Sie eine Verbindung zwischen zwei netzwerkregionen definieren und die Netzwerkbandbreite ist eingeschränkt auf audio und video Verbindungen zwischen diesen Regionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="ae239-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="ae239-128">Erstellen Sie eine netzwerkregionenverbindung</span><span class="sxs-lookup"><span data-stu-id="ae239-128">To create a network region link</span></span>

1.  <span data-ttu-id="ae239-129">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ae239-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae239-130">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae239-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ae239-131">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="ae239-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="ae239-132">Klicken Sie auf der Seite **Regionenverbindung** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="ae239-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="ae239-133">Geben Sie in **Neue Regionenverbindung**einen Wert in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="ae239-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ae239-134">Dieser Wert muss innerhalb Ihrer Skype für Business Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="ae239-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="ae239-135">Aus der **netzwerkregion \#1** Dropdown-Listenfeld, wählen Sie eine der zwei Regionen aus, die verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="ae239-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="ae239-136">Aus der **netzwerkregion \#2** Dropdown-Liste, wählen Sie die anderen Region verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae239-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="ae239-137">Diese Region muss die Region für die netzwerkregion ausgewählt anders \#1.</span><span class="sxs-lookup"><span data-stu-id="ae239-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="ae239-138">(Optional) Wenn Sie die Netzwerkbandbreite ist eingeschränkt auf Audio- oder Videoinhalten Anrufe zwischen diesen Regionen platzieren möchten, wählen Sie ein bandbreitenrichtlinienprofil aus der Dropdownliste **bandbreitenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="ae239-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="ae239-139">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ae239-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="ae239-140">So ändern Sie eine netzwerkregionenverbindung</span><span class="sxs-lookup"><span data-stu-id="ae239-140">To modify a network region link</span></span>

1.  <span data-ttu-id="ae239-141">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ae239-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae239-142">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae239-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ae239-143">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="ae239-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="ae239-144">Klicken Sie auf der Seite **Regionenverbindung** auf die regionenverbindung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ae239-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="ae239-145">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ae239-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ae239-146">Im **Abschnitt Regionenverbindung bearbeiten**können Sie ändern, der die verknüpften Regionen oder das bandbreitenrichtlinienprofil für diese Verknüpfung.</span><span class="sxs-lookup"><span data-stu-id="ae239-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="ae239-147">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ae239-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="ae239-148">Löschen von netzwerkregionenverbindungen</span><span class="sxs-lookup"><span data-stu-id="ae239-148">Delete network region links</span></span>

<span data-ttu-id="ae239-149">Sie können die Verbindungen zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae239-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="ae239-150">Regionen in einem Netzwerk sind über Netzwerkkonnektivität (WAN) physischen WAN verknüpft.</span><span class="sxs-lookup"><span data-stu-id="ae239-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="ae239-151">Die Skype Business Server-Systemsteuerung können Sie um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ae239-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="ae239-152">So löschen Sie eine netzwerkregionenverbindung</span><span class="sxs-lookup"><span data-stu-id="ae239-152">To delete a network region link</span></span>

1.  <span data-ttu-id="ae239-153">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ae239-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae239-154">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae239-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ae239-155">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="ae239-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="ae239-156">Klicken Sie auf der Seite **Regionenverbindung** auf die regionenverbindung, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae239-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ae239-157">Sie können mehrere regionenverbindung zu einem Zeitpunkt löschen.</span><span class="sxs-lookup"><span data-stu-id="ae239-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="ae239-158">Zu diesem Zweck drücken Sie STRG, und wählen Sie mehrere regionenverbindungen, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="ae239-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="ae239-159">Oder, um alle regionenverbindungen auszuwählen, klicken Sie auf <STRONG>Alles markieren</STRONG> im Menü <STRONG>Bearbeiten</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ae239-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="ae239-160">Wählen Sie im Menü **Bearbeiten** **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="ae239-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="ae239-161">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae239-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="ae239-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae239-162">See Also</span></span>

[<span data-ttu-id="ae239-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="ae239-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="ae239-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="ae239-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="ae239-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="ae239-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="ae239-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="ae239-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
