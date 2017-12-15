---
title: "Anruffluss mit ExpressRoute"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
description: "In diesem Artikel werden die wichtigsten Grundsätze zum Anruffluss für Skype for Business Online und ExpressRoute mit detaillierten Beispielen für Anrufflüsse erläutert, um Sie bei einer adäquaten Planung zu unterstützen."
---

# Anruffluss mit ExpressRoute

In diesem Artikel werden die wichtigsten Grundsätze zum Anruffluss für Skype for Business Online und ExpressRoute mit detaillierten Beispielen für Anrufflüsse erläutert, um Sie bei einer adäquaten Planung zu unterstützen.
  
Wenn Sie Skype for Business Online im Rahmen von Office 365, Skype for Business Server Hybrid oder Skype for Business Cloud Connector Edition bereitstellen, müssen Sie die Kommunikation zwischen dem Skype for Business-Client und den Servern sowie den Anruffluss verstehen. Dann können Sie Ihre Skype for Business Online-Dienste effektiv planen, bereitstellen und betreiben und Probleme effektiv behandeln. 
  
## Übersicht über Anruffluss

In diesem Dokument werden die Netzwerksegmente beschrieben, die Daten für diese Anrufflüsse übertragen können. Es wird erläutert, welcher Datenverkehr lokal in Ihrem Netzwerk verarbeitet wird und welcher Datenverkehr über das Internet oder über ExpressRoute geleitet wird. Die Kenntnis darüber, welcher Datenverkehr ExpressRoute nutzt, ist für Sie hilfreich bei der Beurteilung der Vorteile, die sich für Ihre Firma durch die Nutzung von ExpressRoute ergeben. Ferner erhalten Sie eine Anleitung zur Bereitstellung von ExpressRoute, damit Sie Ihre Bereitstellung validieren und etwaige Probleme darin behandeln können, nachdem Sie sich für die Nutzung von ExpressRoute entschieden haben.
  
Die hier beschriebenen Anrufflüsse können durch diverse Faktoren beeinflusst werden, die Sie kontrollieren können. Hierzu gehören beispielsweise Firewall-Regeln, die NAT-Konfiguration, Proxyserver und die Routerkonfiguration. Dieses Dokument basiert auf der Annahme, dass die empfohlenen Einstellungen übernommen wurden. Eine Beschreibung dieser empfohlenen Einstellungen finden Sie in:
  
