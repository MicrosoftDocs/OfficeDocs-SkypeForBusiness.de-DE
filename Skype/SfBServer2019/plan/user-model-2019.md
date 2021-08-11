---
title: Kapazitätsplanung für Skype for Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: Die Themen in diesem Abschnitt helfen Ihnen zu verstehen, wie Sie Skype for Business Server planen und bereitstellen, damit Sie die Anzahl der Benutzer in Ihrer Organisation angemessen planen und die Serverlast planen können, die ihre Aktivitäten generieren.
ms.openlocfilehash: aaa34d4ec935735215da36d888ab3c5155f158b89fd366546eac14b3f6259482
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277640"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Kapazitätsplanung für Skype for Business Server 2019

Dieser Artikel enthält Anleitungen dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, gemäß der verwendung, die in [Benutzermodellen in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>Getestete Hardwareplattform

Wir haben unsere Leistungstests auf der in der folgenden Tabelle beschriebenen Hardware durchgeführt. Alle unsere Empfehlungen und Ergebnisse basieren auf dieser Hardware. Wenn Sie versuchen möchten, weniger leistungsfähige Hardware als die hier aufgeführten zu verwenden, beachten Sie bitte, dass Sie möglicherweise mit Funktionalitätsproblemen oder einer schlechten Leistung konfrontiert sind.

**Bei Leistungstests verwendete Hardware**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 GHz oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |Entweder:  <br/> • 8 oder mehr Festplattenlaufwerke mit 10.000 U/min mit mindestens 72 GB freiem Speicherplatz (zwei der Festplatten mit RAID 1 und 6 mit RAID 10).  <br/> ODER  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 1.0000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse zusammengeführt werden).  <br/> Dual- oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server und Standard Edition Server **nicht** unterstützt. <br/> Solange sie nicht für das Betriebssystem verfügbar gemacht werden und zum Überwachen und Verwalten der Serverhardware verwendet werden, können Sie über Out-of-Band-Verwaltungssysteme wie DRAC oder GIF verfügen. Dieses Szenario stellt keinen Server mit mehreren Verwalteten dar und wird unterstützt.  <br/> |

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

In der folgenden Tabelle sind unsere Empfehlungen zusammengefasst.

|**Serverrolle**|**Maximale Anzahl von unterstützten Benutzern**|
|:-----|:-----|
|Front-End-Pool mit 16 Front-End-Servern und Back-End-Servern oder einem Back-End-Serverpaar mit SQL AlwaysOn für hohe Verfügbarkeit.  <br/> |106.000 eindeutige Benutzer gleichzeitig angemeldet, plus 50 % mehrfache Anwesenheitspunkte (Multiple Points of Presence, MPOP), die nicht mobile Instanzen darstellen, plus 40 % der Benutzer, die für Mobilität für insgesamt 210.000 Endpunkte aktiviert sind.  <br/> |
|A/V-Konferenzen  <br/> |Der von einem Front-End-Pool bereitgestellte A/V-Konferenzdienst unterstützt die Konferenzen des Pools mit einer maximalen Konferenzgröße von 250 Benutzern und jeweils nur einer derart großen Konferenzen.  <br/> **Hinweis:** Darüber hinaus können Sie große Konferenzen mit 250 bis 1.000 Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern zum Hosten der großen Konferenzen bereitstellen. Ausführliche Informationen finden Sie unter [Plan for large meetings in Skype for Business Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md). <br/> |
|Ein Edgeserver  <br/> |18.000 gleichzeitige Remotebenutzer.  <br/> |
|Ein Director  <br/> |18.000 gleichzeitige Remotebenutzer.  <br/> |
|Überwachen und Archivieren  <br/> |Die Front-End-Dienste für die Überwachung und Archivierung werden auf jedem Front-End-Server und nicht auf separaten Serverrollen ausgeführt.  <br/> Für die Überwachung und Archivierung sind weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie auch Exchange 2013 oder höher ausführen, können Sie Ihre Archivierungsdaten in Exchange und nicht in einer dedizierten SQL-Datenbank speichern.  <br/> |
|Ein Vermittlungsserver  <br/> |Der Vermittlungsserver, der mit dem Front-End-Server verbunden ist, wird auf jedem Front-End-Server in einem Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen. Informationen zum eigenständigen Vermittlungsserver finden Sie im Abschnitt "Vermittlungsserver" weiter unten in diesem Thema.  <br/> |
|Ein Standard Edition-Server  <br/> |Es wird dringend empfohlen, wenn Sie Standard Edition Server zum Hosten von Benutzern verwenden, immer zwei Server verwenden, gepaart mit den Empfehlungen in [der Planung für hohe Verfügbarkeit und Notfallwiederherstellung.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery) Jeder Server im Paar kann bis zu 2.500 Benutzer hosten, und wenn ein Server ausfällt, kann der verbleibende Server 5.000 Benutzer in einem Failoverszenario unterstützen.  <br/>  Wenn Ihre Bereitstellung einen erheblichen Anteil an Audio- oder Videodatenverkehr umfasst, kann die Serverleistung mit mehr als 2.500 Benutzern pro Server beeinträchtigt werden. In diesem Fall sollten Sie weitere Standard Edition Server hinzufügen oder zu Skype for Business Server Enterprise Edition wechseln. <br/> |

