---
title: Planen der Netzwerkanforderungen für Skype for Business
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
ms.openlocfilehash: 709da2ddd60b5b6ee69c22264c159d5d94ab91e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025796"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planen der Netzwerkanforderungen für Skype for Business

**Zusammenfassung:** Überprüfen Sie die folgenden Überlegungen zur Netzwerkkomponente, bevor Sie Skype for Business Server implementieren.

Die Informationen in diesen Themen werden auch im Whitepaper [Netzwerkplanung,-Überwachung und-Problembehandlung mit lync Server](https://www.microsoft.com/download/details.aspx?id=39084) mit zusätzlichen Details und Tiefe erläutert. Während der Inhalt explizit auf lync 2010 und lync 2013 verweist, sind die Überlegungen für Skype for Business Server unverändert.

Wenn Ihr Netzwerk sowohl WLAN als auch drahtgebundenen Zugriff umfasst, ist das Whitepaper, das [lync 2013 Echtzeitkommunikation über WLAN bereit](https://www.microsoft.com/download/details.aspx?id=36494) stellt, eine gute Referenz und gilt gleichermaßen für Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Serverhardware
<a name="S_hard"> </a>

Der Netzwerkadapter jedes Servers in der Skype for Business Server Topologie muss mindestens 1 Gigabit pro Sekunde (Gbit/s) unterstützen. Im Allgemeinen sollten Sie alle Serverrollen innerhalb der Skype for Business Server Topologie mit einer geringen Wartezeit und einer hohen Bandbreite für lokales Netzwerk (Local Area Network, LAN) verbinden. Die Größe des LANs hängt von der Größe der Topologie ab:

- In Standard Edition-Topologien sollten sich die Server in einem Netzwerk befinden, das 1 Gbit/s-Ethernet oder eine gleichwertige unterstützt.

- In Enterprise Edition-Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 Gbit/s unterstützt, vor allem bei der Unterstützung von Audio/Video-Konferenzen und Anwendungsfreigaben (a/V).

Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.

## <a name="audiovideo-network-requirements"></a>Anforderungen für Audio/Video-Netzwerke
<a name="AV_req"> </a>

Die Netzwerkanforderungen für Audio/Video (a/V) in einer Skype for Business Server-Bereitstellung umfassen Folgendes:

- Wenn Sie einen einzelnen Edgeserver oder einen Edgepool mithilfe des DNS-Lastenausgleichs bereitstellen, können Sie die _externe_ Firewall so konfigurieren, dass die Netzwerkadressübersetzung (Network Address Translation, NAT) ausgeführt wird. Sie können die _interne_ Firewall nicht für die Ausführung von NAT konfigurieren. Ausführliche Informationen finden Sie unter [Port and Firewall Planning](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Wenn Sie über eine Edgepool verfügen und einen Hardwaregerät zum Lastenausgleich verwenden, müssen Sie öffentliche IP-Adressen auf den Edgeserver verwenden, und Sie können NAT nicht für die Server oder den Pool an Ihrem NAT-fähigen Gerät verwenden (beispielsweise eine Firewall-Appliance oder einen LAN-Switch). Ausführliche Informationen finden Sie unter [Edgeserver Szenarien in Skype for Business Server](../edge-server-deployments/scenarios.md).

- Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.

- Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden. Ausführliche Informationen finden Sie unter [IPSec Exceptions](#ipsec-exceptions).

Führen Sie die folgenden Schritte aus, um eine optimale Medienqualität bereitzustellen:

- Stellen Sie die Netzwerkverbindungen zur Verfügung, um den Durchsatz von 65 Kbit/s pro Audiostream und 500 KBit/s pro Videostream (sofern aktiviert) während Spitzennutzungszeiten zu unterstützen. Eine bidirektionale Audio-oder Videositzung verwendet zwei Streams, sodass für eine einfache Audio/Telefon-Verbindung 130Kbps erforderlich ist, um jeden Datenstrom abzudecken. Video verwendet ebenfalls die Gesamtzahl von 1000 KBit/s, um eine Upstream-und Downstream-Verbindung zu führen.

- Zur Bewältigung unerwarteter Datenströme und einer erhöhten Nutzung im Laufe der Zeit können sich Skype for Business Server Medien Endpunkte an unterschiedliche Netzwerkbedingungen anpassen und den dreifachen Durchsatz für Audio und Video unterstützen, während dennoch eine akzeptable Qualität gewährleistet ist. Gehen Sie nicht davon aus, dass diese Anpassungsfähigkeit das Problem verschleiert, wenn ein Netzwerk unter bereitgestellt wird. In einem untergeordneten Netzwerk wird die Fähigkeit der Skype for Business Server Medien Endpunkte, dynamische unterschiedliche Netzwerkbedingungen (beispielsweise ein vorübergehender hoher Paketverlust) zu bewältigen, reduziert.

- Für Netzwerkverbindungen, bei denen die proprovisionierung sehr kostspielig und schwierig ist, müssen Sie möglicherweise die propositionierung für einen geringeren Datenverkehr in Frage stellen. In diesem Szenario lassen Sie die Elastizität der Skype for Business Server Medien Endpunkte den Unterschied zwischen dem Datenverkehrsvolumen und der Spitzen Daten verkehrsstufe absorbieren, wobei sich die Sprachqualität verringert. Außerdem gibt es eine Abnahme der Kopffreiheit, die sonst zur Aufnahme plötzlicher Spitzen im Datenverkehr verfügbar ist.

- Bei Links, die kurzfristig nicht ordnungsgemäß bereitgestellt werden können (beispielsweise eine Website mit sehr schlechten WAN-Verbindungen), sollten Sie das Video für bestimmte Benutzer deaktivieren.

- Stellen Sie das Netzwerk zur Gewährleistung einer maximalen End-to-End-Verzögerung (Latenz) von 150 Millisekunden (MS) unter Spitzenlast zur Verfügung. Latenz ist die einzige Netzwerk Schädigung, die Skype for Business Server Medienkomponenten nicht reduzieren können, und es ist wichtig, die Schwachstellen zu finden und zu beseitigen.

- Schließen Sie für Server mit Antivirensoftware alle Server mit Skype for Business Server in der Ausnahmeliste ein, um optimale Leistung und Audioqualität zu gewährleisten.

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
|Vermittlungsserver, eingehend|Any  |Vermittlungsserver (s) |UDP und TCP|Any |Any |Nicht authentifizieren|
|Vermittlungsserver, ausgehend|Vermittlungsserver (s)  |Any|UDP und TCP|Any |Any |Nicht authentifizieren|
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


## <a name="conferencing-network-requirements"></a>Anforderungen an das Konferenz Netzwerk
<a name="Conf_req"> </a>

Die Bandbreite, die zum Herunterladen von Konferenz Inhalten vom Internet Information Services (IIS) Server verwendet wird, hängt von der Größe des Inhalts ab. Sie können wählen, die tatsächliche Nutzung zu überwachen und die Bandbreitenplanung entsprechend anzupassen.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Anforderungen an die Netzwerkbandbreite für den Mediendatenverkehr
<a name="Conf_req"> </a>

Ein wichtiger Bestandteil der Netzwerkplanung besteht darin, sicherzustellen, dass Ihr Netzwerk den von Skype for Business Server generierten Mediendatenverkehr verarbeiten kann. Dieser Abschnitt hilft Ihnen bei der Planung für diesen Mediendatenverkehr.

### <a name="media-traffic-network-usage"></a>Netzwerknutzung im Mediendatenverkehr
<a name="Net_req"> </a>

Aufgrund der Vielzahl an verschiedenen Faktoren, wie z. B. Codecverwendung, Auflösung und Aktivitätsgrad kann es schwierig sein, die Bandbreite für Mediendatenverkehr zu berechnen. Die Bandbreitennutzung ist eine Funktion des verwendeten Codecs und der Aktivität des Streams, die je nach Szenario unterschiedlich sein kann. In der folgenden Tabelle sind die Audiocodecs aufgeführt, die in Skype for Business Server Szenarien normalerweise verwendet werden.

**Audiocodec-Bandbreite**

|**Audio-Codec**|**Szenario**|**Bitrate für Audio-Nutzlast (Kbit/s)**|**Bandbreite für Audionutzlast und IP-Header (KBit/s)**|**Bandbreite für Audionutzlast, IP-Header, UDP, RTP und SRTP (KBit/s)**|**Bandbreite für Audionutzlast, IP-Header, UDP, RTP, SRTP und Vorwärtsfehlerkorrektur (KBit/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio, Breitband  <br/> |Peer-to-Peer  <br/> |29,0  <br/> |45,0  <br/> |57,0  <br/> |86,0  <br/> |
|RTAudio, Schmalband  <br/> |Peer-to-Peer-PSTN  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G. 722  <br/> |Konferenzen  <br/> |64,0  <br/> |80,0  <br/> |95,6  <br/> |159,6  <br/> |
|G.722, Stereo  <br/> |Peer-zu-Peer-Konferenzen  <br/> |128,0  <br/> |144,0  <br/> |159,6  <br/> |223,6  <br/> |
|G. 711  <br/> |PSTN, Konferenzen  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156,0  <br/> |
|Sirene  <br/> |Konferenzen  <br/> |16,0  <br/> |32,0  <br/> |47,6  <br/> |63,6  <br/> |
|Seiden Breitband  <br/> |Peer-to-Peer  <br/> |36,0  <br/> |52,0  <br/> |64,0  <br/> |100,0  <br/> |
|Seiden Breitband  <br/> |Peer-to-Peer  <br/> |26,0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|Seiden Breitband  <br/> |Peer-to-Peer  <br/> |20,0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|Silk Wideband/Schmalband  <br/> |Peer-to-Peer  <br/> |13,0  <br/> |29,0  <br/> |41,0  <br/> |54,0  <br/> |

> [!NOTE]
> Für PSTN-Anrufe vom Skype for Business-Client wird normalerweise der G. 711-Codec verwendet, der eine hohe Bandbreite erfordert. Wenn für diesen Codec genügend Bandbreite nicht verfügbar ist, können Aufrufe mit einem Fehler auftreten, der in den Medien Protokollen dem folgenden ähnelt: **mindestens ein Codec muss aktiviert sein, HR: c0042004**. Medienprotokolle (Blogdateien) sind verschlüsselt und können nur von Microsoft-Supportmitarbeitern decodiert werden.

Die Bandbreiten Nummern in der vorherigen Tabelle basieren auf der 20ms-Paketerstellung (50-Pakete pro Sekunde) und für die Siren-und G. 722-Codecs, die den zusätzlichen Secure Real-Time Transport Protocol (SRTP)-Overhead aus Konferenzszenarien umfassen und davon ausgehen, dass der Datenstrom 100% aktiv. Die Forward Error Correction (FEC) wird dynamisch verwendet, wenn es auf dem Link einen Paketverlust gibt, um die Qualität des Audiostreams zu verbes-halten.

Die Stereo Version des G. 722-Codecs wird von Systemen verwendet, die auf dem lync-Raum System basieren, das ein einzelnes Stereo-Mikrofon oder ein paar Mono-Mikrofone verwendet, um es den Hörern zu ermöglichen, mehrere Lautsprecher im Besprechungsraum besser zu unterscheiden.

**Bandbreite für Videoauflösung**

|**Videocodec**|**Auflösung und Seitenverhältnis**|**Maximale Bitrate für Video Nutzlast (Kbit/s)**|**Minimale Bitrate für Video Nutzlast (Kbit/s)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H. 264/RTVideo  <br/> |424 x 240 (16:9)  <br/> 320X240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H. 264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H. 264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H. 264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H. 264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H. 264/RTVideo  <br/> |1280X720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H. 264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H. 264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H. 264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H. 264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Der Standard Codec für Video ist der Standard für H. 264/MPEG-4 Part 10 Advanced Video Coding, zusammen mit den skalierbaren Video Codierungs Erweiterungen für die zeitliche Skalierbarkeit. Um die Interoperabilität mit älteren Clients aufrechtzuerhalten, wird der RTVideo-Codec weiterhin für Peer-to-Peer-Anrufe zwischen Skype for Business Server-und Legacyclients verwendet. In Konferenzsitzungen mit Skype for Business Server-und Legacyclients kann der Skype for Business Server-Endpunkt das Video mit beiden Videocodecs codieren und die H. 264 Bitstream an die Skype for Business Server Clients und die RTVideo Bitstream an Legacy senden. Clients.

Die erforderliche Bandbreite hängt von der Auflösung, der Qualität, der Framerate und dem Umfang der Bewegung oder Änderung im Bild ab. Für jede Lösung gibt es zwei relevante Bitraten:

- **Maximale Nutzlast-Bitrate** Dies ist die Bitrate, die ein Endpunkt für die Auflösung mit der maximalen Frame-Rate verwendet. Dies ist der Wert, der die höchste Video-und Soundqualität ermöglicht.

- **Bitrate für minimale Nutzlast** Hierbei handelt es sich um die Bitrate, unter der ein Skype for Business Server-Endpunkt zur nächst niedrigeren Auflösung wechseln wird. Um eine bestimmte Auflösung sicherzustellen, darf die verfügbare Video Nutzlast-Bitrate nicht unter diese Mindestrate für diese Auflösung fallen. Dieser Wert hilft Ihnen, den niedrigsten Wert zu verstehen, der möglich ist, wenn die maximale Bitrate nicht verfügbar oder praktisch ist. Für einige Benutzer kann ein solches Video mit niedriger Bitrate eine unannehmbare Videowiedergabe bieten, also Vorsicht bei diesen minimalen Video Nutzlast-Bitraten verwenden. Beachten Sie, dass bei statischen, unveränderlichen Videoszenen die tatsächliche Bitrate vorübergehend unter die minimale Bitrate fallen kann.

Skype for Business Server unterstützt viele Auflösungen. Auf diese Weise können Skype for Business Server an unterschiedliche Netzwerkbandbreiten und empfangende Clientfunktionen anpassen. Das standardmäßige Seitenverhältnis für Skype for Business Server ist 16:9. Das Legacy 4:3-Seitenverhältnis wird weiterhin für Webcams unterstützt, die keine Erfassung im 16:9-Seitenverhältnis zulassen.

Video-FEC ist immer in der Video Nutzlast-Bitrate enthalten, wenn es verwendet wird, sodass es keine separaten Werte für mit Video FEC und ohne Video FEC gibt.

Endpunkte übertragen Audio- oder Videopakete nicht in einem kontinuierlichen Stream. Für jedes Szenario gibt es unterschiedliche Aktivitätsebenen, die angeben, wie häufig Pakete für einen Stream gesendet werden. Die Aktivität eines Streams richtet sich nach dem Medium und dem Szenario, nicht jedoch nach dem verwendeten Codec. In einem Peer-zu-Peer-Szenario gilt Folgendes:

- Endpunkte senden nur Audiostreams, wenn die Benutzer sprechen.

- Beide Teilnehmer empfangen Audiostreams.

- Wenn Video verwendet wird, senden und empfangen beide Endpunkte während des Anrufs Videodatenströme.

- Bei statischen Videoszenen kann die tatsächliche Bitrate vorübergehend sehr niedrig sein, da der Video Codec Codierungs Bereiche des Videos ohne Änderung seit dem vorherigen Beispiel überspringt.

In einem Konferenzszenario gilt Folgendes:

- Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.

- Alle Teilnehmer empfangen Audiostreams.

- Wenn Video verwendet wird, können alle Teilnehmer bis zu fünf empfangen Videodatenströme und ein Panorama (beispielsweise Seitenverhältnis 20:3) Videostream empfangen. Die fünf empfangenen Videostreams basieren standardmäßig auf dem aktiven Sprecher Verlauf, Benutzer können aber auch manuell die Teilnehmer auswählen, aus denen Sie einen Videostream erhalten möchten. Wenn Multi-Video aktiviert ist, sind die Anforderungen an Auflösung und Bandbreite für jeden Videostream niedriger.

- Jeder Teilnehmer, der den Sende Videodatenstrom des Benutzers aktiviert, sendet einen oder mehrere Videostreams. Skype for Business Server bietet die Möglichkeit, bis zu fünf Videostreams zu senden, um die Videoqualität für alle empfangenden Clients zu optimieren. Die tatsächliche Anzahl an gesendeten Videostreams wird vom Sender basierend auf CPU-Leistung, verfügbarer Uplink-Bandbreite und der Anzahl an Empfängerclients, die einen bestimmten Videostream angefordert haben, bestimmt. Üblicherweise wird ein H.264- und ein RTVideo-Stream gesendet, wenn ein älterer Client an der Konferenz teilnimmt. Bei einem anderen typischen Szenario werden mehrere H.264-Videostreams (z. B. mit verschiedenen Auflösungen) gesendet, um verschiedenen Empfängeranforderungen gerecht zu werden.

Zusätzlich zu der Bandbreite, die für den RTP-Datenverkehr (Real-Time Transport Protocol) für Audio- und Videomedien erforderlich ist, wird auch Bandbreite für RTCP-Datenverkehr (Real-Time Transport Control Protocol) benötigt. RTCP wird zum Generieren von Statistiken und zur Out-of-Band-Steuerung des RTP-Streams genutzt. Verwenden Sie zur Planung die Bandbreitenangaben in der folgenden Tabelle für RTCP-Datenverkehr. Diese Werte stellen die maximale Bandbreite dar, die für RTCP verwendet wird, und unterscheiden sich aufgrund von Unterschieden in den Steuerdaten für Audio-und Videodatenströme

**RTCP-Bandbreite**

|**Medien**|**Maximale RTCP-Bandbreite (KBit/s)**|
|:-----|:-----|
|Audio  <br/> |5   <br/> |
|Video (es wird nur H.264 oder RTVideo gesendet/empfangen)  <br/> |10   <br/> |
|Video (H.264 und RTVideo werden gesendet/empfangen)  <br/> |15   <br/> |

Für die Kapazitätsplanung sind die folgenden beiden Statistiken von Interesse:

- **Maximale Bandbreite ohne FEC** Die maximale Bandbreite, die ein Datenstrom verwendet wird. Dies umfasst die typische Aktivität des Streams und den typischen Codec, der im Szenario ohne FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und kein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur auslöst. Dies ist hilfreich, um zu berechnen, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann. FEC wird in einem verwalteten Netzwerk nicht voraussichtlich vorausgesetzt.

- **Maximale Bandbreite mit FEC** Die maximale Bandbreite, die ein Datenstrom benötigt. Dies umfasst die typische Aktivität des Streams und den typischen Codec, der im Szenario mit FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und ein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur zur Verbesserung der Qualität auslöst. Dies ist hilfreich, um zu berechnen, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann, und die Verwendung von FEC zur Beibehaltung der Qualität unter Paketverlust Bedingungen zu ermöglichen.

Die folgende Tabelle listet auch einen zusätzlichen Bandbreitenwert, **typische Bandbreite**. Dies ist die durchschnittliche Bandbreite, die ein Datenstrom benötigt. Dies umfasst die typische Aktivität des Streams und den typischen Codec, der in dem Szenario verwendet wird. Diese Bandbreite kann verwendet werden, um zu bestimmen, wie viel Bandbreite zu einem bestimmten Zeitpunkt vom Mediendatenverkehr beansprucht wird, sollte jedoch nicht für die Kapazitätsplanung verwendet werden, da einzelne Anrufe diesen Wert überschreiten, wenn die Aktivitätsebene größer als der Durchschnitt ist. Die typische Bandbreite der Videodatenströme in den folgenden Tabellen basiert auf einer Mischung aus unterschiedlichen Videoauflösungen, die in gemessenen Kundendaten beobachtet werden, und bei kleineren Installationen sind wahrscheinlich tatsächliche Zahlen enthalten, die sich von den Tabellendaten unterscheiden. In Peer-to-Peer-Sitzungen würden die meisten Benutzer beispielsweise das standardmäßige Video Renderfenster verwenden, während ein Teil der Benutzer die Skype for Business Server Anwendung erhöht oder maximiert, um bessere Videoauflösungen zu ermöglichen.

Die folgenden Tabellen enthalten Werte für die verschiedenen Szenarien.

**Planen der Audio/Videokapazität für Peer-zu-Peer-Sitzungen**

|**Medien**|**Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |RTAudio, Breitband  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |Seiden Breitband  <br/> |44,3  <br/> |69  <br/> |105  <br/> |
|Hauptvideo beim Aufruf Skype for Business Server Endpunkten  <br/> |H. 264  <br/> |460  <br/> |4010 (für eine maximale Auflösung von 1920x1080)  <br/> |Bereits enthalten  <br/> |
|Hauptvideo beim Aufruf von lync 2010 oder Office Communicator 2007 R2 Endpunkten  <br/> |RTVideo  <br/> |460  <br/> |2510 (für eine maximale Auflösung von 1280x720)  <br/> |Bereits enthalten  <br/> |
|Panorama Video beim Aufruf Skype for Business Server Endpunkten  <br/> |H. 264  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Bereits enthalten  <br/> |
|Panorama Video beim Aufruf lync 2010 Endpunkten  <br/> |RTVideo  <br/> |190  <br/> |510 (für eine maximale Auflösung von 960x144)  <br/> |Bereits enthalten  <br/> |

**Planen der Audio-/Videokapazität für Konferenzen**

|**Medien**|**Typischer Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 722  <br/> |46,1  <br/> |100,6  <br/> |164,6  <br/> |
|Audio  <br/> |Sirene  <br/> |25,5  <br/> |52,6  <br/> |68,6  <br/> |
|Hauptvideo, Empfang  <br/> |H. 264 und RTVideo ¹  <br/> |260  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Hauptvideo, Senden  <br/> |H. 264 und RTVideo  <br/> |270  <br/> |8015  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Empfang  <br/> |H. 264 und RTVideo  <br/> |190  <br/> |2010 (für eine maximale Auflösung von 1920x288)  <br/> |Nicht zutreffend  <br/> |
|Panoramavideo, Senden  <br/> |H. 264 und RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Nicht zutreffend  <br/> |

1. RT-Video wird zusätzlich zu H. 264 gesendet, wenn lync 2010 Clients mit der Konferenz verbunden sind.

2. Wenn mehrere Streams vorhanden sind, wird die zugewiesene Bandbreite dynamisch freigegeben.

Für das Hauptvideo ist die typische Datenstrom Bandbreite die aggregierte Bandbreite über alle empfangenen Videostreams und der maximale Datenstrom die Bandbreite über alle Sende Videodatenströme. Selbst bei mehreren Videostreams ist die typische Videobandbreite kleiner als im Peer-to-Peer-Szenario, da viele Videokonferenzen die Inhaltsfreigabe verwenden, was zu wesentlich kleineren Videofenstern und somit kleineren Videoauflösungen führt. Die maximale Bandbreite unterstützter aggregierter Video Nutzlast beträgt 8000 kBit/s für Sende-und Empfangsdaten Ströme, die verwendet werden würden (beispielsweise, wenn zwei eingehende 1920x1080p-Videostreams vorhanden sind). Maximalwerte werden nur selten in tatsächlichen Implementierungen angezeigt.

Beim Erstellen einer Konferenz mit mehreren Teilnehmern, in der das Feature "Galerieansicht" verwendet wird, nimmt die Bandbreitenauslastung anfänglich zu, wenn die Teilnehmer beitreten, und dann sinkt die Auflösung, wenn die Auflösungen in den Maximalwert passen.

||**2 Teilnehmer**|**3 Teilnehmer**|**4 Teilnehmer**|**5 Teilnehmer**|**6 Teilnehmer**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Empfangene maximale Auflösungen** <br/> |1920x1080  <br/> |1280X720  <br/> |640 x 360  <br/> |640 x 360 320X240  <br/> |640 x 360 320X240  <br/> |
|**Durchschnittliche Bitrate insgesamt** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Maximale Bitrate insgesamt** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

Die typische Stream-Bandbreite für Panorama Video basiert auf Geräten, die nur bis zu 960x144 Panorama Video streamen. Bei Verwendung von Geräten mit 1920x288-Panorama Video wird die typische Datenstrom Bandbreite erhöht.

**Planen der Audiokapazität für PSTN**

|**Medien**|**Typischer Codec**|**Typische Streambandbreite (KBit/s)**|**Maximale Streambandbreite ohne FEC**|**Maximale Streambandbreite mit FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (Dies umfasst PSTN-Teilnehmer an Konferenzen)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |RTAudio, Schmalband  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |

Die Angaben zur Netzwerkbandbreite in diesen Tabellen gelten nur für unidirektionalen Datenverkehr und beinhalten 5 KBit/s für RTCP-Overhead pro Stream.

## <a name="managing-quality-of-service"></a>Verwalten der Dienstqualität
<a name="man_QOS"> </a>

Quality of Service (QoS) ist eine Netzwerktechnologie, die in einigen Organisationen verwendet wird, um eine optimale Benutzeroberfläche für die Audio-und Videokommunikation bereitzustellen. QoS wird am häufigsten in Netzwerken verwendet, in denen die Bandbreite beschränkt ist: bei einer großen Anzahl von Netzwerkpaketen, die um eine relativ kleine Menge an verfügbarer Bandbreite konkurrieren, ermöglicht QoS Administratoren das Zuweisen höherer Prioritäten zu Paketen, die Audio-oder Videodaten übertragen. Wenn Sie diesen Paketen eine höhere Priorität geben, werden die Audio-und Videokommunikation wahrscheinlich schneller und mit weniger Unterbrechung abgeschlossen als Netzwerksitzungen mit Dingen wie Dateiübertragungen, Webbrowsing oder Datenbanksicherungen. Die Ursache dafür ist die Zuweisung einer "Best Effort"-Priorität zu den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden.

> [!NOTE]
> QoS gilt in der Regel nur für Kommunikationssitzungen in Ihrem internen Netzwerk. Wenn Sie QoS implementieren, konfigurieren Sie die Server und Router so, dass die Paketmarkierung auf eine bestimmte Art und Weise unterstützt wird, die möglicherweise nicht im Internet oder in anderen Netzwerken unterstützt wird. Selbst wenn die Dienstqualität in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass QoS genau auf die gleiche Weise konfiguriert wird, wie Sie den Dienst konfiguriert haben. Wenn Sie MPLS verwenden, müssen Sie mit Ihrem MPLS-Anbieter zusammenarbeiten.

Skype for Business Server erfordert keine QoS, wird jedoch dringend empfohlen. Wenn Probleme mit dem Paketverlust im Netzwerk auftreten, müssen ihre verfügbaren Lösungen mehr Bandbreite hinzufügen oder QoS implementieren. Wenn das Hinzufügen weiterer Bandbreite nicht möglich ist, ist die Implementierung von QoS möglicherweise die einzige Maut, um das Problem zu beheben.

Skype for Business Server bietet vollständige Unterstützung für QoS: Das bedeutet, dass Organisationen, die bereits QoS verwenden, problemlos Skype for Business Server in Ihre vorhandene Netzwerkinfrastruktur integrieren können. Hierzu müssen Sie die folgenden Schritte ausführen:

- [Aktivieren von QoS in Skype for Business Server für Geräte, die nicht auf Windows basieren](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Obwohl Sie Skype for Business Server zum Aktivieren und Deaktivieren der Dienstqualität für Geräte verwenden können, können Sie das Produkt in der Regel nicht zum Ändern der von diesen Geräten verwendeten DSCP-Codes verwenden.

- [Konfigurieren von Portbereichen und einer Dienst Qualitätsrichtlinie für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Mithilfe Skype for Business Server Sie QoS nicht aktivieren oder deaktivieren, indem Sie einen Eigenschaftswert auf "true" oder "false" festlegen. Stattdessen aktivieren Sie QoS durch Konfigurieren von Portbereichen und anschließendes Erstellen und Anwenden von Gruppenrichtlinien. Wenn Sie später beschließen, QoS nicht zu verwenden, können Sie QoS durch Entfernen der entsprechenden Gruppenrichtlinienobjekte deaktivieren.

- [Konfigurieren von Portbereichen und einer Dienst Qualitätsrichtlinie für Ihre Edgeserver](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die anderen Server konfigurieren. Das Konfigurieren einer QoS-Richtlinie erfolgt nur für die interne Seite Ihrer Edgeserver. Das liegt daran, dass QoS für die Verwendung in Ihrem internen Netzwerk und nicht im Internet entwickelt wurde.

- [Konfigurieren von Portbereichen und einer Dienst Qualitätsrichtlinie für Ihre Clients in Skype for Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Diese Portbereiche gelten nur für Clientcomputer und unterscheiden sich in der Regel von den auf Ihren Servern konfigurierten Portbereichen. Beachten Sie, dass Skype for Business Server QoS für andere Windows-Betriebssysteme als Windows 10 nicht unterstützt.


> [!NOTE]
> Wenn Sie Windows Server 2012 oder Windows Server 2012 R2 verwenden, interessieren Sie sich möglicherweise für die neuen Windows PowerShell-Cmdlets, die für die Verwaltung von QoS auf dieser Plattform zur Verfügung stehen. Weitere Informationen finden Sie unter [Network QoS Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

QoS wird auch im Whitepaper [Netzwerkplanung,-Überwachung und-Problembehandlung mit lync Server](https://www.microsoft.com/download/details.aspx?id=39084) mit zusätzlichen Details und Tiefe erläutert. Während der Inhalt explizit auf lync 2010 und lync 2013 verweist, sind die Überlegungen für Skype for Business Server unverändert.

## <a name="see-also"></a>Siehe auch
<a name="man_QOS"> </a>

[Planen von IPv6 in Skype for Business](ipv6.md)

[Lastenausgleichsanforderungen für Skype for Business](load-balancing.md)

[DNS-Anforderungen für Skype for Business Server](dns.md)
