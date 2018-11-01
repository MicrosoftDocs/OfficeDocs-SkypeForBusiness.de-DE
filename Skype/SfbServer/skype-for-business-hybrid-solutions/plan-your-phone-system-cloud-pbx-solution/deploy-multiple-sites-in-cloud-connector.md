---
title: Bereitstellen mehrerer Standorte in Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Informationen Sie zu mehreren PSTN-Websites in der Cloud Connector Edition bereitstellen.
ms.openlocfilehash: 388915d0ab22dc50378d84a82c01291cfd7c99eb
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851490"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Bereitstellen mehrerer Standorte in Cloud Connector
 
Informationen Sie zu mehreren PSTN-Websites in der Cloud Connector Edition bereitstellen.
  
In diesem Abschnitt wird die Bereitstellung mehrerer PSTN-Standorte (Public Switched Telephone Network, Telefonfestnetz) erläutert. Standorte werden jeweils nacheinander wie bei der Bereitstellung eines einzelnen Standorts bereitgestellt. In diesem Thema werden Überlegungen zu Standorten und Unterschiede zwischen Standorten in einer Bereitstellung mit mehreren Standorten beschrieben.  
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Mehrere PSTN-Standorte

Die folgende Abbildung zeigt eine Beispielkonfiguration Skype für Business Cloud Connector Edition für andere PSTN-Websites bereitstellen. Stellen Sie vor dem Starten der Bereitstellung sicher, dass Ihre Konfigurationseinstellungen richtig sind.
  
PSTN-Standort 1
  
```
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

PSTN-Standort 2
  
```
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

Führen Sie für jede PSTN-Website, die Sie hinzufügen möchten die Schritte unter [Deploy einer einzelnen Website in der Cloud-Connector](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> Der freigegebene Ordner für die Vorbereitung hoher Verfügbarkeit wird pro PSTN-Standort erstellt. Der freigegebene Ordner **muss** sich zwischen den PSTN-Standorten unterscheiden. Verwenden Sie nicht den gleichen freigegebenen Ordner für mehrere Websites. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Bereitstellung eines einzelnen Standorts mit hoher Verfügbarkeit im Vergleich zur Bereitstellung mehrerer Standorte
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

In der folgenden Tabelle sind die Unterschiede zwischen der Bereitstellung an einem einzelnen Standort mit hoher Verfügbarkeit und der Bereitstellung an mehreren Standorten aufgelistet.
  
|**Kategorie**|**Element**|**Einzelner Standort mit hoher Verfügbarkeit**|**Mehrere Standorte**|
|:-----|:-----|:-----|:-----|
|Konfigurieren  <br/> |Hostname des Geräts <br/> |**Unterschiedlich** für alle Appliances <br/> |**Unterschiedlich** für alle PSTN-Standorte <br/> |
|Installationsanforderungen  <br/> |Freigegebener Ordner  <br/> |Erfordert den **gleiche** freigegebenen Ordner mehreren appliances <br/> |Benötigt für jede Appliance einen **unterschiedlichen** freigegebenen Ordner. <br/> |
|Konfigurieren  <br/> |VirtualMachineDomain  <br/> |Benötigt für alle Appliances **dieselbe** Domäne. <br/> |Benötigt **dieselbe** Domäne für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |SIP-Domänen  <br/> |Domänennamen und der Reihenfolge sollte sein die **gleichen** mehreren appliances <br/> |Domänennamen und der Reihenfolge sollte sein die **gleichen** PSTN-websiteübergreifenden <br/> |
|Konfigurieren  <br/> |Standortname  <br/> |**Identischer** Standortname für alle Appliances <br/> |**Unterschiedlicher** Standortname für jeden einzelnen PSTN-Standort <br/> |
|Konfigurieren  <br/> |Servernamen  <br/> |**Unterschiedlich** für alle Appliances <br/> |**Unterschiedlich** für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |FQDNs interner Pools  <br/> |**Identisch** für alle Appliances <br/> |**Identisch** für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Interne IP-Adressen  <br/> |**Unterschiedlich** für alle Appliances <br/> |**Unterschiedlich** für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Externer FQDN  <br/> |**Identisch** für alle Appliances <br/> |**Unterschiedlich** für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Externe IP-Adressen  <br/> |**Unterschiedlich** für alle Appliances <br/> |**Unterschiedlich** für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Einstellungen für PSTN-Gateway  <br/> |**Identisch** für alle Appliances <br/> |**Unterschiedlich** für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |DNS-Eintrag  <br/> |Hinzufügen von Datensätzen mit der **gleichen** externen Zugriff FQDNs und **verschiedene** IP-Adressen <br/> |Datensätze mit **unterschiedlichen** FQDNs für externen Zugriff und **unterschiedlichen** IP-Adressen hinzufügen <br/> |
|Installationsanforderungen  <br/> |Hybrid-Mandanten  <br/> |„HybridPSTNSite“ festlegen  <br/> Peer-Ziel für Fallback einrichten  <br/> |„HybridPSTNSite“ festlegen  <br/> Peer-Ziel für Fallback einrichten  <br/> |
|Installationsanforderungen  <br/> |Gateway  <br/> |Vermittlungsserver-Gateway **M:N**-Zuordnung an diesem Standort <br/> |PSTN-Gateways an den einzelnen PSTN-Standorten sollten nur Verbindungen mit Vermittlungsservern am gleichen Standort herstellen.  <br/> |
|Installationsanforderungen  <br/> |Benutzer  <br/> |„UserPSTNSettings“ festlegen  <br/> |„UserPSTNSettings“ festlegen  <br/> |
   