## <a name="front-end-server"></a>Front-End-Server

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

In einem Front-End-Pool sollten Sie einen Front-End-Server für alle 6.660 Benutzer haben, die in Ihrem Pool verwaltet werden, vorausgesetzt, dass Hyperthreading auf allen Servern im Pool aktiviert ist, dass Sie SQL Server Express Edition verwenden und dass die Serverhardware die Empfehlungen in den [Serveranforderungen für Skype for Business Server 2019](system-requirements.md)erfüllt. Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 106.000. Dabei wird erneut vorausgesetzt, dass Hyperthreading aktiviert ist und SQL Server Express Edition auf allen Servern in Ihrem Pool verwendet wird. Wenn Sie mehr als 106.000 Benutzer an einem Standort haben, können Sie mehr als einen Front-End-Pool bereitstellen.

Wenn Sie die Anzahl der Benutzer in einem Front-End-Pool berücksichtigen, schließen Sie alle Benutzer ein, die in Survivable Branch Appliances und Survivable Branch-Servern in Zweigstellen verwaltet werden, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. In einem Szenario mit 30.000 Benutzern und fünf Front-End-Servern müssen die Verbindungen von 6.000 Ihrer Benutzer auf die anderen vier verbleibenden Server übertragen werden, wenn ein Server nicht verfügbar ist. Diese vier verbleibenden Server haben dann jeweils 7.500 Benutzer. Dies ist eine größere Anzahl als empfohlen.

Wenn Sie stattdessen mit sechs Front-End-Servern für Ihre 30.000 Benutzer begonnen haben und einer nicht mehr verfügbar ist, müssen insgesamt 5.000 Benutzer zu den verbleibenden fünf Servern wechseln. Diese fünf verbleibenden Server hosten dann jeweils 6.000 Benutzer, was im empfohlenen Bereich liegt.

Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 106.000. Die maximale Anzahl von Front-End-Servern in einem Pool beträgt 16.

Bei einem Front-End-Pool mit 80.000 Benutzern sind 16 Front-End-Server in typischen Bereitstellungen, die den [Benutzermodellen in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)folgen, für die Leistung geeignet. Bei Bereitstellungen zur Unterstützung des Failovers für die Notfallwiederherstellung wird davon ausgegangen, dass maximal 53.000 Benutzer in jedem von zwei front-End-Paarpools gehostet werden können, in denen jeder Pool über genügend Front-End-Server verfügt, um die Benutzer in beiden Pools zu enthalten, falls ein Pool zu einem anderen Pool übergegangen werden muss.

