---
title: Direkte SIP-Verbindungen in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Direkte SIP-Verbindungen werden zwischen Skype für Business Server und sowohl PSTN-Gateways und IP-PBX-Ressource in Enterprise-VoIP unterstützt.
ms.openlocfilehash: 1ddcf66fb19f39661ffdd4cffdff754999db90d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890129"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Direkte SIP-Verbindungen in Skype für Business Server

Direkte SIP-Verbindungen werden zwischen Skype für Business Server und sowohl PSTN-Gateways und IP-PBX-Ressource in Enterprise-VoIP unterstützt.

Sie können direkte SIP-Verbindungen Verbindung Skype für Business Server mit einer der folgenden verwenden:

- An IP-PBX 

- A PSTN gateway

To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk. In beiden Fällen implementieren Sie die Verbindung mithilfe der externen Schnittstelle eines Vermittlungsservers. The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.

## <a name="direct-sip-deployment-options"></a>Direct SIP deployment options

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Wenn Ihre Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet, können Sie als einzige telefonielösung für eine Organisation ganz oder teilweise Skype für Business Server verwenden. This section describes the following deployments in detail:

- **Inkrementelle Bereitstellung:** Diese Option wird davon ausgegangen, dass Sie über eine vorhandene Infrastruktur mit private Branch Exchange, (Nebenstellenanlage PBX) verfügen, und Sie Enterprise Voice schrittweise für kleinere Gruppen oder Teams innerhalb Ihrer Organisation einführen möchten.

- **Nur VoIP-Bereitstellung:** dieser Option wird davon ausgegangen, dass Sie beabsichtigen, Bereitstellung von Enterprise-VoIP an einem Standort, die keine herkömmliche Telefonieinfrastruktur vorhanden ist.

#### <a name="incremental-deployment"></a>Incremental Deployment

Inkrementelle Bereitstellung Skype für Business Server ist die einzige telefonielösung für einzelne Teams oder Abteilungen, während die übrigen Benutzer in einer Organisation weiterhin eine Nebenstellenanlage verwenden. This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs. Arbeitsgruppen, deren Kommunikation sind die Anforderungen am besten von Microsoft Unified Communications bedient, werden in Enterprise-VoIP, verschoben, während andere Benutzer auf die vorhandene Nebenstellenanlage bleiben. Zusätzliche Arbeitsgruppen können bei Bedarf zu Enterprise-VoIP migriert werden.

The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management. This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant. In fact, this option is useful for creating virtual teams whose members may be scattered across the globe. You can create, modify, or disband such teams in rapid response to shifting business requirements.

Die folgende Abbildung zeigt die allgemeine Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Nebenstellenanlage. This is the recommended topology for incremental deployment.

**Incremental deployment option**

