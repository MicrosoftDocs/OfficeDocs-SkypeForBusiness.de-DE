---
title: Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013
TOCTitle: Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994067(v=OCS.15)
ms:contentKeyID: 52056438
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Nachdem Enterprise-VoIP bereitgestellt wurde, müssen Sie Folgendes konfigurieren:

  - Netzwerkregionen

  - Netzwerkstandorte

  - Netzwerksubnetze

## Definieren von Netzwerkregionen

Verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsNetworkRegion" oder Lync Server-Systemsteuerung, um Netzwerkregionen zu definieren.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Weitere Informationen finden Sie unter [New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion).

Im Rahmen dieses Beispiel veranschaulicht der folgende Windows PowerShell-Befehl die Netzwerkregion, Region 1 (Indien), die in diesem Szenario definiert wird.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"


## Definieren von Netzwerkstandorten

Verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsNetworkSite" oder Lync Server-Systemsteuerung, um Netzwerkstandorte zu definieren.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Weitere Informationen finden Sie unter [New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite).

Im Rahmen dieses Beispiels veranschaulichen die folgende Tabelle und der Lync ServerWindows PowerShell-Befehl die in diesem Szenario definierten Netzwerkstandorte. Aus Gründen der Anschaulichkeit enthält die Tabelle nur Einträge, die für standortbasiertes Routing spezifisch sind.

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
<th>Standort 1 (Delhi)</th>
<th>Standort 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standort-ID</p></td>
<td><p>Standort 1 (Delhi)</p></td>
<td><p>Standort 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>Regions-ID</p></td>
<td><p>Region 1 (Indien)</p></td>
<td><p>Region 1 (Indien)</p></td>
</tr>
</tbody>
</table>



## Definieren von Netzwerksubnetzen

Verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsNetworkSubnet" oder Lync Server-Systemsteuerung, um Netzwerksubnetze zu definieren und sie Netzwerkstandorten zuzuordnen.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Weitere Informationen finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet).

Im Rahmen dieses Beispiels veranschaulichen die folgende Tabelle und die Windows PowerShell-Befehle die Zuweisung von Netzwerksubnetzen zu den Netzwerkstandorten Delhi und Hyderabad, die in diesem Szenario definiert werden. Aus Gründen der Anschaulichkeit wurden in die Tabelle nur Einstellungen aufgenommen, die für das standortbasierte Routing spezifisch sind.

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
<th>Standort 1 (Delhi)</th>
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
<td><p>Standort-ID</p></td>
<td><p>Standort 1 (Delhi)</p></td>
<td><p>Standort 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## Siehe auch

#### Weitere Ressourcen

[Konfigurieren von standortbasiertem Routing in Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

