---
title: 'Lync Server 2013: Zuordnen eines Subnetzes zu einem Netzwerkstandort'
description: 'Lync Server 2013: Zuordnen eines Subnetzes zu einem Netzwerkstandort.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed8708b9280455355a010984d09fc91da3313f95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563341"
---
# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="9a15e-103">Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a15e-103">Associate a subnet with a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a15e-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9a15e-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9a15e-105">Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein, da mithilfe von Subnetzinformationen der Netzwerkstandort ermittelt wird, an dem sich ein Endpunkt befindet, während eine neuen Sitzung initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="9a15e-105">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="9a15e-106">Wenn der Speicherort jeder Partei in einer Sitzung bekannt ist, können erweiterte Enterprise-VoIP-Features diese Informationen anwenden, um zu bestimmen, wie die Anrufeinrichtung oder das Routing behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a15e-106">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a15e-107">Alle konfigurierten öffentlichen IP-Adressen der Audio-Video-Edgeserver in Ihrer Bereitstellung müssen den Netzwerkkonfigurationseinstellungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9a15e-107">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="9a15e-108">Diese IP-Adressen werden als Subnetze mit der Maske 32 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9a15e-108">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="9a15e-109">Der zugeordnete Netzwerkstandort muss dem jeweiligen konfigurierten Netzwerkstandort entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9a15e-109">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="9a15e-110">Die öffentliche IP-Adresse, die dem A/V-Edgeserver am zentralen Standort Chicago entspricht, hat beispielsweise die Netzwerkstandort-ID "Chicago".</span><span class="sxs-lookup"><span data-stu-id="9a15e-110">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="9a15e-111">Ausführliche Informationen zu öffentlichen IP-Adressen finden Sie unter <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">bestimmen der externen A/V-Firewall-und Portanforderungen für lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9a15e-111">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9a15e-p103">Es wird eine KHI-Warnung (Key Health Indicator) ausgegeben. Diese enthält eine Liste der IP-Adressen, die in Ihrem Netzwerk vorhanden, aber keinem Subnetz zugeordnet sind, oder sie gibt das Subnetz an, das die IP-Adressen enthält, jedoch keinem Netzwerkstandort zugeordnet ist. Diese Warnung wird innerhalb von acht Stunden nur einmal angezeigt. Nachfolgend finden Sie die relevanten Warnungsinformationen und ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9a15e-p103">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8-hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="9a15e-115"><STRONG>Quelle:</STRONG> CS Bandwidth Policy Service (Kern)</span><span class="sxs-lookup"><span data-stu-id="9a15e-115"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="9a15e-116"><STRONG>Ereignisnummer:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="9a15e-116"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="9a15e-117"><STRONG>Ebene:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="9a15e-117"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="9a15e-118"><STRONG>Beschreibung:</STRONG> Die Subnetze für die folgenden IP-Adressen: &lt; Liste der IP-Adressen &gt; sind entweder nicht konfiguriert oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9a15e-118"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="9a15e-119"><STRONG>Ursache:</STRONG> Die Subnetze für die entsprechenden IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen, oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9a15e-119"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="9a15e-120"><STRONG>Lösung:</STRONG> Fügen Sie den Netzwerkkonfigurationseinstellungen Subnetze hinzu, die der Liste der IP-Adressen entsprechen, und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.</span><span class="sxs-lookup"><span data-stu-id="9a15e-120"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="9a15e-p104">Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet, oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:</span><span class="sxs-lookup"><span data-stu-id="9a15e-p104">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="9a15e-123">Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9a15e-123">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="9a15e-124">Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9a15e-124">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="9a15e-125">Ausführliche Informationen zum Arbeiten mit Netzwerk-Subnetzen finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9a15e-125">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="9a15e-126">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9a15e-126">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="9a15e-127">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9a15e-127">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="9a15e-128">Gruppe-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9a15e-128">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="9a15e-129">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9a15e-129">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="9a15e-p105">Wenn Sie mit vielen Subnetzen arbeiten, wird die Verwendung einer CSV-Datei (mit durch Trennzeichen getrennten Werten) empfohlen, um Subnetze Standorten zuzuordnen. Die CSV-Datei muss die folgenden vier Spalten enthalten: <STRONG>IP-Adresse</STRONG>, <STRONG>Maske</STRONG>, <STRONG>Beschreibung</STRONG>, <STRONG>Netzwerkstandort-ID</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9a15e-p105">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites. The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="9a15e-132">So ordnen Sie ein Subnetz mithilfe der Verwaltungsshell einem Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="9a15e-132">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="9a15e-133">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9a15e-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9a15e-134">Führen Sie das Cmdlet **New-CsNetworkSubnet** aus, um ein Subnetz einem Netzwerkstandort zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="9a15e-134">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="9a15e-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9a15e-135">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="9a15e-136">In diesem Beispiel haben Sie eine Zuordnung zwischen dem Subnetz 172.11.12.13 und dem Netzwerkstandort "Chicago" erstellt.</span><span class="sxs-lookup"><span data-stu-id="9a15e-136">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="9a15e-137">Wiederholen Sie Schritt 2 für alle Subnetze in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="9a15e-137">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="9a15e-138">So ordnen Sie Subnetze durch Importieren einer CSV-Datei Netzwerkstandorten zu</span><span class="sxs-lookup"><span data-stu-id="9a15e-138">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="9a15e-p106">Erstellen Sie eine CSV-Datei, die alle Subnetze enthält, die Sie hinzufügen möchten. Erstellen Sie beispielsweise die Datei **Subnetz.csv** mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="9a15e-p106">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="9a15e-141">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9a15e-141">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9a15e-142">Führen Sie das folgende Cmdlet aus, um **subnet.csv**zu importieren, und speichern Sie dann den Inhalt im lync Server Verwaltungsspeicher:</span><span class="sxs-lookup"><span data-stu-id="9a15e-142">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="9a15e-143">So ordnen Sie ein Subnetz mithilfe der Lync Server-Systemsteuerung einem Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="9a15e-143">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9a15e-144">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9a15e-144">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9a15e-145">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9a15e-145">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="9a15e-146">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9a15e-146">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="9a15e-147">Klicken Sie auf die Navigationsschaltfläche **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="9a15e-147">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="9a15e-148">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="9a15e-148">Click **New**.</span></span>

