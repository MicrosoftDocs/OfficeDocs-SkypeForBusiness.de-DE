---
title: Planen der Netzwerkanforderungen für Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Zusammenfassung: Überprüfen Sie die nachstehenden Überlegungen zur Netzwerkkomponente, bevor Sie Skype for Business Server implementieren.'
---

# <a name="plan-network-requirements-for-skype-for-business"></a>Planen der Netzwerkanforderungen für Skype for Business

**Zusammenfassung:** Überprüfen Sie die nachstehenden Überlegungen zur Netzwerkkomponente, bevor Sie Skype for Business Server implementieren.

Die Informationen in diesen Themen werden auch im Whitepaper ["Netzwerkplanung, Überwachung und Problembehandlung mit Lync Server" mit](https://www.microsoft.com/download/details.aspx?id=39084) zusätzlichen Details und Tiefe erläutert. Während sich der Inhalt explizit auf Lync 2010 und Lync 2013 bezieht, sind die Überlegungen für Skype for Business Server unverändert.

Ebenso ist das Whitepaper ["Delivering Lync 2013 Real-Time Communications over WI-Fi](https://www.microsoft.com/download/details.aspx?id=36494)" eine gute Referenz und gilt auch für Skype for Business Server, wenn Ihr Netzwerk WLAN und kabelgebundenen Zugriff umfasst.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Serverhardware
<a name="S_hard"> </a>

Der Netzwerkadapter jedes Servers in der Skype for Business Server Topologie muss mindestens 1 Gigabit pro Sekunde (GBit/s) unterstützen. Im Allgemeinen sollten Sie alle Serverrollen innerhalb der Skype for Business Server-Topologie mit einer geringen Latenz und einem LAN (Local Area Network) mit hoher Bandbreite verbinden. Die Größe des LAN hängt von der Größe der Topologie ab:

- In Standard Edition Topologien sollten sich Server in einem Netzwerk befinden, das 1 GBit/s Ethernet oder ein entsprechendes Netzwerk unterstützt.

- In Enterprise Edition Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 GBit/s unterstützt, insbesondere bei der Unterstützung von Audio-/Videokonferenzen (A/V) und Anwendungsfreigabe.

Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.

## <a name="audiovideo-network-requirements"></a>Netzwerkanforderungen für Audio/Video
<a name="AV_req"> </a>

Zu den Netzwerkanforderungen für Audio/Video (A/V) in einer Skype for Business Server Bereitstellung gehören:

- Wenn Sie einen einzelnen Edgeserver oder einen Edgepool mithilfe des DNS-Lastenausgleichs bereitstellen, können Sie die  _externe_ Firewall für die Netzwerkadressübersetzung (Network Address Translation, NAT) konfigurieren. Sie können die _interne_ Firewall nicht so konfigurieren, dass NAT ausgeführt wird. Ausführliche Informationen finden Sie unter [Port- und Firewallplanung](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Wenn Sie über einen Edgepool verfügen und ein Hardwaregerät zum Lastenausgleich verwenden, müssen Sie öffentliche IP-Adressen auf den Edgeservern und keine NAT für die Server oder den Pool auf Ihrem NAT-fähigen Gerät (z. B. eine Firewall-Appliance oder einen LAN-Switch) verwenden. Ausführliche Informationen finden Sie [unter Edgeserverszenarien in Skype for Business Server](../edge-server-deployments/scenarios.md).

- Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.

- Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden. Ausführliche Informationen finden Sie unter [IPsec-Ausnahmen](#ipsec-exceptions).

Führen Sie die folgenden Schritte aus, um eine optimale Medienqualität bereitzustellen:

- Stellen Sie die Netzwerkverbindungen bereit, um den Durchsatz von 65 Kilobit pro Sekunde (KBit/s) pro Audiodatenstrom und 500 KBit/s pro Videostream zu unterstützen, sofern diese aktiviert sind, während Spitzenauslastungszeiten. Eine bidirektionale Audio- oder Videositzung verwendet zwei Datenströme, sodass für eine einfache Audio-/Telefonverbindung 130 KBit/s erforderlich sind, um jeden Stream abzudecken. Video verwendet ebenfalls insgesamt 1000 KBit/s, um eine upstream- und downstream-Verbindung zu übertragen.

- Um unerwartete Spitzen beim Datenverkehr und eine höhere Nutzung im Laufe der Zeit zu bewältigen, können sich Skype for Business Server Medienendpunkte an unterschiedliche Netzwerkbedingungen anpassen und den dreifachen Durchsatz für Audio und Video unterstützen und gleichzeitig eine akzeptable Qualität beibehalten. Gehen Sie nicht davon aus, dass diese Anpassungsfähigkeit das Problem überdecken wird, wenn ein Netzwerk nicht bereitgestellt wird. In einem nicht bereitgestellten Netzwerk verringert sich die Fähigkeit der Skype for Business Server Medienendpunkte, dynamisch mit variierenden Netzwerkbedingungen umzugehen (z. B. temporärer hoher Paketverlust).

- Bei Netzwerkverbindungen, bei denen die Bereitstellung sehr kostspielig und schwierig ist, müssen Sie möglicherweise die Bereitstellung für ein geringeres Datenverkehrsvolumen in Betracht ziehen. Lassen Sie in diesem Szenario die Ausfallsicherheit der Skype for Business Server Medienendpunkte den Unterschied zwischen dem Datenverkehrsvolumen und der Spitzendatenverkehrsebene auffangen, was zu einer gewissen Reduzierung der VoIP-Qualität führen kann. Außerdem wird der Headroom verringert, da andernfalls plötzliche Spitzen im Datenverkehr aufgefangen werden können.

- Für Links, die kurzfristig nicht ordnungsgemäß bereitgestellt werden können (z. B. ein Standort, der sehr schlechte WAN-Verbindungen verwendet), sollten Sie die Videofunktion für bestimmte Benutzer deaktivieren.

- Stellen Sie das Netzwerk bereit, um eine maximale End-to-End-Verzögerung (Latenz) von 150 Millisekunden (ms) unter Spitzenlast zu gewährleisten. Latenz ist die einzige Netzwerkbeeinträchtigung, die Skype for Business Server Medienkomponenten nicht reduzieren können, und es ist wichtig, die Schwachstellen zu finden und zu beseitigen.

- Fügen Sie für Server, auf denen Antivirensoftware ausgeführt wird, alle Server, auf denen Skype for Business Server ausgeführt werden, in die Ausnahmeliste ein, um eine optimale Leistung und Audioqualität bereitzustellen.

## <a name="ipsec-exceptions"></a>IPsec-Ausnahmen

Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.

In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert.

**Empfohlene IPsec-Ausnahmen**

|Regelname |Quell-IP |Ziel-IP |Protokoll |Quellport |Zielport |Authentifizierungsanforderung |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V-Edgeserver, intern eingehend|Any  |A/V-Edgeserver, intern|UDP und TCP|Any |Any |Nicht authentifizieren|
|A/V-Edgeserver, extern eingehend|Any  |A/V-Edgeserver, extern|UDP und TCP|Any |Any |Nicht authentifizieren|
|A/V-Edgeserver, intern ausgehend|A/V-Edgeserver, intern  |A/V-Edgeserver, extern |UDP und TCP|Any |Any |Nicht authentifizieren|
|A/V-Edgeserver, extern ausgehend|A/V-Edgeserver, extern |Any |UDP und TCP|Any |Any |Nicht authentifizieren|
|Vermittlungsserver, eingehend|Any  |Vermittlungsserver |UDP und TCP|Any |Any |Nicht authentifizieren|
|Vermittlungsserver, ausgehend|Vermittlungsserver  |Any|UDP und TCP|Any |Any |Nicht authentifizieren|
|Konferenzzentrale, eingehend|Any  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird |UDP und TCP|Any |Any |Nicht authentifizieren|
|Konferenzzentrale (ausgehend)|Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |Any|UDP und TCP|Any |Any |Nicht authentifizieren|
|A/V-Konferenzserver, eingehend|Any|Front-End-Server|UDP und TCP|Any |Any |Nicht authentifizieren|
|A/V-Konferenzen, ausgehend|Front-End-Server|Any|UDP und TCP|Any |Any |Nicht authentifizieren|
|Exchange, eingehend|Any|Exchange Unified Messaging|UDP und TCP|Any |Any |Nicht authentifizieren|
|Anwendungsfreigabeserver, eingehend|Any|Anwendungsfreigabeserver|UDP und TCP|Any |Any |Nicht authentifizieren|
|Anwendungsfreigabeserver, ausgehend|Anwendungsfreigabeserver| Any |UDP und TCP|Any |Any |Nicht authentifizieren|
|Exchange, ausgehend|Exchange Unified Messaging|Any|UDP und TCP|Any |Any |Nicht authentifizieren|
|Clients| Any  |Any|UDP und TCP|Any |Any |Nicht authentifizieren|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Netzwerkanforderungen für Konferenzen
<a name="Conf_req"> </a>

Die Bandbreite, die zum Herunterladen von Konferenzinhalten vom Internetinformationsdienste (IIS)-Server verwendet wird, hängt von der Größe des Inhalts ab. Sie können die tatsächliche Auslastung überwachen und die Bandbreitenplanung entsprechend anpassen.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Netzwerkbandbreitenanforderungen für Mediendatenverkehr
<a name="Conf_req"> </a>

Ein wichtiger Teil der Netzwerkplanung besteht darin, sicherzustellen, dass Ihr Netzwerk den von Skype for Business Server generierten Mediendatenverkehr verarbeiten kann. Dieser Abschnitt hilft Ihnen bei der Planung für diesen Mediendatenverkehr.

### <a name="media-traffic-network-usage"></a>Netzwerknutzung des Mediendatenverkehrs
<a name="Net_req"> </a>

Aufgrund der Vielzahl an verschiedenen Faktoren, wie z. B. Codecverwendung, Auflösung und Aktivitätsgrad kann es schwierig sein, die Bandbreite für Mediendatenverkehr zu berechnen. Die Bandbreitennutzung ist eine Funktion des verwendeten Codecs und der Aktivität des Datenstroms, die je nach Szenario variieren kann. In der folgenden Tabelle sind die Audiocodecs aufgeführt, die normalerweise in Skype for Business Server Szenarien verwendet werden.

**Audiocodecbandbreite**

|**Audiocodec**|**Szenario**|**Audionutzlast-Bitrate (KBIT/s)**|**Bandbreite für Audionutzlast und IP-Header (KBit/s)**|**Bandbreite für Audionutzlast, IP-Header, UDP, RTP und SRTP (KBit/s)**|**Bandbreite für Audionutzlast, IP-Header, UDP, RTP, SRTP und Vorwärtsfehlerkorrektur (KBit/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio, Breitband  <br/> |Peer-to-Peer  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|RTAudio, Schmalband  <br/> |Peer-to-Peer-PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Konferenzen  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722, Stereo  <br/> |Peer-to-Peer-Konferenzen  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN, Konferenzen  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Sirene  <br/> |Konferenzen  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|SILK Wideband  <br/> |Peer-to-Peer  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|SILK Wideband  <br/> |Peer-to-Peer  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|SILK Wideband  <br/> |Peer-to-Peer  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|WIDE Wideband/Schmalband  <br/> |Peer-to-Peer  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> PSTN-Anrufe vom Skype for Business Client verwenden in der Regel den G.711-Codec, der eine hohe Bandbreite erfordert. Wenn für diesen Codec nicht genügend Bandbreite verfügbar ist, können Aufrufe mit einem Fehler fehlschlagen, der in den Medienprotokollen wie folgt aussieht: **Atleast one codec must be enabled, hr: c0042004**. Medienprotokolle (BLOG-Dateien) werden verschlüsselt und können nur von Microsoft-Supportmitarbeitern decodiert werden.

Die Bandbreitennummern in der vorherigen Tabelle basieren auf der Paketisierung von 20 Ms (50 Pakete pro Sekunde) und für die Codecs Siren und G.722 umfassen den zusätzlichen SRTP-Overhead (Secure Real-Time Transport Protocol) von Konferenzszenarien und gehen davon aus, dass der Datenstrom zu 100 % aktiv ist. Die Weiterleitungsfehlerkorrektur (Forward Error Correction, FEC) wird dynamisch verwendet, wenn ein Paketverlust auf dem Link auftritt, um die Qualität des Audiodatenstroms aufrechtzuerhalten.

Die Stereoversion des G.722-Codecs wird von Systemen verwendet, die auf dem Lync-Raumsystem basieren, das ein einzelnes Stereomikrofon oder ein Mono-Mikrofonpaar verwendet, damit Listener mehrere Lautsprecher im Besprechungsraum besser unterscheiden können.

**Bandbreite für Videoauflösung**

|**Videocodec**|**Auflösung und Seitenverhältnis**|**Maximale Bitrate der Videonutzlast (KBit/s)**|**Bitrate der mindesten Videonutzlast (KBit/s)**|
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

Der Standardcodec für Video ist der Standard H.264/MPEG-4 Part 10 Advanced Video Coding, zusammen mit den skalierbaren Videocodierungserweiterungen für die zeitliche Skalierbarkeit. Um die Interoperabilität mit Legacyclients aufrechtzuerhalten, wird der RTVideo-Codec weiterhin für Peer-to-Peer-Anrufe zwischen Skype for Business Server und Legacyclients verwendet. In Konferenzsitzungen mit Skype for Business Server- und Legacyclients kann der Skype for Business Server-Endpunkt das Video mit beiden Videocodecs codieren und den H.264-Bitstream an die Skype for Business Server-Clients und den RTVideo-Bitstream an Legacyclients senden.

Die erforderliche Bandbreite hängt von der Auflösung, Qualität, Bildfrequenz und der Menge der Bewegung oder Änderung im Bild ab. Für jede Auflösung gibt es zwei relevante Bitraten:

- **Bitrate mit maximaler Nutzlast** Dies ist die Bitrate, die ein Endpunkt für die Auflösung mit der maximalen Framerate verwendet. Dies ist der Wert, der die höchste Video- und Tonqualität zulässt.

- **Minimale Nutzlastbitrate** Dies ist die Bitrate, unter der ein Skype for Business Server Endpunkt zur nächst niedrigeren Auflösung wechselt. Um eine bestimmte Auflösung zu gewährleisten, darf die verfügbare Bitrate der Videonutzlast nicht unter diese minimale Bitrate für diese Auflösung fallen. Dieser Wert hilft Ihnen, den niedrigsten wert zu verstehen, der möglich ist, wenn die maximale Bitrate nicht verfügbar oder praktisch ist. Für einige Benutzer kann ein solches Video mit niedriger Bitrate eine inakzeptable Videoumgebung bieten. Seien Sie daher mit diesen Mindest-Videonutzlastbitraten vorsichtig. Beachten Sie, dass bei statischen, sich nicht ändernden Videoszenen die tatsächliche Bitrate vorübergehend unter die minimale Bitrate fällt.

Skype for Business Server unterstützt viele Auflösungen. Auf diese Weise können Skype for Business Server sich an die unterschiedliche Netzwerkbandbreite und empfangende Clientfunktionen anpassen. Das Standardseitenverhältnis für Skype for Business Server ist 16:9. Das alte 4:3-Seitenverhältnis wird weiterhin für Webcams unterstützt, die keine Erfassung im 16:9-Seitenverhältnis zulassen.

Video FEC ist immer in der Videonutzlast-Bitrate enthalten, wenn es verwendet wird, sodass es keine separaten Werte für Video-FEC und ohne Video-FEC gibt.

Endpunkte übertragen Audio- oder Videopakete nicht in einem kontinuierlichen Stream. Für jedes Szenario gibt es unterschiedliche Aktivitätsebenen, die angeben, wie häufig Pakete für einen Stream gesendet werden. Die Aktivität eines Streams richtet sich nach dem Medium und dem Szenario, nicht jedoch nach dem verwendeten Codec. In einem Peer-zu-Peer-Szenario gilt Folgendes:

- Endpunkte senden Audiodatenströme nur, wenn die Benutzer sprechen.

- Beide Teilnehmer empfangen Audiostreams.

- Wenn Video verwendet wird, senden und empfangen beide Endpunkte während des Anrufs Videostreams.

- Bei statischen Videoszenen kann die tatsächliche Bitrate vorübergehend sehr niedrig sein, da der Videocodec die Codierung von Bereichen des Videos ohne Änderung seit dem vorherigen Beispiel überspringt.

In einem Konferenzszenario gilt Folgendes:

- Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.

- Alle Teilnehmer empfangen Audiostreams.

- Wenn Video verwendet wird, können alle Teilnehmer bis zu fünf Videostreams und einen Panoramavideostream (z. B. ein Seitenverhältnis von 20:3) empfangen. Standardmäßig basieren die fünf empfangenden Videostreams auf dem aktiven Lautsprecherverlauf, aber benutzer können auch manuell die Teilnehmer auswählen, aus denen sie einen Videostream empfangen möchten. Wenn Multi-Video aktiviert ist, ist die Auflösungs- und Bandbreitenanforderung für jeden Videodatenstrom geringer.

- Jeder Teilnehmer, der den Sendevideostream des Benutzers aktiviert, sendet einen oder mehrere Videostreams. Skype for Business Server kann bis zu fünf Videostreams senden, um die Videoqualität für alle empfangenden Clients zu optimieren. Die tatsächliche Anzahl an gesendeten Videostreams wird vom Sender basierend auf CPU-Leistung, verfügbarer Uplink-Bandbreite und der Anzahl an Empfängerclients, die einen bestimmten Videostream angefordert haben, bestimmt. Üblicherweise wird ein H.264- und ein RTVideo-Stream gesendet, wenn ein älterer Client an der Konferenz teilnimmt. Bei einem anderen typischen Szenario werden mehrere H.264-Videostreams (z. B. mit verschiedenen Auflösungen) gesendet, um verschiedenen Empfängeranforderungen gerecht zu werden.

Zusätzlich zu der Bandbreite, die für den RTP-Datenverkehr (Real-Time Transport Protocol) für Audio- und Videomedien erforderlich ist, wird auch Bandbreite für RTCP-Datenverkehr (Real-Time Transport Control Protocol) benötigt. RTCP wird zum Generieren von Statistiken und zur Out-of-Band-Steuerung des RTP-Streams genutzt. Verwenden Sie zur Planung die Bandbreitenangaben in der folgenden Tabelle für RTCP-Datenverkehr. Diese Werte stellen die maximale Bandbreite dar, die für RTCP verwendet wird, und unterscheiden sich aufgrund von Unterschieden bei den Steuerelementdaten für Audio- und Videostreams.

**RTCP-Bandbreite**

|**Medien**|**Maximale RTCP-Bandbreite (KBit/s)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Video (es wird nur H.264 oder RTVideo gesendet/empfangen)  <br/> |10  <br/> |
|Video (H.264 und RTVideo werden gesendet/empfangen)  <br/> |15   <br/> |

Für die Kapazitätsplanung sind die folgenden beiden Statistiken von Interesse:

- **Maximale Bandbreite ohne FEC** Die maximale Bandbreite, die ein Datenstrom verbraucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der im Szenario ohne FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und kein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur auslöst. Dies ist nützlich, um zu berechnen, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann. ES wird nicht erwartet, dass FEC eine Anforderung in einem verwalteten Netzwerk ist.

- **Maximale Bandbreite mit FEC** Die maximale Bandbreite, die ein Datenstrom verbraucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der im Szenario mit FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und ein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur zur Verbesserung der Qualität auslöst. Dies ist nützlich, um zu berechnen, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann, und die Verwendung von FEC, um die Qualität unter Paketverlustbedingungen zu erhalten.

In den folgenden Tabellen ist auch ein zusätzlicher Bandbreitenwert aufgeführt, **die typische Bandbreite**. Dies ist die durchschnittliche Bandbreite, die ein Datenstrom verbraucht. Dazu gehören die typische Aktivität des Datenstroms und der typische Codec, der in dem Szenario verwendet wird. Diese Bandbreite kann verwendet werden, um zu ermitteln, wie viel Bandbreite von Mediendatenverkehr zu einem bestimmten Zeitpunkt verbraucht wird, sollte jedoch nicht für die Kapazitätsplanung verwendet werden, da einzelne Anrufe diesen Wert überschreiten, wenn die Aktivitätsstufe größer als der Durchschnitt ist. Die typische Bandbreite des Videodatenstroms in den folgenden Tabellen basiert auf einer Mischung verschiedener Videoauflösungen, wie in gemessenen Kundendaten beobachtet, und kleinere Installationen weisen wahrscheinlich tatsächliche Zahlen auf, die sich von den Tabellendaten unterscheiden. In Peer-to-Peer-Sitzungen würden die meisten Benutzer beispielsweise das Standardfenster für das Videorendering verwenden, während einige Prozent der Benutzer die Skype for Business Server Anwendung erhöhen oder maximieren würden, um bessere Videoauflösungen zu ermöglichen.

Die folgenden Tabellen enthalten Werte für die verschiedenen Szenarien.

**Planen der Audio/Videokapazität für Peer-zu-Peer-Sitzungen**

|**Medien**|**Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |RTAudio, Breitband  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |SILK Wideband  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Hauptvideo beim Aufrufen von Skype for Business Server Endpunkten  <br/> |H.264  <br/> |460  <br/> |4010 (für eine maximale Auflösung von 1920x1080)  <br/> |Bereits enthalten  <br/> |
|Hauptvideo beim Aufrufen von Lync 2010- oder Office Communicator 2007 R2-Endpunkten  <br/> |RTVideo  <br/> |460  <br/> |2510 (für eine maximale Auflösung von 1280x720)  <br/> |Bereits enthalten  <br/> |
|Panoramavideo beim Aufrufen von Skype for Business Server Endpunkten  <br/> |H.264  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Bereits enthalten  <br/> |
|Panoramavideo beim Aufrufen von Lync 2010-Endpunkten  <br/> |RTVideo  <br/> |190  <br/> |510 (für eine maximale Auflösung von 960x144)  <br/> |Bereits enthalten  <br/> |

**Planen der Audio-/Videokapazität für Konferenzen**

|**Medien**|**Typischer Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Sirene  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Hauptvideo, Empfang  <br/> |H.264 und RTVideo  <br/> |260  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Hauptvideo, Senden  <br/> |H.264 und RTVideo  <br/> |270  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Empfang  <br/> |H.264 und RTVideo  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Senden  <br/> |H.264 und RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Nicht zutreffend  <br/> |

1. RT Video wird zusätzlich zu H.264 gesendet, wenn Lync 2010-Clients mit der Konferenz verbunden sind.

2. Wenn mehrere Datenströme vorhanden sind, teilen sie sich dynamisch die zugewiesene Bandbreite.

Für das Hauptvideo ist die typische Streambandbreite die aggregierte Bandbreite über alle empfangenen Videostreams, und der maximale Datenstrom ist die Bandbreite über alle Sendevideostreams. Selbst bei mehreren Videostreams ist die typische Videobandbreite kleiner als im Peer-to-Peer-Szenario, da viele Videokonferenzen die Inhaltsfreigabe verwenden, was zu viel kleineren Videofenstern und damit zu kleineren Videoauflösungen führt. Die maximal unterstützte aggregierte Bandbreite der Videonutzlast beträgt 8000 KBit/s für sowohl Sende- als auch Empfangsstreams, die verwendet werden würden (z. B. wenn zwei eingehende 1920x1080p-Videostreams vorhanden sind). Höchstwerte werden in tatsächlichen Implementierungen nur selten angezeigt.

Beim Erstellen einer Konferenz mit mehreren Teilnehmern, die das Feature für die Galerieansicht verwendet, erhöht sich die Bandbreitenauslastung zunächst, wenn Teilnehmer beitreten, und nimmt dann ab, wenn Die Auflösungen so eingestellt werden, dass sie das Maximum erreichen.

||**2 Teilnehmer**|**3 Teilnehmer**|**4 Teilnehmer**|**5 Teilnehmer**|**6 Teilnehmer**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Max. empfangene Auflösungen** <br/> |1920 x 1080  <br/> |1280 x 720  <br/> |640 x 360  <br/> |640 x 360 320 x 240  <br/> |640 x 360 320 x 240  <br/> |
|**Durchschnittliche Gesamtbitrate** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Maximale Bitrate insgesamt** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

Die typische Streambandbreite für Panoramavideos basiert auf Geräten, die nur Panoramavideos mit einer Breite von bis zu 960 x 144 streamen. Gehen Sie davon aus, dass die typische Streambandbreite bei Verwendung von Geräten mit 1920 x 288 Panoramavideos zunimmt.

**Planen der Audiokapazität für PSTN**

|**Medien**|**Typischer Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (dies umfasst PSTN-Teilnehmer in Konferenzen)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

Die Angaben zur Netzwerkbandbreite in diesen Tabellen gelten nur für unidirektionalen Datenverkehr und beinhalten 5 KBit/s für RTCP-Overhead pro Stream.

## <a name="managing-quality-of-service"></a>Verwalten der Dienstqualität
<a name="man_QOS"> </a>

Quality of Service (QoS) ist eine Netzwerktechnologie, die in einigen Organisationen verwendet wird, um eine optimale Endbenutzererfahrung für die Audio- und Videokommunikation bereitzustellen. QoS wird am häufigsten in Netzwerken verwendet, in denen die Bandbreite begrenzt ist: Da eine große Anzahl von Netzwerkpaketen um eine relativ geringe verfügbare Bandbreite konkurrieren, ermöglicht QoS Administratoren, Paketen, die Audio- oder Videodaten übertragen, höhere Prioritäten zuzuweisen. Wenn diese Pakete eine höhere Priorität haben, wird die Audio- und Videokommunikation wahrscheinlich schneller und ohne Unterbrechung abgeschlossen als Netzwerksitzungen, bei denen es sich um Dateiübertragungen, Webbrowsen oder Datenbanksicherungen handelt. Die Ursache dafür ist die Zuweisung einer "Best Effort"-Priorität zu den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden.

> [!NOTE]
> QoS gilt in der Regel nur für Kommunikationssitzungen in Ihrem internen Netzwerk. Wenn Sie QoS implementieren, konfigurieren Sie Ihre Server und Router so, dass die Paketmarkierung auf eine bestimmte Weise unterstützt wird, die möglicherweise nicht im Internet oder in anderen Netzwerken unterstützt wird. Auch wenn Quality of Service in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass QoS genau so konfiguriert wird, wie Sie den Dienst konfiguriert haben. Wenn Sie MPLS verwenden, müssen Sie mit Ihrem MPLS-Anbieter zusammenarbeiten.

Skype for Business Server erfordert keine QoS, wird jedoch dringend empfohlen. Wenn Probleme mit Paketverlusten im Netzwerk auftreten, können Sie mit Ihren verfügbaren Lösungen mehr Bandbreite hinzufügen oder QoS implementieren. Wenn das Hinzufügen von mehr Bandbreite nicht möglich ist, ist die Implementierung von QoS möglicherweise ihre einzige Gebühren, um das Problem zu beheben.

Skype for Business Server bietet vollständige Unterstützung für QoS: Das bedeutet, dass Organisationen, die QoS bereits verwenden, Skype for Business Server problemlos in ihre vorhandene Netzwerkinfrastruktur integrieren können. Dazu müssen Sie die folgenden Schritte ausführen:

- [Aktivieren von QoS in Skype for Business Server für Geräte, die nicht auf Windows basieren](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Obwohl Sie Skype for Business Server verwenden können, um Quality of Service für Geräte zu aktivieren und zu deaktivieren, können Sie das Produkt in der Regel nicht verwenden, um die von diesen Geräten verwendeten DSCP-Codes zu ändern.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Mithilfe von Skype for Business Server können Sie QoS nicht aktivieren oder deaktivieren, indem Sie einen Eigenschaftswert auf "True" oder "False" festlegen. Stattdessen aktivieren Sie QoS, indem Sie Portbereiche konfigurieren und dann Gruppenrichtlinien erstellen und anwenden. Wenn Sie später entscheiden, QoS nicht zu verwenden, können Sie QoS "deaktivieren", indem Sie die entsprechenden Gruppenrichtlinienobjekte entfernen.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Edgeserver](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die anderen Server konfigurieren. Das Konfigurieren einer QoS-Richtlinie erfolgt nur für die interne Seite Ihrer Edgeserver. Der Grund dafür ist, dass QoS für die Verwendung in Ihrem internen Netzwerk und nicht im Internet entwickelt wurde.

- [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Diese Portbereiche gelten nur für Clientcomputer und unterscheiden sich in der Regel von den auf Ihren Servern konfigurierten Portbereichen. Beachten Sie, dass Skype for Business Server QoS nicht für andere Windows betriebssysteme als Windows 10 unterstützt.


> [!NOTE]
> Wenn Sie Windows Server 2012 oder Windows Server 2012 R2 verwenden, sind Sie möglicherweise an den neuen Windows PowerShell Cmdlets interessiert, die für die Verwaltung von QoS auf dieser Plattform verfügbar sind. Weitere Informationen finden Sie unter [Windows PowerShell Cmdlets for Networking](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj717268(v=ws.11)).

QoS wird auch im Whitepaper ["Netzwerkplanung, Überwachung und Problembehandlung mit Lync Server" mit](https://www.microsoft.com/download/details.aspx?id=39084) zusätzlichen Details und Tiefe erläutert. Während sich der Inhalt explizit auf Lync 2010 und Lync 2013 bezieht, sind die Überlegungen für Skype for Business Server unverändert.

## <a name="see-also"></a>Siehe auch
<a name="man_QOS"> </a>

[Planen von IPv6 in Skype for Business](ipv6.md)

[Anforderungen an den Lastenausgleich für Skype for Business](load-balancing.md)

[DNS-Anforderungen für Skype for Business Server](dns.md)
