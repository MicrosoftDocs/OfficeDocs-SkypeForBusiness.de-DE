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
ms.openlocfilehash: 3c728dab868177aab07c6fe618fba3a8c357eaa2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706670"
---
# <a name="call-flow-using-expressroute"></a>Anruffluss mit ExpressRoute

In diesem Artikel werden die wichtigsten Grundsätze zum Anruffluss für Skype for Business Online und ExpressRoute mit detaillierten Beispielen für Anrufflüsse erläutert, um Sie bei einer adäquaten Planung zu unterstützen.

Wenn Sie Skype for Business Online im Rahmen von Office 365, Skype for Business Server Hybrid oder Skype for Business Cloud Connector Edition bereitstellen, müssen Sie die Kommunikation zwischen dem Skype for Business-Client und den Servern sowie den Anruffluss verstehen. Dann können Sie Ihre Skype for Business Online-Dienste effektiv planen, bereitstellen und betreiben und Probleme effektiv behandeln.

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

 **Express Route** Hierbei handelt es sich um das Netzwerksegment, das Teil Ihres gesamten Netzwerks ist und Ihnen eine dedizierte, private Verbindung zum Microsoft-Netzwerk bietet. Dies ist die empfohlene Option zum Herstellen einer Verbindung zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk (Office 365-Rechenzentren) für alle Arbeitslasten, die von der Netzwerkgeschwindigkeit und-Leistung abhängen, wie etwa die Echtzeit-Kommunikation zwischen Skype for Business Online. Express Route-Verbindungen werden zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk hergestellt verwenden Sie [Express Route-Verbindungsanbieter](https://azure.microsoft.com/documentation/articles/expressroute-locations/) , um ein privates und verwaltetes Netzwerk bereitzustellen, mit einer Verfügbarkeit von 99,9% und Unterstützung für Quality of Service (QoS), die die Leistung für echt Zeit Medien in Zeiten von Netzwerküberlastung verbessern kann.

 **Microsoft-Netzwerk** Dies ist das Netzwerksegment innerhalb Ihres Gesamtnetzwerks, das die Office 365-Dienste unterstützt. Hierzu gehört die gesamte Kommunikation zwischen Onlineservern für Office 365, beispielsweise Datenverkehr, der den Backbone des Microsoft-Netzwerks durchläuft und zwischen verschiedenen geografischen Regionen übermittelt wird.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

Der Netzwerkdatenverkehr für Skype for Business Online lässt sich in zwei Hauptkategorien unterteilen. Diese werden im Anruffluss jeweils als eigener Pfad angezeigt:

 **Echtzeitmedien** sind Daten, die innerhalb von RTP (Real-Time Transport-Protokoll) gekapselt sind und Audio-, Video-, Anwendungsfreigabe- und Dateiübertragungs-Workloads unterstützen. Im Allgemeinen ist der Medienverkehr hochgradig latenzsensitiv. Daher ist es in Ihrem Sinne, wenn dieser Datenverkehr auf einem möglichst direkten Weg übermittelt wird. Aus diesem Grund sollte UDP als Transportschichtprotokoll verwendet werden, weil TCP eine höhere Latenz mit sich bringt.

 **Signalisierung** ist die Kommunikationsverbindung zwischen Client und Server oder mit anderen Clients, die zur Steuerung von Aktivitäten (z. B. wenn ein Anruf initiiert wird) und für die Zustellung von Chatnachrichten verwendet wird. Der Signalisierungsverkehr verwendet überwiegend das SIP-Protokoll. Einige Clients verwenden jedoch HTTP-basierte REST-Schnittstellen. Einfach gesagt, haben wir es bei dieser Art des Datenverkehrs mit diversen Signalisierungen zu tun, die über HTTP- und HTTPS- oder TLS-Verbindungen übermittelt werden können. Ein wichtiger Aspekt ist, dass dieser Datenverkehr wesentlich weniger latenzsensitiv ist. Allerdings kann es zu Dienstausfällen oder zur Unterbrechung von Anrufen wegen Zeitüberschreitungen kommen, wenn die Latenz zwischen den Endpunkten mehrere Sekunden überschreitet.

Die Ziele für diesen Datenverkehr finden Sie für alle Office 365-Dienste unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Für jede URL wird angegeben, ob dieser Teil des Datenverkehrs über ExpressRoute für Office 365 laufen kann. Diagramme, die anzeigen, dass das Internet weiterhin für einige Datenverkehr verwendet wird, wenn Express Route aktiviert ist, finden Sie unter [Azure Express Route für Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Wichtig ist die Erkenntnis, dass selbst URLs, die nominell über ExpressRoute geroutet werden können, auch über das Internet geroutet werden können. Dies bedeutet, dass die Entscheidung, ob das Internet oder ExpressRoute verwendet wird, in einigen Szenarien vom Clientstandort und von der Konfiguration der Proxyserver und Firewalls abhängt. Wichtig ist auch, dass Internetverbindung erforderlich ist, selbst wenn Sie ExpressRoute bei einem ExpressRoute-Partner erwerben, weil nicht alle mit Office 365 verbundenen URLs ExpressRoute nutzen können.

Datenverkehr, der nur über das Internet gesendet werden kann, umfasst allgemeine Internet Abhängigkeiten wie Zertifikatsperrlisten (Certificate Revocation Lists, CRLs), DNS-Lookups und Namensauflösung, URLs für Shared Office 365-Dienste, beispielsweise für das Microsoft 365 Admin Center und einige nicht-Echtzeit-Kommunikationsfunktionen von Skype for Business Online, wie Telemetrie und Föderation für Interoperabilität mit Skype Consumer sowie Medien, die für Skype-Live Konferenz gestreamt werden. Informationen dazu, wie Sie Entscheidungen treffen können, finden Sie unter [Routing mit Express Route für Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) , um weitere Überlegungen zu erfahren, wenn Sie Ihr Netzwerkrouting planen.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Grundsätze für Anrufflüsse bei Skype for Business

Bevor wir die spezifischen Anruffluss-Szenarien näher betrachten, sollen hier sechs allgemeine Grundsätze erläutert werden, die für das Verständnis von Anrufflüssen bei Skype for Business wichtig sind.

1. Eine Skype for Business-Konferenz wird in derselben Region gehostet, in der der Konferenzorganisator verwaltet wird. Das Hosting erfolgt in der Office 365-Cloud, sofern der Organisator Skype for Business Online verwendet. Wenn der Besprechungsorganisator hingegen lokaler Benutzer ist, wird die Konferenz in einem lokalen Datencenter gehostet.

2. Der von einem Client in einer gehosteten Konferenz gesendete Medienverkehr fließt immer zu dem Server, auf dem die Konferenz gehostet wird. Hierbei kann es sich um einen lokalen Server in einem von Ihnen verwalteten Datencenter handeln oder um einen Onlineserver in der Office 365-Cloud. Für den Medienfluss für Onlinekonferenzen wird jedoch immer ein Edgeserver verwendet.

3. Der Medienverkehr für Peer-to-Peer-Anrufe wird auf der direktesten verfügbaren Route übermittelt. Die bevorzugte Route geht direkt zum externen Peer (Client). Ist diese Route jedoch aufgrund einer Blockierung des Datenverkehrs durch eine Firewall oder Ähnliches nicht verfügbar, so wird der Datenverkehr über einen oder mehrere Edgeserver übermittelt.

4. Der Signalisierungsverkehr wird immer auf den Server geleitet, auf dem der Benutzer beheimatet ist. Dies kann entweder ein Online-Server oder ein lokaler Server sein. Ein Edgeserver wird verwendet, wenn eine direkte Verbindung mit dem Front-End-Server nicht möglich ist.

5. Benutzer, die an einer online gehosteten Konferenz teilnehmen, verwenden immer einen Edgeserver (oder zwei, sofern dies aufgrund der Client-Firewallkonfigurationen erforderlich ist).

6. Benutzer, die an einer lokal gehosteten Konferenz teilnehmen, nutzen in der Regel keinen Edgeserver, wenn sie die Verbindung von demselben Netzwerk aus herstellen, das auch die lokale Bereitstellung enthält. Benutzer, die die Verbindung von außerhalb Ihres Netzwerks herstellen, nutzen hingegen einen oder zwei Edgeserver.

Nähere Informationen zum gewählten Medienpfad finden Sie unter [ICE - Edge-Medienverbindungen](https://aka.ms/AVEdge). In diesem Video wird Lync Server 2013 behandelt. Die Grundsätze und Protokolle gelten aber auch für Skype for Business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Skype for Business-Anrufflüsse mit ExpressRoute

Sie kennen jetzt die vier verschiedenen Netzwerksegmente und einige allgemeine Grundsätze für Skype for Business-Anrufflüsse. Anhand dieser Informationen können Sie nun nachvollziehen, welcher Skype for Business-Datenverkehr ein ExpressRoute-Netzwerksegment durchläuft.

Im Allgemeinen durchläuft Netzwerkdatenverkehr die ExpressRoute-Verbindung, wenn sich ein Endpunkt in Ihrem Netzwerk verbindet und der andere Endpunkt im Office 365-Datencenter. Dies beinhaltet den Signalisierungsverkehr zwischen Client und Server, den während der Telefonkonferenzen verwendeten Medienverkehr oder Peer-to-Peer-Anrufe, die einen Online-Edgeserver verwenden.

Der Datenverkehr läuft nicht über die ExpressRoute-Verbindung, wenn beide Endpunkte direkt über das Internet miteinander kommunizieren können oder wenn sich beide innerhalb Ihres Netzwerks befinden. Dies gilt auch für Medien bei Peer-zu-Peer-Anrufen, Datenverkehr aus dem Internet, der an eine lokale Bereitstellung gesendet wird, oder jeglichen Datenverkehr zwischen dem Internet und Office 365-Edgeservern. Ein Beispiel hierfür ist ein Benutzer, der von einem Hotel aus an einer Onlinekonferenz teilnimmt.

## <a name="basic-skype-for-business-call-flow"></a>Allgemeines zum Skype for Business-Anruffluss

Damit Sie die oben beschriebenen Grundsätze über Skype for Business-Anrufflüsse anwenden können, enthält der nächste Abschnitt in diesem Artikel eine Reihe von Diagrammen als Referenz. Dabei handelt es sich nicht um eine vollständige Liste aller denkbaren Anrufflüsse. Vielmehr sollen Ihnen diese Informationen als Orientierung für die Anwendung der oben beschriebenen Grundsätze dienen. Die Szenarios in den Diagrammen wurden außerdem unter dem Gesichtspunkt ausgewählt, dass sie häufige Bereitstellungstypen abdecken: Online, Hybrid, Cloud Connector und in einem speziellen Fall Skype-Livekonferenz.

> [!NOTE]
> Ein Teil des von Skype for Business genutzten Datenverkehrs kann nicht über ExpressRoute geleitet werden und verwendet daher immer einen Internetpfad. Anhand der Informationen unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) können Sie feststellen, welche URLs betroffen sein können.

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Von einem Kundennetzwerk aus initiierter Peer-zu-Peer-Anruf für Office 365-Benutzer
<a name="bk_Figure2"> </a>

Der Medienverkehr für Peer-to-Peer-Anrufe wird immer auf der direktesten verfügbaren Route an das Ziel übermittelt. Der Signalisierungsverkehr wird jedoch an ein Office 365-Datencenter geleitet, in dem der Online-Benutzer beheimatet ist. Da sich beide Benutzer im selben WAN befinden und nichts eine direkte Kommunikation der Clients verhindert, erfolgt der Medienfluss direkt zwischen den beiden. Der Signalisierungsverkehr läuft bei beiden Benutzern über die ExpressRoute-Verbindung, deren Ziel das Rechenzentrum der jeweiligen Organisation ist. Die folgende Darstellung zeigt den Anruffluss in diesem Szenario.

 **Peer-to-Peer-Anruffluss**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt
<a name="bk_Figure3"> </a>

In dem Peer-zu-Peer-Beispiel nimmt der Medienverkehr immer die direkteste Route zu seinem Ziel. Bei einer Onlinekonferenz befindet sich das Ziel jedoch in der Office 365-Cloud. Dies bedeutet, dass der Medienverkehr für alle Benutzer, die von Ihrem Netzwerk aus an der Konferenz teilnehmen, über die ExpressRoute-Verbindung läuft und dass der Signalisierungsverkehr zur Office 365-Cloud geleitet wird. Die nachfolgende Grafik zeigt, dass sowohl Medien als auch Signalisierungen für einen Benutzer innerhalb Ihres Netzwerks über die ExpressRoute-Verbindung laufen. Für Benutzer, die sich außerhalb Ihres Netzwerks (beispielsweise von einem Café oder Hotel aus) mit dem Internet verbunden haben, werden diese Daten hingegen direkt über das Internet geleitet.

Wichtig ist, dass sich der Standort einer Konferenz nach dem Besprechungsorganisator richtet und nicht nach den Teilnehmern. Wenn die Besprechung also von einem lokalen Kunden geplant wird, fließt der Medienverkehr nicht über ExpressRoute zur Office 365-Cloud, sondern wird stattdessen über das Internet zum lokalen Datencenter des Besprechungsorganisators geleitet.

Der Zielort für Medien für Online-Konferenzen ist das Datencenter innerhalb der Office 365-Cloud. Das Datencenter kann sich jedoch in einer anderen geografischen Region befinden als die Benutzer, die an der Konferenz teilnehmen. Hierfür gibt es zwei Möglichkeiten:

- Wenn der Besprechungsorganisator in einem anderen Unternehmen tätig ist als die Teilnehmer und die Organisation für den Organisator an einem anderen geografischen Standort oder in einem anderen Land bzw. einer anderen Region gehostet wird.

- Wenn sich ein Benutzer aus einem anderen Land bzw. einer anderen Region teilnimmt als dem Land bzw. der Region, wo sich der Standort der Organisation des Unternehmens befindet. Dies kann der Fall sein, wenn das Unternehmen multinational ist oder wenn der Benutzer auf Reisen ist.

Das Gute an der Verwendung von ExpressRoute in diesem Szenario ist, dass Daten, die dem ExpressRoute-Pfad folgen, mit dem ExpressRoute Premium-Add-On automatisch über den Backbone von Microsoft zum Datencenter der Organisation der Besprechung geleitet werden. Die geografische Region des Organisators spielt dabei keine Rolle.

 **Anruffluss bei Online-Benutzer in Onlinebesprechung**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Teilnahme an einer Konferenz, die von einem lokalen Benutzer in einer Hybrid-Bereitstellung gehostet wird
<a name="bk_Figure3"> </a>

Bedenken Sie, dass sich die Frage, welche Konferenzserver die gehosteten Konferenzen unterstützen, danach richtet, wo der Besprechungsorganisator verwaltet wird. In diesem Szenario fließen die Medien für alle Benutzer, die an einer von einem lokalen Benutzer in einer Hybridbereitstellung geplanten Konferenz teilnehmen, zu einem lokalen Datencenter. Die Signalisierung für online verwaltete Benutzer fließt über deren Organisation in der Office 365-Cloud, während die Medien eine Direktverbindung zu nutzen versuchen. In diesem Szenario verbinden sich beide Benutzer innerhalb Ihres Netzwerks. Daher ist eine direkte Medienverbindung möglich. ExpressRoute wird also nur für den Signalisierungsverkehr für den online verwalteten Benutzer verwendet. Wenn sich ein online verwalteter Benutzer vom Internet aus verbindet und die Verbindung über einen Online-Edgeserver hergestellt wird, können die Medien über ExpressRoute laufen.

 **Anruffluss bei einer von einem Hybrid-Benutzer gehosteten Konferenz**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Lokale Edgeserver mit in Office 365 gehosteten Konferenzen
<a name="bk_Figure5"> </a>

Wenn ein Hybridbenutzer an einer online gehosteten Konferenz teilnimmt, wissen wir, dass die Signalisierung und die Medien an die Office 365-Cloud geleitet werden. Da der Benutzer vom Internet aus teilnimmt, würde normalerweise ein direkter Internetpfad verwendet. In einigen Fällen ist jedoch kein direkter Internetpfad verfügbar, beispielsweise aufgrund von Firewallbeschränkungen. In diesem Fall kann ein lokaler Edgeserver den Medienverkehr übermitteln. Hierdurch wird der Medienverkehr an Ihr lokales Netzwerk zurückgeleitet, bevor er über die ExpressRoute-Verbindung zur Office 365-Cloud übermittelt wird.

 **Lokale Benutzer, die von einem lokalen Edgeserver aus an einer Online-Telekonferenz teilnehmen**

![Anruffluss für einen Konferenzanruf, der über einen Edgeserver läuft.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>PSTN-Anruf mit Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Mit [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) wird die Anbindung an das Festnetz (PSTN-Anbindung) ermöglicht. Dabei werden lokale Ressourcen genutzt, zum Beispiel ein SIP-Trunk oder ein PSTN-Gateway oder ein minimales Hardwaregerät für die Integration mit Skype for Business. Mit Cloud Connector Edition werden Benutzer online verwaltet und handeln als normale Onlinebenutzer, wenn keine Anrufpläne beteiligt sind. Die Signalisierungen in PSTN-Szenarien fließen zwischen dem Client und der Cloud über eine ExpressRoute-Verbindung, sofern diese verfügbar ist. Der Medienverkehr bleibt in Ihrem WAN. In diesem Fall kehren die Signalisierungen bei der Office 365-Cloud um und enden bei Cloud Connector.

 **PSTN-Anruf über das Telefonsystem in Office 365 und Cloud Connector**

![Anruffluss für einen PSTN-Anruf mit Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype-Livekonferenz mit Benutzern, die von einem Kundennetzwerk aus teilnehmen
<a name="bk_Figure6"> </a>

Skype-Livekonferenz ist ein besonderer Anwendungsfall. In diesem Fall handelt es sich um eine zweiteilige Besprechung, deren Teile unterschiedliche Netzwerktransportprofile aufweisen. Der erste Teil ist die innere Besprechung. Im Hinblick auf die Netzwerkleistung ist dies der bedeutendere Teil. Dies ist der Echtzeitanteil der Besprechung. Er enthält einen oder mehrere Clientendpunkte, die sich mit dem Konferenzserver in der Office 365-Cloud verbinden. Die Daten, die über diesen Teil der Besprechung übermittelt werden, entsprechen genau dem Beispiel oben, in dem ein Office 365-Benutzer an einer Onlinekonferenz teilnimmt.

Das Besondere an einer Skype-Livekonferenz ist die Tatsache, dass die Konferenz über einen Streamingübertragungsdienst an eine große Zahl von Konferenzteilnehmern verteilt wird. Dieser Streamingübertragungsdienst kann nicht über ExpressRoute geleitet werden. Stattdessen nutzt er das Internet mit der optionalen Unterstützung von Content Delivery Network-Diensten (CDN). Es ist hilfreich, sich klar zu machen, dass die Streamingübertragung ein unidirektionaler Medienfluss ist, denn die Teilnehmer hören zu, sprechen aber selbst nicht. Die Pufferung wird dabei unterstützt. Somit ist diese Form der Übertragung wesentlich weniger sensitiv gegenüber Problemen bei der Netzwerkleistung wie Latenz, Paketverlust und Jitter. Statt den Übertragungsdatenverkehr für diese Probleme zu optimieren, wird dieser für die Bandbreitennutzung optimiert, weil potenziell eine sehr große Zahl an Teilnehmern die gestreamten Medien empfängt.

 **Skype-Livekonferenz mit Benutzern aus einem Kundennetzwerk**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Anrufflussmuster nach Entwicklungstyp

Anhand der oben angeführten Beispiele für häufig auftretende Anrufflüsse wurden die allgemeinen Grundsätze erläutert, die die Datenverkehrsmuster steuern. Die nachfolgenden Tabellen enthalten eine Übersicht über die Datenverkehrsmuster für eine große Kombination von Bereitstellungs- und Benutzerszenarien. Diese Tabellen erfassen nicht jede mögliche Kombination von Anrufflüssen. Sie können aber hilfreich sein, um die allgemeinen Grundsätze bei Anrufflüssen nachzuvollziehen.

Die Daten werden übermittelt und aufgeführt, als seien sie für die Organisation lokal. Sie verlassen das Kundennetzwerk, das Internet oder ExpressRoute dabei nicht. Die nachfolgend aufgeführten Muster basieren auf den häufigsten Netzwerkeinstellungen. Hierzu gehören beispielsweise Firewalls, Partnerverbund und Internet. Dabei wird von der Annahme ausgegangen, dass alle Organisationen, die an Anrufflüssen mit mehreren Parteien oder mit Partnerverbunden beteiligt sind, ExpressRoute haben. In der Praxis könnte das Vorhandensein unterschiedlicher Einstellungen zu Datenverkehrsmustern führen, die von den nachfolgend aufgeführten Mustern abweichen.

### <a name="call-flows-for-skype-for-business-online"></a>Anrufflüsse bei Skype for Business Online

Die Verwendungsszenarien für Skype for Business Online umfassen Benutzer, die online verwaltet werden und entweder von Ihrem internen Netzwerk aus oder vom Internet aus anrufen. Lokale Server kommen in diesen Szenarien nicht vor. Daher werden alle Medien in Bezug auf Konferenzen oder PSTN-Anrufe zur Office 365-Cloud fließen, und der Edgeserver der Onlinebenutzer befindet sich ebenfalls in der Cloud.

 **Zusammenfassung des Anrufflusses für Skype for Business Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungs Pfad** <br/> |**Medienpfad** <br/> |**Beispiel Fluss** <br/> |**Hinweise** <br/> |
|Peer-zu-Peer-Anruf  <br/> |Zwei Clients, sowohl in Ihrem Netzwerk.  <br/> |Express Route  <br/> |lokalen  <br/> |[Peer-zu-Peer-Anruf für Office 365-Benutzer im Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Peer-zu-Peer-Anruf  <br/> |Zwei Clients, einer in Ihrem Netzwerk (intern) und der andere Client im Internet (extern).  <br/> |Interner Benutzer: Express Route  <br/> Externer Benutzer: Internet  <br/> |Interner Benutzer: Express Route  <br/> Externer Benutzer: Internet zu Office 365 Edge-Server.  <br/> |[Peer-zu-Peer-Anruf für Office 365-Benutzer im Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Es wird davon ausgegangen, dass die Firewall direkte Verbindungen zwischen Clients blockiert, die einen Online-Edgeserver erfordern. Der Datenverkehr vom internen Benutzer zum Online-Edgeserver folgt einem ähnlichen Pfad wie dem Konferenzserver für Konferenzanrufe.  <br/> |
|Peer-zu-Peer-Anruf an einen Benutzer in einer Verbundorganisation  <br/> |Zwei Clients, in Ihrem Netzwerk (intern) und Online Benutzer im Netzwerk der Verbundorganisation (Federated).  <br/> |Express Route  <br/> |Express Route  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> |Setzt voraus, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, die Online-Edgeserver erfordern. Der Datenverkehr vom internen Benutzer zum Online-Edgeserver folgt einem ähnlichen Pfad wie der eines Konferenzservers für Konferenzgespräche.  <br/> |
|Teilnehmen an Konferenzgesprächen nach Benutzer im Kundennetzwerk  <br/> |Client auf Ihrem Netzwerk und Konferenzserver in der Office 365-Cloud.  <br/> |Express Route  <br/> |Express Route  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnehmen an Konferenzgesprächen nach Benutzer im Internet  <br/> |Der Client befindet sich auf dem Internet-und Konferenzserver in der Office 365-Cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnahme an einer Konferenz, die von einem anderen Unternehmen auf dem Prem-Server gehostet wird  <br/> |Client auf Ihrem Netzwerk und Konferenzserver in einem Drittanbieter-Rechenzentrum.  <br/> |Internet  <br/> |Internet  <br/> |Nicht zutreffend  <br/> |Da sich der Konferenzserver, auf dem sich die Konferenz befindet, in einem lokalen Netzwerk eines anderen Kunden befindet, gehen keine Daten über die Microsoft-Cloud.  <br/> |
|PSTN-Anruf  <br/> |Client in Kunden-Netzwerk-und Telefon System Server in der Office 365-Cloud  <br/> |Express Route  <br/> |Express Route  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN-Anruf  <br/> |Client im Internet und Telefon System Server in der Office 365-Cloud  <br/> |Internet  <br/> |Internet  <br/> |Nicht zutreffend  <br/> |Medien und Signalisierungen fließen in das Office 365-Rechenzentrum. Da sich der Clientendpunkt im Internet befindet, fließen alle Daten in das Microsoft Datacenter über das Internet (auch wenn ein Online-Edgeserver für die Konnektivität benötigt wird).  <br/> |

> [!NOTE]
> Express Route wird auf dem Medienpfad eines Benutzers im Unternehmensnetzwerk zu einem Online-Edgeserver verwendet, wird aber nicht verwendet, wenn der Edgeserver für die lokale Bereitstellungeines anderen Kunden verwendet wird.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Anruf Flüsse für Skype for Business-Hybrid

Es gelten hybride Anruf Flüsse, wenn Sie über eine Skype for Business-Bereitstellung verfügen, die mindestens einige Benutzer umfasst, die lokal gehostet werden. Zu den Anruf strömen in diesem Abschnitt gehören sowohl lokale Konferenzen als auch Peer-to-Peer-oder PSTN-Anrufe mit mindestens einem lokal vernetzten Benutzer.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungs Pfad** <br/> |**Medienpfad** <br/> |**Beispiel Fluss** <br/> |**Hinweise** <br/> |
|Peer-zu-Peer-Anruf  <br/> |Zwei Clients, sowohl im Kundennetzwerk als auch in der lokalen Niederlassung  <br/> |Local  <br/> |lokalen  <br/> |[Peer-zu-Peer-Anruf für Office 365-Benutzer im Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Da Benutzer lokal lokal gehostet werden, fließt die Signalübertragung lokal an das lokale Rechenzentrum statt an die Office 365-Cloud.  <br/> |
|Peer-zu-Peer-Anruf  <br/> |Zwei Clients, die beide über das Kundennetzwerk verbunden sind. Eine ist online, die andere lokal verwaltet.  <br/> |Online-Benutzer: Express Route  <br/> Lokaler Benutzer: lokal  <br/> |lokalen  <br/> |[Peer-zu-Peer-Anruf für Office 365-Benutzer im Kundennetzwerk](call-flow-using-expressroute.md#bk_Figure2) <br/> |Nur der online verwaltete Benutzer sendet signalisierten Datenverkehr an die Office 365-Cloud.  <br/> |
|Peer-zu-Peer-Anruf an einen Benutzer in einer Verbundorganisation  <br/> |Zwei Clients, vor Ort – Benutzer im Kundennetzwerk (intern) und Online Benutzer im Netzwerk des Federated-Unternehmens (Federated).  <br/> |Interner Benutzer: lokal  <br/> Federated-Benutzer: Express Route  <br/> |Internet-oder Express Route (hängt davon ab, ob der Online-oder lokale Edgeserver verwendet wird)  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Konferenz teilnimmt, die online gehostet wird](call-flow-using-expressroute.md#bk_Figure3) , und Teil des [lokalen Edge-Servers mit Office 365-gehosteten Konferenzen](call-flow-using-expressroute.md#bk_Figure5) (für Mediendatenverkehr). <br/> |Setzt voraus, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, die Online-Edgeserver erfordern. Ice Negotiation bietet sowohl online (vom Online Benutzer) als auch lokale Edgeserver (vom lokalen Benutzer) für die Konnektivität an.  <br/> |
|Teilnehmen an einem Konferenzanruf nach Benutzer im Kundennetzwerk (vom Online Benutzer geplantes Konferenzprogramm)  <br/> |Lokalen Benutzer auf Ihrem Netzwerk und Konferenzserver in der Office 365-Cloud.  <br/> |Express Route  <br/> |Express Route  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer Online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> |Server Ressourcen für Konferenzgespräche werden vom Organisator der Besprechung definiert. In diesem Fall wurde es von einem Online Benutzer geplant, sodass sich die Ressourcen in der Office 365-Cloud befinden.  <br/> |
|PSTN-Anruf  <br/> |Lokalen Benutzer in Ihrem Netzwerk und lokales Skype for Business-Rechenzentrum.  <br/> |Local  <br/> |Local  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Ähnliches Szenario für die Verwendung von Cloud Connector Edition, mit der Ausnahme, dass der Benutzer lokal verwaltet wird, sodass die Signalübertragung in Ihrem Netzwerk verbleibt.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Anruf Flüsse für Skype for Business mit Cloud Connector

Benutzer, die eine Verbindung mit der Cloud Connector Edition herstellen, werden alle Online verwaltet. Das bedeutet, dass Konferenzen online sind und die Signalisierung den gleichen Mustern wie für Online-Benutzer entspricht. Für andere Szenarien als PSTN-Anrufe ist der Anruffluss genau wie oben beschrieben für Skype for Business Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verwendungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungs Pfad** <br/> |**Medienpfad** <br/> |**Beispiel Fluss** <br/> |**Hinweise** <br/> |
|PSTN-Anruf  <br/> |Online-Benutzer in Ihrem Netzwerk mit Cloud Connector Edition.  <br/> |lokalen  <br/> |lokalen  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN-Anruf  <br/> |Online-Benutzer, der das Internet mithilfe von Cloud Connector Edition nutzt.  <br/> |Internet  <br/> |Internet  <br/> |Kombination aus [lokalem Edgeserver mit gehosteten Konferenzen in Office 365](call-flow-using-expressroute.md#bk_Figure5) und [PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Internet Benutzer verbinden sich über den Edgeserver, der in Cloud Connector enthalten ist, und Cloud Connector stellt eine Verbindung mit dem PSTN-Netzwerk her.  <br/> |

## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute-Dokumentation](https://go.microsoft.com/fwlink/?LinkId=690285)


