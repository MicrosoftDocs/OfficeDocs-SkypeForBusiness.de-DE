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
description: In diesem Thema werden die Anforderungen an die Netzwerkleistung für Skype for Business Online-Dienste sowie die Verwendung des Internets oder von ExpressRoute für die Konnektivität zwischen Ihrem Netzwerk und Skype for Business Online basierend auf Ihrer Bewertung der Netzwerkkonnektivität definiert. Wenn Sie sich für die Bereitstellung von Azure ExpressRoute für dedizierte Konnektivität für Microsoft 365 oder Office 365 entschieden haben, finden Sie in diesem Dokument auch Anleitungen zum Planen Ihrer ExpressRoute-Verbindungen in verschiedenen Skype for Business Online-Bereitstellungsszenarien.
ms.openlocfilehash: 0bb750be4d4c21c8fec3cc8dc5d0ab5cf0b4cb6a
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240245"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Thema werden die Anforderungen an die Netzwerkleistung für Skype for Business Online-Dienste sowie die Verwendung des Internets oder von ExpressRoute für die Konnektivität zwischen Ihrem Netzwerk und Skype for Business Online basierend auf Ihrer Bewertung der Netzwerkkonnektivität definiert. Wenn Sie sich für die Bereitstellung von Azure ExpressRoute für dedizierte Konnektivität für Microsoft 365 oder Office 365 entschieden haben, finden Sie in diesem Dokument auch Anleitungen zum Planen Ihrer ExpressRoute-Verbindungen in verschiedenen Skype for Business Online-Bereitstellungsszenarien.
  
Die Qualität Real-Time End-to-End-Netzwerkkonnektivität hat großen Einfluss auf die Qualität der End-to-End-Netzwerkkonnektivität (Audio, Video und Anwendungsfreigabe) über IP. Für optimale Medienqualität in Skype for Business Online benötigen Sie eine Verbindung von hoher Qualität zwischen Ihrem Unternehmensnetzwerk und Skype for Business Online. Am besten orientieren Sie sich beim Einrichten der Konnektivität zwischen dem internen Netzwerk und der Cloud an der Kapazität des Netzwerks, damit auch Spitzendatenaufkommen für Skype for Business Online über alle Verbindungen kein Problem darstellen.
  
Azure ExpressRoute ist keine Voraussetzung für Dienste Microsoft 365 und Office 365, einschließlich Skype for Business Online. Azure ExpressRoute ist jedoch eine der verfügbaren Bereitstellungsoptionen, mit der Sie sicherstellen können, dass die Konnektivität mit Microsoft 365 oder Office 365 den Anforderungen an die Skype for Business-Netzwerkleistung entspricht und die optimale Medienqualität in Skype for Business Online gewährleistet.
  
