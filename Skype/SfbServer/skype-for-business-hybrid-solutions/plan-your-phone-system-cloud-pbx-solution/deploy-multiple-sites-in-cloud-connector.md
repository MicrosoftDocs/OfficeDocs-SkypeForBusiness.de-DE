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
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358921"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Bereitstellen mehrerer Standorte in Cloud Connector

> [!Important] 
> Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen. Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

Erfahren Sie mehr über die Bereitstellung mehrerer PSTN-Standorte in Cloud Connector Edition.
  
In diesem Abschnitt wird beschrieben, wie mehrere PSTN-Standorte (Public Switched Telephone Network) bereitgestellt werden. Websites werden jeweils einzeln bereitgestellt, wobei dieselben Schritte wie bei der Bereitstellungeines einzelnen Standorts ausgeführt werden. In diesem Thema werden die Überlegungen und Unterschiede zwischen Websites in einer Bereitstellung mit mehreren Websites beschrieben. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Mehrere PSTN-Standorte (Public Switched Telephone Network)

Im folgenden finden Sie eine Beispielkonfiguration für die Bereitstellung Skype for Business Cloud Connector Edition für verschiedene PSTN-Standorte. Stellen Sie sicher, dass Ihre Konfigurationseinstellungen korrekt sind, bevor Sie eine Bereitstellung starten.
  
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

Führen Sie für jeden hinzuzufügenden PSTN-Standort die Schritte unter [Deploy an Single Site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md)aus.
  
> [!IMPORTANT]
> Der freigegebene Ordner zur Vorbereitung der Hochverfügbarkeit (ha) ist pro PSTN-Standort. Der freigegebene Ordner **muss** zwischen PSTN-Standorten unterschiedlich sein. Verwenden Sie nicht denselben freigegebenen Ordner für mehrere Websites. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Einzelner Standort mit hoher Verfügbarkeit (ha) im Vergleich zu Bereitstellungen mit mehreren Standorten
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

In der folgenden Tabelle sind die Unterschiede zwischen einem einzelnen Standort mit ha-Unterstützung und einer Bereitstellung mit mehreren Standorten aufgeführt.
  
|**Kategorie**|**Element**|**Single-Site mit ha**|**Multi-Site**|
|:-----|:-----|:-----|:-----|
|Konfigurieren  <br/> |Name der Appliance-Host <br/> |**Unterschiedliche** Across Appliances <br/> |**Unterschiedliches** für PSTN-Standorte <br/> |
|Setup  <br/> |Freigegebener Ordner  <br/> |Erfordert **denselben** freigegebenen Ordner für alle Appliances <br/> |Für Appliances ist ein **anderer** freigegebener Ordner erforderlich <br/> |
|Konfigurieren  <br/> |VirtualMachineDomain  <br/> |Erfordert die **gleiche** Domäne für alle Appliances <br/> |Erfordert die **gleiche** Domäne für alle PSTN-Standorte <br/> |
|Konfigurieren  <br/> |SIPDomains  <br/> |Domänennamen und Reihenfolge sollten in allen Appliances **gleich** sein. <br/> |Domänennamen und Reihenfolge sollten für alle PSTN-Standorte **gleich** sein. <br/> |
|Konfigurieren  <br/> |Websitename  <br/> |**Gleiche** Website Name für Appliances <br/> |**Unterschiedliche** Website Name über PSTN-Standorte hinweg <br/> |
|Konfigurieren  <br/> |Server Namen  <br/> |**Unterschiedliche** Across Appliances <br/> |**Unterschiedliches** für PSTN-Standorte <br/> |
|Konfigurieren  <br/> |FQDNs interner Pools  <br/> |**Gleich** in allen Appliances <br/> |**Gleich** auf allen PSTN-Standorten <br/> |
|Konfigurieren  <br/> |Interne IPS  <br/> |**Unterschiedliche** Across Appliances <br/> |**Unterschiedliches** für PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Externer FQDN  <br/> |**Gleich** in allen Appliances <br/> |**Unterschiedliches** für PSTN-Standorte <br/> |
|Konfigurieren  <br/> |Externe IPS  <br/> |**Unterschiedliche** Across Appliances <br/> |**Unterschiedliches** für PSTN-Standorte <br/> |
|Konfigurieren  <br/> |PSTN-GW-Einstellungen  <br/> |**Gleich** in allen Appliances <br/> |**Unterschiedliches** für PSTN-Standorte <br/> |
|Konfigurieren  <br/> |DNS-Eintrag  <br/> |Hinzufügen von Datensätzen mit **denselben** FQDNs für externen Zugriff und **unterschiedlichen** IP-Adressen <br/> |Hinzufügen von Datensätzen mit **verschiedenen** FQDNs für externen Zugriff und **unterschiedlichen** IP-Adressen <br/> |
|Setup  <br/> |Hybrid Mandant  <br/> |HybridPSTNSite festlegen  <br/> Festlegen von Peer Destination für Fallback  <br/> |HybridPSTNSite festlegen  <br/> Festlegen von Peer Destination für Fallback  <br/> |
|Setup  <br/> |Gateway  <br/> |MS GW **m:n-trunk** -Zuordnung auf dieser Website <br/> |PSTN-Gateways an jedem PSTN-Standort sollten nur eine Verbindung mit dem Vermittlungsserver am gleichen Standort herstellen.  <br/> |
|Setup  <br/> |Benutzer  <br/> |UserPSTNSettings festlegen  <br/> |UserPSTNSettings festlegen  <br/> |
   

