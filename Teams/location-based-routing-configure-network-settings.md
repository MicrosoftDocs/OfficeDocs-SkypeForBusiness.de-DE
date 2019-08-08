---
title: Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie netzwerkregionen,-Standorte und-Subnetze für standortbasiertes Routing für das direkte Routing erstellen und einrichten.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245106"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Wenn Sie dies noch nicht getan haben, lesen Sie [Planen des ortsbasierten Routings für das direkte Routing](location-based-routing-plan.md) , um weitere Schritte zu überprüfen, die Sie ausführen müssen, bevor Sie die Netzwerkeinstellungen für standortbasiertes Routing konfigurieren.

In diesem Artikel wird beschrieben, wie Sie Netzwerkeinstellungen für standortbasiertes Routing konfigurieren. Nachdem Sie die direkte Weiterleitung des Telefonsystems in Ihrer Organisation bereitgestellt haben, besteht der nächste Schritt darin, netzwerkregionen, Netzwerk Websites und Netzwerk-Subnets zu erstellen und einzurichten. Um die Schritte in diesem Artikel ausführen zu können, müssen Sie sich mit PowerShell-Cmdlets vertraut machen. Weitere Informationen finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Definieren von netzwerkregionen
 Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg. Verwenden Sie das Cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) , um netzwerkregionen zu definieren. Beachten Sie, dass der Parameter "Regions-ID" ein logischer Name ist, der die Geographie des Bereichs darstellt &lt;und keine&gt; Abhängigkeiten oder Einschränkungen aufweist, und der CentralSite-Parameter der Website-ID optional ist. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

In diesem Beispiel erstellen wir eine netzwerkregion mit dem Namen Indien. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Definieren von Netzwerk Websites

Verwenden Sie das Cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) , um Netzwerk Websites zu definieren. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
In diesem Beispiel erstellen wir zwei neue Netzwerkstandorte, Delhi und Hyderabad, in der Region Indien. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
In der folgenden Tabelle sind die Netzwerk Websites aufgeführt, die in diesem Beispiel definiert sind. 

||Website 1 |Website 2 |
|---------|---------|---------|
|Website-ID    |    Website 1 (Delhi)     |  Website 2 (Hyderabad)       |
|Regions-ID  |     Region 1 (Indien)    |   Region 1 (Indien)      |

## <a name="define-network-subnets"></a>Definieren von Netzwerk-Subnetzen

Verwenden Sie das Cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) , um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen. Jedes interne Subnetz kann nur einer Website zugeordnet werden. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz-192.168.0.0 und der Delhi-Netzwerk Website und zwischen Subnetz 2001:4898: E8:25:844E: 926f: 85ad: dd8e und der Hyderabad-Netzwerk Website.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
In der folgenden Tabelle sind die in diesem Beispiel definierten Subnets aufgeführt. 

||Website 1 |Website 2 |
|---------|---------|---------|
|Subnet-ID   |    192.168.0.0     |  2001:4898: E8:25:844E: 926f: 85ad: dd8e     |
|Format  |     24    |   120      |
|Website-ID  | Website (Delhi) | Website 2 (Hyderabad) |

Bei mehreren Subnetzen können Sie eine CSV-Datei mit einem Skript wie dem folgenden importieren.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
In diesem Beispiel sieht die CSV-Datei etwa wie folgt aus:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Definieren externer Subnetze
Verwenden Sie das Cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) , um externe Subnetze zu definieren und dem Mandanten zuzuweisen. Sie können eine unbegrenzte Anzahl von Subnetzen für einen Mandanten definieren. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Beispiel:
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zum [Aktivieren des ortsbasierten Routings für das direkte Routing](location-based-routing-enable.md).

### <a name="related-topics"></a>Verwandte Themen
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Terminologie für das standortbasierte Routing](location-based-routing-terminology.md)
