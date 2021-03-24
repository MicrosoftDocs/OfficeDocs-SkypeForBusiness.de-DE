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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Erfahren Sie mehr über die Bereitstellung mehrerer PSTN-Standorte in Cloud Connector Edition.
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098401"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Bereitstellen mehrerer Standorte in Cloud Connector

> [!Important] 
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

Erfahren Sie mehr über die Bereitstellung mehrerer PSTN-Standorte in Cloud Connector Edition.
  
In diesem Abschnitt wird beschrieben, wie Mehrere Public Switched Telephone Network (PSTN)-Standorte bereitgestellt werden. Websites werden einzeln mithilfe der gleichen Schritte wie die Bereitstellung eines einzelnen Standorts bereitgestellt. In diesem Thema werden die Überlegungen und Unterschiede zwischen Websites in einer Bereitstellung mit mehreren Standorten beschrieben. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Mehrere Public Switched Telephone Network (PSTN)-Standorte

Im Folgenden finden Sie eine Beispielkonfiguration zum Bereitstellen von Skype for Business Cloud Connector Edition für verschiedene PSTN-Standorte. Stellen Sie sicher, dass die Konfigurationseinstellungen korrekt sind, bevor Sie eine Bereitstellung starten.
  
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

Führen Sie für jeden PSTN-Standort, den Sie hinzufügen möchten, die Schritte unter Bereitstellen eines einzelnen Standorts [in Cloud Connector aus.](deploy-a-single-site-in-cloud-connector.md)
  
> [!IMPORTANT]
> Der freigegebene Ordner für die Vorbereitung von Hochverfügbarkeit (High Availability, HA) ist pro PSTN-Standort. Der freigegebene **Ordner muss zwischen** PSTN-Standorten unterschiedlich sein. Verwenden Sie nicht denselben freigegebenen Ordner für mehrere Websites.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Einzelner Standort mit hoher Verfügbarkeit (High Availability, HA) im Vergleich zu Bereitstellungen mit mehreren Standorten
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

In der folgenden Tabelle sind die Unterschiede zwischen einem einzelnen Standort mit Ha-Unterstützung und einer Bereitstellung mit mehreren Standorten aufgeführt.
  
|**Kategorie**|**Element**|**Einzelner Standort mit HA**|**Multi-Site**|
|:-----|:-----|:-----|:-----|
|Konfigurieren  <br/> |Hostname der Appliance <br/> |**Unterschiedliche** Appliances <br/> |**Unterschiedlich** zwischen PSTN-Standorten <br/> |
|Setup  <br/> |Freigegebener Ordner  <br/> |Erfordert **denselben freigegebenen** Ordner für alle Appliances <br/> |Erfordert einen **anderen freigegebenen** Ordner für appliances <br/> |
|Konfigurieren  <br/> |VirtualMachineDomain  <br/> |Erfordert die **gleiche** Domäne für alle Appliances <br/> |Erfordert dieselbe **Domäne** für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |SIPDomains  <br/> |Domänennamen und -reihenfolge sollten für **alle** Appliances identisch sein <br/> |Domänennamen und -reihenfolge sollten auf **allen** PSTN-Standorten identisch sein <br/> |
|Konfigurieren  <br/> |Websitename  <br/> |**Same** Standortname für alle Appliances <br/> |**Different** Websitename über PSTN-Standorte hinweg <br/> |
|Konfigurieren  <br/> |Servernamen  <br/> |**Unterschiedliche** Appliances <br/> |**Unterschiedlich** zwischen PSTN-Standorten <br/> |
|Konfigurieren  <br/> |FQDNs des internen Pools  <br/> |**Geräteübergreifend** gleich <br/> |**Auf** allen PSTN-Standorten identisch <br/> |
|Konfigurieren  <br/> |Interne IPs  <br/> |**Unterschiedliche** Appliances <br/> |**Unterschiedlich** zwischen PSTN-Standorten <br/> |
|Konfigurieren  <br/> |Externer FQDN  <br/> |**Geräteübergreifend** gleich <br/> |**Unterschiedlich** zwischen PSTN-Standorten <br/> |
|Konfigurieren  <br/> |Externe IPs  <br/> |**Unterschiedliche** Appliances <br/> |**Unterschiedlich** zwischen PSTN-Standorten <br/> |
|Konfigurieren  <br/> |PSTN-GW-Einstellungen  <br/> |**Geräteübergreifend** gleich <br/> |**Unterschiedlich** zwischen PSTN-Standorten <br/> |
|Konfigurieren  <br/> |DNS-Eintrag  <br/> |Hinzufügen von Datensätzen **mit denselben** FQDNs für den externen Zugriff und **unterschiedlichen IP-Adressen** <br/> |Hinzufügen von **Datensätzen mit unterschiedlichen** FQDNs für den externen Zugriff und **unterschiedlichen** IP-Adressen <br/> |
|Setup  <br/> |Hybrid-Mandant  <br/> |Festlegen von HybridPSTNSite  <br/> Festlegen von PeerDestination für Fallback  <br/> |Festlegen von HybridPSTNSite  <br/> Festlegen von PeerDestination für Fallback  <br/> |
|Setup  <br/> |Gateway  <br/> |MS GW **M:N-Zuordnung** an dieser Website <br/> |PSTN-Gateways an jedem PSTN-Standort sollten nur eine Verbindung mit den Vermittlungsservern am gleichen Standort herstellen  <br/> |
|Setup  <br/> |Benutzer  <br/> |Festlegen von UserPSTNSettings  <br/> |Festlegen von UserPSTNSettings  <br/> |
