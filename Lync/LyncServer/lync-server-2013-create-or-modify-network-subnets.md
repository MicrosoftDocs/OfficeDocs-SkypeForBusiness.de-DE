---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerk Subnetzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47075e96171bbeef5c2709e3eb38a480d08938f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="aefba-102">Erstellen oder Ändern von Netzwerk-Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aefba-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aefba-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="aefba-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="aefba-104">Ein Netzwerksubnetz muss einem Netzwerkstandort zugeordnet sein, damit der geografische Standort und der zu diesem Subnetz gehörende Host ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="aefba-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="aefba-105">Sie können lync Server-Systemsteuerung zum Konfigurieren von Subnetzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="aefba-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="aefba-106">Im lync Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="aefba-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="aefba-107">Ausführliche Informationen zum Löschen von Netzwerk Subnetzen finden Sie unter [Löschen von Netzwerksubnetzen in lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="aefba-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="aefba-108">In den meisten Bereitstellungen von Microsoft lync Server 2013, in denen die Anrufsteuerung (Call Admission Control, CAC) implementiert ist, wird in der Regel eine große Anzahl von Subnetzen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="aefba-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="aefba-109">Aus diesem Grund ist es häufig am besten, Subnetze aus dem lync Server-Verwaltungsshell zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="aefba-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="aefba-110">Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem Cmdlet **Import-CSV**von Windows PowerShell aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aefba-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="aefba-111">Wenn Sie diese beiden Cmdlets zusammen verwenden, können Sie die Subnetzeinstellungen aus einer durch Trennzeichen getrennten Datei (Comma-Separated Values, CSV) abrufen und mehrere Subnetze gleichzeitig erstellen.</span><span class="sxs-lookup"><span data-stu-id="aefba-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="aefba-112">Beispiele für die Erstellung von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="aefba-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="aefba-113">So erstellen Sie ein Netzwerksubnetz</span><span class="sxs-lookup"><span data-stu-id="aefba-113">To create a network subnet</span></span>

1.  <span data-ttu-id="aefba-114">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="aefba-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aefba-115">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="aefba-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aefba-116">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aefba-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aefba-117">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="aefba-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="aefba-118">Klicken Sie auf der Seite **Subnetz** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="aefba-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="aefba-p104">Geben Sie unter **Neues Subnetz** einen Wert im Feld **Subnetz-ID** ein. Dabei muss es sich um eine IP-Adresse (z. B. 174.11.12.0) und um die erste Adresse im IP-Adressbereich handeln, der vom Subnetz definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="aefba-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="aefba-121">Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.</span><span class="sxs-lookup"><span data-stu-id="aefba-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aefba-122">Dieser Wert stellt die Bitmaske dar, die auf das erstellte Subnetz angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aefba-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="aefba-123">Wählen Sie in **Netzwerkstandort-ID** den Standort aus, zu dem dieses Subnetz gehört.</span><span class="sxs-lookup"><span data-stu-id="aefba-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="aefba-124">(Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Subnetz ein, die nicht durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="aefba-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="aefba-125">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="aefba-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="aefba-126">So ändern Sie ein Netzwerksubnetz</span><span class="sxs-lookup"><span data-stu-id="aefba-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="aefba-127">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="aefba-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aefba-128">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="aefba-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aefba-129">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aefba-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aefba-130">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="aefba-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="aefba-131">Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="aefba-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="aefba-132">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="aefba-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="aefba-p106">Auf der Seite **Subnetz bearbeiten** können Sie die Bitmaske, den zugeordneten Netzwerkstandort oder die Beschreibung ändern. Beachten Sie beim Ändern der Bitmaske, dass die Subnetz-ID noch immer der ersten Adresse in dem vom Subnetz definierten IP-Adressbereich entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="aefba-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="aefba-135">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="aefba-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aefba-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aefba-136">See Also</span></span>


[<span data-ttu-id="aefba-137">Löschen von Netzwerk Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aefba-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="aefba-138">Informationen zu netzwerkregionen, Standorten und Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aefba-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="aefba-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="aefba-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="aefba-140">Gruppe-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="aefba-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="aefba-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="aefba-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="aefba-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="aefba-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