- [Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [Azure ExpressRoute für Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)
    
- [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/)
    
Eine vom Einrichtungsverfahren in der oben genannten Dokumentation abweichende Einrichtung und Konfiguration kann dazu führen, dass die Anrufflüsse anders sind als in dieser Dokumentation. Außerdem treten bei Ihnen möglicherweise Konfigurationsprobleme auf, wie zum Beispiel asymmetrische und suboptimale Netzwerkrouten oder suboptimale Transportprotokolle. Das asymmetrische Routing ist im Zusammenhang mit ExpressRoute immer ein wichtiger Aspekt, denn ExpressRoute führt einen zweiten Pfad in Office 365 ein. Dadurch entsteht die Möglichkeit, den Datenverkehr über zwei verschiedene Routen zu leiten: eine Richtung über das Internet und die andere über ExpressRoute. Dies kann dazu führen, dass der zurückfließende Datenverkehr blockiert wird, wenn er auf eine zustandsbehaftete Firewall trifft.
  
## Netzwerksegmente und Arten von Datenverkehr

### Netzwerksegmente

Bevor wir den Anruffluss erläutern können, müssen wir einige Grundbegriffe im Zusammenhang mit den in Skype for Business Online verwendeten Netzwerksegmenten und Arten von Medien definieren. 
  
In den nachfolgenden Anrufflussdiagrammen sehen Sie vier verschiedene Netzwerksegmente. Jedes dieser Segmente wird von einer anderen Organisation verwaltet: Ihrem internen Netzwerk, Ihrem Netzwerkdienstanbieter und dessen Internet-Peering-Partnern sowie Microsoft. Die Segmente weisen jeweils unterschiedliche Leistungsmerkmale auf. Leitlinien für Netzwerkleistungsziele finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
Unten sehen Sie die einzelnen Netzwerksegmente, die hier erläutert werden sollen.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **Ihr Netzwerk** Dies ist das Netzwerksegment in Ihrem Gesamtnetzwerk, das Sie selbst steuern und verwalten. Hierzu gehören alle Verbindungen innerhalb Ihrer Geschäftsräume - verkabelt oder über Funk, zwischen Bürogebäuden, mit lokalen Datencentern - und Ihre Verbindungen mit Internetdienstanbietern oder ExpressRoute-Partnern.
  
Normalerweise befindet sich am Rand Ihres Netzwerks mindestens eine DMZ mit Firewalls und/oder Proxyservern, die die Sicherheitsrichtlinien Ihrer Organisation durchsetzen und die nur bestimmten Netzwerkdatenverkehr zulassen, den Sie eingerichtet und konfiguriert haben. Da Sie dieses Netzwerk verwalten, haben Sie die direkte Kontrolle über die Leistung Ihres Netzwerks. Es wird dringend empfohlen, die Leistung Ihres Netzwerks sowohl innerhalb der Sites im Netzwerk als auch vom Netzwerk zu Skype for Business Online mithilfe von Netzwerkbewertungen zu validieren. Die Leistungsanforderungen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
 **Internet** Dies ist das Netzwerksegment innerhalb Ihres Gesamtnetzwerks, das die Benutzer verwenden, wenn sie sich außerhalb des Netzwerks mit Skype for Business Online verbinden. Wenn ExpressRoute nicht konfiguriert ist, wird dieses Segment für alle Verbindungen verwendet. Das Internet und alle Verbindungen darin werden nicht von Ihnen oder von Microsoft verwaltet. Darum können die Leistung und die Routingpfade nicht bestimmt werden. Dies hat die größten Auswirkungen auf den Anruffluss und die Qualität insgesamt.
  
 **ExpressRoute** Dies ist das Netzwerksegment innerhalb Ihres Gesamtnetzwerks, das für Sie eine dedizierte, private Verbindung mit dem Microsoft-Netzwerk bereitstellt. Diese Option wird für alle Workloads, bei denen Netzwerkgeschwindigkeit und Leistung von besonders hoher Bedeutung sind (z. B. Echtzeitkommunikation über Skype for Business Online), für die Verbindung Ihres Netzwerks mit dem Microsoft-Netzwerk (Office 365-Datencenter) empfohlen. ExpressRoute-Verbindungen zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk werden über[ExpressRoute-Verbindungsanbieter](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) hergestellt. Dadurch genießen Sie ein privates und verwaltetes Netzwerk mit 99,9 % Betriebszeit und QoS-Unterstützung (Quality of Service, Dienstqualität). Dies ermöglicht eine bessere Leistung für Echtzeitmedien, wenn die Netzwerke überlastet sind.
  
 **Microsoft-Netzwerk** Dies ist das Netzwerksegment innerhalb Ihres Gesamtnetzwerks, das die Office 365-Dienste unterstützt. Hierzu gehört die gesamte Kommunikation zwischen Onlineservern für Office 365, beispielsweise Datenverkehr, der den Backbone des Microsoft-Netzwerks durchläuft und zwischen verschiedenen geografischen Regionen übermittelt wird.
  
### Arten von Datenverkehr

Der Netzwerkdatenverkehr für Skype for Business Online lässt sich in zwei Hauptkategorien unterteilen. Diese werden im Anruffluss jeweils als eigener Pfad angezeigt:
  
 **Echtzeitmedien** sind Daten, die innerhalb von RTP (Real-Time Transport-Protokoll) gekapselt sind und Audio-, Video-, Anwendungsfreigabe- und Dateiübertragungs-Workloads unterstützen. Im Allgemeinen ist der Medienverkehr hochgradig latenzsensitiv. Daher ist es in Ihrem Sinne, wenn dieser Datenverkehr auf einem möglichst direkten Weg übermittelt wird. Aus diesem Grund sollte UDP als Transportschichtprotokoll verwendet werden, weil TCP eine höhere Latenz mit sich bringt.
  
 **Signalisierung** ist die Kommunikationsverbindung zwischen Client und Server oder mit anderen Clients, die zur Steuerung von Aktivitäten (z. B. wenn ein Anruf initiiert wird) und für die Zustellung von Chatnachrichten verwendet wird. Der Signalisierungsverkehr verwendet überwiegend das SIP-Protokoll. Einige Clients verwenden jedoch HTTP-basierte REST-Schnittstellen. Einfach gesagt, haben wir es bei dieser Art des Datenverkehrs mit diversen Signalisierungen zu tun, die über HTTP- und HTTPS- oder TLS-Verbindungen übermittelt werden können. Ein wichtiger Aspekt ist, dass dieser Datenverkehr wesentlich weniger latenzsensitiv ist. Allerdings kann es zu Dienstausfällen oder zur Unterbrechung von Anrufen wegen Zeitüberschreitungen kommen, wenn die Latenz zwischen den Endpunkten mehrere Sekunden überschreitet.
  
Die Ziele für diesen Datenverkehr finden Sie für alle Office 365-Dienste unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Für jede URL wird angegeben, ob dieser Teil des Datenverkehrs über ExpressRoute für Office 365 laufen kann. Diagramme, die zeigen, dass das Internet auch bei Aktivierung von ExpressRoute noch für bestimmten Datenverkehr verwendet wird, finden Sie unter [Azure ExpressRoute für Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Wichtig ist die Erkenntnis, dass selbst URLs, die nominell über ExpressRoute geroutet werden können, auch über das Internet geroutet werden können. Dies bedeutet, dass die Entscheidung, ob das Internet oder ExpressRoute verwendet wird, in einigen Szenarien vom Clientstandort und von der Konfiguration der Proxyserver und Firewalls abhängt. Wichtig ist auch, dass Internetverbindung erforderlich ist, selbst wenn Sie ExpressRoute bei einem ExpressRoute-Partner erwerben, weil nicht alle mit Office 365 verbundenen URLs ExpressRoute nutzen können. 
  
Folgender Datenverkehr kann nur über das Internet gesendet werden: allgemein vom Internet abhängiger Datenverkehr wie Zertifikatsperrlisten (Certificate Revocation Lists, CRLs), DNS-Lookups und Namensauflösungen, URLs für freigegebene Office 365-Dienste wie z. B. das Office 365 Admin Center sowie einige nicht an Echtzeit gebundene Kommunikationsfunktionen von Skype for Business Online, wie zum Beispiel Telemetrie und Partnerverbund für die Interoperabilität mit Skype für Heimanwender. Auch für Skype-Livekonferenzen gestreamte Medien gehören hierzu. Weitere Überlegungen für die Planung Ihres Netzwerkroutings, die für Ihre Entscheidungen relevant sein können, finden Sie unter [Routing mit ExpressRoute für Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408). 
  
## Grundsätze für Anrufflüsse bei Skype for Business

Bevor wir die spezifischen Anruffluss-Szenarien näher betrachten, sollen hier sechs allgemeine Grundsätze erläutert werden, die für das Verständnis von Anrufflüssen bei Skype for Business wichtig sind.
  
1. Eine Skype for Business-Konferenz wird in derselben Region gehostet, in der der Konferenzorganisator verwaltet wird. Das Hosting erfolgt in der Office 365-Cloud, sofern der Organisator Skype for Business Online verwendet. Wenn der Besprechungsorganisator hingegen lokaler Benutzer ist, wird die Konferenz in einem lokalen Datencenter gehostet.
    
2. Der von einem Client in einer gehosteten Konferenz gesendete Medienverkehr fließt immer zu dem Server, auf dem die Konferenz gehostet wird. Hierbei kann es sich um einen lokalen Server in einem von Ihnen verwalteten Datencenter handeln oder um einen Onlineserver in der Office 365-Cloud. Für den Medienfluss für Onlinekonferenzen wird jedoch immer ein Edgeserver verwendet.
    
3. Der Medienverkehr für Peer-to-Peer-Anrufe wird auf der direktesten verfügbaren Route übermittelt. Die bevorzugte Route geht direkt zum externen Peer (Client). Ist diese Route jedoch aufgrund einer Blockierung des Datenverkehrs durch eine Firewall oder Ähnliches nicht verfügbar, so wird der Datenverkehr über einen oder mehrere Edgeserver übermittelt.
    
4. Der Signalisierungsverkehr wird immer auf den Server geleitet, auf dem der Benutzer beheimatet ist. Dies kann entweder ein Online-Server oder ein lokaler Server sein. Ein Edgeserver wird verwendet, wenn eine direkte Verbindung mit dem Front-End-Server nicht möglich ist.
    
5. Benutzer, die an einer online gehosteten Konferenz teilnehmen, verwenden immer einen Edgeserver (oder zwei, sofern dies aufgrund der Client-Firewallkonfigurationen erforderlich ist).
    
6. Benutzer, die an einer lokal gehosteten Konferenz teilnehmen, nutzen in der Regel keinen Edgeserver, wenn sie die Verbindung von demselben Netzwerk aus herstellen, das auch die lokale Bereitstellung enthält. Benutzer, die die Verbindung von außerhalb Ihres Netzwerks herstellen, nutzen hingegen einen oder zwei Edgeserver. 
    
Nähere Informationen zum gewählten Medienpfad finden Sie unter [ICE - Edge-Medienverbindungen](https://aka.ms/AVEdge). In diesem Video wird Lync Server 2013 behandelt. Die Grundsätze und Protokolle gelten aber auch für Skype for Business.
  
## Skype for Business-Anrufflüsse mit ExpressRoute

Sie kennen jetzt die vier verschiedenen Netzwerksegmente und einige allgemeine Grundsätze für Skype for Business-Anrufflüsse. Anhand dieser Informationen können Sie nun nachvollziehen, welcher Skype for Business-Datenverkehr ein ExpressRoute-Netzwerksegment durchläuft.
  
Im Allgemeinen durchläuft Netzwerkdatenverkehr die ExpressRoute-Verbindung, wenn sich ein Endpunkt in Ihrem Netzwerk verbindet und der andere Endpunkt im Office 365-Datencenter. Dies beinhaltet den Signalisierungsverkehr zwischen Client und Server, den während der Telefonkonferenzen verwendeten Medienverkehr oder Peer-to-Peer-Anrufe, die einen Online-Edgeserver verwenden.
  
Der Datenverkehr läuft nicht über die ExpressRoute-Verbindung, wenn beide Endpunkte direkt über das Internet miteinander kommunizieren können oder wenn sich beide innerhalb Ihres Netzwerks befinden. Dies gilt auch für Medien bei Peer-zu-Peer-Anrufen, Datenverkehr aus dem Internet, der an eine lokale Bereitstellung gesendet wird, oder jeglichen Datenverkehr zwischen dem Internet und Office 365-Edgeservern. Ein Beispiel hierfür ist ein Benutzer, der von einem Hotel aus an einer Onlinekonferenz teilnimmt.
  
## Allgemeines zum Skype for Business-Anruffluss

Damit Sie die oben beschriebenen Grundsätze über Skype for Business-Anrufflüsse anwenden können, enthält der nächste Abschnitt in diesem Artikel eine Reihe von Diagrammen als Referenz. Dabei handelt es sich nicht um eine vollständige Liste aller denkbaren Anrufflüsse. Vielmehr sollen Ihnen diese Informationen als Orientierung für die Anwendung der oben beschriebenen Grundsätze dienen. Die Szenarios in den Diagrammen wurden außerdem unter dem Gesichtspunkt ausgewählt, dass sie häufige Bereitstellungstypen abdecken: Online, Hybrid, Cloud Connector und in einem speziellen Fall Skype-Livekonferenz.
  
> [!NOTE]
> Ein Teil des von Skype for Business genutzten Datenverkehrs kann nicht über ExpressRoute geleitet werden und verwendet daher immer einen Internetpfad. Anhand der Informationen unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) können Sie feststellen, welche URLs betroffen sein können.
  
### Von einem Kundennetzwerk aus initiierter Peer-zu-Peer-Anruf für Office 365-Benutzer
<a name="bk_Figure2"> </a>

Der Medienverkehr für Peer-to-Peer-Anrufe wird immer auf der direktesten verfügbaren Route an das Ziel übermittelt. Der Signalisierungsverkehr wird jedoch an ein Office 365-Datencenter geleitet, in dem der Online-Benutzer beheimatet ist. Da sich beide Benutzer im selben WAN befinden und nichts eine direkte Kommunikation der Clients verhindert, erfolgt der Medienfluss direkt zwischen den beiden. Der Signalisierungsverkehr läuft bei beiden Benutzern über die ExpressRoute-Verbindung, deren Ziel das Rechenzentrum der jeweiligen Organisation ist. Die folgende Darstellung zeigt den Anruffluss in diesem Szenario.
  
 **Peer-to-Peer-Anruffluss**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt
<a name="bk_Figure3"> </a>

In dem Peer-zu-Peer-Beispiel nimmt der Medienverkehr immer die direkteste Route zu seinem Ziel. Bei einer Onlinekonferenz befindet sich das Ziel jedoch in der Office 365-Cloud. Dies bedeutet, dass der Medienverkehr für alle Benutzer, die von Ihrem Netzwerk aus an der Konferenz teilnehmen, über die ExpressRoute-Verbindung läuft und dass der Signalisierungsverkehr zur Office 365-Cloud geleitet wird. Die nachfolgende Grafik zeigt, dass sowohl Medien als auch Signalisierungen für einen Benutzer innerhalb Ihres Netzwerks über die ExpressRoute-Verbindung laufen. Für Benutzer, die sich außerhalb Ihres Netzwerks (beispielsweise von einem Café oder Hotel aus) mit dem Internet verbunden haben, werden diese Daten hingegen direkt über das Internet geleitet.
  
Wichtig ist, dass sich der Standort einer Konferenz nach dem Besprechungsorganisator richtet und nicht nach den Teilnehmern. Wenn die Besprechung also von einem lokalen Kunden geplant wird, fließt der Medienverkehr nicht über ExpressRoute zur Office 365-Cloud, sondern wird stattdessen über das Internet zum lokalen Datencenter des Besprechungsorganisators geleitet.
  
Der Zielort für Medien für Online-Konferenzen ist das Datencenter innerhalb der Office 365-Cloud. Das Datencenter kann sich jedoch in einer anderen geografischen Region befinden als die Benutzer, die an der Konferenz teilnehmen. Hierfür gibt es zwei Möglichkeiten:
  
- Wenn der Besprechungsorganisator in einem anderen Unternehmen tätig ist als die Teilnehmer und die Organisation für den Organisator an einem anderen geografischen Standort oder in einem anderen Land bzw. einer anderen Region gehostet wird.
    
- Wenn sich ein Benutzer aus einem anderen Land bzw. einer anderen Region teilnimmt als dem Land bzw. der Region, wo sich der Standort der Organisation des Unternehmens befindet. Dies kann der Fall sein, wenn das Unternehmen multinational ist oder wenn der Benutzer auf Reisen ist.
    
Das Gute an der Verwendung von ExpressRoute in diesem Szenario ist, dass Daten, die dem ExpressRoute-Pfad folgen, mit dem ExpressRoute Premium-Add-On automatisch über den Backbone von Microsoft zum Datencenter der Organisation der Besprechung geleitet werden. Die geografische Region des Organisators spielt dabei keine Rolle.
  
 **Anruffluss bei Online-Benutzer in Onlinebesprechung**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### Teilnahme an einer Konferenz, die von einem lokalen Benutzer in einer Hybrid-Bereitstellung gehostet wird
<a name="bk_Figure3"> </a>

Bedenken Sie, dass sich die Frage, welche Konferenzserver die gehosteten Konferenzen unterstützen, danach richtet, wo der Besprechungsorganisator verwaltet wird. In diesem Szenario fließen die Medien für alle Benutzer, die an einer von einem lokalen Benutzer in einer Hybridbereitstellung geplanten Konferenz teilnehmen, zu einem lokalen Datencenter. Die Signalisierung für online verwaltete Benutzer fließt über deren Organisation in der Office 365-Cloud, während die Medien eine Direktverbindung zu nutzen versuchen. In diesem Szenario verbinden sich beide Benutzer innerhalb Ihres Netzwerks. Daher ist eine direkte Medienverbindung möglich. ExpressRoute wird also nur für den Signalisierungsverkehr für den online verwalteten Benutzer verwendet. Wenn sich ein online verwalteter Benutzer vom Internet aus verbindet und die Verbindung über einen Online-Edgeserver hergestellt wird, können die Medien über ExpressRoute laufen.
  
 **Anruffluss bei einer von einem Hybrid-Benutzer gehosteten Konferenz**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### Lokale Edgeserver mit in Office 365 gehosteten Konferenzen
<a name="bk_Figure5"> </a>

Wenn ein Hybridbenutzer an einer online gehosteten Konferenz teilnimmt, wissen wir, dass die Signalisierung und die Medien an die Office 365-Cloud geleitet werden. Da der Benutzer vom Internet aus teilnimmt, würde normalerweise ein direkter Internetpfad verwendet. In einigen Fällen ist jedoch kein direkter Internetpfad verfügbar, beispielsweise aufgrund von Firewallbeschränkungen. In diesem Fall kann ein lokaler Edgeserver den Medienverkehr übermitteln. Hierdurch wird der Medienverkehr an Ihr lokales Netzwerk zurückgeleitet, bevor er über die ExpressRoute-Verbindung zur Office 365-Cloud übermittelt wird.
  
 **Lokale Benutzer, die von einem lokalen Edgeserver aus an einer Online-Telekonferenz teilnehmen**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### PSTN-Anruf mit Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Mit [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) wird die Anbindung an das Festnetz (PSTN-Anbindung) ermöglicht. Dabei werden lokale Ressourcen genutzt, zum Beispiel ein SIP-Trunk oder ein PSTN-Gateway oder ein minimales Hardwaregerät für die Integration mit Skype for Business. Mit Cloud Connector Edition werden Benutzer online verwaltet und handeln als normale Onlinebenutzer, wenn keine Anrufpläne beteiligt sind. Die Signalisierungen in PSTN-Szenarien fließen zwischen dem Client und der Cloud über eine ExpressRoute-Verbindung, sofern diese verfügbar ist. Der Medienverkehr bleibt in Ihrem WAN. In diesem Fall kehren die Signalisierungen bei der Office 365-Cloud um und enden bei Cloud Connector.
  
 **PSTN-Anruf über das Telefonsystem in Office 365 und Cloud Connector**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### Skype-Livekonferenz mit Benutzern, die von einem Kundennetzwerk aus teilnehmen
<a name="bk_Figure6"> </a>

Skype-Livekonferenz ist ein besonderer Anwendungsfall. In diesem Fall handelt es sich um eine zweiteilige Besprechung, deren Teile unterschiedliche Netzwerktransportprofile aufweisen. Der erste Teil ist die innere Besprechung. Im Hinblick auf die Netzwerkleistung ist dies der bedeutendere Teil. Dies ist der Echtzeitanteil der Besprechung. Er enthält einen oder mehrere Clientendpunkte, die sich mit dem Konferenzserver in der Office 365-Cloud verbinden. Die Daten, die über diesen Teil der Besprechung übermittelt werden, entsprechen genau dem Beispiel oben, in dem ein Office 365-Benutzer an einer Onlinekonferenz teilnimmt. 
  
Das Besondere an einer Skype-Livekonferenz ist die Tatsache, dass die Konferenz über einen Streamingübertragungsdienst an eine große Zahl von Konferenzteilnehmern verteilt wird. Dieser Streamingübertragungsdienst kann nicht über ExpressRoute geleitet werden. Stattdessen nutzt er das Internet mit der optionalen Unterstützung von Content Delivery Network-Diensten (CDN). Es ist hilfreich, sich klar zu machen, dass die Streamingübertragung ein unidirektionaler Medienfluss ist, denn die Teilnehmer hören zu, sprechen aber selbst nicht. Die Pufferung wird dabei unterstützt. Somit ist diese Form der Übertragung wesentlich weniger sensitiv gegenüber Problemen bei der Netzwerkleistung wie Latenz, Paketverlust und Jitter. Statt den Übertragungsdatenverkehr für diese Probleme zu optimieren, wird dieser für die Bandbreitennutzung optimiert, weil potenziell eine sehr große Zahl an Teilnehmern die gestreamten Medien empfängt.
  
 **Skype-Livekonferenz mit Benutzern aus einem Kundennetzwerk**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## Anrufflussmuster nach Entwicklungstyp

Anhand der oben angeführten Beispiele für häufig auftretende Anrufflüsse wurden die allgemeinen Grundsätze erläutert, die die Datenverkehrsmuster steuern. Die nachfolgenden Tabellen enthalten eine Übersicht über die Datenverkehrsmuster für eine große Kombination von Bereitstellungs- und Benutzerszenarien. Diese Tabellen erfassen nicht jede mögliche Kombination von Anrufflüssen. Sie können aber hilfreich sein, um die allgemeinen Grundsätze bei Anrufflüssen nachzuvollziehen.
  
Die Daten werden übermittelt und aufgeführt, als seien sie für die Organisation lokal. Sie verlassen das Kundennetzwerk, das Internet oder ExpressRoute dabei nicht. Die nachfolgend aufgeführten Muster basieren auf den häufigsten Netzwerkeinstellungen. Hierzu gehören beispielsweise Firewalls, Partnerverbund und Internet. Dabei wird von der Annahme ausgegangen, dass alle Organisationen, die an Anrufflüssen mit mehreren Parteien oder mit Partnerverbunden beteiligt sind, ExpressRoute haben. In der Praxis könnte das Vorhandensein unterschiedlicher Einstellungen zu Datenverkehrsmustern führen, die von den nachfolgend aufgeführten Mustern abweichen.
  
### Anrufflüsse bei Skype for Business Online

Die Verwendungsszenarien für Skype for Business Online umfassen Benutzer, die online verwaltet werden und entweder von Ihrem internen Netzwerk aus oder vom Internet aus anrufen. Lokale Server kommen in diesen Szenarien nicht vor. Daher werden alle Medien in Bezug auf Konferenzen oder PSTN-Anrufe zur Office 365-Cloud fließen, und der Edgeserver der Onlinebenutzer befindet sich ebenfalls in der Cloud.
  
 **Übersicht über Anrufflüsse bei Skype for Business Online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Nutzungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Notizen** <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, beide in Ihrem Netzwerk.  <br/> |ExpressRoute  <br/> |lokal  <br/> |[Von einem Kundennetzwerk aus initiierter Peer-zu-Peer-Anruf für Office 365-Benutzer](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, einer in Ihrem Netzwerk (intern) und der andere Client im Internet (extern)  <br/> |Interner Benutzer: ExpressRoute  <br/> Externer Benutzer: Internet  <br/> |Interner Benutzer: ExpressRoute  <br/> Externer Benutzer: Internet zum Office 365-Edgeserver.  <br/> |[Von einem Kundennetzwerk aus initiierter Peer-zu-Peer-Anruf für Office 365-Benutzer](call-flow-using-expressroute.md#bk_Figure2) <br/> |Dabei wird vorausgesetzt, dass die Firewall direkte Verbindungen zwischen Clients blockiert, sodass ein Online-Edgeserver erforderlich ist. Der Datenverkehr vom internen Benutzer zum Online-Edgeserver folgt einem ähnlichen Pfad wie der Datenverkehr zum Konferenzserver für die Telefonkonferenz.  <br/> |
|Peer-to-Peer-Anruf zu einem Benutzer in einer Partnerorganisation  <br/> |Zwei Clients, einer auf Ihrem Netzwerk (intern) und der andere beim Online-Benutzer auf dem Netzwerk der Partnerorganisation (Verbund).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> |Dabei wird vorausgesetzt, dass die Firewall direkte Verbindungen zwischen Clients blockiert, sodass ein Online-Edgeserver erforderlich ist. Der Datenverkehr vom internen Benutzer zum Online-Edgeserver folgt einem ähnlichen Pfad wie der Datenverkehr eines Konferenzservers für die Telefonkonferenz.  <br/> |
|Teilnahme an einer Telekonferenz durch einen Benutzer im Netzwerk eines Kunden  <br/> |Client auf Ihrem Netzwerk und Konferenzserver in der Office 365-Cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnahme an einer Telefonkonferenz durch einen Benutzer im Internet  <br/> |Der Client befindet sich im Internet und der Konferenzserver in der Office 365-Cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Teilnahme an einer Konferenz, die vom lokalen Server eines anderen Unternehmens gehostet wird  <br/> |Client auf Ihrem Netzwerk und Konferenzserver im externen Rechenzentrum.  <br/> |Internet  <br/> |Internet  <br/> |Nicht anwendbar  <br/> |Der Konferenzserver, der die Konferenz hostet, befindet sich im lokalen Netzwerk eines anderen Kunden. Daher würden keine Daten durch die Microsoft-Cloud geleitet.  <br/> |
|PSTN-Anruf  <br/> |Client im Netzwerk eines Kunden und Telefonsystemserver in der Office 365-Cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN-Anruf  <br/> |Client im Internet und Telefonsystemserver in der Office 365-Cloud  <br/> |Internet  <br/> |Internet  <br/> |Nicht anwendbar  <br/> |Die Medien und Signalisierungen fließen zum Office 365-Datencenter. Der Clientendpunkt befindet sich im Internet. Daher fließen alle Daten zum Microsoft-Datencenter über das Internet (auch wenn ein Online-Edgeserver für Verbindungen erforderlich ist).  <br/> |
   
> [!NOTE]
> ExpressRoute wird auf dem Medienpfad von einem Benutzer im Unternehmensnetz zu einem Online-Edgeserver verwendet. ExpressRoute wird jedoch nicht verwendet, wenn der Edgeserver für die lokale Bereitstellung eines anderen Kunden verwendet wird. 
  
### Anrufflüsse bei Skype for Business Hybrid

Hybridanrufflüsse kommen zum Tragen, wenn Sie eine Skype for Business-Bereitstellung haben, bei der mindestens einige Benutzer lokal verwaltet werden. Die Anrufflüsse in diesem Abschnitt umfassen sowohl lokale Konferenzen als auch Peer-zu-Peer- oder PSTN-Anrufe mit mindestens einem lokal verwalteten Benutzer.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Nutzungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Notizen** <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, beide auf dem Kundennetzwerk und lokal beheimatet  <br/> |Lokal  <br/> |lokal  <br/> |[Von einem Kundennetzwerk aus initiierter Peer-zu-Peer-Anruf für Office 365-Benutzer](call-flow-using-expressroute.md#bk_Figure2) <br/> |Da die Benutzer lokal beheimatet sind, fließen die Signalisierungen lokal zum lokalen Rechenzentrum statt zur Office 365-Cloud.  <br/> |
|Peer-to-Peer-Anruf  <br/> |Zwei Clients, die sich beide vom Kundennetzwerk aus verbinden. Einer ist online beheimatet, der andere lokal.  <br/> |Online-Benutzer: ExpressRoute  <br/> Lokaler Benutzer: lokal  <br/> |lokal  <br/> |[Von einem Kundennetzwerk aus initiierter Peer-zu-Peer-Anruf für Office 365-Benutzer](call-flow-using-expressroute.md#bk_Figure2) <br/> |Nur der online beheimatete Benutzer sendet Signalisierungsverkehr zur Office 365-Cloud.  <br/> |
|Peer-zu-Peer-Anruf an einen Benutzer in einer Partnerorganisation  <br/> |Zwei Clients, ein lokaler Benutzer im Kundennetzwerk (intern) und ein Online-Benutzer im Netzwerk des Partnerunternehmens (Verbund).  <br/> |Interner Benutzer: lokal  <br/> Partnerbenutzer: ExpressRoute  <br/> |Internet oder ExpressRoute (je nachdem, ob ein Online- oder lokaler Edgeserver verwendet wird)  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) und Teil eines[Lokale Edgeserver mit in Office 365 gehosteten Konferenzen](call-flow-using-expressroute.md#bk_Figure5) (für Medienverkehr). <br/> |Dabei wird vorausgesetzt, dass eine Firewall direkte Verbindungen zwischen Clients blockiert, sodass ein Online-Edgeserver erforderlich ist. ICE-Aushandlung bietet sowohl Online-Edgeserver (durch den Onlinebenutzer) als auch lokale Edgeserver (durch den lokalen Benutzer) für die Verbindung an.  <br/> |
|Teilnahme an einer Telefonkonferenz durch einen Benutzer im Kundennetzwerk (von Online-Benutzer geplante Konferenz)  <br/> |Lokaler Benutzer auf Ihrem Netzwerk und Konferenzserver in der Office 365-Cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Online-Benutzer in Ihrem Netzwerk, der an einer online gehosteten Konferenz teilnimmt](call-flow-using-expressroute.md#bk_Figure3) <br/> |Serverressourcen für die Telefonkonferenz werden durch den Besprechungsorganisator definiert. In diesem Fall wurde die Konferenz durch einen Onlinebenutzer geplant. Die Ressourcen befinden sich also in der Office 365-Cloud.  <br/> |
|PSTN-Anruf  <br/> |Lokaler Benutzer in Ihrem Netzwerk und lokalen Skype for Business-Rechenzentrum.  <br/> |Lokal  <br/> |Lokal  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Vergleichbares Szenario für die Verwendung von Cloud Connector Edition, außer dass der Benutzer lokal beheimatet ist, sodass die Signalisierung in Ihrem Netzwerk verbleibt.  <br/> |
   
### Anrufflüsse für Skype for Business mit Cloud Connector

Benutzer, die sich mit Cloud Connector Edition verbinden, sind alle online beheimatet. Dies bedeutet, dass die Konferenzen online sind und dass die Signalisierung den gleichen Mustern folgt wie für Online-Benutzer. Für Szenarien außer PSTN-Anrufen ist der Anruffluss genau so, wie oben für Skype for Business Online beschrieben.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Nutzungsszenario** <br/> |**Endpunkte** <br/> |**Signalisierungspfad** <br/> |**Medienpfad** <br/> |**Beispielfluss** <br/> |**Notizen** <br/> |
|PSTN-Anruf  <br/> |Online-Benutzer in Ihrem Netzwerk, der Cloud Connector Edition nutzt.  <br/> |lokal  <br/> |lokal  <br/> |[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN-Anruf  <br/> |Online-Benutzer im Internet, der Cloud Connector Edition nutzt.  <br/> |Internet  <br/> |Internet  <br/> |Kombination von [Lokale Edgeserver mit in Office 365 gehosteten Konferenzen](call-flow-using-expressroute.md#bk_Figure5) und[PSTN-Anruf mit Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Internetbenutzer verbinden sich über den Edgeserver, der in Cloud Connector enthalten ist, und Cloud Connector verbindet sich mit dem Festnetz.  <br/> |
   

