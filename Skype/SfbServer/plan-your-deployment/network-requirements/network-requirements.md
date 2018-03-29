---
title: Planen von Netzwerkanforderungen für Skype for Business 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Zusammenfassung: Prüfen der Überlegungen zum Netzwerk-Komponente unter vor der Implementierung von Skype für Business Server 2015.'
ms.openlocfilehash: 3d3fd2141da93a9b0b866fe44e2ed8dee6942f3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-network-requirements-for-skype-for-business-2015"></a>Planen von Netzwerkanforderungen für Skype for Business 2015
 
**Zusammenfassung:** Überprüfen Sie die Komponente Netzwerkaspekte unter vor der Implementierung von Skype für Business Server 2015.
  
Die Informationen in diesen Themen wird in das Whitepaper [Netzwerkplanung, Überwachung und Problembehandlung von Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) mit weiteren Details und Tiefe ebenfalls diskutiert. Während sich der Inhalt explizit auf Lync 2010 und Lync 2013 bezieht, sind die Kriterien für die Skype für Business Server 2015 unverändert.
  
Dienstanbieter entscheidet auch, wenn Ihr Netzwerk wi-Fi sowie verkabelten Zugriff beinhaltet, im Whitepaper [Bereitstellung von Lync 2013 Real-Time Communications über Wi-Fi](http://www.microsoft.com/en-us/download/details.aspx?id=36494) ist eine gute Verweis und gleichermaßen auf Skype für Business Server 2015.
  
Die Netzwerkleistung und die Anforderungen an das Netzwerk sind direkt mit der Datenverkehrsauslastung verbunden. Bei der Planung Ihrer Implementierung Netzwerk- und es wird empfohlen, die [Skype für Business Server 2015 Planungstool](../../management-tools/planning-tool/planning-tool.md)verwendet die [Skype für Business 2015 Planung Kapazitätsrechner für Server](../../management-tools/capacity-planning-calculator.md)und die [Skype für Business Server 2015 Stress and Performance-Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="server-hardware"></a>Serverhardware
<a name="S_hard"> </a>

Der Netzwerkadapter der einzelnen Server in der Skype für Business Server-Topologie muss mindestens 1 Gigabit pro Sekunde (Gbit/s) unterstützen. Im Allgemeinen sollten Sie alle Serverrollen innerhalb der Skype für Business Server-Topologie mit einem geringer Latenz und hoher Bandbreite lokales Netzwerk (LAN) verbinden. Die Größe des LAN ist von der Größe der Topologie abhängig: 
  
- In Standard Edition-Topologien sollten Server in einem Netzwerk befinden, die 1 Gbit/s Ethernet oder eine vergleichbare unterstützt.
    
- In Enterprise Edition-Topologien sollten sich die meisten Server in einem Netzwerk, die mehr als 1 Gbit/s, unterstützt, insbesondere dann, wenn a/v-Unterstützung (A / V) Konferenzen und Anwendungsfreigabe.
    
Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.
  
## <a name="audiovideo-network-requirements"></a>Netzwerkanforderungen für die Audio/Video-Unterstützung
<a name="AV_req"> </a>

Netzwerkanforderungen für Audio/Video (A / V) in einer Skype für Business Server-Bereitstellung lauten wie folgt:
  
- Wenn Sie einen einzelnen Edgeserver oder ein Edge-Pool mit DNS-Lastenausgleich bereitstellen, können Sie die _externe_ Firewall zum Ausführen der Netzwerkadressübersetzung (NAT) konfigurieren. Sie können keine NAT ausführen, um die _interne_ Firewall konfigurieren. Weitere Informationen hierzu finden Sie unter [Determining Firewall and 50 k Port Range Requirements](http://technet.microsoft.com/library/3b849dc7-175d-40d1-820d-80e6ade6d332.aspx).
    
    > [!IMPORTANT]
    > Wenn Sie einen edgepool haben und ein Hardwaregerät zum Lastenausgleich verwenden, müssen Sie öffentliche IP-Adressen verwenden, auf dem Edge-Servern und können keine NAT für die Server oder Pool an Ihre NAT-fähigen Geräten (beispielsweise eine Firewall Appliance oder LAN wechseln. Weitere Informationen hierzu finden Sie unter [Port-Zusammenfassung – skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich](http://technet.microsoft.com/library/91213b1e-f875-464b-83e8-fe3a351595a4.aspx). 
  
- Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt. 
    
- Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden. Weitere Informationen hierzu finden Sie unter [IPsec-Ausnahmen](http://technet.microsoft.com/library/241f1eca-6f2f-44de-90b1-2cb659cbe27c.aspx).
    
Mit folgenden Maßnahmen können Sie optimale Medienqualität sicherstellen:
  
- Richten Sie die Netzwerkverbindungen zum Durchsatz von 65 Kilobit pro Sekunde (Kbit/s) pro Audiostream und 500 KBit/s pro Videostream, sofern sie, während Spitzenzeiten aktiviert sind unterstützen. Eine bidirektionale Audio- oder videositzung verwendet zwei Datenströme, sodass eine einfache Audio-/Telefonverbindung 130 Kbit/s, um jeden Stream abzudecken erforderlich ist. Video wird ebenso 1000 Kbit/s insgesamt verwenden, um eine Verbindung Upstream- und Downstreamkomponenten auszuführen. 
    
- Um unerwartete Spitzen im Datenverkehr und erhöhte Nutzung über einen Zeitraum zu bewältigen kann Skype für Business Server Media Endpunkte an unterschiedlichen netzwerkbedingungen angepasst und unterstützt drei Mal den Durchsatz für Audio und Video bei gleichzeitiger Wahrung der akzeptable Qualität. Nehmen Sie nicht an, dass diese Flexibilität des Problems maskieren wird, wenn ein Netzwerk unter bereitgestellt wird. In einem Netzwerk unter bereitgestellt wird die Fähigkeit von der Skype für Medien-Endpunkte dynamisch Umgang mit unterschiedlichen netzwerkbedingungen (beispielsweise temporäre hoher Paketverlust) Business Server reduziert.
    
- Für Netzwerkverbindungen, deren Bereitstellung sehr kostspielig und aufwendig ist, können Sie eine Dimensionierung für ein niedrigeres Datenverkehrsaufkommen erwägen. Können Sie in diesem Szenario der Elastizität der der Skype für Business Server Media Endpunkte den Unterschied zwischen der Lautstärke Datenverkehr und der Spitzenzeiten Datenverkehr Ebene, aber einige Verringerung der Sprachqualität kompensieren. Gleichzeitig verringert sich der Puffer, der andernfalls zum Auffangen plötzlicher Datenspitzen zur Verfügung steht.
    
- Bei Verbindungen, die kurzfristig nicht ausreichend dimensioniert werden können (beispielsweise an einem Standort mit sehr schlechten WAN-Verbindungen) kann es ratsam sein, die Videofunktion für bestimmte Benutzer zu deaktivieren.
    
- Stellen Sie bei der Netzwerkbereitstellung sicher, dass bei Spitzenauslastung eine maximale End-to-End-Verzögerung (Latenz) von 150 ms auftritt. Latenz ist eine netzwerkbeeinträchtigung, die Skype für Business Server-Medienkomponenten verringern kann nicht, und es ist wichtig, zu finden und auszuschließen die Schwachpunkte.
    
- Schließen Sie für Server, auf denen Antivirensoftware ausgeführt werden alle Server, die in die Ausnahmeliste ein, um eine optimale Leistung und Audioqualität zu gewährleisten Skype für Business Server ausgeführt werden. 
    
## <a name="conferencing-network-requirements"></a>Netzwerkanforderungen für Konferenzen
<a name="Conf_req"> </a>

Die Bandbreite, die zum Herunterladen von konferenzinhalten vom Server (Internet Information Services, IIS) verwendet, hängt von der Größe des Inhalts. Daher sollten Sie die tatsächliche Nutzung überwachen und gegebenenfalls eine größere Bandbreite in Ihre Planung miteinbeziehen.
  
## <a name="network-bandwidth-requirements-for-media-traffic"></a>Anforderungen hinsichtlich der Netzwerkbandbreite für Mediendatenverkehr
<a name="Conf_req"> </a>

Ein wichtiger Bestandteil von netzwerkplanung müssen Sie sicherstellen, dass Ihr Netzwerk der Mediendatenverkehr von Skype für Business Server generierte verarbeitet werden kann. Dieser Abschnitt hilft Ihnen bei der Planung für diesen Mediendatenverkehr. 
  
### <a name="media-traffic-network-usage"></a>Netzwerkbelegung durch Mediendatenverkehr
<a name="Net_req"> </a>

Aufgrund der Vielzahl an verschiedenen Faktoren, wie z. B. Codecverwendung, Auflösung und Aktivitätsgrad kann es schwierig sein, die Bandbreite für Mediendatenverkehr zu berechnen. Die Bandbreitennutzung wird durch den verwendeten Codec und die Streamaktivität bestimmt und beide Faktoren können in unterschiedlichen Szenarien variieren. Die folgende Tabelle enthält die Audiocodecs in der Regel in Skype für Szenarien mit Business Server verwendet.
  
**Bandbreite für Audiocodec**

|**Audiocodec**|**Szenario**|**Audionutzlast Bitrate (Kbit/s)**|**Bandbreite für audionutzlast und IP-Header (Kbit/s)**|**Bandbreite für audionutzlast, IP-Header, UDP, RTP und SRTP (Kbit/s)**|**Bandbreite für audionutzlast, IP-Header, UDP, RTP, SRTP und vorwärtsfehlerkorrektur (Kbit/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio, Breitband  <br/> |Peer-to-Peer  <br/> |29.0  <br/> |45.0  <br/> |57,0  <br/> |86,0  <br/> |
|RTAudio, Schmalband  <br/> |Peer-to-Peer PSTN  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G. 722  <br/> |Konferenzen  <br/> |64,0  <br/> |80,0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 Stereo  <br/> |Peer-to-Peer Konferenzen  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G. 711  <br/> |PSTN, Konferenzen  <br/> |64,0  <br/> |80,0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Konferenzen  <br/> |16,0  <br/> |32,0  <br/> |47.6  <br/> |63.6  <br/> |
|SILK-Breitband  <br/> |Peer-to-Peer  <br/> |36.0  <br/> |52.0  <br/> |64,0  <br/> |100,0  <br/> |
|SILK-Breitband  <br/> |Peer-to-Peer  <br/> |26.0  <br/> |42.0  <br/> |54,0  <br/> |80,0  <br/> |
|SILK-Breitband  <br/> |Peer-to-Peer  <br/> |20,0  <br/> |36.0  <br/> |: 48,0  <br/> |68.0  <br/> |
|SEIDENBLUMEN Breitband/Schmalband  <br/> |Peer-to-Peer  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54,0  <br/> |
   
Die Bandbreitenangaben in dieser Tabelle basieren auf einer Paketierung mit 20 ms (50 Pakete pro Sekunde), für Siren und G.722, einschließlich SRTP-Overhead (Secure Real-Time Transport Protocol) aus Konferenzszenarien und setzen voraus, dass der Stream zu 100% aktiv ist. Die Vorwärtsfehlerkorrektur (Forward Error Correction, FEC) wird dynamisch eingesetzt, um bei einem Paketverlust in der Verbindung die Qualität des Audiostreams zu erhalten. 
  
Die Stereoversion des G.722-Codec wird von Systemen verwendet, die auf dem Lync-Raumsystem basieren. Auf diese Weise können Mikrofonaufnahmen in Stereoqualität vorgenommen werden, damit Zuhörer die unterschiedlichen Personen im Besprechungsraum besser voneinander unterscheiden können.
  
**Bandbreite für Videoauflösung**

|**Videocodec**|**Auflösung und Seitenverhältnis**|**Maximale video Nutzlast Bitrate (Kbit/s)**|**Minimale video Nutzlast Bitrate (Kbit/s)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9))  <br/> 320x240 (4:3  <br/> |350  <br/> |100  <br/> |
|H. 264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H. 264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H. 264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H. 264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H. 264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H. 264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |
   
Videodaten werden standardmäßig mit H.264/MPEG-4 Advanced Video Coding (Part 10) zusammen mit den entsprechenden skalierbaren Erweiterungen für eine temporäre Skalierbarkeit codiert. Um die Interoperabilität mit Clients von Vorversionen zu verwalten, wird der RTVideo Codec weiterhin für Peer-zu-Peer-Anrufe zwischen Skype für Business Server und Clients von Vorversionen verwendet. In konferenzsitzungen mit beiden Skype für Business Server und Clients von Vorversionen der Skype für Business Server Endpunkt codieren das Video mit beiden video-Codecs und Senden der h. 264-Bit-Stream, der Skype für Business Server-Clients und der RTVideo-Bit-Stream auf legacy Clients.
  
Die erforderliche Bandbreite richtet sich nach der Auflösung, Qualität, Framerate sowie der Menge der im Bild vorhandenen Bewegungen oder Veränderungen. Bei jeder Auflösung sind zwei Bitraten von Interesse:
  
- **Maximum Nutzlast Bitrate** Dies ist die Bitrate, die ein Endpunkt für die Auflösung an die maximale Framerate verwendet wird. Hiermit kann die höchste Video- und Tonqualität erreicht werden.
    
- **Minimum Nutzlast Bitrate** Dies ist die Bitrate Unterschreitung einen Skype für Business Server Endpunkt auf die nächste niedriger Auflösung wechseln. Um eine bestimmte Auflösung zu gewährleisten, darf die verfügbare Videonutzlast-Bitrate nicht unter diese minimale Bitrate für die jeweilige Auflösung absinken. Diese Zahl ist von Interesse, da sie für Fälle, in denen die maximale Bitrate nicht verfügbar oder sinnvoll ist, den geringstmöglichen Wert angibt. Bedenken Sie jedoch bei Verwendung dieser Bitraten, dass für einige Benutzer eine derart niedrige Videoübertragungsrate möglicherweise nicht akzeptabel ist. Beachten Sie, dass die tatsächliche Bitrate bei statischen und sich nicht verändernden Videoszenen ebenfalls kurzfristig unter die minimale Bitrate absinken kann.
    
Skype für Business Server unterstützt viele Lösungen. Dies ermöglicht Skype für Business Server, um verschiedene Netzwerkbandbreite und Empfangen von Clientfunktionen anzupassen. Das standardmäßige Seitenverhältnis Skype für Business Server ist 16:9. Das Seitenverhältnis legacy 4:3 ist weiterhin für Webcams Capture in das Seitenverhältnis 16:9 dürfen nicht unterstützt.
  
Wenn die Vorwärtsfehlerkorrektur eingesetzt wird, ist sie in der Videonutzlast enthalten, daher sind keine unterschiedlichen Werte mit und ohne Video-FEC vorhanden. 
  
Endpunkte übertragen Audio- oder Videopakete nicht in einem kontinuierlichen Stream. Für jedes Szenario gibt es unterschiedliche Aktivitätsebenen, die angeben, wie häufig Pakete für einen Stream gesendet werden. Die Aktivität eines Streams richtet sich nach dem Medium und dem Szenario, nicht jedoch nach dem verwendeten Codec. In einem Peer-to-Peer-Szenario gilt Folgendes: 
  
- Endpunkte senden Audiostreams nur dann, wenn die Benutzer miteinander sprechen.
    
- Beide Teilnehmer empfangen Audiostreams.
    
- Wenn Videodaten übertragen werden, senden und empfangen beide Endpunkte Videostreams während der gesamten Kommunikation.
    
- In statischen Videoszenen kann die tatsächliche Bitrate kurzfristig sehr gering sein, da der Videocodec die Codierung von Bereichen des Videos überspringt, in denen vom Zeitpunkt der letzten Überprüfung an keine Änderungen auftreten.
    
In einem Konferenzszenario gilt Folgendes:
  
- Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.
    
- Alle Teilnehmer empfangen Audiostreams.
    
- Wenn Videodaten übertragen werden, alle Teilnehmer erhalten bis zu fünf empfangen Videostreams und ein (beispielsweise Seitenverhältnis 20:3) panoramavideo-Stream. Standardmäßig die fünf empfangene basieren Videostreams auf Verlauf des aktiven Sprechers, aber die Benutzer können die Teilnehmer aus denen sie einen Videostream empfangen möchten auch manuell auswählen. Video mit mehreren aktiviert ist, wird die Anforderung Auflösung und Bandbreite für jede der Videostreams niedriger sein.
    
- Jeder Teilnehmer, die des Benutzers aktiviert wird Videostream sendet eine oder mehrere Videostreams senden. Skype für Business Server kann bis zu fünf Videostreams senden die Videoqualität für alle empfangenden Clients optimiert. Die tatsächliche Anzahl an gesendeten Videostreams wird vom Sender basierend auf CPU-Leistung, verfügbarer Uplink-Bandbreite und der Anzahl an Empfängerclients, die einen bestimmten Videostream angefordert haben, bestimmt. Üblicherweise wird ein H.264- und ein RTVideo-Stream gesendet, wenn ein Vorversions-Client an der Konferenz teilnimmt. Bei einem anderen typischen Szenario werden mehrere H.264-Videostreams (z. B. mit verschiedenen Auflösungen) gesendet, um verschiedenen Empfängeranforderungen gerecht zu werden. 
    
Zusätzlich zu der Bandbreite, die für den RTP-Datenverkehr (Real-Time Transport Protocol) für Audio- und Videomedien erforderlich ist, wird auch Bandbreite für RTCP-Datenverkehr (Real-Time Transport Control Protocol) benötigt. RTCP wird zum Generieren von Statistiken und zur Out-of-Band-Steuerung des RTP-Streams genutzt. Verwenden Sie zur Planung die Bandbreitenangaben in der folgenden Tabelle für RTCP-Datenverkehr. Diese Werte stellen die maximale Bandbreite für RTCP dar und variieren aufgrund der Unterschiede in den Steuerungsdaten bei Audio- und Videostreams. 
  
**RTCP-Bandbreite**

|**Media**|**Maximale RTCP-Bandbreite (Kbit/s)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Video (es wird nur H.264 oder RTVideo gesendet/empfangen)  <br/> |10  <br/> |
|Video (H.264 und RTVideo werden gesendet/empfangen)  <br/> |15  <br/> |
   
Für die Kapazitätsplanung sind die folgenden beiden Bandbreiten von Interesse:
  
- **Maximale Bandbreite ohne FEC** Die maximale Bandbreite, die ein Datenstrom belegt. Dazu gehören die normale Aktivität des Datenstroms und der typischer Codec, der verwendet wird, im Szenario mit ohne FEC vorhanden. Dies ist die Bandbreite, wenn der Stream auf 100 % Aktivität ist und es sind keine Paketverluste Auslösen der die Verwendung von FEC vorhanden. Dies ist hilfreich für Netzwerke wie viel Bandbreite zugewiesen werden muss, damit den Codec in einem bestimmten Szenario verwendet werden können. FEC wird nicht erwartet, dass eine Anforderung für ein verwaltetes Netzwerk sein.
    
- **Maximale Bandbreite mit FEC** Die maximale Bandbreite, die in ein Stream benötigt. Dazu gehören die normale Aktivität des Datenstroms und der typischer Codec, der verwendet wird, im Szenario mit FEC vorhanden. Dies ist die Bandbreite, wenn der Stream auf 100 % Aktivität ist und die Verwendung von FEC zur Verbesserung der Qualität auslösen Paketverlust vorhanden ist. Dies ist hilfreich für Netzwerke wie viel Bandbreite zugewiesen werden muss, damit den Codec zulassen der Verwendung von FEC Qualität unter Umständen Paketverlust beibehalten und in einem bestimmten Szenario verwendet werden können.
    
In den folgenden Tabellen Listen auch zusätzliche Bandbreite einen Wert für eine **Typische Bandbreite**. Dies ist die durchschnittliche Bandbreite, die in ein Stream benötigt. Dazu gehören die normale Aktivität des Datenstroms und der typischer Codec, der verwendet wird, im Szenario. Diese Bandbreite Annäherung, wie viel Bandbreite durch Mediendatenverkehr zu einem bestimmten Zeitpunkt verbraucht wird verwendet werden kann, jedoch sollte nicht für die kapazitätsplanung verwendet werden, weil einzelne Aufrufe dieser Wert überschritten werden, wenn die Aktivitätsebene durchschnittlich größer ist. Die normale Videostream Bandbreite in den folgenden Tabellen basiert auf eine Mischung aus verschiedenen Auflösung wie gemessene Kundendaten beobachteten und kleinere Installationen sind mit hoher Wahrscheinlichkeit tatsächliche Zahlen haben, die von der Tabellendaten abweichen. Um beispielsweise in Peer-zu-Peer-Sitzungen, die meisten Benutzer das Standard-Video verwenden Rendern Sie Fenster während einige Prozentsatz der Benutzer erhöhen oder der Skype für Business Server-Anwendung maximieren an eine bessere Auflösung zulassen würden.
  
In den folgenden Tabellen finden Sie Werte für verschiedene Szenarien.
  
**A/v-Kapazitätsplanung für Peer-zu-Peer-Sitzungen**

|**Media**|**Codec**|**Typische streambandbreite (Kbit/s)**|**Maximale streambandbreite ohne FEC**|**Maximale streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |RTAudio, Breitband  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |SILK-Breitband  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Hauptvideo beim Aufruf von Skype für Business Server-Endpunkte  <br/> |H. 264  <br/> |460  <br/> |4010 (für eine maximale Auflösung von 1920x1080)  <br/> |Bereits enthalten  <br/> |
|Hauptvideo beim Aufruf von Lync 2010 oder Office Communicator 2007 R2-Endpunkten  <br/> |RTVideo  <br/> |460  <br/> |2510 (für eine maximale Auflösung von 1280x720)  <br/> |Bereits enthalten  <br/> |
|Panoramavideo beim Aufruf von Skype für Business Server-Endpunkte  <br/> |H. 264  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Bereits enthalten  <br/> |
|Panoramavideo beim Aufruf von Lync 2010-Endpunkten  <br/> |RTVideo  <br/> |190  <br/> |510 (für eine maximale Auflösung von 960x144)  <br/> |Bereits enthalten  <br/> |
   
**Audio/Videokapazität für Konferenzen planen**

|**Media**|**Typischer codec**|**Typische streambandbreite (Kbit/s)**|**Maximale streambandbreite ohne FEC**|**Maximale streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25,5  <br/> |52.6  <br/> |68.6  <br/> |
|Hauptvideo, Empfang  <br/> |H.264 und RTVideo¹  <br/> |260  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Hauptvideo, Senden  <br/> |H.264 und RTVideo  <br/> |270  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Empfang  <br/> |H.264 und RTVideo  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Senden  <br/> |H.264 und RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Nicht zutreffend  <br/> |
   
1. RT-Video wird außerdem an h. 264 gesendet, wenn Lync 2010-Clients mit der Konferenz verbunden sind.
  
2. Wenn mehrere Datenströme vorhanden sind, teilen sie dynamisch zugewiesene Bandbreite.
  
Für das Hauptvideo besteht die typische Streambandbreite aus der aggregierten Bandbreite aller empfangenen Videostreams und die maximale Streambandbreite aus der Bandbreite aller gesendeten Videos. Selbst mit mehreren Videostreams ist die typische Videobandbreite kleiner als im Peer-to-Peer-Szenario, da viele Videokonferenzen die Inhaltsfreigabe nutzen, wobei wesentlich kleinere Videofenster und somit auch niedrigere Videoauflösungen verwendet werden. Die maximal unterstützte aggregierte Bandbreite der Videonutzlast liegt bei 8000 KBit/s für das Senden und Empfangen von Streams, die zum Beispiel beim Empfang von zwei Streams mit je 1920x1080 zum Einsatz käme. Maximalwerte werden im Realfall nur selten erreicht.
  
Beim Erstellen von, die Gallery Ansicht verwendet, um einer Konferenz mit mehreren Teilnehmern, bandbreitenauslastung nimmt Anfangs als Teilnehmer beitreten, und nimmt dann Auflösungen abgelegt werden, das Maximum angepasst. 
  
||**2 Teilnehmer**|**3 Teilnehmer**|**4 Teilnehmer**|**5 Teilnehmer**|**6 Teilnehmer**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Maximale Auflösungen empfangen** <br/> |1920 x 1080  <br/> |1280 x 720  <br/> |640 x 360  <br/> |640 x 360 320 x 240  <br/> |640 x 360 320 x 240  <br/> |
|**Durchschnittliche Gesamtbitrate** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Maximale Gesamtbitrate** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |
   
Die typische Streambandbreite für Panoramavideos basiert auf Geräten, die Panoramavideos mit einer Auflösung von 960x144 streamen. Wenn Sie Geräte mit einer Auflösung von 1920x288 verwenden, sollte sich die typische Bandbreite erhöhen. 
  
**Audio Capacity Planning for PSTN**

|**Media**|**Typischer codec**|**Typische streambandbreite (Kbit/s)**|**Maximale streambandbreite ohne FEC**|**Maximale streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (einschließlich PSTN-Teilnehmer in Konferenzen)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |
   
Die Angaben zur Netzwerkbandbreite in diesen Tabellen gelten nur für unidirektionalen Datenverkehr und beinhalten 5 KBit/s für RTCP-Overhead pro Stream. 
  
## <a name="managing-quality-of-service"></a>Verwalten der Dienstqualität (Quality of Service, QoS)
<a name="man_QOS"> </a>

Bei der Dienstqualität (Quality of Service, QoS) handelt es sich um eine Netzwerktechnologie, die in einigen Organisationen zum Bereitstellen einer optimalen Benutzerfreundlichkeit für die Audio- und Videokommunikation verwendet wird. QoS kommt am häufigsten in Netzwerken mit beschränkter Bandbreite zum Einsatz, bei denen eine große Anzahl Netzwerkpakete um eine relativ geringe Bandbreite konkurrieren. Die Dienstqualität bietet Administratoren die Möglichkeit, Pakete mit Audio- oder Videodaten höhere Prioritäten zuzuweisen. Indem diesen Paketen eine höhere Priorität zugewiesen wird, kann die Audio- und Videokommunikation schneller und mit weniger Unterbrechungen ausgeführt werden als Netzwerksitzungen, in denen Dateiübertragungen, Webbrowsen oder Datenbanksicherungen erfolgen. Dies wird dadurch erreicht, dass den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden, eine „Best Effort“-Priorität zugewiesen wird.
  
> [!NOTE]
> In der Regel wird die Dienstqualität nur auf Kommunikationssitzungen innerhalb Ihres internen Netzwerks angewendet. Beim Implementieren von QoS konfigurieren Sie die Server und Router für die Unterstützung der Paketmarkierung auf eine bestimmte Art und Weise, die im Internet oder in anderen Netzwerken im Normalfall nicht unterstützt wird. Selbst wenn die Dienstqualität in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass sie auf dieselbe Art und Weise wie der Dienst in Ihrem Netzwerk konfiguriert ist. Beim Anwenden von MPLS sind Sie an Ihren MPLS-Anbieter gebunden. 
  
Skype für Business Server keine QoS erforderlich, aber es wird dringend empfohlen. Wenn Paket Datenverluste auftreten im Netzwerk auftreten sind Ihrer Lösung mehr Bandbreite hinzufügen oder QoS zu implementieren. Wenn Sie nicht mehr Bandbreite hinzufügen können, ist das Problem nur mit Dienstqualität zu lösen.
  
Skype für Business Server bietet umfassende Unterstützung für QoS:, dass bedeutet, die Organisationen, die bereits QoS verwenden auf einfache Weise können Skype für Business Server in ihrer vorhandenen Infrastruktur integrieren. Zu diesem Zweck müssen Sie diese Schritte ausführen:
  
- [Aktivieren von QoS für nicht-Windows-Geräte](http://technet.microsoft.com/library/26f793df-aef8-4028-9e3b-6c2c37ea61b9.aspx). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Kann zwar Skype für Business Server aktivieren und deaktivieren QoS für Geräte, in der Regel können das Produkt Sie um die DSCP-Codes verwendet, die für diese Geräte zu ändern.
    
- [Konfigurieren von Portbereichen für Konferenz-, Anwendung und Vermittlungsserver](http://technet.microsoft.com/library/4d6eaa5d-0127-453f-be6a-e55384772d83.aspx). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Mithilfe von Skype für Business Server Sie nicht aktivieren oder Deaktivieren von QoS durch Festlegen eines Eigenschaftswerts auf True oder false. Stattdessen wird die Dienstqualität durch die Konfiguration von Portbereichen und die anschließende Erstellung und Anwendung einer Gruppenrichtlinie aktiviert. Wenn Sie später entscheiden, nicht zu QoS verwenden können Sie "QoS deaktivieren" durch die entsprechenden Gruppenrichtlinienobjekte zu entfernen.
    
- [Konfigurieren von Portbereichen für Edgeserver](http://technet.microsoft.com/library/6f0ae442-6624-4e3f-849a-5b9e387fb8cf.aspx). Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die der anderen Server konfigurieren.
    
- [Konfigurieren von Portbereichen für Microsoft Lync-Clients](http://technet.microsoft.com/library/287d5cea-7ada-461c-9b4a-9da2af315e71.aspx). Diese Portbereiche gelten nur für Clientcomputer und stimmen in der Regel nicht mit den auf Ihren Servern konfigurierten Portbereichen überein.
    
- [Konfigurieren einer QoS-Richtlinie für Konferenz-, Anwendung und Vermittlungsserver](http://technet.microsoft.com/library/8adcbbc5-c9f5-476d-ab7f-72e61859cacf.aspx). Mithilfe dieser Richtlinien werden die DSCP-Codes ermittelt, die auf verschiedene Pakettypen angewendet werden.
    
- [Konfigurieren einer QoS-Richtlinie für A / V-Edgeserver](http://technet.microsoft.com/library/119ee1f5-45b9-40ba-98e5-c694dd2fc5c2.aspx). Dies sollte nur für die interne Seite des Edge-Server ausgeführt werden. Dies liegt daran QoS für die Verwendung in Ihrem internen Netzwerk und nicht auf das Internet entwickelt wurde.
    
- [Konfigurieren von Peer-zu-Peer-von QoS-Richtlinien für Clients unter Windows 7 oder Windows 8 ausgeführt werden](http://technet.microsoft.com/library/efff2b98-b3fb-4183-a4f0-329a9105ce2c.aspx). Beachten Sie, dass Skype für Business Server QoS für andere Windows-Betriebssystemen, wie Windows Vista oder Windows XP nicht unterstützt.
    
- [Konfigurieren von Quality of Service auf Microsoft Lync Phone Edition-Geräte](http://technet.microsoft.com/library/a6eb2620-a512-4ab6-bdfd-eb76be43bbfe.aspx). Standardmäßig ist die QoS für Lync Phone Edition-Geräte aktiviert. Sie können jedoch den DSCP-Standardwert ändern, um sicherzustellen, dass für alle Audiopakete in Ihrer Organisation derselbe DSCP-Code verwendet wird.
    
> [!NOTE]
> Wenn Sie Windows Server 2012 oder Windows Server 2012 R2 verwenden möglicherweise Sie Interesse an den neuen Satz von Windows PowerShell-Cmdlets zum Verwalten von QoS auf dieser Plattform verfügbar. Weitere Informationen finden Sie unter [Netzwerk QoS-Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379). 
  
QoS wird in das Whitepaper [Netzwerkplanung, Überwachung und Problembehandlung von Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) mit weiteren Details und Tiefe ebenfalls diskutiert. Während sich der Inhalt explizit auf Lync 2010 und Lync 2013 bezieht, sind die Kriterien für die Skype für Business Server 2015 unverändert.
  
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="man_QOS"> </a>

#### 

[Planen von IPv6 in Skype for Business](ipv6.md)
  
[Lastenausgleich für Anforderungen für Skype für Unternehmen](load-balancing.md)
  
[DNS-Anforderungen für Skype für Business Server 2015](dns.md)
  
[Ports und Protokolle-Anforderungen für Server](ports-and-protocols.md)

