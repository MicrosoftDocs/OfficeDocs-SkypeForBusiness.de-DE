---
title: Verwalten von netzwerkregionsrouten
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eine netzwerkregionenroute definiert die Route zwischen zwei netzwerkregionen. Jedem netzwerkregionenpaar in der die Bereitstellung der anrufsteuerung erfordert eine netzwerkregionenroute.
ms.openlocfilehash: 98d7f0ce8f6cb89aa443c5dc8863afd34c355ff3
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223157"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="068d1-104">Verwalten von netzwerkregionsrouten in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="068d1-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="068d1-105">Eine *netzwerkregionenroute* definiert die Route zwischen zwei netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="068d1-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="068d1-106">Jedem netzwerkregionenpaar in der die Bereitstellung der anrufsteuerung erfordert eine netzwerkregionenroute.</span><span class="sxs-lookup"><span data-stu-id="068d1-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="068d1-107">So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="068d1-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="068d1-108">Verwenden Sie die Verfahren in diesem Artilce zum Anzeigen, erstellen, ändern oder Löschen von netzwerkregionenrouten.</span><span class="sxs-lookup"><span data-stu-id="068d1-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="068d1-109">Informationen zur Ansicht netzwerkregion route</span><span class="sxs-lookup"><span data-stu-id="068d1-109">View network region route information</span></span> 

<span data-ttu-id="068d1-110">Jeder Region innerhalb einer Call Admission Control (, CAC) Konfiguration benötigen eine Möglichkeit zum Zugriff auf allen anderen Regionen.</span><span class="sxs-lookup"><span data-stu-id="068d1-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="068d1-111">Während die regionenverbindungen bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route welche verknüpften Pfad, der die Verbindung von einer Region zur anderen nimmt wird.</span><span class="sxs-lookup"><span data-stu-id="068d1-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="068d1-112">Verwenden Sie die folgenden Verfahren zum Anzeigen von vorhandenen netzwerkregionsrouten in Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="068d1-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="068d1-113">Zum Anzeigen von Informationen zur netzwerkregion Route in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="068d1-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="068d1-114">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="068d1-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="068d1-115">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="068d1-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="068d1-116">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="068d1-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="068d1-117">Klicken Sie auf der Seite **Regionenroute** auf die regionenroute, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="068d1-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="068d1-118">Sie können nur jeweils eine regionsroute anzeigen.</span><span class="sxs-lookup"><span data-stu-id="068d1-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="068d1-119">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="068d1-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="068d1-120">Anzeigen von Informationen zu Netzwerkregionsrouten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="068d1-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="068d1-121">Informationen zur netzwerkregion Route kann mithilfe von Windows PowerShell und das Cmdlet Get-CsNetworkInterRegionRoute angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="068d1-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="068d1-122">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="068d1-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="068d1-123">So zeigen Sie Informationen zur netzwerkregion Route an</span><span class="sxs-lookup"><span data-stu-id="068d1-123">To view network region route information</span></span>

  - <span data-ttu-id="068d1-124">Informationen zu allen netzwerkregionsrouten anzeigen möchten, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="068d1-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="068d1-125">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="068d1-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="068d1-126">Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="068d1-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="068d1-127">Erstellen oder Ändern von netzwerkregionsrouten</span><span class="sxs-lookup"><span data-stu-id="068d1-127">Create or modify network region routes</span></span>

<span data-ttu-id="068d1-128">Jeder Region innerhalb einer Call Admission Control (, CAC) Konfiguration benötigen eine Möglichkeit zum Zugriff auf allen anderen Regionen.</span><span class="sxs-lookup"><span data-stu-id="068d1-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="068d1-129">Während die regionenverbindungen bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route welche verknüpften Pfad, der die Verbindung von einer Region zur anderen nimmt wird.</span><span class="sxs-lookup"><span data-stu-id="068d1-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="068d1-130">Die Skype Business Server-Systemsteuerung können Sie netzwerkregionsrouten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="068d1-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="068d1-131">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen eine netzwerkregionenroute.</span><span class="sxs-lookup"><span data-stu-id="068d1-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="068d1-132">Verwenden Sie dieses Thema zum Erstellen oder Ändern einer netzwerkregionenroute.</span><span class="sxs-lookup"><span data-stu-id="068d1-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="068d1-133">Erstellen Sie eine netzwerkregionenroute</span><span class="sxs-lookup"><span data-stu-id="068d1-133">To create a network region route</span></span>

