---
title: Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams konfigurieren.
ms.openlocfilehash: c77f1e6d31953ce529bff1fab6aa16e1d889e29f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101061"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams

Wenn Ihre Organisation standortbasiertes Routing für [Direct Routing](location-based-routing-plan.md) oder dynamische Notrufe bereitgestellt [hat,](configure-dynamic-emergency-calling.md)müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Cloud-Sprachfeatures in Microsoft Teams konfigurieren. Netzwerkeinstellungen werden verwendet, um den Speicherort eines Teams-Clients zu bestimmen und Netzwerkregionen, Netzwerkwebsites, Subnetze und vertrauenswürdige IP-Adressen zu umfassen. Abhängig von der Cloud-Sprachfunktion und -funktion, die Sie bereitstellen, konfigurieren Sie einige oder alle diese Einstellungen. Weitere Informationen zu diesen Begriffen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures.](cloud-voice-network-settings.md)

Sie konfigurieren Netzwerkeinstellungen auf der **Seite Netzwerktopologie** im Microsoft Teams Admin Center oder mithilfe Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Konfigurieren von Netzwerkeinstellungen im Microsoft Teams Admin Center

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Sie definieren Netzwerkregionen, Netzwerkwebsites und Subnetze auf der **Registerkarte** Netzwerkwebsites auf der **Seite Netzwerktopologie.** Hier können Sie eine Netzwerkwebsite erstellen oder ändern, eine Website einer Netzwerkregion zuordnen, ein Subnetz der Website zuordnen, standortbasiertes Routing aktivieren und der Website Notfallrichtlinien zuweisen. Sie können auch Netzwerkregionen hinzufügen, die global für alle Websites verwendet werden können.

#### <a name="add-and-configure-a-network-site"></a>Hinzufügen und Konfigurieren einer Netzwerkwebsite

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Topologie** des Speicherortnetzwerks, und klicken Sie dann auf die Registerkarte  >   **Netzwerkwebsites.**
2. Klicken **Sie auf** Hinzufügen , und geben Sie dann einen Namen und eine Beschreibung für die Website ein.

    ![Screenshot der Seite "Netzwerkwebsite hinzufügen"](media/manage-network-topology-add-site.png)

3. Wenn Sie die Website einem Netzwerkbereich zuordnen möchten, klicken  Sie auf Netzwerkbereich **hinzufügen,** wählen Sie eine vorhandene Region aus, oder klicken Sie auf Hinzufügen, um eine Region hinzuzufügen, und klicken Sie dann auf **Verknüpfen**.  
4. Um das Location-Based für die Website zu aktivieren, aktivieren Sie **standortbasiertes Routing.**
5. Wenn Sie der Website Richtlinien für Notdienste zuweisen möchten, gehen Sie wie folgt vor:

    - Wenn Ihre Organisation Anrufpläne oder das bereitgestellte Direkte Telefonsystemrouting verwendet, wählen Sie unter Richtlinie für Notrufe die von Ihnen ausgewählte Richtlinie aus.
    - Wenn Ihre Organisation das direkte Routing des Telefonsystems bereitgestellt hat, wählen Sie unter **Richtlinie** für das Routing von Notrufen die richtlinie aus, die Sie verwenden möchten.

6. Wenn Sie ein Subnetz dem Standort zuordnen möchten, klicken Sie unter **Subnetze** **auf Subnetze hinzufügen.** Geben Sie die IP-Version, die IP-Adresse, den Netzwerkbereich an, fügen Sie eine Beschreibung hinzu, und klicken Sie dann auf **Übernehmen.** Jedes Subnetz muss einer bestimmten Website zugeordnet sein.
7. Klicken Sie auf **Speichern**.

#### <a name="modify-a-network-site"></a>Ändern einer Netzwerkwebsite

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Topologie** des Speicherortnetzwerks, und klicken Sie dann auf die Registerkarte  >   **Netzwerkwebsites.**
2. Wählen Sie die Website aus, indem Sie links vom Websitenamen klicken und dann auf **Bearbeiten klicken.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="manage-external-trusted-ip-addresses"></a>Verwalten externer vertrauenswürdiger IP-Adressen

Sie verwalten externe vertrauenswürdige IP-Adressen auf der Registerkarte **Vertrauenswürdige IPs** auf der Seite **Netzwerktopologie** im Microsoft Teams Admin Center. Sie können eine unbegrenzte Anzahl von externen vertrauenswürdigen IP-Adressen hinzufügen.