> [!TIP]
> Obwohl dieses Thema allgemeine Richtlinien zur Netzwerkleistung bietet, werden vollständige Anleitungen für die Netzwerkbewertung nicht in diesem Dokument beschrieben. Eine Liste der Skype for Business Online-Partner, die Ihnen bei der Messung der Netzwerkleistung im Rahmen einer sorgfältigen und vollständigen Netzwerkbewertung helfen können, finden Sie auf der Seite Skype for Business [Partner Solutions.](http://partnersolutions.skypeforbusiness.com/) 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Anforderungen an die Netzwerkkonnektivität für Skype for Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Faktoren, die sich auf Skype for Business Onlinemedienqualität auswirken

Es gibt viele verschiedene Faktoren, die zu der Qualität von Skype for Business Online Real-Time-Medien (Audio, Video und Anwendungsfreigabe) beitragen, die die verwendeten Geräte, die Umgebung und die Netzwerkkonnektivität umfassen. 
  
#### <a name="devices"></a>Geräte

In einer Real-Time-Mediensitzung haben die von allen Teilnehmern verwendeten Geräte zum Aufzeichnen und Rendern von Medien, z. B. Headsets und Webcams, großen Einfluss auf die allgemeine Audio- und Videoqualität. Geräte von niedrigerer Qualität oder Geräte mit falschen Treibern erzeugen Audiomedien mit einer schlechteren allgemeinen Tonqualität sowie Videomedien mit einer schlechteren Bildqualität. Zertifizierte Geräte oder Geräte von hoher Qualität dagegen verbessern Echounterdrückung, Rauschunterdrückung und Videoauflösung und verringern die Latenz.
  
Zertifizierte Audio- und Videomediengeräte sind zwar nicht erforderlich, für optimale Medienqualität werden jedoch Skype for Business Geräte zertifiziert. Eine Liste aller zertifizierten Skype for Business finden Sie unter Telefone und [Geräte für Skype for Business.](../../SfbPartnerCertification/certification/devices-ip-phones.md) Mithilfe des [Skype for Business Online-Anrufqualitätsdashboards](/microsoftteams/turning-on-and-using-call-quality-dashboard)im **Skype for Business Admin Center** können Sie überprüfen, ob die verwendeten Geräte ordnungsgemäß funktionieren und die Audio- und Videomedienqualität überwachen.
  
> [!TIP]
> **Für optimale Medienqualität ist ein zertifiziertes** Gerät Skype for Business erforderlich.
  
Es ist wichtig daran zu denken, dass bei allen Mediengeräten, Skype for Business Clients und Skype for Business-Servern, Real-Time die Real-Time fließen, eine gewisse Latenz mit sich bringt. Die Latenz bei der Verarbeitung durch Geräte und Software sowie die Netzwerklatenz haben großen Einfluss auf die allgemeine End-to-End-Latenz und die Benutzerfreundlichkeit.
  
#### <a name="environment"></a>Umgebung

Die Umgebung und das Umfeld, in dem sich Nutzer treffen und Audio- und Videogeräte verwenden, stellen ebenfalls einen wichtigen Faktor für die Audio- und Videoqualität dar. Nutzer, die aus einer lauten Umgebung anrufen, hören gedämpften und undeutlichen Ton mit Echos. Nutzer in einer dunklen oder lichtarmen Umgebung können keine hellen und scharfen Videos erzeugen. In einem Konferenzraum wirkt sich die Position des Mikrofons und des Videogeräts direkt auf die Ton- und Bildqualität für die Teilnehmer aus.
  
Um ein klareres Bild der Audio- und Videowiedergabe eines Benutzers zu erhalten, verwenden Sie die Skype for Business-App ToolsOptionen  >    >  **Audiogerät** oder **Videogerät,** um Änderungen an dem verwendeten Gerät vorzunehmen und seine Einstellungen anzupassen.

#### <a name="network"></a>Netzwerk

Die Qualität der Real-Time ip-Netzwerk hat großen Einfluss auf die Qualität der Netzwerkkonnektivität, insbesondere durch die Anzahl der:
  
- **Latenz** Dies ist die Zeit, die es dauert, ein IP-Paket von Punkt A bis Punkt B im Netzwerk zu erhalten. Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Router. Latenz wird als One-Way- oder Round-Trip-Zeit (Round-Trip Time, RTT) gemessen.
    
- **Paketverlust** Dies ist häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Aufbruchsverlusten, die zu einer vollständigen Audioaufnahme führen.
    
- **Jitter zwischen der Ankunftszeit von Paketen oder einfach Jitter** Dies ist die durchschnittliche Änderung der Verzögerung zwischen aufeinander folgenden Paketen. Die meisten modernen VoIP-Skype for Business können sich durch Puffern an bestimmte Jitter-Ebenen anpassen. Erst wenn der Jitter die Pufferung übersteigt, bemerken die Teilnehmer die Auswirkungen.
    
> [!NOTE]
>  Durch Jitter-Puffern erhöht sich die End-to-End-Latenz.
  
Bei vielen gleichzeitigen Skype for Business Online Real-Time-Mediensitzungen sowie anderem Netzwerkdatenverkehr, der von anderen Microsoft 365- oder Office 365-Diensten und anderen Geschäftsanwendungen generiert wird, ist es wichtig sicherzustellen, dass über den gesamten Netzwerkpfad, der Ihr Netzwerk mit dem Skype for Business Online-Dienst verbindet, ausreichend Bandbreite verfügbar ist, um Netzwerküberlastung zu vermeiden und hervorragende Medienqualität Real-Time Medien (Audio, Video und Anwendungsfreigabe) sicherzustellen. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementieren von QoS (Quality of Service) in überlasteten Netzwerken

Außerdem wirkt sich eine Netzwerküberlastung erheblich auf die Medienqualität aus. Damit Audio- und Videopakete schneller in das Netzwerk übertragen werden und vor anderem Netzwerkdatenverkehr in einem überlasteten Netzwerk priorisiert werden können, kann Quality of Service (QoS) verwendet werden, um eine optimale Endbenutzererfahrung für die Audio- und Videokommunikation zu bieten.
  
QoS bietet Ihnen die Möglichkeit, Netzwerkpaketen, die Audio- oder Videodaten enthalten, höhere Prioritäten zuzuordnen. Durch die Zuweisung einer höheren Priorität zu diesen Paketen wird die Audio- und Videokommunikation wahrscheinlich schneller und mit weniger Unterbrechungen über das Netzwerk übertragen als Netzwerksitzungen mit Dateiübertragungen, Webbrowsen oder Datenbanksicherungen. Dies liegt daran, dass den für Dateiübertragungen oder Datenbanksicherungen verwendeten Netzwerkpaketen standardmäßig "Beste Leistung" als Priorität zugewiesen wird und eine Netzwerküberlastung nicht so große Auswirkungen hat. Wenn Sie den Medienpaketen (Audio, Video und Anwendungsfreigabe) keine höhere Priorität zuweisen und auch diese Pakete als "Beste Leistung" zugewiesen lassen, werden diese Pakete zusammen mit dem übrigen Netzwerkdatenverkehr verarbeitet. Je nach Umfang der Netzwerküberlastung kann dies zu einer insgesamt geringeren Audio- und Videoqualität für die Benutzer führen.
  
Es wird dringend empfohlen, QoS in Ihrem Netzwerk zu implementieren, um sicherzustellen, dass eine Netzwerküberlastung in Ihrem Netzwerk keine Auswirkungen hat. Damit dies jedoch die größtmögliche Wirkung hat, müssen alle Netzwerkendpunkte QoS unterstützen, was bedeutet, dass alle Endpunkte die QoS-Kennzeichnung und paket priorisieren müssen. Skype for Business Onlinedienste würdigen die QoS-Kennzeichnung und -Priorisierung innerhalb des Microsoft-Netzwerks. Der Datenverkehr, der über eine öffentliche Verbindung wie das Internet von Ihrem Unternehmensnetzwerk zum Microsoft-Netzwerk geroutet wird, behält jedoch nicht die QoS-Markierungen und die Paket priorisierung bei. Private Verbindungen von Ihrem Netzwerk zu Microsoft 365 oder Office 365 mit [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) bieten eine Bereitstellungslösung, bei der QoS-Markierungen und Paket priorisiert bleiben, die wiederum die allgemeine Audio- und Videoqualität für Ihre Endbenutzer verbessern.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Anforderungen an die Netzwerkleistung für Verbindungen mit Skype for Business Online
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Time können Medien auf vielen verschiedenen Geräten, Client-Apps, Serversoftware und in verschiedenen Netzwerken verwendet werden. Die End-to-End-Latenz Real-Time Medien ist die Gesamtlatenz, die für alle Komponenten und Netzwerksegmente eingeführt wird. Die Qualität der End-to-End-Netzwerkverbindung wird durch das Netzwerksegment mit der schlechtesten Qualität bestimmt. Dieses Segment dient als Engpass für diesen Netzwerkdatenverkehr.
  
Das folgende Diagramm veranschaulicht den one-way Audiofluss in einer Konferenz von Skype for Business Teilnehmer zu einem anderen.
  
![ExpressRoute-Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In diesem Konferenzszenario besteht der Medienpfad aus den folgenden Netzwerksegmenten:
  
1. **Verbindung von Benutzer 1 zum Edge des Microsoft-Netzwerks** Dazu gehören in der Regel eine Netzwerkverbindung wie WLAN oder Ethernet, die WAN-Verbindung von Benutzer 1 zum Internet-Ausgangspunkt (Ihr Netzwerk-Edge-Gerät) und die Internetverbindung von Ihrem Netzwerk-Edge zum Microsoft-Netzwerk-Edge.
    
2. **Verbindung innerhalb des Microsoft-Netzwerks** Dies liegt zwischen Microsoft Edge und Skype for Business Online-Rechenzentrum, in dem die A/V-Konferenzserver verwendet werden.
    
3. **Verbindung innerhalb des Microsoft-Netzwerks** Dieser befindet sich zwischen Skype for Business Online-Rechenzentrum und Microsoft-Netzwerk-Edge.
    
4. **Verbindung vom Microsoft-Netzwerk-Edge zu Benutzer 2** Dies umfasst die Internetverbindung von Ihrem Netzwerk-Edge zum Microsoft-Netzwerk-Edge, die WAN-Verbindung von Benutzer 2 zum Internet-Ausgangspunkt (Ihrem Netzwerk-Edge) und die Netzwerkverbindung wie wlan oder ethernet.
    
Das folgende Diagramm zeigt eine Aufschlüsselung der Komponenten und Netzwerksegmente eines Skype for Business PSTN-Anrufs:
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In einem PSTN-Anrufszenario durchquert der Medienpfad die folgenden Netzwerksegmente:
  
1. **Verbindung von einem Skype for Business-Clientanrufer zum Rand des Microsoft-Netzwerks herstellen** Dazu gehören in der Regel eine Netzwerkverbindung wie WLAN oder Ethernet, die WAN-Verbindung vom Skype for Business-Clientanrufer zum Internet-Ausgangspunkt (Ihr Netzwerk-Edge-Gerät) und die Internetverbindung von Ihrem Netzwerk-Edge zum Microsoft-Netzwerk-Edge.
    
2. **Verbindung innerhalb des Microsoft-Netzwerks** Dies liegt zwischen Microsoft Edge und Skype for Business Online-Rechenzentrum, in dem ein Vermittlungsserver verwendet wird.
    
3. **Verbindung innerhalb des Microsoft-Netzwerks** Dieser befindet sich zwischen Skype for Business Online-Rechenzentrum und Microsoft-Netzwerk-Edge.
    
4. **Verbindung zwischen Dem Microsoft-Netzwerk und den PSTN-Dienstanbieterpartnern** Dies ist die Verbindung, über die ein PSTN-Anruf über den Skype for Business erfolgt, der sich außerhalb des Microsoft-Netzwerks befindet.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Anforderungen an die Netzwerkleistung von einem Skype for Business zum Microsoft-Netzwerk-Edge
<a name="bkSfBClienttoEdge"></a>

Für optimale Skype for Business Medienqualität sind für eine Verbindung von Ihrem Unternehmensnetzwerk zum Microsoft-Netzwerk-Edge die folgenden Ziel- oder Schwellenwerte für Netzwerkleistungsmetriken erforderlich. Dieses Segment des Netzwerks umfasst Ihr internes Netzwerk, einschließlich aller WLAN- und Ethernet-Verbindungen, sämtlichen Datenverkehr zwischen Unternehmensstandorten über eine WAN-Verbindung, z. B. MPLS (Multiprotocol Label Switching), sowie die Internet- oder ExpressRoute-Partnerverbindungen zum Microsoft-Netzwerk-Edge.
  
> [!CAUTION]
> **Die Konnektivität zwischen einem Skype for Business-Client in Ihrem Unternehmensnetzwerk und Microsoft 365- oder Office 365-Dienste muss die folgenden Anforderungen und Schwellenwerte für die Netzwerkleistung erfüllen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |**Target** <br/> |
|Latenz (unidirektional)  <br/> |< 50 ms  <br/> |
|Latenz (RTT oder Round-Trip-Zeit)  <br/> |< 100 ms  <br/> |
|Burstverlust von Paketen  <br/> |<10 % in einem Intervall von 200 ms  <br/> |
|Paketverlust  <br/> |<1 % in einem Intervall von 15 Sekunden  <br/> |
|Jitter zwischen der Ankunftszeit von Paketen  <br/> |<30 ms in einem Intervall von 15 Ms  <br/> |
|Neuanordnung von Paketen  <br/> |< 0,05 % Pakete in falscher Reihenfolge  <br/> |
   
 **Weitere Leistungszielanforderungen:**
  
- Das Microsoft-Netzwerk verfügt über mehr als 160 Edge-Standorte weltweit. Über diese Edge-Websites arbeiten wir mit großen Internetdienstanbietern (ISPs) weltweit zusammen. Für das Metrikziel für die Latenz wird angenommen, dass sich der Standort Ihres Unternehmens und die Microsoft-Edges auf dem gleichen Kontinent befinden.
    
- Ihre Unternehmenswebsites oder Standorte mit der Microsoft-Netzwerk-Edge-Verbindung umfassen Netzwerkzugriff auf den ersten Hop, d. h. WLAN oder eine andere Funktechnologie. 
    
- Für das Ziel für die Netzwerkleistung wird von einer ordnungsgemäßen Planung der Bandbreite und/oder der Dienstqualität ausgegangen. Anders ausgedrückt: Dies gilt direkt für Skype for Business Real-Time, wenn die Netzwerkverbindung unter Spitzenlast steht.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Anforderungen an die Netzwerkleistung von Ihrem Netzwerk-Edge zum Microsoft-Netzwerk-Edge
<a name="bkYourNetworkEdge"> </a>

Im Folgenden werden die Ziele oder Schwellenwerte für die Netzwerkleistung bezeichnet, die für die Verbindung zwischen Ihrem Netzwerk-Edge und dem Microsoft-Netzwerk-Edge erforderlich sind. Dieses Segment des Netzwerks schließt das interne Netzwerk oder WAN des Kunden aus und dient als Leitfaden beim Testen des über das Internet oder über ein ExpressRoute-Partnernetzwerk gesendeten Netzwerkdatenverkehrs, das auch beim Aushandeln einer Leistungsvereinbarung zum Servicelevel (Service Level Agreement, SLA) mit Ihrem ExpressRoute-Anbieter verwendet werden kann.
  
> [!CAUTION]
> **Die Konnektivität zwischen Dem Edge Ihres Unternehmensnetzwerks und dem Microsoft-Netzwerk-Edge muss die folgenden Anforderungen und Schwellenwerte für die Netzwerkleistung erfüllen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |**Target** <br/> |
|Latenz (unidirektional)  <br/> |< 30 ms  <br/> |
|Latenz (RTT)  <br/> |< 60 ms  <br/> |
|Burstverlust von Paketen  <br/> |<1 % in einem Intervall von 200 ms  <br/> |
|Paketverlust  <br/> |<0,1 % in einem Intervall von 15 Sekunden  <br/> |
|Jitter zwischen der Ankunftszeit von Paketen  <br/> |<15 ms in einem Intervall von 15 ms  <br/> |
|Neuanordnung von Paketen  <br/> |< 0,01 % Pakete in falscher Reihenfolge  <br/> |
   
 **Weitere Leistungszielanforderungen:**
  
- Das Leistungsziel setzt eine Verbindung zwischen einem Netzwerk-Edge Ihres Unternehmens und dem nächstgelegenen Microsoft-Netzwerk-Edge auf dem gleichen Kontinent voraus.
    
- Für das Ziel für die Netzwerkleistung wird von einer ordnungsgemäßen Planung der Bandbreite und/oder der Dienstqualität ausgegangen. Dies gilt auch für Skype for Business Real-Time medienverkehr, wenn die Netzwerkverbindung unter Spitzenlast steht. Eine ordnungsgemäße Bandbreiten- und QoS-Planung finden Sie unter ExpressRoute und [QoS in Skype for Business Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>Messen der Netzwerkleistung
<a name="bkNetworkPerf"> </a>

Um die tatsächliche Netzwerkleistung, insbesondere für Latenz und Paketverlust, von einem beliebigen Standort im Unternehmensnetzwerk zu einem Netzwerk-Edge zu messen, können Sie Tools wie Ping verwenden und eine Reihe von Skype for Business Media Relay-Diensten testen, die von den Microsoft Edge- und Rechenzentrumsstandorten ausgeführt werden. 

>[!NOTE]
> Das Messen der Netzwerkleistung mithilfe von Ping (ICMP) ist nicht effektiv. Aus diesem Grund beantwortet die unten angezeigte Anycast-IP keine ICMP-Anforderungen mehr ab Januar 2020. Um die Leistung des Netzwerks effektiv zu messen, empfiehlt Microsoft das [Netzwerk-Assesment-Tool](https://www.microsoft.com/download/details.aspx?id=53885).
  
Zum Testen von Internetverbindungen zum Microsoft-Netzwerk sollten Sie die folgenden VIPs der Skype for Business Media Relays testen. Die *Anycast-VIP*  wird in eine IP-Adresse eines Media Relays auf einer Microsoft-Netzwerk-Edgewebsite aufgelöst, die dem Teststandort am nächsten ist.
  
||||
|:-----|:-----|:-----|
|**IP-Adresse** <br/> |**Typ** <br/> |**Standort** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |Weltweite Anycast-IP  <br/> |
   
 **Hier sind einige Empfehlungen auf einer hohen Ebene, die Sie bei der Bewertung der Netzwerkleistung beachten sollten:**
  
- Bewerten Sie Ihr internes Netzwerk sowie die Verbindungen zu Microsoft 365 Oder Office 365.
    
- Bewerten und sammeln Sie über einen langen Zeitraum Daten für alle Ihre Netzwerke. Es wird empfohlen, die Netzwerkleistung mindestens eine Woche lang zu testen, damit Nutzungsmuster für alle Werktage und -stunden zu sehen sind. Dadurch werden Spitzenzeiten für Sie gezeigt.
    
- Sie sollten mehrere Beispiele für Netzwerkleistungsmessungen verwenden. Es wird empfohlen, während des gesamten Zeitraums, in dem Sie Daten erfassen, alle 10 Minuten eine Messung von einer Unternehmenswebsite aus zu nehmen. Um die Anforderungen Skype for Business Online-Netzwerk zu vergleichen, nehmen Sie den Messwert für das 90. Percentile aus diesem Beispieldatenset. 
    
- Sie sollten die Leistung des Netzwerks kontinuierlich bewerten. Die Netzwerkauslastung variiert im Laufe der Zeit aufgrund von geänderten Nutzungsmustern, neuen unternehmensbasierten Anwendungen, die eine große Bandbreite verwenden, und Änderungen an den Organisations- oder physischen Unternehmensstandorten. Es ist wichtig, dass Sie die Netzwerkleistung kontinuierlich mit diesen Anforderungen und Ziel-/Schwellenwerten überwachen und zeitnahe Anpassungen vornehmen, um die bestmögliche Medienqualität Real-Time sicherzustellen. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Messen der Netzwerkleistung mit Azure-VMs
<a name="bkNetworkPerf"> </a>

Anstelle von Tests für die Microsoft-Netzwerk-Edge-Standorte gibt es Netzwerkbewertungslösungen von Skype for Business-Kunden und -Partnern, die die Einrichtung von Tests für Dienste in der Microsoft Azure nutzen. In diesen Lösungen testen die Netzwerkbewertungstools Latenz, Paketverlust und Jitter für benutzerdefinierte Endpunkte, die als Dienst in der Azure-Cloud eingerichtet wurden. Der Test-Netzwerkdatenverkehr durchlauft daher ein zusätzliches Netzwerksegment, d. h. die Verbindung innerhalb des Microsoft-Netzwerks zwischen den Netzwerk-Edges und Azure-Rechenzentren, in denen der Netzwerkbewertungsdienst gehostet wird.
  
Für diese auf gehosteten Azure-Testdiensten basierenden Netzwerkbewertungslösungen. Es wird empfohlen, die Netzwerkbewertung innerhalb des Landes und/oder der Region zu durchführen. Für Kundenwebsites im Osten der USA sollte die Bewertung beispielsweise für eine Testdienstinstanz durchgeführt werden, die im Azure-Rechenzentrum im Osten der USA gehostet wird. 
  
Im Folgenden werden die Latenz (RTT)-Ziele für das auf dem Azure-Dienst basierende Netzwerkbewertungseinrichtung aufgeführt. Die einwegigen Latenzziele machen die Hälfte der entsprechenden RTT-Ziele aus. Paketverlust und Jitter-Ziele entsprechen denjenigen, die für das Mediare relay-basierte Skype definiert wurden.
  
|||||
|:-----|:-----|:-----|:-----|
|**Kundenregion** <br/> |**Azure-Region** <br/> |**Ihr Netzwerk-Edge – Azure Round-Trip-Zeit (Round-Trip Time, RTT)** <br/> |**Ihre Website – Azure-Round-Trip-Zeit (Round-Trip Time, RTT)** <br/> |
|USA, Mitte  <br/> |USA, Mitte  <br/> |99  <br/> |139  <br/> |
|USA, Osten  <br/> |USA, Osten  <br/> |86  <br/> |126  <br/> |
|USA, Norden-Mitte  <br/> |USA, Norden-Mitte  <br/> |97  <br/> |137  <br/> |
|USA, Süden-Mitte  <br/> |USA, Süden-Mitte  <br/> |94  <br/> |134  <br/> |
|USA, Westen  <br/> |USA, Westen  <br/> |94  <br/> |134  <br/> |
|Hawaii, USA  <br/> |USA, Westen  <br/> |116  <br/> |156  <br/> |
|Kanada, Mitte  <br/> |Kanada, Mitte  <br/> |138  <br/> |178  <br/> |
|Kanada, Osten  <br/> |Kanada, Osten  <br/> |131  <br/> |171  <br/> |
|Europa, Norden  <br/> |Europa, Norden  <br/> |99  <br/> |139  <br/> |
|Europa, Westen  <br/> |Europa, Westen  <br/> |95  <br/> |135  <br/> |
|Ostasien  <br/> |Ostasien  <br/> |118  <br/> |158  <br/> |
|Südostasien  <br/> |Südostasien  <br/> |97  <br/> |137  <br/> |
|Japan, Osten  <br/> |Japan, Osten  <br/> |111  <br/> |151  <br/> |
|Japan, Westen  <br/> |Japan, Westen  <br/> |118  <br/> |158  <br/> |
|Brasilien, Süden  <br/> |Brasilien, Süden  <br/> |70  <br/> |110  <br/> |
|Australien, Osten  <br/> |Australien, Osten  <br/> |124  <br/> |164  <br/> |
|Australien, Südosten  <br/> |Australien, Südosten  <br/> |124  <br/> |164  <br/> |
|Indien, Mitte  <br/> |Indien, Mitte  <br/> |103  <br/> |143  <br/> |
|Indien, Süden  <br/> |Indien, Süden  <br/> |103  <br/> |143  <br/> |
|Indien, Westen  <br/> |Indien, Westen  <br/> |103  <br/> |143  <br/> |
|China, Osten  <br/> |China, Osten  <br/> |120  <br/> |160  <br/> |
|China, Norden  <br/> |China, Norden  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Medienqualität und ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute für Microsoft 365 oder Office 365 ist eine dedizierte Netzwerkverbindung zum Herstellen einer Verbindung mit Microsoft 365 oder Office 365. Sie bietet Kunden die Möglichkeit, den Pfad zu steuern, den ihr Netzwerkdatenverkehr einnimmt. Sie müssen sich nicht mehr mit dem unvorhersehbaren Routing im Internet sorgen, bei dem Daten von unbekannten Netzbetreibern, Anbietern und IsPs übertragen werden. Netzwerkdatenverkehr, der über ExpressRoute gesendet wird, wird direkt über das Netzwerk des ExpressRoute-Partners an das Netzwerk von Microsoft gesendet. So können Kunden Ihre Microsoft 365 oder Office 365 so behandeln, als ob sie sich in ihrem eigenen, nicht vor Ort vorhandenen Rechenzentrum mit einer dedizierten Verbindung befinden.
  
Azure ExpressRoute ist für alle Ihre Microsoft 365 und Office 365 verfügbar. Das Azure ExpressRoute-Premium-Add-On ist jedoch erforderlich, damit Benutzer Microsoft 365 und Office 365 globales Routing aktivieren können. Kunden mit mindestens 500 Sitzen, die ExpressRoute implementieren, können das erforderliche *ExpressRoute Premium Add-On* ohne zusätzliche Kosten erhalten.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>Ist ExpressRoute für eine gute Medienqualität erforderlich?

Azure ExpressRoute ist keine Voraussetzung für optimale Medienqualität Skype for Business Onlinemedien. Es ist jedoch eine der Bereitstellungsoptionen, mit der Sie sicherstellen können, dass Ihre Cloudkonnektivität die Skype for Business oder Schwellenwerte für die Netzwerkleistung erfüllt.
  
Microsoft 365 und Office 365 sind Hochleistung und sichere Dienste, die das Internet verwenden. Wir investieren ständig in neue Sicherheitsfunktionen und regionale Edgeknoten, um die Sicherheit und Leistung kontinuierlich zu verbessern. Azure ExpressRoute ist keine Voraussetzung für Microsoft 365 oder Office 365 Dienste, einschließlich Skype for Business Online. Azure ExpressRoute ist eine der verfügbaren Bereitstellungsoptionen, mit der sie sicherstellen können, dass die Konnektivität mit Microsoft 365 oder Office 365 den Anforderungen an die Skype for Business-Netzwerkleistung entspricht und die optimale Medienqualität in Skype for Business Online gewährleistet.
  
Für die Qualität von Skype for Business Online-Medien ist es wichtig, dass die Verbindung zwischen Ihren Unternehmensstandorten und den Microsoft-Netzwerk-Edges die Leistungsziele unter Anforderungen an die Netzwerkleistung von einem Skype for Business-Client zum [Microsoft-Netzwerk-Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) erfüllt und dass die Verbindung zwischen Ihren Netzwerk-Edges und den Microsoft-Netzwerk-Edges die Leistungsziele unter Anforderungen an die Netzwerkleistung von Ihrem Netzwerk-Edge zum [Microsoft-Netzwerk-Edge](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)erfüllt.  
  
Außerdem ist es wichtig, dass die Konnektivität des physischen Unternehmensnetzwerks einschließlich der Kapazität Ihres internen Netzwerks und der Cloudkonnektivität Spitzenaufkommen bei Mediendatenverkehr aufnehmen kann. Azure ExpressRoute ist eine von vielen Möglichkeiten, mit deren Hilfe Kunden sicherstellen können, dass Skype for Business Online-Cloudkonnektivität alle diese Leistungsanforderungen erfüllt.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>Ist ExpressRoute für SLA zur Sprachqualität erforderlich?

Nein, ExpressRoute ist nicht erforderlich, um SLA zur Skype for Business Online-Sprachqualität zu erhalten. Die [SLA zur Skype for Business Online-Sprachqualität](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) gilt für alle berechtigten Anrufe, die von einem beliebigen Benutzer des Skype for Business Online-VoIP-Diensts innerhalb der richtigen Lizenz und des richtigen Abonnements, die es diesem Benutzer ermöglicht, beliebige Arten von VoIP- oder PSTN-Anrufen zu verwenden. Eine SLA zur Sprachqualität sollte enthalten, dass alle folgenden Bedingungen erfüllt sind:
  
- Anrufe von Microsoft-zertifizierten IP-Telefonen.
    
- Verkabelte Ethernet-Verbindungen.
    
- Probleme mit der Sprachqualität aufgrund von Microsoft-Netzwerkproblemen.
    
> [!NOTE]
> Die SLA zur Sprachqualität schließt alle Anrufe aus, bei denen die geringe Anrufqualität durch Probleme in Nicht-Microsoft-Netzwerken, einschließlich ExpressRoute-Partner und anderen Netzwerken, verursacht wird. 
  
### <a name="internet-or-azure-expressroute"></a>Internet oder Azure ExpressRoute?

Vor der Entscheidung über Netzwerkkonnektivitätsoptionen für Skype for Business Online müssen Kunden ihr Netzwerk und die aktuelle Internetkonnektivität anhand der unter Anforderungen an die Netzwerkleistung für Verbindungen mit Skype for Business [Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)beschriebenen Anforderungen an die Netzwerkleistung bewerten.
  
Wenn die Netzwerkleistung über die aktuelle Internetverbindung für genügend Kapazität während Spitzenzeiten eingerichtet ist und die Anforderungen an die Netzwerkleistung von Standorten zu Microsoft-Netzwerk-Edges sowie von Ihren Netzwerk-Edges zu Microsoft-Netzwerk-Edges erfüllt sind, können Sie weiterhin Ihre vorhandene Internetverbindung verwenden, um eine Verbindung mit Skype for Business Online herzustellen.
  
Für Unternehmensstandorte, an denen die Anforderungen an die Netzwerkleistung nicht erfüllt werden, empfehlen wir dringend, dass Sie zuerst mit Ihren vorhandenen Netzwerkdienstanbietern zusammenarbeiten, um die allgemeine Netzwerkleistung zu verbessern. Wenn sie aber immer noch nicht erfüllt werden, können Sie mit Azure ExpressRoute sicherstellen, dass Ihre Skype for Business Online-Cloudkonnektivität ihnen dabei helfen kann, die Anforderungen an die Netzwerkleistung zu erfüllen.
  
Azure ExpressRoute bietet die folgenden zusätzlichen Vorteile:
  
- Eine Vereinbarung zum Servicelevel (Service Level Agreement, SLA) zur Verfügbarkeit der Verbindung zwischen Ihrem und dem Microsoft-Netzwerk. ExpressRoute bietet eine SLA zur garantierten Verfügbarkeit von 99,9 %.
    
- Geplante und garantierte für Microsoft 365 und Office 365 erforderliche Bandbreite. Zu diesem Ergebnis senden Sie nur Microsoft 365-, Office 365- oder Skype for Business-Datenverkehr über ExpressRoute und lassen dann den übrigen Internetverkehr über andere Internet-Ausgangs- und -Ausgangspunkte Ihres Netzwerks zurück.
    
- ExpressRoute ist darauf ausgelegt, DIE DSCP-QoS-Markierungen zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk beizubehalten.
    
Weitere Informationen zu ExpressRoute-QoS und zur Kapazitätsplanung finden Sie unter ExpressRoute und [QoS in Skype for Business Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Kann ich Azure ExpressRoute nur für Skype for Business Online einrichten?

Ja, Sie können Azure ExpressRoute einrichten, um hervorragende Netzwerkkonnektivität vom Netzwerk Ihres Unternehmens zu nur Skype for Business Online sicherzustellen. Dadurch erhalten Sie die optimale Medienqualität Real-Time Benutzer, können aber weiterhin Verbindungen mit anderen Microsoft 365- oder Office 365-Diensten über das Internet herstellen.
  
Das BGP (Border Gateway Protocol) ist ein Routingprotokoll im Internet, das zum Weiterleiten von Netzwerkdatenverkehr über das Internet verwendet wird. Es ist für den Austausch von Routinginformationen zwischen eigenständigen Systemen (AS) aus dem Internet konzipiert. BGP-Communitywerte sind Attributtags, die auf eingehende oder ausgehende Routen angewendet werden können. BGP-Communitys werden häufig verwendet, um dem empfangenden AS zu signalisieren, welcher ausgehende Link verwendet werden soll, um ein bestimmtes Ziel basierend auf Geographie, Diensttyp oder anderen Kriterien zu erreichen.
  
Mit der Unterstützung von BGP-Communitys tagft Microsoft Präfixe und Routen mit entsprechenden BGP-Communitywerten basierend auf dem Dienst, dem sie angehören. Microsoft tagft Präfixe, die über öffentliches Peering und Microsoft-Peering angekündigt werden, mit entsprechenden BGP-Communitywerten, die die Region angeben, in der die Präfixe gehostet werden. Sie können sich auf die Community-Werte verlassen, um geeignete Routingentscheidungen zu treffen, um optimales Routing zu bieten. Sie können den BGP Skype for Business Wert der Online-BGP-Community verwenden, um eine ExpressRoute-Verbindung nur für ihre Skype for Business einrichten. Weitere Informationen finden Sie unter [ExpressRoute-Routinganforderungen.](/azure/expressroute/expressroute-routing)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>ExpressRoute-Konnektivitätsszenarien für Skype for Business Online
<a name="bkNetworkPerf"> </a>

Wenn Sie aufgrund der oben genannten Empfehlungen entschieden haben, dass ExpressRoute für Sie da ist, finden Sie hier Empfehlungen dazu, wo und wie viele ExpressRoute-Verbindungen Sie erhalten sollten.
  
### <a name="online-only-deployment---single-site"></a>Nur Onlinebereitstellung – Einzelne Website

Wenn alle Benutzer den Skype for Business Online-Dienst nutzen und sich Ihre Niederlassungen an einem einzigen physischen Standort befinden und Sie sich für die Bereitstellung von Azure ExpressRoute entscheiden, sollten Sie eine einzelne ExpressRoute-Verbindung zwischen Ihrem Unternehmensstandort und dem nächstgelegenen [ExpressRoute-Peeringstandort](/azure/expressroute/expressroute-locations)einrichten.
  
Die folgende Abbildung zeigt ein Beispiel für diese Art der Bereitstellung. Für dieses Beispiel ist Contoso eine Universität in Orlando, Florida. Contoso verfügt über 10.000 Lehrpersonalmitglieder und Studenten. Bei den Internettests von ihrem Standort zu den Microsoft-Edge-Standorten wurde ein Paketverlust von mehr als 5 % während der Spitzenklassenzeiten deutlich. Sie haben sich entschieden, eine dedizierte Verbindung zu Microsoft 365 oder Office 365 über ExpressRoute mit über bereitstellender Bandbreite zu erhalten, um eine Netzwerküberlastung für Microsoft 365 oder Office 365 speziell für Skype for Business Online-Real-Time-Datenverkehr zu vermeiden. Die Verbindung zur Microsoft-Cloud wird über ExpressRoute am MeetMe-Standort in Atlanta, GA, hergestellt.
  
![ExpressRoute für einen Standort.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Nur Onlinebereitstellung – mehrere Standorte auf dem gleichen Kontinent

Wenn Ihr Unternehmen Skype for Business Online-Dienste aus mehreren Niederlassungen in derselben Region oder auf dem gleichen Kontinent verwendet und Sie sich für die Implementierung von Azure ExpressRoute entschieden haben, empfiehlt es sich, den Hauptstandort über ExpressRoute zu verbinden und dann optional zusätzliches ExpressRoute-Peering für andere Standorte hinzuzufügen, die die empfohlenen Ziele für die Netzwerkleistung nicht erfüllen.
  
Im folgenden Beispiel ist Contoso ein US-amerikanisches Reisedienstleister mit Hauptsitz in New York und weiteren Niederlassungen in den USA. Ihre Niederlassungen sind über ein WAN miteinander verbunden, das MPLS für die Verbindung zu Microsoft 365 oder Office 365. Sie richten zunächst eine ExpressRoute-Verbindung von ihrem Internetrouter in Hoboken, New Jersey, zum MeetMe-Standort in New York ein. 
  
Bei diesem Setup kann der Netzwerkdatenverkehr von den meisten Standorten zum Microsoft-Netzwerk (Edge-Standort in New York) die unter Anforderungen an die Netzwerkleistung von einem Skype for Business-Client zum [Microsoft-Netzwerk-Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)beschriebenen Ziele für die Netzwerkleistung der Skype for Business-Clientverbindung erfüllen. Die Latenz zwischen den Contoso-Niederlassungen an der Westküste und new York beträgt jedoch mehr als 50 ms (in eine Richtung). Darüber hinaus überschreitet die Latenz von Honolulu, der zweitgrößten Office für Contoso, bis New York 80 ms (einmal). Um eine gute Medienqualität für die Benutzer in diesen Niederlassungen sicherzustellen, hat Contoso beschlossen, eine ExpressRoute-Verbindung an der Westküste zwischen dem Standort in San Francisco und dem MeetMe-Standort im Silicon Valley ExpressRoute hinzuzufügen.
  
![Express Router für mehrere Standorte auf dem gleichen Kontinent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Nur Onlinebereitstellung – mehrere Standorte auf unterschiedlichen Kontinenten

Wenn alle Ihre Benutzer den Skype for Business Online-Dienst verwenden und sich Ihre Niederlassungen an mehreren physischen Standorten auf mehreren Kontinenten befinden, sollten Sie bei Bereitstellung von Azure ExpressRoute mindestens eine ExpressRoute-Verbindung für jeden Kontinent zwischen dem Hauptstandort auf jedem Kontinent und dem nächstgelegenen [ExpressRoute-Peeringstandort](/azure/expressroute/expressroute-locations)einrichten. Je nach Kosten und Nutzen können Sie zusätzliche ExpressRoute-Verbindungen von Standorten bereitstellen, an denen die Ziele für die Netzwerkleistung nicht erreicht werden.
  
Im folgenden Beispiel ist Contoso eine große Wirtschaftskanzlei mit Niederlassungen in Großstädten in Nordamerika und Europa. Aufgrund der Internetverbindung und der Bewertung der Leistung des internen Netzwerks hat Contoso beschlossen, zwei ExpressRoute-Verbindungen in Nordamerika und eine einzige ExpressRoute-Verbindung für alle europäischen Niederlassungen zu implementieren.
  
![ExpressRoute mit mehreren Standorten und Kontinenten.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Hybridbereitstellung

Wenn Sie eine lokale Lync- oder Skype for Business-Bereitstellung haben und sich für die Implementierung einer hybriden Skype for Business Online-Integration entscheiden, empfehlen wir bei Bereitstellung von Azure ExpressRoute mindestens eine ExpressRoute-Verbindung für jeden lokalen Lync- oder Skype for Business-Edge-Standort und mindestens eine ExpressRoute-Verbindung für jeden Kontinent mit Niederlassungen. Je nach Kosten und Nutzen können Sie für jeden Kontinent zusätzliche ExpressRoute-Verbindungen von Niederlassungen bereitstellen, in denen die Ziel für die Netzwerkleistung nicht erreicht werden.
  
Wenn Sie über eine lokale Bereitstellung Skype for Business verfügen, müssen Sie das Handbuch zur Planung und Bereitstellung von [Edgeservern befolgen.](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md) Insbesondere müssen die Edgeserver von außerhalb Ihres Netzwerks erreichbar sein. Dies wird in der Regel erreicht, indem dem Edgeserver eine routbare öffentliche IP-Adresse zugewiesen oder Netzwerkadressenübersetzung (Network Address Translation, NAT) verwendet wird.
  
Im folgenden Beispiel verfügt Contoso über eine lokale Skype for Business Enterprise-VoIP Bereitstellung. Sie möchten lokale Benutzer zu Ihren online Microsoft 365 oder Office 365 migrieren. Sie entschieden sich außerdem für die Verwendung einer Hybridbereitstellung, damit sie ihre vorhandene PSTN-Infrastruktur weiterhin für alle lokalen und Onlinebenutzer nutzen können. Contosos lokales Rechenzentrum und die Skype for Business Edgeserver befinden sich in Chicago. Für die Bereitstellung hat Contoso beschlossen, eine ExpressRoute-Verbindung zwischen dem Rechenzentrum in Chicago und der Chicago ExpressRoute herzustellen. Außerdem wurde eine ExpressRoute-Verbindung für die Westküste hinzugefügt, um das Büro in Honolulu besser bedienen zu können.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Onlinebereitstellung mit Cloud Connector Edition

Skype for Business Online Cloud Connector Edition ist ein Hybridangebot, das aus einem Satz paketierter virtueller Computer (Virtual Machines, VMs) besteht, die lokale PSTN-Anbindung implementieren. Durch die Bereitstellung einer minimalen Skype for Business Server-Topologie in einer virtualisierten Umgebung können Sie anrufe über Festnetztelefone und Mobiltelefone über die vorhandene lokale PSTN-Sprachinfrastruktur senden und empfangen.
  
Wenn Sie sich für die Bereitstellung von Azure ExpressRoute und Cloud Connector Edition entscheiden, empfehlen wir, mindestens eine ExpressRoute-Verbindung für jeden Kontinent zwischen dem Hauptstandort auf jedem Kontinent und dem nächstgelegenen [ExpressRoute-Peeringstandort zu erstellen.](/azure/expressroute/expressroute-locations) Je nach Kosten und Nutzen können Sie für jeden Kontinent zusätzliche ExpressRoute-Verbindungen von Standorten bereitstellen, an denen die Ziel für die Netzwerkleistung nicht erreicht werden.
  
Wenn Sie über eine lokale Bereitstellung Skype for Business verfügen, müssen Sie sich an das [Planungshandbuch für Skype for Business Cloud Connector Edition.](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md) Insbesondere sollten den Access Edge- und A/V-Edgediensten öffentliche IP-Adressen und erreichbare Microsoft 365 oder Office 365-Rechenzentren zugewiesen werden.
  
Im folgenden Beispiel ist Contoso eine europäische Buchhaltung mit Anwesenheit in einigen europäischen Großstädten. Wenn sie sich für Skype for Business Online registrieren, um alle Anforderungen an die Zusammenarbeit zu erfüllen, hat sie sich entschieden, Cloud Connector für jedes Land, in dem es einen physischen Standort hat, zu erstellen, um seine PSTN-Infrastruktur und die bereits vorhandenen Netzbetreiberverträge weiterhin zu nutzen. Basierend auf den Tests aller Standorte und des Microsoft-Netzwerk-Edge wurde festgestellt, dass eine einzelne ExpressRoute-Verbindung in London die unter Anforderungen an die Netzwerkleistung von einem Skype for Business-Client zum [Microsoft-Netzwerk-Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)beschriebenen Ziele für die Netzwerkleistung der Skype for Business-Clientverbindung erfüllen kann.
  
![ExpressRoute Cloud Connector eins.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Im Folgenden finden Sie eine weitere Bereitstellungsoption für Contoso. In diesem Fall hat es sich entschieden, an jedem Standort, an dem Cloud Connector bereitgestellt ist, eine ExpressRoute-Verbindung herzustellen. 
  
![ExpressRoute Cloud Connector zwei.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Verwandte Themen

[ExpressRoute und QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

  