1.  <span data-ttu-id="068d1-134">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="068d1-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="068d1-135">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="068d1-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="068d1-136">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="068d1-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="068d1-137">Klicken Sie auf der Seite **Regionenroute** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="068d1-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="068d1-138">Geben Sie in **neue Regionenroute**einen Wert in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="068d1-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="068d1-139">Dieser Wert muss innerhalb Ihrer Skype für Business Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="068d1-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="068d1-140">Aus der **netzwerkregion \#1** Dropdown-Listenfeld, wählen Sie eine der zwei Regionen aus, die über diese Route verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="068d1-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="068d1-141">Aus der **netzwerkregion \#2** Dropdown-Liste, wählen Sie die anderen Region für diese Route.</span><span class="sxs-lookup"><span data-stu-id="068d1-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="068d1-142">Diese Region muss die Region für die netzwerkregion ausgewählt anders \#1.</span><span class="sxs-lookup"><span data-stu-id="068d1-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="068d1-143">Verwenden Sie das Listenfeld **netzwerkregionenverbindungen** , regionenverbindungen der Route hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="068d1-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="068d1-144">Klicken Sie auf die Schaltfläche **Hinzufügen** , um die Seite **Regionenverbindung** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="068d1-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="068d1-145">Klicken Sie auf einer regionenverbindung Route hinzufügen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="068d1-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="068d1-146">Weiterhin klicken Sie auf die Schaltfläche **Hinzufügen** , um weitere Verbindungen hinzuzufügen, oder wählen Sie einen Link, und klicken Sie auf **Entfernen** , um eine Verbindung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="068d1-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="068d1-147">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="068d1-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="068d1-148">So ändern Sie eine netzwerkregionenroute</span><span class="sxs-lookup"><span data-stu-id="068d1-148">To modify a network region route</span></span>

1.  <span data-ttu-id="068d1-149">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="068d1-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="068d1-150">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="068d1-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="068d1-151">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="068d1-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="068d1-152">Klicken Sie auf der Seite **Regionenroute** auf die regionenroute, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="068d1-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="068d1-153">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="068d1-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="068d1-154">In **Regionenroute bearbeiten**können Sie über diese Route verbundenen Regionen und die der Route zugeordneten regionenverbindungen ändern.</span><span class="sxs-lookup"><span data-stu-id="068d1-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="068d1-155">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="068d1-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="068d1-156">Löschen von vorhandenen netzwerkregionsrouten</span><span class="sxs-lookup"><span data-stu-id="068d1-156">Delete existing network region routes</span></span>

<span data-ttu-id="068d1-157">Jeder Region innerhalb einer Call Admission Control (, CAC) Konfiguration benötigen eine Möglichkeit zum Zugriff auf allen anderen Regionen.</span><span class="sxs-lookup"><span data-stu-id="068d1-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="068d1-158">Während die regionenverbindungen bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route welche verknüpften Pfad, der die Verbindung von einer Region zur anderen nimmt wird.</span><span class="sxs-lookup"><span data-stu-id="068d1-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="068d1-159">Die Skype Business Server-Systemsteuerung können Sie netzwerkregionsrouten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="068d1-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="068d1-160">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen eine netzwerkregionenroute.</span><span class="sxs-lookup"><span data-stu-id="068d1-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="068d1-161">Verwenden Sie in diesem Thema, um vorhandene netzwerkregionsrouten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="068d1-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="068d1-162">So löschen Sie eine netzwerkregionenroute</span><span class="sxs-lookup"><span data-stu-id="068d1-162">To delete a network region route</span></span>

1.  <span data-ttu-id="068d1-163">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="068d1-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="068d1-164">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="068d1-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="068d1-165">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="068d1-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="068d1-166">Klicken Sie auf der Seite **Regionenroute** auf die regionenroute, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="068d1-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="068d1-167">Sie können mehrere regionenroute zu einem Zeitpunkt löschen.</span><span class="sxs-lookup"><span data-stu-id="068d1-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="068d1-168">Zu diesem Zweck, drücken Sie STRG, und wählen Sie mehrere Routen zwischen Regionen aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="068d1-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="068d1-169">Oder, um alle Routen zwischen Regionen auszuwählen, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="068d1-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="068d1-170">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="068d1-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="068d1-171">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="068d1-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="068d1-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="068d1-172">See Also</span></span>

[<span data-ttu-id="068d1-173">Verwalten von netzwerkregionen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="068d1-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="068d1-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="068d1-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="068d1-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="068d1-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="068d1-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="068d1-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="068d1-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="068d1-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  