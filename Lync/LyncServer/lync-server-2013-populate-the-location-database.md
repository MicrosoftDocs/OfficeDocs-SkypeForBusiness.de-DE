---
title: 'Lync Server 2013: Auffüllen der Standortdatenbank'
description: 'Lync Server 2013: füllen Sie die Standortdatenbank.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cf3204795ae2c4f8248517b84d7a5ac1bad0d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543171"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="2e082-103">Auffüllen der Standortdatenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e082-103">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e082-104">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2e082-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2e082-105">Um Clients in einem Netzwerk automatisch zu finden, müssen Sie zunächst die Standortdatenbank mit einem Netzwerk- *Wiremap*füllen, das Netzwerkelemente den Civic-Adressen (also Straße) zuordnet.</span><span class="sxs-lookup"><span data-stu-id="2e082-105">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="2e082-106">Sie können Subnetze, drahtlose Zugriffspunkte, Switches und Ports verwenden, um die Wiremap zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2e082-106">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="2e082-107">Sie können der Standortdatenbank einzeln oder in Massen eine Adresse hinzufügen, indem Sie eine CSV-Datei verwenden, die die in der folgenden Tabelle beschriebenen Spaltenformate enthält.</span><span class="sxs-lookup"><span data-stu-id="2e082-107">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="2e082-108">Wenn Sie ein Elin-Gateway (Emergency Location Identification Number) verwenden, schließen Sie die Elin in das Feld **CompanyName** für jeden Standort ein.</span><span class="sxs-lookup"><span data-stu-id="2e082-108">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="2e082-109">Sie können mehrere Elins für jede Position einschließen, die jeweils durch ein Semikolon voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="2e082-109">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e082-110">Netzwerk Element</span><span class="sxs-lookup"><span data-stu-id="2e082-110">Network Element</span></span></th>
<th><span data-ttu-id="2e082-111">Erforderliche Spalten</span><span class="sxs-lookup"><span data-stu-id="2e082-111">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e082-112"><strong>Drahtloser Zugriffspfad</strong></span><span class="sxs-lookup"><span data-stu-id="2e082-112"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="2e082-113">&lt;BSSID &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; Hausnummer &gt; , &lt; HouseNumberSuffix &gt; , &lt; Vorrichtungs &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="2e082-113">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="2e082-114">... &lt; Streetname &gt; , &lt; "streetsuffix", Post &gt; &lt; Directional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="2e082-114">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e082-115"><strong>Subnetz</strong></span><span class="sxs-lookup"><span data-stu-id="2e082-115"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="2e082-116">&lt;Subnetz &gt; , &lt; Beschreibung &gt; , &lt; Speicherort &gt; , &lt; CompanyName &gt; , &lt; Hausnummer &gt; , &lt; HouseNumberSuffix &gt; , &lt; Vorrichtungs &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="2e082-116">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="2e082-117">... &lt; Streetname &gt; , &lt; "streetsuffix", Post &gt; &lt; Directional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="2e082-117">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e082-118"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="2e082-118"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="2e082-119">&lt;Chassis-PortIDSubType, Port-Nr &gt; &lt; &gt; &lt; &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; Hausnummer &gt; , &lt; HouseNumberSuffix &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="2e082-119">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="2e082-120">... &lt; Predirectional &gt; , &lt; streetname &gt; , &lt; "streetsuffix" &gt; , Post &lt; Directional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="2e082-120">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e082-121"><strong>Switch</strong></span><span class="sxs-lookup"><span data-stu-id="2e082-121"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="2e082-122">&lt;Fahrgestell-Nr &gt; , &lt; Beschreibung &gt; , &lt; Speicherort &gt; , &lt; CompanyName &gt; , &lt; Hausnummer &gt; , &lt; HouseNumberSuffix &gt; , &lt; Vorrichtungs &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="2e082-122">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="2e082-123">... &lt; Streetname &gt; , &lt; "streetsuffix", Post &gt; &lt; Directional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="2e082-123">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2e082-124">Wenn Sie die Standortdatenbank nicht auffüllen und der Speicherort, der in der ortungsrichtlinie **erforderlich** ist, auf **Ja** oder **Haftungsausschluss**festgelegt ist, fordert der Client den Benutzer auf, einen Speicherort manuell einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e082-124">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="2e082-125">Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2e082-125">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="2e082-126">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="2e082-126">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="2e082-127">**Gruppe-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="2e082-127">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="2e082-128">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="2e082-128">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="2e082-129">**Get-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="2e082-129">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="2e082-130">**Gruppe-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="2e082-130">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="2e082-131">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="2e082-131">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="2e082-132">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="2e082-132">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="2e082-133">**Gruppe-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="2e082-133">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="2e082-134">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="2e082-134">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="2e082-135">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="2e082-135">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="2e082-136">**Gruppe-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="2e082-136">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="2e082-137">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="2e082-137">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="2e082-138">So fügen Sie der Standortdatenbank Netzwerkelemente hinzu</span><span class="sxs-lookup"><span data-stu-id="2e082-138">To add network elements to the location database</span></span>

1.  <span data-ttu-id="2e082-139">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank einen Subnetz-Speicherort hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e082-139">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="2e082-140">Legen Sie für Elin-Gateways die Elin in das Feld CompanyName.</span><span class="sxs-lookup"><span data-stu-id="2e082-140">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="2e082-141">Sie können mehr als ein Elin einschließen.</span><span class="sxs-lookup"><span data-stu-id="2e082-141">You can include more than one ELIN.</span></span> <span data-ttu-id="2e082-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2e082-142">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="2e082-143">Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "subnets.csv" zum Massenaktualisieren von Subnet-Speicherorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e082-143">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="2e082-144">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank drahtlose Standorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e082-144">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="2e082-145">Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "waps.csv" zum Massenaktualisieren von drahtlos Standorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e082-145">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="2e082-146">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Switch-Standorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e082-146">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="2e082-147">Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "switches.csv" zum Massenaktualisieren von Switch-Speicherorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e082-147">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="2e082-148">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Port Speicherorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e082-148">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="2e082-149">Der Standardwert für PortIDSubType ist LocallyAssigned.</span><span class="sxs-lookup"><span data-stu-id="2e082-149">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="2e082-150">Sie können ihn auch auf InterfaceAlias oder InterfaceName festlegen.</span><span class="sxs-lookup"><span data-stu-id="2e082-150">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="2e082-151">Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "ports.csv" zum Massenaktualisieren von Port Speicherorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e082-151">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

