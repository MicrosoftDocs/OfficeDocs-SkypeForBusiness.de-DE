---
title: Verwalten Sie Ihre Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Netzwerkeinstellungen für Cloud-Sprachfeatures in Ihrer Microsoft Teams.
ms.openlocfilehash: 701e3900980b628f66d9d62d3dade987fee821fe
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726574"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Verwalten Sie Ihre Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams

Wenn Ihre Organisation standortbasiertes Routing für [Direct Routing](location-based-routing-plan.md) oder dynamische Notrufe [implementiert,](configure-dynamic-emergency-calling.md)müssen Sie die Netzwerkeinstellungen für die Verwendung mit diesen Cloud-Sprachfeatures in Microsoft Teams. Netzwerkeinstellungen werden verwendet, um den Standort eines Teams-Clients zu ermitteln, und umfassen Netzwerkregionen, Netzwerkstandorte, Subnetze und vertrauenswürdige IP-Adressen. Je nach Cloud-Sprachfunktion und -funktion, die Sie bereitstellen, konfigurieren Sie einige oder alle diese Einstellungen. Weitere Informationen zu diesen Begriffen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures.](cloud-voice-network-settings.md)

Sie konfigurieren Netzwerkeinstellungen auf der **Seite Netzwerktopologie** im Microsoft Teams Admin Center oder mithilfe Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Konfigurieren von Netzwerkeinstellungen im Microsoft Teams Admin Center

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Auf der Registerkarte Netzwerkstandorte der Seite  **Netzwerktopologie** definieren Sie Netzwerkregionen, Netzwerkstandorte und Subnetze. Hier können Sie einen Netzwerkstandort erstellen oder ändern, einen Standort einem Netzwerkbereich zuordnen, dem Standort ein Subnetz zuordnen, standortbasiertes Routing aktivieren und dem Standort Notfallrichtlinien zuweisen. Sie können auch Netzwerkregionen hinzufügen, die global für alle Standorte verwendet werden können.

#### <a name="add-and-configure-a-network-site"></a>Hinzufügen und Konfigurieren einer Netzwerkwebsite

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Speicherorte Netzwerktopologie , und klicken Sie  >  dann auf die **Registerkarte Netzwerkwebsites.**
2. Klicken **Sie auf** Hinzufügen , und geben Sie dann einen Namen und eine Beschreibung für die Website ein.

    ![Screenshot der Seite "Netzwerkwebsite hinzufügen"](media/manage-network-topology-add-site.png)

3. Wenn Sie die Website einem Netzwerkbereich zuordnen möchten, klicken  Sie auf Netzwerkregion hinzufügen **,** wählen Sie eine vorhandene Region aus, oder klicken Sie auf Hinzufügen, um eine Region hinzuzufügen, und klicken Sie dann auf **Verknüpfen**.  
4. Um das Location-Based für die Website zu aktivieren, aktivieren Sie **Standortbasiertes Routing**.
5. Wenn Sie der Website Richtlinien für Notdienste zuweisen möchten, gehen Sie wie folgt vor:

    - Wenn Ihre Organisation Anrufpläne verwendet oder Direktrouting Telefonsystem, wählen Sie unter Richtlinie für Notrufe die zu verwendende Richtlinie aus.
    - Wenn Ihre Organisation Telefonsystem Direct Routing bereitgestellt hat, wählen Sie unter Richtlinie für Das Routing von Notrufen die zu verwendende Richtlinie aus.

6. Wenn Sie dem Standort ein Subnetz zuordnen möchten, klicken Sie unter **Subnetze** auf **Subnetze hinzufügen**. Geben Sie die IP-Version, DIE IP-Adresse und den Netzwerkbereich an, fügen Sie eine Beschreibung hinzu, und klicken Sie dann auf **Übernehmen.** Jedes Subnetz muss einem bestimmten Standort zugeordnet sein.
7. Klicken Sie auf **Speichern**.

#### <a name="modify-a-network-site"></a>Ändern einer Netzwerkwebsite

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Speicherorte Netzwerktopologie , und klicken Sie  >  dann auf die **Registerkarte Netzwerkwebsites.**
2. Wählen Sie die Website aus, indem Sie links des Websitenamens klicken und dann auf **Bearbeiten klicken.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="manage-external-trusted-ip-addresses"></a>Verwalten von externen vertrauenswürdigen IP-Adressen

Sie verwalten externe vertrauenswürdige IP-Adressen auf der Registerkarte **Vertrauenswürdige IP-Adressen** auf der Seite Netzwerktopologie im Microsoft Teams Admin Center.  Sie können eine unbegrenzte Anzahl von externen vertrauenswürdigen IP-Adressen hinzufügen.

