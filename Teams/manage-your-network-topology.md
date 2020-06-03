---
title: Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams konfigurieren.
ms.openlocfilehash: 03eaeac1bce07cffa7dc000f964f080361a37d40
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539625"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams

Wenn in Ihrer Organisation [standortbasiertes Routing für direktes Routing](location-based-routing-plan.md) oder [dynamische Notrufe](configure-dynamic-emergency-calling.md)bereitgestellt wird, müssen Sie die Netzwerkeinstellungen für die Verwendung dieser Cloud-Sprachfeatures in Microsoft Teams konfigurieren. Netzwerkeinstellungen werden verwendet, um den Standort eines Teams-Clients zu ermitteln und netzwerkregionen, Netzwerk Websites, Subnetze und vertrauenswürdige IP-Adressen einzubeziehen. Je nach der von Ihnen bereitgestellten Cloud-Sprachfunktion und-Funktion konfigurieren Sie einige oder alle dieser Einstellungen. Weitere Informationen zu diesen Begriffen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md).

Sie konfigurieren die Netzwerkeinstellungen auf der Seite **Netzwerktopologie** des Microsoft Teams admin Centers oder mithilfe von Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Konfigurieren von Netzwerkeinstellungen im Microsoft Teams Admin Center

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Sie definieren netzwerkregionen, Netzwerk Websites und Subnetze auf der Registerkarte **Netzwerk Websites** auf der Seite **Netzwerktopologie** . Hier können Sie eine Netzwerk Website erstellen oder ändern, eine Website mit einem Netzwerkbereich verknüpfen, der Website ein Subnetz zuordnen, standortbasiertes Routing aktivieren und der Website Notfall Richtlinien zuweisen. Sie können auch netzwerkregionen hinzufügen, die für alle Websites Global verwendet werden können.

#### <a name="add-and-configure-a-network-site"></a>Hinzufügen und Konfigurieren einer Netzwerk Website

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**-  >  **Netzwerktopologie**, und klicken Sie dann auf die Registerkarte **Netzwerk Websites** .
2. Klicken Sie auf **Hinzufügen**, und geben Sie dann einen Namen und eine Beschreibung für die Website ein.

    ![Screenshot der Seite "Netzwerk Website hinzufügen"](media/manage-network-topology-add-site.png)

3. Wenn Sie die Website einem Netzwerkbereich zuordnen möchten, klicken Sie auf **Netzwerkbereich hinzufügen**, wählen Sie einen vorhandenen Bereich aus, oder klicken Sie auf **hinzu** fügen, um einen Bereich hinzuzufügen, und klicken Sie dann auf **Verknüpfen**.  
4. Um standortbasiertes Routing für die Website zu aktivieren, aktivieren Sie **standortbasiertes Routing**.
5. Führen Sie eine oder beide der folgenden Aktionen aus, um der Website Notfalldienst Richtlinien zuzuweisen:

    - Wenn in Ihrer Organisation Anrufpläne oder ein direktes Routing für das Telefon System verwendet wird, wählen Sie unter **Notruf Richtlinie**die gewünschte Richtlinie aus.
    - Wenn Ihre Organisation ein direktes Routing für Telefonsysteme bereitgestellt hat, wählen Sie unter **Notfall Routing Richtlinie**die gewünschte Richtlinie aus.

6. Wenn Sie der Website ein Subnetz zuordnen möchten, klicken Sie unter **Subnetze**auf **Subnets hinzufügen**. Geben Sie die IP-Version, die IP-Adresse, den Netzwerkbereich an, fügen Sie eine Beschreibung hinzu, und klicken Sie dann auf über **nehmen**. Jedes Subnetz muss einer bestimmten Website zugeordnet sein.
7. Klicken Sie auf **Speichern**.

#### <a name="modify-a-network-site"></a>Ändern einer Netzwerk Website

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**-  >  **Netzwerktopologie**, und klicken Sie dann auf die Registerkarte **Netzwerk Websites** .
2. Wählen Sie die Website aus, indem Sie links neben dem Websitenamen klicken, und klicken Sie dann auf **Bearbeiten**.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **speichern.**