#### <a name="add-a-trusted-ip-address"></a>Hinzufügen einer vertrauenswürdigen IP-Adresse

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Topologie** des Speicherortnetzwerks, und klicken Sie dann auf die Registerkarte  >   **Vertrauenswürdige IPs.**
2. Klicken Sie auf **Neu**.
3. Geben Sie im Bereich vertrauenswürdige **IP-Adresse** hinzufügen die IP-Version, die IP-Adresse, den Netzwerkbereich an, fügen Sie eine Beschreibung hinzu, und klicken Sie dann auf **Übernehmen.**

    ![Screenshot des Bereichs "Vertrauenswürdige IP-Adresse hinzufügen"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Bearbeiten einer vertrauenswürdigen IP-Adresse

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Topologie** des Speicherortnetzwerks, und klicken Sie dann auf die Registerkarte  >   **Vertrauenswürdige IPs.**
2. Wählen Sie die IP-Adresse aus, indem Sie links davon klicken und dann auf **Bearbeiten klicken.**
3. Nehmen Sie im Bereich vertrauenswürdige **IP-Adresse** bearbeiten die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Übernehmen.**

## <a name="configure-network-settings-using-powershell"></a>Konfigurieren von Netzwerkeinstellungen mit PowerShell

Um die Schritte in diesem Abschnitt ausführen zu können, benötigen Sie einige Vertrautheit mit PowerShell-Cmdlets. Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Definieren von Netzwerkregionen

 Verwenden Sie [das Cmdlet New-CsTenantNetworkRegion,](/powershell/module/skype/New-CsTenantNetworkRegion) um Netzwerkregionen zu definieren. Beachten Sie, dass der Parameter RegionID ein logischer Name ist, der die Geographie der Region darstellt und keine Abhängigkeiten oder Einschränkungen aufweist, und der Parameter "Website-ID der Zentralwebsite" &lt; &gt; ist optional.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

In diesem Beispiel erstellen wir eine Netzwerkregion mit dem Namen Indien.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Siehe auch [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Definieren von Netzwerkwebsites

Verwenden Sie [das Cmdlet New-CsTenantNetworkSite,](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) um Netzwerkwebsites zu definieren. Jede Netzwerkwebsite muss einer Netzwerkregion zugeordnet sein.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

In diesem Beispiel erstellen wir zwei neue Netzwerkwebsites, Delhi und Hyderabad, in der Region Indien.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

Die folgende Tabelle zeigt die in diesem Beispiel definierten Netzwerkwebsites.

||Website 1 |Website 2 |
|---------|---------|---------|
|Website-ID    |    Website 1 (Delhi)     |  Website 2 (Hyderabad)       |
|Region ID  |     Region 1 (Indien)    |   Region 1 (Indien)      |

Siehe auch [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Definieren von Netzwerksubnetzen

Verwenden Sie [das Cmdlet New-CsTenantNetworkSubnet,](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) um Netzwerksubnetze zu definieren und sie Netzwerkwebsites zuzuordnen. Jedes Netzwerksubnetz kann nur einer Website zugeordnet werden.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz 192.168.0.0 und der Netzwerkwebsite in Delhi und zwischen Subnetz 2001:4898:e8:25:844e:926f:85ad:dd8e und der Hyderabad-Netzwerkwebsite.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

Die folgende Tabelle zeigt die in diesem Beispiel definierten Subnetze.

||Website 1 |Website 2 |
|---------|---------|---------|
|Subnetz-ID   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Maske  |     24    |   120      |
|Website-ID  | Website (Delhi) | Website 2 (Hyderabad) |

Bei mehreren Subnetzen können Sie eine CSV-Datei mithilfe eines Skripts importieren, z. B. das folgende.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

In diesem Beispiel sieht die CSV-Datei etwa so aus:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


Siehe auch [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Definieren externer Subnetze (externe vertrauenswürdige IP-Adressen)

Verwenden Sie [das Cmdlet New-CsTenantTrustedIPAddress,](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) um externe Subnetze zu definieren und sie dem Mandanten zuzuordnen. Sie können eine unbegrenzte Anzahl von externen Subnetzen für einen Mandanten definieren.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Beispiel:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Siehe auch [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