Die Anzahl der Benutzer, die von einem bestimmten Front-End-Pool mit einer guten Leistung unterstützt werden, kann aus den folgenden Gründen von diesen Zahlen abweichen:

- Die Hardware für Ihre Front-End-Server entspricht nicht den Empfehlungen.
- Anstatt SQL Server Express Edition zu verwenden, verwenden Sie eine andere SQL Server Edition. Möglicherweise können Sie weitere Benutzer in jedem Front-End-Pool hosten.
- Die Nutzung Ihrer Organisation unterscheidet sich stark von den Benutzermodellen, z. B. wenn Sie viel mehr Konferenzdatenverkehr haben.

Die folgende Tabelle zeigt die durchschnittliche Bandbreite für Chatnachrichten und Anwesenheitsinformationen, wenn das Benutzermodell in [Benutzermodellen in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)definiert ist.

|**Durchschnittliche Bandbreite pro Benutzer**|**Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern**|
|:-----|:-----|
|3-3,75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> Um die Medienleistung der gemeinsam installierten A/V-Konferenz- und Vermittlungsserverfunktionen auf Ihren Front-End-Servern zu verbessern, sollten Sie RSS (Receive-Side Scaling) auf den Netzwerkadaptern auf Ihren Front-End-Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter [RSS (Receive Side Scaling) in der Dokumentation Windows Server 2012.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Angesichts des Benutzermodells, dass sich 5 % der Benutzer in einem Pool zu einem beliebigen Zeitpunkt in einer Konferenz befinden können, könnten in einem Pool von 106.000 Benutzern etwa 5.300 Benutzer gleichzeitig an Konferenzen teilnehmen. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z.B. nur Sofortnachrichten, Sofortnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine feste Grenze für die tatsächliche Anzahl der zulässigen Konferenzen, und die tatsächliche Nutzung bestimmt die tatsächliche Leistung. Wenn Ihre Organisation beispielsweise viel mehr Konferenzen im gemischten Modus hat, als im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server oder A/V-Konferenzserver bereitstellen als die empfehlungen in diesem Artikel. Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

Die maximal unterstützte Konferenzgröße, die von einem regulären Skype for Business Server Front-End-Pool gehostet wird, in dem auch Benutzer gehostet werden, beträgt 250 Teilnehmer. Während eine Konferenz mit 250 Benutzern stattfindet, unterstützt der Pool auch andere Konferenzen, sodass sich insgesamt 5 % der Poolbenutzer an gleichzeitigen Konferenzen befinden. In einem Pool mit 16 Front-End-Servern und 106.000 Benutzern, während die Konferenz mit 250 Benutzern stattfindet, unterstützt Skype for Business Server 5.050 andere Benutzer, die an kleineren Konferenzen teilnehmen.

Unabhängig von der Anzahl der Benutzer, die im Front-End-Pool oder Standard Edition Server verwaltet werden, unterstützt Skype for Business Server mindestens 125 andere Benutzer, die an kleineren Konferenzen im selben Pool oder Server teilnehmen, auf dem eine Konferenz mit 250 Benutzern gehostet wird.

Um Konferenzen mit 250 bis 1.000 Benutzern zu aktivieren, können Sie einen separaten Front-End-Pool einrichten, nur um diese Konferenzen zu hosten. In diesem Front-End-Pool werden keine Benutzer gehostet. Ausführliche Informationen finden Sie unter [Planen großer Besprechungen in Skype for Business Server.](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)

Wenn Ihre Organisation viel mehr Konferenzen im gemischten Modus als im Benutzermodell angenommen hat, müssen Sie möglicherweise mehr Front-End-Server bereitstellen, als in diesem Dokument empfohlen wird (bis zu einem Grenzwert von 16 Front-End-Servern). Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

## <a name="edge-server"></a>Edgeserver

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Sie sollten einen Edgeserver für alle 18.000 Remotebenutzer bereitstellen, die gleichzeitig auf einen Standort zugreifen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Edgeservern empfohlen. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver den Empfehlungen auf [Serverhardwareplattformen entspricht.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Wenn Sie die Anzahl von Benutzern für die Edgeserver berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

> [!NOTE]
> Zum Verbessern der Leistung des A/V-Konferenzedgediensts auf Ihren Edgeservern sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter Ihrer Edgeserver aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie [unter RSS (Receive Side Scaling) in Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)). Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="director"></a>Director

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie die Director-Serverrolle bereitstellen, wird empfohlen, einen Director für alle 18.000 Remotebenutzer bereitzustellen, die gleichzeitig auf eine Website zugreifen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Directors empfohlen. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver den Empfehlungen auf [Serverhardwareplattformen entspricht.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Wenn Sie die Anzahl von Benutzern für die Director-Server berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

## <a name="mediation-server"></a>Vermittlungsserver

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie den Vermittlungsserver mit dem Front-End-Server verbinden, wird der Vermittlungsserver auf jedem Front-End-Server im Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen Vermittlungsserverpool bereitstellen, hängt die Anzahl der bereitzustellenden Vermittlungsserver von vielen Faktoren ab, einschließlich der für den Vermittlungsserver verwendeten Hardware, der Anzahl der voIP-Benutzer, die Sie haben, der Anzahl der Gatewaypeers, die jeder Vermittlungsserverpool steuert, des Datenverkehrs zur Nutzungsstunde über diese Gateways und des Prozentsatzes der Anrufe mit Medien, die den Vermittlungsserver umgehen.

Die folgenden Tabellen enthalten eine Richtlinie für die Anzahl gleichzeitiger Anrufe, die ein Vermittlungsserver verarbeiten kann, vorausgesetzt, dass die Hardware für die Vermittlungsserver die Anforderungen in [Serverhardwareplattformen](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) erfüllt und Hyperthreading aktiviert ist. Ausführliche Informationen zur Skalierbarkeit des Vermittlungsservers finden Sie unter ["Bewerten der VoIP-Nutzung und](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) des Datenverkehrs für Skype for Business Server und [Bereitstellungsrichtlinien für den Vermittlungsserver in Skype for Business Server."](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md)

In allen folgenden Tabellen wird davon ausgegangen, dass die Verwendung in [Benutzermodellen in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)zusammengefasst ist.

**Kapazität des eigenständigen Vermittlungsservers: 70 % interne Benutzer, 30 % externe Benutzer mit Anrufkapazität ohne Umgehung (Medientranscodierung durch vermittlungsserver)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|**Maximale Anzahl von T1-Leitungen**|**Maximale Anzahl von E1-Leitungen**|
|:-----|:-----|:-----|:-----|
|Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 GHz oder höher **mit deaktivierter Hyperthreading,mit** 64 GB Arbeitsspeicher und einer Dualport-Netzwerkadapterkarte.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 GHz oder höher, mit 64 GB Arbeitsspeicher und einer Dualport-Netzwerkadapterkarte.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Obwohl Server mit 64 GB Arbeitsspeicher für Leistungstests verwendet wurden, werden Server mit 32 GB Arbeitsspeicher für einen eigenständigen Vermittlungsserver unterstützt und sind ausreichend, um die in dieser Tabelle dargestellte Leistung bereitzustellen.

**Vermittlungsserverkapazität (Vermittlungsserver mit Front-End-Server verbunden) 70 % interne Benutzer, 30 % externe Benutzer, Anrufkapazität ohne Umgehung (Vom Vermittlungsserver durchgeführte Medienverarbeitung)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|
|:-----|:-----|
|Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 GHz oder höher, mit 64 GB Arbeitsspeicher und 2 1 GB Netzwerkadapterkarten.  <br/> |200  <br/> |

> [!NOTE]
> Diese Zahl ist viel kleiner als die Zahlen für den eigenständigen Vermittlungsserver. Der Grund dafür ist, dass der Front-End-Server neben der für Sprachanrufe erforderlichen Transcodierung auch andere Features und Funktionen für die 6600 Benutzer verarbeiten muss, die darauf verwaltet werden.

> [!NOTE]
> Um die Leistung des Vermittlungsservers zu verbessern, sollten Sie RSS (Receive-Side Scaling) auf den Netzwerkadaptern auf Ihren Vermittlungsservern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter["Receive-Side Scaling in Windows Server 2012".](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="back-end-server"></a>Back-End-Server

Obwohl ein Großteil der Datenbankinformationen hauptsächlich auf den Front-End-Servern gespeichert wird, sollten Sie sicherstellen, dass Ihre Back-End-Server die weiter oben in diesem Abschnitt und in [den Serverhardwareplattformen aufgeführten](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)Hardwareempfehlungen erfüllen.

Um eine hohe Verfügbarkeit ihres Back-End-Servers zu gewährleisten, empfehlen wir die Bereitstellung von AlwaysOn-Verfügbarkeitsgruppen oder Serverspiegelung. Weitere Informationen finden Sie unter [Back-End-Server hohe Verfügbarkeit in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

Wenn Sie die Überwachung oder Archivierung bereitstellen, wird die Front-End-Funktion dieser Dienste auf den Front-End-Servern ausgeführt. Überwachung und Archivierung verwenden jeweils einen eigenen Datenbankspeicher, getrennt vom Back-End-Speicher. Wenn Sie Exchange 2013 bereitgestellt haben, können Sie auch Archivierungsdaten für Chatnachrichten in Exchange statt in einem dedizierten SQL speicher speichern.

Die folgende Tabelle gibt an, wie viel Datenbankspeicher pro Benutzer und Tag für Überwachungs- und Archivierungsdaten erforderlich ist.

||**KDS (Überwachung)** <br/> |**QoE (Überwachung)** <br/> |**Archivierung** <br/> |
|:-----|:-----|:-----|:-----|
|Pro Benutzer und Tag erforderlicher Speicherplatz  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft hat die Hardware in der folgenden Tabelle für den Datenbankserver zur Überwachung und Archivierung während der Leistungstests verwendet. Bei den Tests wurden die Daten von zwei Front-End-Pools gesammelt, von denen jeder 80.000 Benutzer enthielt.

**Bei Überwachungs- und Archivierungsleistungstests verwendete Hardware**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 GHz oder höher.  <br/> |
|Arbeitsspeicher  <br/> |48 GB  <br/> |
|Datenträger  <br/> | Entweder:<br/> • Mindestens 4 Festplattenlaufwerke mit 10.000 U/min mit mindestens 72 GB freiem Speicherplatz (die Datenträger sollten in einer 2x RAID 1-Konfiguration vorhanden sein). <br/>ODER <br/>• SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 4 1.000 U/min bereitstellen können.   <br/> |
|Netzwerk  <br/> | 1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 empfohlen, was eine Teamerstellung mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erfordert).  <br/> |

**Empfohlene Datenträgerkonfigurationen**

|**Laufwerk** <br/> |**RAID-Konfiguration** <br/> |**Anzahl der Datenträger** <br/> |
|:-----|:-----|:-----|
|KDS-, QoE- und Archivierungsdatenbankdatendateien auf einem einzelnen Laufwerk  <br/> |1+0  <br/> |16   <br/> |
|KDS-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|QoE-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|Archivierungsdatenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Kapazität des Video-Interoperabilität-Servers

Wenn Sie den Video-Interoperabilitätsserver bereitstellen und die Kapazität ermitteln müssen, sehen Sie sich die maximale Anzahl von Videotelekonferenzsystemen (Video Teleconferencing Systems, VTCs) an, die sich in gleichzeitigen Anrufen befinden. Wenn Sie beispielsweise 250 VTCs in Ihrer Organisation haben und Ihr Benutzermodell davon aus geht, dass maximal 20 % davon in gleichzeitigen Anrufen vorhanden sein können, basieren Sie ihre Kapazitätsplanung auf 50 gleichzeitigen VTCs.