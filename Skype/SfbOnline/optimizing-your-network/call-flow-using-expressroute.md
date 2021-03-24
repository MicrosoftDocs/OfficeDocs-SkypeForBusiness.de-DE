---
title: Anruffluss mit ExpressRoute
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: In diesem Artikel werden die wichtigsten Grundsätze zum Anruffluss für Skype for Business Online und ExpressRoute mit detaillierten Beispielen für Anrufflüsse erläutert, um Sie bei einer adäquaten Planung zu unterstützen.
ms.openlocfilehash: 968b0a991e89d8c9cfd9ef3e26e2e30806c069b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100731"
---
# <a name="call-flow-using-expressroute"></a>Anruffluss mit ExpressRoute

In diesem Artikel werden die wichtigsten Grundsätze zum Anruffluss für Skype for Business Online und ExpressRoute mit detaillierten Beispielen für Anrufflüsse erläutert, um Sie bei einer adäquaten Planung zu unterstützen.

Wenn Sie Skype for Business Online als Teil von Microsoft 365 oder Office 365, Skype for Business Server Hybrid oder Skype for Business Cloud Connector Edition bereitstellen, müssen Sie die Kommunikation zwischen dem Skype for Business-Client und -Servern und den Anruffluss verstehen, damit Sie Ihre Skype for Business Online-Dienste effektiv planen, bereitstellen, bedienen und Probleme behandeln können.

## <a name="call-flow-overview"></a>Übersicht über Anruffluss

In diesem Dokument werden die Netzwerksegmente beschrieben, die Daten für diese Anrufflüsse übertragen können. Es wird erläutert, welcher Datenverkehr lokal in Ihrem Netzwerk verarbeitet wird und welcher Datenverkehr über das Internet oder über ExpressRoute geleitet wird. Die Kenntnis darüber, welcher Datenverkehr ExpressRoute nutzt, ist für Sie hilfreich bei der Beurteilung der Vorteile, die sich für Ihre Firma durch die Nutzung von ExpressRoute ergeben. Ferner erhalten Sie eine Anleitung zur Bereitstellung von ExpressRoute, damit Sie Ihre Bereitstellung validieren und etwaige Probleme darin behandeln können, nachdem Sie sich für die Nutzung von ExpressRoute entschieden haben.

Die hier beschriebenen Anrufflüsse können durch diverse Faktoren beeinflusst werden, die Sie kontrollieren können. Hierzu gehören beispielsweise Firewall-Regeln, die NAT-Konfiguration, Proxyserver und die Routerkonfiguration. Dieses Dokument basiert auf der Annahme, dass die empfohlenen Einstellungen übernommen wurden. Eine Beschreibung dieser empfohlenen Einstellungen finden Sie in:

- [Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Übersicht über ExpressRoute](/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

Eine vom Einrichtungsverfahren in der oben genannten Dokumentation abweichende Einrichtung und Konfiguration kann dazu führen, dass die Anrufflüsse anders sind als in dieser Dokumentation. Außerdem treten bei Ihnen möglicherweise Konfigurationsprobleme auf, wie zum Beispiel asymmetrische und suboptimale Netzwerkrouten oder suboptimale Transportprotokolle. Das asymmetrische Routing ist im Zusammenhang mit ExpressRoute immer ein wichtiger Aspekt, denn ExpressRoute führt einen zweiten Pfad in Office 365 ein. Dadurch entsteht die Möglichkeit, den Datenverkehr über zwei verschiedene Routen zu leiten: eine Richtung über das Internet und die andere über ExpressRoute. Dies kann dazu führen, dass der zurückfließende Datenverkehr blockiert wird, wenn er auf eine zustandsbehaftete Firewall trifft.

## <a name="network-segments-and-traffic-types"></a>Netzwerksegmente und Arten von Datenverkehr

### <a name="network-segments"></a>Netzwerksegmente

Bevor wir den Anruffluss erläutern können, müssen wir einige Grundbegriffe im Zusammenhang mit den in Skype for Business Online verwendeten Netzwerksegmenten und Arten von Medien definieren.

In den nachfolgenden Anrufflussdiagrammen sehen Sie vier verschiedene Netzwerksegmente. Jedes dieser Segmente wird von einer anderen Organisation verwaltet: Ihrem internen Netzwerk, Ihrem Netzwerkdienstanbieter und dessen Internet-Peering-Partnern sowie Microsoft. Die Segmente weisen jeweils unterschiedliche Leistungsmerkmale auf. Leitlinien für Netzwerkleistungsziele finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance.md).

