---
title: 'Lync Server 2013: Auffüllen der Standortdatenbank'
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
ms.openlocfilehash: de9a5c9015dcaf83252260c89837a473a6a2291f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527972"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="16741-102">Auffüllen der Standortdatenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16741-102">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16741-103">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="16741-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="16741-104">Um Clients in einem Netzwerk automatisch zu finden, müssen Sie zunächst die Standortdatenbank mit einem Netzwerk- *Wiremap*füllen, das Netzwerkelemente den Civic-Adressen (also Straße) zuordnet.</span><span class="sxs-lookup"><span data-stu-id="16741-104">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="16741-105">Sie können Subnetze, drahtlose Zugriffspunkte, Switches und Ports verwenden, um die Wiremap zu definieren.</span><span class="sxs-lookup"><span data-stu-id="16741-105">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="16741-106">Sie können der Standortdatenbank einzeln oder in Massen eine Adresse hinzufügen, indem Sie eine CSV-Datei verwenden, die die in der folgenden Tabelle beschriebenen Spaltenformate enthält.</span><span class="sxs-lookup"><span data-stu-id="16741-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="16741-107">Wenn Sie ein Elin-Gateway (Emergency Location Identification Number) verwenden, schließen Sie die Elin in das Feld **CompanyName** für jeden Standort ein.</span><span class="sxs-lookup"><span data-stu-id="16741-107">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="16741-108">Sie können mehrere Elins für jede Position einschließen, die jeweils durch ein Semikolon voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="16741-108">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16741-109">Netzwerk Element</span><span class="sxs-lookup"><span data-stu-id="16741-109">Network Element</span></span></th>
<th><span data-ttu-id="16741-110">Erforderliche Spalten</span><span class="sxs-lookup"><span data-stu-id="16741-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16741-111"><strong>Drahtloser Zugriffspfad</strong></span><span class="sxs-lookup"><span data-stu-id="16741-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="16741-112">&lt;BSSID &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; Hausnummer &gt; , &lt; HouseNumberSuffix &gt; , &lt; Vorrichtungs &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="16741-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="16741-113">... &lt; Streetname &gt; , &lt; "streetsuffix", Post &gt; &lt; Directional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="16741-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16741-114"><strong>Subnetz</strong></span><span class="sxs-lookup"><span data-stu-id="16741-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="16741-115">&lt;Subnetz &gt; , &lt; Beschreibung &gt; , &lt; Speicherort &gt; , &lt; CompanyName &gt; , &lt; Hausnummer &gt; , &lt; HouseNumberSuffix &gt; , &lt; Vorrichtungs &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="16741-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="16741-116">... &lt; Streetname &gt; , &lt; "streetsuffix", Post &gt; &lt; Directional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="16741-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16741-117"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="16741-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="16741-118">&lt;Chassis-PortIDSubType, Port-Nr &gt; &lt; &gt; &lt; &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; Hausnummer &gt; , &lt; HouseNumberSuffix &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="16741-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="16741-119">... &lt; Predirectional &gt; , &lt; streetname &gt; , &lt; "streetsuffix" &gt; , Post &lt; Directional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="16741-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16741-120"><strong>Switch</strong></span><span class="sxs-lookup"><span data-stu-id="16741-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="16741-121">&lt;Fahrgestell-Nr &gt; , &lt; Beschreibung &gt; , &lt; Speicherort &gt; , &lt; CompanyName &gt; , &lt; Hausnummer &gt; , &lt; HouseNumberSuffix &gt; , &lt; Vorrichtungs &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="16741-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="16741-122">... &lt; Streetname &gt; , &lt; "streetsuffix", Post &gt; &lt; Directional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="16741-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="16741-123">Wenn Sie die Standortdatenbank nicht auffüllen und der Speicherort, der in der ortungsrichtlinie **erforderlich** ist, auf **Ja** oder **Haftungsausschluss**festgelegt ist, fordert der Client den Benutzer auf, einen Speicherort manuell einzugeben.</span><span class="sxs-lookup"><span data-stu-id="16741-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="16741-124">Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="16741-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="16741-125">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="16741-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="16741-126">**Gruppe-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="16741-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="16741-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="16741-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="16741-128">**Get-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="16741-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="16741-129">**Gruppe-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="16741-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="16741-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="16741-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="16741-131">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="16741-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="16741-132">**Gruppe-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="16741-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="16741-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="16741-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="16741-134">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="16741-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="16741-135">**Gruppe-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="16741-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="16741-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="16741-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="16741-137">So fügen Sie der Standortdatenbank Netzwerkelemente hinzu</span><span class="sxs-lookup"><span data-stu-id="16741-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="16741-138">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank einen Subnetz-Speicherort hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="16741-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="16741-139">Legen Sie für Elin-Gateways die Elin in das Feld CompanyName.</span><span class="sxs-lookup"><span data-stu-id="16741-139">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="16741-140">Sie können mehr als ein Elin einschließen.</span><span class="sxs-lookup"><span data-stu-id="16741-140">You can include more than one ELIN.</span></span> <span data-ttu-id="16741-141">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="16741-141">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="16741-142">Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "subnets.csv" zum Massenaktualisieren von Subnet-Speicherorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="16741-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="16741-143">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank drahtlose Standorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="16741-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="16741-144">Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "waps.csv" zum Massenaktualisieren von drahtlos Standorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="16741-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="16741-145">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Switch-Standorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="16741-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="16741-146">Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "switches.csv" zum Massenaktualisieren von Switch-Speicherorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="16741-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="16741-147">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Port Speicherorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="16741-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="16741-148">Der Standardwert für PortIDSubType ist LocallyAssigned.</span><span class="sxs-lookup"><span data-stu-id="16741-148">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="16741-149">Sie können ihn auch auf InterfaceAlias oder InterfaceName festlegen.</span><span class="sxs-lookup"><span data-stu-id="16741-149">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="16741-150">Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "ports.csv" zum Massenaktualisieren von Port Speicherorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="16741-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

