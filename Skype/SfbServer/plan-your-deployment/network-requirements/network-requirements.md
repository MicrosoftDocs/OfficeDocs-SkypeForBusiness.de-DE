---
title: Planen der Netzwerkanforderungen für Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 0b5d183ecc11d09569427e432121fab7de8f401b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834355"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planen der Netzwerkanforderungen für Skype for Business

**Zusammenfassung:** Überprüfen Sie die folgenden Überlegungen zur Netzwerkkomponente, bevor Sie Skype for Business Server implementieren.

Die Informationen in diesen Themen werden auch im Whitepaper ["Netzwerkplanung,](https://www.microsoft.com/download/details.aspx?id=39084) Überwachung und Problembehandlung mit Lync Server" mit weiteren Details und Tiefe erläutert. Während der Inhalt explizit auf Lync 2010 und Lync 2013 verweist, bleiben die Überlegungen für Skype for Business Server unverändert.

Ebenso ist das Whitepaper ["Delivering Lync 2013 Real-Time Communications over WI-Fi"](https://www.microsoft.com/download/details.aspx?id=36494) eine gute Referenz, wenn Ihr Netzwerk sowohl WLAN als auch kabelgebundenen Zugriff umfasst. Es gilt gleichermaßen für Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Serverhardware
<a name="S_hard"> </a>

Der Netzwerkadapter jedes Servers in der Skype for Business Server-Topologie muss mindestens 1 Gigabit pro Sekunde (GBit/s) unterstützen. Im Allgemeinen sollten Sie alle Serverrollen innerhalb der Skype for Business Server-Topologie mit einer geringen Latenz und lan (Local Area Network) mit hoher Bandbreite verbinden. Die Größe des LAN hängt von der Größe der Topologie ab:

- In Standard Edition-Topologien sollten sich Server in einem Netzwerk befinden, das 1 GBit/s Ethernet oder eine entsprechende Unterstützung bietet.

- In Enterprise Edition-Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 GBit/s unterstützt, insbesondere bei der Unterstützung von Audio-/Videokonferenzen (A/V) und Anwendungsfreigaben.

Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.

## <a name="audiovideo-network-requirements"></a>Netzwerkanforderungen für Audio/Video
<a name="AV_req"> </a>

Zu den Netzwerkanforderungen für Audio/Video (A/V) in einer Skype for Business Server-Bereitstellung gehören folgende:

- Wenn Sie einen einzelnen Edgeserver oder Edgepool mithilfe des DNS-Lastenausgleichs bereitstellen, können Sie die externe Firewall so konfigurieren, dass die Netzwerkadressenübersetzung (Network Address Translation, NAT) ausgeführt wird.  Sie können die  interne Firewall nicht für die Durchführung von NAT konfigurieren. Weitere Informationen finden Sie unter [Port- und Firewallplanung.](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)

    > [!IMPORTANT]
    > Wenn Sie über einen Edgepool verfügen und ein Hardwaregerät zum Lastenausgleich verwenden, müssen Sie öffentliche IP-Adressen auf den Edgeservern verwenden, und Sie können nat für die Server oder den Pool an Ihrem NAT-fähigen Gerät (z. B. eine Firewall appliance oder einen LAN-Switch) keine NAT verwenden. Weitere Informationen finden Sie unter [Edgeserverszenarien in Skype for Business Server](../edge-server-deployments/scenarios.md).

- Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.

- Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden. Weitere Informationen finden Sie unter [IPsec-Ausnahmen.](#ipsec-exceptions)

Gehen Sie wie folgt vor, um eine optimale Medienqualität zu gewährleisten:

- Bereitstellen der Netzwerkverbindungen zur Unterstützung des Durchsatzes von 65 KBit/s pro Audiodatenstrom und 500 KBit/s pro Videostream( sofern aktiviert) zu Spitzenauslastungszeiten. Eine zwei-Wege-Audio- oder Videositzung verwendet zwei Datenströme, sodass für eine einfache Audio-/Telefonverbindung 130 KBit/s erforderlich sind, um jeden Stream zu abdecken. Video verwendet ebenfalls insgesamt 1000 KBit/s, um eine Upstream- und Downstreamverbindung zu nutzen.

- Um unerwartete Spitzen des Datenverkehrs und eine höhere Nutzung im Laufe der Zeit zu bewältigen, können sich Skype for Business Server-Medienendpunkte an unterschiedliche Netzwerkbedingungen anpassen und den dreifachen Durchsatz für Audio und Video unterstützen und gleichzeitig eine akzeptable Qualität beibehalten. Gehen Sie nicht davon aus, dass diese Anpassungsfähigkeit das Problem maskiert, wenn ein Netzwerk nicht bereitgestellt ist. In einem nicht bereitgestellten Netzwerk wird die Fähigkeit der Skype for Business Server-Medienendpunkte, sich dynamisch mit unterschiedlichen Netzwerkbedingungen (z. B. temporärem hohen Paketverlust) zu befassen, verringert.

- Bei Netzwerkverbindungen, bei denen die Bereitstellung sehr kostspielig und schwierig ist, müssen Sie möglicherweise die Bereitstellung für ein geringeres Datenverkehrsaufkommen in Betracht ziehen. Lassen Sie in diesem Szenario die Flexibilität der Skype for Business Server-Medienendpunkte den Unterschied zwischen dem Datenverkehrsaufkommen und dem Spitzendatenverkehrniveau auffangen, und dies auf Kosten einer etwas reduzierten Sprachqualität. Außerdem nimmt der Vorraum ab, da andernfalls plötzliche Spitzen des Datenverkehrs aufgefangen werden können.

- Für Verbindungen, die kurzfristig nicht ordnungsgemäß bereitgestellt werden können (z. B. ein Standort mit sehr schlechten WAN-Verbindungen), sollten Sie das Video für bestimmte Benutzer deaktivieren.

- Bereitstellen des Netzwerks, um eine maximale End-to-End-Verzögerung (Latenz) von 150 Millisekunden (ms) unter Spitzenlast zu garantieren. Latenz ist die einzige Netzwerkbeeinträchtigung, die Skype for Business Server-Medienkomponenten nicht reduzieren können, und es ist wichtig, die Schwachstellen zu finden und zu beseitigen.

- Schließen Sie für Server, auf denen Antivirensoftware ausgeführt wird, alle Server, auf denen Skype for Business Server ausgeführt wird, in die Ausnahmeliste ein, um eine optimale Leistung und Audioqualität zu gewährleisten.

## <a name="ipsec-exceptions"></a>IPsec-Ausnahmen

Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.

In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.

**Empfohlene IPsec-Ausnahmen**

|Regelname |Quell-IP |Ziel-IP |Protokoll |Quellport |Zielport |Authentifizierungsanforderung |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V-Edgeserver, intern eingehend|Beliebig  |A/V-Edgeserver, intern|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|A/V-Edgeserver, extern eingehend|Beliebig  |A/V-Edgeserver, extern|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|A/V-Edgeserver, intern ausgehend|A/V-Edgeserver, intern  |A/V-Edgeserver, extern |UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|A/V-Edgeserver, extern ausgehend|A/V-Edgeserver, extern |Beliebig |UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Vermittlungsserver, eingehend|Beliebig  |Vermittlungsserver |UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Vermittlungsserver, ausgehend|Vermittlungsserver  |Beliebig|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Konferenzzentrale, eingehend|Beliebig  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird |UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Konferenzzentrale (ausgehend)|Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |Beliebig|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|A/V-Konferenzserver, eingehend|Beliebig|Front-End-Server|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|A/V-Konferenzen, ausgehend|Front-End-Server|Beliebig|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Exchange, eingehend|Beliebig|Exchange Unified Messaging|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Anwendungsfreigabeserver, eingehend|Beliebig|Anwendungsfreigabeserver|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Anwendungsfreigabeserver, ausgehend|Anwendungsfreigabeserver| Beliebig |UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Exchange, ausgehend|Exchange Unified Messaging|Beliebig|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|Clients| Beliebig  |Beliebig|UDP und TCP|Beliebig |Beliebig |Nicht authentifizieren|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Netzwerkanforderungen für Konferenzen
<a name="Conf_req"> </a>

Die bandbreite zum Herunterladen von Konferenzinhalten vom Internetinformationsdienste (Internet Information Services, IIS)-Server verwendet wird, hängt von der Größe des Inhalts ab. Sie können die tatsächliche Nutzung überwachen und die Bandbreitenplanung entsprechend anpassen.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Netzwerkbandbreitenanforderungen für Mediendatenverkehr
<a name="Conf_req"> </a>

Ein wichtiger Bestandteil der Netzwerkplanung ist die Sicherstellung, dass Ihr Netzwerk den von Skype for Business Server generierten Mediendatenverkehr verarbeiten kann. Dieser Abschnitt hilft Ihnen bei der Planung für diesen Mediendatenverkehr.

### <a name="media-traffic-network-usage"></a>Netzwerknutzung des Mediendatenverkehrs
<a name="Net_req"> </a>

Aufgrund der Vielzahl an verschiedenen Faktoren, wie z. B. Codecverwendung, Auflösung und Aktivitätsgrad kann es schwierig sein, die Bandbreite für Mediendatenverkehr zu berechnen. Die Bandbreitennutzung ist eine Funktion des verwendeten Codecs und der Aktivität des Datenstroms, die je nach Szenario variieren kann. In der folgenden Tabelle sind die Audiocodecs aufgeführt, die normalerweise in Skype for Business Server-Szenarien verwendet werden.

**Bandbreite für Audiocodec**

|**Audiocodec**|**Szenario**|**Bitrate der Audionutzlast (KBIT/s)**|**Bandbreite für Audionutzlast und IP-Header (KBit/s)**|**Bandbreite für Audionutzlast, IP-Header, UDP, RTP und SRTP (KBit/s)**|**Bandbreite für Audionutzlast, IP-Header, UDP, RTP, SRTP und Vorwärtsfehlerkorrektur (KBit/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio, Breitband  <br/> |Peer-to-Peer  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|RTAudio, Schmalband  <br/> |Peer-to-Peer-PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Konferenzen  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722, Stereo  <br/> |Peer-zu-Peer-Konferenzen  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN, Konferenzen  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Konferenzen  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|BUND-Breitband  <br/> |Peer-to-Peer  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|BUND-Breitband  <br/> |Peer-to-Peer  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|BUND-Breitband  <br/> |Peer-to-Peer  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|WIDEBAND/Schmalband FÜR BUND  <br/> |Peer-to-Peer  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> PstN-Anrufe vom Skype for Business-Client verwenden in der Regel den G.711-Codec, der eine hohe Bandbreite erfordert. Wenn für diesen Codec nicht genügend Bandbreite verfügbar ist, können Anrufe mit einem Fehler wie dem folgenden in den Medienprotokollen fehlschlagen: **Atleast one codec must be enabled, hr: c0042004**. Medienprotokolle (BLOG-Dateien) sind verschlüsselt und können nur vom Supportpersonal von Microsoft decodiert werden.

Die Bandbreitennummern in der vorherigen Tabelle basieren auf der Paketierung von 20 ms (50 Pakete pro Sekunde), und für siren- und G.722-Codecs ist der zusätzliche SrTP (Secure Real-Time Transport Protocol)-Overhead durch Konferenzszenarien enthalten, und es wird angenommen, dass der Datenstrom zu 100 % aktiv ist. Die Vorwärtsfehlerkorrektur (Forward Error Correction, FEC) wird dynamisch verwendet, wenn der Link Paketverluste verursacht, um die Qualität des Audiodatenstroms zu erhalten.

Die Stereoversion des G.722-Codecs wird von Systemen verwendet, die auf dem Lync Room System basieren und ein einzelnes Stereomikrofon oder ein Paar Monomikrofone verwenden, damit Listener mehrere Lautsprecher im Besprechungsraum besser unterscheiden können.

**Bandbreite für Videoauflösung**

|**Videocodec**|**Auflösung und Seitenverhältnis**|**Maximale Bitrate der Videonutzlast (KBit/s)**|**Minimale Bitrate der Videonutzlast (KBit/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320 x 180 (16:9)  <br/> 212 x 160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H.264/RTVideo  <br/> |424 x 240 (16:9)  <br/> 320 x 240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480 x 270 (16:9)  <br/> 424 x 320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640 x 480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848 x 480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960 x 540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920 x 1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960 x 144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H.264  <br/> |1280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Der Standardcodec für Video ist der H.264/MPEG-4 Part 10 Advanced Video Coding Standard, zusammen mit seinen skalierbaren Videocodierungserweiterungen für die zeitliche Skalierbarkeit. Zur Aufrechterhaltung der Interoperabilität mit Legacyclients wird der RTVideo-Codec weiterhin für Peer-zu-Peer-Anrufe zwischen Skype for Business Server und Legacyclients verwendet. In Konferenzsitzungen mit Skype for Business Server und Legacyclients kann der Skype for Business Server-Endpunkt das Video mit beiden Videocodecs codieren und den H.264-Bitstream an die Skype for Business Server-Clients und den RTVideo-Bitstream an Legacyclients senden.

Die erforderliche Bandbreite hängt von der Auflösung, Qualität, Bildfrequenz und der Menge der Bewegung oder Änderung im Bild ab. Für jede Auflösung gibt es zwei relevante Bitraten:

- **Maximale Nutzlastbitrate** Dies ist die Bitrate, die ein Endpunkt für die Auflösung mit der maximalen Framerate verwendet. Dies ist der Wert, der die höchste Video- und Tonqualität zulässt.

- **Bitrate der minimalen Nutzlast** Dies ist die Bitrate, unter der ein Skype for Business Server-Endpunkt zur nächsten niedrigeren Auflösung wechselt. Um eine bestimmte Auflösung zu gewährleisten, darf die bitrate der verfügbaren Videonutzlast nicht unter diese minimale Bitrate für diese Auflösung fallen. Dieser Wert hilft Ihnen, den niedrigsten Wert zu verstehen, der möglich ist, wenn die maximale Bitrate nicht verfügbar oder praktikabel ist. Für einige Benutzer kann eine derart niedrige Bitrate video eine inakzeptable Videoerfahrung bieten. Seien Sie daher vorsichtig bei diesen Bitraten der minimalen Videonutzlast. Beachten Sie, dass bei statischen, unveränderlichen Videoszenen die tatsächliche Bitrate vorübergehend unter die minimale Bitrate fallen kann.

Skype for Business Server unterstützt viele Lösungen. Auf diese Weise kann Skype for Business Server an verschiedene Netzwerkbandbreiten und Empfangen von Clientfunktionen angepasst werden. Das Standardaspektverhältnis für Skype for Business Server ist 16:9. Das ältere Seitenverhältnis 4:3 wird weiterhin für Webcams unterstützt, die keine Aufnahme im Seitenverhältnis 16:9 zulassen.

Video-FEC ist immer in der Bitrate der Videonutzlast enthalten, wenn es verwendet wird, sodass es keine separaten Werte für video-FEC und ohne Video-FEC gibt.

Endpunkte übertragen Audio- oder Videopakete nicht in einem kontinuierlichen Stream. Für jedes Szenario gibt es unterschiedliche Aktivitätsebenen, die angeben, wie häufig Pakete für einen Stream gesendet werden. Die Aktivität eines Streams richtet sich nach dem Medium und dem Szenario, nicht jedoch nach dem verwendeten Codec. In einem Peer-zu-Peer-Szenario gilt Folgendes:

- Endpunkte senden nur Audiodatenströme, wenn die Benutzer sprechen.

- Beide Teilnehmer empfangen Audiostreams.

- Wenn Video verwendet wird, senden und empfangen beide Endpunkte Videostreams während des Anrufs.

- Bei statischen Videoszenen kann die tatsächliche Bitrate vorübergehend sehr niedrig sein, da der Videocodec Codierungsbereiche des Videos überspringt, ohne dass seit dem vorherigen Beispiel eine Änderung erforderlich ist.

In einem Konferenzszenario gilt Folgendes:

- Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.

- Alle Teilnehmer empfangen Audiostreams.

- Wenn Video verwendet wird, können alle Teilnehmer bis zu fünf Videostreams und einen Panoramavideostream (z. B. seitenverhältnis 20:3) empfangen. Standardmäßig basieren die fünf Empfangen von Videostreams auf dem Verlauf des aktiven Sprechers, die Benutzer können jedoch auch manuell die Teilnehmer auswählen, von denen sie einen Videostream empfangen möchten. Wenn Multivideos aktiviert sind, ist die Auflösungs- und Bandbreitenanforderung für die einzelnen Videostreams geringer.

- Jeder Teilnehmer, der den Sendevideostream des Benutzers aktiviert, sendet einen oder mehrere Videostreams. Skype for Business Server kann bis zu fünf Videostreams senden, um die Videoqualität für alle empfangenden Clients zu optimieren. Die tatsächliche Anzahl an gesendeten Videostreams wird vom Sender basierend auf CPU-Leistung, verfügbarer Uplink-Bandbreite und der Anzahl an Empfängerclients, die einen bestimmten Videostream angefordert haben, bestimmt. Üblicherweise wird ein H.264- und ein RTVideo-Stream gesendet, wenn ein älterer Client an der Konferenz teilnimmt. Bei einem anderen typischen Szenario werden mehrere H.264-Videostreams (z. B. mit verschiedenen Auflösungen) gesendet, um verschiedenen Empfängeranforderungen gerecht zu werden.

Zusätzlich zu der Bandbreite, die für den RTP-Datenverkehr (Real-Time Transport Protocol) für Audio- und Videomedien erforderlich ist, wird auch Bandbreite für RTCP-Datenverkehr (Real-Time Transport Control Protocol) benötigt. RTCP wird zum Generieren von Statistiken und zur Out-of-Band-Steuerung des RTP-Streams genutzt. Verwenden Sie zur Planung die Bandbreitenangaben in der folgenden Tabelle für RTCP-Datenverkehr. Diese Werte stellen die maximale Bandbreite dar, die für RTCP verwendet wird, und unterscheiden sich aufgrund von Unterschieden in den Steuerungsdaten für Audio- und Videostreams.

**RTCP-Bandbreite**

|**Medien**|**Maximale RTCP-Bandbreite (KBit/s)**|
|:-----|:-----|
|Audio  <br/> |5   <br/> |
|Video (es wird nur H.264 oder RTVideo gesendet/empfangen)  <br/> |10   <br/> |
|Video (H.264 und RTVideo werden gesendet/empfangen)  <br/> |15   <br/> |

Für die Kapazitätsplanung sind die folgenden beiden Statistiken von Interesse:

- **Maximale Bandbreite ohne FEC** Die maximale Bandbreite, die ein Stream verbraucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der im Szenario ohne FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und kein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur auslöst. Dies ist hilfreich, um zu berechnen, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann. Es wird nicht erwartet, dass FEC eine Anforderung in einem verwalteten Netzwerk ist.

- **Maximale Bandbreite mit FEC** Die maximale Bandbreite, die ein Stream verbraucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der im Szenario mit FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und ein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur zur Verbesserung der Qualität auslöst. Dies ist hilfreich, um zu berechnen, wie viel Bandbreite zugewiesen werden muss, um die Verwendung des Codecs in einem bestimmten Szenario zu ermöglichen und die Verwendung von FEC zu ermöglichen, um die Qualität unter Bedingungen des Paketverlusts zu erhalten.

In den folgenden Tabellen ist auch ein zusätzlicher Bandbreitenwert aufgeführt, **die typische Bandbreite.** Dies ist die durchschnittliche Bandbreite, die ein Datenstrom verbraucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der in diesem Szenario verwendet wird. Diese Bandbreite kann zur Schätzung der Bandbreite verwendet werden, die zu einem bestimmten Zeitpunkt vom Mediendatenverkehr verbraucht wird, sollte jedoch nicht für die Kapazitätsplanung verwendet werden, da einzelne Anrufe diesen Wert überschreiten, wenn die Aktivitätsstufe über dem Durchschnitt liegt. Die typische Bandbreite des Videostreams in den folgenden Tabellen basiert auf einer Kombination unterschiedlicher Videoauflösungen, die in gemessenen Kundendaten beobachtet werden, und kleinere Installationen haben wahrscheinlich tatsächliche Zahlen, die sich von den Tabellendaten unterscheiden. In Peer-zu-Peer-Sitzungen würden die meisten Benutzer beispielsweise das Standardfenster zum Rendern von Videos verwenden, während ein Prozentsatz der Benutzer die Skype for Business Server-Anwendung vergrößern oder maximieren würde, um bessere Videoauflösungen zu ermöglichen.

Die folgenden Tabellen enthalten Werte für die verschiedenen Szenarien.

**Planen der Audio/Videokapazität für Peer-zu-Peer-Sitzungen**

|**Medien**|**Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |RTAudio, Breitband  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |BUND-Breitband  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Hauptvideo beim Anrufen von Skype for Business Server-Endpunkten  <br/> |H.264  <br/> |460  <br/> |4010 (für eine maximale Auflösung von 1920x1080)  <br/> |Bereits enthalten  <br/> |
|Hauptvideo beim Aufrufen von Lync 2010- oder Office Communicator 2007 R2-Endpunkten  <br/> |RTVideo  <br/> |460  <br/> |2510 (für eine maximale Auflösung von 1280x720)  <br/> |Bereits enthalten  <br/> |
|Panoramavideo beim Anrufen von Skype for Business Server-Endpunkten  <br/> |H.264  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Bereits enthalten  <br/> |
|Panoramavideo beim Aufrufen von Lync 2010-Endpunkten  <br/> |RTVideo  <br/> |190  <br/> |510 (für eine maximale Auflösung von 960x144)  <br/> |Bereits enthalten  <br/> |

**Planen der Audio-/Videokapazität für Konferenzen**

|**Medien**|**Typischer Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Hauptvideo, Empfang  <br/> |H.264 und RTVideo¹  <br/> |260  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Hauptvideo, Senden  <br/> |H.264 und RTVideo  <br/> |270  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Empfang  <br/> |H.264 und RTVideo  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Senden  <br/> |H.264 und RTVideo  <br/> |190  <br/> |2515 verz  <br/> |Nicht zutreffend  <br/> |

1. RT Video wird zusätzlich zu H.264 gesendet, wenn Lync 2010-Clients mit der Konferenz verbunden sind.

2. Wenn mehrere Datenströme enthalten sind, teilen sie sich die zugewiesene Bandbreite dynamisch.

Für das Hauptvideo ist die typische Streambandbreite die aggregierte Bandbreite über alle empfangenen Videostreams, und der maximale Datenstrom ist die Bandbreite über alle Sendevideostreams. Selbst bei mehreren Videostreams ist die typische Videobandbreite kleiner als im Peer-zu-Peer-Szenario, da viele Videokonferenzen die Inhaltsfreigabe verwenden, was zu wesentlich kleineren Videofenstern und damit zu kleineren Videoauflösungen führt. Die maximal unterstützte Bandbreite für die aggregierte Videonutzlast beträgt 8000 KBit/s für Sende- und Empfangsstreams, die verwendet werden würden (z. B. bei zwei eingehenden 1920x1080p-Videostreams). Höchstwerte werden in tatsächlichen Implementierungen nur selten angezeigt.

Beim Aufbau einer Konferenz mit mehreren Teilnehmern, die die Katalogansichtsfunktion verwendet, nimmt die Bandbreitenauslastung beim Beitritt der Teilnehmer zu Beginn zu und nimmt dann ab, wenn Auflösungen verworfen werden, um den maximal zulässigen Wert zu erreichen.

||**2 Teilnehmer**|**3 Teilnehmer**|**4 Teilnehmer**|**5 Teilnehmer**|**6 Teilnehmer**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Maximale Auflösungen empfangen** <br/> |1920 x 1080  <br/> |1280 x 720  <br/> |640 x 360  <br/> |640 x 360 320 x 240  <br/> |640 x 360 320 x 240  <br/> |
|**Durchschnittliche Bitrate insgesamt** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Maximale Bitrate insgesamt** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

Die typische Streambandbreite für Panoramavideos basiert auf Geräten, die nur Panoramavideos von bis zu 960 x 144 streamen. Erwarten Sie, dass die typische Streambandbreite bei Verwendung von Geräten mit Panoramavideos von 1920 x 288 erhöht wird.

**Planen der Audiokapazität für PSTN**

|**Medien**|**Typischer Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (einschließlich PSTN-Teilnehmern an Konferenzen)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

Die Angaben zur Netzwerkbandbreite in diesen Tabellen gelten nur für unidirektionalen Datenverkehr und beinhalten 5 KBit/s für RTCP-Overhead pro Stream.

## <a name="managing-quality-of-service"></a>Verwalten der Dienstqualität
<a name="man_QOS"> </a>

Quality of Service (QoS) ist eine Netzwerktechnologie, die in einigen Organisationen verwendet wird, um eine optimale Endbenutzererfahrung für die Audio- und Videokommunikation zu bieten. QoS wird am häufigsten in Netzwerken verwendet, in denen die Bandbreite begrenzt ist: Da eine große Anzahl von Netzwerkpaketen um eine relativ kleine Menge verfügbarer Bandbreite konkurrieren, können Administratoren mit QoS Paketen, die Audio- oder Videodaten übertragen, höhere Prioritäten zuweisen. Da diesen Paketen eine höhere Priorität eingeräumt wird, wird die Audio- und Videokommunikation wahrscheinlich schneller und mit weniger Unterbrechungen abgeschlossen als Netzwerksitzungen, an denen z. B. Dateiübertragungen, Webbrowsen oder Datenbanksicherungen beteiligt sind. Die Ursache dafür ist die Zuweisung einer "Best Effort"-Priorität zu den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden.

> [!NOTE]
> In der Regel gilt QoS nur für Kommunikationssitzungen in Ihrem internen Netzwerk. Wenn Sie QoS implementieren, konfigurieren Sie Ihre Server und Router so, dass die Paketmarkierung auf eine bestimmte Weise unterstützt wird, die möglicherweise nicht im Internet oder in anderen Netzwerken unterstützt wird. Auch wenn Quality of Service in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass QoS auf die gleiche Weise konfiguriert wird, wie Sie den Dienst konfiguriert haben. Wenn Sie MPLS verwenden, müssen Sie mit Ihrem MPLS-Anbieter arbeiten.

Skype for Business Server erfordert keine QoS, wird jedoch dringend empfohlen. Wenn Im Netzwerk Probleme mit Paketverlusten auftreten, können Sie mit Ihren verfügbaren Lösungen mehr Bandbreite hinzufügen oder QoS implementieren. Wenn keine zusätzliche Bandbreite hinzugefügt werden kann, ist die Implementierung von QoS möglicherweise die einzige Gebühren, um das Problem zu beheben.

Skype for Business Server bietet vollständige Unterstützung für QoS: Das bedeutet, dass Organisationen, die bereits QoS verwenden, Skype for Business Server problemlos in ihre vorhandene Netzwerkinfrastruktur integrieren können. Führen Sie dazu die folgenden Schritte aus:

- [Aktivieren von QoS in Skype for Business Server für Geräte, die nicht auf Windows basieren.](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md) Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Obwohl Sie Skype for Business Server zum Aktivieren und Deaktivieren der Dienstqualität für Geräte verwenden können, können Sie das Produkt normalerweise nicht verwenden, um die von diesen Geräten verwendeten DSCP-Codes zu ändern.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Konferenz-, Anwendungs- und Vermittlungsserver](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Bei Verwendung von Skype for Business Server aktivieren oder deaktivieren Sie QoS nicht, indem Sie einen Eigenschaftswert auf "True" oder "False" festlegen. Stattdessen aktivieren Sie QoS, indem Sie Portbereiche konfigurieren und dann Gruppenrichtlinien erstellen und anwenden. Wenn Sie QoS später nicht verwenden möchten, können Sie QoS "deaktivieren", indem Sie die entsprechenden Gruppenrichtlinienobjekte entfernen.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Edgeserver](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die anderen Server konfigurieren. Das Konfigurieren einer QoS-Richtlinie erfolgt nur für die interne Seite Ihrer Edgeserver. Der Grund dafür ist, dass QoS für die Verwendung in Ihrem internen Netzwerk und nicht im Internet konzipiert ist.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Diese Portbereiche gelten nur für Clientcomputer und unterscheiden sich in der Regel von den auf den Servern konfigurierten Portbereichen. Beachten Sie, dass Skype for Business Server andere Betriebssysteme als Windows 10 nicht für QoS für Windows unterstützt.


> [!NOTE]
> Wenn Sie Windows Server 2012 oder Windows Server 2012 R2 verwenden, sind Sie möglicherweise an der neuen Gruppe von Windows PowerShell-Cmdlets interessiert, die für die Verwaltung von QoS auf dieser Plattform verfügbar sind. Weitere Informationen finden Sie unter ["Network QoS Cmdlets" in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

QoS wird auch im Whitepaper ["Netzwerkplanung,](https://www.microsoft.com/download/details.aspx?id=39084) Überwachung und Problembehandlung mit Lync Server" mit weiteren Details und Tiefe erläutert. Während der Inhalt explizit auf Lync 2010 und Lync 2013 verweist, bleiben die Überlegungen für Skype for Business Server unverändert.

## <a name="see-also"></a>Siehe auch
<a name="man_QOS"> </a>

[Planen von IPv6 in Skype for Business](ipv6.md)

[Lastenausgleichsanforderungen für Skype for Business](load-balancing.md)

[DNS-Anforderungen für Skype for Business Server](dns.md)
