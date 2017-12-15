---
title: "Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/21/2016
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
description: "In diesem Thema werden die Anforderungen an die Netzwerkleistung für Skype for Business Online-Dienste beschrieben. Außerdem erfahren Sie, wie Sie die Konnektivität zwischen Ihrem Netzwerk und Skype for Business Online wahlweise über das Internet oder über ExpressRoute herstellen können. Entscheidend ist dabei, wie Sie Ihre Netzwerkkonnektivität bewerten. Wenn Sie sich dafür entschieden haben, Azure ExpressRoute für dedizierte Konnektivität mit Office 365 bereitzustellen, erhalten Sie hier außerdem Ratschläge zum Planen der ExpressRoute-Verbindungen in verschiedenen Skype for Business Online-Bereitstellungsszenarien."
---

# Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online

In diesem Thema werden die Anforderungen an die Netzwerkleistung für Skype for Business Online-Dienste beschrieben. Außerdem erfahren Sie, wie Sie die Konnektivität zwischen Ihrem Netzwerk und Skype for Business Online wahlweise über das Internet oder über ExpressRoute herstellen können. Entscheidend ist dabei, wie Sie Ihre Netzwerkkonnektivität bewerten. Wenn Sie sich dafür entschieden haben, Azure ExpressRoute für dedizierte Konnektivität mit Office 365 bereitzustellen, erhalten Sie hier außerdem Ratschläge zum Planen der ExpressRoute-Verbindungen in verschiedenen Skype for Business Online-Bereitstellungsszenarien.
  
Die Qualität der End-to-End-Netzwerkkonnektivität hat großen Einfluss auf die Qualität von Echtzeitmedien (Audio, Video und Anwendungsfreigabe) über IP. Für optimale Medienqualität in Skype for Business Online benötigen Sie eine Verbindung von hoher Qualität zwischen Ihrem Unternehmensnetzwerk und Skype for Business Online. Am besten orientieren Sie sich beim Einrichten der Konnektivität zwischen dem internen Netzwerk und der Cloud an der Kapazität des Netzwerks, damit auch Spitzendatenaufkommen für Skype for Business Online über alle Verbindungen kein Problem darstellen.
  
Azure ExpressRoute ist für Office 365-Dienste wie beispielsweise Skype for Business Online nicht erforderlich. Azure ExpressRoute ist jedoch eine der verfügbaren Bereitstellungsoptionen, mit der Sie dafür sorgen können, dass die Konnektivität mit Office 365 den Anforderungen von Skype for Business an die Netzwerkleistung entspricht. Außerdem wird die optimale Medienqualität in Skype for Business Online sichergestellt.
  