![Abteilungsbezogene Migrationsoption (Diagramm)](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Wenn Sie Ihre Skype für Business Server-Bereitstellung mit einem zertifizierten direkte SIP-Partner herstellen, ist ein Gateway public switched Telephone Network, (PSTN) zwischen dem Vermittlungsserver und der Nebenstellenanlage nicht erforderlich. Eine Liste mit zertifizierten direkte SIP-Partnern finden Sie auf der [Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> The media path shown in this figure has media bypass enabled (the recommended configuration). Wenn Sie sich entscheiden, um die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungsserver weitergeleitet.

In dieser Topologie werden ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise Voice aktiviert. A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX. Benutzer, die für Remotemitarbeiter, einschließlich Enterprise-VoIP aktiviert sind die Kommunikation über das IP-Netzwerk. Anrufe von Enterprise-VoIP-Benutzern mit dem PSTN und Kollegen, die nicht für Enterprise Voice aktiviert sind, werden über das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Kollegen, die sich immer noch das PBX-System befinden oder von Anrufern auf das Telefonfestnetz werden an das PSTN-Gateway weitergeleitet, die die Aufrufe von Skype für das routing für Business Server weiterleitet.

Es gibt zwei Empfohlene Konfigurationen für die Verbindung von Enterprise-VoIP mit einer vorhandenen PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Nebenstellenanlage und Enterprise-VoIP vor der Nebenstellenanlage.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice Behind the PBX

Bei der Bereitstellung von Enterprise-VoIP hinter der Nebenstellenanlage erreichen der Nebenstellenanlage, die Anrufe bei Benutzern von Enterprise-VoIP-Routen für ein PSTN-Gateway und PBX-Benutzern mit der Nebenstellenanlage Ruft alle Anrufe über das PSTN.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice in Front of the PBX

Das PSTN-Gateway leitet Anrufe für Enterprise-VoIP-Benutzern, Skype Business Server auch für Anrufe für PBX-Benutzer mit der Nebenstellenanlage Problembehandlungsprozesse alle Anrufe, bei der Bereitstellung von Enterprise-VoIP vor der Nebenstellenanlage. Anrufe an das Telefonfestnetz von Benutzern für Enterprise-VoIP und einer Nebenstellenanlage werden über das IP-Netzwerk an das kosteneffizienteste PSTN-Gateway weitergeleitet. The following table shows the advantages and disadvantages of this configuration.

**Vor- und Nachteile der Bereitstellung von Enterprise-VoIP vor einer Nebenstellenanlage**

|**Advantages**|**Disadvantages**|
|:-----|:-----|
|Die Nebenstellenanlage bedient weiterhin die Benutzer für Enterprise-VoIP nicht aktiviert.  <br/> |Existing gateways may not support the features or capacity that you want.  <br/> |
|PBX handles all earlier devices.  <br/> |Erfordert einen Trunk aus Gateway zur Nebenstellenanlage und dem Gateway an den Vermittlungsserver. You may need more trunks from the service provider.  <br/> |
|Enterprise-VoIP-Benutzer behalten Ihre Rufnummern.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a> VoIP-Only Deployment

Enterprise-VoIP bietet neue Unternehmen sowie neue Websites in Office für vorhandene Unternehmen die Möglichkeit, eine voll funktionsfähige VoIP-Lösung implementieren, ohne Gedanken PBX-Integration müssen oder dass die umfangreiche Bereitstellung und Wartung Kosten für eine IP-PBX-Infrastruktur. This solution supports both on-site and remote workers.

In this deployment, all calls are routed over the IP network. Calls to the PSTN are routed to the appropriate PSTN gateway. Skype für Geschäftskunden und Lync Phone Edition dienen als Softphone. Remote call control is unavailable and unnecessary because there are no PBX phones for users to control. Voicemail und automatische Telefonzentrale sind optional über von Exchange Unified Messaging (UM) verfügbar.

> [!NOTE]
> Zusätzlich zur Netzwerkinfrastruktur, die zur Unterstützung von Skype für Business Server erforderlich ist, können eine nur-VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Fax- und analogen Geräten.

The following figure shows a typical topology for a VoIP-only deployment.

**VoIP-only deployment option**

![Greenfidle-Bereitstellungsoption](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> The media path shown in this figure has media bypass enabled (the recommended configuration). Wenn Sie sich entscheiden, um die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungsserver weitergeleitet.

## <a name="pstn-gateway-deployment-options"></a>PSTN Gateway deployment options

### <a name="pstn-gateways"></a>PSTN Gateways

Gateways Public switched Telephone Network (Telefonfestnetz PSTN) werden von Drittanbietern Hardwarekomponenten, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz weder direkt noch über Verbindung mit SIP-Trunks übersetzen. In either topology, the gateway terminates the PSTN. Das Gateway wird in einem eigenen Subnetz isoliert und mit dem Unternehmensnetzwerk über den Vermittlungsserver verbunden ist.

An enterprise with multiple sites would typically deploy one or more gateways at each site. Zweigniederlassungen können an das Telefonfestnetz über ein Gateway oder über eine Survivable Branch Appliance, die mit dem Gateway und Server in einem Feld kombiniert verbinden. Wenn Zweigniederlassungen ein Gateway verwendet werden, sind eine Registrierung und den Vermittlungsserver klicken Sie auf Website erforderlich, es sei denn, die WAN-Verbindung ausfallsicher ist. Mindestens einen Vermittlungsserver, die Front-End-Server verbunden sind, können Anrufe für die eine oder mehrere Gateways an jedem Standort weitergeleitet. Es wird empfohlen, dass die Registrierung, Vermittlungsserver und -Gateway erforderlich auf Website als eine Survivable Branch Appliance bereitgestellt werden.

Bestimmen der Anzahl, Größe und Position des PSTN-Gateways ist möglicherweise die wichtigste und teuerste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.

Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent

- How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).

- What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.

- Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.

   You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).

#### <a name="mn-trunk-support"></a>M:N Trunk Support

Der Vermittlungsserver können Anrufe über mehrere Gateways, Session Border Controller (SBCs) von bereitgestellten Internet Telefoniedienstanbieter, oder eine Kombination aus beidem weiterleiten. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route zwischen einem Vermittlungsserver und einem Gateway definiert wird einen Trunk aufgerufen. Wenn ein interner Benutzer einen PSTN-Anruf tätigt, wählt ausgehende Routinglogik auf den Front-End-Pool welche Trunk über alle möglichen Kombinationen weitergeleitet, die für das routing von bestimmten Aufruf verfügbar sein können. Mit der DNS-Lastenausgleich, wenn ein Aufruf fehlschlägt, ein Gateway aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool erreicht wird der Anruf an einen anderen Mediation Server im Pool wiederholt.

Ausführliche Informationen zur Planung für mehrere Gateways finden Sie unter [m: n-Trunk in Skype für Business Server](m-n-trunk.md).

For details about other outbound routing enhancements, see [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Gateway Topologies

When you consider the fundamental questions of gateway deployment, follow these steps:

1. Zählen Sie die Standorte, an denen Sie PSTN-Konnektivität mit Enterprise-VoIP bereitstellen möchten.

2. Estimate the traffic at each site (number of users and average number of calls per hour per user).

3. Deploy one or more gateways at each site to handle the anticipated traffic.

With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.

Um dieses Problem zu beheben, lieber viele große Unternehmen ein oder mehrere große Telefonie zentralen Standorten bereitstellen.

In dieser Topologie werden mehrere große Gateways für die vorherzusehende benutzerauslastung ausreichend an jedem zentralen Standort bereitgestellt. All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site. Routinglogik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder an das PSTN weitergeleitet werden sollen.

#### <a name="gateway-location"></a>Gateway Location

Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.

#### <a name="gateway-size-and-number"></a>Gateway Size and Number

The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:

- Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.

- Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.

- Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.

- Additional ports can be acquired as the number of users or amount of traffic in your organization increases.

For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails. 

Jeder PSTN-Gateway, die Sie bereitstellen, benötigen Sie mindestens einen zugehörigen Vermittlungsserver.


