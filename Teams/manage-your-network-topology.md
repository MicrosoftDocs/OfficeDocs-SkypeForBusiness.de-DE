---
title: Verwalten der Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams
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
ms.openlocfilehash: 7d8bc7f06934134538fca59a3f19285d97756e2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802575"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Verwalten der Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams

Wenn Ihre Organisation standortbasiertes Routing für Direktes Routing oder dynamische Notrufe [implementiert,](configure-dynamic-emergency-calling.md)müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Cloud-Voice-Features in Microsoft Teams konfigurieren. [](location-based-routing-plan.md) Netzwerkeinstellungen werden verwendet, um den Standort eines Teamclients zu ermitteln und Netzwerkregionen, Netzwerkstandorte, Subnetze und vertrauenswürdige IP-Adressen zu umfassen. Abhängig von der Cloud-Sprachfunktion und -funktion, die Sie bereitstellen, konfigurieren Sie einige oder alle diese Einstellungen. Weitere Informationen zu diesen Begriffen finden Sie unter ["Netzwerkeinstellungen für Cloud-Sprachfeatures".](cloud-voice-network-settings.md)

Sie konfigurieren Netzwerkeinstellungen auf der **Seite "Netzwerktopologie"** im Microsoft Teams Admin Center oder mithilfe Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Konfigurieren von Netzwerkeinstellungen im Microsoft Teams Admin Center

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Auf der Registerkarte "Netzwerkstandorte" der  Seite "Netzwerktopologie" definieren Sie Netzwerkregionen, Netzwerkstandorte **und Subnetze.** Hier können Sie einen Netzwerkstandort erstellen oder ändern, einen Standort einem Netzwerkbereich zuordnen, dem Standort ein Subnetz zuordnen, standortbasiertes Routing aktivieren und dem Standort Notfallrichtlinien zuweisen. Sie können auch Netzwerkregionen hinzufügen, die global für alle Standorte verwendet werden können.

#### <a name="add-and-configure-a-network-site"></a>Hinzufügen und Konfigurieren einer Netzwerkwebsite

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Topologie des Standortnetzwerks, und klicken Sie dann auf die Registerkarte  >   **"Netzwerkwebsites".**
2. Klicken Sie **auf**"Hinzufügen", und geben Sie einen Namen und eine Beschreibung für die Website ein.

    ![Screenshot der Seite "Netzwerkwebsite hinzufügen"](media/manage-network-topology-add-site.png)

3. Wenn Sie die Website einem Netzwerkbereich zuordnen möchten, klicken  Sie auf "Netzwerkbereich hinzufügen", wählen Sie eine vorhandene Region aus, oder klicken Sie auf "Hinzufügen", um eine Region hinzuzufügen, und klicken Sie dann auf **"Link".**  
4. Um das Location-Based für die Website zu aktivieren, aktivieren Sie **standortbasiertes Routing.**
5. Wenn Sie der Website Notfallrichtlinien zuweisen möchten, gehen Sie wie folgt vor:

    - Wenn Ihre Organisation Anrufpläne oder das bereitgestellte Direkte Telefonsystem-Routing verwendet, wählen Sie unter "Richtlinie für Notrufe" die richtlinie aus, die Sie verwenden möchten.
    - Wenn Ihre Organisation direct Routing für Telefonsystem bereitgestellt hat, wählen Sie unter **"Richtlinie** für das Routing von Notrufen" die richtlinie aus, die Sie verwenden möchten.

6. Um dem Standort ein Subnetz zuzuordnen, klicken Sie unter **"Subnetze"** auf **"Subnetze hinzufügen".** Geben Sie die IP-Version, die IP-Adresse und den Netzwerkbereich an, fügen Sie eine Beschreibung hinzu, und klicken Sie dann auf **"Übernehmen".** Jedes Subnetz muss einem bestimmten Standort zugeordnet sein.
7. Klicken Sie auf **Speichern**.

#### <a name="modify-a-network-site"></a>Ändern einer Netzwerkwebsite

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Topologie des Standortnetzwerks, und klicken Sie dann auf die Registerkarte  >   **"Netzwerkwebsites".**
2. Wählen Sie die Website aus, indem Sie links des Websitenamens und dann auf **"Bearbeiten" klicken.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **"Speichern".**

### <a name="manage-external-trusted-ip-addresses"></a>Verwalten externer vertrauenswürdiger IP-Adressen

