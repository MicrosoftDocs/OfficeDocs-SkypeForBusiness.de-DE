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
ms.openlocfilehash: b65d7b1e3677c82e562de63257f28ad1561d7190
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164634"
---
# <a name="call-flow-using-expressroute"></a>Anruffluss mit ExpressRoute

In diesem Artikel werden die wichtigsten Grundsätze zum Anruffluss für Skype for Business Online und ExpressRoute mit detaillierten Beispielen für Anrufflüsse erläutert, um Sie bei einer adäquaten Planung zu unterstützen.

Wenn Sie Skype for Business Online als Teil von Microsoft 365 oder Office 365, Skype for Business Server Hybrid oder Skype for Business Cloud Connector Edition bereitstellen, müssen Sie die Kommunikation zwischen dem Skype for Business-Client und den Servern und dem Anruffluss verstehen, damit Sie Ihre Skype for Business Online-Dienste effektiv planen, bereitstellen, betreiben und beheben können.

## <a name="call-flow-overview"></a>Übersicht über Anruffluss

In diesem Dokument werden die Netzwerksegmente beschrieben, die Daten für diese Anrufflüsse übertragen können. Es wird erläutert, welcher Datenverkehr lokal in Ihrem Netzwerk verarbeitet wird und welcher Datenverkehr über das Internet oder über ExpressRoute geleitet wird. Die Kenntnis darüber, welcher Datenverkehr ExpressRoute nutzt, ist für Sie hilfreich bei der Beurteilung der Vorteile, die sich für Ihre Firma durch die Nutzung von ExpressRoute ergeben. Ferner erhalten Sie eine Anleitung zur Bereitstellung von ExpressRoute, damit Sie Ihre Bereitstellung validieren und etwaige Probleme darin behandeln können, nachdem Sie sich für die Nutzung von ExpressRoute entschieden haben.

Die hier beschriebenen Anrufflüsse können durch diverse Faktoren beeinflusst werden, die Sie kontrollieren können. Hierzu gehören beispielsweise Firewall-Regeln, die NAT-Konfiguration, Proxyserver und die Routerkonfiguration. Dieses Dokument basiert auf der Annahme, dass die empfohlenen Einstellungen übernommen wurden. Eine Beschreibung dieser empfohlenen Einstellungen finden Sie in:

