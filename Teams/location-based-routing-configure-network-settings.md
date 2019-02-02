---
title: Konfigurieren von Netzwerkeinstellungen für standortbasierte Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zum Erstellen und Einrichten von netzwerkregionen, Standorten und Subnetzen für standortbasierte Routing zum direkten weiterleiten.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: adb84f58c48292c13bd4af6f355f5e4da22458c9
ms.sourcegitcommit: 9f767b48e5f0eaf43869cba9c42ba3ba3225bcf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2019
ms.locfileid: "29715477"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Konfigurieren von Netzwerkeinstellungen für standortbasierte Routing 

Wenn Sie noch nicht haben lesen [Plan Location-Based Routing für das direkte Routing getan](location-based-routing-plan.md) , um weitere Schritte anzuzeigen müssen Sie vor der Bereitstellung von Netzwerkeinstellungen für standortbasierte Routing übernehmen.

In diesem Artikel wird beschrieben, wie Netzwerk für standortbasierte Routing konfigurieren. Nach der Bereitstellung von Telefon System direkten Routing in Ihrer Organisation sind die nächsten Schritte zum Erstellen und Einrichten von netzwerkregionen, Netzwerkstandorten und Netzwerksubnetzen. Um die Schritte in diesem Artikel ausführen zu können, benötigen Sie einige gute Kenntnisse im Umgang mit PowerShell-Cmdlets. Weitere Informationen finden Sie unter [Teams PowerShell (Übersicht)](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Definieren von netzwerkregionen
 Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche. Verwendung der ``New-CsTenantNetworkRegion`` PowerShell-Cmdlet, um netzwerkregionen zu definieren. Beachten Sie, dass die ``RegionID`` Parameter ist ein logischer Name, der die Region des Bereichs darstellt und hat keine Abhängigkeiten oder Einschränkungen und der ``CentralSite <site ID>`` Parameter ist optional. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

In diesem Beispiel erstellen wir eine netzwerkregion, die mit dem Namen Indien. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Definieren von Netzwerkstandorten

Verwendung der ``New-CsTenantNetworkSitePowerShell`` PowerShell-Cmdlet, um Netzwerkstandorte zu definieren. 

```
New-CsTenantNetworkSite -NetworkRegionID <region ID>  
```
In diesem Beispiel erstellen wir zwei neue Netzwerkstandorte Delhi und Hyderabad, in dem Bereich Indien. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
Die folgende Tabelle zeigt der Netzwerkstandorte, die in diesem Beispiel definiert. 

||Standort 1 |Standort 2 |
|---------|---------|---------|
|Site-ID    |    Website 1 (Delhi)     |  Standort 2 (Hyderabad)       |
|Bereichs-ID  |     Region 1 (Indien)    |   Region 1 (Indien)      |

## <a name="define-network-subnets"></a>Definieren von Netzwerksubnetzen

Verwendung der ``New-Cs-TenantNetworkSubnet`` -Cmdlet zum Definieren von Netzwerksubnetzen und verknüpfen Sie diese mit Netzwerkstandorten. Jeder internen Subnetz kann nur einem einzigen Standort zugeordnet werden. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz 192.168.0.0 und dem Netzwerkstandort Delhi und zwischen Subnetz 192.168.1.0 und dem Netzwerkstandort Hyderabad.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
Die folgende Tabelle zeigt die Subnetze in diesem Beispiel definiert. 

||Standort 1 |Standort 2 |
|---------|---------|---------|
|Subnetz-ID   |    192.168.0.0     |  192.168.1.0     |
|Maske  |     24    |   24      |
|Site-ID  | Website (Delhi) | Standort 2 (Hyderabad) |

Für mehrere Subnetze können Sie eine CSV-Datei mithilfe eines Skripts wie die folgenden importieren.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
In diesem Beispiel sieht die CSV-Datei etwa so aussehen:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Definieren der externen Subnetze
Verwendung der ``New-Cs-TenantTrustedIPAddress`` -Cmdlet zum Definieren von externen Subnetze und weisen Sie diese den Mandanten. Sie können eine unbegrenzte Anzahl von Subnetzen für einen Mandanten definieren. 
```
New-CsTenantTrustedIPAddress -IPAddress <Subnet IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Beispiel:
```
New-CsTenantTrustedIPAddress -IPAddress 192.168.0.1 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zur [speicherortbasierte Routing für die direkte Weiterleitung aktivieren](location-based-routing-enable.md).

### <a name="related-topics"></a>Verwandte Themen
- [Planen Sie die Standortbasierte Weiterleitung für direkten Routing](location-based-routing-plan.md)
- [Speicherortbasierte Routing Terminologie](location-based-routing-terminology.md)