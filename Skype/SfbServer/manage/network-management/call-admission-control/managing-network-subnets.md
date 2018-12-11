---
title: Verwalten von Netzwerksubnetzen
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen. Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.
ms.openlocfilehash: e855805aebc61228c185d04cba1faa9de6700f84
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223353"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="50e17-104">Verwalten von Netzwerksubnetzen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="50e17-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="50e17-105">Sie können entweder die Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell verwenden, zum Verwalten von Netzwerksubnetzen.</span><span class="sxs-lookup"><span data-stu-id="50e17-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="50e17-106">In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="50e17-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="50e17-107">Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="50e17-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="50e17-108">Verwenden Sie in den Abschnitten in diesem Artikel, um Informationen zum Netzwerksubnetz anzuzeigen oder zu erstellen, ändern oder Löschen von Netzwerksubnetzen.</span><span class="sxs-lookup"><span data-stu-id="50e17-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="50e17-109">Anzeigen von netzwerksubnetzinformationen</span><span class="sxs-lookup"><span data-stu-id="50e17-109">View network subnet information</span></span> 

<span data-ttu-id="50e17-110">Das folgende Verfahren können Sie ein Netzwerksubnetz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50e17-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="50e17-111">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz.</span><span class="sxs-lookup"><span data-stu-id="50e17-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="50e17-112">So zeigen Sie ein Netzwerksubnetz an</span><span class="sxs-lookup"><span data-stu-id="50e17-112">To view a network subnet</span></span>

1.  <span data-ttu-id="50e17-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="50e17-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50e17-114">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="50e17-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="50e17-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="50e17-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="50e17-116">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="50e17-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="50e17-117">Sie können nur jeweils ein Subnetz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50e17-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="50e17-118">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="50e17-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="50e17-119">Zeigen Sie Netzwerksubnetz-Konfigurationsinformationen an, indem Sie mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="50e17-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="50e17-120">Informationen zum Netzwerksubnetz kann mithilfe von Windows PowerShell und das Cmdlet "Get-CsNetworkSubnet" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="50e17-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="50e17-121">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="50e17-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="50e17-122">So zeigen Sie Informationen zum Netzwerksubnetz an</span><span class="sxs-lookup"><span data-stu-id="50e17-122">To view network subnet information</span></span>

  - <span data-ttu-id="50e17-123">Um Informationen über alle netzwerksubnetze anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="50e17-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="50e17-124">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="50e17-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="50e17-125">Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="50e17-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="50e17-126">Erstellen oder Ändern von Netzwerksubnetzen</span><span class="sxs-lookup"><span data-stu-id="50e17-126">Create or modify network subnets</span></span> 

<span data-ttu-id="50e17-127">Ein Netzwerksubnetz muss für die Bestimmung des geografischen Standorts des Hosts, gehören zu diesem Subnetz einem Netzwerkstandort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="50e17-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="50e17-128">Die Skype Business Server-Systemsteuerung können Sie Subnetze konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="50e17-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="50e17-129">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz.</span><span class="sxs-lookup"><span data-stu-id="50e17-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="50e17-130">In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="50e17-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="50e17-131">Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="50e17-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="50e17-132">Dort können Sie **New-CsNetworkSubnet** in Verbindung mit der Windows PowerShell-Cmdlet **Import-CSV**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="50e17-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="50e17-133">Diese Cmdlets zusammen verwenden, können Sie in Subnetz Einstellungen aus einer Datei durch Kommas getrennten Werten (CSV) lesen und Erstellen von mehreren Subnetzen zur selben Zeit.</span><span class="sxs-lookup"><span data-stu-id="50e17-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="50e17-134">Beispiele dafür, wie Sie zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-csnetworksubnet aus](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="50e17-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="50e17-135">Erstellen Sie ein Netzwerksubnetz</span><span class="sxs-lookup"><span data-stu-id="50e17-135">To create a network subnet</span></span>

