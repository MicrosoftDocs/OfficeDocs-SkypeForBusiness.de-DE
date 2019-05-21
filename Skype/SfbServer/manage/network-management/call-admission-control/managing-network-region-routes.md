---
title: Verwalten von Routen im Netzwerkbereich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eine Netzwerk Regions Route definiert die Route zwischen zwei netzwerkregionen. Für jedes Paar von netzwerkregionen in der Bereitstellung für die Anrufsteuerung ist eine Netzwerk Regions Route erforderlich.
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279508"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="f9551-104">Verwalten von Netzwerkregionsrouten in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f9551-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="f9551-105">Eine *Netzwerk Regions Route* definiert die Route zwischen zwei netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="f9551-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="f9551-106">Für jedes Paar von netzwerkregionen in der Bereitstellung für die Anrufsteuerung ist eine Netzwerk Regions Route erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f9551-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="f9551-107">So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9551-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="f9551-108">Verwenden Sie die Verfahren in diesem Artilce, um Netzwerkbereichs Routen anzuzeigen, zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f9551-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="f9551-109">Anzeigen von Routeninformationen zu netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="f9551-109">View network region route information</span></span> 

<span data-ttu-id="f9551-110">Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9551-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="f9551-111">Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="f9551-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="f9551-112">Gehen Sie wie folgt vor, um vorhandene Netzwerkbereichs Routen in der Skype for Business Server-Systemsteuerung oder in der Skype for Business Server-Verwaltungsshell anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9551-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f9551-113">So zeigen Sie netzwerkregion-Routeninformationen in der Skype for Business Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="f9551-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f9551-114">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f9551-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9551-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9551-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f9551-116">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Route**.</span><span class="sxs-lookup"><span data-stu-id="f9551-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f9551-117">Klicken Sie auf der Seite **Route des Bereichs** auf die Route, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="f9551-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="f9551-118">Sie können jeweils nur eine Regions Route anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9551-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="f9551-119">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f9551-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f9551-120">Anzeigen von Routeninformationen des Netzwerkbereichs mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f9551-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f9551-121">Netzwerkregion-Routeninformationen können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkInterRegionRoute angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f9551-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="f9551-122">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f9551-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="f9551-123">So zeigen Sie netzwerkregion-Routeninformationen an</span><span class="sxs-lookup"><span data-stu-id="f9551-123">To view network region route information</span></span>

  - <span data-ttu-id="f9551-124">Wenn Sie Informationen zu allen Routen des Netzwerkbereichs anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="f9551-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="f9551-125">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="f9551-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="f9551-126">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="f9551-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="f9551-127">Erstellen oder Ändern von Netzwerkbereichs Routen</span><span class="sxs-lookup"><span data-stu-id="f9551-127">Create or modify network region routes</span></span>

<span data-ttu-id="f9551-128">Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9551-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="f9551-129">Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="f9551-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="f9551-130">Sie können die Skype for Business Server-Systemsteuerung verwenden, um Strecken des Netzwerkbereichs zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f9551-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="f9551-131">Über die Skype for Business Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="f9551-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="f9551-132">Verwenden Sie dieses Thema, um eine Netzwerk Regions Route zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f9551-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="f9551-133">So erstellen Sie eine Netzwerk Regions Route</span><span class="sxs-lookup"><span data-stu-id="f9551-133">To create a network region route</span></span>

1.  <span data-ttu-id="f9551-134">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f9551-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9551-135">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9551-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f9551-136">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Route**.</span><span class="sxs-lookup"><span data-stu-id="f9551-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f9551-137">Klicken Sie auf der Seite **Region Route** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="f9551-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="f9551-138">Geben \*\*\*\* Sie in das Feld Name einen Wert in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="f9551-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="f9551-139">Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f9551-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="f9551-140">Wählen Sie in der Dropdownliste **netzwerkregion \#1** einen der beiden Regionen aus, die mit dieser Route verbunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f9551-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="f9551-141">Wählen Sie in der Dropdownliste **netzwerkregion \#2** den anderen Bereich für diese Route aus.</span><span class="sxs-lookup"><span data-stu-id="f9551-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="f9551-142">Diese Region muss sich von der für netzwerkregion \#1 ausgewählten Region unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f9551-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="f9551-143">Verwenden Sie das Listenfeld **Netzwerk Gebiets Links** , um der Route Bereichs Links hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9551-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="f9551-144">Klicken Sie auf die Schaltfläche **Hinzufügen** , um die Seite **Regions Link** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9551-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="f9551-145">Klicken Sie auf einen Regions Link, der zu dieser Route hinzugefügt werden soll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9551-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="f9551-146">Klicken Sie weiter auf die Schaltfläche **Hinzufügen** , um weitere Links hinzuzufügen, oder wählen Sie einen Link aus, und klicken Sie auf **Entfernen** , um einen Link zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f9551-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="f9551-147">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f9551-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="f9551-148">So ändern Sie eine Route des Netzwerkbereichs</span><span class="sxs-lookup"><span data-stu-id="f9551-148">To modify a network region route</span></span>

1.  <span data-ttu-id="f9551-149">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f9551-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9551-150">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9551-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f9551-151">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Route**.</span><span class="sxs-lookup"><span data-stu-id="f9551-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f9551-152">Klicken Sie auf der Seite **Region Route** auf die Route, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f9551-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="f9551-153">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f9551-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f9551-154">In der **Route "Region bearbeiten**" können Sie die Regionen ändern, die mit dieser Route verbunden sind, und die der Route zugeordneten Regions Verknüpfungen.</span><span class="sxs-lookup"><span data-stu-id="f9551-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="f9551-155">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f9551-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="f9551-156">Löschen vorhandener Strecken des Netzwerkbereichs</span><span class="sxs-lookup"><span data-stu-id="f9551-156">Delete existing network region routes</span></span>

<span data-ttu-id="f9551-157">Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9551-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="f9551-158">Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="f9551-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="f9551-159">Sie können die Skype for Business Server-Systemsteuerung verwenden, um Strecken des Netzwerkbereichs zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f9551-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="f9551-160">Über die Skype for Business Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="f9551-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="f9551-161">Verwenden Sie dieses Thema, um vorhandene Netzwerkbereichs Routen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f9551-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="f9551-162">So löschen Sie eine Route des Netzwerkbereichs</span><span class="sxs-lookup"><span data-stu-id="f9551-162">To delete a network region route</span></span>

1.  <span data-ttu-id="f9551-163">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f9551-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9551-164">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9551-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f9551-165">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Route**.</span><span class="sxs-lookup"><span data-stu-id="f9551-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f9551-166">Klicken Sie auf der Seite **Region Route** auf die Route, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="f9551-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f9551-167">Sie können mehr als eine Regions Route gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="f9551-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="f9551-168">Drücken Sie dazu STRG, und wählen Sie mehrere Bereichs Routen aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="f9551-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="f9551-169">Wenn Sie alle Regions Routen auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen** .</span><span class="sxs-lookup"><span data-stu-id="f9551-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="f9551-170">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f9551-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="f9551-171">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9551-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="f9551-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9551-172">See Also</span></span>

[<span data-ttu-id="f9551-173">Verwalten von Netzwerkregionen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f9551-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="f9551-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f9551-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="f9551-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f9551-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="f9551-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f9551-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="f9551-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f9551-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
