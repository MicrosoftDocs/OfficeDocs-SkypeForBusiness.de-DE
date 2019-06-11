---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerk-Subnetzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="b1865-102">Erstellen oder Ändern von Netzwerk-Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1865-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1865-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b1865-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b1865-104">Ein Netzwerk-Subnetz muss einer Netzwerk Website zugeordnet sein, um den geografischen Standort des Hosts zu ermitteln, der zu diesem Subnetz gehört.</span><span class="sxs-lookup"><span data-stu-id="b1865-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="b1865-105">Sie können die lync Server-Systemsteuerung zum Konfigurieren von Subnetzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1865-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="b1865-106">In der lync Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="b1865-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="b1865-107">Details zum Löschen von Netzwerk-Subnetzen finden Sie unter Löschen von Netzwerk-Subnetzen [in lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="b1865-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="b1865-108">In den meisten Bereitstellungen von Microsoft lync Server 2013, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="b1865-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="b1865-109">Aus diesem Grund ist es am besten, Subnets aus der lync Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b1865-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="b1865-110">Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem Windows PowerShell **-Cmdlet Import-CSV**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b1865-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="b1865-111">Wenn Sie diese Cmdlets zusammen verwenden, können Sie die subneteinstellungen aus einer CSV-Datei (Comma-Separated Values) lesen und gleichzeitig mehrere Subnetze erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1865-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="b1865-112">Beispiele zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="b1865-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="b1865-113">So erstellen Sie ein Netzwerk-Subnetz</span><span class="sxs-lookup"><span data-stu-id="b1865-113">To create a network subnet</span></span>

1.  <span data-ttu-id="b1865-114">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b1865-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1865-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b1865-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1865-116">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b1865-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1865-117">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="b1865-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="b1865-118">Klicken Sie auf der Seite **Subnetz** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="b1865-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="b1865-119">Geben Sie im **neuen Subnetz**einen Wert in das Feld **Subnet-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="b1865-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="b1865-120">Hierbei muss es sich um eine IP-Adresse (beispielsweise 174.11.12.0) handeln, die die erste Adresse im vom Subnetz definierten IP-Adressbereich sein muss.</span><span class="sxs-lookup"><span data-stu-id="b1865-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="b1865-121">Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.</span><span class="sxs-lookup"><span data-stu-id="b1865-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b1865-122">Dieser Wert ist die Bitmaske, die auf das erstellte Subnetz angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b1865-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="b1865-123">Wählen Sie unter **Netzwerk Website-ID**die Website aus, zu der dieses Subnetz gehört.</span><span class="sxs-lookup"><span data-stu-id="b1865-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="b1865-124">Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu diesem Subnetz bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="b1865-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="b1865-125">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b1865-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="b1865-126">So ändern Sie ein Netzwerk-Subnetz</span><span class="sxs-lookup"><span data-stu-id="b1865-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="b1865-127">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b1865-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1865-128">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b1865-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1865-129">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b1865-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1865-130">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="b1865-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="b1865-131">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="b1865-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="b1865-132">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b1865-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b1865-133">Auf der Seite " **Subnetz bearbeiten** " können Sie die Bitmaske, die zugeordnete Netzwerk Website oder die Beschreibung ändern.</span><span class="sxs-lookup"><span data-stu-id="b1865-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="b1865-134">Beachten Sie beim Ändern der Bitmaske, dass die Subnetz-ID immer noch die erste Adresse im IP-Adressbereich sein muss, die vom Subnetz definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b1865-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="b1865-135">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b1865-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1865-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1865-136">See Also</span></span>


[<span data-ttu-id="b1865-137">Löschen von Netzwerk-Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1865-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="b1865-138">Informationen zu Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1865-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="b1865-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b1865-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="b1865-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b1865-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="b1865-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b1865-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="b1865-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b1865-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

