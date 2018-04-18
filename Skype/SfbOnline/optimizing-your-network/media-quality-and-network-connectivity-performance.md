---
title: Medienqualität und Leistung der Netzwerk-Konnektivität
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: In diesem Thema werden die Netzwerk-Performance-Anforderungen für Skype für Business Online Services definiert und wie Sie auswählen können, mit dem Internet oder dem ExpressRoute für die Konnektivität zwischen dem Netzwerk und Skype Business Online Grundlage Ihrer Bewertung des Netzwerks Konnektivität. Wenn Sie zum Bereitstellen von Azure ExpressRoute dedizierte Konnektivität zu Office 365 entschieden haben, enthält dieses Dokument auch Anleitungen zum Planen Ihrer ExpressRoute Verbindungen in verschiedenen Skype für Business Online Bereitstellungsszenarien.
ms.openlocfilehash: a3af3ac55d39089f2fa6146c93a92fcd174a8cb6
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Medienqualität und Konnektivität Leistung des Netzwerks in Skype für Unternehmen Online

In diesem Thema werden die Netzwerk-Performance-Anforderungen für Skype für Business Online Services definiert und wie Sie auswählen können, mit dem Internet oder dem ExpressRoute für die Konnektivität zwischen dem Netzwerk und Skype Business Online Grundlage Ihrer Bewertung des Netzwerks Konnektivität. Wenn Sie zum Bereitstellen von Azure ExpressRoute dedizierte Konnektivität zu Office 365 entschieden haben, enthält dieses Dokument auch Anleitungen zum Planen Ihrer ExpressRoute Verbindungen in verschiedenen Skype für Business Online Bereitstellungsszenarien.
  
Die Qualität von Real-Time-Medien (Audio, Video und Anwendungsfreigabe) Implementation wird durch die Qualität der End-to-End-Netzwerkkonnektivität erheblich beeinträchtigt. Für optimale Medienqualität in Skype for Business Online benötigen Sie eine Verbindung von hoher Qualität zwischen Ihrem Unternehmensnetzwerk und Skype for Business Online. Am besten orientieren Sie sich beim Einrichten der Konnektivität zwischen dem internen Netzwerk und der Cloud an der Kapazität des Netzwerks, damit auch Spitzendatenaufkommen für Skype for Business Online über alle Verbindungen kein Problem darstellen.
  
Azure ExpressRoute ist eine Voraussetzung für Office 365-Dienste einschließlich Skype für Business Online nicht. Azure ExpressRoute ist jedoch eine der Bereitstellung verfügbaren Optionen, die können Sie gewährleisten, dass Konnektivität mit Office 365 die Skype für Business Leistung netzwerkanforderungen erfüllt und dass die optimalen Skype für Business Online-Medien Quality of Experience.
  
