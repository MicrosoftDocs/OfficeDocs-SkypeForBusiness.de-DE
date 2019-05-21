---
title: Direkte SIP-Verbindungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Direkte SIP-Verbindungen werden zwischen Skype for Business Server und sowohl PSTN-Gateways als auch IP-PBX in Enterprise-VoIP unterstützt.
ms.openlocfilehash: d70fa72032b86251870ebaf623679dedc782fe24
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276964"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Direkte SIP-Verbindungen in Skype for Business Server

Direkte SIP-Verbindungen werden zwischen Skype for Business Server und sowohl PSTN-Gateways als auch IP-PBX in Enterprise-VoIP unterstützt.

Sie können direkte SIP-Verbindungen verwenden, um Skype for Business Server mit einem der folgenden zu verbinden:

- An IP-PBX 

- A PSTN gateway

To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk. In beiden Fällen implementieren Sie die Verbindung mithilfe der externen Schnittstelle eines Vermittlungsservers. The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.

## <a name="direct-sip-deployment-options"></a>Direct SIP deployment options

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Wenn in Ihrer Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet wird, können Sie Skype for Business Server als einzige Telefonlösung für einen Teil oder eine ganze Organisation verwenden. This section describes the following deployments in detail:

- **Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene PBX-Infrastruktur (Private Branch Exchange) verfügen und beabsichtigen, Enterprise-VoIP inkrementell für kleinere Gruppen oder Teams innerhalb Ihrer Organisation einzuführen.

- **Nur-VoIP-Bereitstellung:** bei dieser Option wird davon ausgegangen, dass Sie die Bereitstellung von Enterprise-VoIP an einer Website erwägen, die keine herkömmliche Telefonie-Infrastruktur aufweist.

#### <a name="incremental-deployment"></a>Incremental Deployment

Bei der inkrementellen Bereitstellung ist Skype for Business Server die einzige Telefonlösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Telefonanlage verwenden. This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs. Arbeitsgruppen, deren Kommunikationsanforderungen am besten von Microsoft Unified Communications erfüllt werden, werden in Enterprise-VoIP verschoben, während andere Benutzer auf der vorhandenen Telefonanlage verbleiben. Zusätzliche Arbeitsgruppen können nach Bedarf in Enterprise-VoIP migriert werden.

The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management. This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant. In fact, this option is useful for creating virtual teams whose members may be scattered across the globe. You can create, modify, or disband such teams in rapid response to shifting business requirements.

Die folgende Abbildung zeigt die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Telefonanlage. This is the recommended topology for incremental deployment.

**Incremental deployment option**

