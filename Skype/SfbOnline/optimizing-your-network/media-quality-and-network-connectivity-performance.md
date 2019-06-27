---
title: Medienqualität und Leistung der Netzwerkkonnektivität
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: In diesem Thema werden die Anforderungen an die Netzwerkleistung für Skype for Business Online-Dienste und die Art und Weise erläutert, wie Sie das Internet oder Express Route für die Verbindung zwischen Ihrem Netzwerk und Skype for Business Online verwenden können, basierend auf Ihrer Einschätzung des Netzwerks. Connectivity. Wenn Sie sich für die Bereitstellung von Azure Express Route für dedizierte Konnektivität mit Office 365 entschieden haben, finden Sie in diesem Dokument auch Anleitungen zum Planen Ihrer Express Route-Verbindungen in verschiedenen Szenarien für die Bereitstellung von Skype for Business Online.
ms.openlocfilehash: 5818c07bcc939d18275409fd34bb627be2f2abd9
ms.sourcegitcommit: 4fb1c691f0f84d47e215c9c1775da9bdba875f61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "35253719"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online

In diesem Thema werden die Anforderungen an die Netzwerkleistung für Skype for Business Online-Dienste und die Art und Weise erläutert, wie Sie das Internet oder Express Route für die Verbindung zwischen Ihrem Netzwerk und Skype for Business Online verwenden können, basierend auf Ihrer Einschätzung des Netzwerks. Connectivity. Wenn Sie sich für die Bereitstellung von Azure Express Route für dedizierte Konnektivität mit Office 365 entschieden haben, finden Sie in diesem Dokument auch Anleitungen zum Planen Ihrer Express Route-Verbindungen in verschiedenen Szenarien für die Bereitstellung von Skype for Business Online.
  
Die Qualität von Echt Zeit Medien (Audio, Video und Anwendungsfreigabe) über IP wird von der Qualität der End-to-End-Netzwerkkonnektivität stark beeinflusst. Für optimale Medienqualität in Skype for Business Online benötigen Sie eine Verbindung von hoher Qualität zwischen Ihrem Unternehmensnetzwerk und Skype for Business Online. Am besten orientieren Sie sich beim Einrichten der Konnektivität zwischen dem internen Netzwerk und der Cloud an der Kapazität des Netzwerks, damit auch Spitzendatenaufkommen für Skype for Business Online über alle Verbindungen kein Problem darstellen.
  
Azure Express Route ist keine Voraussetzung für Office 365-Dienste wie Skype for Business Online. Azure Express Route ist jedoch eine der verfügbaren Bereitstellungsoptionen, mit denen Sie sicherstellen können, dass die Konnektivität zu Office 365 den Anforderungen an die Netzwerkleistung von Skype for Business entspricht und die optimale Nutzung von Skype for Business Online-Medien gewährleistet. Qualitätserfahrung.
  
