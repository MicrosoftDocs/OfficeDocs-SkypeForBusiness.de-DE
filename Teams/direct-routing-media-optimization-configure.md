---
title: Konfigurieren der lokalen Medienoptimierung für Direct Routing
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
description: Konfigurieren der lokalen Medienoptimierung für Direct Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58cf5f560a22a58cb76ea28389d0dce1e3b3f4fb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674877"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Konfigurieren der lokalen Medienoptimierung für Direct Routing

Die Konfiguration für die lokale Medienoptimierung basiert auf Netzwerkeinstellungen, die mit anderen Cloud-VoIP-Funktionen wie Location-Based Routing und dynamischen Notrufen gemeinsam sind. Weitere Informationen zu Netzwerkregionen, Netzwerkstandorten, Netzwerksubnetzen und vertrauenswürdigen IP-Adressen finden Sie unter [Netzwerkeinstellungen für Cloud-VoIP-Features](cloud-voice-network-settings.md).

Bevor Sie die lokale Medienoptimierung konfigurieren, lesen Sie die [Lokale Medienoptimierung für Direct Routing](direct-routing-media-optimization.md).

Zum Konfigurieren der lokalen Medienoptimierung sind die folgenden Schritte erforderlich. Sie können das Teams Admin Center oder PowerShell verwenden. Ausführliche Informationen finden [Sie unter Verwalten ihrer Netzwerktopologie](manage-your-network-topology.md).

1. Konfigurieren Sie den Benutzer und die SBC-Websites (wie in diesem Artikel beschrieben).
2. Konfigurieren Sie die SBCs für die lokale Medienoptimierung (gemäß Ihrer SBC-Anbieterspezifikation).

Das folgende Diagramm zeigt die Netzwerkeinrichtung, die in den Beispielen in diesem Artikel verwendet wird.

> [!div class="mx-imgBorder"]
> ![Diagramm, das die Netzwerkeinrichtung für Beispiele zeigt.](media/direct-routing-media-op-9.png "Netzwerksetup für Beispiele")

## <a name="configure-the-user-and-the-sbc-sites"></a>Konfigurieren des Benutzers und der SBC-Websites

Um den Benutzer und die SBC-Websites zu konfigurieren, müssen Sie Folgendes ausführen:

1. [Verwalten externer vertrauenswürdiger IP-Adressen](#manage-external-trusted-ip-addresses).

2. [Definieren Sie die Netzwerktopologie](#define-the-network-topology) , indem Sie die Netzwerkregionen, Netzwerkstandorte und Netzwerksubnetze konfigurieren.

3. [Definieren Sie die virtuelle Netzwerktopologie](#define-the-virtual-network-topology) , indem Sie Standort(en) SBC(s) mit relevanten Modi und Proxy-SBC-Werten zuweisen.

> [!NOTE]
> Die lokale Medienoptimierung basiert darauf, dass Clientstandorte im Verhältnis zu den Unternehmensnetzwerken, die über eine interne Schnittstelle des Direct Routing (DR) Session Border Controller (SBC) verfügen, als externe oder interne Standorte erkannt werden.
> In Vpn-Szenarien mit geteiltem Tunnel, wenn der Clientendpunkt als extern für das Netzwerk des Kunden erkannt wird, signalisiert Microsoft dem SBC den externen Standort, obwohl der Client die interne Schnittstelle des Direct Routing-SBC des Kunden erreichen kann. Direct Routing-Kunden, die die lokale Medienoptimierung verwenden, können längere Anrufeinrichtungszeiten und in einigen Fällen keine Audiodaten beim Empfang von Anrufen aus dem PSTN erleben.
> Um dies zu vermeiden, müssen VPN-Administratoren den Zugriff zwischen Remote-VPN-Benutzern und der internen Direct Routing-SBC-Schnittstelle blockieren.

## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Konfigurieren von SBC(s) für die lokale Medienoptimierung gemäß der Spezifikation des SBC-Anbieters

In diesem Artikel wird die Konfiguration für Microsoft-Komponenten beschrieben. Informationen zur SBC-Konfiguration finden Sie in der Dokumentation Ihres SBC-Anbieters. Informationen dazu, welche SBC-Anbieter die lokale Medienoptimierung unterstützen, finden Sie unter [Session Border Controllers Certified for Direct Routing](direct-routing-border-controllers.md).

## <a name="manage-external-trusted-ip-addresses"></a>Verwalten externer vertrauenswürdiger IP-Adressen

Externe vertrauenswürdige IPs sind die externen Internet-IPs des Unternehmensnetzwerks. Diese IP-Adressen sind die IP-Adressen, die von Microsoft Teams Clients verwendet werden, wenn sie eine Verbindung mit Microsoft 365 herstellen. Sie müssen diese externen IPs für jede Website hinzufügen, auf der Benutzer die lokale Medienoptimierung verwenden.

Um die öffentlichen IP-Adressen für jede Website hinzuzufügen, verwenden Sie das cmdlet New-CsTenantTrustedIPAddress. Sie können eine unbegrenzte Anzahl vertrauenswürdiger IP-Adressen für einen Mandanten definieren. Wenn die externen IPs, die von Microsoft 365 angezeigt werden, sowohl IPv4- als auch IPv6-Adressen sind, müssen Sie beide Arten von IP-Adressen hinzufügen. Verwenden Sie für IPv4 das Format 32. Verwenden Sie für IPv6 das Format 128. Sie können sowohl einzelne externe IP-Adressen als auch externe IP-Subnetze hinzufügen, indem Sie verschiedene MaskBits für das Cmdlet angeben.

```powershell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```

Beispiel für das Hinzufügen vertrauenswürdiger IP-Adressen.

```powershell
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```

## <a name="define-the-network-topology"></a>Definieren der Netzwerktopologie

In diesem Abschnitt wird beschrieben, wie Sie die Netzwerkregionen, Netzwerkstandorte und Netzwerksubnetze für Ihre Netzwerktopologie definieren.

Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, sodass Sie sicherstellen müssen, dass Sie denselben Fall verwenden, der während des Setups verwendet wurde.  (Beispielsweise werden die GatewaySiteID-Werte "Vietnam" und "vietnam" als unterschiedliche Websites behandelt.)

### <a name="define-network-regions"></a>Definieren von Netzwerkregionen

Verwenden Sie zum Definieren von Netzwerkregionen das cmdlet New-CsTenantNetworkRegion. Der Parameter "RegionID" ist ein logischer Name, der die Geografie der Region darstellt und keine Abhängigkeiten oder Einschränkungen aufweist. Der Parameter "CentralSite" `<site ID>` ist optional.

```powershell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>
```

Im folgenden Beispiel wird eine Netzwerkregion namens APAC erstellt:

```powershell
New-CsTenantNetworkRegion -NetworkRegionID "APAC"
```

### <a name="define-network-sites"></a>Definieren von Netzwerkstandorten

Verwenden Sie zum Definieren von Netzwerkstandorten das cmdlet New-CsTenantNetworkSite. Jeder Netzwerkstandort muss einer Netzwerkregion zugeordnet sein.

```powershell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

Im folgenden Beispiel werden drei neue Netzwerkstandorte erstellt: Vietnam, Indonesien und Singapur in der Region APAC:

```powershell
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definieren von Netzwerksubnetzen

Verwenden Sie das cmdlet New-CsTenantNetworkSubnet, um Netzwerksubnetze zu definieren und netzwerkstandorten zuzuordnen. Jedes Netzwerksubnetz kann nur einem Standort zugeordnet werden.

```powershell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

Im folgenden Beispiel werden drei Netzwerksubnetze definiert und den drei Netzwerkstandorten Zugeordnet: Vietnam, Indonesien und Singapur:

```powershell
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID "Vietnam"
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID "Indonesia"
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID "Singapore"
```

## <a name="define-the-virtual-network-topology"></a>Definieren der Topologie des virtuellen Netzwerks

Zunächst erstellt der Mandantenadministrator mithilfe des cmdlets New-CsOnlinePSTNGateway eine neue SBC-Konfiguration für jeden relevanten SBC.
Der Mandantenadministrator definiert die virtuelle Netzwerktopologie, indem er die Netzwerkstandorte für die PSTN-Gatewayobjekte mithilfe des cmdlets Set-CsOnlinePSTNGateway angibt:

```powershell
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Beachten Sie Folgendes:

- Wenn der Kunde über einen einzelnen SBC verfügt, muss der Parameter "-ProxySBC" entweder obligatorisch $null oder ein SBC-FQDN-Wert (zentraler SBC mit zentralisierten Trunks) sein.
- Der Parameter "-MediaBypass" muss auf $true festgelegt werden, um die lokale Medienoptimierung zu unterstützen.
- Wenn für den SBC der Parameter "-BypassMode" nicht festgelegt ist, werden keine X-MS-Header gesendet.
- Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, sodass Sie sicherstellen müssen, dass Sie denselben Fall verwenden, der während des Setups verwendet wurde.  (Beispielsweise werden die GatewaySiteID-Werte "Vietnam" und "vietnam" als unterschiedliche Websites behandelt.)

Im folgenden Beispiel werden den Netzwerkstandorten Vietnam, Indonesien und Singapur in der Region APAC drei SBCs mit dem Modus "Immer umgehen" hinzugefügt:

```powershell
Set-CSOnlinePSTNGateway -Identity "proxysbc.contoso.com" -GatewaySiteID "Singapore" -MediaBypass $true -BypassMode "Always" -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity "VNsbc.contoso.com" -GatewaySiteID "Vietnam" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"

Set-CSOnlinePSTNGateway -Identity "IDsbc.contoso.com" -GatewaySiteID "Indonesia" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"
```

> [!NOTE]
> Um unterbrechungsfreien Betrieb sicherzustellen, wenn lokale Medienoptimierung und Location-Based Routing (LBR) gleichzeitig konfiguriert sind, müssen nachgeschaltete SBCs für LBR aktiviert werden, indem der GatewaySiteLbrEnabled-Parameter für jeden nachgeschalteten SBC auf $true festgelegt wird. (Diese Einstellung ist für den Proxy-SBC nicht obligatorisch.)

Basierend auf den obigen Informationen enthält Direct Routing drei proprietäre SIP-Header für SIP-Einladungen und erneute Einladungen, wie in der folgenden Tabelle dargestellt.

In Direct Routing für Einladungen eingeführte X-MS-Header und Re-Invites, wenn BypassMode definiert ist:

|Kopfzeilenname|Werte|Kommentare|
|---|---|---|
|X-MS-UserLocation|intern/extern|Gibt an, ob der Benutzer intern oder extern ist.|
|Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0|SBC-FQDN|Der FQDN, der für den Anruf bestimmt ist, auch wenn der SBC nicht direkt mit Direct Routing verbunden ist|
|X-MS-MediaPath|Beispiel: proxysbc.contoso.com, VNsbc.contoso.com|Reihenfolge der SBCs, die für den Medienpfad zwischen dem Benutzer und dem Ziel-SBC verwendet werden sollen. Der letzte SBC ist immer der letzte|
|X-MS-UserSite|usersiteID|Vom Mandantenadministrator definierte Zeichenfolge|

## <a name="call-flows"></a>Anrufflüsse

Im Folgenden werden Anrufflüsse für zwei Modi gezeigt:

- [Immer umgehen](#always-bypass-mode)
- [Nur für lokale Benutzer](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Modus immer umgehen

Der Modus "Immer umgehen" ist die einfachste Option zum Konfigurieren. Der Mandantenadministrator kann eine einzelne Website für alle Benutzer und SBCs konfigurieren, wenn alle SBCs von einer beliebigen Website aus erreichbar sind.

Die Beispiele zeigen den Modus "Immer umgehen" für die folgenden Szenarien:

- [Ausgehende Anrufe und der Benutzer am selben Speicherort wie der SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Eingehende Anrufe, und der Benutzer befindet sich am selben Speicherort wie der SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Ausgehende Anrufe und externer Benutzer](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Eingehende Anrufe und der Benutzer ist extern](#inbound-calls-and-the-user-is-external-with-always-bypass)

Die folgende Tabelle zeigt die in den Beispielen verwendeten FQDN- und IP-Adressen:

|FQDN|Externe SBC-IP-Adresse|Interne SBC-IP-Adresse|Internes Subnetz|Ort|Externe NAT (Vertrauenswürdige IP)|
|---|---|---|---|---|---|
|VNsbc.contoso.com|Keine|192.168.1.5|192.168.1.0/24|Vietnam|172.16.240.110|
|IDsbc.contoso.com|Keine|192.168.2.5|192.168.2.0/24|Indonesien|172.16.240.120|
|proxysbc.contoso.com|172.16.240.133|192.168.3.5|192.168.3.0/24|Singapur|172.16.240.130|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Ausgehende Anrufe, und der Benutzer befindet sich am selben Speicherort wie der SBC mit "Immer umgehen"

|Modus|Benutzer|Ort|Anrufrichtung|
|---|---|---|---|
|AlwaysBypass|Intern|Dieselbe Website wie SBC|Ausgehend|

Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:

|Physischer Standort des Benutzers|Der Benutzer nimmt einen Anruf an/von der Nummer an oder empfängt ihn.|Telefonnummer des Benutzers|Online-VoIP-Routingrichtlinie|Für SBC konfigurierter Modus|
|---|---|---|---|---|
|Vietnam|+84 4 3926 3000|+84 4 5555 5555|Priorität 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Priorität 2: .* - proxysbc.contoso.com|VNsbc.contoso.com – Immer umgehen <br> proxysbc.contoso.com – Immer umgehen|

Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit dem Modus "Immer umgehen" und den Benutzer am selben Ort wie der SBC.

> [!div class="mx-imgBorder"]
> ![Diagramm mit ausgehenden Anrufen.](media/direct-routing-media-op-10.png "Ausgehende Anrufe")

Die folgende Tabelle zeigt die X-MS-Header, die von Direct Routing gesendet werden:

|Parameter|Erklärung|
|---|---|
|Einladen +8443926300@VNsbc.contoso.com|Der Ziel-FQDN des SBC gemäß definition in der Online-VoIP-Routingrichtlinie wird im Anforderungs-URI gesendet.|
|X-MS-UserLocation: intern|Das Feld gibt an, dass sich der Benutzer innerhalb des Unternehmensnetzwerks befindet.|
|X-MS-MediaPath: VNsbc.contoso.com|Gibt an, welchen SBC der Client zum Ziel-SBC durchlaufen muss. In diesem Fall haben wir always Bypass, und der Client ist intern der Zielname, der als einziger Name in der Kopfzeile gesendet wird.|
|X-MS-UserSite: Vietnam|Das Feld, das auf der Website angegeben ist, auf der sich der Benutzer befindet.|

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Eingehende Anrufe, und der Benutzer befindet sich am selben Speicherort wie der SBC mit "Immer umgehen".

|Modus|Benutzer|Ort|Anrufrichtung|
|---|---|---|---|---|
|AlwaysBypass|Intern|Dieselbe Website wie SBC|Eingehende|

Bei einem eingehenden Anruf ist der Standort des Benutzers unbekannt, und der SBC muss erraten, wo sich der Benutzer befindet. Wenn der Schätzwert nicht richtig ist, ist eine erneute Einladung erforderlich. In diesem Fall wird davon ausgegangen, dass der Benutzer intern ist, Medien direkt fließen können und keine weiteren Aktionen erforderlich sind (erneutes Einladen).
Der mit dem Direct Routing-Dienst verbundene SBC meldet den ursprünglichen SBC-Standort, indem er Record-Route- und Kontaktfelder bereitstellt. Basierend auf diesen Feldern wird der Medienpfad durch Direct Routing berechnet.

Hinweis: Da ein Benutzer mehrere Endpunkte haben kann, ist die Unterstützung von 183 nicht möglich. Das Direct Routing verwendet in diesem Fall immer 180 Klingeln.

Das folgende Diagramm zeigt die SIP-Leiter für eingehende Anrufe im AlwaysBypass-Modus, und der Benutzer befindet sich an derselben Stelle wie der SBC.

> [!div class="mx-imgBorder"]
> ![Diagramm, das die SIP-Leiter zeigt.](media/direct-routing-media-op-11.png)

#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Ausgehende Anrufe und der Benutzer sind extern mit "Immer umgehen"

|Modus|Benutzer|Site|Anrufrichtung
|---|---|---|---|
|AlwaysBypass|Extern|Nicht zutreffend|Ausgehend|

Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf im AlwaysBypass-Modus, und der Benutzer ist extern:

> [!div class="mx-imgBorder"]
> ![Das Diagramm zeigt die SIP-Leiter.](media/direct-routing-media-op-12.png)

Die folgende Tabelle zeigt die X-MS-Header, die vom Direct Routing-Dienst gesendet werden:

|Parameter|Erklärung|
|---|---|
|Einladen +8443926300@VNsbc.contoso.com|Der Ziel-FQDN des SBC gemäß definition in der Online-VoIP-Routingrichtlinie wird im Anforderungs-URI gesendet.|
|X-MS-UserLocation: extern|Das Feld hat angegeben, dass sich der Benutzer außerhalb des Unternehmensnetzwerks befindet.|
|X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com|Gibt an, welchen SBC der Client zum Ziel-SBC durchlaufen muss. In diesem Fall, da wir immer umgehen, und der Client ist extern.|

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Eingehende Anrufe und der Benutzer ist extern mit "Immer umgehen"

|Modus|Benutzer|Site|Anrufrichtung|
|---|---|---|---|
|AlwaysBypass|Extern|Nicht zutreffend|Eingehende|

Für einen eingehenden Anruf muss der mit Direct Routing verbundene SBC eine erneute Einladung senden (standardmäßig werden immer lokale Medienkandidaten angeboten), wenn der Standort des Benutzers extern ist.  Der X-MediaPath wird basierend auf Record-Route und dem angegebenen SBC-Benutzer berechnet.

Das folgende Diagramm zeigt die SIP-Leiter für einen eingehenden Anruf im AlwaysBypass-Modus, und der Benutzer ist extern.

> [!div class="mx-imgBorder"]
> ![Diagramm, das erneut eine SIP-Leiter zeigt.](media/direct-routing-media-op-13.png)

### <a name="only-for-local-users-mode"></a>Nur für den Modus "Lokale Benutzer"

Lokale Medienkandidaten des Ziel-SBC werden nur angeboten, wenn sich ein Benutzer am selben Speicherort wie der SBC befindet. In allen anderen Fällen werden Medien entweder über eine interne oder externe IP des Proxy-SBC übertragen.

Die folgenden Szenarien werden beschrieben:

- [Ausgehende Anrufe und der Benutzer am selben Speicherort wie der SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Eingehende Anrufe, und der Benutzer befindet sich am selben Speicherort wie der SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Der Benutzer befindet sich nicht am selben Speicherort wie der SBC, sondern befindet sich im Unternehmensnetzwerk.](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Eingehende Anrufe und der Benutzer sind intern, befinden sich aber nicht am selben Ort wie der SBC.](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:

|Physischer Standort des Benutzers|Der Benutzer nimmt einen Anruf an/von der Nummer an oder empfängt ihn.|Telefonnummer des Benutzers|Online-VoIP-Routingrichtlinie|Für SBC konfigurierter Modus|
|---|---|---|---|---|
|Vietnam|+84 4 3926  3000|+84 4 5555 5555|Priorität 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Priorität 2: .* - proxysbc.contoso.com|VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Immer umgehen|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Ausgehende Anrufe und der Benutzer befinden sich am selben Speicherort wie der SBC mit nur für lokale Benutzer

|Modus|Benutzer|Site|Anrufrichtung|
|---|---|---|---|
|OnlyForLocalUsers|Intern|Identisch mit SBC|Ausgehend|

Das folgende Diagramm zeigt einen ausgehenden Aufruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich an derselben Position wie der SBC. Dies ist der gleiche Ablauf, der in [ausgehenden Anrufen angezeigt wird, wenn sich der Benutzer am selben Speicherort wie der SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass) befindet.

> [!div class="mx-imgBorder"]
> ![Das Diagramm zeigt erneut eine SIP-Leiter.](media/direct-routing-media-op-14.png)

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Eingehende Anrufe, und der Benutzer befindet sich am selben Speicherort wie der SBC mit "Nur für lokale Benutzer".

|Modus|Benutzer|Site|Anrufrichtung|
|---|---|---|---|
|OnlyForLocalUsers|Intern|Identisch mit SBC|Eingehende|

Das folgende Diagramm zeigt einen eingehenden Aufruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich an derselben Position wie der SBC. Dies ist der gleiche Ablauf wie bei [eingehenden Anrufen, wenn sich der Benutzer am selben Speicherort wie der SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass) befindet.

> [!div class="mx-imgBorder"]
> ![Ein weiteres Diagramm, das die SIP-Leiter zeigt.](media/direct-routing-media-op-15.png)

#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>Der Benutzer befindet sich nicht am selben Speicherort wie der SBC, sondern befindet sich im Unternehmensnetzwerk nur für lokale Benutzer.

|Modus|Benutzer|Site|Anrufrichtung|
|---|---|---|---|
|OnlyForLocalUsers|Intern|Anders als SBC|Ausgehend|

Direct Routing berechnet X-MediaPath basierend auf dem gemeldeten Standort des Benutzers und des modus, der auf dem SBC konfiguriert ist.

Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht an derselben Position wie der SBC befindet.

> [!div class="mx-imgBorder"]
> ![Ein weiteres Diagramm zeigt die SIP-Leiter.](media/direct-routing-media-op-16.png)

#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Eingehender Anruf und der Benutzer intern, aber nicht am selben Ort wie der SBC mit "Nur für lokale Benutzer"

|Modus|Benutzer|Site|Anrufrichtung|
|---|---|---|---|
|OnlyForLocalUsers|Intern|Anders als SBC|Eingehende|

Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am selben Ort wie der SBC befindet.

> [!div class="mx-imgBorder"]
> ![Ein weiteres Diagramm, das die SIP-Leiter zeigt.](media/direct-routing-media-op-17.png)
