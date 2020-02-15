---
title: 'Lync Server 2013: Bereitstellen von netzwerkregionen, Standorten und Subnetzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e4db701dc3d43ed30b8101ef2af5ff2e4a2ad0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Bereitstellen von netzwerkregionen, Standorten und Subnetzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-12_

Nachdem Enterprise-VoIP bereitgestellt wurde, müssen Sie Folgendes konfigurieren:

  - Netzwerkregionen

  - Netzwerkstandorte

  - Netzwerksubnetze

<div>

## <a name="define-network-regions"></a>Definieren von netzwerkregionen

Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkRegion oder lync Server-Systemsteuerung, um netzwerkregionen zu definieren.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Weitere Informationen finden Sie unter [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

In diesem Beispiel veranschaulicht der folgende Windows PowerShell Befehl die netzwerkregion, Region 1 (Indien), die in diesem Szenario definiert ist.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Definieren von Netzwerkstandorten

Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkSite oder lync Server-Systemsteuerung, um Netzwerkstandorte zu definieren.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Weitere Informationen finden Sie unter [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

In diesem Beispiel veranschaulichen die folgenden Tabellen und lync Server Windows PowerShell Befehls die in diesem Szenario definierten Netzwerkstandorte. Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Website 1 (Delhi)</th>
<th>Standort 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Website-ID</p></td>
<td><p>Website 1 (Delhi)</p></td>
<td><p>Standort 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>Regions-ID</p></td>
<td><p>Region 1 (Indien)</p></td>
<td><p>Region 1 (Indien)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>Definieren von Netzwerk Subnetzen

Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkSubnet oder lync Server-Systemsteuerung, um Netzwerksubnetze zu definieren und Sie Netzwerkstandorten zuzuweisen.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Weitere Informationen finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell Befehle die Zuweisung von Netzwerk Subnetzen zu den in diesem Szenario definierten Netzwerkstandorten Delhi und Hyderabad. Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Website 1 (Delhi)</th>
<th>Standort 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Subnetz-ID</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Maske</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Website-ID</p></td>
<td><p>Website 1 (Delhi)</p></td>
<td><p>Standort 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren des standortbasierten Routings in lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

