---
title: Direkte Weiterleitung der lokalen Medienoptimierung
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Konfigurieren der lokalen Medienoptimierung für das direkte Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3097f97a856dc4e947281847c65669c23c73a408
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43158013"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Konfigurieren der lokalen Medienoptimierung für das direkte Routing

Die Konfiguration für die lokale Medienoptimierung basiert auf Netzwerkeinstellungen, die anderen Cloud-Sprachfeatures, wie standortbasiertes Routing und dynamische Notrufe, gemeinsam sind. Weitere Informationen zu netzwerkregionen, Netzwerk Websites, Netzwerk-Subnetzen und vertrauenswürdigen IP-Adressen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md).

Bevor Sie die lokale Medienoptimierung konfigurieren, lesen Sie [lokale Medienoptimierung für direktes Routing](direct-routing-media-optimization.md).  

Zum Konfigurieren der lokalen Medienoptimierung sind die folgenden Schritte erforderlich. Sie können das Team Admin Center oder PowerShell verwenden. Ausführliche Informationen finden Sie unter [Verwalten der Netzwerktopologie](manage-your-network-topology.md).

1. Konfigurieren Sie den Benutzer und die SBC-Websites (wie in diesem Artikel beschrieben).
2. Konfigurieren Sie die SBCS für die lokale Medienoptimierung (gemäß ihrer SBC-Herstellerspezifikation).

Das folgende Diagramm zeigt die Netzwerkeinrichtung, die in den Beispielen in diesem Artikel verwendet wurde.

![Diagramm mit Netzwerk Setup für Beispiele](media/direct-routing-media-op-9.png "Netzwerk-Setup für Beispiele")


## <a name="configure-the-user-and-the-sbc-sites"></a>Konfigurieren des Benutzers und der SBC-Websites

Wenn Sie den Benutzer und die SBC-Websites konfigurieren möchten, müssen Sie Folgendes ausführen:

