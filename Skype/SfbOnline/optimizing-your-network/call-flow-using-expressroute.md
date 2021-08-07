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
ms.openlocfilehash: 098949c41430bc939197a21373489b1aaa10c1678943d0ee695cd7ade02be142
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304637"
---
# <a name="call-flow-using-expressroute"></a>Anruffluss mit ExpressRoute

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Artikel werden die wichtigsten Grundsätze zum Anruffluss für Skype for Business Online und ExpressRoute mit detaillierten Beispielen für Anrufflüsse erläutert, um Sie bei einer adäquaten Planung zu unterstützen.

Wenn Sie Skype for Business Online als Teil von Microsoft 365 oder Office 365, Skype for Business Server Hybrid oder Skype for Business Cloud Connector Edition bereitstellen, müssen Sie die Kommunikation zwischen dem Skype for Business-Client und den Servern und den Anruffluss verstehen, damit Sie Ihre Skype for Business-Onlinedienste effektiv planen, bereitstellen, betreiben und Probleme behandeln können.

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

 **ExpressRoute** Dies ist das Netzwerksegment in Ihrem Gesamtnetzwerk, das Ihnen eine dedizierte private Verbindung mit dem Microsoft-Netzwerk bietet. Dies ist die empfohlene Option zum Verbinden Ihres Netzwerks mit dem Microsoft-Netzwerk (Microsoft 365- oder Office 365-Rechenzentren) für alle Workloads, die von der Netzwerkgeschwindigkeit und -leistung abhängen, z. B. Skype for Business Online-Echtzeitkommunikation. ExpressRoute-Verbindungen werden zwischen Ihrem Netzwerk [](/azure/expressroute/expressroute-locations) und dem Microsoft-Netzwerk hergestellt. Verwenden Sie ExpressRoute-Konnektivitätsanbieter, um ein privates und verwaltetes Netzwerk mit einer Nutzungszeit von 99,9 % und Unterstützung für Quality of Service (QoS) zur Verfügung zu stellen, die die Leistung von Echtzeitmedien in Zeiten einer Netzwerküberlastung verbessern können.

 **Microsoft-Netzwerk** Dies ist das Netzwerksegment in Ihrem Gesamtnetzwerk, das Microsoft 365 und Office 365 unterstützt. Dazu gehört die sämtliche Kommunikation zwischen Onlineservern für Microsoft 365 oder Office 365. Dies kann Datenverkehr umfassen, der das Backbone des Microsoft-Netzwerks durchläuft und zwischen geografischen Regionen übertragen wird.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

Der Netzwerkdatenverkehr für Skype for Business Online lässt sich in zwei Hauptkategorien unterteilen. Diese werden im Anruffluss jeweils als eigener Pfad angezeigt:

 **Echtzeitmedien** sind Daten, die innerhalb von RTP (Real-Time Transport-Protokoll) gekapselt sind und Audio-, Video-, Anwendungsfreigabe- und Dateiübertragungs-Workloads unterstützen. Im Allgemeinen ist der Medienverkehr hochgradig latenzsensitiv. Daher ist es in Ihrem Sinne, wenn dieser Datenverkehr auf einem möglichst direkten Weg übermittelt wird. Aus diesem Grund sollte UDP als Transportschichtprotokoll verwendet werden, weil TCP eine höhere Latenz mit sich bringt.

 **Signalisierung** ist die Kommunikationsverbindung zwischen Client und Server oder mit anderen Clients, die zur Steuerung von Aktivitäten (z. B. wenn ein Anruf initiiert wird) und für die Zustellung von Chatnachrichten verwendet wird. Der Signalisierungsverkehr verwendet überwiegend das SIP-Protokoll. Einige Clients verwenden jedoch HTTP-basierte REST-Schnittstellen. Einfach gesagt, haben wir es bei dieser Art des Datenverkehrs mit diversen Signalisierungen zu tun, die über HTTP- und HTTPS- oder TLS-Verbindungen übermittelt werden können. Ein wichtiger Aspekt ist, dass dieser Datenverkehr wesentlich weniger latenzsensitiv ist. Allerdings kann es zu Dienstausfällen oder zur Unterbrechung von Anrufen wegen Zeitüberschreitungen kommen, wenn die Latenz zwischen den Endpunkten mehrere Sekunden überschreitet.