> [!TIP]
> Obwohl dieses Thema allgemeine Netzwerkprobleme Leitfaden zur Leistung enthält, ist vollständige Anleitung zur Bewertung Netzwerk außerhalb des Bereichs dieses Dokuments. Besuchen Sie um eine Liste der Skype für Business Online Partner zu suchen, die Sie bei der Netzwerk-leistungsmessungen als Teil einer Bewertung sorgfältig und vollständig Netzwerk unterstützt [Skype für Business Partner Solutions](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Konnektivität netzwerkanforderungen zur Skype für Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Faktoren, die für Business Online Medienqualität Skype auswirken

Es gibt zahlreiche verschiedene Faktoren beeinflussen, Skype für Business Online Real-Time (audio und video sowie Anwendung freigeben) Medienqualität, die die Geräte enthalten, die verwendet werden, die Umgebung und die Netzwerkkonnektivität. 
  
#### <a name="devices"></a>Geräte

In einer Sitzung Real-Time Media haben Media erfassen und Rendern von Geräten, die von allen Teilnehmern wie Headsets und Webcams verwendet werden großen Einfluss auf die gesamte Audio- und Videoqualität. Geräte von niedrigerer Qualität oder Geräte mit falschen Treibern erzeugen Audiomedien mit einer schlechteren allgemeinen Tonqualität sowie Videomedien mit einer schlechteren Bildqualität. Zertifizierte Geräte oder Geräte von hoher Qualität dagegen verbessern Echounterdrückung, Rauschunterdrückung und Videoauflösung und verringern die Latenz.
  
Obwohl zertifizierte Geräte Audio- und Videomedien nicht erforderliche Dialogfeldoptionen, wird das Geräte für Skype für Unternehmen für den optimalen Media-Erlebnis zertifiziert dringend empfohlen. Eine Liste mit allen Skype für Unternehmen zertifizierte Geräte finden Sie unter [Telefone und Geräte für Skype für Unternehmen](https://technet.microsoft.com/en-us/office/dn947482). Verwenden Sie die [Skype für Business Online aufrufen Qualitätsdashboard](../using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard.md), gefunden in **Skype für Business Admin center**, um sicherzustellen, dass die verwendeten Geräte ordnungsgemäß konfiguriert sind, und audio und video Medienqualität zu überwachen.
  
> [!TIP]
> **Ein zertifiziertes Gerät ist erforderlich für den optimalen Skype Business Media Quality wünschen**.
  
Es ist wichtig, denken Sie daran, dass alle Mediengeräte, Skype für Geschäftskunden und Skype für Unternehmensserver über welche fließt Real-Time Media gewisse Latenz einführen. Das Gerät Verarbeitung Wartezeit, zusammen mit Netzwerklatenz, haben großen Einfluss auf und Software die End-to-End-durchschnittliche Wartezeit und der Endbenutzer Erfahrung dazu beitragen.
  
#### <a name="environment"></a>Umgebung

Die Umgebung und das Umfeld, in dem sich Nutzer treffen und Audio- und Videogeräte verwenden, stellen ebenfalls einen wichtigen Faktor für die Audio- und Videoqualität dar. Nutzer, die aus einer lauten Umgebung anrufen, hören gedämpften und undeutlichen Ton mit Echos. Nutzer in einer dunklen oder lichtarmen Umgebung können keine hellen und scharfen Videos erzeugen. In einem Konferenzraum wirkt sich die Position des Mikrofons und des Videogeräts direkt auf die Ton- und Bildqualität für die Teilnehmer aus.
  
Um einem besseren Verständnis des Benutzers Audio- und Videoerlebnis Verwendung der Skype für **Tools**-Geschäfts-app erhalten > **Optionen** > **Audiogerät** oder **Videogerät** , ändern Sie das Gerät verwendet und Anpassen der Einstellungen. Sie können auch die Audioqualität eines Aufrufs suchen, indem Sie auf **Anrufqualität überprüfen**. If they click **Check Call Quality**, they can then report the quality and issues found with the test call.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### <a name="network"></a>Netzwerk

Die Qualität des Mediums in Echtzeit über IP-Netzwerk wird erheblich beeinträchtigt, durch die Qualität der Netzwerkkonnektivität, aber vor allem von der Menge an:
  
- **Wartezeit** Dies ist der Zeitaufwand für das ein IP-Paket von Punkt A nach Punkt B im Netzwerk erhalten. Diese Netzwerk Verteilung Verzögerung ist im Wesentlichen an physischen Abstand zwischen zwei Punkte und der Lichtgeschwindigkeit, einschließlich zusätzlichen Aufwand zwischen den verschiedenen Routern geschaltet gebunden. Wartezeit wird als unidirektionale oder Round-Trip Time (Zeit) gemessen.
    
- **Paketverlust** Dies ist häufig als Prozentsatz der Pakete definiert, die in einem angegebenen Fenster Zeit verloren gegangen sind. Paketverlust wirkt sich direkt auf die Audioqualität – von kleinen, einzelne Pakete mit fast nicht auswirken, Back Bursts von Verlusten, die dazu führen, vollständige audio Cut skalierten dass verloren.
    
- **Kommunikation zwischen Paket hinzukommen jitter oder einfach jitter** Dies ist die durchschnittliche Änderung Verzögerung zwischen aufeinander folgende Pakete. Die meisten modernen VoIP-Software, einschließlich Skype für Unternehmen kann für einige Ebenen von Jitter über Pufferung anpassen. Es ist nur, wenn die Jitter überschreitet die Pufferung, dass ein Teilnehmer die Effekte der Jitter bemerken.
    
> [!NOTE]
>  Pufferung für Jitter erhöht die End-to-End-Wartezeit.
  
Mit viele gleichzeitige Skype für Business Online Real-Time Media-Sitzungen als auch von anderen Office 365-Diensten und anderen Geschäftsanwendungen generierte Netzwerkdatenverkehr, sicherstellen, dass genügend Bandbreite über den gesamten Netzwerkpfad vorhanden ist, verbindet Ihr Netzwerk mit der Skype, for Business-Online-Dienst wichtig ist, zu vermeiden Überlastung des Netzwerks und hervorragende Medien (audio und video sowie Anwendung freigeben) in Echtzeit Medienqualität sicherstellen. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementieren von Quality of Service (QoS) über überlastete Netzwerke

Darüber hinaus wird Überlastung über ein Netzwerk Medienqualität erheblich beeinträchtigen. Damit können Audio- und Videodaten Pakete Reisen im Netzwerk schneller und über andere den Netzwerkdatenverkehr in einem Netzwerk überlastete priorisiert werden soll, kann Quality of Service (QoS) verwendet werden, können Sie eine optimale benutzerfreundlichkeit für Audio-und Videokommunikation bereitzustellen.
  
QoS bietet eine Möglichkeit für Sie Netzwerkpakete höhere Priorität zuweisen, die Übertragung von Audio- oder Videoinhalten Daten. Diese Pakete eine höhere Priorität zuweisen, sind Audio-und Videokommunikation wahrscheinlich schneller und mit weniger Unterbrechung als Netzwerk-Sitzungen, die mit Aufgaben wie das dateiübertragungen, das Web durchsuchen oder datenbanksicherungen über das Netzwerk übertragen. Dies liegt daran Netzwerkpakete wird für dateiübertragungen verwendet oder datenbanksicherungen standardmäßig zugewiesen wurden "best Effort" als eine Priorität und Überlastung des Netzwerks wird nicht als große Wirkung. Wenn Sie nicht die (audio und video sowie Anwendung freigeben) von Medien-Pakete eine höhere Priorität zuweisen und lassen Sie sie auch als "best Effort" zugewiesen, werden sie zusammen mit anderen Netzwerkverkehr zu verarbeitet werden. In Abhängigkeit vom Umfang der Überlastung des Netzwerks erhalten Dies potenziell eine niedrigere insgesamt Audio- und Videoqualität Oberfläche für die Benutzer.
  
Es wird dringend empfohlen, dass Sie QoS in Ihrem Netzwerk, um sicherzustellen, dass die Überlastung des Netzwerks innerhalb des Netzwerks auswirken wird nicht implementieren. Allerdings müssen alle Netzwerke Endpunkte für diese Option, um die maximale auswirken, unterstützen QoS, Bedeutung, die alle Endpunkte QoS-Markierung berücksichtigen müssen und paketpriorisierung. QoS-Markierung und Priorisierung innerhalb des Netzwerks Microsoft Skype für Business Online-Dienste berücksichtigt werden. Datenverkehr, der über eine öffentliche Verbindung wie etwa dem Internet aus Ihrem Firmennetzwerk mit dem Microsoft-Netzwerk weitergeleitet wird beibehalten nicht jedoch QoS Auswahlmöglichkeiten und paketpriorisierung. Private Verbindungen aus dem Netzwerk mit Office 365 mit [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) bieten eine Lösung für die Bereitstellung, die behält QoS Auswahlmöglichkeiten und paketpriorisierung, die wiederum insgesamt erhöht wird, die Audio- und Videoqualität für die Endbenutzer.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Leistung netzwerkanforderungen für die Verbindung Skype für Business Online
<a name="bkNetworkPerf"> </a>

Skype für Real-Time Media Business Grundsätze über viele verschiedene Geräte, Client-apps, Serversoftware und über verschiedene Netzwerke. Die End-to-End-Wartezeit von Real-Time Media ist der gesamte Abfragewartezeit, das für alle Komponenten und Netzwerksegmenten eingeführt wurde. Die Qualität der End-to-End-Verbindung wird durch das Netzwerksegment mit der schlechtesten Qualität bestimmt. Dieses Segment fungiert als Engpässe für den Netzwerkdatenverkehr.
  
Das folgende Diagramm veranschaulicht die unidirektionale audio-Flusses in einer Konferenz aus einem Skype für Business Teilnehmer zu einer anderen.
  
![ExpressRoute Anruffluss.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In diesem Szenario Conferencing besteht aus der Medienpfad in der folgenden Netzwerksegmenten:
  
1. **Verbindung von Benutzer 1 zum Rand des Microsoft network** Dazu gehören in der Regel eine Netzwerkverbindung wie WiFi oder Ethernet, die WAN-Verbindung von Benutzer 1 zum Internet Austritt (Ihr Netzwerk-Edge-Gerät) und den Internetzugang Ihres Netzwerks Edge zu Microsoft-Netzwerk Edge.
    
2. **Verbindung innerhalb von Microsoft-Netzwerk** Dies ist zwischen der Microsoft Edge zu Skype für Business Online-Rechenzentrum, in dem der A / V-Konferenzserver verwendet werden.
    
3. **Verbindung innerhalb von Microsoft-Netzwerk** Dies ist zwischen den Skype für Business Online-Rechenzentrum und Microsoft Network Edge.
    
4. **Verbindung von Microsoft Netzwerkgrenze an Benutzer 2** Dazu gehören die Internet-Verbindung aus dem Netzwerk Edge zu Microsoft-Netzwerk Edge, die WAN-Verbindung von Benutzer 2 zum Internet Austritt (in Ihrem Netzwerk Edge), und das Netzwerk wie ein WLAN oder Ethernet.
    
Das folgende Diagramm zeigt die Aufschlüsselung der Komponenten und Netzwerksegmente der einen Skype für Business Online PSTN-Anruf:
  
![ExpressRoute PSTN-Betreibers Anruffluss.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In einem Szenario mit PSTN Anruf schneidet Medienpfad die folgenden Netzwerksegmente:
  
1. **Verbindung von einer Skype für Business Client des Anrufers an den Rand des Microsoft Network** Dazu gehören in der Regel eine Netzwerkverbindung wie WiFi oder Ethernet, die WAN-Verbindung zwischen der Skype für Business Client Anrufer und Internet Austritt (Ihr Netzwerk-Edge-Gerät) und den Internetzugang Ihres Netzwerks Edge zu Microsoft-Netzwerk Edge.
    
2. **Verbindung innerhalb von Microsoft-Netzwerk** Dies ist zwischen der Microsoft Edge zu Skype für Business Online-Rechenzentrum, in einen Vermittlungsserver verwendet wird.
    
3. **Verbindung innerhalb von Microsoft-Netzwerk** Dies ist zwischen den Skype für Business Online-Rechenzentrum und Microsoft Network Edge.
    
4. **Verbindung zwischen Microsoft-Netzwerk und die PSTN-Service-Partner** Dies ist die Verbindung, die zum Platzieren eines PSTN-Anrufs aus der Skype für Business-Clients, die sich außerhalb der Microsoft-Netzwerk vorhanden ist.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Netzwerk-leistungsanforderungen aus einer Skype für Business-Client zu Microsoft-Netzwerk Edge
<a name="bkSfBClienttoEdge"></a>

Für eine optimale Skype für Business Medienqualität sind die folgenden Netzwerk Metriken Leistungsziele oder Schwellenwerte für eine Verbindung mit dem Microsoft-Netzwerk Edge aus Ihrem Firmennetzwerk erforderlich. Dieses Segment des Netzwerks umfasst das interne Netzwerk, einschließlich aller Wi-Fi und Ethernet-Verbindungen, Firma Standort-zu-Standort-Datenverkehr über eine WAN-Verbindung, beispielsweise Multiprotocol Label wechseln (MPLS) als auch der Internet- oder ExpressRoute partner Verbindungen mit dem Microsoft-Netzwerk Edge.
  
> [!CAUTION]
> **Verbindung zwischen einer Skype für Business-Client auf Ihrem Unternehmensnetzwerk zu Office 365-Diensten muss diese in der folgenden netzwerkanforderungen Leistung und Schwellenwerte erfüllen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |**Ziel** <br/> |
|Wartezeit (unidirektional)  <br/> |< 50 ms  <br/> |
|Wartezeit (Zeit oder Roundtripzeit)  <br/> |< 100 ms  <br/> |
|Bursts von Paketverlusten  <br/> |< 10 % in einem Intervall von 200 ms  <br/> |
|Paketverlust  <br/> |< 1% in einem Intervall von 15 s  <br/> |
|Die Kommunikation zwischen hinzukommen Jitter Paket  <br/> |< 30 ms in einem Intervall von 15 s  <br/> |
|Paket neu anordnen  <br/> |< 0,05 % Pakete in falscher Reihenfolge  <br/> |
   
 **Andere leistungsanforderungen Ziel:**
  
- Microsoft Network hat mehr als 160 Edge-Standorte weltweit. Wir arbeiten mit großen Internetdienstanbietern (ISP) weltweit über die Edge-Websites. Das Ziel des Vorgangs Wartezeit metrischen geht davon aus der Website Ihres Unternehmens oder Websites und die Microsoft Edges sind auf dem gleichen Kontinent.
    
- Ihr Unternehmen Website oder Websites mit dem Microsoft-Netzwerk Edge Verbindung enthalten ersten Hop Netzwerkzugriff, WiFi oder einer anderen drahtlosen Technologie werden kann. 
    
- Das Netzwerk Leistungsziel wird davon ausgegangen erforderlichen Bandbreite und/oder Qualität der Service-Planung. Dies gilt mit anderen Worten, direkt an Skype für Unternehmen in Echtzeit Mediendatenverkehr, wenn die Netzwerkschnittstelle unter einer spitzenauslastung befindet.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Netzwerk-leistungsanforderungen aus dem Netzwerk Edge zu Microsoft-Netzwerk Edge
<a name="bkYourNetworkEdge"> </a>

Im folgenden werden die Leistungsziele Netzwerk oder Schwellenwerte, die für die Verbindung zwischen dem Netzwerk Edge und Microsoft Network Edge erforderlich sind. Dieses Segment des Netzwerks schließt das interne Kundennetzwerk oder WAN und dient als Leitfaden beim Testen des Netzwerkverkehrs, der über das Internet oder über ein ExpressRoute Partner-Netzwerk gesendet und können auch verwendet werden, wenn eine Leistung aushandeln Service Level Agreement (SLA) mit Ihrem Anbieter ExpressRoute.
  
> [!CAUTION]
> **Konnektivität zwischen Ihrem Firmennetzwerk Edge am Rand der Microsoft-Netzwerk muss diese in der folgenden netzwerkanforderungen Leistung und Schwellenwerte erfüllen.**
  
|||
|:-----|:-----|
|**Metrik** <br/> |**Ziel** <br/> |
|Wartezeit (unidirektional)  <br/> |< 30 ms  <br/> |
|Wartezeit (Zeit)  <br/> |< 60 ms  <br/> |
|Bursts von Paketverlusten  <br/> |< 1% in einem Intervall von 200 ms  <br/> |
|Paketverlust  <br/> |< 0,1% in einem Intervall von 15 s  <br/> |
|Die Kommunikation zwischen hinzukommen Jitter Paket  <br/> |< 15 ms in einem Intervall von 15 s  <br/> |
|Paket neu anordnen  <br/> |< 0,01% Pakete in falscher Reihenfolge  <br/> |
   
 **Andere leistungsanforderungen Ziel:**
  
- Das Leistungsziel erfordert Verbindung zwischen eines Netzwerk Ihres Unternehmens Edge und seiner nächsten Microsoft Network Edgeserver, auf dem gleichen Kontinent sein.
    
- Das Netzwerk Leistungsziel wird davon ausgegangen erforderlichen Bandbreite und/oder Qualität der Service-Planung. Dies gilt auch für Skype für Unternehmen in Echtzeit Mediendatenverkehr bei einer spitzenauslastung die Netzwerkschnittstelle ist. Für die ordnungsgemäße Bandbreite und QoS-Planung Näheres [ExpressRoute und QoS in Skype für Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Messen der Leistung des Netzwerks
<a name="bkNetworkPerf"> </a>

Die tatsächliche netzwerkleistung, insbesondere für Wartezeit und Paketverlust beliebigen Unternehmen Network-Website mit einem Netzwerk Edge, gemessen, können Sie Tools wie Ping verwenden, anhand einer Reihe von Skype für Business Media Relay-Dienste der Microsoft Edge und Daten verlaufende testen Center-Websites. 
  
Für das internetverbindungen mit dem Microsoft-Netzwerk testen, empfiehlt es sich, dass Sie mit der folgenden VIP-Adresse des der Skype für Business Media Relays testen. Die *Anycast VIP* wird in ein Mediarelay in einem Microsoft Edge Netzwerkstandort IP-Adresse aufgelöst, die zum Testen Speicherort am nächsten ist.
  
||||
|:-----|:-----|:-----|
|**IP-Adresse** <br/> |**Typ** <br/> |**Standort** <br/> |
|13.107.8.2  <br/> |VIP-ADRESSE  <br/> |World Wide Anycast IP  <br/> |
   
 **Hier sind einige auf hoher Ebenen Empfehlungen für die Bewertung der Leistung des Netzwerks folgen:**
  
- Sie sollten das interne Netzwerk als auch die Verbindungen mit Office 365 bewerten.
    
- Sie sollten bewerten und Sammeln von Daten für alle Ihre Netzwerke über einen längeren Zeitraum. Es wird empfohlen, für die Sie zum Testen Ihrer des netzwerkleistung für mindestens eine Woche, damit Sie für alle Business Tage und Stunden Verwendungsmuster sehen können. Hieraus sehen Sie Spitzenzeiten.
    
- Ergreifen Sie mehrere Beispiele für leistungsmessungen Netzwerk ein. Es wird empfohlen, eine Maßeinheit 10 Minuten aus einer Unternehmens-Website nutzen, während des gesamten Zeitraums Sie Daten erfasst werden. Übernehmen Sie für den Vergleich der Skype für Business Online Netzwerk leistungsanforderungen, die Messung der 90 Prozentwert aus dieser Beispieldaten. 
    
- Bewerten Sie fortlaufend Leistung im Netzwerk. Netzwerklast variiert über die Zeit aufgrund von Usage Muster ändert, neue Enterprise-basierte Anwendungen, die eine große Menge an Bandbreite verwenden und Änderungen an Organisations- oder physischen Unternehmensstandorten. Es ist wichtig, ständig überwachen die Leistung Ihres Netzwerks gegen diese netzwerkanforderungen für Leistung und Ziele-Schwellenwerte und rechtzeitige ändern Sie den optimalen in Echtzeit Medienqualität sicherstellen. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Messen der Leistung des Netzwerks mit virtuellen Azure-Computern
<a name="bkNetworkPerf"> </a>

Anstelle von Tests mit den Microsoft-Netzwerk-Edge-Websites, sind es Netzwerk Assessment-Lösungen von Skype für Business-Kunden und Partnern, die testing Setup für in der Microsoft Azure-Cloud-Dienste nutzen. In diesen Lösungen die Netzwerk-Bewertungstools Wartezeit, Paketverlust testen und jitter gegen benutzerdefinierte Endpunkte in der Azure-Cloud als Dienst einrichten. Daher der Test-Netzwerkverkehr durchläuft eine zusätzliche Netzwerksegment, das die Verbindung innerhalb des Netzwerks Microsoft zwischen den Rändern Netzwerk ist und Azure Rechenzentren, die als Host den Bewertung Netzwerkdienst.
  
Für diese Netzwerk gehostet Assessment Lösungen auf Grundlage von Azure testen Webdiensten. Es wird empfohlen, das Netzwerk Assessment in Land und/oder Region durchführen. Beispielsweise sollte für Kundenstandorten in East US-Rufnummern, die Bewertung gegen eine testing Dienstinstanz in Azure des East US Center Datenbereich gehostet ausgeführt werden. 
  
Im folgenden sind die Wartezeit (Zeit) Ziele für die Netzwerkkonfiguration Assessment Azure-basierten Dienst. Die unidirektionale Wartezeit Ziele werden die Hälfte der entsprechenden Zeit Ziele. Die Paket-Datenverlust und Jitter Ziele bleibt identisch definierten Skype Mediarelay testen basierend.
  
|||||
|:-----|:-----|:-----|:-----|
|**Der region** <br/> |**Azure region** <br/> |**Ihr Netzwerk Edge - Azure Round-Trip Time (Zeit)** <br/> |**Ihre Website - Azure Roundtripzeit (Zeit)** <br/> |
|Zentrale US  <br/> |Zentrale US  <br/> |99  <br/> |139  <br/> |
|Ostasiatische US  <br/> |Ostasiatische US  <br/> |86  <br/> |126  <br/> |
|Zentrale US North  <br/> |Zentrale US North  <br/> |97  <br/> |137  <br/> |
|South zentralen USA  <br/> |South zentralen USA  <br/> |94  <br/> |134  <br/> |
|West, USA  <br/> |West, USA  <br/> |94  <br/> |134  <br/> |
|Hawaii US  <br/> |West, USA  <br/> |116  <br/> |156  <br/> |
|Kanada Central  <br/> |Kanada Central  <br/> |138  <br/> |178  <br/> |
|Canada-East  <br/> |Canada-East  <br/> |131  <br/> |171  <br/> |
|Nordamerika Europa  <br/> |Nordamerika Europa  <br/> |99  <br/> |139  <br/> |
|West Europa  <br/> |West Europa  <br/> |95  <br/> |135  <br/> |
|Ostasien  <br/> |Ostasien  <br/> |118  <br/> |158  <br/> |
|Südosten Asien  <br/> |Südosten Asien  <br/> |97  <br/> |137  <br/> |
|Japan East  <br/> |Japan East  <br/> |111  <br/> |151  <br/> |
|Japan West  <br/> |Japan West  <br/> |118  <br/> |158  <br/> |
|Brasilien Süd  <br/> |Brasilien Süd  <br/> |70  <br/> |110  <br/> |
|Australien East  <br/> |Australien East  <br/> |124  <br/> |164  <br/> |
|Australien Südost  <br/> |Australien Südost  <br/> |124  <br/> |164  <br/> |
|Zentrale Indien  <br/> |Zentrale Indien  <br/> |103  <br/> |143  <br/> |
|South Indien  <br/> |South Indien  <br/> |103  <br/> |143  <br/> |
|West Indien  <br/> |West Indien  <br/> |103  <br/> |143  <br/> |
|China East  <br/> |China East  <br/> |120  <br/> |160  <br/> |
|China North  <br/> |China North  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Medienqualität und ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute für Office 365 ist eine dedizierte Netzwerkschnittstelle für die Verbindung mit Office 365. Es bietet Kunden die Möglichkeit, Kontrolle über den Pfad ihrer Office 365 Netzwerkdatenverkehr akzeptiert. Sie haben nicht mehr betreffenden mit dem unvorhersehbare routing, die im Internet passiert, in dem Daten von unbekannten Netzbetreibern, Anbieter und Internetdienstanbieter durchgeführt werden. Netzwerkdatenverkehr, die über ExpressRoute gesendet wird, wird direkt über die ExpressRoute beim Partner Network an Microsoft Netzwerk gesendet. Dadurch können Kunden zu Office 365 behandelt, als ob es in ihren eigenen Offsite-Rechenzentrum mit einer dedizierten Verbindung befindet.
  
Azure ExpressRoute ist für alle Lizenzierung Office 365-Dienstangebote verfügbar. Jedoch ist der Azure ExpressRoute Premium Add-on für Office 365 So aktivieren Sie globale routing erforderlich. Office 365-Kunden mit mindestens 500 Arbeitsplätze, die ExpressRoute implementieren können die erforderlichen *ExpressRoute Premium Add-on* ohne Zusatzkosten abrufen.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>Ist die ExpressRoute für eine gute Medienqualität erforderlich?

Azure ExpressRoute ist eine Voraussetzung für das Abrufen der optimalen Skype für Business Online Medienqualität nicht. Es ist jedoch, eine der Bereitstellung Optionen, mit denen Sie stellen Sie sicher, dass Ihre Cloud-Diensten die Skype für Business Netzwerk Leistungsziele oder Schwellenwerte erfüllt.
  
Office 365 ist eine hohe Leistung und sichere Dienst, der im Internet verwendet wird. Wir weiter investieren in neue Sicherheitsfunktionen und regionale edgeknoten kontinuierlich verbessern von Sicherheit und Leistung. Azure ExpressRoute ist eine Voraussetzung für Office 365-Dienste einschließlich Skype für Business Online nicht. Azure ExpressRoute ist eine der Bereitstellung verfügbaren Optionen, die können Sie gewährleisten, dass Konnektivität mit Office 365 die Skype für Business Leistung netzwerkanforderungen erfüllt und dass die optimalen Skype für Business Online Medienqualität auftreten.
  
Skype für Business Online Medienqualität ist es wichtig, dass die Verbindung zwischen den Standorten Unternehmen und die Microsoft-Netzwerk Kanten in [Netzwerk-Performance-Anforderungen aus einer Skype für Business-Client zu Microsoft-Netzwerk die Leistungsziele erfüllt Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) und dass die Verbindung zwischen Ihrer Netzwerk Ränder und die Ränder der Microsoft-Netzwerk die Leistungsziele im [Netzwerk leistungsanforderungen aus dem Netzwerk Edge zu Microsoft-Netzwerk Edge](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)erfüllt.  
  
Es ist außerdem wichtig, dass physische Netzwerkkonnektivität Ihres Unternehmens, einschließlich Ihrer interne Netzwerk- und Cloud-Diensten Kapazität Spitzenzeiten Media Datenvolumen aufzunehmen. Azure ExpressRoute ist auf verschiedene Weise, mit dem Kunden, stellen Sie sicher, dass ihre Skype für Online Business Cloud-Diensten alle diese leistungsanforderungen erfüllt.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>Ist die ExpressRoute für VoIP Qualität SLA erforderlich?

Nein, ExpressRoute für Skype für Business Online VoIP Qualität SLA erforderlich. Die [Skype für Business Online VoIP Qualität SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) gilt für alle zu auswählbaren Anruf platziert, indem Skype für Business Online VoIP-Service-Benutzer in die richtige Lizenz und das Abonnement, mit dem dieser Benutzer jede Art von VoIP oder PSTN-Anruf zu tätigen. Alle der folgenden Bedingungen adressiert sind, sollte eine VoIP-Qualität Vereinbarung zum SERVICELEVEL enthalten:
  
- Anrufe von Microsoft certified IP-Telefone.
    
- Verkabelten Ethernet-Verbindungen.
    
- Sprachqualität aufgrund von Problemen mit Microsoft Network.
    
> [!NOTE]
> Die VoIP-Qualität SLA schließt diese Anrufe, in dem die niedrigen Anrufqualität durch Probleme in nicht-Microsoft-Netzwerke einschließlich ExpressRoute Partner und anderen Netzwerken verursacht wird. 
  
### <a name="internet-or-azure-expressroute"></a>Internet oder Azure ExpressRoute?

Bevor Sie eine Entscheidung Netzwerk Konnektivitätsoptionen zu Skype für Business Online, müssen Kunden ihr Netzwerk und Ihre aktuelle Internetkonnektivität basierend auf die Netzwerk-leistungsanforderungen in [Leistung netzwerkanforderungen zur beschriebenen bewerten. Verbinden mit Skype für Online Business](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Wenn die Leistung des Netzwerks über den aktuellen Internetzugang festgelegt ist bei ausreichende Kapazität während der Spitzenzeiten und, die es die Netzwerk-leistungsanforderungen von Websites an Microsoft Network Ränder und Ihr Netzwerk Kanten an Microsoft Network Ränder erfüllt, können Sie weiterhin die vorhandene Verbindung zum Internet Verbindung zu Skype für Business Online verwenden.
  
Unternehmens-Websites, in dem Netzwerk leistungsanforderungen nicht erfüllt wird ist, wird dringend empfohlen, dass Sie Ihre vorhandenen Netzwerk-Dienstanbieter zur Verbesserung der Leistung Ihres gesamten Netzwerks zuerst entwickelt. Jedoch, wenn sie noch nicht erfüllt wird ist, kann mit Azure ExpressRoute sicherzustellen, dass die Ihrer Skype für Online Business Cloud-Diensten die Netzwerk-Performance-Anforderungen erfüllen erleichtern.
  
Azure ExpressRoute bietet die folgenden zusätzlichen Vorteile:
  
- Eine Vereinbarung zum Servicelevel (SLA) auf die Verfügbarkeit der Verbindung zwischen dem Netzwerk und die Microsoft-Netzwerk. ExpressRoute hat eine garantierter SLA Verfügbarkeit von 99,9 %.
    
- Geplante und garantierter Bandbreite für Office 365-Dienste. Sie können dies durch Senden von nur Datenverkehr von Office 365 oder Skype für Business-Datenverkehr von der ExpressRoute erreichen und dann alle anderen Internet Datenverkehr durch die anderen Internet Ausgang/eingehende Punkte für Ihr Netzwerk wechseln.
    
- ExpressRoute ist entwickelt, um QoS-DSCP Auswahlmöglichkeiten zwischen Ihrem Netzwerk und Microsoft Network beizubehalten.
    
Weitere Informationen zur kapazitätsplanung und ExpressRoute QoS Näheres [ExpressRoute und QoS in Skype für Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Kann ich nur Online Business für Azure ExpressRoute für Skype einrichten?

Ja, können Sie Azure ExpressRoute einrichten, um sicherzustellen, dass hervorragende Netzwerkkonnektivität zwischen Ihrem Firmennetzwerk und nur Skype für Business Online. Dies stellt den optimalen in Echtzeit Medienqualität für Ihre Benutzer bereit, aber Sie können dann fortfahren, eine Verbindung mit anderen Office 365-Diensten über das Internet.
  
Border Gateway Protocol (BGP) ist ein routing-Protokoll im Internet, die zum Weiterleiten des Netzwerkverkehrs über das Internet verwendet wird. Es dient zum Austauschen von routing-Informationen zwischen autonomen Systemen (AS) über das Internet gefunden. BGP Communitys Werte sind Attribut-Tags, die eingehende oder ausgehende Routen zugewiesen werden können. BGP Communitys werden häufig verwendet, um den Empfang als welche ausgehende Link zu verwenden, um ein bestimmtes Ziel basierend auf Geografie, Diensttyp oder anderen Kriterien erreichen darauf hinzuweisen.
  
Mit der Unterstützung von Communitys BGP wird Microsoft markieren Präfixe und Routen durch die entsprechenden BGP Community Werte basierend auf den Dienst, dem sie angehören. Microsoft wird über öffentliche peering angekündigt Präfixe markieren und Microsoft peering durch die entsprechenden BGP Community-Werte, der angibt, der Region, in die Präfixe gehostet werden. Sie können auf die Werte der Community entsprechenden Routingentscheidungen optimale routing anbieten verlassen. Sie können die Skype für Business Online BGP Community Wert zum Einrichten einer Verbindung ExpressRoute nur für Skype für Business Online verwenden. Sie können unter [ExpressRoute Routinganforderungen](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/)finden.
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>ExpressRoute Connectivity Szenarien für die Skype für Business Online
<a name="bkNetworkPerf"> </a>

Wenn Sie entschieden haben, dass ExpressRoute basierend auf den oben genannten Empfehlungen für Sie ist, folgen Sie den Empfehlungen, wo und wie viele ExpressRoute Verbindungen sollten Sie erhalten.
  
### <a name="online-only-deployment---single-site"></a>Online nur Bereitstellung – einzelne Website

Wenn alle Benutzer der Skype für Business Online-Dienst verwenden und um einen einzelnen physischen Standort des Büros zentriert sind und Sie Azure ExpressRoute bereitstellen möchten, sollten Sie einzelne ExpressRoute-Verbindung zwischen der Website Ihres Unternehmens, die am nächsten einrichten [ExpressRoute Peers Speicherort](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
Die folgende Grafik zeigt ein Beispiel für diese Art der Bereitstellung. In diesem Beispiel kann Contoso eine befindet sich im Orlando, Florida Universität Contoso hat 10.000 Fakultät Elemente und Studenten. Die Tests Internet aus ihrem Standort Microsoft Edge Websites ergab größer als 5 % Paketverlusten während der Spitzenzeiten-Klasse. Die haben sich entschlossen, erhalten eine dedizierte Verbindung zu Office 365 mit ExpressRoute mit zu viel bereitgestellten Bandbreite, damit sie die netzwerküberlastung für Office 365 vor allem für Skype für Business Online Real-Time-Datenverkehr umgehen können. Sie werden mit der Microsoft-Cloud über ExpressRoute am Standort Atlanta, GA MeetMe.
  
![ExpressRoute einzelner Standorte.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Online nur Bereitstellung – mehrere Websites auf dem gleichen Kontinent

Wenn Ihr Unternehmen Skype für mehrere Büros in derselben Region oder Kontinent Business Online-Diensten, und Sie zum Implementieren von Azure ExpressRoute ausgewählt haben, wird empfohlen, die Hauptwebsite über ExpressRoute verbinden, und fügen Sie dann optional zusätzliche ExpressRoute peering für andere Standorte, die nicht die empfohlene Netzwerk Leistungsziele entsprechen.
  
Im folgenden Beispiel kann Contoso ein US Geschäftsreisen Services Unternehmen, die in New York Hauptsitz ist aber verfügt über andere Büros in den USA. Ihre Büros sind verbundener über ein WAN, die MPLS verwendet, um eine Verbindung mit Office 365. Sie zunächst eine ExpressRoute Verbindung von ihrer Internet-Router in Hoboken, New Jersey so eingerichtet New York MeetMe-Website. 
  
Mit dieser Konfiguration kann Netzwerkverkehr von den meisten ihre Websites zu Microsoft Network (New York-Edge-Website) die Skype für Business Client Verbindung Netzwerk Leistungsziele in [Netzwerk leistungsanforderungen aus einer Skype für Business-Client beschrieben erfüllen. an Microsoft network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Jedoch ist und Wartezeit zwischen Contoso Süd Büros von New York über 50 ms unidirektionale sollte. Darüber hinaus Honolulu ist der zweite größten Office für Contoso, Latenz Honolulu von New York 80ms unidirektionale überschreitet. Contoso möchte, eine gute Medienqualität für Benutzer in diesen Büros sicherstellen, eine Süd ExpressRoute Verbindung zwischen ihren San Jose und der Silicon Valley ExpressRoute MeetMe Website hinzufügen.
  
![Express mit mehreren Standorten Router auf dem gleichen Kontinent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Online nur Bereitstellung – mehrere Websites auf verschiedenen Kontinenten

Wenn alle Benutzer für die Business-Onlinedienst Skype verwenden und Ihre Büros an mehreren physischen Standorten über mehrere Kontinente sind, wenn Sie Azure ExpressRoute bereitstellen möchten, sollten Sie mindestens eine ExpressRoute Verbindung für jeden Kontinent festlegen. zwischen jeden Kontinent Hauptwebsite an den nächstgelegenen [ExpressRoute Peers Speicherort](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). Je nach Kosten Vs nutzen können Sie zusätzliche ExpressRoute Verbindungen von Websites bereitstellen, auf dem Netzwerk Leistungsziele nicht erfüllt ist.
  
Im folgenden Beispiel kann Contoso eine große Unternehmen Anwaltskanzlei mit Sitz in größere Städte in Nordamerika und Europa. Basierend auf ihren Internetzugang und ihre internen Netzwerk-Performance-Bewertung, entschieden Contoso zum Bereitstellen von zwei ExpressRoute Verbindungen in Nordamerika und einer einzelnen ExpressRoute Netzfrequenz für alle ihre Europäischen Büros.
  
![ExpressRoute mit mehreren Standorten und Kontinenten.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Hybridbereitstellung

Wenn Sie eine lokale Lync haben oder Skype für die Bereitstellung von Business, und wählen Sie zum Implementieren einer hybrides Skype für Business Online-Integration, es wird empfohlen, wenn Sie Azure ExpressRoute bereitstellen möchten, Sie mindestens eine ExpressRoute-Verbindung für die einzelnen haben müssen lokale Lync oder Skype für Business Edge-Website und mindestens eine ExpressRoute Verbindung für jeden Kontinent mit Büros. Je nach Kosten Vs nutzen für jeden Kontinent können Sie zusätzliche ExpressRoute Verbindungen von Büros bereitstellen, auf dem Netzwerk Leistungsziele erfüllt wird ist.
  
Wenn Sie eine lokale Skype für die Business-Bereitstellung haben, müssen Sie die [Edge Server Planning and Deployment Guide](https://technet.microsoft.com/en-us/library/mt346417.aspx)befolgen. Insbesondere müssen die Edge-Server von außerhalb des Netzwerks erreichbar sein. Dies geschieht in der Regel der Edge-Server eine routingfähige öffentliche IP-Adresse zuweisen oder Netzwerkadressübersetzung (NAT).
  
Im folgenden Beispiel hat Contoso einer vorhandenen lokalen Skype für Business Enterprise Voice-Bereitstellung. Migrieren von lokalen Benutzern zu Office 365-Onlinediensten möchten. Sie möchte eine hybridbereitstellung verwenden, damit sie weiterhin die vorhandene PSTN-Infrastruktur für alle lokalen und online-Benutzer verwenden können. Contoso lokalen Rechenzentrum und Skype für Business Edge-Server befinden sich in Chicago. Contoso möchte für ihre Bereitstellung eine Verbindung zwischen Chicago im Rechenzentrum und die Chicago ExpressRoute als ExpressRoute einrichten. Aufgenommen auch eine Süd ExpressRoute Verbindung mit ihrer Office Honolulu besser zu verarbeiten.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Online-Bereitstellung mit Cloud Connector Edition

Skype für Business Online Cloud Connector Edition ist eine hybride anbietet, der eine Reihe von gepackte virtuellen Computern (VMs) besteht, die lokalen PSTN-Anbindung zu implementieren. Durch eine minimale Skype für Business Server-Topologie in einer virtualisierten Umgebung bereitstellen, können Sie senden und Empfangen von Anrufen mit Landlines und Mobiltelefone über die vorhandenen lokalen PSTN-VoIP-Infrastruktur.
  
Wenn Sie beschließen, Azure ExpressRoute und Cloud Connector Edition bereitstellen, wird empfohlen, mindestens eine Route Express-Verbindung für jeden Kontinent zwischen jeden Kontinent Hauptwebsite an den nächstgelegenen [ExpressRoute Peers Speicherort](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)einrichten. Je nach Kosten Vs nutzen für jeden Kontinent können Sie zusätzliche ExpressRoute Verbindungen von Websites bereitstellen, auf dem Netzwerk Leistungsziele erfüllt wird ist.
  
Wenn Sie eine lokale Skype für die Business-Bereitstellung haben, müssen Sie im [Planungshandbuch für Skype für Business Cloud Connector Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx)ausführen. Insbesondere der Zugriffs-Edgeserver und A / V-edgedienste öffentliche IP-Adressen zugewiesen werden soll und von Office 365-Rechenzentren erreichbar.
  
Im folgenden Beispiel wird "Contoso" Europäischen Buchhaltung Firma mit Anwesenheitsinformationen in einige wichtige Ländern und Städte. Wenn sie für Skype für Business Online für die Zusammenarbeit benötigen anmelden, entschieden sie Platzieren einer Cloud-Connector für jedes Land, die sie einen physischen Standort besitzen weiterhin ihre PSTN-Infrastruktur verwenden und Netzbetreiber Verträge, die bereits vorhanden. Basierend auf ihren Tests aus allen Websites und Microsoft Network Edge, bestimmt sie, dass eine einzelne Verbindung ExpressRoute in London unterstützen die Skype für Business Client Verbindung Netzwerk Leistungsziele in [Netzwerkleistung beschriebenen erfüllen Anforderungen aus einer Skype für Business-Client an Microsoft network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![ExpressRoute Cloud-Connector ein.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Es folgt eine andere Option für die Bereitstellung für Contoso. In diesem Fall möchte diese eine Verbindung ExpressRoute an jedem Standort einrichten, wo ein Cloud-Connector bereitgestellt wird. 
  
![Zwei ExpressRoute Cloud-Connector.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>See Also

[ExpressRoute und QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 