1. [Verwalten externer vertrauenswürdiger IP-Adressen](#manage-external-trusted-ip-addresses).  

2. [Definieren Sie die Netzwerktopologie](#define-the-network-topology) , indem Sie die netzwerkregionen, Netzwerkstandorte und Netzwerk-Subnetze konfigurieren.

3. [Definieren Sie die virtuelle Netzwerktopologie](#define-the-virtual-network-topology) , indem Sie SBC (s) den Websites mit relevanten Modi und Proxy-SBC-Werten zuweisen.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Konfigurieren von SBC (s) für die lokale Medienoptimierung gemäß der SBC-Herstellerspezifikation

In diesem Artikel wird die Konfiguration für Microsoft-Komponenten beschrieben. Informationen zur SBC-Konfiguration finden Sie in Ihrem SBC-Anbieterdokumentation.

Die lokale Medienoptimierung wird von den folgenden SBC-Anbietern unterstützt:

| Anbieter | Produkt |    Software Version |
|:------------|:-------|:-------| :-------|
| [AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7,2 a. 256 | 
|            |  Mediant 800 SBC |   7,2 a. 256 | 
|            |  Mediant 2600 SBC |  7,2 a. 256 | 
|            |  Mediant 4000 SBC |  7,2 a. 256 | 
|            |  Mediant-1000B-SBC | 7,2 a. 256 | 
|            |  Mediant 9000 SBC |  7,2 a. 256 | 
|            |  Mediant Virtual Edition SBC |   7,2 a. 256 | 
|            |  Mediant Cloud Edition SBC | 7,2 a. 256 |
| [Menüband-SBC-Kern](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8,2  |
|            |  SBC 5210         | 8,2  |
|            |  SBC 5400         | 8,2  |
|            |  SBC 7000         | 8,2  |
|            |  SBC SWe          | 8,2  |
| [Menüband SBC-Kante](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  SBC 1000         | 8.1.1, Build 527 |
|            |  SBC 2000         | 8.1.1, Build 527 |
|            |  Lite SBC Schwedisch     | 8.1.0, Build 222 |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1 + |


## <a name="manage-external-trusted-ip-addresses"></a>Verwalten externer vertrauenswürdiger IP-Adressen

Externe vertrauenswürdige IPS sind die Internet externen IPS des Unternehmensnetzwerks. Diese IP-Adressen sind die IP-Adressen, die von Microsoft Teams-Clients verwendet werden, wenn Sie eine Verbindung mit Microsoft 365 herstellen. Sie müssen diese externen IPS für jede Website hinzufügen, auf der Benutzer die lokale Medienoptimierung verwenden.

Wenn Sie die öffentlichen IP-Adressen für jede Website hinzufügen möchten, verwenden Sie das Cmdlet New-CsTenantTrustedIPAddress. Sie können eine unbegrenzte Anzahl von vertrauenswürdigen IP-Adressen für einen Mandanten definieren. Wenn die von Microsoft 365 gesehenen externen IPS sowohl IPv4-als auch IPv6-Adressen sind, müssen Sie beide Typen von IP-Adressen hinzufügen. Verwenden Sie für IPv4 Maske 32. Verwenden Sie für IPv6 die Maske 128. Sie können sowohl einzelne externe IP-Adressen als auch externe IP-Subnetze hinzufügen, indem Sie unterschiedliche MaskBits für das Cmdlet angeben.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


Beispiel für das Hinzufügen von vertrauenswürdigen IP-Adressen.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>Definieren der Netzwerktopologie

In diesem Abschnitt wird beschrieben, wie Sie die netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze für Ihre Netzwerktopologie definieren.

Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, daher müssen Sie sicherstellen, dass Sie denselben Fall verwenden, der während des Setups verwendet wurde.  (Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)

### <a name="define-network-regions"></a>Definieren von netzwerkregionen

Verwenden Sie zum Definieren von netzwerkregionen das Cmdlet New-CsTenantNetworkRegion. Der Parameter Regions-Nr ist ein logischer Name, der die Geographie des Bereichs darstellt und keine Abhängigkeiten oder Einschränkungen aufweist. Der CentralSite <site ID> -Parameter ist optional.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Im folgenden Beispiel wird eine netzwerkregion mit dem Namen APAC erstellt:

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Definieren von Netzwerk Websites

Verwenden Sie zum Definieren von Netzwerk Websites das Cmdlet New-CsTenantNetworkSite. Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

Im folgenden Beispiel werden drei neue Netzwerk Websites, Vietnam, Indonesien und Singapur, in der Region APAC erstellt:

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definieren von Netzwerk-Subnetzen

Verwenden Sie das Cmdlet New-CsTenantNetworkSubnet, um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen. Jedes Netzwerk Subnetz kann nur einer Website zugeordnet werden. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

Im folgenden Beispiel werden drei Netzwerk-Subnetze definiert und den drei Netzwerkstandorten zugeordnet: Vietnam, Indonesien und Singapur:

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Definieren der virtuellen Netzwerktopologie 

Zunächst erstellt der mandantenadministrator mithilfe des Cmdlets New-CsOnlinePSTNGateway eine neue SBC-Konfiguration für jeden relevanten SBC.
Der mandantenadministrator definiert die virtuelle Netzwerktopologie, indem er die Netzwerk Websites für die PSTN-Gateway-Objekte mit dem Cmdlet "CsOnlinePSTNGateway" angibt:

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Beachten Sie Folgendes: 
   - Wenn der Kunde über einen einzelnen SBC verfügt, muss der-ProxySBC-Parameter entweder obligatorisch $NULL oder SBC-FQDN-Wert sein (zentrales SBC-Szenario mit zentralisierten Trunks).
   - Der-MediaBypass-Parameter muss auf $true eingestellt sein, um die lokale Medienoptimierung zu unterstützen.
   - Wenn der SBC-BypassMode-Parametersatz nicht vorhanden ist, werden keine X-MS-Header gesendet. 
   - Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, sodass Sie sicherstellen müssen, dass Sie den gleichen Fall verwenden, der während des Setups verwendet wurde.  (Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)

Im folgenden Beispiel werden drei SBCS zu den Netzwerkstandorten Vietnam, Indonesien und Singapur im Bereich APAC mit dem Modus immer umgehen hinzugefügt:

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Hinweis: um unterbrechungsfreie Vorgänge zu gewährleisten, wenn die lokale Medienoptimierung und standortbasiertes Routing (LBR) gleichzeitig konfiguriert sind, muss Downstream-SBCS für LBR aktiviert werden, indem der GatewaySiteLbrEnabled-Parameter für jeden Downstream-SBC auf $true festgelegt wird. (Diese Einstellung ist für den Proxy-SBC nicht zwingend erforderlich.)

Basierend auf den oben aufgeführten Informationen umfasst das direkte Routing drei proprietäre SIP-Header für SIP-Einladungen und erneute Einladungen, wie in der folgenden Tabelle dargestellt.

X-MS-Header, die beim direkten Routing bei Einladungen und erneuten Einladungen eingeführt werden, wenn BypassMode definiert ist:

| Header Name | Werte | Kommentare | 
|:------------|:-------|:-------|
| X-MS-UserLocation | intern/extern | Gibt an, ob der Benutzer intern oder extern ist |
| Request-URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0 | SBC-FQDN | Der FQDN, der für den Anruf vorgesehen ist, auch wenn der SBC nicht direkt mit dem direkten Routing verbunden ist |
| X-MS-MediaPath | Beispiel: proxysbc.contoso.com, VNsbc.contoso.com | Die Reihenfolge der SBCS, die für den Medienpfad zwischen dem Benutzer und dem Ziel-SBC verwendet werden soll. Der endgültige SBC ist immer der letzte. |
| X-MS-UserSite | usersiteID | Vom mandantenadministrator festgelegte Zeichenfolge |

## <a name="call-flows"></a>Anruf Flüsse 

Im folgenden werden die Anruf Flüsse für zwei Modi angezeigt:

- [Immer umgehen](#always-bypass-mode)
- [Nur für lokale Benutzer](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Modus immer umgehen

Der Bypass-Modus ist immer die einfachste Option für die Konfiguration. Der mandantenadministrator kann eine einzelne Website für alle Benutzer und SBCS konfigurieren, wenn alle SBCS von einer beliebigen Website aus erreichbar sind.

In den Beispielen wird der Modus "immer umgehen" für die folgenden Szenarien angezeigt:

- [Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Ausgehende Anrufe und der Benutzer ist extern](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Eingehende Anrufe und der Benutzer ist extern](#inbound-calls-and-the-user-is-external-with-always-bypass)

In der folgenden Tabelle sind die in den Beispielen verwendeten FQDN-und IP-Adressen aufgeführt:

| FQDN | Externe SBC-IP-Adresse | Interne SBC-IP-Adresse | Internes Subnetz | Ort | Externe NAT (vertrauenswürdige IP-Adresse) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Keine | 192.168.1.5 | 192.168.1.0/24 | Vietnam | 172.16.240.110 |
| IDsbc.contoso.com | Keine | 192.168.2.5 | 192.168.2.0/24 | Indonesien | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Singapur | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit Always Bypass

| Modus |    Benutzer |  Ort |  Anrufrichtung |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Intern |  Dieselbe Website wie SBC |  Ausgehend |

Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:

| Physischer Standort des Benutzers| Der Benutzer macht oder empfängt einen Anruf an/von der Nummer | Telefonnummer des Benutzers  | Online-VoIP-Routing Richtlinie | Für SBC konfigurierter Modus |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | + 84 4 3926 3000 | + 84 4 5555 5555   | Priorität 1: ^\+84 (\d{9}) $-VNsbc.contoso.com <br> Priorität 2:. *-proxysbc.contoso.com   | VNsbc.contoso.com – immer umgehen <br> proxysbc.contoso.com – immer umgehen


Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit Always Bypass-Modus und den Benutzer am gleichen Speicherort wie der SBC.

![Diagramm mit ausgehenden Anrufen](media/direct-routing-media-op-10.png "Ausgehende Anrufe")

Die folgende Tabelle zeigt die X-MS-Kopfzeilen, die durch Direct Routing gesendet wurden:

| Parameter | Erklärung |
|:------------|:-------|
| Einladen + 8443926300@VNsbc.contoso.com | Der Zielname des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet | 
| X-MS-UserLocation: intern | Das Feld hat angegeben, dass sich der Benutzer im Unternehmensnetzwerk befindet |
| X-MS-MediaPath: VNsbc.contoso.com |   Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss. In diesem Fall, da wir immer Bypass haben und der Client intern ist, wird der Zielname als einziger Name im Header gesendet. | 
|X-MS-UserSite: Vietnam |   Das Feld, das auf der Website angegeben ist, in der sich der Benutzer befindet. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit Always Bypass

| Modus |    Benutzer |  Ort |  Anrufrichtung |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Intern | Dieselbe Website wie SBC | Inbound |


Bei einem eingehenden Anruf ist der Standort des Benutzers unbekannt, und der SBC muss erraten, wo sich der Benutzer befindet. Wenn die Vermutung nicht korrekt ist, wird eine erneute Einladung benötigt. In diesem Fall wird davon ausgegangen, dass der Benutzer intern ist, Medien direkt fließen können und keine weiteren Aktionen erforderlich sind (erneut einladen).
Der SBC, der mit dem Direct Routing-Dienst verbunden ist, meldet den ursprünglichen SBC-Standort durch Bereitstellen von Daten Satz Routen-und Kontaktfeldern. Basierend auf diesen Feldern wird der Medienpfad durch direkte Weiterleitung berechnet.

Hinweis: da ein Benutzer mehrere Endpunkte haben kann, ist die Unterstützung von 183 nicht möglich. Die direkte Weiterleitung wird in diesem Fall immer 180-Klingeln verwenden. 

Das folgende Diagramm zeigt die SIP-Leiter für eingehende Anrufe mit dem AlwaysBypass-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Ausgehende Anrufe und der Benutzer ist extern mit Always Bypass

| Modus |    Benutzer |  Standort |  Anrufrichtung
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Extern |  N/A | Ausgehend |


Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern:

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-12.png)

Die folgende Tabelle zeigt die X-MS-Header, die vom Direct Routing-Dienst gesendet wurden:

| Parameter |   Erklärung |
|:------------|:-------|
|Einladen + 8443926300@VNsbc.contoso.com | Der Zielname des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet.|
| X-MS-UserLocation: Extern | Das Feld hat angegeben, dass der Benutzer sich außerhalb des Unternehmensnetzwerks befindet. |
| X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com    | Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss. In diesem Fall, da wir immer Bypass haben und der Client extern ist. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Eingehende Anrufe und der Benutzer ist extern mit Always Bypass

| Modus | Benutzer | Standort |  Anrufrichtung |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Extern |  N/A |   Inbound |

Bei einem eingehenden Anruf muss der SBC, der mit dem direkten Routing verbunden ist, eine erneute Einladung senden (Standardmäßig werden lokale Medien Kandidaten immer angeboten), wenn der Standort des Benutzers extern ist.  Die X-MediaPath wird basierend auf der Daten Satz Route und dem angegebenen SBC-Benutzer berechnet.

Das folgende Diagramm zeigt die SIP-Leiter für einen eingehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern.

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Nur für den lokalen Benutzermodus

Lokale Medien Kandidaten des Ziel-SBC werden nur angeboten, wenn sich ein Benutzer am selben Ort wie der SBC befindet. In allen anderen Fällen fließen Medien entweder über eine interne oder externe IP-Adresse des Proxy-SBC.

Die folgenden Szenarien werden beschrieben:

- [Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk.](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Eingehende Anrufe und der Benutzer ist intern, aber nicht am selben Ort wie der SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:

| Physischer Standort des Benutzers |  Der Benutzer macht oder empfängt einen Anruf an/von der Nummer |  Telefonnummer des Benutzers | Online-VoIP-Routing Richtlinie |   Für SBC konfigurierter Modus |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | + 84 4 3926 3000 |  + 84 4 5555 5555 | Priorität 1: ^\+84 (\d{9}) $-VNsbc.contoso.com <br> Priorität 2:. *-proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – immer umgehen |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit nur für lokale Benutzer

| Modus | Benutzer | Standort | Anrufrichtung |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Intern |Identisch mit SBC   | Ausgehend |

Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC. Dies ist derselbe Fluss, der bei [ausgehenden Anrufen angezeigt wird, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit nur für lokale Benutzer

| Modus | Benutzer | Standort | Anrufrichtung |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Intern | Identisch mit SBC | Inbound |

Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC. Hierbei handelt es sich um denselben Fluss wie in [eingehenden Anrufen, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk mit nur für lokale Benutzer.

| Modus | Benutzer | Standort |Anrufrichtung |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Intern |   Anders als SBC | Ausgehend |

Das direkte Routing berechnet X-MediaPath basierend auf dem gemeldeten Speicherort des Benutzers und des Modus, der für den SBC konfiguriert wurde.


Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Eingehender Anruf und der Benutzer ist intern, befindet sich aber nicht am gleichen Ort wie der SBC mit nur für lokale Benutzer

| Modus |    Benutzer |  Standort |  Anrufrichtung |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Intern |    Anders als SBC |    Inbound |

Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-17.png)