Die Ziele für diesen Datenverkehr finden Sie in Office 365 [URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) und IP-Adressbereichen für alle Microsoft 365 oder Office 365 Dienste. Für jede URL gibt sie an, ob dieser Teil des Datenverkehrs das ExpressRoute für die Microsoft 365 oder Office 365. Diagramme, die zeigen, dass das Internet noch für bestimmten Datenverkehr verwendet wird, wenn ExpressRoute aktiviert ist, finden Sie unter [Azure ExpressRoute für Office 365.](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd) Wichtig ist die Erkenntnis, dass selbst URLs, die nominell über ExpressRoute geroutet werden können, auch über das Internet geroutet werden können. Dies bedeutet, dass die Entscheidung, ob das Internet oder ExpressRoute verwendet wird, in einigen Szenarien vom Clientstandort und von der Konfiguration der Proxyserver und Firewalls abhängt. Außerdem ist es wichtig zu wissen, dass eine Internetverbindung erforderlich ist, auch wenn Sie ExpressRoute von einem ExpressRoute-Partner erwerben, da nicht alle mit Microsoft 365 oder Office 365 verbundenen URLs ExpressRoute verwenden können.

Datenverkehr, der nur über das Internet gesendet werden kann, umfasst allgemeine Internetabhängigkeiten, z. B. CRLs (Certificate Revocation Lists), DNS-Suchfunktionen und Namensauflösung, URLs für freigegebene Microsoft 365- oder Office 365-Dienste wie für die Microsoft 365 Admin Center und einige Features der nicht-Echtzeitkommunikation von Skype for Business Online, z. B. Telemetrie und Verbund für die Interoperabilität mit Skype-Consumer sowie Medien, die für Skype-Besprechung Broadcast gestreamt werden. Weitere Überlegungen bei der Planung des Netzwerkroutings finden Sie Office 365 Routing mit [ExpressRoute.](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="principles-for-call-flows-with-skype-for-business"></a>Grundsätze für Anrufflüsse bei Skype for Business

Bevor wir die spezifischen Anruffluss-Szenarien näher betrachten, sollen hier sechs allgemeine Grundsätze erläutert werden, die für das Verständnis von Anrufflüssen bei Skype for Business wichtig sind.

1. Eine Skype for Business Konferenz wird in derselben Region gehostet, in der auch der Organisator der Konferenz gehostet wird. Dies befindet sich in der Cloud, wenn es sich bei dem Organisator um einen Onlinebenutzer handelt, oder in einem lokalen Rechenzentrum, wenn es sich bei dem Besprechungsorganisator um einen lokalen Benutzer handelt.

2. Der von einem Client in einer gehosteten Konferenz gesendete Medienverkehr fließt immer zu dem Server, auf dem die Konferenz gehostet wird. Dabei kann es sich um einen lokalen Server in einem von Ihnen verwalteten Rechenzentrum oder um einen Onlineserver in der Cloud sein. Für den Medienfluss für Onlinekonferenzen wird jedoch immer ein Edgeserver verwendet.

3. Der Medienverkehr für Peer-to-Peer-Anrufe wird auf der direktesten verfügbaren Route übermittelt. Die bevorzugte Route geht direkt zum externen Peer (Client). Ist diese Route jedoch aufgrund einer Blockierung des Datenverkehrs durch eine Firewall oder Ähnliches nicht verfügbar, so wird der Datenverkehr über einen oder mehrere Edgeserver übermittelt.

4. Der Signalisierungsverkehr wird immer auf den Server geleitet, auf dem der Benutzer beheimatet ist. Dies kann entweder ein Online-Server oder ein lokaler Server sein. Ein Edgeserver wird verwendet, wenn eine direkte Verbindung mit dem Front-End-Server nicht möglich ist.

5. Benutzer, die an einer online gehosteten Konferenz teilnehmen, verwenden immer einen Edgeserver (oder zwei, sofern dies aufgrund der Client-Firewallkonfigurationen erforderlich ist).

6. Benutzer, die an einer lokal gehosteten Konferenz teilnehmen, nutzen in der Regel keinen Edgeserver, wenn sie die Verbindung von demselben Netzwerk aus herstellen, das auch die lokale Bereitstellung enthält. Benutzer, die die Verbindung von außerhalb Ihres Netzwerks herstellen, nutzen hingegen einen oder zwei Edgeserver.

Nähere Informationen zum gewählten Medienpfad finden Sie unter [ICE - Edge-Medienverbindungen](https://aka.ms/AVEdge). In diesem Video wird Lync Server 2013 behandelt. Die Grundsätze und Protokolle gelten aber auch für Skype for Business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Skype for Business-Anrufflüsse mit ExpressRoute

Sie kennen jetzt die vier verschiedenen Netzwerksegmente und einige allgemeine Grundsätze für Skype for Business-Anrufflüsse. Anhand dieser Informationen können Sie nun nachvollziehen, welcher Skype for Business-Datenverkehr ein ExpressRoute-Netzwerksegment durchläuft.

Im Allgemeinen durchläuft Netzwerkdatenverkehr die ExpressRoute-Verbindung, wenn sich ein Endpunkt in Ihrem Netzwerk und der andere Endpunkt im rechenzentrum Microsoft 365 oder Office 365 befindet. Dies beinhaltet den Signalisierungsverkehr zwischen Client und Server, den während der Telefonkonferenzen verwendeten Medienverkehr oder Peer-to-Peer-Anrufe, die einen Online-Edgeserver verwenden.

Der Datenverkehr läuft nicht über die ExpressRoute-Verbindung, wenn beide Endpunkte direkt über das Internet miteinander kommunizieren können oder wenn sich beide innerhalb Ihres Netzwerks befinden. Dies umfasst Medien für Peer-zu-Peer-Anrufe, Datenverkehr aus dem Internet, der an eine lokale Bereitstellung bestimmt ist, oder jeglichen Datenverkehr zwischen dem Internet und Microsoft 365 oder Office 365 Edgeservern. Ein Beispiel hierfür ist ein Benutzer, der von einem Hotel aus an einer Onlinekonferenz teilnimmt.

## <a name="basic-skype-for-business-call-flow"></a>Allgemeines zum Skype for Business-Anruffluss

Damit Sie die oben beschriebenen Grundsätze über Skype for Business-Anrufflüsse anwenden können, enthält der nächste Abschnitt in diesem Artikel eine Reihe von Diagrammen als Referenz. Dabei handelt es sich nicht um eine vollständige Liste aller denkbaren Anrufflüsse. Vielmehr sollen Ihnen diese Informationen als Orientierung für die Anwendung der oben beschriebenen Grundsätze dienen. Die Szenarios in den Diagrammen wurden außerdem unter dem Gesichtspunkt ausgewählt, dass sie häufige Bereitstellungstypen abdecken: Online, Hybrid, Cloud Connector und in einem speziellen Fall Skype-Livekonferenz.

> [!NOTE]
> Ein Teil des von Skype for Business genutzten Datenverkehrs kann nicht über ExpressRoute geleitet werden und verwendet daher immer einen Internetpfad. Anhand der Informationen unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) können Sie feststellen, welche URLs betroffen sein können.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Peer-to-Peer-Anruf für Microsoft 365 oder Office 365 innerhalb des Kundennetzwerks
<a name="bk_Figure2"> </a>

Der Medienverkehr für Peer-to-Peer-Anrufe wird immer auf der direktesten verfügbaren Route an das Ziel übermittelt. Der Signalisierungsverkehr wird jedoch an ein Rechenzentrum Microsoft 365 oder Office 365, in dem der Onlinebenutzer gehostet wird. Da sich beide Benutzer im selben WAN befinden und nichts eine direkte Kommunikation der Clients verhindert, erfolgt der Medienfluss direkt zwischen den beiden. Der Signalisierungsverkehr läuft bei beiden Benutzern über die ExpressRoute-Verbindung, deren Ziel das Rechenzentrum der jeweiligen Organisation ist. Die folgende Darstellung zeigt den Anruffluss in diesem Szenario.

 **Peer-to-Peer-Anruffluss**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt
<a name="bk_Figure3"> </a>

Im Peer-to-Peer-Beispiel geht der Medienverkehr immer über die direkteste Route an das Ziel. Bei einer Onlinekonferenz befindet sich das Ziel jedoch in der Cloud. Dies bedeutet, dass der Medienverkehr für alle Benutzer, die von innerhalb Ihres Netzwerks an der Konferenz teilnehmen, die ExpressRoute-Verbindung durchläuft und der Signalisierungsverkehr zur Cloud führt. Die folgende Abbildung zeigt, dass sowohl Medien als auch Signalisierung die ExpressRoute-Verbindung für einen Benutzer innerhalb Ihres Netzwerks durchlaufen und das Internet für Benutzer, die von außerhalb Ihres Netzwerks mit dem Internet verbunden sind( z. B. aus einem Café oder Hotel), direkt durchläuft.

Wichtig ist, dass sich der Standort einer Konferenz nach dem Besprechungsorganisator richtet und nicht nach den Teilnehmern. Dies bedeutet: Wenn die Besprechung von einem lokalen Kunden geplant wird, fließt der Medienverkehr nicht über ExpressRoute zur Cloud, sondern durchläuft stattdessen das Internet zum lokalen Rechenzentrum des Besprechungsorganisators.

Ziel für Medien für Onlinekonferenzen ist ein Rechenzentrum innerhalb der Microsoft 365- oder Office 365-Cloud, das Rechenzentrum kann sich jedoch in einer anderen geografischen Region befinden als die Benutzer, die der Konferenz beitreten. Dies kann auf eine von zwei Arten geschehen:

- Wenn der Besprechungsorganisator in einem anderen Unternehmen tätig ist als die Teilnehmer und die Organisation für den Organisator an einem anderen geografischen Standort oder in einem anderen Land bzw. einer anderen Region gehostet wird.

- Wenn sich ein Benutzer aus einem anderen Land bzw. einer anderen Region teilnimmt als dem Land bzw. der Region, wo sich der Standort der Organisation des Unternehmens befindet. Dies kann der Fall sein, wenn das Unternehmen multinational ist oder wenn der Benutzer auf Reisen ist.

Das Gute an der Verwendung von ExpressRoute in diesem Szenario ist, dass Daten, die dem ExpressRoute-Pfad folgen, mit dem ExpressRoute Premium-Add-On automatisch über den Backbone von Microsoft zum Datencenter der Organisation der Besprechung geleitet werden. Die geografische Region des Organisators spielt dabei keine Rolle.

 **Anruffluss bei Online-Benutzer in Onlinebesprechung**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Teilnahme an einer Konferenz, die von einem lokalen Benutzer in einer Hybrid-Bereitstellung gehostet wird
<a name="bk_Figure3"> </a>

Denken Sie daran, dass die Konferenzserver, die gehostete Konferenzen unterstützen, davon bestimmt werden, wo der Besprechungsorganisator gehostet wird. In diesem Szenario werden Medien für alle Benutzer, die an einer von einem lokalen Benutzer in einer Hybridbereitstellung geplanten Konferenz teilnehmen, an ein lokales Rechenzentrum fließen. Die Signalisierung für benutzer, die über die Online-Startseite verfügen, wird über ihre Organisation in der Cloud eingerichtet, während die Medien eine direkte Verbindung versuchen. Da in diesem Szenario beide Benutzer eine Verbindung innerhalb Ihres Netzwerks herstellen, ist eine direkte Medienverbindung möglich, sodass ExpressRoute nur zum Signalisieren des Datenverkehrs für den Online-Homed-Benutzer verwendet wird. Wenn ein online gespeicherter Benutzer eine Verbindung über das Internet herstellt, können die Medien ExpressRoute durchlaufen, wenn ein Online-Edgeserver zum Herstellen einer Verbindung verwendet wird.

 **Anruffluss bei einer von einem Hybrid-Benutzer gehosteten Konferenz**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Lokales Edgeserver mit Microsoft 365 oder Office 365 gehosteten Konferenzen
<a name="bk_Figure5"> </a>

Wenn ein Hybridbenutzer einer online gehosteten Konferenz beitritt, wissen wir, dass Signalisierung und Medien für die Microsoft 365- oder Office 365-Cloud bestimmt sind, und da der Benutzer über das Internet beitritt, wird normalerweise ein direkter Internetpfad verwendet. In einigen Fällen, z. B. aufgrund von Firewalleinschränkungen, ist jedoch kein direkter Internetpfad verfügbar. In diesem Fall kann ein lokales Edgeserver den Medienverkehr weiterleiten. Dadurch wird der Medienverkehr zu Ihrem lokalen Netzwerk zurückkehren, bevor der ExpressRoute-Schaltkreis in die Cloud durchlaufen wird.

 **Lokale Benutzer, die von einem lokalen Edgeserver aus an einer Online-Telekonferenz teilnehmen**

![Anruffluss für eine Telefonkonferenz, die über einen Edgeserver läuft.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>PSTN-Anruf mit Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Die [Verwendung](https://aka.ms/CloudConnectorInstaller) von Skype for Business Online Cloud Connector Edition ermöglicht PSTN-Konnektivität mithilfe von lokalen Ressourcen wie einem SIP-Trunk oder einem PSTN-Gateway oder der Verwendung eines minimalen Hardwaregeräts für die Integration mit Skype for Business. Mit Cloud Connector Edition sind Die Benutzer online heimisiert und fungieren als normale Onlinebenutzer, wenn sie keine Anrufpläne nutzen. Signalisierungen für PSTN-Szenarien werden zwischen dem Client und der Cloud über eine ExpressRoute-Verbindung (falls verfügbar) gesendet, und der Medienverkehr bleibt in Ihrem WAN. In diesem Fall dreht sich die Signalisierung in der Microsoft 365 oder Office 365 Cloud und endet mit Cloud Connector.

 **PSTN-Anruf über Telefonsystem in Microsoft 365 oder Office 365 und Cloud Connector**

![Anruffluss für einen PSTN-Anruf mit Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype-Livekonferenz mit Benutzern, die von einem Kundennetzwerk aus teilnehmen
<a name="bk_Figure6"> </a>

Skype-Besprechung Übertragung ist ein Sonderfall, der aus einer zweigeteilten Besprechung besteht, bei der jeder Teil unterschiedliche Netzwerktransportprofile hat. Der erste Teil, und der aus Sicht der Netzwerkleistung am wichtigsten ist, ist die innere Besprechung. Dies ist der Echtzeitteil der Besprechung, der einen oder mehrere Clientendpunkte umfasst, die eine Verbindung mit dem Konferenzserver in der Cloud herstellen. Daten, die mithilfe dieses Teils der Besprechung übertragen werden, sind genau wie das Beispiel oben, in dem ein Benutzer einer Onlinekonferenz beitritt.

Das Besondere an einer Skype-Livekonferenz ist die Tatsache, dass die Konferenz über einen Streamingübertragungsdienst an eine große Zahl von Konferenzteilnehmern verteilt wird. Dieser Streamingübertragungsdienst kann nicht über ExpressRoute geleitet werden. Stattdessen nutzt er das Internet mit der optionalen Unterstützung von Content Delivery Network-Diensten (CDN). Es ist hilfreich, sich klar zu machen, dass die Streamingübertragung ein unidirektionaler Medienfluss ist, denn die Teilnehmer hören zu, sprechen aber selbst nicht. Die Pufferung wird dabei unterstützt. Somit ist diese Form der Übertragung wesentlich weniger sensitiv gegenüber Problemen bei der Netzwerkleistung wie Latenz, Paketverlust und Jitter. Statt den Übertragungsdatenverkehr für diese Probleme zu optimieren, wird dieser für die Bandbreitennutzung optimiert, weil potenziell eine sehr große Zahl an Teilnehmern die gestreamten Medien empfängt.

 **Skype-Livekonferenz mit Benutzern aus einem Kundennetzwerk**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Anrufflussmuster nach Entwicklungstyp

Anhand der oben angeführten Beispiele für häufig auftretende Anrufflüsse wurden die allgemeinen Grundsätze erläutert, die die Datenverkehrsmuster steuern. Die nachfolgenden Tabellen enthalten eine Übersicht über die Datenverkehrsmuster für eine große Kombination von Bereitstellungs- und Benutzerszenarien. Diese Tabellen erfassen nicht jede mögliche Kombination von Anrufflüssen. Sie können aber hilfreich sein, um die allgemeinen Grundsätze bei Anrufflüssen nachzuvollziehen.

Die Daten werden übermittelt und aufgeführt, als seien sie für die Organisation lokal. Sie verlassen das Kundennetzwerk, das Internet oder ExpressRoute dabei nicht. Die nachfolgend aufgeführten Muster basieren auf den häufigsten Netzwerkeinstellungen. Hierzu gehören beispielsweise Firewalls, Partnerverbund und Internet. Dabei wird von der Annahme ausgegangen, dass alle Organisationen, die an Anrufflüssen mit mehreren Parteien oder mit Partnerverbunden beteiligt sind, ExpressRoute haben. In der Praxis könnte das Vorhandensein unterschiedlicher Einstellungen zu Datenverkehrsmustern führen, die von den nachfolgend aufgeführten Mustern abweichen.

### <a name="call-flows-for-skype-for-business-online"></a>Anrufflüsse bei Skype for Business Online

Skype for Business Szenarien für die Onlineverwendung umfassen Benutzer, die online zu Hause sind und entweder über Ihr internes Netzwerk oder über das Internet anrufen. Lokale Server sind nicht Teil dieser Szenarien, sodass alle Konferenz- oder PSTN-bezogenen Medien in die Cloud fließen, und auch der Edgeserver der Onlinebenutzer wird sich in der Cloud befinden.

 **Anrufflusszusammenfassung für Skype for Business Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Hinweise** <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, beide in Ihrem Netzwerk.  <br/> |ExpressRoute  <br/> |lokal  <br/> |[Peer-to-Peer-Anruf für Microsoft 365 oder Office 365 innerhalb des Kundennetzwerks](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, einer in Ihrem Netzwerk (intern) und der andere Client im Internet (extern).  <br/> |Interner Benutzer: ExpressRoute  <br/> Externer Benutzer: Internet  <br/> |Interner Benutzer: ExpressRoute  <br/> Externer Benutzer: Internet zum Microsoft 365 oder Office 365 Edgeserver.  <br/> |[Peer-to-Peer-Anruf für Microsoft 365 oder Office 365 innerhalb des Kundennetzwerks](call-flow-using-expressroute.md#bk_Figure2) <br/> |Dabei wird vorausgesetzt, dass die Firewall direkte Verbindungen zwischen Clients blockiert, für die ein Online-Edgeserver erforderlich ist. Der Datenverkehr vom internen Benutzer zum Online-Edgeserver folgt einem ähnlichen Pfad wie der Datenverkehr zum Konferenzserver für die Telefonkonferenz.  <br/> |
|Peer-to-Peer-Anruf an einen Benutzer in einer Partnerorganisation  <br/> |Zwei Clients, in Ihrem Netzwerk (intern) und bei einem Onlinebenutzer im Netzwerk der Partnerorganisation (Partnerverbund).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilt](call-flow-using-expressroute.md#bk_Figure3) <br/> |Dabei wird vorausgesetzt, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, d. h., dass ein Online-Edgeserver erforderlich ist. Der Datenverkehr vom internen Benutzer zum Online-Edgeserver folgt einem ähnlichen Pfad wie der Datenverkehr eines Konferenzservers für die Telefonkonferenz.  <br/> |
|Teilnahme an einer Telefonkonferenz durch einen Benutzer im Kundennetzwerk  <br/> |Client in Ihrem Netzwerk und Konferenzserver in der Cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnahme an einer Telefonkonferenz durch einen Benutzer im Internet  <br/> |Der Client befindet sich im Internet und der Konferenzserver in der Cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnehmen an einer Konferenz, die vom vor orts gehosteten Server eines anderen Unternehmens gehostet wird  <br/> |Client in Ihrem Netzwerk und Konferenzserver im Drittanbieter-Rechenzentrum.  <br/> |Internet  <br/> |Internet  <br/> |Nicht zutreffend  <br/> |Da sich der Konferenzserver, der die Konferenz hostet, in einem lokalen Netzwerk eines anderen Kunden befindet, würden keine Daten durch die Microsoft-Cloud übertragen.  <br/> |
|PSTN-Anruf  <br/> |Client im Kundennetzwerk und Telefonsystem in der Cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN-Anruf  <br/> |Client im Internet und Telefonsystem in der Cloud  <br/> |Internet  <br/> |Internet  <br/> |Nicht zutreffend  <br/> |Die Medien und Signale werden an das Microsoft 365 oder Office 365 Datencenter fließen. Da sich der Clientendpunkt im Internet befindet, werden alle Daten über das Internet zum Microsoft-Rechenzentrum übertragen (auch wenn für die Verbindung ein Online-Edgeserver erforderlich ist).  <br/> |

> [!NOTE]
> ExpressRoute wird auf dem Medienpfad von einem Benutzer im Unternehmensnetzwerk zu einem Online-Edgeserver verwendet, aber nicht, wenn der Edgeserver für die lokale Bereitstellung eines anderen Kunden verwendet wird.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Anrufflüsse für Skype for Business Hybrid

Hybridanrufflüsse gelten, wenn Sie über eine Bereitstellung Skype for Business verfügen, die mindestens einige Benutzer umfasst, die lokal behaust sind. Die Anrufflüsse in diesem Abschnitt umfassen sowohl lokale Konferenzen als auch Peer-zu-Peer- oder PSTN-Anrufe mit mindestens einem lokal gespeicherten Benutzer.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Hinweise** <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, sowohl im Kundennetzwerk als auch lokal  <br/> |Local  <br/> |lokal  <br/> |[Peer-to-Peer-Anruf für Microsoft 365 oder Office 365 innerhalb des Kundennetzwerks](call-flow-using-expressroute.md#bk_Figure2) <br/> |Da die Benutzer lokal gehostet werden, fließt die Signalisierung lokal zum lokalen Rechenzentrum und nicht zur Cloud.  <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, die sich beide vom Kundennetzwerk aus verbinden. Einer ist online, der andere lokal.  <br/> |Onlinebenutzer: ExpressRoute  <br/> Lokaler Benutzer: lokal  <br/> |lokal  <br/> |[Peer-to-Peer-Anruf für Microsoft 365 oder Office 365 innerhalb des Kundennetzwerks](call-flow-using-expressroute.md#bk_Figure2) <br/> |Nur der Online-Homed-Benutzer sendet Signalisierungsverkehr an die Cloud.  <br/> |
|Peer-to-Peer-Anruf an einen Benutzer in einer Partnerorganisation  <br/> |Zwei Clients: der lokale Benutzer im Kundennetzwerk (intern) und der Onlinebenutzer im Netzwerk des Partnerunternehmens (Partnerverbund).  <br/> |Interner Benutzer: lokal  <br/> Partnerbenutzer: ExpressRoute  <br/> |Internet oder ExpressRoute (abhängig davon, ob ein Online- oder lokale Edgeserver verwendet wird)  <br/> |[Onlinebenutzer](call-flow-using-expressroute.md#bk_Figure3) in Ihrem Netzwerk, der an einer Konferenz teilt, die online gehostet wird und Teil eines lokalen [Edgeservers](call-flow-using-expressroute.md#bk_Figure5) mit Microsoft 365 oder Office 365 gehosteten Konferenzen ist (für Medienverkehr). <br/> |Dabei wird vorausgesetzt, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, d. h., dass ein Online-Edgeserver erforderlich ist. ICE-Aushandlung bietet sowohl Online-Edgeserver (durch den Onlinebenutzer) als auch lokale Edgeserver (durch den lokalen Benutzer) für die Konnektivität an.  <br/> |
|Teilnahme an einer Telefonkonferenz durch einen Benutzer im Kundennetzwerk (von Onlinebenutzer geplante Konferenz)  <br/> |Lokale Benutzer in Ihrem Netzwerk und Konferenzserver in der Cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Onlinebenutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilt](call-flow-using-expressroute.md#bk_Figure3) <br/> |Serverressourcen für die Telefonkonferenz werden vom Besprechungsorganisator definiert. In diesem Fall wurde sie von einem Onlinebenutzer geplant, sodass sich die Ressourcen in der Cloud befinden.  <br/> |
|PSTN-Anruf  <br/> |Lokale Benutzer in Ihrem Netzwerk und lokales Skype for Business-Rechenzentrum.  <br/> |Local  <br/> |Local  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Ähnliches Szenario für die Verwendung von Cloud Connector Edition, mit der Ausnahme, dass der Benutzer lokal heimisiert ist, sodass die Signalisierung in Ihrem Netzwerk erhalten bleibt.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Anrufflüsse bei Skype for Business mit Cloud Connector

Benutzer, die eine Verbindung mit Cloud Connector Edition herstellen, sind alle online gespeichert. Dies bedeutet, dass die Konferenzen online sind und die Signalisierung den gleichen Mustern folgt wie für Online-Benutzer. Für Szenarien, die keine PSTN-Anrufe sind, ist der Anruffluss genau so, wie oben für Skype for Business Online beschrieben.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Hinweise** <br/> |
|PSTN-Anruf  <br/> |Onlinebenutzer in Ihrem Netzwerk mit Cloud Connector Edition.  <br/> |lokal  <br/> |lokal  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN-Anruf  <br/> |Onlinebenutzer, der das Internet mit Cloud Connector Edition verwendet.  <br/> |Internet  <br/> |Internet  <br/> |Kombination von [lokalem Edgeserver](call-flow-using-expressroute.md#bk_Figure5) mit Microsoft 365 oder Office 365 gehosteten Konferenzen und PSTN-Anrufen mithilfe [von Skype for Business Cloud Connector Edition.](call-flow-using-expressroute.md#bk_Figure6)  <br/> |Internetbenutzer stellen eine Verbindung über den Edgeserver, der in Cloud Connector enthalten ist, und Cloud Connector wird eine Verbindung mit dem PSTN-Netzwerk herstellen.  <br/> |

## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute-Dokumentation](/azure/expressroute/)