Unten sehen Sie die einzelnen Netzwerksegmente, die hier erläutert werden sollen.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Ihr Netzwerk** Dies ist das Netzwerksegment in Ihrem Gesamtnetzwerk, das Sie selbst steuern und verwalten. Hierzu gehören alle Verbindungen innerhalb Ihrer Geschäftsräume - verkabelt oder über Funk, zwischen Bürogebäuden, mit lokalen Datencentern - und Ihre Verbindungen mit Internetdienstanbietern oder ExpressRoute-Partnern.

Normalerweise befindet sich am Rand Ihres Netzwerks mindestens eine DMZ mit Firewalls und/oder Proxyservern, die die Sicherheitsrichtlinien Ihrer Organisation durchsetzen und die nur bestimmten Netzwerkdatenverkehr zulassen, den Sie eingerichtet und konfiguriert haben. Da Sie dieses Netzwerk verwalten, haben Sie die direkte Kontrolle über die Leistung Ihres Netzwerks. Es wird dringend empfohlen, die Leistung Ihres Netzwerks sowohl innerhalb der Sites im Netzwerk als auch vom Netzwerk zu Skype for Business Online mithilfe von Netzwerkbewertungen zu validieren. Die Leistungsanforderungen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance.md).

 **Internet** Dies ist das Netzwerksegment innerhalb Ihres Gesamtnetzwerks, das die Benutzer verwenden, wenn sie sich außerhalb des Netzwerks mit Skype for Business Online verbinden. Wenn ExpressRoute nicht konfiguriert ist, wird dieses Segment für alle Verbindungen verwendet. Das Internet und alle Verbindungen darin werden nicht von Ihnen oder von Microsoft verwaltet. Darum können die Leistung und die Routingpfade nicht bestimmt werden. Dies hat die größten Auswirkungen auf den Anruffluss und die Qualität insgesamt.

 **ExpressRoute** Dies ist das Netzwerksegment, das Teil Ihres Gesamtnetzwerks ist und Ihnen eine dedizierte, private Verbindung mit dem Microsoft-Netzwerk bietet. Dies ist die empfohlene Option zum Verbinden Ihres Netzwerks mit dem Microsoft-Netzwerk (Microsoft 365- oder Office 365-Rechenzentren) für alle Workloads, die von der Netzwerkgeschwindigkeit und -leistung abhängig sind, z. B. Skype for Business Online-Echtzeitkommunikation. ExpressRoute-Verbindungen werden zwischen Ihrem Netzwerk [](/azure/expressroute/expressroute-locations) und dem Microsoft-Netzwerk hergestellt und verwenden ExpressRoute-Konnektivitätsanbieter, um ein privates und verwaltetes Netzwerk mit 99,9 % Uptime und Unterstützung für Quality of Service (QoS) zur Verfügung zu stellen, die die Leistung von Echtzeitmedien in Zeiten von Netzwerküberlastung verbessern können.

 **Microsoft-Netzwerk** Dies ist das Netzwerksegment, das Teil Ihres Gesamtnetzwerks ist, das Microsoft 365- und Office 365-Dienste unterstützt. Dies umfasst die kommunikation zwischen Onlineservern für Microsoft 365 oder Office 365. Dies kann Datenverkehr umfassen, der das Rückgrat des Microsoft-Netzwerks durchläuft und zwischen geografischen Regionen übertragen wird.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

Der Netzwerkdatenverkehr für Skype for Business Online lässt sich in zwei Hauptkategorien unterteilen. Diese werden im Anruffluss jeweils als eigener Pfad angezeigt:

 **Echtzeitmedien** sind Daten, die innerhalb von RTP (Real-Time Transport-Protokoll) gekapselt sind und Audio-, Video-, Anwendungsfreigabe- und Dateiübertragungs-Workloads unterstützen. Im Allgemeinen ist der Medienverkehr hochgradig latenzsensitiv. Daher ist es in Ihrem Sinne, wenn dieser Datenverkehr auf einem möglichst direkten Weg übermittelt wird. Aus diesem Grund sollte UDP als Transportschichtprotokoll verwendet werden, weil TCP eine höhere Latenz mit sich bringt.

 **Signalisierung** ist die Kommunikationsverbindung zwischen Client und Server oder mit anderen Clients, die zur Steuerung von Aktivitäten (z. B. wenn ein Anruf initiiert wird) und für die Zustellung von Chatnachrichten verwendet wird. Der Signalisierungsverkehr verwendet überwiegend das SIP-Protokoll. Einige Clients verwenden jedoch HTTP-basierte REST-Schnittstellen. Einfach gesagt, haben wir es bei dieser Art des Datenverkehrs mit diversen Signalisierungen zu tun, die über HTTP- und HTTPS- oder TLS-Verbindungen übermittelt werden können. Ein wichtiger Aspekt ist, dass dieser Datenverkehr wesentlich weniger latenzsensitiv ist. Allerdings kann es zu Dienstausfällen oder zur Unterbrechung von Anrufen wegen Zeitüberschreitungen kommen, wenn die Latenz zwischen den Endpunkten mehrere Sekunden überschreitet.