#### <a name="add-a-trusted-ip-address"></a>Hinzufügen einer vertrauenswürdigen IP-Adresse

1. Navigieren Sie im linken Navigationsbereich Microsoft Teams Admin Center zu Speicherorte-Netzwerktopologie , und klicken Sie dann auf die Registerkarte  >   **Vertrauenswürdige IPs.**
2. Klicken Sie auf **Neu**.
3. Geben Sie **im Bereich Vertrauenswürdige IP-Adresse** hinzufügen die IP-Version, die IP-Adresse und den Netzwerkbereich an, fügen Sie eine Beschreibung hinzu, und klicken Sie dann auf **Übernehmen.**

    ![Screenshot des Bereichs "Vertrauenswürdige IP-Adresse hinzufügen"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Bearbeiten einer vertrauenswürdigen IP-Adresse

1. Navigieren Sie im linken Navigationsbereich Microsoft Teams Admin Center zu Speicherorte-Netzwerktopologie , und klicken Sie dann auf die Registerkarte  >   **Vertrauenswürdige IPs.**
2. Wählen Sie die IP-Adresse aus, indem Sie links davon klicken und dann auf **Bearbeiten klicken.**
3. Nehmen Sie **im Bereich Vertrauenswürdige IP-Adresse** bearbeiten die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Übernehmen.**

## <a name="configure-network-settings-using-powershell"></a>Konfigurieren von Netzwerkeinstellungen mithilfe von PowerShell

Um die Schritte in diesem Abschnitt ausführen zu können, müssen Sie mit PowerShell-Cmdlets vertraut sein. Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Definieren von Netzwerkregionen

 Verwenden Sie das [Cmdlet New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) zum Definieren von Netzwerkregionen. Beachten Sie, dass der Parameter RegionID ein logischer Name ist, der die Geografie der Region darstellt und keine Abhängigkeiten oder Einschränkungen aufweist, und der Parameter CentralSite &lt; site ID &gt; ist optional.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

In diesem Beispiel erstellen wir eine Netzwerkregion namens Indien.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Siehe auch [Set-CsTenantNetworkRegion.](/powershell/module/skype/set-cstenantnetworkregion)

### <a name="define-network-sites"></a>Definieren von Netzwerkwebsites

Verwenden Sie [das Cmdlet New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) zum Definieren von Netzwerkwebsites. Jede Netzwerkwebsite muss einer Netzwerkregion zugeordnet sein.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

In diesem Beispiel erstellen wir zwei neue Netzwerkwebsites, Silben und Hyderabad, in der Region Indien.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

Die folgende Tabelle zeigt die in diesem Beispiel definierten Netzwerkwebsites.

||Website 1 |Website 2 |
|---------|---------|---------|
|Website-ID    |    Site 1 (Ing)     |  Site 2 (Hyderabad)       |
|Gebietsnummer  |     Region 1 (Indien)    |   Region 1 (Indien)      |

Siehe auch [Set-CsTenantNetworkRegion.](/powershell/module/skype/set-cstenantnetworksite)

### <a name="define-network-subnets"></a>Definieren von Netzwerk-Subnetzen

Verwenden Sie [das Cmdlet New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) zum Definieren von Netzwerksubnetzen und zum Zuordnen von Subnetzen zu Netzwerkstandorten. Jedes Netzwerksubnetz kann nur einem Standort zugeordnet werden.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

In diesem Beispiel erstellen wir eine Zuordnung zwischen dem Subnetz 192.168.0.0 und dem Standort des Mobilfunknetzwerks und zwischen Subnetz 2001:4898:e8:25:844e:926f:85ad:dd8e und dem Hyderabad-Netzwerkstandort.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

Die folgende Tabelle zeigt die in diesem Beispiel definierten Subnetze.

||Website 1 |Website 2 |
|---------|---------|---------|
|Subnetz-ID   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Mask  |     24    |   120      |
|Website-ID  | Website (Standort) | Site 2 (Hyderabad) |

Für mehrere Subnetze können Sie eine CSV-Datei mithilfe eines Skripts wie dem folgenden importieren.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

In diesem Beispiel sieht die CSV-Datei in etwa so aus:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


Siehe auch [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Definieren externer Subnetze (externe vertrauenswürdige IP-Adressen)

Verwenden Sie [das Cmdlet New-CsTenantTrustedIPAddress,](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) um externe Subnetze zu definieren und sie dem Mandanten zuzuordnen. Sie können eine unbegrenzte Anzahl externer Subnetze für einen Mandanten definieren.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Zum Beispiel:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Siehe auch [Set-CsTenantTrustedIPAddress.](/powershell/module/skype/set-cstenanttrustedipaddress)

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