> [!TIP]
> In diesem Thema finden Sie zwar allgemeine Anleitungen zur Netzwerkleistung, aber vollständige Anleitungen für die Netzwerkbewertung liegen außerhalb des Umfangs dieses Dokuments. Wenn Sie eine Liste der Skype for Business Online-Partner finden möchten, die Ihnen bei der Messung der Netzwerkleistung im Rahmen einer gründlichen und vollständigen Netzwerkbewertung helfen können, besuchen Sie bitte die [Skype for Business Partner-Lösungen](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Anforderungen an die Netzwerkkonnektivität für Skype for Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Faktoren, die Auswirkungen auf die Qualität von Skype for Business Online-Medien haben

Es gibt viele verschiedene Faktoren, die zu Skype for Business Online-Medien in Echtzeit (Audio-, Video-und Anwendungsfreigabe) beitragen, die die verwendeten Geräte, die Umgebung und die Netzwerkkonnektivität umfassen. 
  
#### <a name="devices"></a>Geräte

In einer echt Zeit Mediensitzung wirken sich Medien, die von allen Teilnehmern wie Headsets und Webcams verwendet werden, auf die gesamte Audio-und Videoqualität aus. Geräte von niedrigerer Qualität oder Geräte mit falschen Treibern erzeugen Audiomedien mit einer schlechteren allgemeinen Tonqualität sowie Videomedien mit einer schlechteren Bildqualität. Zertifizierte Geräte oder Geräte von hoher Qualität dagegen verbessern Echounterdrückung, Rauschunterdrückung und Videoauflösung und verringern die Latenz.
  
Obwohl zertifizierte Audio-und Video Mediengeräte nicht erforderlich sind, empfiehlt es sich, für Skype for Business zertifizierte Geräte für optimale Mediennutzung zu empfehlen. Eine Liste aller zertifizierten Skype for Business-Geräte finden Sie unter [Telefone und Geräte für Skype for Business](https://technet.microsoft.com/en-us/office/dn947482). Sie können das [Skype for Business Online-Dashboard für die Anrufqualität](/microsoftteams/turning-on-and-using-call-quality-dashboard)verwenden, das im **Skype for Business Admin Center**zu finden ist, um zu überprüfen, ob die verwendeten Geräte ordnungsgemäß funktionieren und die Qualität der Audio-und Video Medien überwachen.
  
> [!TIP]
> **Für die optimale Nutzung von Skype for Business-Medienqualität ist ein zertifiziertes Gerät erforderlich**.
  
Beachten Sie, dass alle Mediengeräte, Skype for Business-Clients und Skype for Business-Server, über die Echt Zeit Medien fließen, einige Latenzzeiten einführen. Die Wartezeit für Geräte-und Software Verarbeitung sowie die Netzwerklatenz haben einen großen Einfluss auf die Gesamtlatenz und die Endbenutzererfahrung.
  
#### <a name="environment"></a>Umgebung

Die Umgebung und das Umfeld, in dem sich Nutzer treffen und Audio- und Videogeräte verwenden, stellen ebenfalls einen wichtigen Faktor für die Audio- und Videoqualität dar. Nutzer, die aus einer lauten Umgebung anrufen, hören gedämpften und undeutlichen Ton mit Echos. Nutzer in einer dunklen oder lichtarmen Umgebung können keine hellen und scharfen Videos erzeugen. In einem Konferenzraum wirkt sich die Position des Mikrofons und des Videogeräts direkt auf die Ton- und Bildqualität für die Teilnehmer aus.
  
Wenn Sie ein klareres Bild von der Audio-und Videoqualität eines Benutzers erhalten möchten, verwenden Sie **** > das Skype for Business-APP-**options** > **-Audiogerät oder-** **Videogerät** , um Änderungen am verwendeten Gerät vorzunehmen und die Einstellungen anzupassen.

#### <a name="network"></a>Netzwerk

Die Qualität des Echt Zeit Mediums über das IP-Netzwerk wird stark von der Qualität der Netzwerkkonnektivität beeinflusst, vor allem aber von der Anzahl der folgenden:
  
- **Latenz** Dies ist die Zeit, die erforderlich ist, um ein IP-Paket von Punkt a nach Punkt B im Netzwerk abzurufen. Diese Verzögerung der Netzwerk Propagierung ist im Wesentlichen an den physikalischen Abstand zwischen den beiden Punkten und der Lichtgeschwindigkeit gebunden, einschließlich des zusätzlichen Overhead, der von den verschiedenen Routern dazwischen genommen wird. Die Wartezeit wird als unidirektionale oder Roundtrip-Zeit (Round-Trip Time, RTT) gemessen.
    
- **Paketverlust** Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Burst Verlusten, die zu einem vollständigen Audioausschnitt führen.
    
- **Zwischen Paket-Ankunfts Jitter oder einfach Jitter** Dies ist die durchschnittliche Verzögerungs Änderung zwischen aufeinanderfolgenden Paketen. Die modernste VoIP-Software, einschließlich Skype for Business, kann sich durch Pufferung an einige Jitter-Ebenen anpassen. Dies ist nur der Fall, wenn der Jitter die Pufferzeit überschreitet, die ein Teilnehmer auf die Effekte von Jitter hinweist.
    
> [!NOTE]
>  Die Pufferung für Jitter erhöht die End-to-End-Latenz.
  
Mit vielen gleichzeitigen Skype for Business Online-Mediensitzungen in Echtzeit sowie anderen Netzwerkdatenverkehr, der von anderen Office 365-Diensten und anderen Geschäftsanwendungen generiert wird, stellen Sie sicher, dass genügend Bandbreite über den gesamten Netzwerkpfad vorhanden ist, der die Verbindung zwischen Ihrem Netzwerk und dem Skype for Business Online-Dienst ist wichtig, um Netzwerküberlastung zu vermeiden und eine hervorragende Qualität der Medien in Echtzeit zu gewährleisten (Audio-, Video-und Anwendungsfreigabe). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementieren von Quality of Service (QoS) in überlasteten Netzwerken

Darüber hinaus beeinträchtigt die Verkehrsüberlastung in einem Netzwerk die Medienqualität erheblich. Damit Audio-und Videopakete das Netzwerk schneller durchlaufen und über anderen Netzwerkdatenverkehr in einem überlasteten Netzwerk priorisiert werden können, kann Quality of Service (QoS) verwendet werden, um eine optimale Endbenutzererfahrung bei der Audio-und Videokommunikation zu gewährleisten.
  
QoS bietet eine Möglichkeit, Netzwerkpaketen, die Audio-oder Videodaten übertragen, höhere Prioritäten zuzuweisen. Durch das Zuweisen einer höheren Priorität für diese Pakete können Audio-und Videokommunikation schneller und mit weniger Unterbrechungen über das Netzwerk erfolgen als Netzwerksitzungen, die Dinge wie Dateiübertragungen, Web-Browsing oder Datenbanksicherungen umfassen. Das liegt daran, dass die Netzwerkpakete, die standardmäßig für Dateiübertragungen oder Datenbank-Backups verwendet werden, als Priorität "Best Effort" zugewiesen werden und die Überlastung des Netzwerks nicht so stark beeinträchtigt wird. Wenn Sie den Medien (Audio-, Video-und Anwendungsfreigabe-Pakete) keine höhere Priorität zuweisen und diese auch als "Best Effort" zugewiesen lassen, werden Sie zusammen mit allen anderen Netzwerkdatenverkehr verarbeitet. Je nach Netzwerküberlastung wird dies möglicherweise zu einer niedrigeren Gesamtqualität der Audio-und Videoqualität für Ihre Benutzer.
  
Es wird dringend empfohlen, QoS in Ihrem Netzwerk zu implementieren, um sicherzustellen, dass Netzwerküberlastung in Ihrem Netzwerk keine Auswirkungen hat. Damit dies jedoch die maximale Auswirkung hat, müssen alle Netzwerkendpunkte QoS unterstützen, was bedeutet, dass alle Endpunkte QoS-Kennzeichnung und Paket Priorisierung berücksichtigen müssen. Skype for Business Online Services Ehren QoS-Kennzeichnung und Priorisierung innerhalb des Microsoft-Netzwerks. Datenverkehr, der über eine öffentliche Verbindung wie das Internet aus Ihrem Unternehmensnetzwerk an das Microsoft-Netzwerk weitergeleitet wird, behält jedoch keine QoS-Markierungen und eine Paket Priorisierung bei. Private Verbindungen von Ihrem Netzwerk zu Office 365 mithilfe von [Azure Express Route](https://azure.microsoft.com/services/expressroute/) bieten eine Bereitstellungslösung, die QoS-Markierungen und die Paket Priorisierung erhält, die wiederum die allgemeine Audio-und Videoqualität für Ihre Endbenutzer erhöhen.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Netzwerk Leistungsanforderungen zum Herstellen einer Verbindung mit Skype for Business Online
<a name="bkNetworkPerf"> </a>

Skype for Business-Echt Zeit Medien durchlaufen viele verschiedene Geräte, Client-apps, Server-Software und in verschiedenen Netzwerken. Die End-to-End-Latenz von Echt Zeit Medien ist die Gesamtanzahl der Latenzzeiten, die für alle Komponenten und Netzwerksegmente eingeführt werden. Die Qualität der End-to-End-Netzwerkverbindung wird vom Netzwerksegment mit der schlechtesten Qualität bestimmt. Dieses Segment fungiert als Engpass für diesen Netzwerkdatenverkehr.
  
Das folgende Diagramm zeigt einen unidirektionalen audiofluss in einer Konferenz von einem Skype for Business-Teilnehmer zu einem anderen.
  
![Express Route-Anruffluss.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In diesem Konferenz Szenario besteht der Medienpfad in den folgenden Netzwerksegmenten:
  
1. **Verbindung vom Benutzer 1 an den Rand des Microsoft-Netzwerks** Dazu gehören in der Regel eine Netzwerkverbindung wie WLAN oder Ethernet, die WAN-Verbindung vom Benutzer 1 zum Internet-Ausgangspunkt (Ihr Netzwerk-Edge-Gerät) und die Internetverbindung von Ihrem Netzwerk-Edge zu Microsoft Network Edge.
    
2. **Verbindung innerhalb des Microsoft-Netzwerks** Dies ist zwischen dem Microsoft Edge und dem Skype for Business Online-Rechenzentrum, in dem die A/V-Konferenzserver verwendet werden.
    
3. **Verbindung innerhalb des Microsoft-Netzwerks** Dies liegt zwischen dem Skype for Business Online-Rechenzentrum und dem Microsoft Network Edge.
    
4. **Verbindung von Microsoft Network Edge zu Benutzer 2** Dazu gehören die Internetverbindung von Ihrem Netzwerk-Edge zu Microsoft-Netzwerk-Edge, die WAN-Verbindung von Benutzer 2 mit dem Internet-Ausgangspunkt (Ihr Netzwerk-Edge) und die Netzwerkverbindung wie eine WLAN-oder Ethernet-Verbindung.
    
Das folgende Diagramm zeigt die Aufteilung von Komponenten und Netzwerksegmenten eines PSTN-Anrufs in Skype for Business Online:
  
![Express Route-Anruffluss des PSTN-Netzbetreibers.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In einem PSTN-Anruf Szenario kreuzt der Medienpfad die folgenden Netzwerksegmente:
  
1. **Verbindung von einem Skype for Business-Client-Anrufer an den Rand des Microsoft-Netzwerks** Dies umfasst in der Regel eine Netzwerkverbindung wie WLAN oder Ethernet, die WAN-Verbindung vom Skype for Business-Client-Anrufer an den Internet-Ausgangspunkt (Ihr Netzwerk-Edge-Gerät) und die Internetverbindung von Ihrem Netzwerk-Edge zu Microsoft Network Edge.
    
2. **Verbindung innerhalb des Microsoft-Netzwerks** Dies liegt zwischen dem Microsoft Edge-und dem Skype for Business Online-Rechenzentrum, in dem ein Vermittlungs Server verwendet wird.
    
3. **Verbindung innerhalb des Microsoft-Netzwerks** Dies liegt zwischen dem Skype for Business Online-Rechenzentrum und dem Microsoft Network Edge.
    
4. **Verbindung zwischen Microsoft Network und den Partnern des PSTN-Dienstanbieters** Dies ist die Verbindung, die vorhanden ist, um einen PSTN-Anruf über den Skype for Business-Client zu tätigen, der sich außerhalb des Microsoft-Netzwerks befindet.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Netzwerk Leistungsanforderungen von einem Skype for Business-Client zu Microsoft Network Edge
<a name="bkSfBClienttoEdge"></a>

Für eine optimale Medienqualität von Skype for Business sind für eine Verbindung vom Netzwerk Ihres Unternehmens zum Microsoft-Netzwerk Edge die folgenden Ziele für die Netzwerk Leistungsmetrik erforderlich. Dieses Segment des Netzwerks umfasst Ihr internes Netzwerk, dazu gehören alle WLAN-und Ethernet-Verbindungen, jeder Standort-zu-Standort-Datenverkehr über eine WAN-Verbindung, beispielsweise Multiprotocol Label Switching (MPLS) sowie das Internet oder Express Route-Partner. Verbindungen mit dem Microsoft-Netzwerk-Edge.
  
> [!CAUTION]
> **Die Konnektivität zwischen einem Skype for Business-Client in Ihrem Unternehmensnetzwerk und den Office 365-Diensten muss diesen folgenden Netzwerk Leistungsanforderungen und-Schwellenwerten entsprechen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |** Target** <br/> |
|Latenz (eine Möglichkeit)  <br/> |< 50ms  <br/> |
|Latenz (RTT oder Round-Trip-Zeit)  <br/> |< 100M  <br/> |
|Burst-Paketverlust  <br/> |<10% während eines 200M-Intervalls  <br/> |
|Paketverlust  <br/> |<1% in einem 15-minütigen Intervall  <br/> |
|Paket Inter-arrival Jitter  <br/> |<30ms während eines 15-15-Intervalls  <br/> |
|Paket Reihenfolge  <br/> |<0,05% Pakete außerhalb der Reihenfolge  <br/> |
   
 **Andere Leistungsziel Anforderungen:**
  
- Das Microsoft-Netzwerk verfügt über mehr als 160 Edge-Standorte weltweit. Wir arbeiten mit wichtigen Internet Dienstanbietern (ISP) weltweit über diese Edge-Websites. Das Latenz Metrik-Ziel setzt voraus, dass Ihre Unternehmenswebsite oder Ihre Websites und die Microsoft-Ränder auf demselben Kontinent sind.
    
- Die Website Ihres Unternehmens oder Ihre Websites für die Microsoft-Netzwerk-Edge-Verbindung umfassen den Zugriff auf den First Hop-Netzwerkzugriff, der WLAN-oder eine andere drahtlose Technologie sein kann 
    
- Das Netzwerk Leistungsziel übernimmt die richtige Bandbreite und/oder die Qualität der Dienstplanung. Anders ausgedrückt: Dies gilt direkt für Skype for Business in Echtzeit-Medien Verkehr, wenn die Netzwerkverbindung unter einer Spitzenlast liegt.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Netzwerk Leistungsanforderungen von Ihrem Netzwerk Edge zu Microsoft Network Edge
<a name="bkYourNetworkEdge"> </a>

Im folgenden finden Sie die Netzwerk Leistungsziele oder-Schwellenwerte, die für die Verbindung zwischen Ihrem Netzwerk-Edge und dem Microsoft-Netzwerk-Edge erforderlich sind. Dieses Segment des Netzwerks schließt das interne Netzwerk oder das WAN des Kunden aus und dient als Leitfaden beim Testen des Netzwerkdatenverkehrs, der über das Internet oder über ein Express Route-Partnernetzwerk gesendet wird und auch bei der Aushandlung einer Leistung verwendet werden kann. Vereinbarung zum Service Level (SLA) mit Ihrem Express Route-Anbieter.
  
> [!CAUTION]
> **Die Konnektivität zwischen dem Netzwerk Edge Ihres Unternehmens und dem Microsoft-Netzwerkrand muss diesen folgenden Netzwerk Leistungsanforderungen und-Schwellenwerten entsprechen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |** Target** <br/> |
|Latenz (eine Möglichkeit)  <br/> |< 30ms  <br/> |
|Latenz (RTT)  <br/> |< 60ms  <br/> |
|Burst-Paketverlust  <br/> |<1% während eines beliebigen 200 MS-Intervalls  <br/> |
|Paketverlust  <br/> |<0,1% in einem 15-15-Intervall  <br/> |
|Paket Inter-arrival Jitter  <br/> |<15ms während eines 15-15-Intervalls  <br/> |
|Paket Reihenfolge  <br/> |<0,01% Pakete außerhalb der Reihenfolge  <br/> |
   
 **Andere Leistungsziel Anforderungen:**
  
- Das Leistungsziel erfordert eine Verbindung zwischen dem Netzwerkrand Ihres Unternehmens und dem nächsten Microsoft-Netzwerk Edge, um sich auf demselben Kontinent zu befinden.
    
- Das Netzwerk Leistungsziel übernimmt die richtige Bandbreite und/oder die Qualität der Dienstplanung. Dies gilt auch für Skype for Business-Datenverkehr in Echtzeit, wenn die Netzwerkverbindung unter einer Spitzenlast liegt. Informationen zur richtigen Bandbreiten-und QoS-Planung finden Sie unter [Express Route und QoS in Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Messen der Netzwerkleistung
<a name="bkNetworkPerf"> </a>

Um die tatsächliche Netzwerkleistung, insbesondere für Latenz-und Paketverluste, von einer beliebigen Unternehmensnetzwerk-Website bis zu einem Netzwerkrand zu messen, können Sie Tools wie Ping, Test mit einer Reihe von Skype for Business-Media-Relay-Diensten verwenden, die von Microsoft Edge und Data ausgeführt werden. Center-Websites. 
  
Wenn Sie Internet Verbindungen mit dem Microsoft-Netzwerk testen möchten, sollten Sie die folgenden VIPs der Skype for Business-Medien Relays testen. Der *Anycast-VIP* wird in eine IP-Adresse eines Medien Relais auf einer Microsoft-Netzwerk-Edge-Website aufgelöst, die dem Test Speicherort am nächsten ist.
  
||||
|:-----|:-----|:-----|
|**IP-Adresse** <br/> |**Typ** <br/> |**Standort** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **Nachfolgend finden Sie einige allgemeine Empfehlungen für die Bewertung der Netzwerkleistung:**
  
- Sie sollten Ihr internes Netzwerk sowie die Verbindungen zu Office 365 bewerten.
    
- Sie sollten über einen längeren Zeitraum Daten für alle Ihre Netzwerke bewerten und sammeln. Wir empfehlen Ihnen, die Netzwerkleistung für eine mindestwoche zu testen, damit Sie Nutzungsmuster für alle Arbeitstage und Arbeitsstunden sehen können. Dadurch werden die Höchstzeiten angezeigt.
    
- Sie sollten mehrere Beispiele für Netzwerk Leistungsmessungen durchführen. Wir empfehlen, während des gesamten Zeitraums, in dem Sie Daten sammeln, alle 10 Minuten eine Messung von einer Unternehmenswebsite durch zu nehmen. Wenn Sie die Leistungsanforderungen des Skype for Business Online-Netzwerks vergleichen, nehmen Sie den 90-Perzentil-Messwert aus diesem Beispieldatensatz. 
    
- Sie sollten die Leistung des Netzwerks kontinuierlich bewerten. Die Netzwerkauslastung variiert im Laufe der Zeit aufgrund von Nutzungsmuster Änderungen, neuen unternehmensbasierten Anwendungen, die eine große Bandbreite nutzen, und Änderungen an den Speicherorten Ihrer Organisation oder Ihres Unternehmens. Es ist wichtig, dass Sie Ihre Netzwerkleistung kontinuierlich anhand dieser Netzwerk Leistungsanforderungen und-Ziele/-Schwellenwerte überwachen und rechtzeitig Anpassungen vornehmen, um die optimale Medienqualität in Echtzeit zu gewährleisten. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Messen der Netzwerkleistung mithilfe von Azure VMS
<a name="bkNetworkPerf"> </a>

Anstatt die Microsoft-Netzwerk-Edge-Websites zu testen, gibt es Netzwerk bewertungslösungen von Skype for Business-Kunden und-Partnern, die das Test Setup für Dienste in der Microsoft Azure Cloud nutzen. In diesen Lösungen testen die Netzwerk Bewertungstools Latenz, Paketverlust und Jitter für benutzerdefinierte Endpunkte, die als Dienst in der Azure-Cloud eingerichtet wurden. Daher wird der Testnetzwerk Datenverkehr durch ein zusätzliches Netzwerksegment durchlaufen, das die Verbindung innerhalb des Microsoft-Netzwerks zwischen den Netzwerk Rändern und Azure-Rechenzentren darstellt, die den Netzwerk Bewertungsdienst hosten.
  
Für diese Netzwerk bewertungslösungen, die auf Azure Hosted Testing Services basieren. Wir empfehlen, die Netzwerk Beurteilung innerhalb des Landes und/oder der Region durchzuführen. Beispielsweise sollte für Kunden Websites in Ost-USA die Bewertung für eine Testdienst Instanz durchgeführt werden, die in Azures East US Data Center-Region gehostet wird. 
  
Im folgenden finden Sie die Latency-Ziele für das Azure-dienstbasierte Netzwerk Beurteilungs Setup. Bei den unidirektionalen Latenz Zielen handelt es sich um die Hälfte der entsprechenden RTT-Ziele. Die Zielsetzungen für Paketverlust und Jitter bleiben die gleichen, die für Skype Media Relay-basierte Tests definiert sind.
  
|||||
|:-----|:-----|:-----|:-----|
|**Kundenbereich** <br/> |**Azure-Bereich** <br/> |**Ihr Netzwerk-Edge – Azure-Roundtrip-Zeit (Round-Trip Time, RTT)** <br/> |**Ihre Website – Azure-Roundtrip-Zeit (Round-Trip Time, RTT)** <br/> |
|Zentral-US  <br/> |Zentral-US  <br/> |99  <br/> |139  <br/> |
|East US  <br/> |East US  <br/> |86  <br/> |126  <br/> |
|Nord-Zentral-USA  <br/> |Nord-Zentral-USA  <br/> |97  <br/> |137  <br/> |
|Süd-Mittelamerika  <br/> |Süd-Mittelamerika  <br/> |94  <br/> |134  <br/> |
|West-US  <br/> |West-US  <br/> |94  <br/> |134  <br/> |
|Hawaii USA  <br/> |West-US  <br/> |116  <br/> |156  <br/> |
|Kanada Central  <br/> |Kanada Central  <br/> |138  <br/> |178  <br/> |
|Kanada, Osten  <br/> |Kanada, Osten  <br/> |131  <br/> |171  <br/> |
|Nordeuropa  <br/> |Nordeuropa  <br/> |99  <br/> |139  <br/> |
|West Europa  <br/> |West Europa  <br/> |95  <br/> |135  <br/> |
|Ostasien  <br/> |Ostasien  <br/> |118  <br/> |158  <br/> |
|Südostasien  <br/> |Südostasien  <br/> |97  <br/> |137  <br/> |
|Japan (Ost)  <br/> |Japan (Ost)  <br/> |111  <br/> |151  <br/> |
|Japan West  <br/> |Japan West  <br/> |118  <br/> |158  <br/> |
|Brasilien Süd  <br/> |Brasilien Süd  <br/> |70  <br/> |110  <br/> |
|Australien (Ost)  <br/> |Australien (Ost)  <br/> |124  <br/> |164  <br/> |
|Australien südöstlich  <br/> |Australien südöstlich  <br/> |124  <br/> |164  <br/> |
|Zentralindien  <br/> |Zentralindien  <br/> |103  <br/> |143  <br/> |
|Südindien  <br/> |Südindien  <br/> |103  <br/> |143  <br/> |
|West Indien  <br/> |West Indien  <br/> |103  <br/> |143  <br/> |
|China Ost  <br/> |China Ost  <br/> |120  <br/> |160  <br/> |
|China Nord  <br/> |China Nord  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Medienqualität und Express Route
<a name="bkNetworkPerf"> </a>

Azure Express Route für Office 365 ist eine dedizierte Netzwerkverbindung zum Herstellen einer Verbindung mit Office 365. Es bietet Kunden die Möglichkeit, die Kontrolle über den Pfad zu haben, den Ihr Office 365-Netzwerkdatenverkehr übernimmt. Sie müssen sich nicht mehr mit dem unvorhersehbaren Routing befassen, das im Internet geschieht, wenn Daten von unbekannten Netzbetreibern, Anbietern und ISPs übertragen werden. Netzwerkdatenverkehr, der über Express Route gesendet wird, wird direkt über das Netzwerk des Express Route-Partners an das Microsoft-Netzwerk gesendet. Auf diese Weise können Kunden Office 365 so behandeln, als ob es sich in einem eigenen, außerhalb des Standorts befindlichen Rechenzentrum mit einer dedizierten Verbindung befindet.
  
Azure Express Route steht für alle Office 365-Lizenzierungsangebote zur Verfügung. Das Azure Express Route Premium-Add-on ist jedoch für Office 365 erforderlich, um das globale Routing zu ermöglichen. Office 365-Kunden mit mindestens 500-Plätzen, die Express Route implementieren, können das erforderliche *Express Route-Premium-Add-on* ohne zusätzliche Kosten erhalten.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>Ist Express Route für eine gute Medienqualität erforderlich?

Azure Express Route ist keine Voraussetzung, um die optimale Skype for Business Online-Medienqualität zu erhalten. Es ist jedoch eine der Bereitstellungsoptionen, mit denen Sie sicherstellen können, dass Ihre Cloud-Konnektivität den Zielsetzungen oder Schwellenwerten für Skype for Business-Netzwerkleistung entspricht.
  
Office 365 ist ein leistungsstarker und sicherer Dienst, der das Internet verwendet. Wir investieren weiterhin in neue Sicherheitsfunktionen und regionale Edge-Knoten, um die Sicherheit und Leistung kontinuierlich zu verbessern. Azure Express Route ist keine Voraussetzung für Office 365-Dienste wie Skype for Business Online. Azure Express Route ist eine der verfügbaren Bereitstellungsoptionen, mit denen sichergestellt wird, dass die Konnektivität zu Office 365 den Anforderungen an die Netzwerkleistung von Skype for Business entspricht und die optimale Qualität von Skype for Business Online-Medien gewährleistet. Erfahrung.
  
Für die Medienqualität von Skype for Business Online ist es wichtig, dass die Verbindung zwischen den Websites Ihres Unternehmens und den Microsoft-Netzwerk Rändern die Leistungsziele in den [Netzwerk Leistungsanforderungen von einem Skype for Business-Client zu einem Microsoft-Netzwerk erfüllt. Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) und die Verbindung zwischen Ihren Netzwerk Rändern und den Microsoft-Netzwerk Rändern erfüllt die Leistungsziele in den [Netzwerk Leistungsanforderungen vom Netzwerk Edge zu Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge).  
  
Darüber hinaus ist es wichtig, dass die physische Netzwerkkonnektivität Ihres Unternehmens, einschließlich ihrer internen Netzwerk-und Cloud-Konnektivitäts-Kapazität, dem Höchstvolumen des Medien Verkehrs gerecht wird. Azure Express Route ist eine von vielen Möglichkeiten, mit denen Kunden sicherstellen können, dass Ihre Skype for Business Online-Cloud-Konnektivität alle diese Leistungsanforderungen erfüllt.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>Ist Express Route für die Sprachqualität SLA erforderlich?

Nein, Express Route ist für die Skype for Business Online-SLA für Sprachqualität nicht erforderlich. Die [SLA für Skype for Business Online-Sprachqualität](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) bezieht sich auf alle berechtigten Anrufe, die von einem Skype for Business Online-Voice-Service-Nutzer innerhalb der richtigen Lizenz und des entsprechenden Abonnements getätigt werden, damit dieser Nutzer jede Art von VoIP-oder PSTN-Anruf tätigen kann. Bei einer SLA für die Sprachqualität sollte berücksichtigt werden, dass alle folgenden Bedingungen erfüllt sind:
  
- Anrufe von Microsoft Certified IP-Telefonen.
    
- Ethernet-Kabelverbindungen.
    
- Probleme mit der Sprachqualität aufgrund von Problemen mit dem Microsoft-Netzwerk.
    
> [!NOTE]
> Die SLA für die Sprachqualität schließt diese Anrufe aus, bei denen die niedrige Anrufqualität durch Probleme in nicht-Microsoft-Netzwerken wie Express Route-Partner und anderen Netzwerken verursacht wird. 
  
### <a name="internet-or-azure-expressroute"></a>Internet-oder Azure-Express Route?

Bevor eine Entscheidung über Netzwerkverbindungsoptionen für Skype for Business Online getroffen wird, müssen Kunden ihre Netzwerk-und aktuelle Internet Konnektivität basierend auf den Netzwerk Leistungsanforderungen bewerten, die unter [Netzwerk Leistungsanforderungen beschrieben werden, um Herstellen einer Verbindung mit Skype for Business Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Wenn die Netzwerkleistung über die aktuelle Internet Verbindung für genügend Kapazität während der Spitzenzeit eingerichtet ist und die Netzwerk Leistungsanforderungen von Websites zu Microsoft-Netzwerk Rändern und von den Netzwerk Rändern zu Microsoft-Netzwerk Rändern erfüllt sind, können Sie Verwenden Sie weiterhin Ihre vorhandene Internet Verbindung, um eine Verbindung mit Skype for Business Online herzustellen.
  
Für Unternehmenswebsites, auf denen die Anforderungen an die Netzwerkleistung nicht erfüllt werden, wird dringend empfohlen, dass Sie zunächst mit Ihren vorhandenen Netzwerkdienstanbietern zusammenarbeiten, um die Gesamtnetzwerkleistung zu verbessern. Wenn Sie jedoch noch nicht erfüllt sind, können Sie mithilfe von Azure Express Route sicherstellen, dass Ihre Skype for Business Online-Cloud-Konnektivität Ihnen dabei helfen kann, die Anforderungen an die Netzwerkleistung zu erfüllen.
  
Azure Express Route bietet die folgenden zusätzlichen Vorteile:
  
- Eine Vereinbarung zum Service Level (SLA) zur Verfügbarkeit der Verbindung zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk. Express Route verfügt über eine garantierte Verfügbarkeits-SLA von 99,9%.
    
- Geplanter und garantierter Bandbreitenbedarf für Office 365-Dienste. Sie können dies erreichen, indem Sie nur Office 365-Datenverkehr oder Skype for Business-Datenverkehr über das Express Route senden und dann alle anderen Internetdatenverkehr über andere Internet-Ausgänge/Ingress-Punkte für Ihr Netzwerk durchlaufen lassen.
    
- Express Route wurde entwickelt, um DSCP-QoS-Markierungen zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk beizubehalten.
    
Weitere Informationen zur QoS-und Kapazitätsplanung von Express Route finden Sie unter [Express Route und QoS in Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Kann ich nur Azure Express Route für Skype for Business Online einrichten?

Ja, Sie können Azure Express Route einrichten, um eine hervorragende Netzwerkverbindung aus dem Netzwerk Ihres Unternehmens mit Skype for Business Online zu gewährleisten. Dadurch wird die optimale Echtzeit-Medienqualität für Ihre Benutzer bereitgestellt, Sie können dann aber auch weiterhin über das Internet mit anderen Office 365-Diensten eine Verbindung herstellen.
  
Das Border Gateway Protocol (BGP) ist ein Routingprotokoll im Internet, das zum Weiterleiten von Netzwerkdatenverkehr über das Internet verwendet wird. Es dient zum Austausch von Routinginformationen zwischen autonomen Systemen (as), die über das Internet gefunden werden. BGP Communities-Werte sind Attributtags, die auf eingehende oder ausgehende Routen angewendet werden können. BGP-Communities werden häufig verwendet, um dem Empfänger zu signalisieren, welche ausgehenden Links zum Erreichen eines bestimmten Ziels auf Grundlage der geografischen Gegebenheiten, des Diensttyps oder anderer Kriterien zu verwenden sind.
  
Mit der Unterstützung von BGP Communities werden Präfixe und Routen mit den entsprechenden BGP-Community-Werten basierend auf dem Dienst, zu dem Sie gehören, gekennzeichnet. Microsoft kennzeichnet Präfixe, die über Public Peering und Microsoft Peering mit entsprechenden BGP-Community-Werten angekündigt werden, die den Bereich angeben, in dem die Präfixe gehostet werden. Sie können sich darauf verlassen, dass die Community-Werte geeignete Routingentscheidungen treffen, um optimales Routing zu ermöglichen. Sie können den Skype for Business Online-BGP-Community-Wert verwenden, um eine Express Route-Verbindung nur für Skype for Business Online einzurichten. Weitere Informationen finden Sie unter [Express Route-Routing Anforderungen](https://azure.microsoft.com/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Express Route-Verbindungsszenarien für Skype for Business Online
<a name="bkNetworkPerf"> </a>

Wenn Sie entschieden haben, dass Express Route basierend auf den oben aufgeführten Empfehlungen für Sie bestimmt ist, finden Sie hier die Empfehlungen dazu, wo und wie viele Express Route-Verbindungen Sie erhalten sollten.
  
### <a name="online-only-deployment---single-site"></a>Nur Online Bereitstellung – einzelne Website

Wenn alle Ihre Benutzer den Skype for Business Online-Dienst verwenden und ihre Büros an einem einzigen physikalischen Standort zentriert sind und Sie sich entscheiden, Azure Express Route bereitzustellen, sollten Sie eine einzelne Express Route-Verbindung zwischen Ihrer Unternehmenswebsite und der nächstgelegenen [Express Route-Peering-Standort](https://azure.microsoft.com/documentation/articles/expressroute-locations/).
  
Die folgende Abbildung zeigt ein Beispiel für diese Art der Bereitstellung. In diesem Beispiel ist Contoso eine Universität in Orlando, FL. Contoso hat 10.000-Dozenten und-Schüler. Die Internet Tests von Ihrem Standort auf Microsoft Edge-Websites zeigten einen Paketverlust von mehr als 5% während der Spitzenstunden. Sie haben sich entschieden, eine dedizierte Verbindung zu Office 365 mithilfe von Express Route mit über bereitgestellter Bandbreite zu erhalten, damit Sie den Netzwerkengpass für Office 365 insbesondere für den Echtzeitverkehr von Skype for Business Online vermeiden können. Sie stellen eine Verbindung mit der Microsoft-Cloud über Express Route auf der Atlanta, GA MeetMe-Website her.
  
![Express Route-einzelne Website.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Nur Online Bereitstellung – mehrere Websites auf demselben Kontinent

Wenn Ihr Unternehmen Skype for Business Online-Dienste aus mehreren Niederlassungen in derselben Region oder einem Kontinent verwendet und Sie sich für die Implementierung von Azure Express Route entschieden haben, empfiehlt es sich, die Hauptwebsite über Express Route zu verbinden und dann optional weitere Express Route Peering für andere Speicherorte, die die empfohlenen Netzwerk Leistungsziele nicht erfüllen.
  
Im folgenden Beispiel ist Contoso ein US-amerikanische Reise Dienstanbieter-Unternehmen, das seinen Hauptsitz in New York hat, aber über andere Niederlassungen in den Vereinigten Staaten verfügt. Ihre Niederlassungen sind über ein WAN verbunden, in dem MPLS zum Herstellen einer Verbindung mit Office 365 verwendet wird. Sie haben zunächst eine Express Route-Verbindung von Ihrem Internet-Router in Hoboken, New Jersey zur New York MeetMe-Website eingerichtet. 
  
Mit diesem Setup kann der Netzwerkdatenverkehr von den meisten ihrer Websites an das Microsoft-Netzwerk (New York Edge-Website) die in den [Netzwerk Leistungsanforderungen von einem Skype for Business-Client beschriebenen Leistungsziele für Skype for Business-Clientverbindungen erfüllen. an Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Die Wartezeit zwischen den Niederlassungen von Contoso an der Westküste nach New York geht jedoch 50ms unidirektional weiter. Darüber hinaus ist Honolulu das zweitgrößte Office für Contoso, die Latenz von Honolulu nach New York überschreitet 80ms unidirektional. Um eine gute Medienqualität für die Benutzer in diesen Offices zu gewährleisten, beschloss contoso, eine West Coast Express Route-Verbindung zwischen Ihrer San Jose-Website und der Website Silicon Valley Express Route MeetMe hinzuzufügen.
  
![Express-Router-Multi-Site auf dem gleichen Kontinent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Nur Online Bereitstellung – mehrere Websites auf unterschiedlichen Kontinenten

Wenn alle Ihre Benutzer den Skype for Business Online-Dienst verwenden und sich ihre Niederlassungen an mehreren physischen Standorten auf mehreren Kontinenten befinden, wenn Sie sich entschließen, Azure Express Route bereitzustellen, sollten Sie mindestens eine Express Route-Verbindung für jeden Kontinent einrichten. zwischen der Hauptwebsite des jeweiligen Kontinents und dem nächstgelegenen [Express Route-Peering-Standort](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Je nach Kosten vs. Benefit können Sie weitere Express Route-Verbindungen von Websites bereitstellen, auf denen Netzwerk Leistungsziele nicht erfüllt werden.
  
Im folgenden Beispiel ist Contoso eine große Unternehmens Kanzlei mit Niederlassungen in Großstädten in Nordamerika und Europa. Basierend auf Ihrer Internet Verbindung und ihrer internen Netzwerk Leistungsbewertung beschloss contoso, zwei Express Route-Verbindungen in Nordamerika und einen einzigen Express Route-Schaltkreis für alle ihre europäischen Niederlassungen bereitzustellen.
  
![Express Route mit mehreren Websites und Kontinenten](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Hybrid Bereitstellung

Wenn Sie über eine lokale lync-oder Skype for Business-Bereitstellung verfügen und eine hybride Skype for Business Online-Integration implementieren möchten, empfiehlt es sich, wenn Sie sich für die Bereitstellung von Azure Express Route entscheiden, dass Sie mindestens über eine Express Route-Verbindung verfügen müssen. lokale lync-oder Skype for Business Edge-Website und mindestens eine Express Route-Verbindung für jeden Kontinent mit Offices. Je nach Kosten vs. Benefit können Sie für jeden Kontinent zusätzliche Express Route-Verbindungen von Offices bereitstellen, in denen Netzwerk Leistungsziele nicht erfüllt werden.
  
Wenn Sie über eine lokale Skype for Business-Bereitstellung verfügen, müssen Sie dem [Handbuch für die Planung und Bereitstellung von Edge-Servern](https://technet.microsoft.com/en-us/library/mt346417.aspx)folgen. Insbesondere müssen die Edgeserver von außerhalb Ihres Netzwerks erreichbar sein. Dies erfolgt in der Regel entweder durch Zuweisen einer routingfähigen öffentlichen IP-Adresse zum Edgeserver oder mithilfe der Netzwerkadressübersetzung (Network Address Translation, NAT).
  
Im folgenden Beispiel verfügt Contoso über eine vorhandene lokale Skype for Business Enterprise-VoIP-Bereitstellung. Sie möchten lokale Benutzer zu Office 365 Online-Diensten migrieren. Außerdem haben Sie entschieden, eine hybridbereitstellung zu verwenden, damit diese Ihre vorhandene PSTN-Infrastruktur weiterhin für alle lokalen und Online Benutzer verwenden können. Das lokale Contoso-Rechenzentrum und die Skype for Business Edge-Server befinden sich in Chicago. Für Ihre Bereitstellung beschloss contoso, eine Express Route-Verbindung zwischen dem Chicago-Rechenzentrum und dem Chicago-Express Route einzurichten. Sie haben auch eine West Coast Express Route-Verbindung hinzugefügt, um Ihre Niederlassung in Honolulu besser zu bedienen.
  
![Express Route-Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Online Bereitstellung mit Cloud Connector Edition

Skype for Business Online Cloud Connector Edition ist ein Hybrid Angebot, das aus einer Reihe von virtuellen Maschinen (Virtual Machines) besteht, die lokale PSTN-Konnektivität implementieren. Wenn Sie eine minimale Skype for Business Server-Topologie in einer virtualisierten Umgebung bereitstellen, können Sie über die vorhandene lokale PSTN-VoIP-Infrastruktur Anrufe an Festnetztelefone und Handys senden und empfangen.
  
Wenn Sie sich entschließen, Azure Express Route und Cloud Connector Edition bereitzustellen, empfehlen wir Ihnen, mindestens eine Express-Routen Verbindung für jeden Kontinent zwischen dem Hauptstandort des jeweiligen Kontinents und dem nächstgelegenen [Express Route-Peering-Standort](https://azure.microsoft.com/documentation/articles/expressroute-locations/)einzurichten. Je nach Kosten vs. Benefit können Sie für jeden Kontinent zusätzliche Express Route-Verbindungen von Websites bereitstellen, auf denen Netzwerk Leistungsziele nicht erfüllt werden.
  
Wenn Sie über eine lokale Skype for Business-Bereitstellung verfügen, müssen Sie das [Planungshandbuch für Skype for Business Cloud Connector Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx)befolgen. Insbesondere sollten die Access Edge-und A/V-Edgedienst öffentlichen IP-Adressen zugewiesen und von Office 365-Rechenzentren aus erreichbar sein.
  
Im folgenden Beispiel ist Contoso ein europäisches Wirtschaftsprüfungsunternehmen mit Anwesenheit in einigen wenigen großen europäischen Ländern und Städten. Wenn Sie sich bei Skype for Business Online für alle Ihre Anforderungen an die Zusammenarbeit registrieren, haben Sie sich entschlossen, für jedes Land, in dem Sie einen physischen Standort haben, einen Cloud Connector einzusetzen, um weiterhin die bereits vorhandenen PSTN-Infrastruktur-und Netzbetreiber Verträge zu verwenden. Basierend auf Ihren Tests von allen ihren Websites und Microsoft Network Edge haben Sie festgestellt, dass eine einzige Express Route-Verbindung in London dazu beitragen wird, die in der Netzwerkleistung beschriebenen Leistungsziele für Skype for Business-Clientverbindungen zu erfüllen. [ Anforderungen von einem Skype for Business-Client zu Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Express Route Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Nachfolgend finden Sie eine weitere Bereitstellungsoption für contoso. In diesem Fall haben Sie sich für die Einrichtung einer Express Route-Verbindung an jedem Standort entschieden, auf dem ein Cloud Connector bereitgestellt wird. 
  
![Express Route Cloud Connector 2.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute und QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 