1.  <span data-ttu-id="50e17-136">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="50e17-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50e17-137">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="50e17-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="50e17-138">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="50e17-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="50e17-139">Klicken Sie auf der Seite **Subnetz** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="50e17-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="50e17-140">Geben Sie in **Neues Subnetz**einen Wert im Feld **Subnetz-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="50e17-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="50e17-141">Dies muss eine IP-Adresse (beispielsweise 174.11.12.0), und es muss die erste Adresse in der IP-Adressbereich durch das Subnetz definiert sein.</span><span class="sxs-lookup"><span data-stu-id="50e17-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="50e17-142">Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.</span><span class="sxs-lookup"><span data-stu-id="50e17-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="50e17-143">Dieser Wert ist die Bitmaske dar, auf das erstellte Subnetz angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50e17-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="50e17-144">Wählen Sie in **Netzwerkstandort-ID**, zu der dieses Subnetz gehört.</span><span class="sxs-lookup"><span data-stu-id="50e17-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="50e17-145">(Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu diesem Subnetz bereitzustellen, die durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="50e17-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="50e17-146">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="50e17-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="50e17-147">So ändern Sie ein Netzwerksubnetz</span><span class="sxs-lookup"><span data-stu-id="50e17-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="50e17-148">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="50e17-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50e17-149">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="50e17-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="50e17-150">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="50e17-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="50e17-151">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="50e17-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="50e17-152">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="50e17-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="50e17-153">Auf der Seite **Subnetz bearbeiten** können Sie die Bitmaske, die zugeordneten Netzwerkstandort oder die Beschreibung ändern.</span><span class="sxs-lookup"><span data-stu-id="50e17-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="50e17-154">Wenn Sie die Bitmaske ändern, Überwachungsfunktionen Sie berücksichtigen, die der Subnetz-ID weiterhin die erste Adresse in der IP-Adressbereich durch das Subnetz definiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="50e17-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="50e17-155">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="50e17-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="50e17-156">Löschen von Netzwerksubnetzen</span><span class="sxs-lookup"><span data-stu-id="50e17-156">Delete network subnets</span></span>

<span data-ttu-id="50e17-157">Das folgende Verfahren können Sie um ein Subnetz zu löschen.</span><span class="sxs-lookup"><span data-stu-id="50e17-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="50e17-158">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz.</span><span class="sxs-lookup"><span data-stu-id="50e17-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="50e17-159">In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="50e17-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="50e17-160">Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="50e17-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="50e17-161">Dort können Sie **New-CsNetworkSubnet** in Verbindung mit der Windows PowerShell-Cmdlet **Import-CSV**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="50e17-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="50e17-162">Diese Cmdlets zusammen verwenden, können Sie in Subnetz Einstellungen aus einer Datei durch Kommas getrennten Werten (CSV) lesen und Erstellen von mehreren Subnetzen zur selben Zeit.</span><span class="sxs-lookup"><span data-stu-id="50e17-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="50e17-163">Beispiele dafür, wie Sie zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-csnetworksubnet aus](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="50e17-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="50e17-164">So löschen Sie ein Netzwerksubnetz</span><span class="sxs-lookup"><span data-stu-id="50e17-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="50e17-165">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="50e17-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50e17-166">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="50e17-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="50e17-167">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="50e17-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="50e17-168">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="50e17-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="50e17-169">Sie können mehrere Subnetze zu einem Zeitpunkt löschen.</span><span class="sxs-lookup"><span data-stu-id="50e17-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="50e17-170">Zu diesem Zweck, drücken Sie STRG, und wählen Sie mehrere Subnetze, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="50e17-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="50e17-171">Oder, wenn alle Subnetze auswählen möchten, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="50e17-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="50e17-172">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="50e17-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="50e17-173">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="50e17-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="50e17-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50e17-174">See Also</span></span>

[<span data-ttu-id="50e17-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="50e17-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="50e17-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="50e17-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="50e17-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="50e17-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="50e17-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="50e17-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  