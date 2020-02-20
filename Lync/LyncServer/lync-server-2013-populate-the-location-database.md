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
ms.openlocfilehash: 161a418728362da4817610dfa8e13be3046e3df6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>Auffüllen der Standortdatenbank in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

Um Clients in einem Netzwerk automatisch zu finden, müssen Sie zunächst die Standortdatenbank mit einem Netzwerk- *Wiremap*füllen, das Netzwerkelemente den Civic-Adressen (also Straße) zuordnet. Sie können Subnetze, drahtlose Zugriffspunkte, Switches und Ports verwenden, um die Wiremap zu definieren.

Sie können der Standortdatenbank einzeln oder in Massen eine Adresse hinzufügen, indem Sie eine CSV-Datei verwenden, die die in der folgenden Tabelle beschriebenen Spaltenformate enthält.

Wenn Sie ein Elin-Gateway (Emergency Location Identification Number) verwenden, schließen Sie die Elin in das Feld **CompanyName** für jeden Standort ein. Sie können mehrere Elins für jede Position einschließen, die jeweils durch ein Semikolon voneinander getrennt sind.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Netzwerk Element</th>
<th>Erforderliche Spalten</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Drahtloser Zugriffspfad</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;Hausnummer&gt;,&lt;HouseNumberSuffix&gt;,&lt;Vorrichtungs&gt;,...</p>
<p>... &lt;Streetname&gt;,&lt;"streetsuffix"&gt;&lt;, Post Directional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;&gt;PostalCode&lt;, Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnetz</strong></p></td>
<td><p>&lt;Subnetz&gt;,&lt;Beschreibung&gt;,&lt;Speicherort&gt;,&lt;CompanyName&gt;,&lt;Hausnummer&gt;,&lt;HouseNumberSuffix&gt;,&lt;Vorrichtungs&gt;,...</p>
<p>... &lt;Streetname&gt;,&lt;"streetsuffix"&gt;&lt;, Post Directional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;&gt;PostalCode&lt;, Country&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;&gt;Chassis-&lt;PortIDSubType&gt;,&lt;Port-&gt;Nr&lt;,&gt;Description&lt;,&gt;Location&lt;,&gt;CompanyName&lt;,&gt;Hausnummer&lt;,&gt;HouseNumberSuffix,...</p>
<p>... &lt;Predirectional&gt;,&lt;streetname&gt;,&lt;"streetsuffix"&gt;,&lt;Post Directional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;&gt;PostalCode&lt;, Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Switch</strong></p></td>
<td><p>&lt;Fahrgestell-&gt;Nr&lt;,&gt;Beschreibung&lt;,&gt;Speicherort&lt;,&gt;CompanyName&lt;,&gt;Hausnummer&lt;,&gt;HouseNumberSuffix&lt;, Vorrichtungs&gt;,...</p>
<p>... &lt;Streetname&gt;,&lt;"streetsuffix"&gt;&lt;, Post Directional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;&gt;PostalCode&lt;, Country&gt;</p></td>
</tr>
</tbody>
</table>


Wenn Sie die Standortdatenbank nicht auffüllen und der Speicherort, der in der ortungsrichtlinie **erforderlich** ist, auf **Ja** oder **Haftungsausschluss**festgelegt ist, fordert der Client den Benutzer auf, einen Speicherort manuell einzugeben.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:

  - **Get-CsLisSubnet**

  - **Gruppe-CsLisSubnet**

  - Remove-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Gruppe-CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Gruppe-CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **Get-CsLisPort**

  - **Gruppe-CsLisPort**

  - **Remove-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>So fügen Sie der Standortdatenbank Netzwerkelemente hinzu

1.  Führen Sie das folgende Cmdlet aus, um der Standortdatenbank einen Subnetz-Speicherort hinzuzufügen.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Legen Sie für Elin-Gateways die Elin in das Feld CompanyName. Sie können mehr als ein Elin einschließen. Zum Beispiel:
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "Subnetze. csv" verwenden, um Massenaktualisierungen für Subnet-Speicherorte durchzuführen.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Führen Sie das folgende Cmdlet aus, um der Standortdatenbank drahtlose Standorte hinzuzufügen.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "WAPs. csv" zum Massenaktualisieren von drahtlos Standorten verwenden.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Switch-Standorte hinzuzufügen.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "Switches. csv" zum Massenaktualisieren von Switch-Standorten verwenden.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Port Speicherorte hinzuzufügen.
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Der Standardwert für PortIDSubType ist LocallyAssigned. Sie können ihn auch auf InterfaceAlias oder InterfaceName festlegen.
    
    Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "Ports. csv" zum Massenaktualisieren von Port Speicherorten verwenden.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

