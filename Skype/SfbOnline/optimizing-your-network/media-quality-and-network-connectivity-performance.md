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
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: In diesem Thema werden die Anforderungen an die Netzwerkleistung für Skype for Business Online-Dienste definiert und beschrieben, wie Sie das Internet oder ExpressRoute für die Konnektivität zwischen Ihrem Netzwerk und Skype for Business Online verwenden können, basierend auf Ihrer Bewertung der Netzwerkkonnektivität. Wenn Sie sich für die Bereitstellung von Azure ExpressRoute für dedizierte Konnektivität mit Microsoft 365 oder Office 365 entschieden haben, enthält dieses Dokument auch Anleitungen zum Planen Ihrer ExpressRoute-Verbindungen in verschiedenen Skype for Business Online-Bereitstellungsszenarien.
ms.openlocfilehash: 4ac879c1e2e7b625a45f5d5f399d7438d038595f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100711"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online

In diesem Thema werden die Anforderungen an die Netzwerkleistung für Skype for Business Online-Dienste definiert und beschrieben, wie Sie das Internet oder ExpressRoute für die Konnektivität zwischen Ihrem Netzwerk und Skype for Business Online verwenden können, basierend auf Ihrer Bewertung der Netzwerkkonnektivität. Wenn Sie sich für die Bereitstellung von Azure ExpressRoute für dedizierte Konnektivität mit Microsoft 365 oder Office 365 entschieden haben, enthält dieses Dokument auch Anleitungen zum Planen Ihrer ExpressRoute-Verbindungen in verschiedenen Skype for Business Online-Bereitstellungsszenarien.
  
Die Qualität der Real-Time (Audio, Video und Anwendungsfreigabe) über DIE IP ist stark von der Qualität der End-to-End-Netzwerkkonnektivität betroffen. Für optimale Medienqualität in Skype for Business Online benötigen Sie eine Verbindung von hoher Qualität zwischen Ihrem Unternehmensnetzwerk und Skype for Business Online. Am besten orientieren Sie sich beim Einrichten der Konnektivität zwischen dem internen Netzwerk und der Cloud an der Kapazität des Netzwerks, damit auch Spitzendatenaufkommen für Skype for Business Online über alle Verbindungen kein Problem darstellen.
  
Azure ExpressRoute ist keine Anforderung für Microsoft 365- und Office 365-Dienste, einschließlich Skype for Business Online. Azure ExpressRoute ist jedoch eine der verfügbaren Bereitstellungsoptionen, mit deren Hilfe sichergestellt werden kann, dass die Konnektivität mit Microsoft 365 oder Office 365 den Anforderungen an die Netzwerkleistung von Skype for Business entspricht und die optimale Medienqualität von Skype for Business Online gewährleistet.
  
