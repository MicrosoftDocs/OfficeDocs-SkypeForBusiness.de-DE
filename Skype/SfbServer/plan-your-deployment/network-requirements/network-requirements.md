---
title: Plan network requirements for Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Zusammenfassung: Überprüfen Sie die folgenden Überlegungen zur Netzwerkkomponente, bevor Sie Skype for Business Server implementieren.'
ms.openlocfilehash: b7b9c7e239aab5d395fcdadf0cb254df4e13cecd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802025"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Plan network requirements for Skype for Business

**Zusammenfassung:** Überprüfen Sie die folgenden Überlegungen zur Netzwerkkomponente, bevor Sie Skype for Business Server implementieren.

Die Informationen in diesen Themen werden auch im Whitepaper [Netzwerkplanung,-Überwachung und-Problembehandlung mit lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) mit zusätzlichen Details und Tiefe erläutert. Während sich der Inhalt explizit auf lync 2010 und lync 2013 bezieht, sind die Überlegungen für Skype for Business Server unverändert.

Wenn Ihr Netzwerk sowohl WLAN als auch kabelgebundenen Zugriff umfasst, ist das Whitepaper, das [lync 2013-Echtzeitkommunikation über Wi-Fi bereit](https://www.microsoft.com/en-us/download/details.aspx?id=36494) stellt, eine gute Referenz und gilt auch für Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Serverhardware
<a name="S_hard"> </a>

Der Netzwerkadapter jedes Servers in der Skype for Business Server-Topologie muss mindestens 1 Gigabit pro Sekunde (Gbit/s) unterstützen. Im Allgemeinen sollten Sie alle Serverrollen innerhalb der Skype for Business Server-Topologie mithilfe einer geringen Latenz und einem lokalen Netzwerk mit großer Bandbreite verbinden. Die Größe des LAN ist von der Größe der Topologie abhängig:

- In Standard Edition-Topologien sollten sich die Server in einem Netzwerk befinden, das 1 Gbit/s Ethernet oder eine Entsprechung unterstützt.

- In Enterprise Edition-Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 Gbit/s unterstützt, insbesondere bei der Unterstützung von Audio/Video-Konferenzen (a/V) und Anwendungsfreigabe.

Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.

## <a name="audiovideo-network-requirements"></a>Netzwerkanforderungen für die Audio/Video-Unterstützung
<a name="AV_req"> </a>

Zu den Netzwerkanforderungen für Audio/Video (a/V) in einer Skype for Business Server-Bereitstellung gehören die folgenden:

- Wenn Sie einen einzelnen Edgeserver oder einen Edge-Pool mithilfe des DNS-Lastenausgleichs bereitstellen, können Sie die _externe_ Firewall so konfigurieren, dass die Netzwerkadressübersetzung (Network Address Translation, NAT) ausgeführt wird. Die _internal_-Firewall unterstützt keine Konfiguration mit NAT. Ausführliche Informationen finden Sie unter [Planung von Ports und Firewalls](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Wenn Sie über einen Edge-Pool verfügen und ein Hardware-Lastenausgleichsmodul verwenden, müssen Sie öffentliche IP-Adressen auf den Edge-Servern verwenden, und Sie können NAT nicht für die Server oder den Pool an Ihrem NAT-fähigen Gerät verwenden (beispielsweise eine Firewall-Appliance oder einen LAN-Switch. Ausführliche Informationen finden Sie unter [Edge-Server Szenarien in Skype for Business Server](../edge-server-deployments/scenarios.md).

- Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.

- Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden. Ausführliche Informationen finden Sie unter [IPsec-Ausnahmen](#ipsec-exceptions).

Mit folgenden Maßnahmen können Sie optimale Medienqualität sicherstellen:

- Stellen Sie die Netzwerk Links bereit, um den Durchsatz von 65 Kbit/s pro Audio-Stream und 500 KBit/s pro Videostream zu unterstützen, wenn diese während der Spitzenauslastungszeiten aktiviert sind. Eine bidirektionale Audio-oder Videositzung verwendet zwei Streams, sodass eine einfache Audio-130Kbps-Verbindung erforderlich ist, um jeden Datenstrom abzudecken. Video wird ebenfalls 1000 KBit/s insgesamt verwenden, um eine Upstream-und Downstream-Verbindung zu führen.

- Um unerwartete Auslastungsspitzen und eine erhöhte Nutzung im Laufe der Zeit zu bewältigen, können sich Skype for Business Server Media-Endpunkte an unterschiedliche Netzwerkbedingungen anpassen und den dreifachen Durchsatz für Audio-und Videodaten unterstützen, während Sie dennoch akzeptable Qualität erhalten. Gehen Sie nicht davon aus, dass diese Anpassungsfähigkeit das Problem verdeckt, wenn ein Netzwerk unter bereitgestellt wird. In einem unter bereitgestellten Netzwerk wird die Möglichkeit, dass die Skype for Business Server-Medien Endpunkte dynamisch mit unterschiedlichen Netzwerkbedingungen (beispielsweise temporärer hoher Paketverlust) umgehen können, verringert.

- Für Netzwerkverbindungen, deren Bereitstellung sehr kostspielig und aufwendig ist, können Sie eine Dimensionierung für ein niedrigeres Datenverkehrsaufkommen erwägen. Lassen Sie in diesem Szenario die Elastizität der Medien Endpunkte von Skype for Business Server die Unterschiede zwischen dem Verkehrsaufkommen und dem Höchstwert für den Datenverkehr absorbieren, und zwar zu den Kosten für eine gewisse Verringerung der Sprachqualität. Gleichzeitig verringert sich der Puffer, der andernfalls zum Auffangen plötzlicher Datenspitzen zur Verfügung steht.

- Bei Verbindungen, die kurzfristig nicht ausreichend dimensioniert werden können (beispielsweise an einem Standort mit sehr schlechten WAN-Verbindungen) kann es ratsam sein, die Videofunktion für bestimmte Benutzer zu deaktivieren.

- Stellen Sie bei der Netzwerkbereitstellung sicher, dass bei Spitzenauslastung eine maximale End-to-End-Verzögerung (Latenz) von 150 ms auftritt. Latenz ist die einzige Netzwerk Beeinträchtigung, die Skype for Business Server-Medienkomponenten nicht reduzieren können, und es ist wichtig, die Schwachstellen zu finden und zu eliminieren.

- Berücksichtigen Sie bei Servern, die Antivirensoftware ausführen, alle Server, die Skype for Business Server ausführen, in der Ausnahmeliste, um eine optimale Leistung und Audioqualität zu gewährleisten.

## <a name="ipsec-exceptions"></a>IPSec-Ausnahmen

Für Unternehmensnetzwerke, in denen IPSec (Internet Protocol Security) (siehe IETF-RFC 4301-4309) bereitgestellt wurde, muss IPsec über den Portbereich deaktiviert werden, der für die Bereitstellung von Audio-, Video-und Panorama Video verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.

In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.

**Empfohlene IPsec-Ausnahmen**

|Regelname |Quell-IP |Ziel-IP |Protokoll |Quellport |Zielport |Authentifizierungsanforderung |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V-Edgeserver, intern eingehend|Beliebig  |A/V-Edgeserver, intern|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|A/V-Edgeserver, extern eingehend|Beliebig  |A/V-Edgeserver, extern|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|A/V-Edgeserver, intern ausgehend|A/V-Edgeserver, intern  |A/V-Edgeserver, extern |UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|A/V-Edgeserver, extern ausgehend|A/V-Edgeserver, extern |Beliebig |UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Vermittlungsserver, eingehend|Beliebig  |Vermittlungs Server |UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Vermittlungsserver, ausgehend|Vermittlungs Server  |Beliebig|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Konferenzzentrale, eingehend|Beliebig  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird |UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Konferenzzentrale (ausgehend)|Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |Beliebig|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|A/V-Konferenzserver, eingehend|Beliebig|Front-End-Server|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|A/V-Konferenzen, ausgehend|Front-End-Server|Beliebig|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Exchange, eingehend|Beliebig|Exchange Unified Messaging|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Anwendungsfreigabeserver, eingehend|Beliebig|Anwendungsfreigabeserver|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Anwendungsfreigabeserver, ausgehend|Anwendungsfreigabeserver| Beliebig |UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Exchange, ausgehend|Exchange Unified Messaging|Beliebig|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|Clients| Beliebig  |Beliebig|UDP und TCP|Beliebig  |Beliebig |Nicht authentifizieren|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Netzwerkanforderungen für Konferenzen
<a name="Conf_req"> </a>

Die Bandbreite, die zum Herunterladen von Konferenz Inhalten vom IIS-Server (Internet Information Services) verwendet wird, hängt von der Größe des Inhalts ab. Daher sollten Sie die tatsächliche Nutzung überwachen und gegebenenfalls eine größere Bandbreite in Ihre Planung miteinbeziehen.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Anforderungen hinsichtlich der Netzwerkbandbreite für Mediendatenverkehr
<a name="Conf_req"> </a>

Ein wichtiger Bestandteil der Netzwerkplanung besteht darin, sicherzustellen, dass Ihr Netzwerk den von Skype for Business Server generierten Medien Verkehr verarbeiten kann. Dieser Abschnitt hilft Ihnen bei der Planung für diesen Mediendatenverkehr.

### <a name="media-traffic-network-usage"></a>Netzwerkbelegung durch Mediendatenverkehr
<a name="Net_req"> </a>

Aufgrund der Vielzahl an verschiedenen Faktoren, wie z. B. Codecverwendung, Auflösung und Aktivitätsgrad kann es schwierig sein, die Bandbreite für Mediendatenverkehr zu berechnen. Die Bandbreitennutzung wird durch den verwendeten Codec und die Streamaktivität bestimmt und beide Faktoren können in unterschiedlichen Szenarien variieren. In der folgenden Tabelle sind die Audiocodecs aufgeführt, die in Skype for Business Server-Szenarien typischerweise verwendet werden.

**Bandbreite für Audiocodec**

|**Audiocodec**|**Szenario**|**Bitrate der Audionutzlast (KBit/s)**|**Bandbreite für Audionutzlast und IP-Header (KBit/s)**|**Bandbreite für Audionutzlast, IP-Header, UDP, RTP und SRTP (KBit/s)**|**Bandbreite für Audionutzlast, IP-Header, UDP, RTP, SRTP und Vorwärtsfehlerkorrektur (KBit/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio, Breitband  <br/> |Peer-to-Peer  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|RTAudio, Schmalband  <br/> |Peer-to-Peer PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Konferenzen  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 Stereo  <br/> |Peer-to-Peer Konferenzen  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN, Konferenzen  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Konferenzen  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|SILK-Breitband  <br/> |Peer-to-Peer  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|SILK-Breitband  <br/> |Peer-to-Peer  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|SILK-Breitband  <br/> |Peer-to-Peer  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|Seiden Breitband/Schmalband  <br/> |Peer-to-Peer  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> Für PSTN-Anrufe über den Skype for Business-Client wird normalerweise der G. 711-Codec verwendet, der eine große Bandbreite erfordert. Wenn für diesen Codec nicht genügend Bandbreite zur Verfügung steht, können Aufrufe mit einem Fehler auftreten, der in den Medien Protokollen wie folgt aussieht: **mindestens ein Codec muss aktiviert sein, HR: c0042004**. Medienprotokolle (Blogdateien) sind verschlüsselt und können nur vom Microsoft-Supportpersonal decodiert werden.

Die Bandbreitenangaben in dieser Tabelle basieren auf einer Paketierung mit 20 ms (50 Pakete pro Sekunde), für Siren und G.722, einschließlich SRTP-Overhead (Secure Real-Time Transport Protocol) aus Konferenzszenarien und setzen voraus, dass der Stream zu 100% aktiv ist. Die Vorwärtsfehlerkorrektur (Forward Error Correction, FEC) wird dynamisch eingesetzt, um bei einem Paketverlust in der Verbindung die Qualität des Audiostreams zu erhalten.

Die Stereoversion des G.722-Codec wird von Systemen verwendet, die auf dem Lync-Raumsystem basieren. Auf diese Weise können Mikrofonaufnahmen in Stereoqualität vorgenommen werden, damit Zuhörer die unterschiedlichen Personen im Besprechungsraum besser voneinander unterscheiden können.

**Bandbreite für Videoauflösung**

|**Videocodec**|**Auflösung und Seitenverhältnis**|**Bitrate bei maximaler Videonutzlast (KBit/s)**|**Bitrate bei minimaler Videonutzlast (KBit/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320X240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H.264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Videodaten werden standardmäßig mit H.264/MPEG-4 Advanced Video Coding (Part 10) zusammen mit den entsprechenden skalierbaren Erweiterungen für eine temporäre Skalierbarkeit codiert. Um die Interoperabilität mit Legacy-Clients aufrechtzuerhalten, wird der RTVideo-Codec weiterhin für Peer-to-Peer-Anrufe zwischen Skype for Business-Servern und Legacy-Clients verwendet. In Konferenzsitzungen mit Skype for Business Server-und Legacy-Clients kann der Skype for Business Server-Endpunkt das Video mit beiden Video-Codecs kodieren und die H. 264-Bitstreams an die Skype for Business Server-Clients und die RTVideo Bitstream an Legacy senden. Clients.

Die erforderliche Bandbreite richtet sich nach der Auflösung, Qualität, Framerate sowie der Menge der im Bild vorhandenen Bewegungen oder Veränderungen. Bei jeder Auflösung sind zwei Bitraten von Interesse:

- **Maximale Nutzlast-Bitrate** Hierbei handelt es sich um die Bitrate, die von einem Endpunkt für die Auflösung mit der maximalen Bildwiederholrate verwendet wird. Hiermit kann die höchste Video- und Tonqualität erreicht werden.

- **Minimale Nutzlast-Bitrate** Hierbei handelt es sich um die Bitrate, unter der ein Skype for Business Server-Endpunkt auf die nächst niedrigere Auflösung umgeschaltet wird. Um eine bestimmte Auflösung zu gewährleisten, darf die verfügbare Videonutzlast-Bitrate nicht unter diese minimale Bitrate für die jeweilige Auflösung absinken. Diese Zahl ist von Interesse, da sie für Fälle, in denen die maximale Bitrate nicht verfügbar oder sinnvoll ist, den geringstmöglichen Wert angibt. Bedenken Sie jedoch bei Verwendung dieser Bitraten, dass für einige Benutzer eine derart niedrige Videoübertragungsrate möglicherweise nicht akzeptabel ist. Beachten Sie, dass die tatsächliche Bitrate bei statischen und sich nicht verändernden Videoszenen ebenfalls kurzfristig unter die minimale Bitrate absinken kann.

Skype for Business Server unterstützt viele Lösungen. Dadurch kann sich Skype for Business Server an unterschiedliche Netzwerkbandbreiten anpassen und Clientfunktionen empfangen. Das standardmäßige Seitenverhältnis für Skype for Business Server ist 16:9. Das Legacy-4:3-Seitenverhältnis wird weiterhin für Webcams unterstützt, bei denen die Aufnahme im 16:9-Seitenverhältnis nicht zulässig ist.

Wenn die Vorwärtsfehlerkorrektur eingesetzt wird, ist sie in der Videonutzlast enthalten, daher sind keine unterschiedlichen Werte mit und ohne Video-FEC vorhanden.

Endpunkte übertragen Audio- oder Videopakete nicht in einem kontinuierlichen Stream. Für jedes Szenario gibt es unterschiedliche Aktivitätsebenen, die angeben, wie häufig Pakete für einen Stream gesendet werden. Die Aktivität eines Streams richtet sich nach dem Medium und dem Szenario, nicht jedoch nach dem verwendeten Codec. In einem Peer-to-Peer-Szenario gilt Folgendes:

- Endpunkte senden Audiostreams nur dann, wenn die Benutzer miteinander sprechen.

- Beide Teilnehmer empfangen Audiostreams.

- Wenn Videodaten übertragen werden, senden und empfangen beide Endpunkte Videostreams während der gesamten Kommunikation.

- In statischen Videoszenen kann die tatsächliche Bitrate kurzfristig sehr gering sein, da der Videocodec die Codierung von Bereichen des Videos überspringt, in denen vom Zeitpunkt der letzten Überprüfung an keine Änderungen auftreten.

In einem Konferenzszenario gilt Folgendes:

- Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.

- Alle Teilnehmer empfangen Audiostreams.

- Wenn Video verwendet wird, können alle Teilnehmer bis zu fünf Video-Streams empfangen und einen Panorama-Videostream (beispielsweise Seitenverhältnis 20:3) empfangen. Standardmäßig basieren die fünf empfangenen Videostreams auf dem aktiven Sprecher Verlauf, aber Benutzer können auch die Teilnehmer, aus denen Sie einen Videostream empfangen möchten, manuell auswählen. Wenn Multi-Video aktiviert ist, sind die Anforderungen für die Auflösung und die Bandbreite für jeden Videostream niedriger.

- Jeder Teilnehmer, der den senden-Videostream des Benutzers aktiviert, sendet einen oder mehrere Videostreams. Skype for Business Server bietet die Möglichkeit, bis zu fünf Videodatenströme zu senden, um die Videoqualität für alle empfangenden Clients zu optimieren. Die tatsächliche Anzahl an gesendeten Videostreams wird vom Sender basierend auf CPU-Leistung, verfügbarer Uplink-Bandbreite und der Anzahl an Empfängerclients, die einen bestimmten Videostream angefordert haben, bestimmt. Üblicherweise wird ein H.264- und ein RTVideo-Stream gesendet, wenn ein Vorversions-Client an der Konferenz teilnimmt. Bei einem anderen typischen Szenario werden mehrere H.264-Videostreams (z. B. mit verschiedenen Auflösungen) gesendet, um verschiedenen Empfängeranforderungen gerecht zu werden.

Zusätzlich zu der Bandbreite, die für den RTP-Datenverkehr (Real-Time Transport Protocol) für Audio- und Videomedien erforderlich ist, wird auch Bandbreite für RTCP-Datenverkehr (Real-Time Transport Control Protocol) benötigt. RTCP wird zum Generieren von Statistiken und zur Out-of-Band-Steuerung des RTP-Streams genutzt. Verwenden Sie zur Planung die Bandbreitenangaben in der folgenden Tabelle für RTCP-Datenverkehr. Diese Werte stellen die maximale Bandbreite für RTCP dar und variieren aufgrund der Unterschiede in den Steuerungsdaten bei Audio- und Videostreams.

**RTCP-Bandbreite**

|**Medien**|**Maximale RTCP-Bandbreite (KBit/s)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Video (es wird nur H.264 oder RTVideo gesendet/empfangen)  <br/> |10  <br/> |
|Video (H.264 und RTVideo werden gesendet/empfangen)  <br/> |15  <br/> |

Für die Kapazitätsplanung sind die folgenden beiden Bandbreiten von Interesse:

- **Maximale Bandbreite ohne FEC** Die maximale Bandbreite, die ein Datenstrom verbraucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der im Szenario ohne FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, wenn sich der Datenstrom bei einer Aktivität von 100% befindet und kein Paketverlust die Verwendung von FEC auslöst. Dies ist nützlich, um zu berechnen, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann. FEC erwartet in einem verwalteten Netzwerk keine Voraussetzungen.

- **Maximale Bandbreite mit FEC** Die maximale Bandbreite, die ein Datenstrom beansprucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der im Szenario mit FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, wenn sich der Datenstrom bei einer Aktivität von 100% befindet und ein Paketverlust die Verwendung von FEC zur Verbesserung der Qualität auslöst. Dies ist nützlich, um zu berechnen, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann, und die Verwendung von FEC zur Beibehaltung der Qualität unter Paketverlust Bedingungen zu ermöglichen.

In den folgenden Tabellen wird auch ein zusätzlicher Bandbreitenwert, **typische Bandbreite**, aufgeführt. Dies ist die durchschnittliche Bandbreite, die ein Datenstrom verbraucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der im Szenario verwendet wird. Diese Bandbreite kann verwendet werden, um zu ermitteln, wie viel Bandbreite vom Mediendatenverkehr zu einem bestimmten Zeitpunkt verbraucht wird, sollte aber nicht für die Kapazitätsplanung verwendet werden, da einzelne Anrufe diesen Wert überschreiten, wenn die Aktivitätsstufe größer als der Durchschnitt ist. Die typische Videostream-Bandbreite in den folgenden Tabellen basiert auf einer Kombination verschiedener Videoauflösungen, wie Sie in gemessenen Kundendaten zu beobachten sind, und kleinere Installationen haben wahrscheinlich tatsächliche Zahlen, die sich von den Tabellendaten unterscheiden. In Peer-zu-Peer-Sitzungen würden die meisten Benutzer beispielsweise das standardmäßige videowiedergabefenster verwenden, während einige Prozent der Benutzer die Skype for Business Server-Anwendung erhöhen oder maximieren, um bessere Videoauflösungen zu ermöglichen.

In den folgenden Tabellen finden Sie Werte für verschiedene Szenarien.

**Planen der Audio/Videokapazität für Peer-to-Peer-Sitzungen**

|**Medien**|**Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |RTAudio, Breitband  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |SILK-Breitband  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Hauptvideo beim Anrufen von Skype for Business Server-Endpunkten  <br/> |H.264  <br/> |460  <br/> |4010 (für eine maximale Auflösung von 1920x1080)  <br/> |Bereits enthalten  <br/> |
|Hauptvideo beim Aufrufen von lync 2010-oder Office Communicator 2007 R2-Endpunkten  <br/> |RTVideo  <br/> |460  <br/> |2510 (für eine maximale Auflösung von 1280x720)  <br/> |Bereits enthalten  <br/> |
|Panorama Video beim Anrufen von Skype for Business Server-Endpunkten  <br/> |H.264  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Bereits enthalten  <br/> |
|Panorama Video beim Aufrufen von lync 2010-Endpunkten  <br/> |RTVideo  <br/> |190  <br/> |510 (für eine maximale Auflösung von 960x144)  <br/> |Bereits enthalten  <br/> |

**Planen der Audio-/Videokapazität für Konferenzen**

|**Medien**|**Typischer Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Hauptvideo, Empfang  <br/> |H.264 und RTVideo¹  <br/> |260  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Hauptvideo, Senden  <br/> |H.264 und RTVideo  <br/> |270  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Empfang  <br/> |H.264 und RTVideo  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Senden  <br/> |H.264 und RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Nicht zutreffend  <br/> |

1. RT-Video wird zusätzlich zu H. 264 gesendet, wenn lync 2010-Clients mit der Konferenz verbunden sind.

2. Wenn mehrere Streams vorhanden sind, geben Sie die zugewiesene Bandbreite dynamisch frei.

Für das Hauptvideo besteht die typische Streambandbreite aus der aggregierten Bandbreite aller empfangenen Videostreams und die maximale Streambandbreite aus der Bandbreite aller gesendeten Videos. Selbst mit mehreren Videostreams ist die typische Videobandbreite kleiner als im Peer-to-Peer-Szenario, da viele Videokonferenzen die Inhaltsfreigabe nutzen, wobei wesentlich kleinere Videofenster und somit auch niedrigere Videoauflösungen verwendet werden. Die maximal unterstützte aggregierte Bandbreite der Videonutzlast liegt bei 8000 KBit/s für das Senden und Empfangen von Streams, die zum Beispiel beim Empfang von zwei Streams mit je 1920x1080 zum Einsatz käme. Maximalwerte werden im Realfall nur selten erreicht.

Beim Erstellen einer mehrteiligen Konferenz, in der das Feature "Katalogansicht" verwendet wird, nimmt die Bandbreitennutzung zunächst zu, wenn die Teilnehmer beitreten, und nimmt dann ab, wenn die Auflösungen in die maximale Größe fallen.

||**2 Teilnehmer**|**3 Teilnehmer**|**4 Teilnehmer**|**5 Teilnehmer**|**6 Teilnehmer**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Maximale Auflösungen empfangen** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Durchschnittliche Gesamtbitrate** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Maximale Gesamtbitrate** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

Die typische Streambandbreite für Panoramavideos basiert auf Geräten, die Panoramavideos mit einer Auflösung von 960x144 streamen. Wenn Sie Geräte mit einer Auflösung von 1920x288 verwenden, sollte sich die typische Bandbreite erhöhen.

**Planen der Audiokapazität für PSTN**

|**Medien**|**Typischer Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (Dies umfasst PSTN-Teilnehmer in Konferenzen)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

Die Angaben zur Netzwerkbandbreite in diesen Tabellen gelten nur für unidirektionalen Datenverkehr und beinhalten 5 KBit/s für RTCP-Overhead pro Stream.

## <a name="managing-quality-of-service"></a>Verwalten der Dienstqualität (Quality of Service, QoS)
<a name="man_QOS"> </a>

Bei der Dienstqualität (Quality of Service, QoS) handelt es sich um eine Netzwerktechnologie, die in einigen Organisationen zum Bereitstellen einer optimalen Benutzerfreundlichkeit für die Audio- und Videokommunikation verwendet wird. QoS kommt am häufigsten in Netzwerken mit beschränkter Bandbreite zum Einsatz, bei denen eine große Anzahl Netzwerkpakete um eine relativ geringe Bandbreite konkurrieren. Die Dienstqualität bietet Administratoren die Möglichkeit, Pakete mit Audio- oder Videodaten höhere Prioritäten zuzuweisen. Indem diesen Paketen eine höhere Priorität zugewiesen wird, kann die Audio- und Videokommunikation schneller und mit weniger Unterbrechungen ausgeführt werden als Netzwerksitzungen, in denen Dateiübertragungen, Webbrowsen oder Datenbanksicherungen erfolgen. Dies wird dadurch erreicht, dass den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden, eine „Best Effort“-Priorität zugewiesen wird.

> [!NOTE]
> In der Regel wird die Dienstqualität nur auf Kommunikationssitzungen innerhalb Ihres internen Netzwerks angewendet. Beim Implementieren von QoS konfigurieren Sie die Server und Router für die Unterstützung der Paketmarkierung auf eine bestimmte Art und Weise, die im Internet oder in anderen Netzwerken im Normalfall nicht unterstützt wird. Auch wenn die Dienstqualität in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass QoS auf die gleiche Weise konfiguriert wird, wie Sie den Dienst konfiguriert haben. Beim Anwenden von MPLS sind Sie an Ihren MPLS-Anbieter gebunden.

Skype for Business Server erfordert keine QoS, wird aber dringend empfohlen. Wenn Sie Probleme mit dem Paketverlust im Netzwerk haben, bestehen ihre verfügbaren Lösungen darin, mehr Bandbreite hinzuzufügen oder QoS zu implementieren. Wenn Sie nicht mehr Bandbreite hinzufügen können, ist das Problem nur mit Dienstqualität zu lösen.

Skype for Business Server bietet vollständige Unterstützung für QoS: Dies bedeutet, dass Organisationen, die bereits QoS verwenden, Skype for Business Server problemlos in Ihre vorhandene Netzwerkinfrastruktur integrieren können. Führen Sie dazu die folgenden Schritte aus:

- [Aktivieren von QoS in Skype for Business Server für Geräte, die nicht auf Windows basieren](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Zwar können Sie Skype for Business Server verwenden, um die Dienstqualität für Geräte zu aktivieren und zu deaktivieren, doch können Sie das Produkt in der Regel nicht zum Ändern der DSCP-Codes verwenden, die von diesen Geräten verwendet werden.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Durch die Verwendung von Skype for Business Server können Sie QoS nicht aktivieren oder deaktivieren, indem Sie einen Eigenschaftswert auf "wahr" oder "falsch" festlegen. Stattdessen wird die Dienstqualität durch die Konfiguration von Portbereichen und die anschließende Erstellung und Anwendung einer Gruppenrichtlinie aktiviert. Wenn Sie sich später entschließen, QoS zu verwenden, können Sie QoS deaktivieren, indem Sie die entsprechenden Gruppenrichtlinienobjekte entfernen.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Edgeserver](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md) Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die der anderen Server konfigurieren. Das Konfigurieren einer QoS-Richtlinie erfolgt nur für die interne Seite Ihrer Edgeserver. Das liegt daran, dass QoS für die Verwendung in Ihrem internen Netzwerk und nicht im Internet vorgesehen ist.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Diese Portbereiche gelten nur für Clientcomputer und stimmen in der Regel nicht mit den auf Ihren Servern konfigurierten Portbereichen überein. Beachten Sie, dass Skype for Business Server keine QoS für Windows-Betriebssysteme außer Windows 10 unterstützt.


> [!NOTE]
> Wenn Sie Windows Server 2012 oder Windows Server 2012 R2 verwenden, interessieren Sie sich möglicherweise für den neuen Satz von Windows PowerShell-Cmdlets, die für die Verwaltung von QoS auf dieser Plattform zur Verfügung stehen. Weitere Informationen finden Sie unter [Netzwerk-QoS-Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

QoS wird auch im Whitepaper [Netzwerkplanung,-Überwachung und-Problembehandlung mit lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) mit zusätzlichen Details und Tiefe erläutert. Während sich der Inhalt explizit auf lync 2010 und lync 2013 bezieht, sind die Überlegungen für Skype for Business Server unverändert.

## <a name="see-also"></a>Siehe auch
<a name="man_QOS"> </a>

[Plan für IPv6 in Skype for Business](ipv6.md)

[Anforderungen an den Lastenausgleich für Skype for Business](load-balancing.md)

[DNS-Anforderungen für Skype for Business Server](dns.md)