### <a name="manage-external-trusted-ip-addresses"></a>Verwalten externer vertrauenswürdiger IP-Adressen

Sie verwalten externe vertrauenswürdige IP-Adressen auf der Registerkarte **Vertrauenswürdige IPS** auf der Seite **Netzwerktopologie** des Microsoft Teams admin Centers. Sie können eine unbegrenzte Anzahl externer vertrauenswürdiger IP-Adressen hinzufügen.

#### <a name="add-a-trusted-ip-address"></a>Hinzufügen einer vertrauenswürdigen IP-Adresse

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**-  >  **Netzwerktopologie**, und klicken Sie dann auf die Registerkarte **Vertrauenswürdige IPS** .
2. Klicken Sie auf **Neu**.
3. Geben Sie im Bereich **Vertrauenswürdige IP-Adresse hinzufügen** die IP-Version, die IP-Adresse, den Netzwerkbereich und eine Beschreibung ein, und klicken Sie dann auf über **nehmen**.

    ![Screenshot des Bereichs "Vertrauenswürdige IP-Adresse hinzufügen"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Bearbeiten einer vertrauenswürdigen IP-Adresse

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**-  >  **Netzwerktopologie**, und klicken Sie dann auf die Registerkarte **Vertrauenswürdige IPS** .
2. Wählen Sie die IP-Adresse aus, indem Sie links davon klicken, und klicken Sie dann auf **Bearbeiten**.
3. Nehmen Sie im Bereich **Vertrauenswürdige IP-Adresse bearbeiten** die gewünschten Änderungen vor, und klicken Sie dann auf über **nehmen**.

## <a name="configure-network-settings-using-powershell"></a>Konfigurieren von Netzwerkeinstellungen mithilfe von PowerShell

Zum Ausführen der Schritte in diesem Abschnitt benötigen Sie einige Vertrautheit mit PowerShell-Cmdlets. Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Definieren von netzwerkregionen

 Verwenden Sie das Cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) , um netzwerkregionen zu definieren. Beachten Sie, dass der Parameter "Regions-ID" ein logischer Name ist, der die Geographie des Bereichs darstellt und keine Abhängigkeiten oder Einschränkungen aufweist, und der CentralSite- &lt; Parameter der Website-ID &gt; optional ist.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

In diesem Beispiel erstellen wir eine netzwerkregion mit dem Namen Indien.
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Siehe auch [Satz-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Definieren von Netzwerk Websites

Verwenden Sie das Cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) , um Netzwerk Websites zu definieren. Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

In diesem Beispiel erstellen wir zwei neue Netzwerkstandorte, Delhi und Hyderabad, in der Region Indien.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

In der folgenden Tabelle sind die Netzwerk Websites aufgeführt, die in diesem Beispiel definiert sind.

||Website 1 |Website 2 |
|---------|---------|---------|
|Website-ID    |    Website 1 (Delhi)     |  Website 2 (Hyderabad)       |
|Regions-ID  |     Region 1 (Indien)    |   Region 1 (Indien)      |

Siehe auch [Satz-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Definieren von Netzwerk-Subnetzen

Verwenden Sie das Cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) , um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen. Jedes Netzwerk Subnetz kann nur einer Website zugeordnet werden.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz-192.168.0.0 und der Delhi-Netzwerk Website und zwischen Subnetz 2001:4898: E8:25:844E: 926f: 85ad: dd8e und der Hyderabad-Netzwerk Website.

```PowerShell
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

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

In diesem Beispiel sieht die CSV-Datei etwa wie folgt aus:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

Siehe auch [Satz-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Definieren externer Subnetze (externe vertrauenswürdige IP-Adressen)

Verwenden Sie das Cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) , um externe Subnetze zu definieren und dem Mandanten zuzuweisen. Sie können eine unbegrenzte Anzahl von externen Subnetzen für einen Mandanten definieren.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Beispiel:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Siehe auch [Satz-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