5.  <span data-ttu-id="9a15e-149">Klicken Sie auf der Seite **Neues Subnetz** auf **Subnetz-ID**, und geben Sie dann die erste Adresse in den IP-Adressbereich ein, der von dem Subnetz definiert wird, das Sie einem Netzwerkstandort zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="9a15e-149">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="9a15e-150">Klicken Sie auf **Maske**, und geben Sie die Bitmaske für das Subnetz ein.</span><span class="sxs-lookup"><span data-stu-id="9a15e-150">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="9a15e-151">Klicken Sie auf **Netzwerkstandort-ID**, und wählen Sie die Standort-ID des Standorts aus, dem Sie dieses Subnetz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9a15e-151">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a15e-152">Wenn Sie noch keine Netzwerkstandorte erstellt haben, ist diese Liste leer.</span><span class="sxs-lookup"><span data-stu-id="9a15e-152">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="9a15e-153">Ausführliche Informationen zur Vorgehensweise finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9a15e-153">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="9a15e-154">Sie können auch Standort-IDs für Ihre Bereitstellung abrufen, indem Sie das Cmdlet <STRONG>Get-CsNetworkSite</STRONG> ausführen.</span><span class="sxs-lookup"><span data-stu-id="9a15e-154">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="9a15e-155">Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="9a15e-155">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="9a15e-156">Klicken Sie optional auf **Beschreibung**, und geben Sie zusätzliche Informationen zur Beschreibung dieses Subnetzes ein.</span><span class="sxs-lookup"><span data-stu-id="9a15e-156">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="9a15e-157">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9a15e-157">Click **Commit**.</span></span>

<span data-ttu-id="9a15e-158">Wiederholen Sie diese Schritte, um einem Netzwerkstandort weitere Subnetze hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9a15e-158">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

