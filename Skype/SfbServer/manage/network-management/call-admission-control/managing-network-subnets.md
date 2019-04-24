---
title: Verwalten von Netzwerksubnetzen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen. Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.
ms.openlocfilehash: 3b61ad1b4e1eb7f11d61b32c15e337bcd4ff77c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198908"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="9c8a2-104">Verwalten von Netzwerksubnetzen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9c8a2-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="9c8a2-105">Sie können entweder die Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell verwenden, zum Verwalten von Netzwerksubnetzen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="9c8a2-106">In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="9c8a2-107">Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="9c8a2-108">Verwenden Sie in den Abschnitten in diesem Artikel, um Informationen zum Netzwerksubnetz anzuzeigen oder zu erstellen, ändern oder Löschen von Netzwerksubnetzen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="9c8a2-109">Anzeigen von netzwerksubnetzinformationen</span><span class="sxs-lookup"><span data-stu-id="9c8a2-109">View network subnet information</span></span> 

<span data-ttu-id="9c8a2-110">Das folgende Verfahren können Sie ein Netzwerksubnetz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="9c8a2-111">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="9c8a2-112">So zeigen Sie ein Netzwerksubnetz an</span><span class="sxs-lookup"><span data-stu-id="9c8a2-112">To view a network subnet</span></span>

1.  <span data-ttu-id="9c8a2-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9c8a2-114">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9c8a2-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="9c8a2-116">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="9c8a2-117">Sie können nur jeweils ein Subnetz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="9c8a2-118">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9c8a2-119">Zeigen Sie Netzwerksubnetz-Konfigurationsinformationen an, indem Sie mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="9c8a2-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9c8a2-120">Informationen zum Netzwerksubnetz kann mithilfe von Windows PowerShell und das Cmdlet "Get-CsNetworkSubnet" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="9c8a2-121">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="9c8a2-122">So zeigen Sie Informationen zum Netzwerksubnetz an</span><span class="sxs-lookup"><span data-stu-id="9c8a2-122">To view network subnet information</span></span>

  - <span data-ttu-id="9c8a2-123">Um Informationen über alle netzwerksubnetze anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="9c8a2-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="9c8a2-124">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9c8a2-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="9c8a2-125">Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="9c8a2-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="9c8a2-126">Erstellen oder Ändern von Netzwerksubnetzen</span><span class="sxs-lookup"><span data-stu-id="9c8a2-126">Create or modify network subnets</span></span> 

<span data-ttu-id="9c8a2-127">Ein Netzwerksubnetz muss für die Bestimmung des geografischen Standorts des Hosts, gehören zu diesem Subnetz einem Netzwerkstandort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="9c8a2-128">Die Skype Business Server-Systemsteuerung können Sie Subnetze konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="9c8a2-129">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="9c8a2-130">In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="9c8a2-131">Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9c8a2-132">Dort können Sie **New-CsNetworkSubnet** in Verbindung mit der Windows PowerShell-Cmdlet **Import-CSV**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="9c8a2-133">Diese Cmdlets zusammen verwenden, können Sie in Subnetz Einstellungen aus einer Datei durch Kommas getrennten Werten (CSV) lesen und Erstellen von mehreren Subnetzen zur selben Zeit.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="9c8a2-134">Beispiele dafür, wie Sie zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-csnetworksubnet aus](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="9c8a2-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="9c8a2-135">Erstellen Sie ein Netzwerksubnetz</span><span class="sxs-lookup"><span data-stu-id="9c8a2-135">To create a network subnet</span></span>

1.  <span data-ttu-id="9c8a2-136">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9c8a2-137">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9c8a2-138">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="9c8a2-139">Klicken Sie auf der Seite **Subnetz** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="9c8a2-140">Geben Sie in **Neues Subnetz**einen Wert im Feld **Subnetz-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="9c8a2-141">Dies muss eine IP-Adresse (beispielsweise 174.11.12.0), und es muss die erste Adresse in der IP-Adressbereich durch das Subnetz definiert sein.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="9c8a2-142">Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="9c8a2-143">Dieser Wert ist die Bitmaske dar, auf das erstellte Subnetz angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="9c8a2-144">Wählen Sie in **Netzwerkstandort-ID**, zu der dieses Subnetz gehört.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="9c8a2-145">(Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu diesem Subnetz bereitzustellen, die durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="9c8a2-146">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="9c8a2-147">So ändern Sie ein Netzwerksubnetz</span><span class="sxs-lookup"><span data-stu-id="9c8a2-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="9c8a2-148">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9c8a2-149">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9c8a2-150">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="9c8a2-151">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="9c8a2-152">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9c8a2-153">Auf der Seite **Subnetz bearbeiten** können Sie die Bitmaske, die zugeordneten Netzwerkstandort oder die Beschreibung ändern.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="9c8a2-154">Wenn Sie die Bitmaske ändern, Überwachungsfunktionen Sie berücksichtigen, die der Subnetz-ID weiterhin die erste Adresse in der IP-Adressbereich durch das Subnetz definiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="9c8a2-155">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="9c8a2-156">Löschen von Netzwerksubnetzen</span><span class="sxs-lookup"><span data-stu-id="9c8a2-156">Delete network subnets</span></span>

<span data-ttu-id="9c8a2-157">Das folgende Verfahren können Sie um ein Subnetz zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="9c8a2-158">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="9c8a2-159">In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="9c8a2-160">Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9c8a2-161">Dort können Sie **New-CsNetworkSubnet** in Verbindung mit der Windows PowerShell-Cmdlet **Import-CSV**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="9c8a2-162">Diese Cmdlets zusammen verwenden, können Sie in Subnetz Einstellungen aus einer Datei durch Kommas getrennten Werten (CSV) lesen und Erstellen von mehreren Subnetzen zur selben Zeit.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="9c8a2-163">Beispiele dafür, wie Sie zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-csnetworksubnet aus](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="9c8a2-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="9c8a2-164">So löschen Sie ein Netzwerksubnetz</span><span class="sxs-lookup"><span data-stu-id="9c8a2-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="9c8a2-165">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9c8a2-166">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9c8a2-167">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="9c8a2-168">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="9c8a2-169">Sie können mehrere Subnetze zu einem Zeitpunkt löschen.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="9c8a2-170">Zu diesem Zweck, drücken Sie STRG, und wählen Sie mehrere Subnetze, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="9c8a2-171">Oder, wenn alle Subnetze auswählen möchten, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="9c8a2-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="9c8a2-172">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="9c8a2-173">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c8a2-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="9c8a2-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c8a2-174">See Also</span></span>

[<span data-ttu-id="9c8a2-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9c8a2-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="9c8a2-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9c8a2-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="9c8a2-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9c8a2-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="9c8a2-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9c8a2-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
