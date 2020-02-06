---
title: Verwalten von Netzwerk-Subnetzen
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
description: In den meisten Bereitstellungen von Skype for Business Server, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es am besten, Subnets aus der Skype for Business Server-Verwaltungsshell zu konfigurieren.
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817464"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="26dc5-104">Verwalten von Netzwerksubnetzen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="26dc5-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="26dc5-105">Sie können die Skype for Business Server-Systemsteuerung oder die Skype for Business Server-Verwaltungsshell verwenden, um Netzwerk-Subnets zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="26dc5-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="26dc5-106">In den meisten Bereitstellungen von Skype for Business Server, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="26dc5-107">Aus diesem Grund ist es am besten, Subnets aus der Skype for Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="26dc5-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="26dc5-108">Verwenden Sie die Abschnitte in diesem Artikel, um Netzwerk-Subnetinformationen anzuzeigen oder Netzwerk-Subnets zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="26dc5-109">Netzwerk-Subnetz-Informationen anzeigen</span><span class="sxs-lookup"><span data-stu-id="26dc5-109">View network subnet information</span></span> 

<span data-ttu-id="26dc5-110">Sie können das folgende Verfahren verwenden, um ein Netzwerk-Subnetz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="26dc5-111">In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="26dc5-112">So zeigen Sie ein Netzwerk-Subnetz an</span><span class="sxs-lookup"><span data-stu-id="26dc5-112">To view a network subnet</span></span>

1.  <span data-ttu-id="26dc5-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="26dc5-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="26dc5-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="26dc5-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="26dc5-116">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="26dc5-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="26dc5-117">Sie können jeweils nur ein Subnetz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="26dc5-118">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="26dc5-119">Anzeigen von Netzwerk-Subnet-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="26dc5-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="26dc5-120">Netzwerk-Subnetz-Informationen können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkSubnet angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="26dc5-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="26dc5-121">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="26dc5-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="26dc5-122">So zeigen Sie Netzwerk-Subnetz-Informationen an</span><span class="sxs-lookup"><span data-stu-id="26dc5-122">To view network subnet information</span></span>

  - <span data-ttu-id="26dc5-123">Wenn Sie Informationen zu allen Netzwerk-Subnetzen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="26dc5-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="26dc5-124">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="26dc5-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="26dc5-125">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="26dc5-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="26dc5-126">Erstellen oder Ändern von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="26dc5-126">Create or modify network subnets</span></span> 

<span data-ttu-id="26dc5-127">Ein Netzwerk-Subnetz muss einer Netzwerk Website zugeordnet sein, um den geografischen Standort des Hosts zu ermitteln, der zu diesem Subnetz gehört.</span><span class="sxs-lookup"><span data-stu-id="26dc5-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="26dc5-128">Sie können die Skype for Business Server-Systemsteuerung verwenden, um Subnets zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="26dc5-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="26dc5-129">In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="26dc5-130">In den meisten Bereitstellungen von Skype for Business Server, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="26dc5-131">Aus diesem Grund ist es am besten, Subnets aus der Skype for Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="26dc5-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="26dc5-132">Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem Windows PowerShell **-Cmdlet Import-CSV**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="26dc5-133">Wenn Sie diese Cmdlets zusammen verwenden, können Sie die subneteinstellungen aus einer CSV-Datei (Comma-Separated Values) lesen und gleichzeitig mehrere Subnetze erstellen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="26dc5-134">Beispiele zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="26dc5-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="26dc5-135">So erstellen Sie ein Netzwerk-Subnetz</span><span class="sxs-lookup"><span data-stu-id="26dc5-135">To create a network subnet</span></span>

1.  <span data-ttu-id="26dc5-136">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="26dc5-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="26dc5-137">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="26dc5-138">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="26dc5-139">Klicken Sie auf der Seite **Subnetz** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="26dc5-140">Geben Sie im **neuen Subnetz**einen Wert in das Feld **Subnet-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="26dc5-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="26dc5-141">Hierbei muss es sich um eine IP-Adresse (beispielsweise 174.11.12.0) handeln, die die erste Adresse im vom Subnetz definierten IP-Adressbereich sein muss.</span><span class="sxs-lookup"><span data-stu-id="26dc5-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="26dc5-142">Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.</span><span class="sxs-lookup"><span data-stu-id="26dc5-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="26dc5-143">Dieser Wert ist die Bitmaske, die auf das erstellte Subnetz angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="26dc5-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="26dc5-144">Wählen Sie unter **Netzwerk Website-ID**die Website aus, zu der dieses Subnetz gehört.</span><span class="sxs-lookup"><span data-stu-id="26dc5-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="26dc5-145">Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu diesem Subnetz bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="26dc5-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="26dc5-146">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="26dc5-147">So ändern Sie ein Netzwerk-Subnetz</span><span class="sxs-lookup"><span data-stu-id="26dc5-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="26dc5-148">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="26dc5-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="26dc5-149">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="26dc5-150">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="26dc5-151">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="26dc5-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="26dc5-152">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="26dc5-153">Auf der Seite " **Subnetz bearbeiten** " können Sie die Bitmaske, die zugeordnete Netzwerk Website oder die Beschreibung ändern.</span><span class="sxs-lookup"><span data-stu-id="26dc5-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="26dc5-154">Beachten Sie beim Ändern der Bitmaske, dass die Subnetz-ID immer noch die erste Adresse im IP-Adressbereich sein muss, die vom Subnetz definiert ist.</span><span class="sxs-lookup"><span data-stu-id="26dc5-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="26dc5-155">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="26dc5-156">Löschen von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="26dc5-156">Delete network subnets</span></span>

<span data-ttu-id="26dc5-157">Sie können das folgende Verfahren verwenden, um ein Subnetz zu löschen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="26dc5-158">In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="26dc5-159">In den meisten Bereitstellungen von Skype for Business Server, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="26dc5-160">Aus diesem Grund ist es am besten, Subnets aus der Skype for Business Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="26dc5-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="26dc5-161">Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem Windows PowerShell **-Cmdlet Import-CSV**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="26dc5-162">Wenn Sie diese Cmdlets zusammen verwenden, können Sie die subneteinstellungen aus einer CSV-Datei (Comma-Separated Values) lesen und gleichzeitig mehrere Subnetze erstellen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="26dc5-163">Beispiele zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="26dc5-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="26dc5-164">So löschen Sie ein Netzwerk-Subnetz</span><span class="sxs-lookup"><span data-stu-id="26dc5-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="26dc5-165">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="26dc5-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="26dc5-166">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="26dc5-167">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="26dc5-168">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="26dc5-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="26dc5-169">Sie können mehr als ein Subnetz gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="26dc5-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="26dc5-170">Drücken Sie dazu STRG, und wählen Sie mehrere Subnetze aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="26dc5-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="26dc5-171">Wenn Sie alle Subnetze auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alles auswählen** .</span><span class="sxs-lookup"><span data-stu-id="26dc5-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="26dc5-172">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="26dc5-173">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="26dc5-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="26dc5-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26dc5-174">See Also</span></span>

[<span data-ttu-id="26dc5-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="26dc5-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="26dc5-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="26dc5-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="26dc5-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="26dc5-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="26dc5-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="26dc5-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
