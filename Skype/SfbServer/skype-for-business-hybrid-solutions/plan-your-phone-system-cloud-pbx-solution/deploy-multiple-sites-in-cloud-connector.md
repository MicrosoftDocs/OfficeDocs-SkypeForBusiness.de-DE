---
title: Bereitstellen mehrerer Standorte in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Erfahren Sie mehr über die Bereitstellung mehrerer PSTN-Standorte in Cloud Connector Edition.
ms.openlocfilehash: 7f771875605ffef130b430fd7c7a00d9d1a63873
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613765"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Bereitstellen mehrerer Standorte in Cloud Connector

> [!Important] 
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

Erfahren Sie mehr über die Bereitstellung mehrerer PSTN-Standorte in Cloud Connector Edition.
  
In diesem Abschnitt wird beschrieben, wie Sie mehrere PSTN-Standorte (Public Switched Telephone Network) bereitstellen. Websites werden nacheinander mit den gleichen Schritten wie die Bereitstellung eines einzelnen Standorts bereitgestellt. In diesem Thema werden die Überlegungen und Unterschiede zwischen Standorten in einer Bereitstellung mit mehreren Standorten beschrieben. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Mehrere PSTN-Standorte (Public Switched Telephone Network)

Im Folgenden finden Sie ein Beispiel für die Konfiguration zum Bereitstellen von Skype for Business Cloud Connector Edition für verschiedene PSTN-Standorte. Stellen Sie sicher, dass Ihre Konfigurationseinstellungen korrekt sind, bevor Sie eine Bereitstellung starten.
  
PSTN-Standort 1
  
```console
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
  
```console
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

Führen Sie für jeden PSTN-Standort, den Sie hinzufügen möchten, die Schritte unter [Bereitstellen eines einzelnen Standorts in Cloud Connector](deploy-a-single-site-in-cloud-connector.md)aus.
  
> [!IMPORTANT]
> Der freigegebene Ordner für die Vorbereitung der Hohen Verfügbarkeit (HA) ist pro PSTN-Standort. Der freigegebene Ordner **muss** sich zwischen PSTN-Standorten unterscheiden. Verwenden Sie nicht denselben freigegebenen Ordner für mehrere sites.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Einzelner Standort mit hoher Verfügbarkeit (Ha) im Vergleich zu Bereitstellungen mit mehreren Standorten
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

In der folgenden Tabelle sind die Unterschiede zwischen einem einzelnen Standort mit HA-Unterstützung und einer Bereitstellung mit mehreren Standorten aufgeführt.
  
|**Kategorie**|**Element**|**Einzelner Standort mit HA**|**Mehrere Standorte**|
|:-----|:-----|:-----|:-----|
|Konfigurieren  <br/> |Appliance-Hostname <br/> |**Unterschiedliche** Appliances <br/> |**Unterschiedliche** PSTN-Standorte <br/> |
|Setup  <br/> |Freigegebener Ordner  <br/> |Erfordert den **gleichen** freigegebenen Ordner für alle Appliances <br/> |Erfordert einen **anderen** freigegebenen Ordner in appliances <br/> |
|Konfigurieren  <br/> |VirtualMachineDomain  <br/> |Erfordert die **gleiche** Domäne in allen Appliances <br/> |Erfordert **dieselbe** Domäne über PSTN-Standorte hinweg <br/> |
|Konfigurieren  <br/> |SIPDomains  <br/> |Domänennamen und Reihenfolge sollten in allen Appliances **identisch** sein <br/> |Domänennamen und Reihenfolge sollten an allen PSTN-Standorten **identisch** sein. <br/> |
|Konfigurieren  <br/> |Websitename  <br/> |**Identisch** Standortname in allen Appliances <br/> |**Anders** Standortname an allen PSTN-Standorten <br/> |
|Konfigurieren  <br/> |Servernamen  <br/> |**Unterschiedliche** Appliances <br/> |**Unterschiedliche** PSTN-Standorte <br/> |
|Konfigurieren  <br/> |FQDNs für internen Pool  <br/> |**In** allen Appliances gleich <br/> |**Identisch** für PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Interne IPs  <br/> |**Unterschiedliche** Appliances <br/> |**Unterschiedliche** PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Externer FQDN  <br/> |**In** allen Appliances gleich <br/> |**Unterschiedliche** PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Externe IPs  <br/> |**Unterschiedliche** Appliances <br/> |**Unterschiedliche** PSTN-Standorte <br/> |
|Konfigurieren  <br/> |PSTN GW-Einstellungen  <br/> |**In** allen Appliances gleich <br/> |**Unterschiedliche** PSTN-Standorte <br/> |
|Konfigurieren  <br/> |DNS-Eintrag  <br/> |Hinzufügen von Datensätzen mit **denselben** FQDNs für den externen Zugriff und **verschiedenen** IP-Adressen <br/> |Hinzufügen von Datensätzen mit **unterschiedlichen** FQDNs für den externen Zugriff und **verschiedenen** IP-Adressen <br/> |
|Setup  <br/> |Hybridmandant  <br/> |Festlegen von HybridPSTNSite  <br/> PeerDestination für Fallback festlegen  <br/> |Festlegen von HybridPSTNSite  <br/> PeerDestination für Fallback festlegen  <br/> |
|Setup  <br/> |Gateway  <br/> |MS GW **M:N-Zuordnung** an dieser Website <br/> |PSTN-Gateways an jedem PSTN-Standort sollten nur eine Verbindung mit den Vermittlungsservern am selben Standort herstellen.  <br/> |
|Setup  <br/> |User  <br/> |Festlegen von UserPSTNSettings  <br/> |Festlegen von UserPSTNSettings  <br/> |