> [!TIP]
> Obwohl in diesem Thema eine allgemeine Anleitung zur Netzwerkleistung angezeigt wird, liegt die vollständige Anleitung für die Netzwerkbewertung außerhalb des Umfangs dieses Dokuments. Eine Liste der Skype for Business Online-Partner, die Ihnen bei den Messungen der Netzwerkleistung im Rahmen einer gründlichen und vollständigen Netzwerkbewertung helfen können, finden Sie unter [Skype for Business Partner Solutions](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Netzwerkkonnektivitätsanforderungen für Skype for Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Faktoren, die sich auf die Medienqualität von Skype for Business Online auswirken

Es gibt viele verschiedene Faktoren, die zur Qualität von Skype for Business Online Real-Time Medienqualität (Audio, Video und Anwendungsfreigabe) beitragen, die die verwendeten Geräte, die Umgebung und die Netzwerkkonnektivität umfassen. 
  
#### <a name="devices"></a>Geräte

In einer Real-Time Mediensitzung haben Geräte zum Aufzeichnen und Rendern von Medien, die von allen Teilnehmern verwendet werden, wie Headsets und Webcams, einen großen Einfluss auf die Audio- und Videoqualität insgesamt. Geräte von niedrigerer Qualität oder Geräte mit falschen Treibern erzeugen Audiomedien mit einer schlechteren allgemeinen Tonqualität sowie Videomedien mit einer schlechteren Bildqualität. Zertifizierte Geräte oder Geräte von hoher Qualität dagegen verbessern Echounterdrückung, Rauschunterdrückung und Videoauflösung und verringern die Latenz.
  
Obwohl zertifizierte Audio- und Videomediengeräte nicht erforderlich sind, sind sie für Skype for Business für die optimale Medienerfahrung äußerst empfehlenswert. Eine Liste aller skype for Business-zertifizierten Geräte finden Sie unter [Telefone und Geräte für Skype for Business.](../../SfbPartnerCertification/certification/devices-ip-phones.md) Sie können das Skype for Business Online-Anrufqualitätsdashboard im **Skype for Business Admin Center** verwenden, um zu überprüfen, ob die verwendeten Geräte ordnungsgemäß funktionieren, und die Audio- und Videomedienqualität überwachen. [](/microsoftteams/turning-on-and-using-call-quality-dashboard)
  
> [!TIP]
> Für die optimale Medienqualität in Skype for Business ist ein **zertifiziertes Gerät erforderlich.**
  
Es ist wichtig zu bedenken, dass alle Mediengeräte, Skype for Business-Clients und Skype for Business-Server, über die Real-Time Medienflüsse übertragen werden, eine gewisse Latenz mit sich bringen. Die Latenz der Geräte- und Softwareverarbeitung sowie die Netzwerklatenz haben einen großen Einfluss auf die Gesamtlatenz und die Benutzerfreundlichkeit.
  
#### <a name="environment"></a>Umgebung

Die Umgebung und das Umfeld, in dem sich Nutzer treffen und Audio- und Videogeräte verwenden, stellen ebenfalls einen wichtigen Faktor für die Audio- und Videoqualität dar. Nutzer, die aus einer lauten Umgebung anrufen, hören gedämpften und undeutlichen Ton mit Echos. Nutzer in einer dunklen oder lichtarmen Umgebung können keine hellen und scharfen Videos erzeugen. In einem Konferenzraum wirkt sich die Position des Mikrofons und des Videogeräts direkt auf die Ton- und Bildqualität für die Teilnehmer aus.
  
Um ein übersichtlicheres Bild der Audio- und Videoerfahrung eines Benutzers zu erhalten, verwenden Sie die Skype for **Business-App-Tools** Optionen  >    >  **Audiogerät** oder **Videogerät,** um Änderungen am verwendeten Gerät vorzunehmen und seine Einstellungen anzupassen.

#### <a name="network"></a>Netzwerk

Die Qualität der Real-Time -Medien über ein IP-Netzwerk ist stark von der Qualität der Netzwerkkonnektivität, aber insbesondere von der Menge der:
  
- **Latenz** Dies ist die Zeit, die benötigt wird, um ein IP-Paket von Punkt A bis Punkt B im Netzwerk zu erhalten. Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Router. Die Latenz wird als One-Way- oder Roundtrip time (RTT) gemessen.
    
- **Paketverlust** Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Back-to-Back-Burstverlusten, die einen vollständigen Audioausschnitt verursachen.
    
- **Paketübergreifendes Ankunfts-Jitter oder einfaches Jittern** Dies ist die durchschnittliche Änderung der Verzögerung zwischen aufeinander folgenden Paketen. Die meisten modernen VoIP-Software, einschließlich Skype for Business, können sich durch Pufferung an einige Jitterebenen anpassen. Erst wenn der Jitter die Pufferung übersteigt, bemerken die Teilnehmer die Auswirkungen.
    
> [!NOTE]
>  Durch puffern für Jitter wird die End-to-End-Latenz erhöht.
  
Bei vielen gleichzeitigen Skype for Business Online Real-Time-Mediensitzungen sowie anderen Netzwerkdatenverkehr, der von anderen Microsoft 365- oder Office 365-Diensten und anderen Geschäftsanwendungen generiert wird, ist es wichtig sicherzustellen, dass über den gesamten Netzwerkpfad, der Ihr Netzwerk mit dem Skype for Business Real-Time Online-Dienst verbindet, eine ausreichende Bandbreite vorhanden ist, um Netzwerküberlastungen zu vermeiden und eine hervorragende Medienqualität (Audio, Video und Anwendungsfreigabe) sicherzustellen. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementieren von Quality of Service (QoS) über überlastete Netzwerke hinweg

Darüber hinaus wirkt sich die Überlastung des Datenverkehrs über ein Netzwerk erheblich auf die Medienqualität aus. Damit Audio- und Videopakete schneller in das Netzwerk reisen und über anderen Netzwerkdatenverkehr in einem überlasteten Netzwerk priorisiert werden können, kann Quality of Service (QoS) verwendet werden, um eine optimale Benutzererfahrung für Audio- und Videokommunikation zu bieten.
  
QoS bietet Ihnen die Möglichkeit, Netzwerkpaketen, die Audio- oder Videodaten enthalten, höhere Prioritäten zuzuordnen. Durch das Zuweisen einer höheren Priorität zu diesen Paketen wird die Audio- und Videokommunikation wahrscheinlich schneller und mit weniger Unterbrechungen über das Netzwerk übertragen als Netzwerksitzungen, die z. B. Dateiübertragungen, Webbrowsen oder Datenbanksicherungen enthalten. Der Grund dafür ist, dass den standardmäßig für Dateiübertragungen oder Datenbanksicherungen verwendeten Netzwerkpaketen "best effort" als Priorität zugewiesen wird und die Netzwerküberlastung nicht so große Auswirkungen hat. Wenn Sie den Medienpaketen (Audio, Video und Anwendungsfreigabe) keine höhere Priorität zuweisen und diese auch als "optimale Leistung" zuweisen, werden auch diese zusammen mit dem anderen Netzwerkdatenverkehr verarbeitet. Je nach Umfang der Netzwerküberlastung kann dies zu einer insgesamt geringeren Audio- und Videoqualität für Ihre Benutzer führen.
  
Es wird dringend empfohlen, QoS in Ihrem Netzwerk zu implementieren, um sicherzustellen, dass sich die Netzwerküberlastung in Ihrem Netzwerk nicht auswirken wird. Damit dies jedoch die größtmögliche Auswirkung hat, müssen alle Netzwerkendpunkte QoS unterstützen, d. h., dass alle Endpunkte die QoS-Markierung und Paket priorisieren müssen. Skype for Business Online-Dienste honorieren die QoS-Kennzeichnung und -Priorisierung innerhalb des Microsoft-Netzwerks. Der Datenverkehr, der über eine öffentliche Verbindung wie das Internet vom Unternehmensnetzwerk zum Microsoft-Netzwerk geroutet wird, behält jedoch keine QoS-Markierungen und Paket priorisierung bei. Private Verbindungen von Ihrem Netzwerk zu Microsoft 365 oder Office 365 mit [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) bieten eine Bereitstellungslösung, die QoS-Markierungen und Paket priorisiert, was wiederum die Gesamtaudio- und Videoqualität für Ihre Endbenutzer erhöht.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Anforderungen an die Netzwerkleistung für die Verbindung mit Skype for Business Online
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Time unterschiedliche Geräte, Client-Apps, Serversoftware und unterschiedliche Netzwerke. Die End-to-End-Latenz Real-Time Medien ist die Gesamtlatenz, die für alle Komponenten und Netzwerksegmente eingeführt wird. Die Qualität der End-to-End-Netzwerkverbindung wird durch das Netzwerksegment mit der schlechtesten Qualität bestimmt. Dieses Segment fungiert als Engpass für diesen Netzwerkdatenverkehr.
  
Das folgende Diagramm veranschaulicht den einweg-Audiofluss in einer Konferenz von einem Skype for Business-Teilnehmer zum anderen.
  
![ExpressRoute-Anruffluss.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In diesem Konferenzszenario besteht der Medienpfad über die folgenden Netzwerksegmente:
  
1. **Verbindung von Benutzer 1 zum Rand des Microsoft-Netzwerks** Dies umfasst in der Regel eine Netzwerkverbindung wie WLAN oder Ethernet, die WAN-Verbindung von Benutzer 1 zum Internet-Ausgangspunkt (Ihr Netzwerk-Edge-Gerät) und die Internetverbindung von Ihrem Netzwerk Edge zu Microsoft Network Edge.
    
2. **Verbindung innerhalb des Microsoft-Netzwerks** Dies befindet sich zwischen dem Microsoft Edge- und Skype for Business Online-Rechenzentrum, in dem die A/V-Konferenzserver verwendet werden.
    
3. **Verbindung in Microsoft Network** Dies befindet sich zwischen dem Skype for Business Online-Rechenzentrum und Microsoft Network Edge.
    
4. **Verbindung von Microsoft Network Edge zu Benutzer 2** Dazu gehören die Internetverbindung von Ihrem Netzwerk Edge zu Microsoft Network Edge, die WAN-Verbindung von Benutzer 2 zum Internet-Ausgangspunkt (Ihr Netzwerkrand) und die Netzwerkverbindung wie ein WLAN oder ein Ethernet.
    
Das folgende Diagramm zeigt eine Aufschlüsselung der Komponenten und Netzwerksegmente eines Skype for Business Online-PSTN-Anrufs:
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In einem PstN-Anrufszenario durchquert der Medienpfad die folgenden Netzwerksegmente:
  
1. **Verbindung von einem Skype for Business-Clientanrufer zum Rand des Microsoft Network** Dies umfasst in der Regel eine Netzwerkverbindung wie WLAN oder Ethernet, die WAN-Verbindung vom Skype for Business-Clientanrufer zum Internet-Ausgangspunkt (Ihr Netzwerk-Edge-Gerät) und die Internetverbindung von Ihrem Edge-Netzwerk zu Microsoft Network Edge.
    
2. **Verbindung innerhalb des Microsoft-Netzwerks** Dies befindet sich zwischen dem Microsoft Edge- und Skype for Business Online-Rechenzentrum, in dem ein Vermittlungsserver verwendet wird.
    
3. **Verbindung in Microsoft Network** Dies befindet sich zwischen dem Skype for Business Online-Rechenzentrum und Microsoft Network Edge.
    
4. **Verbindung zwischen Microsoft Network und den PstN-Dienstanbieterpartnern** Dies ist die Verbindung, die besteht, um einen PSTN-Anruf über den Skype for Business-Client zu führen, der sich außerhalb des Microsoft-Netzwerks befindet.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Anforderungen an die Netzwerkleistung von einem Skype for Business-Client bis zu Microsoft Network Edge
<a name="bkSfBClienttoEdge"></a>

Für eine optimale Medienqualität in Skype for Business sind die folgenden Ziele oder Schwellenwerte für netzwerkleistungsmetrik für eine Verbindung vom Netzwerk Ihres Unternehmens mit dem Microsoft Network Edge erforderlich. Dieses Segment des Netzwerks umfasst Ihr internes Netzwerk. Dies umfasst alle WLAN- und Ethernetverbindungen, alle Website-zu-Website-Datenverkehre von Unternehmen über eine WAN-Verbindung, z. B. MpLS (Multiprotocol Label Switching), sowie die Internet- oder ExpressRoute-Partnerverbindungen mit dem Microsoft-Netzwerk edge.
  
> [!CAUTION]
> **Die Konnektivität zwischen einem Skype for Business-Client in Ihrem Unternehmensnetzwerk und Microsoft 365- oder Office 365-Diensten muss die folgenden Anforderungen und Schwellenwerte für die Netzwerkleistung erfüllen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |**Target** <br/> |
|Latenz (unidirektional)  <br/> |< 50 ms  <br/> |
|Latenz (RTT- oder Roundtripzeit)  <br/> |< 100 ms  <br/> |
|Burstverlust von Paketen  <br/> |<10 % während eines Intervalls von 200 ms  <br/> |
|Paketverlust  <br/> |<1 % während eines 15s-Intervalls  <br/> |
|Jitter zwischen der Ankunftszeit von Paketen  <br/> |<30 ms in einem intervall von 15s  <br/> |
|Neuanordnung von Paketen  <br/> |< 0,05 % Pakete in falscher Reihenfolge  <br/> |
   
 **Weitere Leistungszielanforderungen:**
  
- Das Microsoft-Netzwerk verfügt über mehr als 160 Edge-Standorte weltweit. Über diese Edgewebsites arbeiten wir weltweit mit großen Internetdienstanbietern (ISPs) zusammen. Das Metrikziel für latenzmetrische Daten setzt voraus, dass sich Ihre Unternehmenswebsites oder -websites und die Microsoft Edges auf demselben Kontinent befinden.
    
- Ihre Unternehmenswebsite oder Websites zur Microsoft-Netzwerk-Edge-Verbindung umfassen First Hop-Netzwerkzugriff, bei dem es sich um WLAN oder eine andere Funktechnologie geben kann. 
    
- Für das Netzwerkleistungsziel wird die richtige Bandbreite und/oder Qualität der Dienstplanung vorausgesetzt. Anders ausgedrückt: Dies gilt direkt für Skype for Business Real-Time Mediendatenverkehr, wenn die Netzwerkverbindung eine Spitzenlast hat.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Anforderungen an die Netzwerkleistung von Ihrem Edge-Netzwerk zu Microsoft Network Edge
<a name="bkYourNetworkEdge"> </a>

Im Folgenden sind die Ziele oder Schwellenwerte für die Netzwerkleistung zu finden, die für die Verbindung zwischen Ihrem Netzwerk edge und dem Microsoft Network Edge erforderlich sind. Dieses Segment des Netzwerks schließt das interne Netzwerk oder WAN des Kunden aus und dient als Anleitung beim Testen des Netzwerkdatenverkehrs, der über das Internet oder über ein ExpressRoute-Partnernetzwerk gesendet wird und auch beim Aushandeln eines Service Level Agreement (SLA) mit Ihrem ExpressRoute-Anbieter verwendet werden kann.
  
> [!CAUTION]
> **Die Konnektivität zwischen Ihrem Unternehmensnetzwerk Edge und dem Microsoft-Netzwerkrand muss die folgenden Anforderungen und Schwellenwerte für die Netzwerkleistung erfüllen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |**Target** <br/> |
|Latenz (unidirektional)  <br/> |< 30 ms  <br/> |
|Latenz (RTT)  <br/> |< 60 ms  <br/> |
|Burstverlust von Paketen  <br/> |<1 % in einem Intervall von 200 ms  <br/> |
|Paketverlust  <br/> |<0,1 % in einem Intervall von 15 Sekunden  <br/> |
|Jitter zwischen der Ankunftszeit von Paketen  <br/> |<15 ms in einem intervall von 15s  <br/> |
|Neuanordnung von Paketen  <br/> |< 0,01 % Pakete in falscher Reihenfolge  <br/> |
   
 **Weitere Leistungszielanforderungen:**
  
- Für das Leistungsziel ist eine Verbindung zwischen dem Edge Ihres Unternehmensnetzwerks und dem nächstgelegenen Microsoft-Netzwerk edge erforderlich, um sich auf demselben Kontinent zu befinden.
    
- Für das Netzwerkleistungsziel wird die richtige Bandbreite und/oder Qualität der Dienstplanung vorausgesetzt. Dies gilt auch für Skype for Business Real-Time Mediendatenverkehr, wenn die Netzwerkverbindung eine Spitzenlast hat. Informationen zur richtigen Bandbreite und QoS-Planung finden Sie unter [ExpressRoute und QoS in Skype for Business Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>Messen der Netzwerkleistung
<a name="bkNetworkPerf"> </a>

Zum Messen der tatsächlichen Netzwerkleistung, insbesondere für Latenz und Paketverlust, von einer beliebigen Unternehmensnetzwerkwebsite bis zu einem Netzwerkrand können Sie Tools wie Ping verwenden, eine Reihe von Skype for Business-Medienrelaisdiensten testen, die von Microsoft Edge- und Rechenzentrumswebsites ausgeführt werden. 

>[!NOTE]
> Die Messung der Netzwerkleistung durch Ping (ICMP) ist nicht effektiv. Aus diesem Grund beendet die unten angezeigte Anycast-IP die Beantwortung von ICMP-Anforderungen ab Januar 2020. Um die Leistung des Netzwerks effektiv zu messen, empfiehlt Microsoft das [Netzwerk-Assesment-Tool](https://www.microsoft.com/download/details.aspx?id=53885).
  
Zum Testen von Internetverbindungen mit dem Microsoft-Netzwerk empfiehlt es sich, die folgenden VIPs der Skype for Business-Medienrelais zu testen. Die *Anycast-VIP*  wird in eine IP-Adresse eines Media Relays auf einer Microsoft Network Edge-Website aufgelöst, die dem Testspeicherort am nächsten ist.
  
||||
|:-----|:-----|:-----|
|**IP-Adresse** <br/> |**Typ** <br/> |**Standort** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **Hier sind einige Empfehlungen auf hoher Ebene, die Sie zur Bewertung der Netzwerkleistung befolgen sollten:**
  
- Sie sollten Ihr internes Netzwerk sowie die Verbindungen zu Microsoft 365 oder Office 365 bewerten.
    
- Sie sollten Daten für alle Ihre Netzwerke über einen langen Zeitraum bewerten und sammeln. Wir empfehlen Ihnen, die Netzwerkleistung mindestens eine Woche lang zu testen, damit Sie Nutzungsmuster für alle Geschäftstage und -stunden sehen können. Dadurch werden Spitzenzeiten gezeigt.
    
- Sie sollten mehrere Beispiele für Netzwerkleistungsmessungen verwenden. Wir empfehlen, während des gesamten Zeitraums, in dem Sie Daten sammeln, alle 10 Minuten eine Messung von einer Unternehmenswebsite zu nehmen. Zum Vergleichen der Anforderungen an die Netzwerkleistung von Skype for Business Online verwenden Sie den 90. Perzentilmaßwert aus diesem Beispieldatensatz. 
    
- Sie sollten die Leistung des Netzwerks kontinuierlich bewerten. Die Netzwerkauslastung variiert im Laufe der Zeit aufgrund von Nutzungsmusteränderungen, neuen unternehmensbasierten Anwendungen, die eine große Bandbreite verwenden, und Änderungen an Ihren Organisations- oder physischen Unternehmensstandorten. Es ist wichtig, dass Sie Ihre Netzwerkleistung kontinuierlich an diesen Anforderungen und Zielen/Schwellenwerten für die Netzwerkleistung überwachen und rechtzeitige Anpassungen vornehmen, um die optimale Medienqualität Real-Time sicherzustellen. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Messen der Netzwerkleistung mithilfe von Azure VMs
<a name="bkNetworkPerf"> </a>

Anstelle von Tests für microsoft network Edge-Websites gibt es Netzwerkbewertungslösungen von Skype for Business-Kunden und -Partnern, die die Einrichtung von Tests für Dienste in der Microsoft Azure-Cloud nutzen. In diesen Lösungen testen die Tools für die Netzwerkbewertung Latenz, Paketverlust und Jitter für benutzerdefinierte Endpunkte, die als Dienst in der Azure-Cloud eingerichtet wurden. Daher wird der Testnetzwerkverkehr durch ein zusätzliches Netzwerksegment durchgeführt, d. h. die Verbindung innerhalb des Microsoft-Netzwerks zwischen den Netzwerkrändern und Azure-Rechenzentren, die den Netzwerkbewertungsdienst hosten.
  
Für diese Netzwerkbewertungslösungen, die auf gehosteten Azure-Testdiensten basieren. Wir empfehlen, die Netzwerkbewertung innerhalb des Landes und/oder der Region zu durchführen. Bei Kundenwebsites im Osten der USA sollte die Bewertung beispielsweise für eine Testdienstinstanz ausgeführt werden, die in der Region des Rechenzentrums ost der USA in Azure gehostet wird. 
  
Im Folgenden sind die Latenzziele (Latency, RTT) für das Setup für die dienstbasierte Netzwerkbewertung von Azure aufgeführt. Die Einweglatenzziele sind die Hälfte der entsprechenden RTT-Ziele. Die Ziele für Paketverlust und Jitter bleiben mit denen identisch, die für skype Media Relay-basierte Tests definiert sind.
  
|||||
|:-----|:-----|:-----|:-----|
|**Kundenregion** <br/> |**Azure-Region** <br/> |**Ihr Netzwerk edge – Azure Round-Trip Time (RTT)** <br/> |**Ihre Website – Azure Round-Trip Time (RTT)** <br/> |
|Zentral USA  <br/> |Zentral USA  <br/> |99  <br/> |139  <br/> |
|Ost-USA  <br/> |Ost-USA  <br/> |86  <br/> |126  <br/> |
|North Central USA  <br/> |North Central USA  <br/> |97  <br/> |137  <br/> |
|South Central USA  <br/> |South Central USA  <br/> |94  <br/> |134  <br/> |
|Usa, Westen  <br/> |Usa, Westen  <br/> |94  <br/> |134  <br/> |
|Hawaii USA  <br/> |Usa, Westen  <br/> |116  <br/> |156  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |138  <br/> |178  <br/> |
|Kanada Ost  <br/> |Kanada Ost  <br/> |131  <br/> |171  <br/> |
|Nordeuropa  <br/> |Nordeuropa  <br/> |99  <br/> |139  <br/> |
|Westeuropa  <br/> |Westeuropa  <br/> |95  <br/> |135  <br/> |
|Ostasien  <br/> |Ostasien  <br/> |118  <br/> |158  <br/> |
|Südostasien  <br/> |Südostasien  <br/> |97  <br/> |137  <br/> |
|Japan Ost  <br/> |Japan Ost  <br/> |111  <br/> |151  <br/> |
|Japan West  <br/> |Japan West  <br/> |118  <br/> |158  <br/> |
|Brasilien Süd  <br/> |Brasilien Süd  <br/> |70  <br/> |110  <br/> |
|Australien , Osten  <br/> |Australien , Osten  <br/> |124  <br/> |164  <br/> |
|Australien Südosten  <br/> |Australien Südosten  <br/> |124  <br/> |164  <br/> |
|Zentralindien  <br/> |Zentralindien  <br/> |103  <br/> |143  <br/> |
|Südindien  <br/> |Südindien  <br/> |103  <br/> |143  <br/> |
|Westindien  <br/> |Westindien  <br/> |103  <br/> |143  <br/> |
|China Ost  <br/> |China Ost  <br/> |120  <br/> |160  <br/> |
|China North  <br/> |China North  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Medienqualität und ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute für Microsoft 365 oder Office 365 ist eine dedizierte Netzwerkverbindung zum Herstellen einer Verbindung mit Microsoft 365 oder Office 365. Sie bietet Kunden die Möglichkeit, die Kontrolle über den Pfad zu haben, den ihr Netzwerkdatenverkehr einnimmt. Sie müssen sich nicht mehr um das unvorhersehbare Routing im Internet sorgen, bei dem Daten von unbekannten Netzbetreibern, Anbietern und ISPs übertragen werden. Netzwerkdatenverkehr, der über ExpressRoute gesendet wird, wird direkt über das Netzwerk des ExpressRoute-Partners an das Netzwerk von Microsoft gesendet. Auf diese Weise können Kunden Microsoft 365 oder Office 365 so behandeln, als ob es sich in einem eigenen rechenzentrum außerhalb der Website mit einer dedizierten Verbindung befindet.
  
Azure ExpressRoute ist für alle Microsoft 365- und Office 365-Lizenzierungsangebote verfügbar. Das Azure ExpressRoute Premium-Add-On ist jedoch für Microsoft 365 und Office 365 erforderlich, um das globale Routing zu aktivieren. Kunden mit mindestens 500 Sitzen, die ExpressRoute implementieren, können das erforderliche *ExpressRoute Premium-Add-On* ohne zusätzliche Kosten erhalten.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>Ist ExpressRoute für eine gute Medienqualität erforderlich?

Azure ExpressRoute ist keine Anforderung, um die optimale Medienqualität von Skype for Business Online zu erhalten. Es ist jedoch eine der Bereitstellungsoptionen, mit deren Hilfe Sie sicherstellen können, dass Ihre Cloudkonnektivität die Ziele oder Schwellenwerte für die Netzwerkleistung von Skype for Business erfüllt.
  
Microsoft 365 und Office 365 sind leistungsstarke und sichere Dienste, die das Internet verwenden. Wir investieren weiterhin in neue Sicherheitsfunktionen und regionale Edgeknoten, um Die Sicherheit und Leistung kontinuierlich zu verbessern. Azure ExpressRoute ist keine Anforderung für Microsoft 365- oder Office 365-Dienste, einschließlich Skype for Business Online. Azure ExpressRoute ist eine der verfügbaren Bereitstellungsoptionen, mit deren Hilfe sichergestellt werden kann, dass die Konnektivität mit Microsoft 365 oder Office 365 den Anforderungen an die Netzwerkleistung von Skype for Business entspricht und die optimale Medienqualität von Skype for Business Online gewährleistet.
  
Für die Medienqualität von Skype for Business Online ist es wichtig, dass die Verbindung zwischen Ihren Unternehmenswebsites und den Microsoft-Netzwerkrändern die Leistungsziele in den Anforderungen an die Netzwerkleistung von einem [Skype for Business-Client](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) zum Microsoft Network Edge erfüllt und dass die Verbindung zwischen Ihren Netzwerkrändern und den Microsoft-Netzwerkrändern die Leistungsziele in den Anforderungen an die Netzwerkleistung von Ihrem Edge-Netzwerk zum [Microsoft-Netzwerk edge erfüllt.](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
Außerdem ist es wichtig, dass die physische Netzwerkkonnektivität Ihres Unternehmens, einschließlich ihrer internen Netzwerk- und Cloudkonnektivitätskapazität, spitzen Mediendatenverkehr aufnehmen kann. Azure ExpressRoute ist eine von vielen Möglichkeiten, mit deren Hilfe Kunden sicherstellen können, dass ihre Skype for Business Online-Cloudkonnektivität alle diese Leistungsanforderungen erfüllt.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>Ist ExpressRoute für die SLA für Sprachqualität erforderlich?

Nein, ExpressRoute ist für skype for Business Online Voice Quality SLA nicht erforderlich. Die [Skype for Business Online Voice Quality SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) gilt für alle berechtigten Anrufe, die von einem Skype for Business Online-Sprachdienstbenutzer innerhalb der richtigen Lizenz und des richtigen Abonnements platziert werden, die es diesem Benutzer ermöglichen, jede Art von VoIP- oder PSTN-Anruf zu führen. Eine Sla für die Sprachqualität sollte enthalten, dass alle folgenden Bedingungen erfüllt werden:
  
- Anrufe von microsoft-zertifizierten IP-Telefonen.
    
- Verkabelte Ethernetverbindungen.
    
- Probleme mit der Sprachqualität aufgrund von Microsoft Network-Problemen.
    
> [!NOTE]
> Die SLA für die Sprachqualität schließt anrufe aus, bei denen die geringe Anrufqualität durch Probleme in Nicht-Microsoft-Netzwerken, einschließlich ExpressRoute-Partner und anderen Netzwerken, verursacht wird. 
  
### <a name="internet-or-azure-expressroute"></a>Internet oder Azure ExpressRoute?

Bevor Kunden eine Entscheidung über Netzwerkkonnektivitätsoptionen mit Skype for Business Online treffen, müssen sie ihr Netzwerk und die aktuelle Internetverbindung basierend auf den netzwerkleistungsanforderungen bewerten, die unter Netzwerkleistungsanforderungen beschrieben sind, um eine Verbindung mit [Skype for Business Online herzustellen.](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)
  
Wenn die Netzwerkleistung über die aktuelle Internetverbindung für genügend Kapazität in Spitzenzeiten eingerichtet ist und die Netzwerkleistungsanforderungen von Websites zu Microsoft-Netzwerkrändern und von Ihren Netzwerkrändern bis zu Microsoft-Netzwerkrändern erfüllt werden, können Sie weiterhin Ihre vorhandene Internetverbindung verwenden, um eine Verbindung mit Skype for Business Online herzustellen.
  
Bei Unternehmenswebsites, auf denen die Anforderungen an die Netzwerkleistung nicht erfüllt werden, empfehlen wir dringend, zuerst mit Ihren vorhandenen Netzwerkdienstanbietern zusammen zu arbeiten, um die Gesamtnetzwerkleistung zu verbessern. Wenn sie jedoch immer noch nicht erfüllt werden, können Sie mit Azure ExpressRoute sicherstellen, dass Ihre Skype for Business Online-Cloudkonnektivität Ihnen dabei helfen kann, die Anforderungen an die Netzwerkleistung zu erfüllen.
  
Azure ExpressRoute bietet die folgenden zusätzlichen Vorteile:
  
- Ein Service Level Agreement (SLA) über die Verfügbarkeit der Verbindung zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk. ExpressRoute verfügt über eine garantierte Verfügbarkeits-SLA von 99,9 %.
    
- Geplante und garantierte Bandbreite für Microsoft 365- und Office 365-Dienste. Sie können dies erreichen, indem Sie nur Microsoft 365-, Office 365- oder Skype for Business-Datenverkehr über ExpressRoute senden und dann alle anderen Internetdatenverkehre über andere Internet-Ausgangs-/Ausgangspunkte für Ihr Netzwerk übertragen lassen.
    
- ExpressRoute wurde entwickelt, um DSCP-QoS-Markierungen zwischen Ihrem Netzwerk und dem Microsoft Network beizubehalten.
    
Weitere Informationen zu ExpressRoute QoS und der Kapazitätsplanung finden Sie unter [ExpressRoute und QoS in Skype for Business Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Kann ich Azure ExpressRoute nur für Skype for Business Online einrichten?

Ja, Sie können Azure ExpressRoute einrichten, um eine hervorragende Netzwerkkonnektivität vom Netzwerk Ihres Unternehmens zu nur Skype for Business Online sicherzustellen. Dies bietet die optimale Medienqualität Real-Time Benutzer, Sie können dann aber weiterhin eine Verbindung mit anderen Microsoft 365- oder Office 365-Diensten über das Internet herstellen.
  
Das Border Gateway Protocol (BGP) ist ein Routingprotokoll im Internet, das zum Weiterleiten des Netzwerkdatenverkehrs über das Internet verwendet wird. Es ist für den Austausch von Routinginformationen zwischen eigenständigen Systemen (AS) konzipiert, die über das Internet gefunden werden. BGP-Communitywerte sind Attributtags, die auf eingehende oder ausgehende Routen angewendet werden können. BGP-Communitys werden häufig verwendet, um dem empfangenden AS zu signalisieren, welcher ausgehende Link verwendet werden soll, um ein bestimmtes Ziel basierend auf geografischen, Diensttypen oder anderen Kriterien zu erreichen.
  
Mit der Unterstützung von BGP-Communitys tagft Microsoft Präfixe und Routen mit geeigneten BGP-Communitywerten basierend auf dem Dienst, dem sie angehören. Microsoft tagt Präfixe, die über öffentliches Peering und Microsoft-Peering angekündigt werden, mit geeigneten BGP-Communitywerten, die angeben, in welchem Bereich die Präfixe gehostet werden. Sie können sich auf die Communitywerte verlassen, um geeignete Routingentscheidungen zu treffen, um optimales Routing zu bieten. Sie können den Skype for Business Online BGP-Communitywert verwenden, um eine ExpressRoute-Verbindung nur für Skype for Business Online zu einrichten. Weitere Informationen finden Sie unter [ExpressRoute-Routinganforderungen.](/azure/expressroute/expressroute-routing)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>ExpressRoute-Konnektivitätsszenarien für Skype for Business Online
<a name="bkNetworkPerf"> </a>

Wenn Sie entschieden haben, dass ExpressRoute basierend auf den oben genannten Empfehlungen für Sie gilt, finden Sie hier die Empfehlungen, wo und wie viele ExpressRoute-Verbindungen Sie erhalten sollten.
  
### <a name="online-only-deployment---single-site"></a>Bereitstellung nur online – Einzelne Website

Wenn alle Ihre Benutzer den Skype for Business Online-Dienst verwenden und Ihre Niederlassungen sich um einen einzigen physischen Standort befinden und Sie sich für die Bereitstellung von Azure ExpressRoute entscheiden, sollten Sie eine einzelne ExpressRoute-Verbindung zwischen Ihrer Unternehmenswebsite und dem nächstgelegenen [ExpressRoute-Peeringstandort](/azure/expressroute/expressroute-locations)einrichten.
  
Die folgende Abbildung zeigt ein Beispiel für diesen Bereitstellungstyp. Für dieses Beispiel ist Contoso eine Universität in Orlando, FL. Contoso hat 10.000 Lehrkräfte und Studenten. Die Internettests von ihrem Standort zu Microsoft-Edgewebsites haben zu Spitzenklassenzeiten einen Paketverlust von mehr als 5 % ergeben. Sie haben sich entschieden, eine dedizierte Verbindung mit Microsoft 365 oder Office 365 mithilfe von ExpressRoute mit über bereitgestellter Bandbreite zu erhalten, damit sie die Netzwerküberlastung für Microsoft 365 oder Office 365 insbesondere für Skype for Business Online Real-Time datenverkehr vermeiden können. Sie stellen über ExpressRoute auf der Website Atlanta, GA MeetMe eine Verbindung mit der Microsoft-Cloud ein.
  
![Einzelne ExpressRoute-Website.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Bereitstellung nur online – Mehrere Websites auf demselben Kontinent

Wenn Ihr Unternehmen Skype for Business Online-Dienste von mehreren Niederlassungen in derselben Region oder demselben Kontinent aus verwendet und Sie Azure ExpressRoute implementiert haben, wird empfohlen, Ihre Hauptwebsite über ExpressRoute zu verbinden und dann optional zusätzliches ExpressRoute-Peering für andere Standorte hinzuzufügen, die nicht den empfohlenen Netzwerkleistungszielen entsprechen.
  
Im folgenden Beispiel ist Contoso ein US-amerikanisches Reisedienstunternehmen, das seinen Hauptsitz in New York hat, aber über andere Niederlassungen in den USA verfügt. Ihre Niederlassungen sind über ein WAN verbunden, das MPLS für die Verbindung mit Microsoft 365 oder Office 365 verwendet. Sie richten zunächst eine ExpressRoute-Verbindung von ihrem Internetrouter in Hoboken, New Jersey, zur New York MeetMe-Website ein. 
  
Mit diesem Setup kann der Netzwerkdatenverkehr von den meisten websites zum Microsoft Network (New York Edge-Website) die In-App-Netzwerkleistungsziele für Skype for Business-Clientverbindungen erfüllen, die unter Netzwerkleistungsanforderungen von einem Skype for Business-Client zu Microsoft Network Edge beschrieben [werden.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) Die Latenz zwischen den Niederlassungen an der Westküste von Contoso nach New York beträgt jedoch mehr als 50 ms one-way. Darüber hinaus ist Honolulu das zweitgrößte Büro für Contoso, die Latenz von Honolulu nach New York überschreitet 80 ms one-way. Um eine gute Medienqualität für die Benutzer in diesen Niederlassungen sicherzustellen, hat Contoso beschlossen, eine ExpressRoute-Westküstenverbindung zwischen ihrer Website in San Jose und der Silicon Valley ExpressRoute MeetMe-Website hinzuzufügen.
  
![Express Router Multi-Site auf demselben Kontinent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Bereitstellung nur online – Mehrere Websites auf verschiedenen Kontinenten

Wenn alle Ihre Benutzer den Skype for Business Online-Dienst verwenden und Sich Ihre Niederlassungen an mehreren physischen Standorten auf mehreren Kontinenten befinden, sollten Sie bei der Bereitstellung von Azure ExpressRoute mindestens eine ExpressRoute-Verbindung für jeden Kontinent zwischen dem Hauptstandort jedes Kontinents und dem nächstgelegenen [ExpressRoute-Peeringstandort](/azure/expressroute/expressroute-locations)einrichten. Je nach Kosten und Nutzen können Sie auswählen, ob Sie zusätzliche ExpressRoute-Verbindungen von Websites bereitstellen möchten, an denen die Netzwerkleistungsziele nicht erreicht werden.
  
Im folgenden Beispiel ist Contoso eine große Unternehmenskanzlei mit Niederlassungen in großen Städten in Nordamerika und Europa. Basierend auf der Internetverbindung und der Bewertung der internen Netzwerkleistung hat Contoso entschieden, zwei ExpressRoute-Verbindungen in Nordamerika und einen einzigen ExpressRoute-Schaltkreis für alle europäischen Niederlassungen zu implementieren.
  
![ExpressRoute mit mehreren Websites und Kontinenten.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Hybridbereitstellung

Wenn Sie über eine lokale Lync- oder Skype for Business-Bereitstellung verfügen und eine Skype for Business Online-Hybridintegration implementieren möchten, empfiehlt es sich, bei der Bereitstellung von Azure ExpressRoute mindestens eine ExpressRoute-Verbindung für jede lokale Lync- oder Skype for Business Edge-Website und mindestens eine ExpressRoute-Verbindung für jeden Kontinent mit Niederlassungen zu verwenden. Je nach Kosten und Nutzen können Sie für jeden Kontinent zusätzliche ExpressRoute-Verbindungen aus Niederlassungen bereitstellen, in denen die Netzwerkleistungsziele nicht erreicht werden.
  
Wenn Sie über eine lokale Skype for Business-Bereitstellung verfügen, müssen Sie den [Edgeserverplanungs- und -bereitstellungsleitfaden befolgen.](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md) Insbesondere müssen die Edgeserver von außerhalb Ihres Netzwerks erreichbar sein. Dies wird in der Regel entweder durch Zuweisen einer routablen öffentlichen IP-Adresse zum Edgeserver oder durch Verwenden der Netzwerkadressenübersetzung (Network Address Translation, NAT) erreicht.
  
Im folgenden Beispiel verfügt Contoso über eine lokale Skype for Business-Enterprise-VoIP Bereitstellung. Sie möchten lokale Benutzer zu Microsoft 365- oder Office 365-Onlinediensten migrieren. Sie entschieden sich außerdem für die Verwendung einer Hybridbereitstellung, damit sie weiterhin ihre vorhandene PSTN-Infrastruktur für alle lokalen und Onlinebenutzer nutzen können. Contosos lokales Rechenzentrum und Skype for Business Edge-Server befinden sich in Chicago. Für die Bereitstellung hat Contoso beschlossen, eine ExpressRoute-Verbindung zwischen ihrem Rechenzentrum in Chicago und Chicago ExpressRoute herzustellen. Sie haben auch eine ExpressRoute-Verbindung an der Westküste hinzugefügt, um ihr Honolulu-Büro besser bedienen zu können.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Onlinebereitstellung mit Cloud Connector Edition

Skype for Business Online Cloud Connector Edition ist ein Hybridangebot, das aus einer Reihe von gepackten virtuellen Computern (VMs) besteht, die lokale PSTN-Konnektivität implementieren. Durch die Bereitstellung einer minimalen Skype for Business Server-Topologie in einer virtualisierten Umgebung können Sie Anrufe mit Festnetz- und Mobiltelefonen über die vorhandene lokale PSTN-Sprachinfrastruktur senden und empfangen.
  
Wenn Sie sich für die Bereitstellung von Azure ExpressRoute und Cloud Connector Edition entscheiden, empfehlen wir Ihnen, mindestens eine ExpressRoute-Verbindung für jeden Kontinent zwischen dem Hauptstandort jedes Kontinents und dem nächstgelegenen [ExpressRoute-Peeringspeicherort](/azure/expressroute/expressroute-locations)einrichten. Je nach Kosten und Nutzen können Sie für jeden Kontinent zusätzliche ExpressRoute-Verbindungen von Standorten bereitstellen, an denen die Netzwerkleistungsziele nicht erreicht werden.
  
Wenn Sie über eine lokale Skype for Business-Bereitstellung verfügen, müssen Sie dem Planungshandbuch für [Skype for Business Cloud Connector Edition folgen.](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md) Insbesondere sollten den Access Edge- und A/V-Edgediensten öffentliche IP-Adressen und erreichbare Microsoft 365- oder Office 365-Rechenzentren zugewiesen werden.
  
Im folgenden Beispiel ist Contoso eine europäische Buchhaltungsfirma, die in einigen großen europäischen Ländern und Städten präsent ist. Als sie sich für alle Anforderungen an die Zusammenarbeit bei Skype for Business Online registrieren, entschieden sie sich, einen Cloud Connector für jedes Land, in dem sie über einen physischen Standort verfügen, zu verwenden, um ihre bereits vorhandenen Verträge für die PSTN-Infrastruktur und netzbetreiber weiterhin zu nutzen. Basierend auf ihren Tests von allen ihren Websites und Microsoft Network Edge haben sie festgestellt, dass eine einzelne ExpressRoute-Verbindung in London dazu beitragen wird, die In-App-Netzwerkleistungsziele für Skype for Business-Clientverbindungen zu erreichen, die unter Netzwerkleistungsanforderungen von [einem Skype for Business-Client](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)zu Microsoft Network Edge beschrieben werden.
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Im Folgenden finden Sie eine weitere Bereitstellungsoption für Contoso. In diesem Fall haben sie beschlossen, an jedem Standort, an dem ein Cloud Connector bereitgestellt wird, eine ExpressRoute-Verbindung einrichten. 
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute und QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

  