- [Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Übersicht über Express Route](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

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

 **Express Route** Hierbei handelt es sich um das Netzwerksegment, das Teil Ihres gesamten Netzwerks ist und Ihnen eine dedizierte, private Verbindung zum Microsoft-Netzwerk bietet. Dies ist die empfohlene Option für die Verbindung Ihres Netzwerks mit dem Microsoft-Netzwerk (Microsoft 365 oder Office 365-Rechenzentren) für alle Arbeitslasten, die von der Netzwerkgeschwindigkeit und-Leistung abhängen, wie etwa die Echtzeitkommunikation zwischen Skype for Business Online. Express Route-Verbindungen werden zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk hergestellt verwenden Sie [Express Route-Verbindungsanbieter](https://azure.microsoft.com/documentation/articles/expressroute-locations/) , um ein privates und verwaltetes Netzwerk bereitzustellen, mit einer Verfügbarkeit von 99,9% und Unterstützung für Quality of Service (QoS), die die Leistung für echt Zeit Medien in Zeiten von Netzwerküberlastung verbessern kann.

 **Microsoft-Netzwerk** Hierbei handelt es sich um das Netzwerksegment, das Teil des gesamten Netzwerks ist, das Microsoft 365-und Office 365-Dienste unterstützt. Dies umfasst die gesamte Kommunikation zwischen Online Servern für Microsoft 365 oder Office 365. Dies kann Datenverkehr umfassen, der das Microsoft-Netzwerk-Backbone durchläuft und zwischen geografischen Regionen übertragen wird.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

Der Netzwerkdatenverkehr für Skype for Business Online lässt sich in zwei Hauptkategorien unterteilen. Diese werden im Anruffluss jeweils als eigener Pfad angezeigt:

 **Echtzeitmedien** sind Daten, die innerhalb von RTP (Real-Time Transport-Protokoll) gekapselt sind und Audio-, Video-, Anwendungsfreigabe- und Dateiübertragungs-Workloads unterstützen. Im Allgemeinen ist der Medienverkehr hochgradig latenzsensitiv. Daher ist es in Ihrem Sinne, wenn dieser Datenverkehr auf einem möglichst direkten Weg übermittelt wird. Aus diesem Grund sollte UDP als Transportschichtprotokoll verwendet werden, weil TCP eine höhere Latenz mit sich bringt.

 **Signalisierung** ist die Kommunikationsverbindung zwischen Client und Server oder mit anderen Clients, die zur Steuerung von Aktivitäten (z. B. wenn ein Anruf initiiert wird) und für die Zustellung von Chatnachrichten verwendet wird. Der Signalisierungsverkehr verwendet überwiegend das SIP-Protokoll. Einige Clients verwenden jedoch HTTP-basierte REST-Schnittstellen. Einfach gesagt, haben wir es bei dieser Art des Datenverkehrs mit diversen Signalisierungen zu tun, die über HTTP- und HTTPS- oder TLS-Verbindungen übermittelt werden können. Ein wichtiger Aspekt ist, dass dieser Datenverkehr wesentlich weniger latenzsensitiv ist. Allerdings kann es zu Dienstausfällen oder zur Unterbrechung von Anrufen wegen Zeitüberschreitungen kommen, wenn die Latenz zwischen den Endpunkten mehrere Sekunden überschreitet.

Die Ziele für diesen Datenverkehr finden Sie in den [Office 365-URLs und IP-Adressbereichen](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) für alle Microsoft 365-oder Office 365-Dienste. Für jede URL gibt Sie an, ob dieser Teil des Datenverkehrs die Express Route für Microsoft 365 oder Office 365 durchlaufen kann. Diagramme, die anzeigen, dass das Internet weiterhin für einige Datenverkehr verwendet wird, wenn Express Route aktiviert ist, finden Sie unter [Azure Express Route für Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Wichtig ist die Erkenntnis, dass selbst URLs, die nominell über ExpressRoute geroutet werden können, auch über das Internet geroutet werden können. Dies bedeutet, dass die Entscheidung, ob das Internet oder ExpressRoute verwendet wird, in einigen Szenarien vom Clientstandort und von der Konfiguration der Proxyserver und Firewalls abhängt. Darüber hinaus ist es wichtig zu verstehen, dass nicht alle URLs, die mit Microsoft 365 oder Office 365 verbunden sind, Express Route verwenden können, sondern auch eine Internet Verbindung erforderlich ist, wenn Sie Express Route von einem Express Route-Partner kaufen.

Datenverkehr, der nur über das Internet gesendet werden kann, umfasst allgemeine Internet Abhängigkeiten wie Zertifikatsperrlisten (Certificate Revocation Lists, CRLs), DNS-Lookups und Namensauflösung, URLs für freigegebene Microsoft 365-oder Office 365-Dienste, beispielsweise für das Microsoft 365 Admin Center und einige nicht-Echtzeit-Kommunikationsfunktionen von Skype for Business Online, wie Telemetrie und sowie Medien, die für die Skype-Live Konferenz gestreamt werden. Informationen dazu, wie Sie Entscheidungen treffen können, finden Sie unter [Routing mit Express Route für Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) , um weitere Überlegungen zu erfahren, wenn Sie Ihr Netzwerkrouting planen.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Grundsätze für Anrufflüsse bei Skype for Business

Bevor wir die spezifischen Anruffluss-Szenarien näher betrachten, sollen hier sechs allgemeine Grundsätze erläutert werden, die für das Verständnis von Anrufflüssen bei Skype for Business wichtig sind.

1. Eine Skype for Business-Konferenz wird in der gleichen Region gehostet, in der der Konferenzorganisator beheimatet ist. Dies befindet sich in der Cloud, wenn es sich bei dem Organisator um einen Online Benutzer oder in einem lokalen Rechenzentrum handelt, wenn der Besprechungsorganisator ein lokales Benutzer ist.

2. Der von einem Client in einer gehosteten Konferenz gesendete Medienverkehr fließt immer zu dem Server, auf dem die Konferenz gehostet wird. Hierbei kann es sich um einen lokalen Server innerhalb eines Rechenzentrums handeln, das Sie verwalten, oder um einen Online Server innerhalb der Cloud. Für den Medienfluss für Onlinekonferenzen wird jedoch immer ein Edgeserver verwendet.

3. Der Medienverkehr für Peer-to-Peer-Anrufe wird auf der direktesten verfügbaren Route übermittelt. Die bevorzugte Route geht direkt zum externen Peer (Client). Ist diese Route jedoch aufgrund einer Blockierung des Datenverkehrs durch eine Firewall oder Ähnliches nicht verfügbar, so wird der Datenverkehr über einen oder mehrere Edgeserver übermittelt.

4. Der Signalisierungsverkehr wird immer auf den Server geleitet, auf dem der Benutzer beheimatet ist. Dies kann entweder ein Online-Server oder ein lokaler Server sein. Ein Edgeserver wird verwendet, wenn eine direkte Verbindung mit dem Front-End-Server nicht möglich ist.

5. Benutzer, die an einer online gehosteten Konferenz teilnehmen, verwenden immer einen Edgeserver (oder zwei, sofern dies aufgrund der Client-Firewallkonfigurationen erforderlich ist).

6. Benutzer, die an einer lokal gehosteten Konferenz teilnehmen, nutzen in der Regel keinen Edgeserver, wenn sie die Verbindung von demselben Netzwerk aus herstellen, das auch die lokale Bereitstellung enthält. Benutzer, die die Verbindung von außerhalb Ihres Netzwerks herstellen, nutzen hingegen einen oder zwei Edgeserver.

Nähere Informationen zum gewählten Medienpfad finden Sie unter [ICE - Edge-Medienverbindungen](https://aka.ms/AVEdge). In diesem Video wird Lync Server 2013 behandelt. Die Grundsätze und Protokolle gelten aber auch für Skype for Business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Skype for Business-Anrufflüsse mit ExpressRoute

Sie kennen jetzt die vier verschiedenen Netzwerksegmente und einige allgemeine Grundsätze für Skype for Business-Anrufflüsse. Anhand dieser Informationen können Sie nun nachvollziehen, welcher Skype for Business-Datenverkehr ein ExpressRoute-Netzwerksegment durchläuft.

Im allgemeinen durchläuft der Netzwerkdatenverkehr die Express Route-Verbindung, wenn sich ein Endpunkt in Ihrem Netzwerk befindet und sich der andere Endpunkt im Microsoft 365-oder Office 365-Rechenzentrum befindet. Dies beinhaltet den Signalisierungsverkehr zwischen Client und Server, den während der Telefonkonferenzen verwendeten Medienverkehr oder Peer-to-Peer-Anrufe, die einen Online-Edgeserver verwenden.

Der Datenverkehr läuft nicht über die ExpressRoute-Verbindung, wenn beide Endpunkte direkt über das Internet miteinander kommunizieren können oder wenn sich beide innerhalb Ihres Netzwerks befinden. Dazu gehören Medien für Peer-to-Peer-Anrufe, Datenverkehr aus dem Internet, der zu einer lokalen Bereitstellung bestimmt ist, oder ein beliebiger Datenverkehr zwischen dem Internet und Microsoft 365-oder Office 365-Edgeserver. Ein Beispiel hierfür ist ein Benutzer, der von einem Hotel aus an einer Onlinekonferenz teilnimmt.

## <a name="basic-skype-for-business-call-flow"></a>Allgemeines zum Skype for Business-Anruffluss

Damit Sie die oben beschriebenen Grundsätze über Skype for Business-Anrufflüsse anwenden können, enthält der nächste Abschnitt in diesem Artikel eine Reihe von Diagrammen als Referenz. Dabei handelt es sich nicht um eine vollständige Liste aller denkbaren Anrufflüsse. Vielmehr sollen Ihnen diese Informationen als Orientierung für die Anwendung der oben beschriebenen Grundsätze dienen. Die Szenarios in den Diagrammen wurden außerdem unter dem Gesichtspunkt ausgewählt, dass sie häufige Bereitstellungstypen abdecken: Online, Hybrid, Cloud Connector und in einem speziellen Fall Skype-Livekonferenz.

> [!NOTE]
> Ein Teil des von Skype for Business genutzten Datenverkehrs kann nicht über ExpressRoute geleitet werden und verwendet daher immer einen Internetpfad. Anhand der Informationen unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) können Sie feststellen, welche URLs betroffen sein können.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Peer-zu-Peer-Anruf für Microsoft 365 oder Office 365-Benutzer im Kundennetzwerk
<a name="bk_Figure2"> </a>

Der Medienverkehr für Peer-to-Peer-Anrufe wird immer auf der direktesten verfügbaren Route an das Ziel übermittelt. Der Signalisierungs Datenverkehr wechselt jedoch zu einem Microsoft 365-oder Office 365-Rechenzentrum, in dem sich der Online Benutzer befindet. Da sich beide Benutzer im selben WAN befinden und nichts eine direkte Kommunikation der Clients verhindert, erfolgt der Medienfluss direkt zwischen den beiden. Der Signalisierungsverkehr läuft bei beiden Benutzern über die ExpressRoute-Verbindung, deren Ziel das Rechenzentrum der jeweiligen Organisation ist. Die folgende Darstellung zeigt den Anruffluss in diesem Szenario.

 **Peer-to-Peer-Anruffluss**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt
<a name="bk_Figure3"> </a>

Im Peer-to-Peer-Beispiel nimmt der Medien Verkehr immer den direktsten Weg zum Ziel. Bei einer Online Konferenz befindet sich das Ziel jedoch in der Cloud. Das bedeutet, dass der Medien Verkehr für alle Benutzer, die an der Konferenz teilnehmen, von Ihrem Netzwerk aus die Express Route-Verbindung durchläuft und der Signalisierungs Datenverkehr in die Cloud reist. Die folgende Abbildung zeigt, dass sowohl Medien als auch Signalisierungen die Express Route-Verbindung für einen Benutzer in Ihrem Netzwerk durchlaufen und das Internet direkt für Benutzer durchlaufen, die von außerhalb Ihres Netzwerks mit dem Internet verbunden sind, beispielsweise in einem Coffee-Shop oder einem Hotel.

Wichtig ist, dass sich der Standort einer Konferenz nach dem Besprechungsorganisator richtet und nicht nach den Teilnehmern. Das bedeutet: Wenn die Besprechung von einem lokalen Kunden geplant wurde, wird der Mediendatenverkehr nicht über Express Route in die Cloud übertragen, sondern stattdessen das Internet in das lokale Rechenzentrum des Besprechungsorganisators durchlaufen.

Das Ziel für Medien für Online Konferenzen ist ein Rechenzentrum in der Microsoft 365-oder Office 365-Cloud, aber das Rechenzentrum befindet sich möglicherweise in einer anderen geografischen Region als die Benutzer, die der Konferenz beitreten. Dies kann auf eine von zwei Arten erfolgen:

- Wenn der Besprechungsorganisator in einem anderen Unternehmen tätig ist als die Teilnehmer und die Organisation für den Organisator an einem anderen geografischen Standort oder in einem anderen Land bzw. einer anderen Region gehostet wird.

- Wenn sich ein Benutzer aus einem anderen Land bzw. einer anderen Region teilnimmt als dem Land bzw. der Region, wo sich der Standort der Organisation des Unternehmens befindet. Dies kann der Fall sein, wenn das Unternehmen multinational ist oder wenn der Benutzer auf Reisen ist.

Das Gute an der Verwendung von ExpressRoute in diesem Szenario ist, dass Daten, die dem ExpressRoute-Pfad folgen, mit dem ExpressRoute Premium-Add-On automatisch über den Backbone von Microsoft zum Datencenter der Organisation der Besprechung geleitet werden. Die geografische Region des Organisators spielt dabei keine Rolle.

 **Anruffluss bei Online-Benutzer in Onlinebesprechung**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Teilnahme an einer Konferenz, die von einem lokalen Benutzer in einer Hybrid-Bereitstellung gehostet wird
<a name="bk_Figure3"> </a>

Beachten Sie, dass die Konferenzserver, die gehostete Konferenzen unterstützen, von der Position des Besprechungsorganisators abhängig sind. In diesem Szenario fließen Medien für alle Benutzer, die an einer Konferenz teilnehmen, die von einem lokalen Benutzer in einer Hybrid Bereitstellung geplant wird, in ein lokales Rechenzentrum. Das signalisieren für Online vernetzte Benutzer wird über Ihre Organisation in der Cloud eingerichtet, während Medien eine direkte Verbindung versuchen. Da beide Benutzer innerhalb Ihres Netzwerks eine Verbindung herstellen, ist in diesem Szenario eine direkte Medien Verbindung möglich, damit Express Route nur für das signalisieren von Datenverkehr für den Online vernetzten Benutzer verwendet wird. Wenn ein Online verwalteter Benutzer eine Verbindung mit dem Internet herstellt, kann das Medium Express Route durchlaufen, wenn eine Verbindung mit einem Online-Edgeserver hergestellt wird.

 **Anruffluss bei einer von einem Hybrid-Benutzer gehosteten Konferenz**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Lokales Edgeserver mit Microsoft 365 oder Office 365, gehostete Konferenzen
<a name="bk_Figure5"> </a>

Wenn ein Hybrid Benutzer einer Online gehosteten Konferenz Beitritt, wissen wir, dass Signalisierungs-und Medieninformationen für die Microsoft 365-oder Office 365-Cloud bestimmt sind, und da der Benutzer aus dem Internet Beitritt, wird normalerweise ein direkter Internet Pfad ausgeführt. In einigen Fällen, beispielsweise aufgrund von Firewall-Einschränkungen, ist jedoch kein direkter Internet Pfad verfügbar. In diesem Fall kann ein lokales Edgeserver den Mediendatenverkehr weiterleiten, was dazu führt, dass der Mediendatenverkehr wieder in Ihr lokales Netzwerk zurückgeleitet wird, bevor der Express Route-Schaltkreis in die Cloud übertragen wird.

 **Lokale Benutzer, die von einem lokalen Edgeserver aus an einer Online-Telekonferenz teilnehmen**

![Anruffluss für einen Konferenzanruf, der über einen Edgeserver läuft.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>PSTN-Anruf mit Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Die Verwendung von [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) bietet PSTN-Konnektivität mithilfe von lokalen Ressourcen wie einem SIP-Stamm oder einem PSTN-Gateway oder mithilfe eines minimalen Hardwaregeräts zur Integration in Skype for Business. Mit Cloud Connector Edition sind Benutzer online und fungieren als normale Online Benutzer, wenn Sie keine Anrufpläne beinhalten. Das signalisieren für PSTN-Szenarien reist zwischen dem Client und der Cloud über eine Express Route-Verbindung, falls verfügbar, und der Mediendatenverkehr bleibt in Ihrem WAN. In diesem Fall wird die Signalisierung bei der Microsoft 365-oder Office 365-Cloud umgestellt und am Cloud-Connector beendet.

 **PSTN-Anruf über das Telefon System in Microsoft 365 oder Office 365 und Cloud Connector**

![Anruffluss für einen PSTN-Anruf mit Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype-Livekonferenz mit Benutzern, die von einem Kundennetzwerk aus teilnehmen
<a name="bk_Figure6"> </a>

Skype-Live Konferenz ist ein spezieller Anwendungsfall, der aus einer zwei teiligen Besprechung besteht, wobei jeder Teil unterschiedliche Netzwerktransport Profile hat. Der erste Teil, und der wichtigste aus der Sicht des Netzwerk Leistungs Aspekts, ist die innere Besprechung. Dies ist der Teil der Besprechung in Echtzeit, der einen oder mehrere Clientendpunkte enthält, die mit dem Konferenzserver in der Cloud verbunden sind. Die über diesen Teil der Besprechung übertragenen Daten sind genau wie im obigen Beispiel, wenn ein Benutzer an einer Online Konferenz teilnimmt.

Das Besondere an einer Skype-Livekonferenz ist die Tatsache, dass die Konferenz über einen Streamingübertragungsdienst an eine große Zahl von Konferenzteilnehmern verteilt wird. Dieser Streamingübertragungsdienst kann nicht über ExpressRoute geleitet werden. Stattdessen nutzt er das Internet mit der optionalen Unterstützung von Content Delivery Network-Diensten (CDN). Es ist hilfreich, sich klar zu machen, dass die Streamingübertragung ein unidirektionaler Medienfluss ist, denn die Teilnehmer hören zu, sprechen aber selbst nicht. Die Pufferung wird dabei unterstützt. Somit ist diese Form der Übertragung wesentlich weniger sensitiv gegenüber Problemen bei der Netzwerkleistung wie Latenz, Paketverlust und Jitter. Statt den Übertragungsdatenverkehr für diese Probleme zu optimieren, wird dieser für die Bandbreitennutzung optimiert, weil potenziell eine sehr große Zahl an Teilnehmern die gestreamten Medien empfängt.

 **Skype-Livekonferenz mit Benutzern aus einem Kundennetzwerk**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Anrufflussmuster nach Entwicklungstyp

Anhand der oben angeführten Beispiele für häufig auftretende Anrufflüsse wurden die allgemeinen Grundsätze erläutert, die die Datenverkehrsmuster steuern. Die nachfolgenden Tabellen enthalten eine Übersicht über die Datenverkehrsmuster für eine große Kombination von Bereitstellungs- und Benutzerszenarien. Diese Tabellen erfassen nicht jede mögliche Kombination von Anrufflüssen. Sie können aber hilfreich sein, um die allgemeinen Grundsätze bei Anrufflüssen nachzuvollziehen.

Die Daten werden übermittelt und aufgeführt, als seien sie für die Organisation lokal. Sie verlassen das Kundennetzwerk, das Internet oder ExpressRoute dabei nicht. Die nachfolgend aufgeführten Muster basieren auf den häufigsten Netzwerkeinstellungen. Hierzu gehören beispielsweise Firewalls, Partnerverbund und Internet. Dabei wird von der Annahme ausgegangen, dass alle Organisationen, die an Anrufflüssen mit mehreren Parteien oder mit Partnerverbunden beteiligt sind, ExpressRoute haben. In der Praxis könnte das Vorhandensein unterschiedlicher Einstellungen zu Datenverkehrsmustern führen, die von den nachfolgend aufgeführten Mustern abweichen.

### <a name="call-flows-for-skype-for-business-online"></a>Anrufflüsse bei Skype for Business Online

Bei Skype for Business Online-Nutzungsszenarien handelt es sich um Benutzer, die Online sind, und Sie können entweder über Ihr internes Netzwerk oder das Internet anrufen. Lokale Server sind nicht Teil dieser Szenarien, sodass alle Konferenz-oder PSTN-bezogenen Medien in die Cloud fließen und der Edgeserver für Online Benutzer ebenfalls in der Cloud vorhanden ist.

 **Zusammenfassung des Anrufflusses für Skype for Business Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungs Pfad** <br/> |**Medienpfad** <br/> |**Beispiel Fluss** <br/> |**Hinweise** <br/> |
|Peer-zu-Peer-Anruf  <br/> |Zwei Clients, sowohl in Ihrem Netzwerk.  <br/> |ExpressRoute  <br/> |lokalen  <br/> |[Peer-zu-Peer-Anruf für Microsoft 365 oder Office 365-Benutzer im Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Peer-zu-Peer-Anruf  <br/> |Zwei Clients, einer in Ihrem Netzwerk (intern) und der andere Client im Internet (extern).  <br/> |Interner Benutzer: Express Route  <br/> Externer Benutzer: Internet  <br/> |Interner Benutzer: Express Route  <br/> Externer Benutzer: Internet zu Microsoft 365 oder Office 365 Edge Server.  <br/> |[Peer-zu-Peer-Anruf für Microsoft 365-oder Office 365-Benutzer im Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Es wird davon ausgegangen, dass die Firewall direkte Verbindungen zwischen Clients blockiert, die einen Online-Edgeserver erfordern. Der Datenverkehr vom internen Benutzer zum Online-Edgeserver folgt einem ähnlichen Pfad wie dem Konferenzserver für Konferenzanrufe.  <br/> |
|Peer-zu-Peer-Anruf an einen Benutzer in einer Verbundorganisation  <br/> |Zwei Clients, in Ihrem Netzwerk (intern) und Online Benutzer im Netzwerk der Verbundorganisation (Federated).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> |Setzt voraus, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, die Online-Edgeserver erfordern. Der Datenverkehr vom internen Benutzer zum Online-Edgeserver folgt einem ähnlichen Pfad wie der eines Konferenzservers für Konferenzgespräche.  <br/> |
|Teilnehmen an Konferenzgesprächen nach Benutzer im Kundennetzwerk  <br/> |Client auf Ihrem Netzwerk und Konferenzserver in der Cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnehmen an Konferenzgesprächen nach Benutzer im Internet  <br/> |Der Client befindet sich auf dem Internet-und Konferenzserver in der Cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnahme an einer Konferenz, die von einem anderen Unternehmen auf dem Prem-Server gehostet wird  <br/> |Client auf Ihrem Netzwerk und Konferenzserver in einem Drittanbieter-Rechenzentrum.  <br/> |Internet  <br/> |Internet  <br/> |Nicht zutreffend  <br/> |Da sich der Konferenzserver, auf dem sich die Konferenz befindet, in einem lokalen Netzwerk eines anderen Kunden befindet, gehen keine Daten über die Microsoft-Cloud.  <br/> |
|PSTN-Anruf  <br/> |Client in Kunden-Netzwerk-und Telefon System Server in der Cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN-Anruf  <br/> |Client im Internet und Telefon System Server in der Cloud  <br/> |Internet  <br/> |Internet  <br/> |Nicht zutreffend  <br/> |Medien und Signalisierungen fließen in das Microsoft 365-oder Office 365-Rechenzentrum. Da sich der Clientendpunkt im Internet befindet, fließen alle Daten in das Microsoft Datacenter über das Internet (auch wenn ein Online-Edgeserver für die Konnektivität benötigt wird).  <br/> |

> [!NOTE]
> Express Route wird auf dem Medienpfad eines Benutzers im Unternehmensnetzwerk zu einem Online-Edgeserver verwendet, wird aber nicht verwendet, wenn der Edgeserver für die lokale Bereitstellungeines anderen Kunden verwendet wird.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Anruf Flüsse für Skype for Business-Hybrid

Es gelten hybride Anruf Flüsse, wenn Sie über eine Skype for Business-Bereitstellung verfügen, die mindestens einige Benutzer umfasst, die lokal gehostet werden. Zu den Anruf strömen in diesem Abschnitt gehören sowohl lokale Konferenzen als auch Peer-to-Peer-oder PSTN-Anrufe mit mindestens einem lokal vernetzten Benutzer.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungs Pfad** <br/> |**Medienpfad** <br/> |**Beispiel Fluss** <br/> |**Hinweise** <br/> |
|Peer-zu-Peer-Anruf  <br/> |Zwei Clients, sowohl im Kundennetzwerk als auch in der lokalen Niederlassung  <br/> |Local  <br/> |lokalen  <br/> |[Peer-zu-Peer-Anruf für Microsoft 365 oder Office 365-Benutzer im Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Da die Benutzer lokal lokal gehostet werden, fließt die Signalübertragung lokal in das lokale Rechenzentrum statt in die Cloud.  <br/> |
|Peer-zu-Peer-Anruf  <br/> |Zwei Clients, die beide über das Kundennetzwerk verbunden sind. Eine ist online, die andere lokal verwaltet.  <br/> |Online-Benutzer: Express Route  <br/> Lokaler Benutzer: lokal  <br/> |lokalen  <br/> |[Peer-zu-Peer-Anruf für Microsoft 365-oder Office 365-Benutzer im Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Nur der Online vernetzte Benutzer sendet signalisierten Datenverkehr an die Cloud.  <br/> |
|Peer-zu-Peer-Anruf an einen Benutzer in einer Verbundorganisation  <br/> |Zwei Clients, vor Ort – Benutzer im Kundennetzwerk (intern) und Online Benutzer im Netzwerk des Federated-Unternehmens (Federated).  <br/> |Interner Benutzer: lokal  <br/> Federated-Benutzer: Express Route  <br/> |Internet-oder Express Route (hängt davon ab, ob der Online-oder lokale Edgeserver verwendet wird)  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Konferenz teilnimmt, die online gehostet wird](call-flow-using-expressroute.md#bk_Figure3) , und Teil des [lokalen Edge-Servers mit Microsoft 365 oder Office 365, gehostete Konferenzen](call-flow-using-expressroute.md#bk_Figure5) (für Mediendatenverkehr). <br/> |Setzt voraus, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, die Online-Edgeserver erfordern. Ice Negotiation bietet sowohl online (vom Online Benutzer) als auch lokale Edgeserver (vom lokalen Benutzer) für die Konnektivität an.  <br/> |
|Teilnehmen an einem Konferenzanruf nach Benutzer im Kundennetzwerk (vom Online Benutzer geplantes Konferenzprogramm)  <br/> |Lokalen Benutzer auf Ihrem Netzwerk und Konferenzserver in der Cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> |Server Ressourcen für Konferenzgespräche werden vom Organisator der Besprechung definiert. In diesem Fall wurde es von einem Online Benutzer geplant, sodass sich die Ressourcen in der Cloud befinden.  <br/> |
|PSTN-Anruf  <br/> |Lokalen Benutzer in Ihrem Netzwerk und lokales Skype for Business-Rechenzentrum.  <br/> |Local  <br/> |Local  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Ähnliches Szenario für die Verwendung von Cloud Connector Edition, mit der Ausnahme, dass der Benutzer lokal verwaltet wird, sodass die Signalübertragung in Ihrem Netzwerk verbleibt.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Anruf Flüsse für Skype for Business mit Cloud Connector

Benutzer, die eine Verbindung mit der Cloud Connector Edition herstellen, werden alle Online verwaltet. Das bedeutet, dass Konferenzen online sind und die Signalisierung den gleichen Mustern wie für Online-Benutzer entspricht. Für andere Szenarien als PSTN-Anrufe ist der Anruffluss genau wie oben beschrieben für Skype for Business Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungs Pfad** <br/> |**Medienpfad** <br/> |**Beispiel Fluss** <br/> |**Hinweise** <br/> |
|PSTN-Anruf  <br/> |Online-Benutzer in Ihrem Netzwerk mit Cloud Connector Edition.  <br/> |lokalen  <br/> |lokalen  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN-Anruf  <br/> |Online-Benutzer, der das Internet mithilfe von Cloud Connector Edition nutzt.  <br/> |Internet  <br/> |Internet  <br/> |Kombination aus [lokalem Edgeserver mit Microsoft 365 oder Office 365-gehosteten Konferenzen](call-flow-using-expressroute.md#bk_Figure5) und [PSTN-anrufen mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Internet Benutzer verbinden sich über den Edgeserver, der in Cloud Connector enthalten ist, und Cloud Connector stellt eine Verbindung mit dem PSTN-Netzwerk her.  <br/> |

## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute-Dokumentation](https://go.microsoft.com/fwlink/?LinkId=690285)