Die Ziele für diesen Datenverkehr finden Sie in [Office 365-URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) und IP-Adressbereichen für alle Microsoft 365- oder Office 365-Dienste. Für jede URL wird angegeben, ob dieser Teil des Datenverkehrs die ExpressRoute für Microsoft 365 oder Office 365 durchlaufen kann. Diagramme, die zeigen, dass das Internet bei aktivierter ExpressRoute weiterhin für bestimmten Datenverkehr verwendet wird, finden Sie unter [Azure ExpressRoute für Office 365.](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd) Wichtig ist die Erkenntnis, dass selbst URLs, die nominell über ExpressRoute geroutet werden können, auch über das Internet geroutet werden können. Dies bedeutet, dass die Entscheidung, ob das Internet oder ExpressRoute verwendet wird, in einigen Szenarien vom Clientstandort und von der Konfiguration der Proxyserver und Firewalls abhängt. Es ist auch wichtig zu wissen, dass, da nicht alle urLs, die mit Microsoft 365 oder Office 365 verknüpft sind, ExpressRoute verwenden können, eine Internetverbindung erforderlich ist, auch wenn Sie ExpressRoute von einem ExpressRoute-Partner erwerben.

Datenverkehr, der nur über das Internet gesendet werden kann, umfasst allgemeine Internetabhängigkeiten, z. B. Zertifikatsperrlisten (CrLs), DNS-Nachschlage- und Namensauflösung, URLs für freigegebene Microsoft 365- oder Office 365-Dienste, z. B. für das Microsoft 365 Admin Center, und einige Nicht-Echtzeitkommunikationsfunktionen von Skype for Business Online, z. B. Telemetrie und Verbund zur Interoperabilität mit Skype-Consumern. , sowie Medien, die für Skype Meeting Broadcast gestreamt werden. Weitere Überlegungen zur Planung des Netzwerkroutings finden Sie unter Routing mit [ExpressRoute für Office 365.](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="principles-for-call-flows-with-skype-for-business"></a>Grundsätze für Anrufflüsse bei Skype for Business

Bevor wir die spezifischen Anruffluss-Szenarien näher betrachten, sollen hier sechs allgemeine Grundsätze erläutert werden, die für das Verständnis von Anrufflüssen bei Skype for Business wichtig sind.

1. Eine Skype for Business-Konferenz wird in derselben Region gehostet, in der sich auch der Konferenzorganisator befindet. Dies befindet sich in der Cloud, wenn der Organisator ein Onlinebenutzer ist, oder in einem lokalen Rechenzentrum, wenn es sich bei dem Besprechungsorganisator um einen lokalen Benutzer handelt.

2. Der von einem Client in einer gehosteten Konferenz gesendete Medienverkehr fließt immer zu dem Server, auf dem die Konferenz gehostet wird. Dabei kann es sich um einen lokalen Server in einem von Ihnen verwalteten Rechenzentrum oder um einen Onlineserver in der Cloud gehen. Für den Medienfluss für Onlinekonferenzen wird jedoch immer ein Edgeserver verwendet.

3. Der Medienverkehr für Peer-to-Peer-Anrufe wird auf der direktesten verfügbaren Route übermittelt. Die bevorzugte Route geht direkt zum externen Peer (Client). Ist diese Route jedoch aufgrund einer Blockierung des Datenverkehrs durch eine Firewall oder Ähnliches nicht verfügbar, so wird der Datenverkehr über einen oder mehrere Edgeserver übermittelt.

4. Der Signalisierungsverkehr wird immer auf den Server geleitet, auf dem der Benutzer beheimatet ist. Dies kann entweder ein Online-Server oder ein lokaler Server sein. Ein Edgeserver wird verwendet, wenn eine direkte Verbindung mit dem Front-End-Server nicht möglich ist.

5. Benutzer, die an einer online gehosteten Konferenz teilnehmen, verwenden immer einen Edgeserver (oder zwei, sofern dies aufgrund der Client-Firewallkonfigurationen erforderlich ist).

6. Benutzer, die an einer lokal gehosteten Konferenz teilnehmen, nutzen in der Regel keinen Edgeserver, wenn sie die Verbindung von demselben Netzwerk aus herstellen, das auch die lokale Bereitstellung enthält. Benutzer, die die Verbindung von außerhalb Ihres Netzwerks herstellen, nutzen hingegen einen oder zwei Edgeserver.

Nähere Informationen zum gewählten Medienpfad finden Sie unter [ICE - Edge-Medienverbindungen](https://aka.ms/AVEdge). In diesem Video wird Lync Server 2013 behandelt. Die Grundsätze und Protokolle gelten aber auch für Skype for Business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Skype for Business-Anrufflüsse mit ExpressRoute

Sie kennen jetzt die vier verschiedenen Netzwerksegmente und einige allgemeine Grundsätze für Skype for Business-Anrufflüsse. Anhand dieser Informationen können Sie nun nachvollziehen, welcher Skype for Business-Datenverkehr ein ExpressRoute-Netzwerksegment durchläuft.

Im Allgemeinen wird der Netzwerkdatenverkehr über die ExpressRoute-Verbindung geleitet, wenn sich ein Endpunkt in Ihrem Netzwerk und der andere Endpunkt im Microsoft 365- oder Office 365-Rechenzentrum befindet. Dies beinhaltet den Signalisierungsverkehr zwischen Client und Server, den während der Telefonkonferenzen verwendeten Medienverkehr oder Peer-to-Peer-Anrufe, die einen Online-Edgeserver verwenden.

Der Datenverkehr läuft nicht über die ExpressRoute-Verbindung, wenn beide Endpunkte direkt über das Internet miteinander kommunizieren können oder wenn sich beide innerhalb Ihres Netzwerks befinden. Dies umfasst Medien für Peer-zu-Peer-Anrufe, Datenverkehr aus dem Internet, der für eine lokale Bereitstellung bestimmt ist, oder datenverkehr zwischen dem Internet und Microsoft 365- oder Office 365-Edgeservern. Ein Beispiel hierfür ist ein Benutzer, der von einem Hotel aus an einer Onlinekonferenz teilnimmt.

## <a name="basic-skype-for-business-call-flow"></a>Allgemeines zum Skype for Business-Anruffluss

Damit Sie die oben beschriebenen Grundsätze über Skype for Business-Anrufflüsse anwenden können, enthält der nächste Abschnitt in diesem Artikel eine Reihe von Diagrammen als Referenz. Dabei handelt es sich nicht um eine vollständige Liste aller denkbaren Anrufflüsse. Vielmehr sollen Ihnen diese Informationen als Orientierung für die Anwendung der oben beschriebenen Grundsätze dienen. Die Szenarios in den Diagrammen wurden außerdem unter dem Gesichtspunkt ausgewählt, dass sie häufige Bereitstellungstypen abdecken: Online, Hybrid, Cloud Connector und in einem speziellen Fall Skype-Livekonferenz.

> [!NOTE]
> Ein Teil des von Skype for Business genutzten Datenverkehrs kann nicht über ExpressRoute geleitet werden und verwendet daher immer einen Internetpfad. Anhand der Informationen unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) können Sie feststellen, welche URLs betroffen sein können.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Peer-to-Peer-Anruf für Microsoft 365- oder Office 365-Benutzer aus dem Kundennetzwerk
<a name="bk_Figure2"> </a>

Der Medienverkehr für Peer-to-Peer-Anrufe wird immer auf der direktesten verfügbaren Route an das Ziel übermittelt. Der Signalisierungsverkehr wird jedoch an ein Microsoft 365- oder Office 365-Rechenzentrum gesendet, in dem sich der Onlinebenutzer befindet. Da sich beide Benutzer im selben WAN befinden und nichts eine direkte Kommunikation der Clients verhindert, erfolgt der Medienfluss direkt zwischen den beiden. Der Signalisierungsverkehr läuft bei beiden Benutzern über die ExpressRoute-Verbindung, deren Ziel das Rechenzentrum der jeweiligen Organisation ist. Die folgende Darstellung zeigt den Anruffluss in diesem Szenario.

 **Peer-to-Peer-Anruffluss**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt
<a name="bk_Figure3"> </a>

Im Peer-to-Peer-Beispiel führt der Mediendatenverkehr immer die direkteste Route zum Ziel. Für eine Onlinekonferenz befindet sich das Ziel jedoch in der Cloud. Dies bedeutet, dass der Mediendatenverkehr für alle Benutzer, die von ihrem Netzwerk aus an der Konferenz teilnehmen, die ExpressRoute-Verbindung durchläuft und der Signaldatenverkehr in die Cloud führt. Die folgende Grafik zeigt, dass sowohl Medien als auch Signalisierung die ExpressRoute-Verbindung für einen Benutzer innerhalb Ihres Netzwerks durchlaufen und das Internet für Benutzer, die von außerhalb Ihres Netzwerks mit dem Internet verbunden sind, direkt durchlaufen, z. B. von einem Café oder Hotel aus.

Wichtig ist, dass sich der Standort einer Konferenz nach dem Besprechungsorganisator richtet und nicht nach den Teilnehmern. Dies bedeutet: Wenn die Besprechung von einem lokalen Kunden geplant wurde, fließt der Mediendatenverkehr nicht über ExpressRoute in die Cloud, sondern über das Internet zum lokalen Rechenzentrum des Besprechungsorganisators.

Das Ziel für Medien für Onlinekonferenzen ist ein Rechenzentrum in der Microsoft 365- oder Office 365-Cloud, aber das Rechenzentrum befindet sich möglicherweise in einer anderen geografischen Region als die Benutzer, die an der Konferenz teilnehmen. Dies kann auf eine von zwei Arten erfolgen:

- Wenn der Besprechungsorganisator in einem anderen Unternehmen tätig ist als die Teilnehmer und die Organisation für den Organisator an einem anderen geografischen Standort oder in einem anderen Land bzw. einer anderen Region gehostet wird.

- Wenn sich ein Benutzer aus einem anderen Land bzw. einer anderen Region teilnimmt als dem Land bzw. der Region, wo sich der Standort der Organisation des Unternehmens befindet. Dies kann der Fall sein, wenn das Unternehmen multinational ist oder wenn der Benutzer auf Reisen ist.

Das Gute an der Verwendung von ExpressRoute in diesem Szenario ist, dass Daten, die dem ExpressRoute-Pfad folgen, mit dem ExpressRoute Premium-Add-On automatisch über den Backbone von Microsoft zum Datencenter der Organisation der Besprechung geleitet werden. Die geografische Region des Organisators spielt dabei keine Rolle.

 **Anruffluss bei Online-Benutzer in Onlinebesprechung**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Teilnahme an einer Konferenz, die von einem lokalen Benutzer in einer Hybrid-Bereitstellung gehostet wird
<a name="bk_Figure3"> </a>

Denken Sie daran, dass die Konferenzserver, die gehostete Konferenzen unterstützen, davon bestimmt werden, wo sich der Besprechungsorganisator befindet. In diesem Szenario fließen Medien für alle Benutzer, die an einer von einem lokalen Benutzer geplanten Konferenz in einer Hybridbereitstellung teilnehmen, in ein lokales Rechenzentrum. Die Signalisierung für heime Onlinebenutzer wird über ihre Organisation in der Cloud eingerichtet, während medien eine direkte Verbindung versuchen. Da in diesem Szenario beide Benutzer eine Verbindung von ihrem Netzwerk aus herstellen, ist eine direkte Medienverbindung möglich, sodass ExpressRoute nur zum Signalisieren des Datenverkehrs für den Online-Homed-Benutzer verwendet wird. Wenn ein Online-Homed-Benutzer eine Verbindung über das Internet herstellt, können die Medien ExpressRoute durchlaufen, wenn ein Online-Edgeserver zum Herstellen einer Verbindung verwendet wird.

 **Anruffluss bei einer von einem Hybrid-Benutzer gehosteten Konferenz**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Lokalen Edgeserver mit von Microsoft 365 oder Office 365 gehosteten Konferenzen
<a name="bk_Figure5"> </a>

Wenn ein Hybridbenutzer an einer von Online gehosteten Konferenz teilnachtet, wissen wir, dass Signalisierung und Medien für die Microsoft 365- oder Office 365-Cloud bestimmt sind, und da der Benutzer aus dem Internet beitritt, würde normalerweise ein direkter Internetpfad verwendet. In einigen Fällen, z. B. aufgrund von Firewalleinschränkungen, ist jedoch kein direkter Internetpfad verfügbar. In diesem Fall kann ein lokales Edgeserver den Mediendatenverkehr weiterleiten, wodurch der Mediendatenverkehr zu Ihrem lokalen Netzwerk zurückzukehren, bevor der ExpressRoute-Schaltkreis in die Cloud übertragen wird.

 **Lokale Benutzer, die von einem lokalen Edgeserver aus an einer Online-Telekonferenz teilnehmen**

![Anruffluss für eine Telefonkonferenz, die über einen Edgeserver läuft.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>PSTN-Anruf mit Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Die [Verwendung](https://aka.ms/CloudConnectorInstaller) der Skype for Business Online Cloud Connector Edition stellt eine PSTN-Konnektivität mithilfe von lokalen Ressourcen wie einem SIP-Trunk oder einem PSTN-Gateway oder mit einem minimalen Hardwaregerät zur Integration in Skype for Business zur Verfügung. Mit Cloud Connector Edition sind Benutzer online heimisiert und fungieren als normale Onlinebenutzer, wenn sie keine Anrufpläne beinhalten. Die Signalisierung für PSTN-Szenarien wird zwischen Client und Cloud über eine ExpressRoute-Verbindung ausgeführt, sofern verfügbar, und der Mediendatenverkehr bleibt in Ihrem WAN erhalten. In diesem Fall dreht sich die Signalisierung in der Microsoft 365- oder Office 365-Cloud und endet am Cloud Connector.

 **ANRUFE über das Telefonsystem in Microsoft 365 oder Office 365 und Cloud Connector**

![Anruffluss für einen PSTN-Anruf mit Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype-Livekonferenz mit Benutzern, die von einem Kundennetzwerk aus teilnehmen
<a name="bk_Figure6"> </a>

Skype Meeting Broadcast ist ein spezieller Einsatzfall, der aus einer zweigeteilten Besprechung mit jedem Teil mit unterschiedlichen Netzwerktransportprofilen besteht. Der erste Und der aus Sicht der Netzwerkleistung wichtigste Teil ist die innere Besprechung. Dies ist der Echtzeitteil der Besprechung, der einen oder mehrere Clientendpunkte umfasst, die eine Verbindung mit dem Konferenzserver in der Cloud herstellen. Daten, die mithilfe dieses Teils der Besprechung übertragen werden, sind genau wie im obigen Beispiel, wenn ein Benutzer an einer Onlinekonferenz teiln.

Das Besondere an einer Skype-Livekonferenz ist die Tatsache, dass die Konferenz über einen Streamingübertragungsdienst an eine große Zahl von Konferenzteilnehmern verteilt wird. Dieser Streamingübertragungsdienst kann nicht über ExpressRoute geleitet werden. Stattdessen nutzt er das Internet mit der optionalen Unterstützung von Content Delivery Network-Diensten (CDN). Es ist hilfreich, sich klar zu machen, dass die Streamingübertragung ein unidirektionaler Medienfluss ist, denn die Teilnehmer hören zu, sprechen aber selbst nicht. Die Pufferung wird dabei unterstützt. Somit ist diese Form der Übertragung wesentlich weniger sensitiv gegenüber Problemen bei der Netzwerkleistung wie Latenz, Paketverlust und Jitter. Statt den Übertragungsdatenverkehr für diese Probleme zu optimieren, wird dieser für die Bandbreitennutzung optimiert, weil potenziell eine sehr große Zahl an Teilnehmern die gestreamten Medien empfängt.

 **Skype-Livekonferenz mit Benutzern aus einem Kundennetzwerk**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Anrufflussmuster nach Entwicklungstyp

Anhand der oben angeführten Beispiele für häufig auftretende Anrufflüsse wurden die allgemeinen Grundsätze erläutert, die die Datenverkehrsmuster steuern. Die nachfolgenden Tabellen enthalten eine Übersicht über die Datenverkehrsmuster für eine große Kombination von Bereitstellungs- und Benutzerszenarien. Diese Tabellen erfassen nicht jede mögliche Kombination von Anrufflüssen. Sie können aber hilfreich sein, um die allgemeinen Grundsätze bei Anrufflüssen nachzuvollziehen.

Die Daten werden übermittelt und aufgeführt, als seien sie für die Organisation lokal. Sie verlassen das Kundennetzwerk, das Internet oder ExpressRoute dabei nicht. Die nachfolgend aufgeführten Muster basieren auf den häufigsten Netzwerkeinstellungen. Hierzu gehören beispielsweise Firewalls, Partnerverbund und Internet. Dabei wird von der Annahme ausgegangen, dass alle Organisationen, die an Anrufflüssen mit mehreren Parteien oder mit Partnerverbunden beteiligt sind, ExpressRoute haben. In der Praxis könnte das Vorhandensein unterschiedlicher Einstellungen zu Datenverkehrsmustern führen, die von den nachfolgend aufgeführten Mustern abweichen.

### <a name="call-flows-for-skype-for-business-online"></a>Anrufflüsse bei Skype for Business Online

Skype for Business Online-Nutzungsszenarien umfassen Benutzer, die online zu Hause sind und möglicherweise über Ihr internes Netzwerk oder das Internet anrufen. Lokale Server sind nicht Teil dieser Szenarien, daher fließen alle Konferenz- oder PSTN-bezogenen Medien in die Cloud, und der Edgeserver der Onlinebenutzer wird ebenfalls in der Cloud gespeichert.

 **Anrufflusszusammenfassung für Skype for Business Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Hinweise** <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, beide im Netzwerk.  <br/> |ExpressRoute  <br/> |Lokal  <br/> |[Peer-to-Peer-Anruf für Microsoft 365- oder Office 365-Benutzer aus dem Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, einer in Ihrem Netzwerk (intern) und der andere Client im Internet (extern).  <br/> |Interner Benutzer: ExpressRoute  <br/> Externer Benutzer: Internet  <br/> |Interner Benutzer: ExpressRoute  <br/> Externer Benutzer: Internet mit Microsoft 365- oder Office 365 Edgeserver.  <br/> |[Peer-to-Peer-Anruf für Microsoft 365- oder Office 365-Benutzer aus dem Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Es wird davon ausgegangen, dass die Firewall direkte Verbindungen zwischen Clients blockiert, was einen Online edge-Server erfordert. Der Datenverkehr vom internen Benutzer zum Online Edge-Server folgt einem ähnlichen Pfad wie dem des Konferenzservers für Telefonkonferenzen.  <br/> |
|Peer-to-Peer-Aufruf eines Benutzers in einer Verbundorganisation  <br/> |Zwei Clients in Ihrem Netzwerk (intern) und bei Onlinebenutzern im Netzwerk der Verbundorganisation (Verbund).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer Konferenz teiln beitritt, die online gehostet wird](call-flow-using-expressroute.md#bk_Figure3) <br/> |Es wird davon ausgegangen, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, was einen Online edge-Server erfordert. Der Datenverkehr vom internen Benutzer zum Online Edge-Server folgt einem ähnlichen Pfad wie der eines Konferenzservers für Telefonkonferenzen.  <br/> |
|Teilnehmen an einer Telefonkonferenz nach Benutzer im Kundennetzwerk  <br/> |Client in Ihrem Netzwerk und Konferenzserver in der Cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer Konferenz teiln beitritt, die online gehostet wird](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnehmen an einer Telefonkonferenz nach Benutzer im Internet  <br/> |Der Client befindet sich im Internet und konferenzserver in der Cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer Konferenz teiln beitritt, die online gehostet wird](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnehmen an einer Konferenz, die vom on-prem Server eines anderen Unternehmens gehostet wird  <br/> |Client in Ihrem Netzwerk und Konferenzserver im Rechenzentrum von Drittanbietern.  <br/> |Internet  <br/> |Internet  <br/> |Nicht zutreffend  <br/> |Da sich der Konferenzserver, der die Konferenz hostet, in einem lokalen Netzwerk eines anderen Kunden befindet, würden keine Daten über die Microsoft-Cloud übertragen.  <br/> |
|PSTN-Anruf  <br/> |Client in Kundennetzwerk- und Telefonsystemservern in der Cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer Konferenz teiln beitritt, die online gehostet wird](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN-Anruf  <br/> |Client im Internet und Telefonsystemserver in der Cloud  <br/> |Internet  <br/> |Internet  <br/> |Nicht zutreffend  <br/> |Die Medien und Signale fließen in das Microsoft 365- oder Office 365-Rechenzentrum. Da sich der Clientendpunkt im Internet befindet, fließen alle Daten über das Internet in das Microsoft-Rechenzentrum (auch wenn für die Konnektivität ein Online-Edge-Server erforderlich ist).  <br/> |

> [!NOTE]
> ExpressRoute wird auf dem Medienpfad von einem Benutzer im Unternehmensnetzwerk zu einem Online-Edgeserver verwendet, wird aber nicht verwendet, wenn der Edgeserver für die lokale Bereitstellung eines anderen Kunden verwendet wird.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Anrufflüsse für Skype for Business Hybrid

Hybridanrufflüsse gelten, wenn Sie über eine Skype for Business-Bereitstellung verfügen, die mindestens einige Benutzer umfasst, die lokal zu Hause sind. Die Anrufflüsse in diesem Abschnitt umfassen sowohl lokale Konferenzen als auch Peer-zu-Peer- oder PSTN-Anrufe mit mindestens einem lokalen heimischen Benutzer.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Hinweise** <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, sowohl im Kundennetzwerk als auch lokal zuhause  <br/> |Local  <br/> |Lokal  <br/> |[Peer-to-Peer-Anruf für Microsoft 365- oder Office 365-Benutzer aus dem Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Da Benutzer lokal gehostet werden, fließt die Signalisierung lokal an das lokale Rechenzentrum und nicht an die Cloud.  <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, die beide über das Kundennetzwerk verbunden sind. Eine ist online zuhause, die andere lokal.  <br/> |Onlinebenutzer: ExpressRoute  <br/> Lokaler Benutzer: lokal  <br/> |Lokal  <br/> |[Peer-to-Peer-Anruf für Microsoft 365- oder Office 365-Benutzer aus dem Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Nur der Online-Homed-Benutzer sendet Signalisierungsdatenverkehr an die Cloud.  <br/> |
|Peer-to-Peer-Aufruf eines Benutzers in einer Verbundorganisation  <br/> |Zwei Clients, Lokalbenutzer im Kundennetzwerk (intern) und Onlinebenutzer im Netzwerk des Verbundunternehmens (Federated).  <br/> |Interner Benutzer: lokal  <br/> Verbundbenutzer: ExpressRoute  <br/> |Internet oder ExpressRoute (hängt davon ab, ob online oder lokal edge server verwendet wird)  <br/> |[Onlinebenutzer in Ihrem](call-flow-using-expressroute.md#bk_Figure3) Netzwerk, der an einer Konferenz teilt, die online gehostet wird und teil des lokalen Edgeservers mit [von Microsoft 365 oder Office 365](call-flow-using-expressroute.md#bk_Figure5) gehosteten Konferenzen (für Mediendatenverkehr) ist. <br/> |Es wird davon ausgegangen, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, was einen Online edge-Server erfordert. Die ICE-Aushandlung bietet sowohl Onlineserver (vom Onlinebenutzer) als auch lokale Edgeserver (vom lokalen Benutzer) für die Konnektivität an.  <br/> |
|Teilnehmen an einer Telefonkonferenz nach Benutzer im Kundennetzwerk (von Onlinebenutzern geplante Konferenz)  <br/> |Lokale Benutzer in Ihrem Netzwerk und Konferenzserver in der Cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer Konferenz teiln beitritt, die online gehostet wird](call-flow-using-expressroute.md#bk_Figure3) <br/> |Serverressourcen für Telefonkonferenzen werden vom Besprechungsorganisator definiert. In diesem Fall wurde sie von einem Onlinebenutzer geplant, sodass sich Ressourcen in der Cloud befinden.  <br/> |
|PSTN-Anruf  <br/> |Lokale Benutzer in Ihrem Netzwerk und lokales Skype for Business-Rechenzentrum.  <br/> |Local  <br/> |Local  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Ein ähnliches Szenario wie die Verwendung von Cloud Connector Edition, mit der Ausnahme, dass der Benutzer lokal heimisiert ist, sodass die Signalisierung in Ihrem Netzwerk bleibt.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Anrufflüsse für Skype for Business mit Cloud Connector

Benutzer, die eine Verbindung mit Cloud Connector Edition herstellen, sind alle online homed. Dies bedeutet, dass Konferenzen online sind, und die Signalisierung folgt den gleichen Mustern wie für Onlinebenutzer. Bei anderen Szenarien als PSTN-Anrufen wird der Anruffluss genau wie oben für Skype for Business Online beschrieben.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Hinweise** <br/> |
|PSTN-Anruf  <br/> |Onlinebenutzer in Ihrem Netzwerk mit Cloud Connector Edition.  <br/> |Lokal  <br/> |Lokal  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN-Anruf  <br/> |Onlinebenutzer, der das Internet mit Cloud Connector Edition verwendet.  <br/> |Internet  <br/> |Internet  <br/> |Kombination aus [lokalem Edgeserver mit von Microsoft 365 oder Office 365](call-flow-using-expressroute.md#bk_Figure5) gehosteten Konferenzen und [PSTN-Anrufen](call-flow-using-expressroute.md#bk_Figure6)mit Skype for Business Cloud Connector Edition .  <br/> |Internetbenutzer stellen eine Verbindung über den Edgeserver, der in Cloud Connector enthalten ist, und Cloud Connector wird eine Verbindung mit dem PSTN-Netzwerk herstellen.  <br/> |

## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute-Dokumentation](/azure/expressroute/)