> [!TIP]
> Sie erhalten in diesem Thema nur allgemeine Ratschläge zur Netzwerkleistung, eine vollständige Anleitung für die Netzwerkbewertung würde den Rahmen dieses Dokuments sprengen. Eine Liste mit Skype for Business Online-Partnern, die Ihnen beim Messen der Netzwerkleistung im Rahmen einer umfassenden und vollständigen Netzwerkbewertung helfen können, finden Sie auf der [Website mit Partnerlösungen für Skype for Business](http://partnersolutions.skypeforbusiness.com/). 
  
## Anforderungen an die Netzwerkkonnektivität für Skype for Business Online

### Faktoren, die sich auf die Medienqualität in Skype for Business Online auswirken

Viele verschiedene Faktoren tragen zur Qualität von Echtzeitmedien (Audio, Video und Anwendungsfreigabe) in Skype for Business Online bei. Dazu gehören die verwendeten Geräte, die Umgebung und die Netzwerkkonnektivität. 
  
#### Geräte

In einer Echtzeitmedien-Sitzung haben die von allen Teilnehmern verwendeten Geräte für das Erfassen und Rendern von Medien, zum Beispiel Headsets und Webcams, großen Einfluss auf die allgemeine Audio- und Videoqualität. Geräte von niedrigerer Qualität oder Geräte mit falschen Treibern erzeugen Audiomedien mit einer schlechteren allgemeinen Tonqualität sowie Videomedien mit einer schlechteren Bildqualität. Zertifizierte Geräte oder Geräte von hoher Qualität dagegen verbessern Echounterdrückung, Rauschunterdrückung und Videoauflösung und verringern die Latenz.
  
Zertifizierte Audio- und Videomediengeräte sind zwar nicht erforderlich, aber die bestmögliche Medienqualität erzielen Sie, wenn Sie für Skype for Business zertifizierte Geräte verwenden. Eine Liste aller entsprechend zertifizierten Geräte finden Sie unter [Phones and Devices for Skype for Business](https://technet.microsoft.com/en-us/office/dn947482) (Mobiltelefone und Geräte für Skype for Business). Mit dem[Qualitätsdashboard für Anrufe mit Skype for Business Online](https://support.office.com/en-us/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c?ui=en-US&amp;rs=en-US&amp;ad=US), das Sie im **Skype for Business Admin Center** finden, können Sie überprüfen, ob die genutzten Geräte richtig funktionieren, und die Qualität von Audio- und Videomedien überwachen.
  
> [!TIP]
> **Die optimale Medienqualität in Skype for Business erzielen Sie mit einem zertifizierten Gerät**.
  
Denken Sie daran, dass durch alle Mediengeräte, Skype for Business-Clients und Skype for Business-Server, durch die Echtzeitmedien fließen, eine gewisse Latenz entsteht. Die Latenz bei der Verarbeitung durch Geräte und Software sowie die Netzwerklatenz haben großen Einfluss auf die allgemeine End-to-End-Latenz und die Wahrnehmung durch die Endbenutzer.
  
#### Umgebung

Die Umgebung und das Umfeld, in dem sich Nutzer treffen und Audio- und Videogeräte verwenden, stellen ebenfalls einen wichtigen Faktor für die Audio- und Videoqualität dar. Nutzer, die aus einer lauten Umgebung anrufen, hören gedämpften und undeutlichen Ton mit Echos. Nutzer in einer dunklen oder lichtarmen Umgebung können keine hellen und scharfen Videos erzeugen. In einem Konferenzraum wirkt sich die Position des Mikrofons und des Videogeräts direkt auf die Ton- und Bildqualität für die Teilnehmer aus.
  
Einen besseren Eindruck davon, wie Nutzer Audio und Video erleben, können Sie sich mit der Skype for Business-App verschaffen. Unter **Extras** > **Optionen** > **Audiogerät** oder **Videogerät** können Sie Änderungen für das verwendete Gerät vornehmen und die Einstellungen anpassen. Sie können auch die Audioqualität eines Anrufs überprüfen, indem Sie auf **Anrufqualität überprüfen** klicken. Wenn Sie auf **Anrufqualität überprüfen** klicken, können Sie anschließend die Qualität des Testanrufs bewerten und aufgetretene Probleme melden.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### Netzwerk

Die Qualität der Netzwerkkonnektivität hat großen Einfluss auf die Qualität von Echtzeitmedien über das IP-Netzwerk. Besonders wichtig sind dabei folgende Werte:
  
- **Latenz**: Dieser Wert gibt an, wie lange es dauert, ein IP-Paket im Netzwerk von Punkt A zu Punkt B zu übertragen. Diese Verzögerung bei der Netzwerkverteilung ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verbunden. Dazu gehört auch der zusätzliche Aufwand durch die verschiedenen zwischen den Punkten positionierten Router. Die Latenz wird als One-Way-Zeit oder Round-Trip-Zeit (Round-Trip Time, RTT) gemessen.
    
- **Paketverlust**: Dieser Wert wird oft als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus - von einzelnen kleinen verlorenen Paketen, die praktisch keine Auswirkungen haben, bis hin zu aufeinanderfolgenden Burst-Verlusten, die zu Tonaussetzern führen.
    
- **Jitter zwischen der Ankunftszeit von Paketen oder einfach Jitter**: Dies ist die durchschnittliche Veränderung der Verzögerung zwischen aufeinanderfolgenden Paketen. Die meisten modernen VoIP-Softwareprodukte wie auch Skype for Business können durch Puffern ein gewisses Maß an Jitter ausgleichen. Erst wenn der Jitter die Pufferung übersteigt, bemerken die Teilnehmer die Auswirkungen.
    
> [!NOTE]
>  Durch Jitter-bedingtes Puffern steigt die End-to-End-Latenz.
  
Bei vielen gleichzeitigen Echtzeitmedien-Sitzungen in Skype for Business Online sowie zusätzlichem Netzwerkverkehr durch andere Office 365-Dienste und Geschäfts-Apps muss ausreichende Bandbreite im gesamten Netzwerkpfad zwischen Ihrem Netzwerk und dem Skype for Business Online-Dienst sichergestellt sein. Dadurch vermeiden Sie Netzwerküberlastung und sorgen für hervorragende Qualität von Echtzeitmedien (Audio, Video und Anwendungsfreigabe). 
  
#### Implementieren von QoS (Quality of Service) in überlasteten Netzwerken

Außerdem wird durch Verkehrsüberlastung in einem Netzwerk die Medienqualität deutlich beeinträchtigt. Sie können die Audio- und Videokommunikation für die Endbenutzer verbessern, indem Sie mit QoS die schnellere Übertragung von Audio- und Videopaketen im Netzwerk und ihre Priorisierung gegenüber anderem Netzwerkverkehr in einem überlasteten Netzwerk ermöglichen.
  
Mit QoS können Sie Netzwerkpaketen, die Audio- oder Videodaten enthalten, eine höhere Priorität zuweisen. Durch die Zuweisung einer höheren Priorität zu diesen Paketen kann die Audio- und Videokommunikation schneller und mit weniger Unterbrechungen im Netzwerk übertragen werden als Netzwerksitzungen, an denen Dateiübertragungen, Webbrowsen oder Datenbanksicherungen beteiligt sind. Das ist darauf zurückzuführen, dass die für Dateiübertragungen oder Datenbanksicherungen verwendeten Netzwerkpakete standardmäßig die Priorität „Beste Leistung" erhalten und die Netzwerküberlastung sich dann nicht so stark auswirkt. Wenn Sie den Medienpaketen (Audio, Video und Anwendungsfreigabe) keine höhere Priorität zuweisen und außerdem die Kennzeichnung „Beste Leistung" beibehalten, werden diese Pakete zusammen mit dem übrigen Netzwerkverkehr verarbeitet. Je nach Ausmaß der Netzwerküberlastung kann dies dazu führen, dass die Nutzer eine allgemein niedrigere Audio- und Videoqualität wahrnehmen.
  
Es wird dringend empfohlen, QoS im Netzwerk zu implementieren, um Beeinträchtigungen durch Netzwerküberlastung zu verhindern. Dazu müssen jedoch alle Endpunkte im Netzwerk QoS unterstützen, das heißt, alle Endpunkte müssen die QoS-Kennzeichnung und die Paketprioritäten respektieren. Skype for Business Online-Dienste respektieren die QoS-Kennzeichnung und -Priorisierung innerhalb des Microsoft-Netzwerks. Wenn jedoch Datenverkehr aus Ihrem Unternehmensnetzwerk über eine öffentliche Verbindung wie das Internet an das Microsoft-Netzwerk weitergeleitet wird, bleiben die QoS-Kennzeichnungen und die Paketprioritäten nicht erhalten. Private Verbindungen aus Ihrem Netzwerk zu Office 365 über [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) bieten eine Bereitstellungslösung, bei der die QoS-Kennzeichnungen und die Paketprioritäten erhalten bleiben, sodass die Audio- und Videoqualität für die Endbenutzer gesteigert wird.
  
## Anforderungen an die Netzwerkleistung für Verbindungen mit Skype for Business Online
<a name="bk_NetworkPerf"> </a>

Skype for Business-Echtzeitmedien durchlaufen viele verschiedene Geräte, Client-Apps, Serversoftwareprodukte und Netzwerke. Die End-to-End-Latenz von Echtzeitmedien entspricht der Gesamtlatenz, die zwischen allen Komponenten und Netzwerksegmenten entsteht. Ausschlaggebend für die Qualität der End-to-End-Netzwerkverbindung ist das Netzwerksegment mit der niedrigsten Qualität. Dieses Segment stellt einen Engpass für den jeweiligen Netzwerkverkehr dar.
  
Das folgende Diagramm veranschaulicht einen unidirektionalen Audiofluss zwischen Skype for Business-Teilnehmern in einer Konferenz.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In diesem Konferenzszenario besteht der Medienpfad aus den folgenden Netzwerksegmenten:
  
1. **Verbindung von Nutzer 1 zum Edge des Microsoft-Netzwerks**: Dazu gehören normalerweise eine Netzwerkverbindung über WLAN oder Ethernet, die WAN-Verbindung von Nutzer 1 zum Internetausgangspunkt (Ihrem Netzwerk-Edge-Gerät) und die Internetverbindung von Ihrem Netzwerk-Edge zum Microsoft-Netzwerk-Edge.
    
2. **Verbindung innerhalb des Microsoft-Netzwerks**: Diese Verbindung besteht zwischen dem Microsoft Edge und dem Skype for Business Online-Rechenzentrum, in dem die A/V-Konferenzserver verwendet werden.
    
3. **Verbindung innerhalb des Microsoft-Netzwerks**: Diese Verbindung besteht zwischen dem Skype for Business Online-Rechenzentrum und dem Microsoft-Netzwerk-Edge.
    
4. **Verbindung vom Microsoft-Netzwerk-Edge zu Nutzer 2**: Dazu gehören die Internetverbindung von Ihrem Netzwerk-Edge, die WAN-Verbindung von Nutzer 2 zum Internetausgangspunkt (Ihrem Netzwerk-Edge) und die Netzwerkverbindung über WLAN oder Ethernet.
    
Das folgende Diagramm zeigt die Aufteilung der Komponenten und Netzwerksegmente eines PSTN-Anrufs über Skype for Business Online:
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In diesem Szenario eines PSTN-Anrufs durchquert der Medienpfad die folgenden Netzwerksegmente:
  
1. **Verbindung von einem Skype for Business-Client-Anrufer zum Edge des Microsoft-Netzwerks**: Dazu gehören normalerweise eine Netzwerkverbindung über WLAN oder Ethernet, die WAN-Verbindung vom Skype for Business-Client-Anrufer zum Internetausgangspunkt (Ihrem Netzwerk-Edge-Gerät) und die Internetverbindung von Ihrem Netzwerk-Edge zum Microsoft-Netzwerk-Edge.
    
2. **Verbindung innerhalb des Microsoft-Netzwerks**: Diese Verbindung besteht zwischen dem Microsoft-Edge und dem Skype for Business Online-Rechenzentrum, in dem ein Vermittlungsserver verwendet wird.
    
3. **Verbindung innerhalb des Microsoft-Netzwerks**: Diese Verbindung besteht zwischen dem Skype for Business Online-Rechenzentrum und dem Microsoft-Netzwerk-Edge.
    
4. **Verbindung zwischen dem Microsoft-Netzwerk und den PSTN-Dienstanbieterpartnern**: Über diese Verbindung können PSTN-Anrufe über den Skype for Business-Client getätigt werden, der sich außerhalb des Microsoft-Netzwerks befindet.
    
### Anforderungen an die Netzwerkleistung von einem Skype for Business-Client zum Microsoft-Netzwerk-Edge
<a name="bk_SfBClienttoEdge"> </a>

Für optimale Medienqualität in Skype for Business muss eine Verbindung aus dem Netzwerk Ihres Unternehmens zum Edge des Microsoft-Netzwerks die folgenden Ziel- oder Schwellenwerte für Netzwerk-Leistungsmetriken erreichen. Dieses Segment des Netzwerks umfasst Ihr internes Netzwerk einschließlich aller WLAN- und Ethernet-Verbindungen, den gesamten Datenverkehr zwischen Unternehmensstandorten über eine WAN-Verbindung, zum Beispiel MPLS (Multiprotocol Label Switching), sowie die Internet- oder ExpressRoute-Partnerverbindungen mit dem Microsoft-Netzwerk-Edge.
  
> [!CAUTION]
> **Die Konnektivität zwischen einem Skype for Business-Client in Ihrem Unternehmensnetzwerk und Office 365-Diensten muss die folgenden Anforderungen an die Netzwerkleistung erfüllen und die genannten Schwellenwerte erreichen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |**Ziel** <br/> |
|Latenz (unidirektional)  <br/> |< 50 ms  <br/> |
|Latenz (RTT oder Round-Trip-Zeit)  <br/> |< 100 ms  <br/> |
|Burst-Verlust von Paketen  <br/> |< 10 % in einem Intervall von 200 ms  <br/> |
|Paketverlust  <br/> |< 1% in einem Intervall von 15 Sek.  <br/> |
|Jitter zwischen der Ankunftszeit von Paketen  <br/> |< 30 ms in einem Intervall von 15 Sek.  <br/> |
|Neuanordnung von Paketen  <br/> |< 0,05 % Pakete mit geänderter Reihenfolge  <br/> |
   
 **Weitere Leistungszielanforderungen:**
  
- Das Microsoft-Netzwerk umfasst weltweit über 160 Edge-Standorte. Über diese Edge-Standorte arbeiten wir mit großen Internetdienstanbietern (ISPs) in aller Welt zusammen. Bei dem Metrikzielwert für die Latenz wird angenommen, dass sich die Standorte Ihres Unternehmens und die Microsoft-Edges auf dem gleichen Kontinent befinden.
    
- Die Verbindung zwischen Ihren Unternehmensstandorten und dem Microsoft-Netzwerk-Edge schließt Netzwerkzugriff über den ersten Hop ein, für den ein WLAN oder eine andere Funktechnologie genutzt werden kann. 
    
- Bei dem Zielwert für die Netzwerkleistung wird von einer sorgfältigen Planung der Bandbreite und/oder der Quality of Service ausgegangen. Mit anderen Worten: Dies hat direkte Auswirkungen auf den Echtzeitmedienverkehr in Skype for Business, wenn die Netzwerkverbindung unter Spitzenlast steht.
    
### Anforderungen an die Netzwerkleistung von Ihrem Netzwerk-Edge zum Microsoft-Netzwerk-Edge
<a name="bk_YourNetworkEdge"> </a>

Die Verbindung zwischen Ihrem Netzwerk-Edge und dem Microsoft-Netzwerk-Edge muss die folgenden Ziel- oder Schwellenwerte für die Netzwerkleistung erreichen. Zu diesem Segment des Netzwerks gehört nicht das interne Netzwerk oder WAN des Kunden. Es ist als Leitlinie für Tests Ihres über das Internet oder ein ExpressRoute-Partnernetzwerk gesendeten Netzwerkverkehrs gedacht. Sie können es auch beim Aushandeln einer leistungsbezogenen Vereinbarung zum Servicelevel (SLA) mit Ihrem ExpressRoute-Anbieter nutzen.
  
> [!CAUTION]
> **Die Konnektivität zwischen Ihrem Unternehmensnetzwerk und dem Microsoft-Netzwerk-Edge muss die folgenden Anforderungen an die Netzwerkleistung erfüllen und die genannten Schwellenwerte erreichen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |**Ziel** <br/> |
|Latenz (unidirektional)  <br/> |< 30 ms  <br/> |
|Latenz (RTT)  <br/> |< 60 ms  <br/> |
|Burst-Verlust von Paketen  <br/> |< 1 % in einem Intervall von 200 ms  <br/> |
|Paketverlust  <br/> |< 0,1 % in einem Intervall von 15 Sek.  <br/> |
|Jitter zwischen der Ankunftszeit von Paketen  <br/> |< 15 ms in einem Intervall von 15 Sek.  <br/> |
|Neuanordnung von Paketen  <br/> |< 0,01 % Pakete mit geänderter Reihenfolge  <br/> |
   
 **Weitere Leistungszielanforderungen:**
  
- Der Leistungszielwert setzt eine Verbindung zwischen Netzwerk-Edges Ihres Unternehmens und dem jeweils nächstgelegenen Microsoft-Netzwerk-Edge auf dem gleichen Kontinent voraus.
    
- Bei dem Zielwert für die Netzwerkleistung wird von einer sorgfältigen Planung der Bandbreite und/oder der Quality of Service ausgegangen. Dies gilt auch für den Echtzeitmedienverkehr in Skype for Business, wenn die Netzwerkverbindung unter Spitzenlast steht. Wie Sie die Bandbreite und QoS richtig planen, erfahren Sie unter [ExpressRoute und QoS in Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## Messen der Netzwerkleistung
<a name="bk_NetworkPerf"> </a>

Um die tatsächliche Netzwerkleistung zwischen einem beliebigen Standort im Unternehmensnetzwerk und einem Netzwerk-Edge zu messen, insbesondere im Hinblick auf Latenz und Paketverluste, können Sie Tools wie Ping verwenden. Damit können Sie eine Reihe von Skype for Business-Mediarelay-Diensten testen, die an Microsoft-Edge- und Rechenzentrums-Standorten ausgeführt werden. 
  
Die Internetverbindungen zum Microsoft-Netzwerk sollten Sie anhand der folgenden VIPs der Skype for Business-Mediarelays testen. Die  *Anycast-VIP*  wird in eine IP-Adresse eines Mediarelays an dem Teststandort nächstgelegenen Microsoft-Netzwerk-Edge-Standort aufgelöst.
  
||||
|:-----|:-----|:-----|
|**IP-Adresse** <br/> |**Typ** <br/> |**Ort** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |Weltweite Anycast-IP  <br/> |
   
 **Hier sind ein paar allgemeine Empfehlungen, an denen Sie sich beim Bewerten der Netzwerkleistung orientieren können:**
  
- Bewerten Sie das interne Netzwerk sowie die Verbindungen mit Office 365.
    
- Bewerten und sammeln Sie über einen langen Zeitraum Daten für alle Ihre Netzwerke. Wir empfehlen, die Netzwerkleistung mindestens eine Woche lang zu testen, damit Sie Nutzungsmuster für alle Arbeitstage und -zeiten sehen können. Auf diese Weise werden Spitzenzeiten sichtbar.
    
- Nehmen Sie mehrere Messwert-Stichproben für die Netzwerkleistung. Wir empfehlen, während des gesamten Zeitraums der Datensammlung alle zehn Minuten eine Messung an einem Unternehmensstandort vorzunehmen. Nehmen Sie für den Vergleich der Anforderungen an die Netzwerkleistung für Skype for Business Online das 90. Perzentil der Messwerte aus diesem Stichproben-Dataset. 
    
- Sie sollten die Leistung des Netzwerks kontinuierlich bewerten. Die Netzwerkauslastung schwankt im Lauf der Zeit aufgrund von geänderten Nutzungsmustern, neuen unternehmensbasierten Apps mit hohem Bandbreitenverbrauch sowie Änderungen an organisatorischen oder physischen Unternehmensstandorten. Wichtig ist, dass Sie die Netzwerkleistung kontinuierlich anhand dieser Anforderungen und Ziel-/Schwellenwerte überwachen und zeitnahe Anpassungen vornehmen, um die optimale Qualität von Echtzeitmedien sicherzustellen. 
    
## Messen der Netzwerkleistung mit Azure-VMs
<a name="bk_NetworkPerf"> </a>

Anstelle der Durchführung von Tests an Microsoft-Netzwerk-Edge-Standorten können Sie Netzwerkbewertungslösungen von Skype for Business-Kunden und -Partnern verwenden, die die Einrichtung von Tests für Dienste in der Microsoft Azure-Cloud nutzen. In diesen Lösungen testen die Netzwerkbewertungstools Latenz, Paketverlust und Jitter für Kundenendpunkte, die als Dienst in der Azure-Cloud eingerichtet wurden. Dies führt dazu, dass der Test-Netzwerkdatenverkehr ein zusätzliches Netzwerksegment durchläuft, bei dem es sich um die Verbindung innerhalb des Microsoft-Netzwerks zwischen den Netzwerk-Edges und Azure-Rechenzentren handelt, in dem der Netzwerkbewertungsdienst gehostet wird.
  
Für diese auf gehosteten Azure-Webdiensten basierten Netzwerkbewertungslösungen wird empfohlen, die Netzwerkbewertung innerhalb des jeweiligen Landes bzw. der jeweiligen Region durchzuführen. Für einen Kunden im Osten der USA sollte die Bewertung beispielsweise für eine Testdienstinstanz durchgeführt werden, die im Azure-Rechenzentrum im Osten der USA gehostet wird. 
  
Im Folgenden finden Sie die Latenz (RTT)-Ziele für die auf dem Azure-Dienst basierte Netzwerkbewertungseinrichtung. Die unidirektionalen Ziele bilden die Hälfte der jeweiligen RTT-Ziele. Der Paketverlust und Jitter-Ziele bleiben unverändert und entsprechen denjenigen, die für das auf Mediarelays basierte Testen definiert wurden.
  
|||||
|:-----|:-----|:-----|:-----|
|**Kundenregion** <br/> |**Azure-Region** <br/> |**Ihr Netzwerk-Edge - Azure-Round-Trip-Zeit (Round-Trip Time, RTT)** <br/> |**Ihr Standort - Azure-Round-Trip-Zeit (Round-Trip Time, RTT)** <br/> |
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
   
## Medienqualität und ExpressRoute
<a name="bk_NetworkPerf"> </a>

Azure ExpressRoute für Office 365 ist eine dedizierte Netzwerkverbindung für die Anbindung an Office 365. Dadurch haben Kunden die Kontrolle über den Pfad, den ihr Office 365-Netzwerkdatenverkehr durchläuft. Sie müssen sich nicht mehr mit unvorhersehbarem Routing im Internet befassen, bei dem Daten von unbekannten Netzbetreibern, Anbietern und ISPs übertragen werden. Durch ExpressRoute gesendeter Netzwerkdatenverkehr wird direkt über das Netzwerk des ExpressRoute-Partners an das Netzwerk von Microsoft gesendet. Auf diese Weise können Kunden Office 365 wie eine in ihrem eigenen externen Rechenzentrum installierte Lösung mit einer dedizierten Verbindung behandeln.
  
Azure ExpressRoute ist für alle Office 365-Lizenzangebote verfügbar. Für globales Routing mit Office 365 benötigen Sie jedoch das Azure ExpressRoute Premium-Add-On. Office 365-Kunden mit mindestens 500 Arbeitsplätzen, die ExpressRoute implementieren, erhalten das  *ExpressRoute Premium-Add-On*  kostenlos.
  
### Ist ExpressRoute erforderlich für gute Medienqualität?

Azure ExpressRoute ist keine Voraussetzung für optimale Medienqualität in Skype for Business Online. Es ist vielmehr eine der Bereitstellungsoptionen, mit denen Sie sicherstellen können, dass Ihre Cloudkonnektivität die Ziel- oder Schwellenwerte für die Netzwerkleistung in Skype for Business erreicht.
  
Office 365 ist ein leistungsstarker und sicherer Dienst, der das Internet nutzt. Wir investieren fortlaufend in neue Sicherheitsfunktionen und regionale Edge-Knoten, um die Sicherheit und Leistung zu verbessern. Azure ExpressRoute ist für Office 365-Dienste wie beispielsweise Skype for Business Online nicht erforderlich. Azure ExpressRoute ist eine der verfügbaren Bereitstellungsoptionen, mit der Sie sicherstellen können, dass die Konnektivität mit Office 365 den Anforderungen von Skype for Business an die Netzwerkleistung entspricht. Außerdem wird die optimale Medienqualität in Skype for Business Online sichergestellt.
  
Für die Medienqualität in Skype for Business Online ist es wichtig, dass die Verbindung zwischen Ihren Unternehmensstandorten und den Microsoft-Netzwerk-Edges die Leistungszielwerte unter [Anforderungen an die Netzwerkleistung von einem Skype for Business-Client zum Microsoft-Netzwerk-Edge](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge) und die Verbindung zwischen Ihren Netzwerk-Edges und den Microsoft-Netzwerk-Edges die Leistungszielwerte unter[Anforderungen an die Netzwerkleistung von Ihrem Netzwerk-Edge zum Microsoft-Netzwerk-Edge](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_YourNetworkEdge) erreicht.
  
Wichtig ist außerdem, dass die Konnektivität des physischen Unternehmensnetzwerks einschließlich der Kapazität Ihres internen Netzwerks und der Cloudkonnektivität Spitzenaufkommen bei Mediendaten gewachsen ist. Azure ExpressRoute ist eine von vielen Möglichkeiten, mit denen Kunden sicherstellen können, dass ihre Skype for Business Online-Cloudkonnektivität alle diese Leistungsanforderungen erfüllt.
  
### Ist ExpressRoute erforderlich für SLAs zur Sprachqualität?

Nein, ExpressRoute ist für SLAs zur Sprachqualität in Skype for Business Online Voice nicht erforderlich. Die [SLA zur Sprachqualität in Skype for Business Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) gilt für alle geeigneten Anrufe, die von Nutzern des Sprachdiensts in Skype for Business Online mit den entsprechenden Lizenzen und Abonnements für alle Arten von VoIP- oder PSTN-Anrufen getätigt werden. Eine SLA zur Sprachqualität sollte die folgenden Punkte enthalten:
  
- Anrufe von Microsoft-zertifizierten IP-Telefonen
    
- Kabelgebundene Ethernet-Verbindungen
    
- Probleme mit der Sprachqualität aufgrund von Problemen im Microsoft-Netzwerk
    
> [!NOTE]
> Ausgenommen von der SLA zur Sprachqualität sind alle Anrufe, bei denen die schlechte Anrufqualität durch Probleme in nicht zu Microsoft gehörenden Netzwerken verursacht wird. Dazu gehören Netzwerke von ExpressRoute-Partnern und anderen Anbietern. 
  
### Internet oder Azure ExpressRoute?

Vor der Entscheidung über Netzwerkkonnektivitätsoptionen für Skype for Business Online müssen Kunden ihr Netzwerk und die aktuelle Internetkonnektivität anhand der unter [Anforderungen an die Netzwerkleistung für Verbindungen mit Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_NetworkPerf) beschriebenen Anforderungen an die Netzwerkleistung bewerten.
  
Wenn die Netzwerkleistung über die aktuelle Internetverbindung genug Kapazität zu Spitzenzeiten bietet und den Anforderungen an die Netzwerkleistung von Standorten zu Microsoft-Netzwerk-Edges und von Ihren Netzwerk-Edges zu Microsoft-Netzwerk-Edges entspricht, können Sie die vorhandene Internetkonnektivität auch für Verbindungen mit Skype for Business Online nutzen.
  
Für Unternehmensstandorte, an denen die Anforderungen an die Netzwerkleistung nicht erfüllt werden, empfehlen wir dringend, zunächst gemeinsam mit Ihren vorhandenen Netzwerkdienstanbietern die allgemeine Netzwerkleistung zu verbessern. Wenn die Anforderungen dennoch nicht erfüllt werden, können Sie mit Azure ExpressRoute sicherstellen, dass Ihre Skype for Business Online-Cloudkonnektivität dazu beiträgt, die Anforderungen an die Netzwerkleistung zu erfüllen.
  
Darüber hinaus bietet Azure ExpressRoute die folgenden Vorteile:
  
- Eine Vereinbarung zum Servicelevel (Service Level Agreement, SLA) zur Verfügbarkeit der Verbindung zwischen Ihrem Netzwerk und dem Microsoft-Netzwerk. ExpressRoute hat eine SLA zur garantierten Verfügbarkeit von 99,9 %.
    
- Geplante und garantierte für Office 365-Dienste benötigte Bandbreite. Zu diesem Zweck können Sie nur Office 365- oder Skype for Business-Datenverkehr über ExpressRoute senden und den gesamten sonstigen Internetverkehr über andere Interneteingangs- und -ausgangspunkte Ihres Netzwerks leiten.
    
- ExpressRoute ist dafür gedacht, die DSCP-QoS-Markierungen zwischen Ihrem und dem Microsoft-Netzwerk beizubehalten.
    
Weitere Informationen zu QoS in ExpressRoute und zur Kapazitätsplanung finden Sie unter [ExpressRoute und QoS in Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### Kann ich Azure ExpressRoute nur für Skype for Business Online einrichten?

Ja, Sie können Azure ExpressRoute einrichten, um hervorragende Netzwerkkonnektivität ausschließlich zwischen dem Netzwerk Ihres Unternehmens und Skype for Business Online sicherzustellen. Dadurch erzielen Sie die optimale Qualität von Echtzeitmedien für Ihre Nutzer und können gleichzeitig weiterhin Verbindungen mit anderen Office 365-Diensten über das Internet herstellen.
  
Das BGP (Border Gateway Protocol)-Protokoll ist ein Internet-Routingprotokoll, das zur Weiterleitung von Datenverkehr über das Internet verwendet wird. Das Protokoll ist dafür gedacht, Routinginformationen zwischen anonymen Systemen (AS) über das Internet auszutauschen. BGP-Community-Werte sind Attribut-Tags, die für eingehende oder ausgehende Routen verwendet werden können. BGP-Communities werden häufig verwendet, um dem empfangenden AS zu signalisieren, welcher ausgehende Link zum Erreichen eines vorhandenen Ziels basierend auf Diensttypkriterien, geografischen oder anderen Kriterien verwendet werden sollte.
  
Dank der Unterstützung für BGP-Communitys markiert Microsoft Präfixe und Routen mit entsprechenden BGP-Community-Werten für den zugehörigen Dienst. Microsoft markiert durch öffentliches Peering und Microsoft-Peering angekündigte Präfixe mit entsprechenden BGP-Community-Werten, die die Region angeben, in der die Präfixe gehostet werden. Anhand der Community-Werte können Sie die richtigen Routingentscheidungen treffen, um optimales Routing anzubieten. Sie können den BGP-Community-Wert für Skype for Business Online verwenden, um eine ExpressRoute-Verbindung nur für Skype for Business Online einzurichten. Mehr dazu erfahren Sie unter [ExpressRoute-Routinganforderungen](https://azure.microsoft.com/de-de/documentation/articles/expressroute-routing/).
  
## ExpressRoute-Konnektivitätsszenarien für Skype for Business Online
<a name="bk_NetworkPerf"> </a>

Wenn Sie aufgrund der oben genannten Empfehlungen zu dem Schluss gekommen sind, dass ExpressRoute für Sie geeignet ist, erfahren Sie hier, welche und wie viele ExpressRoute-Verbindungen Sie benötigen.
  
### Reine Onlinebereitstellung - ein Standort

Wenn alle Nutzer den Skype for Business Online-Dienst verwenden, alle Niederlassungen sich an einem einzigen physischen Standort befinden und Sie sich für die Bereitstellung von Azure ExpressRoute entscheiden, sollten Sie eine einzige ExpressRoute-Verbindung zwischen Ihrem Unternehmensstandort und dem nächstgelegenen [ExpressRoute-Peering-Standort](https://azure.microsoft.com/de-de/documentation/articles/expressroute-locations/) einrichten.
  
Die folgende Grafik zeigt ein Beispiel für diesen Bereitstellungstyp. In diesem Beispiel ist Contoso eine Universität in Orlando, Florida. Contoso hat 10.000 Lehrpersonalmitglieder und Studenten. Die Tests für die Internetverbindung von Contosos Standort zu den Microsoft-Edge-Standorten ergaben einen Paketverlust von mehr als 5 % während der Spitzenunterrichtszeiten. Contoso entschied sich für eine dedizierte Verbindung mit Office 365 über ExpressRoute mit überzähliger Bandbreite, um eine Netzwerküberlastung für Office 365, insbesondere durch Echtzeitdatenverkehr in Skype for Business Online, zu vermeiden. Die Verbindung mit der Microsoft-Cloud wird am MeetMe-Standort in Atlanta, Georgia, über ExpressRoute hergestellt.
  
![ExpressRoute Single Site.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### Reine Onlinebereitstellung - mehrere Standorte auf dem gleichen Kontinent

Wenn Ihr Unternehmen Skype for Business Online-Dienste in mehreren Niederlassungen in der gleichen Region oder auf dem gleichen Kontinent nutzt und Sie sich für die Implementierung von Azure ExpressRoute entschieden haben, sollten Sie den Hauptstandort über ExpressRoute verbinden. Dann können Sie optional zusätzliches ExpressRoute-Peering für weitere Standorte hinzufügen, die nicht die empfohlenen Zielwerte für die Netzwerkleistung erreichen.
  
Im folgenden Beispiel ist Contoso ein US-amerikanischer Reisedienstleister mit Hauptsitz in New York und weiteren Niederlassungen an verschiedenen Orten in den USA. Die Niederlassungen sind über ein WAN vernetzt, das über MPLS mit Office 365 verbunden ist. Zunächst hat das Unternehmen eine ExpressRoute-Verbindung von seinem Internetrouter in Hoboken, New Jersey, zu dem MeetMe-Standort in New York hergestellt. 
  
Mit dieser Konfiguration kann der Netzwerkverkehr von den meisten Standorten zum Microsoft-Netzwerk (Edge-Standort in New York) die unter [Anforderungen an die Netzwerkleistung von einem Skype for Business-Client zum Microsoft-Netzwerk-Edge](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge) beschriebenen Zielwerte für die Netzwerkleistung für Verbindungen mit Skype for Business-Clients erreichen. Die Latenz zwischen den Contoso-Niederlassungen an der Westküste und in New York beträgt jedoch mehr als 50 ms (unidirektional). Darüber hinaus überschreitet die Latenz von Honolulu, der zweitgrößten Niederlassung von Contoso, und New York 80 ms (unidirektional). Um eine hohe Medienqualität für die Nutzer in diesen Niederlassungen sicherzustellen, hat Contoso für die Westküste eine ExpressRoute-Verbindung zwischen dem Standort in San Jose und dem ExpressRoute-Standort für MeetMe im Silicon Valley hinzugefügt.
  
![Express Router Multi-site on the same continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### Reine Onlinebereitstellung - mehrere Standorte auf verschiedenen Kontinenten

Wenn alle Nutzer den Skype for Business Online-Dienst verwenden, die Niederlassungen sich an mehreren physischen Standorten auf verschiedenen Kontinenten befinden und Sie sich für die Bereitstellung von Azure ExpressRoute entscheiden, sollten Sie mindestens eine ExpressRoute-Verbindung für jeden Kontinent zwischen dem Hauptstandort auf dem jeweiligen Kontinent und dem nächstgelegenen [ExpressRoute-Peering-Standort](https://azure.microsoft.com/de-de/documentation/articles/expressroute-locations/) einrichten.
  
Im folgenden Beispiel ist Contoso ist eine große Wirtschaftskanzlei mit Niederlassungen in Großstädten in Nordamerika und Europa. Im Hinblick auf die Internetverbindung und die Bewertung der Netzwerkleistung hat Contoso beschlossen, zwei ExpressRoute-Verbindungen in Nordamerika und eine einzelne ExpressRoute-Verbindung für alle europäischen Niederlassungen bereitzustellen.
  
![ExpressRoute with multiple sites and continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### Hybridbereitstellung

Wenn Sie eine lokale Lync- oder Skype for Business-Bereitstellung haben und sich für die Implementierung einer hybriden Skype for Business Online-Integration entscheiden, empfehlen wir bei Bereitstellung von Azure ExpressRoute mindestens eine ExpressRoute-Verbindung für jeden lokalen Lync- oder Skype for Business-Edge-Standort und mindestens eine ExpressRoute-Verbindung für jeden Kontinent mit Niederlassungen. Abhängig vom Kosten-Nutzen-Verhältnis können Sie zusätzliche ExpressRoute-Verbindungen von Niederlassungen bereitstellen, in denen die Zielwerte für die Netzwerkleistung nicht erreicht werden.
  
Wenn Sie eine lokale Skype for Business-Bereitstellung haben, müssen Sie sich an die Anweisungen unter [Planen der Edgeserverbereitstellungen in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/mt346417.aspx) halten. Vor allem müssen die Edgeserver von außerhalb des Netzwerks erreichbar sein. Dazu weisen Sie in der Regel dem Edgeserver eine routbare öffentliche IP-Adresse zu oder verwenden Netzwerkadressenübersetzung (Network Address Translation, NAT).
  
Im folgenden Beispiel verfügt Contoso über eine lokale Skype for Business Enterprise-VoIP-Bereitstellung. Das Unternehmen möchte die lokalen Nutzer zu Office 365-Onlinediensten migrieren. Außerdem hat sich Contoso für eine hybride Bereitstellung entschieden, um die vorhandene PSTN-Infrastruktur für alle lokalen Nutzer und Onlinenutzer zu verwenden. Contosos lokales Rechenzentrum und die Skype for Business-Edgeserver befinden sich in Chicago. Für die Bereitstellung hat Contoso beschlossen, eine ExpressRoute-Verbindung zwischen dem Rechenzentrum in Chicago und der Chicago-ExpressRoute einzurichten. Außerdem hat das Unternehmen eine ExpressRoute-Verbindung für die Westküste hinzugefügt, um die Niederlassung in Honolulu besser anzubinden.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### Onlinebereitstellung mit Cloud Connector Edition

Skype for Business Online Cloud Connector Edition ist ein hybrides Angebot, das aus einem Satz paketierter virtueller Computer (Virtual Machines, VMs) besteht, die eine lokale PSTN-Anbindung implementieren. Durch die Bereitstellung einer minimalen Skype for Business Server-Topologie in einer virtualisierten Umgebung können Sie alle Anrufe über Festnetztelefone und Mobiltelefone über die vorhandene lokale PSTN-Sprachinfrastruktur senden und empfangen.
  
Wenn Sie sich für die Bereitstellung von Azure ExpressRoute und Cloud Connector Edition entscheiden, sollten Sie mindestens eine ExpressRoute-Verbindung für jeden Kontinent zwischen dem Hauptstandort auf dem jeweiligen Kontinent und dem nächstgelegenen [ExpressRoute-Peering-Standort](https://azure.microsoft.com/de-de/documentation/articles/expressroute-locations/) einrichten. Abhängig vom Kosten-Nutzen-Verhältnis können Sie zusätzliche ExpressRoute-Verbindungen von Standorten bereitstellen, an denen die Zielwerte für die Netzwerkleistung nicht erreicht werden.
  
Wenn Sie eine lokale Skype for Business-Bereitstellung haben, müssen Sie sich an die Anweisungen unter [Planen für die Skype for Business Cloud Connector-Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx) halten. Weisen Sie vor allem dem Zugriffs-Edgedienst und dem A/V-Edgedienst öffentliche IP-Adressen zu. Außerdem müssen diese Dienste von den Office 365-Rechenzentren aus erreichbar sein.
  
Im folgenden Beispiel ist Contoso eine europäische Wirtschaftsprüfungsfirma, die in ein paar wichtigen europäischen Ländern und Städten vertreten ist. Contoso hat sich für Skype for Business Online registriert, um die Zusammenarbeit zu verbessern, und beschlossen, in jedem Land mit einem physischen Standort Cloud Connector bereitzustellen. Auf diese Weise sollten die bereits vorhandene PSTN-Infrastruktur und bestehende Verträge mit Netzbetreibern genutzt werden. Contoso hat an allen Standorten und am Microsoft-Netzwerk-Edge Tests durchgeführt und ist zu dem Schluss gekommen, dass mit einer einzigen ExpressRoute-Verbindung in London die unter [Anforderungen an die Netzwerkleistung von einem Skype for Business-Client zum Microsoft-Netzwerk-Edge](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge) beschriebenen Zielwerte für die Netzwerkleistung für Verbindungen mit Skype for Business-Clients erreicht werden können.
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Unten sehen Sie eine weitere Bereitstellungsoption für Contoso. In diesem Fall hat sich das Unternehmen für die Einrichtung einer ExpressRoute-Verbindung an jedem Standort entschieden, an dem Cloud Connector bereitgestellt ist.
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## Siehe auch
<a name="bk_NetworkPerf"> </a>

#### Weitere Ressourcen

[ExpressRoute und QoS in Skype for Business Online](20c654da-30ee-4e4f-a764-8b7d8844431d.md)