![Abteilungsbezogene Migrationsoption (Diagramm)](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Wenn Sie die Bereitstellung von Skype for Business Server mit einem Certified Direct SIP-Partner verbinden, ist kein öffentliches PSTN-Gateway zwischen dem Vermittlungsserver und der Telefonanlage erforderlich. Eine Liste der zertifizierten Direct SIP-Partner finden Sie im [Microsoft Unified Communications Open Interoperability-Programm](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> The media path shown in this figure has media bypass enabled (the recommended configuration). Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.

In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert. A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX. Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remotemitarbeitern, kommunizieren über das IP-Netzwerk. Anrufe von Enterprise-VoIP-Benutzern an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Kollegen, die sich noch im PBX-System befinden, oder von Anrufern im PSTN, werden an das PSTN-Gateway weitergeleitet, das die Anrufe an den Skype for Business-Server für das Routing weiterleitet.

Es gibt zwei Empfohlene Konfigurationen für die Verbindung von Enterprise-VoIP zu einer vorhandenen PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Telefonanlage und Enterprise-VoIP vor der Telefonanlage.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice Behind the PBX

Wenn Enterprise-VoIP hinter der Telefonanlage bereitgestellt wird, kommen alle Anrufe vom PSTN an die Telefonanlage, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway weiterleitet, und Anrufe an PBX-Benutzer an die Telefonanlage.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice in Front of the PBX

Wenn Enterprise-VoIP vor der Telefonanlage bereitgestellt wird, gelangen alle Anrufe an das PSTN-Gateway, das Anrufe an Enterprise-VoIP-Benutzer an den Skype for Business-Server weiterleitet und Telefonanlagen Nutzer an die Telefonanlage anruft. Anrufe an das PSTN von Enterprise-VoIP-und PBX-Benutzern werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway weitergeleitet. The following table shows the advantages and disadvantages of this configuration.

**Vor-und Nachteile der Bereitstellung von Enterprise-VoIP vor einer Telefonanlage**

|**Advantages**|**Disadvantages**|
|:-----|:-----|
|PBX bietet weiterhin Benutzern, die nicht für Enterprise-VoIP aktiviert sind.  <br/> |Existing gateways may not support the features or capacity that you want.  <br/> |
|PBX handles all earlier devices.  <br/> |Erfordert einen trunk vom Gateway zur Telefonanlage und vom Gateway zum Vermittlungs Server. You may need more trunks from the service provider.  <br/> |
|Enterprise-VoIP-Benutzer behalten die gleichen Telefonnummern.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a> VoIP-Only Deployment

Enterprise-VoIP bietet neuen Unternehmen und auch neuen Office-Websites für vorhandene Unternehmen die Möglichkeit, eine vollständige VoIP-Lösung zu implementieren, ohne sich um die Integration von Telefonanlagen zu kümmern oder um eine beträchtliche Bereitstellung und Wartung zu vermeiden. Kosten einer IP-PBX-Infrastruktur. This solution supports both on-site and remote workers.

In this deployment, all calls are routed over the IP network. Calls to the PSTN are routed to the appropriate PSTN gateway. Skype for Business oder lync Phone Edition dient als Softphone. Remote call control is unavailable and unnecessary because there are no PBX phones for users to control. Voicemail-und automatische Telefonzentralendienste stehen über die optionale Bereitstellung von Exchange Unified Messaging (um) zur Verfügung.

> [!NOTE]
> Zusätzlich zur Netzwerkinfrastruktur, die für die Unterstützung von Skype for Business Server erforderlich ist, kann eine reine VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Faxgeräten und analogen Geräten verwenden.

The following figure shows a typical topology for a VoIP-only deployment.

**VoIP-only deployment option**

![Greenfidle-Bereitstellungsoption](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> The media path shown in this figure has media bypass enabled (the recommended configuration). Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.

## <a name="pstn-gateway-deployment-options"></a>PSTN Gateway deployment options

### <a name="pstn-gateways"></a>PSTN Gateways

PSTN-Gateways (Public Switched Telephone Network) sind Hardwarekomponenten von Drittanbietern, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über die Verbindung zu SIP-Stämmen. In either topology, the gateway terminates the PSTN. Das Gateway ist in seinem eigenen Subnetz isoliert und wird über den Vermittlungs Server mit dem Unternehmensnetzwerk verbunden.

An enterprise with multiple sites would typically deploy one or more gateways at each site. Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über eine Survivable Branch-Appliance herstellen, die Gateway und Server in einem einzigen Feld kombiniert. Wenn Verzweigungs Websites ein Gateway verwenden, sind auf der Website sowohl eine Registrierungsstelle als auch ein Vermittlungs Server erforderlich, es sei denn, die WAN-Verbindung ist widerstandsfähig. Auf einem oder mehreren Vermittlungsservern, die sich auf Front-End-Servern befinden, können Anrufe an die einen oder mehrere Gateways an jedem Standort weitergeleitet werden. Wir empfehlen, dass die auf der Website erforderliche Registrierungsstelle, der Vermittlungs Server und das Gateway als Survivable Branch Appliance bereitgestellt werden.

Die Ermittlung von Anzahl, Größe und Standort von PSTN-Gateways ist vielleicht die wichtigste und kostspieligste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.

Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent

- How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).

- What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.

- Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.

   You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).

#### <a name="mn-trunk-support"></a>M:N Trunk Support

Die Vermittlungsserver können Anrufe über mehrere Gateways (Session Border Controllers, SBCS), die von Internet-Telefoniedienst-Anbietern bereitgestellt werden, oder eine Kombination der beiden leiten. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route, die zwischen einem Vermittlungs Server und einem Gateway definiert wird, wird als trunk bezeichnet. Wenn ein interner Benutzer einen PSTN-Anruf annimmt, wählt die ausgehende Routinglogik im Front-End-Pool aus, welcher trunk über alle möglichen Kombinationen weitergeleitet werden soll, die möglicherweise für das Routing dieses bestimmten Anrufs verfügbar sind. Wenn ein Anruf aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool durch einen DNS-Lastenausgleich nicht erreicht wird, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.

Details zur Planung mehrerer Gateways finden Sie unter [M:N trunk in Skype for Business Server](m-n-trunk.md).

For details about other outbound routing enhancements, see [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Gateway Topologies

When you consider the fundamental questions of gateway deployment, follow these steps:

1. Zählen Sie die Websites, auf denen Sie PSTN-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.

2. Estimate the traffic at each site (number of users and average number of calls per hour per user).

3. Deploy one or more gateways at each site to handle the anticipated traffic.

With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.

Um dieses Problem zu beheben, bevorzugen viele große Unternehmen die Bereitstellung von einem oder wenigen großen zentralen Telefonie-Websites.

In dieser Topologie sind mehrere große Gateways, die für die erwartete Benutzerauslastung ausreichend sind, an jedem zentralen Standort bereitgestellt. All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site. Die Routing Logik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder das PSTN weitergeleitet werden soll.

#### <a name="gateway-location"></a>Gateway Location

Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.

#### <a name="gateway-size-and-number"></a>Gateway Size and Number

The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:

- Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.

- Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.

- Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.

- Additional ports can be acquired as the number of users or amount of traffic in your organization increases.

For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails. 

Jedes von Ihnen bereitgestellte PSTN-Gateway muss mindestens über einen entsprechenden Vermittlungs Server verfügen.


