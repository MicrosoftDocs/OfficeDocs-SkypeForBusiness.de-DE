---
title: Verknüpfen von netzwerkregionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren. '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817524"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="3d50e-103">Verknüpfen von Netzwerkregionen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3d50e-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="3d50e-104">Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3d50e-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3d50e-105">Verwenden Sie die Abschnitte in diesem Artikel, um die Verknüpfungsinformationen für den Molch Bereich anzuzeigen oder Brücker Regions Verknüpfungen zu konfigurieren oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="3d50e-106">Link Informationen zum Anzeigen von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="3d50e-106">View network region link information</span></span> 

<span data-ttu-id="3d50e-107">Sie können die Verknüpfungen zwischen zwei netzwerkregionen im Rahmen der Anrufsteuerung (Call Admission Control, CAC) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3d50e-108">Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden.</span><span class="sxs-lookup"><span data-stu-id="3d50e-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="3d50e-109">Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="3d50e-110">So zeigen Sie einen Link zur netzwerkregion in der Skype for Business Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="3d50e-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="3d50e-111">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3d50e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d50e-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3d50e-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Link**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3d50e-114">Klicken Sie auf der Seite **Regions Link** auf den Link Region, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="3d50e-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="3d50e-115">Sie können nur Informationen zu einem Regions Link gleichzeitig anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="3d50e-116">Wählen Sie im Menü **Bearbeiten** die Option **Details anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="3d50e-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3d50e-117">Anzeigen von Link Informationen zu netzwerkregionen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3d50e-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3d50e-118">Sie können Netzwerk Regions Verknüpfungen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsNetworkRegionLink** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="3d50e-119">Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="3d50e-120">So zeigen Sie netzwerkregion-Verknüpfungsinformationen an</span><span class="sxs-lookup"><span data-stu-id="3d50e-120">To view network region link information</span></span>

  - <span data-ttu-id="3d50e-121">Wenn Sie Informationen zu allen ihren netzwerkregion-Links anzeigen möchten, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="3d50e-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="3d50e-122">Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="3d50e-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="3d50e-123">Ausführliche Informationen finden Sie unter [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="3d50e-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="3d50e-124">Konfigurieren von Netzwerk Regions Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="3d50e-124">Configure network region links</span></span> 

<span data-ttu-id="3d50e-125">Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3d50e-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3d50e-126">Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden.</span><span class="sxs-lookup"><span data-stu-id="3d50e-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="3d50e-127">Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine Verknüpfung zwischen zwei netzwerkregionen zu definieren und die Bandbreiteneinschränkungen für Audio-und Videoverbindungen zwischen diesen Regionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="3d50e-128">So erstellen Sie eine Netzwerk Regions Verknüpfung</span><span class="sxs-lookup"><span data-stu-id="3d50e-128">To create a network region link</span></span>

1.  <span data-ttu-id="3d50e-129">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3d50e-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d50e-130">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3d50e-131">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Link**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3d50e-132">Klicken Sie auf der Seite **Regions Link** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="3d50e-133">Geben Sie im Feld **neuer Bereich**einen Wert in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="3d50e-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="3d50e-134">Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3d50e-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="3d50e-135">Wählen Sie in der Dropdownliste **netzwerkregion \#1** einen der beiden zu verknüpfende Regionen aus.</span><span class="sxs-lookup"><span data-stu-id="3d50e-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="3d50e-136">Wählen Sie in der Dropdownliste **netzwerkregion \#2** die andere Region aus, die verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="3d50e-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="3d50e-137">Diese Region muss sich von der für netzwerkregion \#1 ausgewählten Region unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3d50e-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="3d50e-138">Optional Wenn Sie Bandbreiteneinschränkungen für Audio-oder Videoanrufe zwischen diesen Regionen festlegen möchten, wählen Sie in der Dropdownliste **bandbreitenrichtlinie** ein Profil für Bandbreitenrichtlinien aus.</span><span class="sxs-lookup"><span data-stu-id="3d50e-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="3d50e-139">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="3d50e-140">So ändern Sie eine Netzwerk Regions Verknüpfung</span><span class="sxs-lookup"><span data-stu-id="3d50e-140">To modify a network region link</span></span>

1.  <span data-ttu-id="3d50e-141">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3d50e-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d50e-142">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3d50e-143">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Link**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3d50e-144">Klicken Sie auf der Seite **Regions Link** auf den zu ändernden Bereichs Link.</span><span class="sxs-lookup"><span data-stu-id="3d50e-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="3d50e-145">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3d50e-146">Im **Link "Region bearbeiten**" können Sie die verknüpften Regionen oder das bandbreitenrichtlinienprofil für diesen Link ändern.</span><span class="sxs-lookup"><span data-stu-id="3d50e-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="3d50e-147">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="3d50e-148">Löschen von Netzwerk Regions Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="3d50e-148">Delete network region links</span></span>

<span data-ttu-id="3d50e-149">Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3d50e-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3d50e-150">Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden.</span><span class="sxs-lookup"><span data-stu-id="3d50e-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="3d50e-151">Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="3d50e-152">So löschen Sie eine Netzwerk Regions Verknüpfung</span><span class="sxs-lookup"><span data-stu-id="3d50e-152">To delete a network region link</span></span>

1.  <span data-ttu-id="3d50e-153">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3d50e-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d50e-154">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3d50e-155">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Link**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3d50e-156">Klicken Sie auf der Seite **Regions Link** auf den zu löschenden Regions Link.</span><span class="sxs-lookup"><span data-stu-id="3d50e-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="3d50e-157">Sie können mehrere Regions Verknüpfungen gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="3d50e-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="3d50e-158">Drücken Sie dazu STRG, und wählen Sie bei gedrückter STRG-Taste mehrere Regions Links aus.</span><span class="sxs-lookup"><span data-stu-id="3d50e-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="3d50e-159">Wenn Sie alle Regions Verknüpfungen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3d50e-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="3d50e-160">Wählen Sie im Menü **Bearbeiten** die Option **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="3d50e-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="3d50e-161">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d50e-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="3d50e-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d50e-162">See Also</span></span>

[<span data-ttu-id="3d50e-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3d50e-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="3d50e-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3d50e-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="3d50e-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3d50e-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="3d50e-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3d50e-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