Sie verwalten externe vertrauenswürdige IP-Adressen auf der Registerkarte **"Vertrauenswürdige IPs"** auf der Seite **"Netzwerktopologie"** im Microsoft Teams Admin Center. Sie können eine unbegrenzte Anzahl von externen vertrauenswürdigen IP-Adressen hinzufügen.

#### <a name="add-a-trusted-ip-address"></a>Hinzufügen einer vertrauenswürdigen IP-Adresse

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Topologie des Standortnetzwerks, und klicken Sie dann auf die Registerkarte "Vertrauenswürdige  >   **IPs".**
2. Klicken Sie auf **Neu**.
3. Geben Sie im Bereich "Vertrauenswürdige **IP-Adresse** hinzufügen" die IP-Version, die IP-Adresse und den Netzwerkbereich an, fügen Sie eine Beschreibung hinzu, und klicken Sie dann auf **"Übernehmen".**

    ![Screenshot des Bereichs "Vertrauenswürdige IP-Adresse hinzufügen"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Bearbeiten einer vertrauenswürdigen IP-Adresse

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Topologie des Standortnetzwerks, und klicken Sie dann auf die Registerkarte "Vertrauenswürdige  >   **IPs".**
2. Wählen Sie die IP-Adresse aus, indem Sie links davon klicken und dann auf **"Bearbeiten" klicken.**
3. Nehmen Sie **im Bereich "Vertrauenswürdige IP-Adresse bearbeiten"** die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf "Übernehmen". 

## <a name="configure-network-settings-using-powershell"></a>Konfigurieren von Netzwerkeinstellungen mithilfe von PowerShell

Um die Schritte in diesem Abschnitt ausführen zu können, benötigen Sie einige Vertrautheit mit PowerShell-Cmdlets. Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Definieren von Netzwerkregionen

 Verwenden Sie [das Cmdlet "New-CsTenantNetworkRegion",](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) um Netzwerkregionen zu definieren. Beachten Sie, dass der Parameter "RegionID" ein logischer Name ist, der die Geografie der Region darstellt und keine Abhängigkeiten oder Einschränkungen aufweist. Der Parameter "CentralSite-Website-ID" ist &lt; &gt; optional.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

In diesem Beispiel erstellen wir eine Netzwerkregion namens Indien.
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Siehe auch [Set-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)

### <a name="define-network-sites"></a>Definieren von Netzwerkwebsites

Verwenden Sie [das Cmdlet "New-CsTenantNetworkSite",](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) um Netzwerkwebsites zu definieren. Jede Netzwerkwebsite muss einer Netzwerkregion zugeordnet sein.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

In diesem Beispiel erstellen wir in der Region Indien zwei neue Netzwerkwebsites, "Silben" und "Hyderabad".

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

Die folgende Tabelle zeigt die in diesem Beispiel definierten Netzwerkwebsites.

||Website 1 |Website 2 |
|---------|---------|---------|
|Website-ID    |    Website 1 (Nachen)     |  Site 2 (Hyderabad)       |
|Regionsnummer  |     Region 1 (Indien)    |   Region 1 (Indien)      |

Siehe auch [Set-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)

### <a name="define-network-subnets"></a>Definieren von Netzwerksubnetzen

Verwenden Sie [das Cmdlet "New-CsTenantNetworkSubnet",](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) um Netzwerksubnetzen zu definieren und diese Netzwerkstandorten zuzuordnen. Jedes Netzwerksubnetz kann nur einem Standort zugeordnet werden.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz 192.168.0.0 und dem Netzwerkstandort "Subnetz" und zwischen Subnetz 2001:4898:e8:25:844e:926f:85ad:dd8e und dem Hyderabad-Netzwerkstandort.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

Die folgende Tabelle zeigt die in diesem Beispiel definierten Subnetze.

||Website 1 |Website 2 |
|---------|---------|---------|
|Subnetz-ID   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Mask  |     24    |   120      |
|Website-ID  | Website (Ort) | Site 2 (Hyderabad) |

Für mehrere Subnetze können Sie mithilfe eines Skripts wie dem folgenden eine CSV-Datei importieren.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

In diesem Beispiel sieht die Datei "CSV" in etwa so aus: 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

Siehe auch [Set-CsTenantNetworkSubnet.](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Definieren externer Subnetze (externe vertrauenswürdige IP-Adressen)

Verwenden Sie [das Cmdlet "New-CsTenantTrustedIPAddress",](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) um externe Subnetze zu definieren und sie dem Mandanten zuzuordnen. Sie können eine unbegrenzte Anzahl von externen Subnetzen für einen Mandanten definieren.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Beispiel:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Siehe auch [Set-CsTenantTrustedIPAddress.](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
