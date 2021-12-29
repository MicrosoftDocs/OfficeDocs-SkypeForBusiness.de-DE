---
title: Verwenden von PowerShell für Aufgaben im Menü "Netzwerkkonfiguration"
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Zusammenfassung: Skype for Business Server Systemsteuerung zur Cmdlet-Zuordnung für das Netzwerkkonfigurationsmenü.'
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626305"
---
# <a name="network-configuration"></a>Netzwerkkonfiguration

In diesem Artikel wird beschrieben, wie ähnliche Ergebnisse wie die des Menüelements **"Netzwerkkonfiguration"** in der älteren Systemsteuerung mithilfe von Cmdlets erzielt werden können.

In diesem Artikel werden die folgenden Untermenüs beschrieben:

- [Netzwerkkonfiguration](#network-configuration)
  - [Standortrichtlinie](#location-policy)
  - [Bandbreitenrichtlinie](#bandwidth-policy)
  - [Region](#region)
  - [Site](#site)
  - [Subnetz](#subnet)
  - [Regionslink](#region-link)
  - [Regionsroute](#region-route)

## <a name="location-policy"></a>Ortungsrichtlinie

Das Untermenü **"STANDORTRICHTLINIE"** wird verwendet, um Einstellungen anzuwenden, die sich auf die E9-1-1-Funktionalität beziehen. Die Standortrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist und wenn ja, welches Verhalten ein Notruf hat.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer in **der STANDORTRICHTLINIE** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Standortrichtlinien

   ![Standortrichtlinie auflisten](./media/location-policy-1.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Beispiel***

```powershell
 Get-CsLocationPolicy
```

---

> **Szenario 2:** Erstellen einer neuen Standortrichtlinie

   ![Standortrichtlinie erstellen](./media/location-policy-2.png)

***Cmdlet***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***Beispiel***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Standortrichtlinie

   ![Standortrichtlinie abrufen](./media/location-policy-3.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Beispiel***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **Szenario 4:** Löschen ausgewählter Standortrichtlinien

   ![Standortrichtlinie löschen](./media/location-policy-4.png)

***Cmdlet***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***Beispiel***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **Szenario 5:** Aktualisieren einer Standortrichtlinie

   ![Aktualisieren der Standortrichtlinie](./media/location-policy-5.png)

***Cmdlet***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***Beispiel***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>Bandbreitenrichtlinie

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. (In Skype for Business Server können nur Audio- und Videomodalitäten Bandbreiteneinschränkungen zugewiesen werden.) Dieses Cmdlet erstellt ein Containerprofil für diese Richtlinien. Sie definieren die einzelnen Richtlinien innerhalb des Containers, indem Sie beim Aufruf dieses Cmdlets die Beschränkungen für die Audio- und Videobandbreite angeben.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **bandbreitenrichtlinien** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Bandbreitenrichtlinien

   ![Bandbreitenrichtlinie auflisten](./media/bandwidth-policy-1.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Beispiel***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **Szenario 2:** Erstellen einer neuen Bandbreitenrichtlinie

   ![Neue Bandbreitenrichtlinie](./media/bandwidth-policy-2.png)

***Cmdlet***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***Beispiel***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Bandbreitenrichtlinie

   ![Bandbreitenrichtlinie abrufen](./media/bandwidth-policy-3.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Beispiel***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Szenario 4:** Ausgewählte Bandbreitenrichtlinien löschen

   ![Löschen der Bandbreitenrichtlinie](./media/bandwidth-policy-4.png)

***Cmdlet***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***Beispiel***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Szenario 5:** Aktualisieren einer Bandbreitenrichtlinie

   ![Aktualisieren der Bandbreitenrichtlinie](./media/bandwidth-policy-5.png)

***Cmdlet***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***Beispiel***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>Region

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Administratoren können das Menü **REGION** verwenden, um Informationen zu einer oder mehreren Netzwerkregionen zu verwalten, einschließlich des zugeordneten zentralen Standorts und einstellungen, die bestimmen, ob alternative Pfade für Audio- und Videoverbindungen zulässig sind, und die die Standorte innerhalb der Region einer Medienumgehungskonfiguration zuordnen.

---

> **Szenario 1:** Auflisten aller Regionen

   ![Region auflisten](./media/network-region-1.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Beispiel***

```powershell
 Get-CsNetworkRegion
```

---

> **Szenario 2:** Erstellen einer neuen Region

   ![Region erstellen](./media/network-region-2.png)

***Cmdlet***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***Beispiel***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Region

   ![Region abrufen](./media/network-region-3.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Beispiel***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **Szenario 4:** Ausgewählte Regionen löschen

   ![Region löschen](./media/network-region-4.png)

***Cmdlet***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***Beispiel***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **Szenario 5:** Aktualisieren einer Region

   ![Updatebereich](./media/network-region-5.png)

- **Anmerkung 1 – Ergebnis**

    Diese Anmerkung auf dem Bild gibt ein Ergebnis an, d. h. die Daten, die abgerufen und angezeigt werden.

    ***Cmdlet***

    [Get-CsNetworkSite from Region](/powershell/module/skype/get-csnetworksite)

    ***Beispiel***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **Anmerkung 2 – Option (für den Benutzer)**

    Diese Anmerkung auf dem Bild zeigt eine Option an, die der Benutzer implementieren kann, d. h. eine Netzwerkregion zu speichern.

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***Beispiel***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>Website

Netzwerkstandorte sind Niederlassungen oder Standorte, die in jeder Region einer Anrufsteuerungs- oder E9-1-1-Bereitstellung konfiguriert sind. Das Untermenü **"SITE"** hilft Administratoren, ihre Einstellungen hinzuzufügen, zu entfernen oder zu verwalten.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer auf **SITE** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Websites

   ![Website auflisten](./media/network-site-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Beispiel***

```powershell
 Get-CsNetworkSite
```

---

> **Szenario 2:** Erstellen einer neuen Website

   ![Website erstellen](./media/network-site-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***Beispiel***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **Szenario 3:** Abrufen von Details einer ausgewählten Website

   ![Website abrufen](./media/network-site-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Beispiel***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **Szenario 4:** Ausgewählte Websites löschen

   ![Website löschen](./media/network-site-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***Beispiel***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **Szenario 5:** Aktualisieren einer Website

   ![Aktualisieren der Website](./media/network-site-5.png)

- **Anmerkung 1 – Ergebnis**

    Diese Anmerkung auf dem Bild gibt ein Ergebnis an, d. h. die Daten, die abgerufen und angezeigt werden.

    ***Cmdlet***

    [Get-CsNetworkSubnet from Site](/powershell/module/skype/get-csnetworksubnet)

    ***Beispiel***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **Anmerkung 2 – Option (für den Benutzer)**

    Diese Anmerkung auf dem Bild zeigt eine Option an, die der Benutzer implementieren kann, d. h. einen Netzwerkstandort zu speichern.

   ***Cmdlet***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***Beispiel***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>Subnetz

Administratoren können **das Subnetz-Untermenü** verwenden, um Netzwerksubnetze zu erstellen, zu aktualisieren und zu verwalten.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer im **SUBNETZ** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Subnetze

   ![Subnetz auflisten](./media/network-subnet-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Beispiel***

```powershell
 Get-CsNetworkSubnet
```

---

> **Szenario 2:** Erstellen eines neuen Subnetzes

   ![Subnetz erstellen](./media/network-subnet-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***Beispiel***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **Szenario 3:** Abrufen von Details zu einem ausgewählten Subnetz

   ![Subnetz abrufen](./media/network-subnet-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Beispiel***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Szenario 4:** Ausgewählte Subnetze löschen

   ![Subnetz löschen](./media/network-subnet-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***Beispiel***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Szenario 5:** Aktualisieren eines Subnetzes

   ![Subnetz aktualisieren](./media/network-subnet-5.png)

***Cmdlet***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***Beispiel***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>Regionslink

Regionen innerhalb eines Netzwerks werden über physische WAN-Verbindungen miteinander verbunden. Administratoren können das Untermenü **REGION LINK** verwenden, um Netzwerksubnetze zu erstellen, zu aktualisieren und zu verwalten.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer auf **REGION LINK** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Regionslinks

   ![Link "Region auflisten"](./media/network-regionlink-1.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Beispiel***

```powershell
 Get-CsNetworkRegionLink
```

---

> **Szenario 2:** Erstellen eines neuen Regionslinks

   ![Regionslink erstellen](./media/network-regionlink-2.png)

***Cmdlet***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***Beispiel***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **Szenario 3:** Abrufen von Details zu einem ausgewählten Regionslink

   ![Link "Region abrufen"](./media/network-regionlink-3.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Beispiel***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Szenario 4:** Löschen ausgewählter Regionslinks

   ![Regionslink löschen](./media/network-regionlink-4.png)

***Cmdlet***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***Beispiel***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Szenario 5:** Aktualisieren eines Regionslinks

   ![Link "Region aktualisieren"](./media/network-regionlink-5.png)

***Cmdlet***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***Beispiel***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>Regionsroute

Jede Region in einer Anrufsteuerungskonfiguration muss auf jede andere Region zugreifen können. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Administratoren können das Untermenü **REGION ROUTE** verwenden, um diese zu erstellen, zu aktualisieren und zu verwalten.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer auf **REGION ROUTE** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Regionenrouten

   ![Regionenroute auflisten](./media/network-regionroute-1.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Beispiel***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **Szenario 2:** Erstellen einer neuen Regionsroute

   ![Regionenroute erstellen](./media/network-regionroute-2.png)

***Cmdlet***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***Beispiel***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Regionsroute

   ![Regionsroute abrufen](./media/network-regionroute-3.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Beispiel***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **Szenario 4:** Ausgewählte Regionenrouten löschen

   ![Regionenroute löschen](./media/network-regionroute-4.png)

***Cmdlet***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***Beispiel***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **Szenario 5:** Aktualisieren einer Regionsroute

   ![Aktualisieren der Regionsroute](./media/network-regionroute-5.png)

- **Anmerkung 1 – Option (für den Benutzer)**

    Diese Anmerkung auf dem Bild gibt ein Ergebnis an, d. h. die Daten, die abgerufen und angezeigt werden.

   ***Cmdlet***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***Beispiel***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **Anmerkung 2 – Option (für den Benutzer)**

    Diese Anmerkung auf dem Bild zeigt eine Option an, die der Benutzer implementieren kann, d. h. eine Netzwerkregionenroute zu speichern.

    ***Cmdlet***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***Beispiel***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
